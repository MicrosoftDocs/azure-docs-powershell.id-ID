---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azaduser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADUser.md
ms.openlocfilehash: 23d0e3c3796a0b0686f3538397b18d13241a16f4
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144570404"
---
# New-AzADUser

## SYNOPSIS
Menambahkan entitas baru ke pengguna

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

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

### Contoh 1: Membuat pengguna
```powershell
$pp = New-Object -TypeName "Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordProfile" -Property @{Password=$password}
New-AzADUser -DisplayName $uname -PasswordProfile $pp -AccountEnabled -MailNickname $nickname -UserPrincipalName $upn
```

Membuat pengguna

## PARAMETERS

### -AboutMe
Bidang entri teks bentuk bebas untuk dijelaskan sendiri oleh pengguna.
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
true untuk mengaktifkan akun; jika tidak, salah.

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
Nilai yang diizinkan: null, minor, notAdult dan adult.
Lihat definisi properti kelompok usia hukum untuk informasi lebih lanjut.
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

### -Ulang Tahun
Ulang tahun pengguna.
Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC.
Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z Dikembalikan hanya pada $select.

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
Kota tempat pengguna berada.
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
Properti ini dapat berguna untuk menjelaskan perusahaan asal pengguna eksternal.
Panjang maksimum nama perusahaan adalah 64 karakter. Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith).

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
Mengatur apakah persetujuan telah diperoleh untuk anak di bawah umur.
Nilai yang diizinkan: null, granted, denied, dan notRequired.
Lihat definisi properti kelompok usia hukum untuk informasi lebih lanjut.
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
Negara/wilayah tempat pengguna berada; misalnya, AS atau Inggris.
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
Nama departemen tempat pengguna bekerja.
Panjang maksimum adalah 64 karakter. Mendukung $filter (operator eq, ne, NOT , ge, le, dan in).

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
Batas jumlah maksimum perangkat yang diizinkan untuk didaftarkan pengguna.
Nilai yang diizinkan adalah 5 atau 1000.

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
Nama yang ditampilkan dalam buku alamat untuk pengguna.
Nilai ini biasanya merupakan kombinasi dari nama depan pengguna, inisial tengah, dan nama belakang pengguna.
Properti ini diperlukan ketika pengguna dibuat dan tidak dapat dibersihkan selama pembaruan.
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

### -EmployeeHireDate
Tanggal dan waktu saat pengguna dipekerjakan atau akan mulai bekerja jika terjadi persewaan di masa mendatang.
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
Pengidentifikasi karyawan yang ditetapkan untuk pengguna oleh organisasi.
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
Menangkap jenis pekerja perusahaan.
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
Untuk pengguna yang diundang, statusnya dapat Berupa PendingAcceptance atau Accepted, atau null untuk semua pengguna lain.
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
Memperlihatkan tanda waktu untuk perubahan terbaru pada properti externalUserState.
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
Ini harus ditentukan jika pengguna harus mengubah kata sandi pada login berhasil berikutnya (benar).
Perilaku default adalah (false) untuk tidak mengubah kata sandi pada login berikutnya yang berhasil.

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
Tanggal sewa pengguna.
Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC.
Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z.
Dikembalikan hanya pada $select.
Catatan: Properti ini khusus untuk SharePoint Online.
Sebaiknya gunakan properti employeeHireDate asli untuk mengatur dan memperbarui nilai tanggal sewa menggunakan Microsoft Graph API.

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
Properti ini digunakan untuk mengaitkan akun pengguna Active Directory lokal ke objek pengguna Azure AD mereka.
Properti ini harus ditentukan saat membuat akun pengguna baru di Graph jika Anda menggunakan domain federasi untuk properti userPrincipalName (UPN) pengguna.
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

### -Bunga
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
Jangan gunakan - dicadangkan untuk digunakan di masa mendatang.

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
Jabatan pengguna.
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
Perubahan pada properti ini juga akan memperbarui koleksi proxyAddresses pengguna untuk menyertakan nilai sebagai alamat SMTP.
Meskipun properti ini dapat berisi karakter aksen, menggunakannya dapat menyebabkan masalah akses dengan aplikasi Microsoft lainnya untuk pengguna.
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
Properti ini harus ditentukan ketika pengguna dibuat.
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
Daftar alamat email tambahan untuk pengguna; misalnya: ['bob@contoso.com', 'Robert@fabrikam.com']. CATATAN: Meskipun properti ini dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna. Mendukung $filter (eq, NOT, ge, le, in, startsWith).

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

### -Kata sandi
Kata sandi untuk pengguna.
Ini harus memenuhi persyaratan kompleksitas kata sandi penyewa.
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
Nilai ini adalah enumerasi dengan satu nilai yang mungkin adalah DisableStrongPassword, yang memungkinkan kata sandi yang lebih lemah daripada kebijakan default yang ditentukan.
DisablePasswordExpiration juga dapat ditentukan.
Keduanya dapat ditentukan bersama-sama; misalnya: DisablePasswordExpiration, DisableStrongPassword.Supports $filter (ne, NOT).

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
passwordProfile Untuk membangun, lihat bagian CATATAN untuk properti PASSWORDPROFILE dan buat tabel hash.

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
Kode pos khusus untuk negara/wilayah pengguna.
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
Nama yang disukai untuk pengguna.
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
Daftar bagi pengguna untuk menghitung tanggung jawab mereka.
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
Daftar bagi pengguna untuk menghitung sekolah yang telah mereka ikuti.
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
true jika daftar alamat global Outlook harus berisi pengguna ini, jika tidak salah.
Jika tidak diatur, ini akan diperlakukan sebagai benar.
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

### -Keterampilan
Daftar bagi pengguna untuk menghitung keterampilan mereka.
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

### -State
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

### -Nama Keluarga
Nama depan pengguna (nama keluarga atau nama belakang).
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
Diperlukan untuk pengguna yang akan diberi lisensi karena persyaratan hukum untuk memeriksa ketersediaan layanan di negara- negara.
Contohnya meliputi: US, JP, dan GB.
Tidak dapat diubah ke null.
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
Nama prinsipal pengguna (UPN) dari pengguna.
UPN adalah nama untuk masuk berbasis Internet untuk pengguna berdasarkan standar Internet RFC 822.
Menurut konvensi, ini harus dipetakan ke nama email pengguna.
Format umumnya adalah alias@domain, di mana domain harus ada dalam kumpulan domain terverifikasi penyewa.
Properti ini diperlukan saat pengguna dibuat.
Domain terverifikasi untuk penyewa dapat diakses dari properti organisasi verifiedDomains. CATATAN: Meskipun properti ini dapat berisi karakter aksen, properti ini dapat menyebabkan masalah akses ke aplikasi pihak pertama untuk pengguna.
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
Nilai string yang dapat digunakan untuk mengklasifikasikan jenis pengguna di direktori Anda, seperti Anggota dan Tamu.
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PASSWORDPROFILE <IMicrosoftGraphPasswordProfile>: passwordProfile
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[ForceChangePasswordNextSignIn <Boolean?>]`: benar jika pengguna harus mengubah kata sandinya pada login berikutnya; jika tidak salah. Jika tidak diatur, defaultnya adalah false. CATATAN: Untuk penyewa Azure B2C, atur ke false dan sebagai gantinya gunakan kebijakan kustom dan alur pengguna untuk memaksa reset kata sandi saat pertama kali masuk. Lihat Memaksa reset kata sandi pada saat pertama kali masuk.
  - `[ForceChangePasswordNextSignInWithMfa <Boolean?>]`: Jika true, pada rincian masuk berikutnya, pengguna harus melakukan autentikasi multifaktor (MFA) sebelum dipaksa untuk mengubah kata sandi mereka. Perilaku ini identik dengan forceChangePasswordNextSignIn kecuali bahwa pengguna harus terlebih dahulu melakukan autentikasi multifaktor sebelum perubahan kata sandi. Setelah perubahan kata sandi, properti ini akan secara otomatis direset ke false. Jika tidak diatur, defaultnya adalah false.
  - `[Password <String>]`: Kata sandi untuk pengguna. Properti ini diperlukan saat pengguna dibuat. Ini dapat diperbarui, tetapi pengguna akan diminta untuk mengubah kata sandi pada login berikutnya. Kata sandi harus memenuhi persyaratan minimum seperti yang ditentukan oleh properti passwordPolicies pengguna. Secara default, kata sandi yang kuat diperlukan.

## RELATED LINKS
