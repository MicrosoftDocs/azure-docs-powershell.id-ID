---
title: Menggunakan perwakilan layanan Azure dengan Azure PowerShell
description: Pelajari cara membuat dan menggunakan perwakilan layanan dengan Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 04/23/2019
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: adc4ab0f374cecd3ccca85cfb16aac5d77f69f41
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428000"
---
# <a name="create-an-azure-service-principal-with-azure-powershell"></a>Membuat prinsipal layanan Azure dengan Microsoft Azure PowerShell

Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Sebagai alternatif membuat aplikasi masuk sebagai pengguna dengan hak istimewa penuh, Azure menawarkan perwakilan layanan.

Perwakilan layanan Azure adalah identitas yang dibuat untuk digunakan dengan aplikasi, layanan yang dihosting, dan alat otomatis untuk mengakses sumber daya Azure. Akses ini dibatasi oleh peran yang ditetapkan untuk perwakilan layanan, yang memberi Anda kontrol atas sumber daya mana yang dapat diakses dan pada tingkat mana. Untuk alasan keamanan, selalu disarankan untuk menggunakan perwakilan layanan dengan alat otomatis dibanding mengizinkan mereka masuk dengan identitas pengguna.

Artikel ini berisi langkah-langkah untuk membuat, mendapatkan informasi tentang, dan mengatur ulang perwakilan layanan dengan Azure PowerShell.

## <a name="create-a-service-principal"></a>Buat perwakilan layanan

> [!WARNING]
> Saat Anda membuat perwakilan layanan menggunakan perintah [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal), output akan menyertakan info masuk yang harus dilindungi. Sebagai alternatif, pertimbangkan untuk menggunakan [identitas terkelola](/azure/active-directory/managed-identities-azure-resources/overview) untuk mencegah penggunaan info masuk.
>
> Secara default, [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal) menetapkan peran [Kontributor](/azure/role-based-access-control/built-in-roles#contributor) ke perwakilan layanan di cakupan langganan. Untuk mengurangi risiko perwakilan layanan disusupi, tetapkan peran yang lebih spesifik dan persempit cakupan ke sumber daya atau grup sumber daya. Untuk informasi selengkapnya, lihat [Langkah-langkah untuk menambahkan penetapan peran](/azure/role-based-access-control/role-assignments-steps).

Buat perwakilan layanan dengan cmdlet [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal). Saat membuat perwakilan layanan, pilih jenis autentikasi masuk yang digunakannya.

> [!NOTE]
>
> Jika akun Anda tidak memiliki izin untuk membuat perwakilan layanan, `New-AzADServicePrincipal` akan menampilkan pesan kesalahan yang berisi "Hak istimewa tidak memadai untuk menyelesaikan operasi." Hubungi admin Azure Active Directory Anda untuk membuat perwakilan layanan.

Ada dua jenis autentikasi yang tersedia untuk perwakilan layanan: Autentikasi berbasis kata sandi dan autentikasi berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

Tanpa parameter autentikasi lainnya, autentikasi berbasis kata sandi digunakan dan kata sandi acak yang dibuat untuk Anda. Jika Anda menginginkan autentikasi berbasis kata sandi, metode ini disarankan.

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

Objek yang ditampilkan berisi anggota `Secret`, yang berupa `SecureString` yang berisi kata sandi yang dibuat. Pastikan Anda menyimpan nilai ini di suatu tempat yang aman untuk diautentikasi dengan perwakilan layanan. Nilainya __tidak__ akan ditampilkan di output konsol. Jika lupa kata sandi, [atur ulang info masuk perwakilan layanan](#reset-credentials).

Kode berikut akan memungkinkan Anda mengekspor rahasia:

```azurepowershell-interactive
$BSTR = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($sp.Secret)
$UnsecureSecret = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($BSTR)
```

Untuk kata sandi yang disediakan pengguna, argumen `-PasswordCredential` mengambil objek `Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential`. Objek ini harus memiliki `StartDate` dan `EndDate` yang valid, dan mengambil teks biasa `Password`. Saat membuat kata sandi, pastikan Anda mengikuti [Aturan dan batasan kata sandi Azure Active Directory](/azure/active-directory/active-directory-passwords-policy). Jangan gunakan kata sandi yang lemah atau menggunakan kembali kata sandi.

```azurepowershell-interactive
Import-Module Az.Resources # Imports the PSADPasswordCredential object
$credentials = New-Object Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential -Property @{ StartDate=Get-Date; EndDate=Get-Date -Year 2024; Password=<Choose a strong password>}
$sp = New-AzAdServicePrincipal -DisplayName ServicePrincipalName -PasswordCredential $credentials
```

Objek yang dikembalikan dari `New-AzADServicePrincipal` berisi `Id` dan `DisplayName` anggota, yang keduanya dapat digunakan untuk masuk dengan perwakilan layanan.

> [!IMPORTANT]
>
> Masuk dengan perwakilan layanan memerlukan ID penyewa tempat perwakilan layanan dibuat. Untuk mendapatkan penyewa aktif saat perwakilan layanan dibuat, jalankan perintah berikut __segera setelah__ pembuatan perwakilan layanan:
>
> ```azurepowershell-interactive
> (Get-AzContext).Tenant.Id
> ```

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

Perwakilan layanan yang menggunakan autentikasi berbasis sertifikat dibuat dengan parameter `-CertValue`. Parameter ini mengambil string ASCII yang dikodekan base64 dari sertifikat publik. Ini diwakili oleh file PEM, atau CRT atau CER yang dikodekan teks. Pengodean biner dari sertifikat publik tidak didukung. Instruksi ini mengasumsikan bahwa Anda sudah memiliki sertifikat yang tersedia.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -CertValue $cert
```

Anda juga dapat menggunakan parameter `-KeyCredential`, yang mengambil objek `PSADKeyCredential`. Objek-objek ini harus memiliki `StartDate`, `EndDate` yang valid, dan anggota `CertValue` diatur ke string ASCII yang dikodekan base64 dari sertifikat publik.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$credentials = New-Object Microsoft.Azure.Commands.ActiveDirectory.PSADKeyCredential -Property @{ StartDate=Get-Date; EndDate=Get-Date -Year 2024; KeyId=New-Guid; CertValue=$cert}
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -KeyCredential $credentials
```

Objek yang dikembalikan dari `New-AzADServicePrincipal` berisi `Id` dan `DisplayName` anggota, yang keduanya dapat digunakan untuk masuk dengan perwakilan layanan. Klien yang masuk dengan perwakilan layanan juga memerlukan akses ke kunci privat sertifikat.

> [!IMPORTANT]
>
> Masuk dengan perwakilan layanan memerlukan ID penyewa tempat perwakilan layanan dibuat. Untuk mendapatkan penyewa aktif saat perwakilan layanan dibuat, jalankan perintah berikut __segera setelah__ pembuatan perwakilan layanan:
>
> ```azurepowershell-interactive
> (Get-AzContext).Tenant.Id
> ```

## <a name="get-an-existing-service-principal"></a>Mendapatkan perwakilan layanan yang ada

Daftar perwakilan layanan untuk penyewa yang saat ini aktif dapat diambil dengan [Get-AzADServicePrincipal](/powershell/module/az.resources/get-azadserviceprincipal). Secara default perintah ini menampilkan __semua__ perwakilan layanan di penyewa, jadi untuk organisasi besar, mungkin perlu waktu lama untuk menampilkan hasil. Sebagai gantinya, menggunakan salah satu argumen pemfilteran sisi server opsional disarankan:

* `-DisplayNameBeginsWith` meminta perwakilan layanan yang memiliki _awalan_ yang sesuai dengan nama yang disediakan. Nama tampilan perwakilan layanan adalah nilai yang ditetapkan dengan parameter `-DisplayName` selama pembuatan.
* `-DisplayName` meminta _kecocokan yang tepat_ dari nama perwakilan layanan.

## <a name="manage-service-principal-roles"></a>Kelola peran perwakilan layanan

Azure PowerShell memiliki cmdlet berikut untuk mengelola penetapan peran:

* [Get-AzRoleAssignment](/powershell/module/az.resources/get-azroleassignment)
* [New-AzRoleAssignment](/powershell/module/az.resources/new-azroleassignment)
* [Remove-AzRoleAssignment](/powershell/module/az.resources/remove-azroleassignment)

Peran default untuk perwakilan layanan adalah **Kontributor**. Peran ini memiliki izin penuh untuk membaca dan menulis ke akun Azure. Peran **Pembaca** lebih ketat, dengan akses baca-saja.  Untuk informasi selengkapnya tentang Kontrol Akses Berbasis Peran (RBAC) dan peran, lihat [RBAC: Peran bawaan](/azure/active-directory/role-based-access-built-in-roles).

Contoh ini menambahkan peran **Pembaca** dan menghapus peran **Kontributor**:

```azurepowershell-interactive
New-AzRoleAssignment -ApplicationId <service principal application ID> -RoleDefinitionName "Reader"
Remove-AzRoleAssignment -ApplicationId <service principal application ID> -RoleDefinitionName "Contributor"
```

> [!IMPORTANT]
> Cmdlet penetapan peran tidak mengambil ID objek perwakilan layanan. Cmdlet mengambil ID aplikasi terkait, yang dibuat pada waktu pembuatan. Untuk mendapatkan ID aplikasi untuk perwakilan layanan, gunakan `Get-AzADServicePrincipal`.

> [!NOTE]
> Jika akun Anda tidak memiliki izin untuk menetapkan peran, Anda akan melihat pesan kesalahan bahwa akun Anda "tidak memiliki otorisasi untuk melakukan tindakan 'Microsoft.Authorization/roleAssignments/write'." Hubungi admin Azure Active Directory Anda untuk mengelola peran.

Penambahan peran _tidak_ membatasi izin yang ditetapkan sebelumnya. Jika izin perwakilan layanan dibatasi, peran __Kontributor__ akan dihapus.

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
Connect-AzAccount -ServicePrincipal -Tenant <tenant ID> -CertificateThumbprint <thumbprint>
```

Untuk petunjuk tentang mengimpor sertifikat ke penyimpanan info masuk yang dapat diakses oleh PowerShell, lihat [Masuk dengan Azure PowerShell](authenticate-azureps.md#sp-signin)

## <a name="reset-credentials"></a>Mengatur ulang info masuk

Jika Anda lupa info masuk untuk perwakilan layanan, gunakan [New-AzADSpCredential](/powershell/module/az.resources/new-azadspcredential) untuk menambahkan info masuk baru. Cmdlet ini mengambil argumen dan jenis info masuk yang sama dengan `New-AzADServicePrincipal`. Tanpa argumen info masuk, `PasswordCredential` yang baru dengan kata sandi acak dibuat.

> [!IMPORTANT]
> Sebelum menetapkan info masuk baru, Anda mungkin ingin menghapus info masuk yang ada untuk mencegah masuk dengannya. Untuk melakukannya, gunakan cmdlet [Remove-AzADSpCredential](/powershell/module/az.resources/remove-azadspcredential):
>
> ```azurepowershell-interactive
> Remove-AzADSpCredential -DisplayName ServicePrincipalName
> ```

```azurepowershell-interactive
$newCredential = New-AzADSpCredential -ServicePrincipalName ServicePrincipalName
```
