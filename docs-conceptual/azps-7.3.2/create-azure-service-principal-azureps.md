---
description: Pelajari cara membuat dan menggunakan perwakilan layanan dengan Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 03/12/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Menggunakan perwakilan layanan Azure dengan Azure PowerShell
ms.openlocfilehash: 907983b422220f0eaf5fdfd2b4de6d8d69ad3abc
ms.sourcegitcommit: b346b2fbd8b25f54759984e75ddbee3304921c43
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2022
ms.locfileid: "140662923"
---
# <a name="create-an-azure-service-principal-with-azure-powershell"></a>Membuat prinsipal layanan Azure dengan Microsoft Azure PowerShell

Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Sebagai alternatif membuat aplikasi masuk sebagai pengguna dengan hak istimewa penuh, Azure menawarkan perwakilan layanan.

Perwakilan layanan Azure adalah identitas yang dibuat untuk digunakan dengan aplikasi, layanan yang dihosting, dan alat otomatis untuk mengakses sumber daya Azure. Akses ini dibatasi oleh peran yang ditetapkan untuk perwakilan layanan, yang memberi Anda kontrol atas sumber daya mana yang dapat diakses dan pada tingkat mana. Untuk alasan keamanan, selalu disarankan untuk menggunakan perwakilan layanan dengan alat otomatis dibanding mengizinkan mereka masuk dengan identitas pengguna.

Artikel ini berisi langkah-langkah untuk membuat, mendapatkan informasi tentang, dan mengatur ulang perwakilan layanan dengan Azure PowerShell.

> [!WARNING]
> Saat Anda membuat perwakilan layanan menggunakan perintah [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal), output akan menyertakan info masuk yang harus dilindungi. Sebagai alternatif, pertimbangkan untuk menggunakan [identitas terkelola](/azure/active-directory/managed-identities-azure-resources/overview) untuk mencegah penggunaan info masuk.

## <a name="create-a-service-principal"></a>Buat perwakilan layanan

Buat perwakilan layanan dengan cmdlet [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal). Saat membuat perwakilan layanan, pilih jenis autentikasi masuk yang digunakannya.

> [!IMPORTANT]
> Dimulai dengan modul Az PowerShell versi 7.x, [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal) tidak lagi menetapkan peran [Kontributor](/azure/role-based-access-control/built-in-roles#contributor) ke perwakilan layanan secara default. Untuk menetapkan peran tertentu ke perwakilan layanan, lihat [Langkah untuk menambahkan penetapan peran](/azure/role-based-access-control/role-assignments-steps).

> [!NOTE]
> Jika akun Anda tidak memiliki izin untuk membuat perwakilan layanan, `New-AzADServicePrincipal` akan menampilkan pesan kesalahan yang berisi "Hak istimewa tidak memadai untuk menyelesaikan operasi".
> Hubungi admin Azure Active Directory Anda untuk membuat perwakilan layanan.

Ada dua jenis autentikasi yang tersedia untuk perwakilan layanan: Autentikasi berbasis kata sandi dan autentikasi berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

> [!IMPORTANT]
> Peran default untuk perwakilan layanan autentikasi berbasis kata sandi adalah **Kontributor**. Peran ini memiliki izin penuh untuk membaca dan menulis ke akun Azure. Untuk informasi tentang mengelola penetapan peran, lihat [Mengelola peran perwakilan layanan](#manage-service-principal-roles).

Tanpa parameter autentikasi lainnya, autentikasi berbasis kata sandi digunakan dan kata sandi acak yang dibuat untuk Anda. Jika Anda menginginkan autentikasi berbasis kata sandi, metode ini disarankan.

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

Objek yang ditampilkan berisi properti `PasswordCredentials.SecretText` yang berisi kata sandi yang dibuat. Pastikan Anda menyimpan nilai ini di suatu tempat yang aman untuk diautentikasi dengan perwakilan layanan. Nilainya _tidak akan_ ditampilkan di output konsol. Jika lupa kata sandi, [atur ulang info masuk perwakilan layanan](#reset-credentials).

Kode berikut akan memungkinkan Anda mengekspor rahasia:

```powershell-interactive
$sp.PasswordCredentials.SecretText
```

Objek yang dikembalikan dari `New-AzADServicePrincipal` berisi `Id` dan `DisplayName` anggota, yang keduanya dapat digunakan untuk masuk dengan perwakilan layanan.

> [!IMPORTANT]
> Masuk dengan perwakilan layanan memerlukan ID penyewa tempat perwakilan layanan dibuat. Untuk mendapatkan penyewa aktif saat perwakilan layanan dibuat, jalankan perintah berikut _segera setelah_ pembuatan perwakilan layanan:

```azurepowershell-interactive
(Get-AzContext).Tenant.Id
```

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

> [!IMPORTANT]
> Tidak ada peran default yang ditetapkan saat membuat perwakilan layanan autentikasi berbasis sertifikat. Untuk informasi tentang mengelola penetapan peran, lihat [Mengelola peran perwakilan layanan](#manage-service-principal-roles).

Perwakilan layanan yang menggunakan autentikasi berbasis sertifikat dibuat dengan parameter `CertValue`. Parameter ini mengambil string ASCII yang dikodekan base64 dari sertifikat publik. Ini diwakili oleh file PEM, atau CRT atau CER yang dikodekan teks. Pengodean biner dari sertifikat publik tidak didukung. Instruksi ini mengasumsikan bahwa Anda sudah memiliki sertifikat yang tersedia.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -CertValue $cert
```

Objek yang dikembalikan dari `New-AzADServicePrincipal` berisi properti `Id` dan `DisplayName`, yang keduanya dapat digunakan untuk masuk dengan perwakilan layanan. Klien yang masuk dengan perwakilan layanan juga memerlukan akses ke kunci privat sertifikat.

> [!IMPORTANT]
> Masuk dengan perwakilan layanan memerlukan ID penyewa tempat perwakilan layanan dibuat. Untuk mendapatkan penyewa aktif saat perwakilan layanan dibuat, jalankan perintah berikut _segera setelah_ pembuatan perwakilan layanan:

```azurepowershell-interactive
(Get-AzContext).Tenant.Id
```

## <a name="get-an-existing-service-principal"></a>Mendapatkan perwakilan layanan yang ada

Daftar perwakilan layanan untuk penyewa aktif dapat diambil dengan [Get-AzADServicePrincipal](/powershell/module/az.resources/get-azadserviceprincipal). Secara default perintah ini mengembalikan _semua_ perwakilan layanan di penyewa. Untuk organisasi besar, mungkin perlu waktu lama untuk mengembalikan hasil. Sebagai gantinya, menggunakan salah satu argumen pemfilteran sisi server opsional disarankan:

- `DisplayNameBeginsWith` meminta perwakilan layanan yang memiliki _awalan_ yang sesuai dengan nama yang disediakan. Nama tampilan perwakilan layanan adalah nilai yang ditetapkan dengan parameter `DisplayName` selama pembuatan.
- `DisplayName` meminta _kecocokan yang tepat_ dari nama perwakilan layanan.

## <a name="manage-service-principal-roles"></a>Kelola peran perwakilan layanan

Azure PowerShell memiliki cmdlet berikut untuk mengelola penetapan peran:

- [Get-AzRoleAssignment](/powershell/module/az.resources/get-azroleassignment)
- [New-AzRoleAssignment](/powershell/module/az.resources/new-azroleassignment)
- [Remove-AzRoleAssignment](/powershell/module/az.resources/remove-azroleassignment)

Untuk informasi selengkapnya tentang Kontrol Akses Berbasis Peran (RBAC) dan peran, lihat [RBAC: Peran bawaan](/azure/active-directory/role-based-access-built-in-roles).

Contoh berikut menambahkan peran **Pembaca** dan menghapus peran **Kontributor**:

```azurepowershell-interactive
New-AzRoleAssignment -ApplicationId <service principal application ID> -RoleDefinitionName 'Reader'
Remove-AzRoleAssignment -ObjectId <service principal object ID> -RoleDefinitionName 'Contributor'
```

> [!IMPORTANT]
> Cmdlet penetapan peran tidak mengambil ID objek perwakilan layanan. Cmdlet mengambil ID aplikasi terkait, yang dibuat pada waktu pembuatan. Untuk mendapatkan ID aplikasi untuk perwakilan layanan, gunakan `Get-AzADServicePrincipal`.

> [!NOTE]
> Jika akun Anda tidak memiliki izin untuk menetapkan peran, Anda akan melihat pesan kesalahan bahwa akun Anda "tidak memiliki otorisasi untuk melakukan tindakan 'Microsoft.Authorization/roleAssignments/write'". Hubungi admin Azure Active Directory Anda untuk mengelola peran.

Penambahan peran _tidak_ membatasi izin yang ditetapkan sebelumnya. Jika izin perwakilan layanan dibatasi, peran **Kontributor** akan dihapus.

Perubahan ini dapat diverifikasi dengan mencantumkan peran yang ditetapkan:

```azurepowershell-interactive
Get-AzRoleAssignment -ServicePrincipalName ServicePrincipalName
```

## <a name="sign-in-using-a-service-principal"></a>Masuk menggunakan perwakilan layanan

Uji info masuk dan izin perwakilan layanan baru dengan masuk. Untuk masuk dengan perwakilan layanan, Anda memerlukan nilai `applicationId` yang terkait dengannya, dan penyewa tempatnya dibuat.

Untuk masuk dengan perwakilan layanan menggunakan kata sandi:

```azurepowershell-interactive
# Use the application ID as the username, and the secret as password
$credentials = Get-Credential
Connect-AzAccount -ServicePrincipal -Credential $credentials -Tenant <tenant ID>
```

Autentikasi berbasis sertifikat mengharuskan Azure PowerShell dapat mengambil informasi dari penyimpanan sertifikat lokal berdasarkan thumbprint sertifikat.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -Tenant <TenantId> -CertificateThumbprint <Thumbprint> -ApplicationId <ApplicationId>
```

Untuk petunjuk tentang mengimpor sertifikat ke penyimpanan info masuk yang dapat diakses oleh PowerShell, lihat [Masuk dengan Azure PowerShell](authenticate-azureps.md#sign-in-with-a-service-principal)

## <a name="reset-credentials"></a>Mengatur ulang info masuk

Jika Anda lupa info masuk untuk perwakilan layanan, gunakan [New-AzADSpCredential](/powershell/module/az.resources/new-azadspcredential) untuk menambahkan info masuk baru dengan kata sandi acak. Cmdlet ini tidak mendukung info masuk yang ditentukan pengguna saat mengatur ulang kata sandi.

> [!IMPORTANT]
> Sebelum menetapkan info masuk baru, Anda mungkin ingin menghapus info masuk yang ada untuk mencegah masuk dengannya. Untuk melakukannya, gunakan cmdlet [Remove-AzADSpCredential](/powershell/module/az.resources/remove-azadspcredential):

```azurepowershell-interactive
Remove-AzADSpCredential -DisplayName ServicePrincipalName
```

```azurepowershell-interactive
$newCredential = New-AzADSpCredential -ServicePrincipalName ServicePrincipalName
```

## <a name="troubleshooting"></a>Pemecahan Masalah

Jika Anda menerima kesalahan: _"New-AzADServicePrincipal: Objek lain dengan nilai yang sama untuk properti propertiUris sudah ada."_ , verifikasi bahwa perwakilan layanan dengan nama yang sama belum ada.

```azurepowershell-interactive
Get-AzAdServicePrincipal -DisplayName ServicePrincipalName
```

Jika perwakilan layanan yang ada tidak lagi diperlukan, Anda dapat menghapusnya menggunakan contoh berikut.

```azurepowershell-interactive
Remove-AzAdServicePrincipal -DisplayName ServicePrincipalName
```

Kesalahan ini juga dapat terjadi saat Anda sebelumnya telah membuat perwakilan layanan untuk aplikasi Azure Active Directory. Jika Anda menghapus perwakilan layanan, aplikasi masih tersedia. Aplikasi ini mencegah Anda membuat perwakilan layanan lain dengan nama yang sama.

Anda dapat menggunakan contoh berikut untuk memverifikasi bahwa aplikasi Azure Active Directory dengan nama yang sama tidak ada:

```azurepowershell-interactive
Get-AzADApplication -DisplayName ServicePrincipalName
```

Jika aplikasi dengan nama yang sama memang ada dan tidak diperlukan lagi, aplikasi tersebut dapat dihapus menggunakan contoh berikut.

```azurepowershell-interactive
Remove-AzADApplication -DisplayName ServicePrincipalName
```

Jika tidak, pilih nama alternatif untuk perwakilan layanan baru yang ingin dibuat.
