---
title: Menggunakan prinsipal layanan Azure dengan Azure PowerShell
description: Pelajari cara membuat dan menggunakan prinsipal layanan dengan Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.service: azure-powershell
ms.date: 01/06/2022
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 8bee19b6626d5f9db547f756336fe8e91ec23a52
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335115"
---
# <a name="create-an-azure-service-principal-with-azure-powershell"></a>Membuat prinsipal layanan Azure dengan Microsoft Azure PowerShell

Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Alih-alih memiliki aplikasi masuk sebagai pengguna yang sepenuhnya istimewa, Azure menawarkan prinsipal layanan.

Prinsipal layanan Azure adalah identitas yang dibuat untuk digunakan dengan aplikasi, layanan yang dihosting, dan alat otomatis untuk mengakses sumber daya Azure. Akses ini dibatasi oleh peran yang ditetapkan untuk kepala layanan, memberi Anda kontrol atas sumber daya mana yang dapat diakses dan pada tingkat mana. Untuk alasan keamanan, selalu disarankan untuk menggunakan perwakilan layanan dengan alat otomatis dibanding mengizinkan mereka masuk dengan identitas pengguna.

Artikel ini menunjukkan kepada Anda langkah-langkah untuk membuat, mendapatkan informasi tentang, dan mengatur ulang prinsipal layanan dengan Azure PowerShell.

> [!WARNING]
> Saat Anda membuat prinsipal layanan menggunakan perintah [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal) , output menyertakan kredensial yang harus Anda lindungi. Sebagai alternatif, pertimbangkan untuk menggunakan [identitas terkelola](/azure/active-directory/managed-identities-azure-resources/overview) untuk menghindari kebutuhan untuk menggunakan kredensial.

## <a name="create-a-service-principal"></a>Buat perwakilan layanan

Buat prinsipal layanan dengan cmdlet [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal) . Saat membuat prinsipal layanan, Anda memilih jenis autentikasi masuk yang digunakannya.

> [!IMPORTANT]
> Dimulai dengan modul Az PowerShell versi 7.x, [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal) tidak lagi menetapkan peran [Kontributor](/azure/role-based-access-control/built-in-roles#contributor) ke prinsipal layanan secara default. Untuk menetapkan peran tertentu ke prinsipal layanan, lihat [Langkah-langkah untuk menambahkan penetapan peran](/azure/role-based-access-control/role-assignments-steps).

> [!NOTE]
> Jika akun Anda tidak memiliki izin untuk membuat prinsipal layanan, `New-AzADServicePrincipal` akan mengembalikan pesan kesalahan yang berisi "Hak istimewa yang tidak mencukupi untuk menyelesaikan operasi".
> Hubungi admin Azure Active Directory Anda untuk membuat prinsipal layanan.

Ada dua jenis otentikasi yang tersedia untuk prinsipal layanan: otentikasi berbasis kata sandi, dan otentikasi berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

> [!IMPORTANT]
> Peran default untuk prinsipal layanan autentikasi berbasis kata sandi adalah **Kontributor**. Peran ini memiliki izin penuh untuk membaca dan menulis ke akun Azure. Untuk informasi tentang mengelola tugas peran, lihat [Mengelola peran utama layanan](#manage-service-principal-roles).

Tanpa parameter otentikasi lainnya, otentikasi berbasis kata sandi digunakan dan kata sandi acak yang dibuat untuk Anda. Jika Anda menginginkan autentikasi berbasis kata sandi, metode ini disarankan.

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

Objek yang `PasswordCredentials.SecretText` dikembalikan berisi properti yang berisi kata sandi yang dihasilkan. Pastikan Anda menyimpan nilai ini di tempat yang aman untuk diautentikasi dengan prinsipal layanan. Nilainya _tidak_ akan ditampilkan dalam output konsol. Jika Anda kehilangan kata sandi, [atur ulang kredensial utama layanan](#reset-credentials).

Kode berikut akan memungkinkan Anda untuk mengekspor rahasia:

```powershell-interactive
$sp.PasswordCredentials.SecretText
```

Objek yang dikembalikan berisi `New-AzADServicePrincipal` `Id` dan `DisplayName` anggota, yang keduanya dapat digunakan untuk masuk dengan kepala layanan.

> [!IMPORTANT]
> Masuk dengan prinsipal layanan memerlukan ID penyewa tempat kepala layanan dibuat. Untuk mendapatkan penyewa aktif saat prinsipal layanan dibuat, jalankan perintah berikut _segera setelah_ pembuatan utama layanan:

```azurepowershell-interactive
(Get-AzContext).Tenant.Id
```

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

> [!IMPORTANT]
> Tidak ada peran default yang ditetapkan saat membuat prinsip layanan autentikasi berbasis sertifikat. Untuk informasi tentang mengelola tugas peran, lihat [Mengelola peran utama layanan](#manage-service-principal-roles).

Prinsipal layanan yang menggunakan autentikasi berbasis sertifikat dibuat dengan `CertValue` parameter. Parameter ini mengambil string ASCII yang dikodekan basis64 dari sertifikat publik. Ini diwakili oleh file PEM, atau CRT atau CER yang dikodekan teks. Pengkodean biner dari sertifikat publik tidak didukung. Instruksi ini mengasumsikan bahwa Anda sudah memiliki sertifikat yang tersedia.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -CertValue $cert
```

Objek yang dikembalikan berisi `New-AzADServicePrincipal` `Id` properti dan `DisplayName` properti, yang keduanya dapat digunakan untuk masuk dengan prinsipal layanan. Klien yang masuk dengan prinsipal layanan juga memerlukan akses ke kunci pribadi sertifikat.

> [!IMPORTANT]
> Masuk dengan prinsipal layanan memerlukan ID penyewa tempat kepala layanan dibuat. Untuk mendapatkan penyewa aktif saat prinsipal layanan dibuat, jalankan perintah berikut _segera setelah_ pembuatan utama layanan:

```azurepowershell-interactive
(Get-AzContext).Tenant.Id
```

## <a name="get-an-existing-service-principal"></a>Dapatkan prinsipal layanan yang ada

Daftar prinsipal layanan untuk penyewa aktif dapat diambil dengan [Get-AzADServicePrincipal](/powershell/module/az.resources/get-azadserviceprincipal). Secara default perintah ini mengembalikan _semua_ prinsipal layanan di penyewa. Untuk organisasi besar, mungkin perlu waktu lama untuk mengembalikan hasil. Sebagai gantinya, menggunakan salah satu argumen pemfilteran sisi server opsional dianjurkan:

- `DisplayNameBeginsWith` meminta prinsipal layanan yang memiliki _awalan_ yang sesuai dengan nilai yang disediakan. Nama tampilan prinsipal layanan adalah nilai yang ditetapkan `DisplayName` selama pembuatan.
- `DisplayName` meminta _kecocokan yang tepat_ dari nama utama layanan.

## <a name="manage-service-principal-roles"></a>Mengelola peran utama layanan

Azure PowerShell memiliki cmdlet berikut untuk mengelola tugas peran:

- [Get-AzRoleAssignment](/powershell/module/az.resources/get-azroleassignment)
- [New-AzRoleAssignment](/powershell/module/az.resources/new-azroleassignment)
- [Remove-AzRoleAssignment](/powershell/module/az.resources/remove-azroleassignment)

Untuk informasi selengkapnya tentang kontrol akses Role-Based (RBAC) dan peran, lihat [RBAC: Peran bawaan](/azure/active-directory/role-based-access-built-in-roles).

Contoh berikut menambahkan peran **Pembaca** dan menghapus peran **Kontributor** :

```azurepowershell-interactive
New-AzRoleAssignment -ApplicationId <service principal application ID> -RoleDefinitionName 'Reader'
Remove-AzRoleAssignment -ObjectId <service principal object ID> -RoleDefinitionName 'Contributor'
```

> [!IMPORTANT]
> Cmdlet penetapan peran tidak mengambil ID objek utama layanan. Mereka mengambil ID aplikasi terkait, yang dihasilkan pada waktu pembuatan. Untuk mendapatkan ID aplikasi untuk prinsipal layanan, gunakan `Get-AzADServicePrincipal`.

> [!NOTE]
> Jika akun Anda tidak memiliki izin untuk menetapkan peran, Anda akan melihat pesan kesalahan bahwa akun Anda "tidak memiliki otorisasi untuk melakukan tindakan 'Microsoft.Authorization/roleAssignments/write'". Hubungi admin Azure Active Directory Anda untuk mengelola peran.

Menambahkan peran _tidak_ membatasi izin yang ditetapkan sebelumnya. Saat membatasi izin prinsipal layanan, peran **Kontributor** harus dihapus.

Perubahan dapat diverifikasi dengan mencantumkan peran yang ditetapkan:

```azurepowershell-interactive
Get-AzRoleAssignment -ServicePrincipalName ServicePrincipalName
```

## <a name="sign-in-using-a-service-principal"></a>Masuk menggunakan prinsipal layanan

Uji kredensial dan izin prinsipal layanan baru dengan masuk. Untuk masuk dengan prinsipal layanan, Anda memerlukan nilai yang `applicationId` terkait dengannya, dan penyewa tempat ia dibuat di bawahnya.

Untuk masuk dengan prinsipal layanan menggunakan kata sandi:

```azurepowershell-interactive
# Use the application ID as the username, and the secret as password
$credentials = Get-Credential
Connect-AzAccount -ServicePrincipal -Credential $credentials -Tenant <tenant ID>
```

Otentikasi berbasis sertifikat mengharuskan Azure PowerShell dapat mengambil informasi dari toko sertifikat lokal berdasarkan cap jempol sertifikat.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -Tenant <TenantId> -CertificateThumbprint <Thumbprint> -ApplicationId <ApplicationId>
```

Untuk petunjuk tentang mengimpor sertifikat ke toko kredensial yang dapat diakses oleh PowerShell, lihat [Masuk dengan Azure PowerShell](authenticate-azureps.md#sign-in-with-a-service-principal)

## <a name="reset-credentials"></a>Mengatur ulang info masuk

Jika Anda lupa kredensial untuk prinsipal layanan, gunakan [New-AzADSpCredential](/powershell/module/az.resources/new-azadspcredential) untuk menambahkan kredensial baru dengan kata sandi acak. Cmdlet ini tidak mendukung kredensial yang ditentukan pengguna saat mengatur ulang kata sandi.

> [!IMPORTANT]
> Sebelum menetapkan kredensial baru, Anda mungkin ingin menghapus kredensial yang ada untuk mencegah masuk dengan mereka. Untuk melakukannya, gunakan cmdlet [Remove-AzADSpCredential](/powershell/module/az.resources/remove-azadspcredential) :

```azurepowershell-interactive
Remove-AzADSpCredential -DisplayName ServicePrincipalName
```

```azurepowershell-interactive
$newCredential = New-AzADSpCredential -ServicePrincipalName ServicePrincipalName
```

## <a name="troubleshooting"></a>Pemecahan Masalah

Jika Anda menerima kesalahan: _"New-AzADServicePrincipal: Objek lain dengan nilai yang sama untuk pengidentifikasi propertiUris sudah ada."_, verifikasi bahwa prinsipal layanan dengan nama yang sama belum ada.

```azurepowershell-interactive
Get-AzAdServicePrincipal -DisplayName ServicePrincipalName
```

Jika prinsipal layanan yang ada tidak lagi diperlukan, Anda dapat menghapusnya menggunakan contoh berikut.

```azurepowershell-interactive
Remove-AzAdServicePrincipal -DisplayName ServicePrincipalName
```

Kesalahan ini juga dapat terjadi ketika Anda sebelumnya telah membuat prinsipal layanan untuk aplikasi Azure Active Directory. Jika Anda menghapus prinsipal layanan, aplikasi masih tersedia. Aplikasi ini mencegah Anda membuat prinsipal layanan lain dengan nama yang sama.

Anda dapat menggunakan contoh berikut untuk memverifikasi bahwa aplikasi Azure Active Directory dengan nama yang sama tidak ada:

```azurepowershell-interactive
Get-AzADApplication -DisplayName ServicePrincipalName
```

Jika aplikasi dengan nama yang sama memang ada dan tidak lagi diperlukan, aplikasi tersebut dapat dihapus menggunakan contoh berikut.

```azurepowershell-interactive
Remove-AzADApplication -DisplayName ServicePrincipalName
```

Jika tidak, pilih nama alternatif untuk prinsipal layanan baru yang ingin Anda buat.
