---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azaduser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADUser.md
ms.openlocfilehash: 46123d970a5272ab60a2a34df572aac1f60d6de1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140084033"
---
# New-AzADUser

## SYNOPSIS
Menambahkan entitas baru ke pengguna

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/new-azaduser) untuk informasi terkini.

## SYNTAX

```
New-AzADUser -DisplayName <String> -MailNickname <String> -UserPrincipalName <String> -Password <SecureString>
 [-AboutMe <String>] [-AccountEnabled <Boolean>] [-AgeGroup <String>] [-Birthday <DateTime>] [-City <String>]
 [-CompanyName <String>] [-ConsentProvidedForMinor <String>] [-Country <String>] [-DeletedDateTime <DateTime>]
 [-Department <String>] [-DeviceEnrollmentLimit <Int32>] [-EmployeeHireDate <DateTime>] [-EmployeeId <String>]
 [-EmployeeType <String>] [-ExternalUserState <String>] [-ExternalUserStateChangeDateTime <DateTime>]
 [-FaxNumber <String>] [-GivenName <String>] [-HireDate <DateTime>] [-Interest <String[]>] [-IsResourceAccount]
 [-JobTitle <String>] [-Mail <String>] [-MobilePhone <String>] [-MySite <String>] [-OfficeLocation <String>]
 [-ImmutableId <String>] [-OtherMail <String[]>] [-PasswordPolicy <String>]
 [-PasswordProfile <IMicrosoftGraphPasswordProfile>] [-PostalCode <String>] [-PreferredLanguage <String>]
 [-PreferredName <String>] [-Responsibility <String[]>] [-School <String[]>] [-ShowInAddressList]
 [-Skill <String[]>] [-State <String>] [-StreetAddress <String>] [-Surname <String>] [-UsageLocation <String>]
 [-UserType <String>] [-ForceChangePasswordNextLogin] [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Menambahkan entitas baru ke pengguna

## EXAMPLES

### Contoh 1: Buat pengguna
```powershell
PS C:\> $pp=New-Object -TypeName "Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordProfile" -Property @{Password=$password}
PS C:\> New-MgUser -DisplayName $uname -PasswordProfile $pp -AccountEnabled -MailNickname $nickname -UserPrincipalName $upn
```

Buat pengguna

## PARAMETERS

### -AboutMe
Bidang entri teks bentuk bebas bagi pengguna untuk menjelaskan diri mereka sendiri.
Dikembalikan hanya pada $select.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountEnabled
true untuk mengaktifkan akun; jika tidak, false.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: EnableAccount

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgeGroup
Mengatur grup usia pengguna.
Nilai yang diperbolehkan: null, minor, notAdult dan dewasa.
Lihat definisi properti kelompok usia legal untuk informasi lebih lanjut.
Mendukung $filter (eq, ne, NOT, dan in).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Birthday
Ulang tahun pengguna.
Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC.
Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z yang hanya dikembalikan pada $select.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kota
Kota di mana pengguna berada.
Panjang maksimum adalah 128 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompanyName
Nama perusahaan yang dikaitkan dengan pengguna.
Properti ini dapat berguna untuk menjelaskan perusahaan dari mana pengguna eksternal berasal.
Panjang maksimal nama perusahaan adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsentProvidedForMinor
Mengatur apakah persetujuan telah diperoleh untuk pengguna di bawah umur.
Nilai yang diperbolehkan: null, granted, denied, dan notRequired.
Lihat definisi properti kelompok usia legal untuk informasi lebih lanjut.
Mendukung $filter (eq, ne, NOT, dan in).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Negara
Negara/kawasan tempat pengguna berada; misalnya, AS atau UK.
Panjang maksimum adalah 128 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DeletedDateTime
.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Departemen
Nama untuk departemen tempat pengguna bekerja.
Panjang maksimum adalah 64 karakter. Mendukung $filter (eq, ne, NOT , ge, le, dan in operators).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceEnrollmentLimit
Batas pada jumlah maksimum perangkat yang diizinkan pengguna untuk mendaftar.
Nilai yang diperbolehkan adalah 5 atau 1000.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Nama ditampilkan di buku alamat untuk pengguna.
Nilai ini biasanya adalah kombinasi nama depan, inisial tengah, dan nama belakang pengguna.
Properti ini diperlukan saat pengguna dibuat dan tidak bisa dibersihkan selama pembaruan.
Panjang maksimum adalah 256 karakter.
Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith), $orderBy, dan $search.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmployeeDate
Tanggal dan waktu saat pengguna dipekerjakan atau akan mulai bekerja dalam kasus karyawan mendatang.
Mendukung $filter (eq, ne, NOT , ge, le, in).

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmployeeId
Pengidentifikasi karyawan yang ditetapkan kepada pengguna oleh organisasi.
Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmployeeType
Merekam tipe pekerja perusahaan.
Misalnya, Karyawan, Kontraktor, Konsultan, atau Vendor.
Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalUserState
Untuk pengguna eksternal yang diundang ke penyewa menggunakan API undangan, properti ini mewakili status undangan pengguna yang diundang.
Untuk pengguna yang diundang, status bisa menjadi PendingAcceptance atau Accepted, atau null untuk semua pengguna lain.
Mendukung $filter (eq, ne, NOT , in).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalUserStateChangeDateTime
Memperlihatkan tanda waktu untuk perubahan terakhir pada properti externalUserState.
Mendukung $filter (eq, ne, NOT , in).

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaxNumber
Nomor faks pengguna.
Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceChangePasswordNextLogin
Ini harus ditentukan jika pengguna harus mengubah kata sandi di login berikutnya yang berhasil (true).
Perilaku default adalah (false) agar tidak mengubah kata sandi di saat berikutnya berhasil masuk.

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

### -GivenName
Nama yang diberikan (nama depan) pengguna.
Panjang maksimum adalah 64 karakter.
Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HireDate
Tanggal mulai karyawan pengguna.
Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC.
Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z.
Dikembalikan hanya pada $select.
Catatan: Properti ini khusus untuk SharePoint Online.
Kami menyarankan agar menggunakan properti native employee Salah SatuDate untuk mengatur dan memperbarui nilai tanggal karyawan menggunakan API Graph Microsoft.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImmutableId
Properti ini digunakan untuk mengaitkan akun pengguna Direktori Aktif lokal ke objek pengguna Azure AD mereka.
Properti ini harus ditentukan saat membuat akun pengguna baru di Graph jika Anda menggunakan domain gabungan untuk properti userPrincipalName (UPN).
CATATAN: Karakter $ dan _ tidak dapat digunakan saat menentukan properti ini.
Dikembalikan hanya pada $select.
Mendukung $filter (eq, ne, NOT, ge, le, in)..

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OnPremisesImmutableId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interest
Daftar bagi pengguna untuk menjelaskan minat mereka.
Dikembalikan hanya pada $select.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsResourceAccount
Jangan gunakan - dicadangkan untuk penggunaan di masa mendatang.

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

### -JobTitle
Jabatan pekerjaan pengguna.
Panjang maksimum adalah 128 karakter.
Mendukung $filter (eq, ne, NOT , ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mail
Alamat SMTP untuk pengguna, misalnya, admin@contoso.com.
Perubahan pada properti ini juga akan memperbarui kumpulan proxyAddresses pengguna agar menyertakan nilai sebagai alamat SMTP.
Meskipun properti ini dapat berisi karakter aksen, menggunakannya dapat menyebabkan masalah akses dengan aplikasi Microsoft lainnya untuk pengguna tersebut.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith, endsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MailNickname
Alias email untuk pengguna.
Properti ini harus ditentukan saat pengguna dibuat.
Panjang maksimum adalah 64 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MobilePhone
Nomor telepon seluler utama untuk pengguna.
Baca-saja untuk pengguna yang disinkronkan dari direktori lokal.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Situs Saya
URL untuk situs pribadi pengguna.
Dikembalikan hanya pada $select.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OfficeLocation
Lokasi kantor di tempat bisnis pengguna.
Panjang maksimum adalah 128 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherMail
Daftar alamat email tambahan untuk pengguna; misalnya: ['bob@contoso.com', 'Robert@fabrikam.com']. CATATAN: Meskipun dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna. Mendukung $filter (eq, NOT, ge, le, in, startsWith).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Kata sandi untuk pengguna.
Kata sandi harus memenuhi persyaratan kompleksitas kata sandi penyewa.
Disarankan untuk mengatur kata sandi yang kuat.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordPolicy
Menentukan kebijakan kata sandi untuk pengguna.
Nilai ini adalah enumerasi dengan satu nilai yang memungkinkan adalah DisableStrongPassword, yang memungkinkan kata sandi yang lebih lemah daripada kebijakan default yang ditentukan.
DisablePasswordExpiration juga bisa ditentukan.
Keduanya mungkin ditentukan bersama; misalnya: DisablePasswordExpiration, DisableStrongPassword.Supports $filter (ne, NOT).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordProfile
passwordProfile Untuk membangun, lihat bagian CATATAN untuk properti PASSWORDPROFILE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PostalCode
Kode pos untuk alamat pos pengguna.
Kode pos khusus untuk negara/kawasan pengguna.
Di Amerika Serikat, atribut ini berisi kode pos.
Panjang maksimum adalah 40 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredLanguage
Bahasa pilihan untuk pengguna.
Harus mengikuti Kode ISO 639-1; misalnya en-US.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredName
Nama pilihan untuk pengguna.
Dikembalikan hanya pada $select.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tanggung Jawab
Sebuah daftar agar pengguna menghitung tanggung jawab mereka.
Dikembalikan hanya pada $select.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sekolah
Daftar bagi pengguna untuk menghitung sekolah yang telah mereka hadiri.
Dikembalikan hanya pada $select.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowInAddressList
true jika daftar Outlook global harus berisi pengguna ini, jika tidak salah.
Jika tidak diatur, maka hal ini akan diperlakukan sebagai benar.
Untuk pengguna yang diundang melalui pengelola undangan, properti ini akan diatur ke false.
Mendukung $filter (eq, ne, NOT, in).

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

### -Skill
Daftar bagi pengguna untuk menghitung keahlian mereka.
Dikembalikan hanya pada $select.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Negara Bagian
Negara bagian atau provinsi di alamat pengguna.
Panjang maksimum adalah 128 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StreetAddress
Alamat jalan tempat bisnis pengguna.
Panjang maksimum adalah 1024 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Surname
Nama keluarga pengguna (nama keluarga atau nama belakang).
Panjang maksimum adalah 64 karakter.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsageLocation
Kode negara dua huruf (standar ISO 3166).
Diperlukan untuk pengguna yang akan diberi lisensi karena persyaratan hukum untuk memeriksa ketersediaan layanan di negara-negara.
Contohnya antara lain: US, JP, dan GB.
Not nullable.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserPrincipalName
Nama prinsipal pengguna (UPN, User Principal Name) pengguna.
UPN adalah nama masuk gaya internet untuk pengguna berdasarkan RFC 822 standar internet.
Menurut konvensi, ini harus di petakan ke nama email pengguna.
Format umumnya alias@domainadalah, di mana domain harus ada dalam kumpulan penyewa domain terverifikasi.
Properti ini diperlukan saat pengguna dibuat.
Domain terverifikasi untuk penyewa bisa diakses dari properti verifiedDomains organisasi. CATATAN: Meskipun dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith, endsWith) dan $orderBy.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserType
Nilai string yang bisa digunakan untuk mengklasifikasikan tipe pengguna di direktori Anda, seperti Anggota dan Tamu.
Mendukung $filter (eq, ne, NOT, in,).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PASSWORDPROFILE <IMicrosoftGraphPasswordProfile>: passwordProfile
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[ForceChangePasswordNextSignIn <Boolean?>]`: true jika pengguna harus mengubah kata sandinya di login berikutnya; jika tidak false. Jika tidak diatur, defaultnya adalah false. CATATAN: Untuk penyewa Azure B2C, atur ke false, tetapi gunakan kebijakan kustom dan aliran pengguna untuk memaksa pengaturan ulang kata sandi pada kali pertama masuk. Lihat Mengatur ulang kata sandi saat masuk pertama kali.
  - `[ForceChangePasswordNextSignInWithMfa <Boolean?>]`: Jika benar, pada saat masuk berikutnya, pengguna harus melakukan multi-factor authentication (MFA) sebelum dipaksa mengubah kata sandinya. Perilaku ini identik dengan forceChangePasswordNextSignIn, kecuali bahwa pengguna diperlukan untuk melakukan multi-factor authentication terlebih dahulu sebelum kata sandi berubah. Setelah perubahan kata sandi, properti ini akan diatur ulang secara otomatis ke false. Jika tidak diatur, defaultnya adalah false.
  - `[Password <String>]`: Kata sandi untuk pengguna. Properti ini diperlukan saat pengguna dibuat. Kode ini dapat diperbarui, tetapi pengguna akan diminta untuk mengubah kata sandi pada login berikutnya. Kata sandi harus memenuhi persyaratan minimal seperti yang ditentukan oleh properti passwordPolicies pengguna. Secara default, kata sandi yang kuat diperlukan.

## RELATED LINKS
