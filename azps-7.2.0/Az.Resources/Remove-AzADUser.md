---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azaduser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADUser.md
ms.openlocfilehash: 7c5e13d8ef41fa055be219a1e7e2ef3fe5082ebc
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140116935"
---
# Remove-AzADUser

## SYNOPSIS
Menghapus entitas dari pengguna.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/remove-azaduser) untuk informasi terkini.

## SYNTAX

### UPNOrObjectIdParameterSet (Default)
```
Remove-AzADUser -UPNOrObjectId <String> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ObjectIdParameterSet
```
Remove-AzADUser -ObjectId <String> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UPNParameterSet
```
Remove-AzADUser -UserPrincipalName <String> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayNameParameterSet
```
Remove-AzADUser -DisplayName <String> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectParameterSet
```
Remove-AzADUser -InputObject <IMicrosoftGraphUser> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus entitas dari pengguna.

## EXAMPLES

### Contoh 1: Hapus pengguna berdasarkan nama tampilan
```powershell
PS C:\> Remove-AzADUser -DisplayName $name
```

Hapus pengguna menurut nama tampilan

### Contoh 2: Hapus input pengguna menurut saluran
```powershell
PS C:\> Get-AzADUser -UserPrincipalName $id | Remove-AzADUser
```

Menghapus pengguna menurut input saluran

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
nama tampilan pengguna

```yaml
Type: System.String
Parameter Sets: DisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
objek input pengguna Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
kunci: id pengguna

```yaml
Type: System.String
Parameter Sets: ObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UPNOrObjectId
UserPrincipalName atau ObjectId pengguna akan dihapus.

```yaml
Type: System.String
Parameter Sets: UPNOrObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserPrincipalName
nama prinsipal pengguna

```yaml
Type: System.String
Parameter Sets: UPNParameterSet
Aliases: UPN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMicrosoftGraphUser>: objek input pengguna
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[AccountEnabled <Boolean?>]`: true jika akun diaktifkan; jika tidak, false. Properti ini diperlukan saat pengguna dibuat. Mendukung $filter (eq, ne, NOT, dan in).
  - `[AgeGroup <String>]`: Mengatur grup usia pengguna. Nilai yang diperbolehkan: null, minor, notAdult dan dewasa. Lihat definisi properti kelompok usia legal untuk informasi lebih lanjut. Mendukung $filter (eq, ne, NOT, dan in).
  - `[ApproximateLastSignInDateTime <DateTime?>]`: Tipe timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Baca-saja. Mendukung $filter (eq, ne, not, ge, le, dan eq pada nilai null) dan $orderBy.
  - `[City <String>]`: Kota di mana pengguna berada. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[CompanyName <String>]`: Nama perusahaan yang dikaitkan dengan pengguna. Properti ini dapat berguna untuk menjelaskan perusahaan dari mana pengguna eksternal berasal. Panjang maksimal nama perusahaan adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[ComplianceExpirationDateTime <DateTime?>]`: Tanda waktu saat perangkat tidak lagi dianggap sesuai. Tipe timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Baca-saja.
  - `[ConsentProvidedForMinor <String>]`: Mengatur apakah persetujuan telah diperoleh untuk pengguna di bawah umur. Nilai yang diperbolehkan: null, granted, denied, dan notRequired. Lihat definisi properti kelompok usia legal untuk informasi lebih lanjut. Mendukung $filter (eq, ne, NOT, dan in).
  - `[Country <String>]`: Negara/kawasan tempat pengguna berada; misalnya, AS atau UK. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[Department <String>]`: Nama untuk departemen tempat pengguna bekerja. Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT , ge, le, dan in operators).
  - `[DeviceVersion <Int32?>]`: Hanya untuk penggunaan internal.
  - `[EmployeeHireDate <DateTime?>]`: Tanggal dan waktu saat pengguna dipekerjakan atau akan mulai bekerja dalam kasus karyawan mendatang. Mendukung $filter (eq, ne, NOT , ge, le, in).
  - `[EmployeeId <String>]`: Pengidentifikasi karyawan yang ditetapkan kepada pengguna oleh organisasi. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[EmployeeType <String>]`: Merekam tipe pekerja perusahaan. Misalnya, Karyawan, Kontraktor, Konsultan, atau Vendor. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[ExternalUserState <String>]`: Untuk pengguna eksternal yang diundang ke penyewa menggunakan API undangan, properti ini mewakili status undangan pengguna yang diundang. Untuk pengguna yang diundang, status bisa menjadi PendingAcceptance atau Accepted, atau null untuk semua pengguna lain. Mendukung $filter (eq, ne, NOT , in).
  - `[ExternalUserStateChangeDateTime <DateTime?>]`: Memperlihatkan tanda waktu untuk perubahan terakhir pada properti externalUserState. Mendukung $filter (eq, ne, NOT , in).
  - `[FaxNumber <String>]`: Nomor faks pengguna. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[GivenName <String>]`: Nama depan (nama depan) pengguna. Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[Identity <IMicrosoftGraphObjectIdentity[]>]`: Mewakili identitas yang bisa digunakan untuk masuk ke akun pengguna ini. Identitas bisa disediakan oleh Microsoft (juga dikenal sebagai akun lokal), oleh organisasi, atau oleh penyedia identitas sosial seperti Facebook, Google, dan Microsoft, dan terikat ke akun pengguna. Mungkin berisi beberapa item dengan nilai signInType yang sama. Mendukung $filter (eq) hanya di mana signInType bukan userPrincipalName.
    - `[Issuer <String>]`: Menentukan penerbit identitas, misalnya facebook.com.Untuk akun lokal (di mana signInType tidak federasi), properti ini adalah nama domain penyewa B2C lokal, misalnya contoso.onmicrosoft.com.Untuk pengguna eksternal dari organisasi Azure AD lain, ini akan menjadi domain organisasi gabungan, misalnya contoso.com.Mendukung $filter. Batas 512 karakter.
    - `[IssuerAssignedId <String>]`: Menentukan pengidentifikasi unik yang ditetapkan kepada pengguna oleh penerbit. Kombinasi dari penerbit dan penerbitAssignedId harus unik di dalam organisasi. Mewakili nama masuk untuk pengguna, ketika signInType diatur ke emailAddress atau userName (juga dikenal sebagai akun lokal). Ketika signInType diatur ke: emailAddress, (atau string kustom yang dimulai dengan emailAddress seperti emailAddress1) issuerAssignedId harus merupakan namapengguna alamat email yang valid, issuerAssignedId harus merupakan bagian lokal yang valid dari alamat emailSupport $filter. Batas 100 karakter.
    - `[SignInType <String>]`: Menentukan tipe masuk pengguna di direktori Anda, seperti emailAddress, userName atau gabungan. Di sini, gabungan mewakili pengidentifikasi unik untuk pengguna dari penerbit, yang bisa berada dalam format apa pun yang dipilih oleh penerbit. Validasi tambahan diterapkan pada issuerAssignedId ketika tipe masuk diatur ke emailAddress atau userName. Properti ini juga dapat diatur ke string kustom apa pun.
  - `[IsResourceAccount <Boolean?>]`: Jangan gunakan - dicadangkan untuk penggunaan di masa mendatang.
  - `[JobTitle <String>]`: Jabatan pekerjaan pengguna. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[Mail <String>]`: Alamat SMTP untuk pengguna, misalnya, admin@contoso.com. Perubahan pada properti ini juga akan memperbarui kumpulan proxyAddresses pengguna agar menyertakan nilai sebagai alamat SMTP. Meskipun properti ini dapat berisi karakter aksen, menggunakannya dapat menyebabkan masalah akses dengan aplikasi Microsoft lainnya untuk pengguna tersebut. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith, endsWith).
  - `[MailNickname <String>]`: Alias email untuk pengguna. Properti ini harus ditentukan saat pengguna dibuat. Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[OfficeLocation <String>]`: Lokasi kantor di tempat bisnis pengguna. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[OnPremisesImmutableId <String>]`: Properti ini digunakan untuk mengaitkan akun pengguna Direktori Aktif lokal ke objek pengguna Azure AD miliknya. Properti ini harus ditentukan saat membuat akun pengguna baru di Graph jika Anda menggunakan domain gabungan untuk properti userPrincipalName (UPN). CATATAN: Karakter $ dan _ tidak dapat digunakan saat menentukan properti ini. Dikembalikan hanya pada $select. Mendukung $filter (eq, ne, NOT, ge, le, in)..
  - `[OnPremisesLastSyncDateTime <DateTime?>]`: Terakhir kali objek disinkronkan dengan direktori lokal. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z Baca-saja. Mendukung $filter (eq, ne, not, ge, le, in).
  - `[OnPremisesSyncEnabled <Boolean?>]`: true jika objek ini disinkronkan dari direktori lokal; false jika objek ini aslinya disinkronkan dari direktori lokal tetapi tidak lagi disinkronkan; null jika objek ini belum pernah disinkronkan dari direktori lokal (default). Baca-saja. Mendukung $filter (eq, ne, not, in, dan eq pada nilai null).
  - `[OperatingSystem <String>]`: Sistem operasi perangkat. Windows, iOS, dll. Properti ini merupakan baca-saja.
  - `[OperatingSystemVersion <String>]`: Versi sistem operasi perangkat. Diperlukan. Mendukung $filter (eq, ne, not, ge, le, startsWith, dan eq on null values).
  - `[OtherMail <String[]>]`: Daftar alamat email tambahan untuk pengguna; misalnya: ['bob@contoso.com', 'Robert@fabrikam.com']. CATATAN: Meskipun dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna. Mendukung $filter (eq, NOT, ge, le, in, startsWith).
  - `[PasswordPolicy <String>]`: Menentukan kebijakan kata sandi untuk pengguna. Nilai ini adalah enumerasi dengan satu nilai yang memungkinkan adalah DisableStrongPassword, yang memungkinkan kata sandi yang lebih lemah daripada kebijakan default yang ditentukan. DisablePasswordExpiration juga bisa ditentukan. Keduanya mungkin ditentukan bersama; misalnya: DisablePasswordExpiration, DisableStrongPassword.Supports $filter (ne, NOT).
  - `[PasswordProfile <IMicrosoftGraphPasswordProfile>]`: passwordProfile
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[ForceChangePasswordNextSignIn <Boolean?>]`: true jika pengguna harus mengubah kata sandinya di login berikutnya; jika tidak false. Jika tidak diatur, defaultnya adalah false. CATATAN: Untuk penyewa Azure B2C, atur ke false, tetapi gunakan kebijakan kustom dan aliran pengguna untuk memaksa pengaturan ulang kata sandi pada kali pertama masuk. Lihat Mengatur ulang kata sandi saat masuk pertama kali.
    - `[ForceChangePasswordNextSignInWithMfa <Boolean?>]`: Jika benar, pada saat masuk berikutnya, pengguna harus melakukan multi-factor authentication (MFA) sebelum dipaksa mengubah kata sandinya. Perilaku ini identik dengan forceChangePasswordNextSignIn, kecuali bahwa pengguna diperlukan untuk melakukan multi-factor authentication terlebih dahulu sebelum kata sandi berubah. Setelah perubahan kata sandi, properti ini akan diatur ulang secara otomatis ke false. Jika tidak diatur, defaultnya adalah false.
    - `[Password <String>]`: Kata sandi untuk pengguna. Properti ini diperlukan saat pengguna dibuat. Kode ini dapat diperbarui, tetapi pengguna akan diminta untuk mengubah kata sandi pada login berikutnya. Kata sandi harus memenuhi persyaratan minimal seperti yang ditentukan oleh properti passwordPolicies pengguna. Secara default, kata sandi yang kuat diperlukan.
  - `[PhysicalId <String[]>]`: Hanya untuk penggunaan internal. Not nullable. Mendukung $filter (eq, not, ge, le, startsWith).
  - `[PostalCode <String>]`: Kode pos untuk alamat pos pengguna. Kode pos khusus untuk negara/kawasan pengguna. Di Amerika Serikat, atribut ini berisi kode pos. Panjang maksimum adalah 40 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[PreferredLanguage <String>]`: Bahasa pilihan untuk pengguna. Harus mengikuti Kode ISO 639-1; misalnya en-US. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[ShowInAddressList <Boolean?>]`: true jika Outlook alamat global harus berisi pengguna ini, jika tidak salah. Jika tidak diatur, maka hal ini akan diperlakukan sebagai benar. Untuk pengguna yang diundang melalui pengelola undangan, properti ini akan diatur ke false. Mendukung $filter (eq, ne, NOT, in).
  - `[State <String>]`: Negara bagian atau provinsi di alamat pengguna. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[StreetAddress <String>]`: Alamat jalan tempat bisnis pengguna. Panjang maksimum adalah 1024 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[Surname <String>]`: Nama keluarga pengguna (nama keluarga atau nama belakang). Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[TrustType <String>]`: Tipe kepercayaan untuk perangkat yang tergabung. Baca-saja. Nilai yang mungkin: Tempat kerja (menunjukkan membawa perangkat pribadi Anda sendiri), AzureAd (Perangkat yang bergabung hanya di awan), ServerAd (perangkat bersama domain lokal yang tergabung dalam Azure AD). Untuk detail selengkapnya, lihat Pengenalan manajemen perangkat di Azure Active Directory
  - `[UsageLocation <String>]`: Kode negara dua huruf (standar ISO 3166). Diperlukan untuk pengguna yang akan diberi lisensi karena persyaratan hukum untuk memeriksa ketersediaan layanan di negara-negara.  Contohnya antara lain: US, JP, dan GB. Not nullable. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[UserPrincipalName <String>]`: Nama prinsipal pengguna (UPN) pengguna. UPN adalah nama masuk gaya internet untuk pengguna berdasarkan RFC 822 standar internet. Menurut konvensi, ini harus di petakan ke nama email pengguna. Format umumnya alias@domainadalah, di mana domain harus ada dalam kumpulan penyewa domain terverifikasi. Properti ini diperlukan saat pengguna dibuat. Domain terverifikasi untuk penyewa bisa diakses dari properti verifiedDomains organisasi. CATATAN: Meskipun dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith, endsWith) dan $orderBy.
  - `[UserType <String>]`: Nilai string yang dapat digunakan untuk mengklasifikasikan tipe pengguna dalam direktori Anda, seperti Anggota dan Tamu. Mendukung $filter (eq, ne, NOT, in,).

## RELATED LINKS

## RELATED LINKS
