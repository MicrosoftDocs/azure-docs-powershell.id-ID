---
title: Menggunakan prinsipal layanan Azure dengan Azure PowerShell
description: Pelajari cara membuat dan menggunakan prinsipal layanan dengan Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.service: azure-powershell
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 8f2a2f546086f2b475835b46017083271a990c5b
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "134026024"
---
# <a name="create-an-azure-service-principal-with-azure-powershell"></a>Membuat prinsipal layanan Azure dengan Azure PowerShell

Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Sebagai ganti mendapatkan akses masuk aplikasi sebagai pengguna dengan hak istimewa penuh, Azure menawarkan prinsipal layanan.

Prinsipal layanan Azure adalah identitas yang dibuat untuk digunakan dengan aplikasi, layanan yang dihosting, dan alat otomatis untuk mengakses sumber daya Azure. Akses ini dibatasi oleh peran yang ditetapkan untuk prinsipal layanan, yang memberi Anda kontrol atas sumber daya mana yang dapat diakses dan di tingkat mana. Untuk alasan keamanan, selalu disarankan untuk menggunakan prinsipal layanan dengan alat otomatis daripada memperbolehkan mereka untuk masuk dengan identitas pengguna.

Artikel ini memperlihatkan langkah-langkah untuk membuat, mendapatkan informasi tentang, dan mereset prinsipal layanan dengan Azure PowerShell.

> [!WARNING]
> Ketika Anda membuat prinsipal layanan menggunakan [perintah New-AzADServicePrincipal,](/powershell/module/Az.Resources/New-AzADServicePrincipal) output menyertakan kredensial yang harus Anda proteksi. Sebagai alternatif, pertimbangkan [menggunakan identitas terkelola](/azure/active-directory/managed-identities-azure-resources/overview) untuk menghindari perlu menggunakan kredensial.
>
> Secara default, [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal) menetapkan peran [Kontributor](/azure/role-based-access-control/built-in-roles#contributor) pada prinsipal layanan pada lingkup langganan. Untuk mengurangi risiko prinsipal layanan yang dibobol, tetapkan peran yang lebih spesifik dan persempit lingkupnya pada grup sumber daya atau sumber daya. Lihat [Langkah-langkah untuk menambahkan penetapan peran](/azure/role-based-access-control/role-assignments-steps) untuk informasi selengkapnya.

## <a name="create-a-service-principal"></a>Membuat prinsipal layanan

Buat prinsipal layanan dengan cmdlet [New-AzADServicePrincipal.](/powershell/module/Az.Resources/New-AzADServicePrincipal) Saat membuat prinsipal layanan, Anda memilih tipe autentikasi masuk yang digunakannya.

> [!NOTE]
> Jika akun Anda tidak memiliki izin untuk membuat prinsipal layanan, akan mengembalikan pesan kesalahan yang berisi "Hak istimewa `New-AzADServicePrincipal` yang kurang untuk menyelesaikan operasi".
> Hubungi admin Azure Active Directory untuk membuat pokok layanan.

Ada dua tipe autentikasi yang tersedia untuk prinsipal layanan: Autentikasi berbasis kata sandi, dan autentikasi berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

> [!IMPORTANT]
> Peran default untuk prinsipal layanan autentikasi berbasis kata sandi adalah **Kontributor.** Peran ini memiliki izin penuh untuk membaca dan menulis ke akun Azure. Untuk informasi tentang mengelola penetapan peran, lihat [Mengelola peran utama layanan](#manage-service-principal-roles).

Tanpa parameter autentikasi lainnya, autentikasi berbasis kata sandi digunakan dan kata sandi acak yang dibuat untuk Anda. Jika Anda menginginkan autentikasi berbasis kata sandi, metode ini disarankan.

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

Objek yang dikembalikan berisi `Secret` anggota, yang berisi `SecureString` kata sandi yang dihasilkan. Pastikan Anda menyimpan nilai ini di suatu tempat yang aman untuk diautentikasi dengan prinsipal layanan. Nilainya _tidak akan_ ditampilkan dalam output konsol. Jika Anda kehilangan kata sandi, [reset kredensial prinsipal layanan](#reset-credentials).

Kode berikut akan memungkinkan Anda mengekspor rahasianya:

```powershell-interactive
$BSTR = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($sp.Secret)
$UnsecureSecret = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($BSTR)
```

Untuk kata sandi yang diberikan pengguna, `PasswordCredential` parameter mengambil `Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential` objek. Objek tersebut harus memiliki teks yang valid `StartDate` dan , serta menggunakan teks `EndDate` `Password` biasa. Saat membuat kata sandi, pastikan Anda mengikuti aturan [Azure Active Directory kata sandi dan pembatasan](/azure/active-directory/active-directory-passwords-policy).
Jangan gunakan kata sandi yang lemah atau gunakan kembali kata sandi.

```azurepowershell-interactive
Import-Module -Name Az.Resources # Imports the PSADPasswordCredential object
$credentials = New-Object Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential -Property @{StartDate=Get-Date; EndDate=Get-Date -Year 2024; Password=<Choose a strong password>}
$sp = New-AzAdServicePrincipal -DisplayName ServicePrincipalName -PasswordCredential $credentials
```

Objek yang dikembalikan dari memuat dan anggota, yang mana salah satu `New-AzADServicePrincipal` dapat digunakan untuk masuk dengan `Id` `DisplayName` prinsipal layanan.

> [!IMPORTANT]
> Masuk dengan prinsipal layanan memerlukan ID penyewa tempat prinsipal layanan dibuat. Untuk mendapatkan penyewa aktif ketika prinsipal layanan dibuat, jalankan perintah berikut segera _setelah pembuatan_ prinsipal layanan:

```azurepowershell-interactive
(Get-AzContext).Tenant.Id
```

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

> [!IMPORTANT]
> Tidak ada peran default yang ditetapkan saat membuat prinsipal layanan autentikasi berbasis sertifikat. Untuk informasi tentang mengelola penetapan peran, lihat [Mengelola peran utama layanan](#manage-service-principal-roles).

Prinsipal layanan yang menggunakan autentikasi berbasis sertifikat dibuat dengan `CertValue` parameter. Parameter ini menggunakan string ASCII yang dikodekan basis64 dari sertifikat publik. Ini ditunjukkan oleh file PEM, atau CRT atau CER berkode teks. Pengodean biner sertifikat publik tidak didukung. Instruksi ini mengasumsikan bahwa Anda sudah memiliki sertifikat yang tersedia.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -CertValue $cert
```

Anda juga bisa menggunakan `KeyCredential` parameter, yang mengambil `PSADKeyCredential` objek. Objek ini harus memiliki string ASCII yang valid , , dan telah diatur anggota ke `StartDate` string ASCII yang dikodekan `EndDate` `CertValue` basis64 dari sertifikat publik.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$credentials = New-Object -TypeName Microsoft.Azure.Commands.ActiveDirectory.PSADKeyCredential -Property @{StartDate=Get-Date; EndDate=Get-Date -Year 2024; KeyId=New-Guid; CertValue=$cert}
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -KeyCredential $credentials
```

Objek yang dikembalikan dari memuat dan anggota, yang mana salah satu `New-AzADServicePrincipal` dapat digunakan untuk masuk dengan `Id` `DisplayName` prinsipal layanan. Klien yang masuk dengan prinsipal layanan juga memerlukan akses ke kunci privat sertifikat.

> [!IMPORTANT]
> Masuk dengan prinsipal layanan memerlukan ID penyewa tempat prinsipal layanan dibuat. Untuk mendapatkan penyewa aktif ketika prinsipal layanan dibuat, jalankan perintah berikut segera _setelah pembuatan_ prinsipal layanan:

```azurepowershell-interactive
(Get-AzContext).Tenant.Id
```

## <a name="get-an-existing-service-principal"></a>Dapatkan prinsipal layanan yang sudah ada

Daftar prinsipal layanan untuk penyewa aktif bisa diambil dengan [Get-AzADServicePrincipal](/powershell/module/az.resources/get-azadserviceprincipal). Secara default, perintah ini _mengembalikan_ semua prinsipal layanan dalam penyewa. Bagi organisasi besar, mungkin akan memakan waktu lama untuk mengembalikan hasil. Sebagai gantinya, gunakan salah satu argumen pemfilteran pihak server opsional disarankan:

- `DisplayNameBeginsWith` permintaan prinsipal layanan yang memiliki _prefiks_ yang cocok dengan nilai yang disediakan. Nama tampilan prinsipal layanan adalah nilai yang ditetapkan selama `DisplayName` pembuatan.
- `DisplayName` meminta yang _sama persis_ dengan nama prinsipal layanan.

## <a name="manage-service-principal-roles"></a>Mengelola peran prinsipal layanan

Azure PowerShell memiliki cmdlet berikut untuk mengelola penetapan peran:

- [Get-AzRoleAssignment](/powershell/module/az.resources/get-azroleassignment)
- [New-AzRoleAssignment](/powershell/module/az.resources/new-azroleassignment)
- [Remove-AzRoleAssignment](/powershell/module/az.resources/remove-azroleassignment)

Peran default untuk prinsipal layanan autentikasi berbasis kata sandi adalah **Kontributor.** Peran ini memiliki izin penuh untuk membaca dan menulis ke akun Azure. Peran **Pembaca** lebih terbatas, dengan akses baca-saja. Untuk informasi selengkapnya tentang Role-Based Kontrol Akses (RBAC) dan peran, lihat [RBAC: Peran bawaan](/azure/active-directory/role-based-access-built-in-roles).

Contoh ini menambahkan **peran** Pembaca dan menghapus **peran Kontributor:**

```azurepowershell-interactive
New-AzRoleAssignment -ApplicationId <service principal application ID> -RoleDefinitionName 'Reader'
Remove-AzRoleAssignment -ObjectId <service principal object ID> -RoleDefinitionName 'Contributor'
```

> [!IMPORTANT]
> Cmdlet penetapan peran tidak mengambil ID objek prinsipal layanan. Aplikasi akan mengambil ID aplikasi terkait, yang dihasilkan pada saat pembuatan. Untuk mendapatkan ID aplikasi untuk prinsipal layanan, gunakan `Get-AzADServicePrincipal` .

> [!NOTE]
> Jika akun Anda tidak memiliki izin untuk menetapkan peran, Anda melihat pesan kesalahan bahwa akun Anda "tidak memiliki otorisasi untuk melakukan tindakan 'Microsoft.Authorization/roleAssignments/write'". Hubungi admin Azure Active Directory untuk mengelola peran.

Menambahkan peran _tidak membatasi izin_ yang ditetapkan sebelumnya. Ketika membatasi izin prinsipal layanan, **peran Kontributor** harus dihapus.

Perubahan bisa diverifikasi dengan mencantumkan peran yang ditetapkan:

```azurepowershell-interactive
Get-AzRoleAssignment -ServicePrincipalName ServicePrincipalName
```

## <a name="sign-in-using-a-service-principal"></a>Masuk menggunakan prinsipal layanan

Menguji kredensial dan izin prinsipal layanan baru dengan masuk. Untuk masuk dengan prinsipal layanan, Anda memerlukan `applicationId` nilai yang terkait dengannya, dan penyewa tempat layanan tersebut dibuat.

Untuk masuk dengan prinsipal layanan menggunakan kata sandi:

```azurepowershell-interactive
# Use the application ID as the username, and the secret as password
$credentials = Get-Credential
Connect-AzAccount -ServicePrincipal -Credential $credentials -Tenant <tenant ID>
```

Autentikasi berbasis sertifikat mengharuskan Azure PowerShell mengambil informasi dari penyimpanan sertifikat lokal berdasarkan pada cetakan sertifikat.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -Tenant <TenantId> -CertificateThumbprint <Thumbprint> -ApplicationId <ApplicationId>
```

Untuk instruksi tentang mengimpor sertifikat ke penyimpanan kredensial yang dapat diakses oleh PowerShell, [lihat Masuk dengan Azure PowerShell](authenticate-azureps.md#sign-in-with-a-service-principal)

## <a name="reset-credentials"></a>Mereset kredensial

Jika Anda lupa kredensial untuk prinsipal layanan, gunakan [New-AzADSpCredential](/powershell/module/az.resources/new-azadspcredential) untuk menambahkan kredensial baru dengan kata sandi acak. Cmdlet ini tidak mendukung kredensial yang ditentukan pengguna saat mereset kata sandi.

> [!IMPORTANT]
> Sebelum menetapkan kredensial baru, Anda mungkin ingin menghapus kredensial yang sudah ada untuk mencegah masuk dengan kredensial tersebut. Untuk melakukannya, gunakan cmdlet [Remove-AzADSpCredential:](/powershell/module/az.resources/remove-azadspcredential)

```azurepowershell-interactive
Remove-AzADSpCredential -DisplayName ServicePrincipalName
```

```azurepowershell-interactive
$newCredential = New-AzADSpCredential -ServicePrincipalName ServicePrincipalName
```

## <a name="troubleshooting"></a>Pemecahan masalah

Jika Anda menerima kesalahan: _"New-AzADServicePrincipal:_ Objek lain dengan nilai yang sama untuk pengidentifikasi properti sudah ada." , verifikasi bahwa prinsipal layanan dengan nama yang sama belum ada.

```azurepowershell-interactive
Get-AzAdServicePrincipal -DisplayName ServicePrincipalName
```

Jika prinsipal layanan yang ada tidak lagi diperlukan, Anda dapat menghapusnya menggunakan contoh berikut.

```azurepowershell-interactive
Remove-AzAdServicePrincipal -DisplayName ServicePrincipalName
```

Kesalahan ini juga dapat terjadi ketika Anda sebelumnya telah membuat prinsipal layanan untuk Azure Active Directory ini. Jika Anda menghapus prinsipal layanan, aplikasi masih tersedia. Aplikasi ini mencegah Anda membuat prinsipal layanan lain dengan nama yang sama.

Anda bisa menggunakan contoh berikut untuk memverifikasi bahwa Azure Active Directory aplikasi dengan nama yang sama tidak ada:

```azurepowershell-interactive
Get-AzADApplication -DisplayName ServicePrincipalName
```

Jika ada aplikasi dengan nama yang sama dan tidak lagi diperlukan, aplikasi dapat dihapus menggunakan contoh berikut.

```azurepowershell-interactive
Remove-AzADApplication -DisplayName ServicePrincipalName
```

Jika tidak, pilih nama alternatif untuk prinsipal layanan baru yang sedang Anda coba buat.
