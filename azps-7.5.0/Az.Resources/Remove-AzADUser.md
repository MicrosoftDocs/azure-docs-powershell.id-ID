---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azaduser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzADUser.md
ms.openlocfilehash: 46115693719f7542e02491dbde2d6ea25da1efaf
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146588774"
---
# Remove-AzADUser

## SYNOPSIS
Menghapus entitas dari pengguna.

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/remove-azaduser) untuk informasi terbaru.

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

### Contoh 1: Menghapus pengguna menurut nama tampilan
```powershell
Remove-AzADUser -DisplayName $name
```

Menghapus pengguna menurut nama tampilan

### Contoh 2: Menghapus pengguna menurut input alur
```powershell
Get-AzADUser -UserPrincipalName $id | Remove-AzADUser
```

Menghapus pengguna menurut input alur

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
objek input pengguna Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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
userPrincipalName atau ObjectId pengguna yang akan dihapus.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IMicrosoftGraphUser>`: objek input pengguna
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AccountEnabled <Boolean?>]`: true jika akun diaktifkan; jika tidak, salah. Properti ini diperlukan saat pengguna dibuat. Mendukung $filter (eq, ne, NOT, dan in).
  - `[AgeGroup <String>]`: Mengatur grup usia pengguna. Nilai yang diizinkan: null, minor, notAdult dan adult. Lihat definisi properti kelompok usia legal untuk informasi lebih lanjut. Mendukung $filter (eq, ne, NOT, dan in).
  - `[ApproximateLastSignInDateTime <DateTime?>]`: Jenis tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Baca-saja. Mendukung $filter (eq, ne, not, ge, le, dan eq pada nilai null) dan $orderBy.
  - `[City <String>]`: Kota tempat pengguna berada. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[CompanyName <String>]`: Nama perusahaan yang dikaitkan dengan pengguna. Properti ini dapat berguna untuk menjelaskan perusahaan asal pengguna eksternal. Panjang maksimum nama perusahaan adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[ComplianceExpirationDateTime <DateTime?>]`: Tanda waktu ketika perangkat tidak lagi dianggap sesuai. Jenis tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Baca-saja.
  - `[ConsentProvidedForMinor <String>]`: Menetapkan apakah persetujuan telah diperoleh untuk anak di bawah umur. Nilai yang diizinkan: null, granted, denied, dan notRequired. Lihat definisi properti kelompok usia legal untuk informasi lebih lanjut. Mendukung $filter (eq, ne, NOT, dan in).
  - `[Country <String>]`: Negara/wilayah tempat pengguna berada; misalnya, AS atau Inggris. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[Department <String>]`: Nama untuk departemen tempat pengguna bekerja. Panjang maksimum adalah 64 karakter. Mendukung $filter (operator eq, ne, NOT , ge, le, dan in).
  - `[DeviceVersion <Int32?>]`: Hanya untuk penggunaan internal.
  - `[EmployeeHireDate <DateTime?>]`: Tanggal dan waktu ketika pengguna dipekerjakan atau akan mulai bekerja jika terjadi persewaan di masa mendatang. Mendukung $filter (eq, ne, NOT , ge, le, in).
  - `[EmployeeId <String>]`: Pengidentifikasi karyawan yang ditetapkan untuk pengguna oleh organisasi. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[EmployeeType <String>]`: Menangkap jenis pekerja perusahaan. Misalnya, Karyawan, Kontraktor, Konsultan, atau Vendor. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[ExternalUserState <String>]`: Untuk pengguna eksternal yang diundang ke penyewa menggunakan API undangan, properti ini mewakili status undangan pengguna yang diundang. Untuk pengguna yang diundang, statusnya bisa PendingAcceptance atau Accepted, atau null untuk semua pengguna lain. Mendukung $filter (eq, ne, NOT , in).
  - `[ExternalUserStateChangeDateTime <DateTime?>]`: Menampilkan tanda waktu untuk perubahan terbaru pada properti externalUserState. Mendukung $filter (eq, ne, NOT , in).
  - `[FaxNumber <String>]`: Nomor faks pengguna. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[GivenName <String>]`: Nama yang diberikan (nama depan) pengguna. Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[Identity <IMicrosoftGraphObjectIdentity[]>]`: Mewakili identitas yang dapat digunakan untuk masuk ke akun pengguna ini. Identitas dapat disediakan oleh Microsoft (juga dikenal sebagai akun lokal), oleh organisasi, atau oleh penyedia identitas sosial seperti Facebook, Google, dan Microsoft, dan terkait dengan akun pengguna. Mungkin berisi beberapa item dengan nilai signInType yang sama. Mendukung $filter (eq) hanya di mana signInType bukan userPrincipalName.
    - `[Issuer <String>]`: Menentukan penerbit identitas, misalnya facebook.com.Untuk akun lokal (di mana signInType tidak terfederasi), properti ini adalah nama domain default penyewa B2C lokal, misalnya contoso.onmicrosoft.com.Untuk pengguna eksternal dari organisasi Azure AD lain, ini akan menjadi domain organisasi federasi, misalnya contoso.com.Supports $filter. Batas karakter 512.
    - `[IssuerAssignedId <String>]`: Menentukan pengidentifikasi unik yang ditetapkan untuk pengguna oleh penerbit. Kombinasi pengeluar sertifikat dan issuerAssignedId harus unik dalam organisasi. Mewakili nama masuk untuk pengguna, saat signInType diatur ke emailAddress atau userName (juga dikenal sebagai akun lokal). Ketika signInType diatur ke: emailAddress, (atau string kustom yang dimulai dengan emailAddress seperti emailAddress1) issuerAssignedId harus berupa addressuserName email yang valid, issuerAssignedId harus menjadi bagian lokal yang valid dari alamat emailSupports $filter. Batas 100 karakter.
    - `[SignInType <String>]`: Menentukan jenis masuk pengguna di direktori Anda, seperti emailAddress, userName, atau federated. Di sini, federasi mewakili pengidentifikasi unik untuk pengguna dari penerbit, yang dapat dalam format apa pun yang dipilih oleh penerbit. Validasi tambahan diberlakukan pada issuerAssignedId saat jenis masuk diatur ke emailAddress atau userName. Properti ini juga dapat diatur ke string kustom apa pun.
  - `[IsResourceAccount <Boolean?>]`: Jangan gunakan - dicadangkan untuk digunakan di masa mendatang.
  - `[JobTitle <String>]`: Jabatan pengguna. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).
  - `[Mail <String>]`: Alamat SMTP untuk pengguna, misalnya, admin@contoso.com. Perubahan pada properti ini juga akan memperbarui koleksi proxyAddresses pengguna untuk menyertakan nilai sebagai alamat SMTP. Meskipun properti ini dapat berisi karakter aksen, menggunakannya dapat menyebabkan masalah akses dengan aplikasi Microsoft lainnya untuk pengguna. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith, endsWith).
  - `[MailNickname <String>]`: Alias email untuk pengguna. Properti ini harus ditentukan ketika pengguna dibuat. Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[OfficeLocation <String>]`: Lokasi kantor di tempat bisnis pengguna. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[OnPremisesImmutableId <String>]`: Properti ini digunakan untuk mengaitkan akun pengguna Active Directory lokal ke objek pengguna Azure AD mereka. Properti ini harus ditentukan saat membuat akun pengguna baru di Graph jika Anda menggunakan domain federasi untuk properti userPrincipalName (UPN) pengguna. CATATAN: Karakter $ dan _ tidak dapat digunakan saat menentukan properti ini. Dikembalikan hanya pada $select. Mendukung $filter (eq, ne, NOT, ge, le, in)..
  - `[OnPremisesLastSyncDateTime <DateTime?>]`: Terakhir kali objek disinkronkan dengan direktori lokal. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z Baca-saja. Mendukung $filter (eq, ne, not, ge, le, in).
  - `[OnPremisesSyncEnabled <Boolean?>]`: true jika objek ini disinkronkan dari direktori lokal; false jika objek ini awalnya disinkronkan dari direktori lokal tetapi tidak lagi disinkronkan; null jika objek ini belum pernah disinkronkan dari direktori lokal (default). Baca-saja. Mendukung $filter (eq, ne, not, in, dan eq pada nilai null).
  - `[OperatingSystem <String>]`: Sistem operasi perangkat. Windows, iOS, dll. Properti ini bersifat baca-saja.
  - `[OperatingSystemVersion <String>]`: Versi sistem operasi perangkat. Wajib diisi. Mendukung $filter (eq, ne, not, ge, le, startsWith, dan eq pada nilai null).
  - `[OtherMail <String[]>]`: Daftar alamat email tambahan untuk pengguna; misalnya: ['bob@contoso.com', 'Robert@fabrikam.com']. CATATAN: Meskipun properti ini dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna. Mendukung $filter (eq, NOT, ge, le, in, startsWith).
  - `[PasswordPolicy <String>]`: Menentukan kebijakan kata sandi untuk pengguna. Nilai ini adalah enumerasi dengan satu nilai yang mungkin adalah DisableStrongPassword, yang memungkinkan kata sandi yang lebih lemah daripada kebijakan default yang ditentukan. DisablePasswordExpiration juga dapat ditentukan. Keduanya dapat ditentukan bersama-sama; misalnya: DisablePasswordExpiration, DisableStrongPassword.Supports $filter (ne, NOT).
  - `[PasswordProfile <IMicrosoftGraphPasswordProfile>]`: passwordProfile
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[ForceChangePasswordNextSignIn <Boolean?>]`: benar jika pengguna harus mengubah kata sandinya pada login berikutnya; jika tidak salah. Jika tidak diatur, defaultnya adalah false. CATATAN: Untuk penyewa Azure B2C, atur ke false dan sebagai gantinya gunakan kebijakan kustom dan alur pengguna untuk memaksa reset kata sandi saat pertama kali masuk. Lihat Memaksa reset kata sandi pada log masuk pertama.
    - `[ForceChangePasswordNextSignInWithMfa <Boolean?>]`: Jika true, pada rincian masuk berikutnya, pengguna harus melakukan autentikasi multifaktor (MFA) sebelum dipaksa untuk mengubah kata sandi mereka. Perilaku ini identik dengan forceChangePasswordNextSignIn kecuali bahwa pengguna diperlukan untuk terlebih dahulu melakukan autentikasi multifaktor sebelum perubahan kata sandi. Setelah perubahan kata sandi, properti ini akan secara otomatis diatur ulang ke false. Jika tidak diatur, defaultnya adalah false.
    - `[Password <String>]`: Kata sandi untuk pengguna. Properti ini diperlukan saat pengguna dibuat. Ini dapat diperbarui, tetapi pengguna akan diminta untuk mengubah kata sandi pada login berikutnya. Kata sandi harus memenuhi persyaratan minimum seperti yang ditentukan oleh properti passwordPolicies pengguna. Secara default, kata sandi yang kuat diperlukan.
  - `[PhysicalId <String[]>]`: Hanya untuk penggunaan internal. Tidak dapat diubah ke null. Mendukung $filter (eq, bukan, ge, le, startsWith).
  - `[PostalCode <String>]`: Kode pos untuk alamat pos pengguna. Kode pos khusus untuk negara/wilayah pengguna. Di Amerika Serikat, atribut ini berisi kode pos. Panjang maksimum adalah 40 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[PreferredLanguage <String>]`: Bahasa pilihan untuk pengguna. Harus mengikuti Kode ISO 639-1; misalnya en-US. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[ShowInAddressList <Boolean?>]`: true jika daftar alamat global Outlook harus berisi pengguna ini, jika tidak salah. Jika tidak diatur, ini akan diperlakukan sebagai benar. Untuk pengguna yang diundang melalui pengelola undangan, properti ini akan diatur ke false. Mendukung $filter (eq, ne, NOT, in).
  - `[State <String>]`: Negara bagian atau provinsi di alamat pengguna. Panjang maksimum adalah 128 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[StreetAddress <String>]`: Alamat jalan tempat bisnis pengguna. Panjang maksimum adalah 1024 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[Surname <String>]`: Nama keluarga pengguna (nama keluarga atau nama belakang). Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[TrustType <String>]`: Jenis kepercayaan untuk perangkat yang bergabung. Baca-saja. Nilai yang mungkin: Tempat kerja (menunjukkan bawa perangkat pribadi Anda sendiri), AzureAd (Perangkat yang bergabung hanya cloud), ServerAd (perangkat yang bergabung dengan domain lokal bergabung ke Azure AD). Untuk detail selengkapnya, lihat Pengenalan manajemen perangkat di Azure Active Directory
  - `[UsageLocation <String>]`: Kode negara dua huruf (standar ISO 3166). Diperlukan untuk pengguna yang akan diberi lisensi karena persyaratan hukum untuk memeriksa ketersediaan layanan di negara- negara.  Contohnya meliputi: US, JP, dan GB. Tidak dapat diubah ke null. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).
  - `[UserPrincipalName <String>]`: Nama prinsipal pengguna (UPN) pengguna. UPN adalah nama untuk masuk berbasis Internet untuk pengguna berdasarkan standar Internet RFC 822. Menurut konvensi, ini harus dipetakan ke nama email pengguna. Format umumnya adalah alias@domain, di mana domain harus ada dalam kumpulan domain terverifikasi penyewa. Properti ini diperlukan saat pengguna dibuat. Domain terverifikasi untuk penyewa dapat diakses dari properti organisasi verifiedDomains. CATATAN: Meskipun properti ini dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith, endsWith) dan $orderBy.
  - `[UserType <String>]`: Nilai string yang dapat digunakan untuk mengklasifikasikan jenis pengguna di direktori Anda, seperti Anggota dan Tamu. Mendukung $filter (eq, ne, NOT, in,).

## RELATED LINKS

## RELATED LINKS
