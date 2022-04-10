---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azadapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADApplication.md
ms.openlocfilehash: 7a8999cfb3338869adce02ecc03162c7e021e4e9
ms.sourcegitcommit: b346b2fbd8b25f54759984e75ddbee3304921c43
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2022
ms.locfileid: "140663841"
---
# New-AzADApplication

## SYNOPSIS
Menambahkan entitas baru ke aplikasi

[!INCLUDE [msgraph-migration-banner-az7](../../includes/msgraph-migration-banner-az7.md)]

## SYNTAX

### ApplicationWithoutCredentialParameterSet (Default)
```
New-AzADApplication -DisplayName <String> [-AvailableToOtherTenants <Boolean>] [-HomePage <String>]
 [-ReplyUrls <String[]>] [-IdentifierUri <String[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-ApplicationTemplateId <String>] [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>]
 [-Description <String>] [-DisabledByMicrosoftStatus <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>] [-DefaultProfile <PSObject>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ApplicationWithKeyCredentialParameterSet
```
New-AzADApplication -DisplayName <String> [-AvailableToOtherTenants <Boolean>] [-HomePage <String>]
 [-ReplyUrls <String[]>] [-IdentifierUri <String[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-ApplicationTemplateId <String>] [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>]
 [-Description <String>] [-DisabledByMicrosoftStatus <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>] -KeyCredentials <IMicrosoftGraphKeyCredential[]>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithPasswordCredentialParameterSet
```
New-AzADApplication -DisplayName <String> [-AvailableToOtherTenants <Boolean>] [-HomePage <String>]
 [-ReplyUrls <String[]>] [-IdentifierUri <String[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-ApplicationTemplateId <String>] [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>]
 [-Description <String>] [-DisabledByMicrosoftStatus <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 -PasswordCredentials <IMicrosoftGraphPasswordCredential[]> [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationWithKeyPlainParameterSet
```
New-AzADApplication -DisplayName <String> [-AvailableToOtherTenants <Boolean>] [-HomePage <String>]
 [-ReplyUrls <String[]>] [-IdentifierUri <String[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-ApplicationTemplateId <String>] [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>]
 [-Description <String>] [-DisabledByMicrosoftStatus <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>] -CertValue <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithPasswordPlainParameterSet
```
New-AzADApplication -DisplayName <String> [-AvailableToOtherTenants <Boolean>] [-HomePage <String>]
 [-ReplyUrls <String[]>] [-IdentifierUri <String[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-ApplicationTemplateId <String>] [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>]
 [-Description <String>] [-DisabledByMicrosoftStatus <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>] [-StartDate <DateTime>] [-EndDate <DateTime>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menambahkan entitas baru ke aplikasi

## EXAMPLES

### Contoh 1: Buat aplikasi
```powershell
PS C:\> New-AzADApplication -SigninAudience AzureADandPersonalMicrosoftAccount
```

Buat aplikasi dengan audiens masuk 'AzureADandPersonalMicrosoftAccount', opsi lain yang tersedia adalah: 'AzureADMyOrg', 'AzureADMultipleOrgs', 'PersonalMicrosoftAccount'

## PARAMETERS

### -AddIn
Menentukan perilaku kustom yang dapat digunakan oleh layanan untuk memanggil aplikasi dalam konteks tertentu.
Misalnya, aplikasi yang dapat menyajikan streaming file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'.
Ini akan memungkinkan layanan Office 365 panggilan aplikasi dalam konteks dokumen yang sedang digunakan pengguna.
Untuk membuat, lihat bagian CATATAN untuk properti ADDIN dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphAddIn[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Api
apiApplication To construct, see NOTES section for API properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApiApplication
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTemplateId
Pengidentifikasi unik aplikasiTemplate.

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

### -AppRole
Kumpulan peran yang ditetapkan untuk aplikasi.
Dengan penetapan peran aplikasi, peran ini dapat ditetapkan kepada pengguna, grup, atau prinsipal layanan yang terkait dengan aplikasi lainnya.
Not nullable.
Untuk membuat, lihat bagian CATATAN untuk properti APPROLE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphAppRole[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AvailableToOtherTenants
Nilai yang menentukan apakah aplikasi merupakan penyewa tunggal atau multi-penyewa.
Sama dengan '-SignInAudience AzureADMultipleOrgs' saat tombol aktif

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertValue
Nilai tipe kredensial 'asimetris'.
Kode ini mewakili sertifikat berkode basis 64.

```yaml
Type: System.String
Parameter Sets: ApplicationWithKeyPlainParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreatedOnBehalfOfDeletedDateTime
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

### -Deskripsi
Deskripsi opsional dari aplikasi.
Dikembalikan secara default.
Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.

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

### -DisabledByMicrosoftStatus
Menentukan apakah Microsoft telah menonaktifkan aplikasi yang terdaftar.
Nilai yang mungkin adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasan dapat mencantumkan aktivitas yang mencurigakan, melecehkan, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).
Mendukung $filter (eq, ne, NOT).

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

### -DisplayName
Nama tampilan untuk aplikasi.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith), $search, dan $orderBy.

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

### -EndDate
Tanggal berakhir efektif penggunaan kredensial.
Nilai tanggal akhir default adalah satu tahun dari hari ini.
Untuk kredensial tipe 'asimetris', kredensial ini harus diatur ke aktif atau sebelum tanggal sertifikat X509 valid.

```yaml
Type: System.DateTime
Parameter Sets: ApplicationWithKeyPlainParameterSet, ApplicationWithPasswordPlainParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupMembershipClaim
Mengonfigurasi klaim grup yang diterbitkan di pengguna atau token akses OAuth 2.0 yang diharapkan oleh aplikasi.
Untuk mengatur atribut ini, gunakan salah satu dari nilai string berikut ini: Tidak Ada, Grup Keamanan (untuk grup keamanan dan peran Azure AD), Semua (ini mendapatkan semua grup keamanan, grup distribusi, dan peran direktori Azure AD di mana pengguna yang masuk adalah anggotanya).

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

### -HomePage
URL ke laman aplikasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: WebHomePageUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HomeRealmDiscoveryPolicy
.
Untuk membuat, lihat bagian CATATAN untuk properti HOMEREALMDISCOVERYPOLICY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphHomeRealmDiscoveryPolicy[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentifierUri
URI yang mengidentifikasi aplikasi.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: IdentifierUris

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Info
informationalUrl To construct, lihat bagian CATATAN untuk properti INFO dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphInformationalUrl
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsDeviceOnlyAuth Didukung
Menentukan apakah aplikasi ini mendukung autentikasi perangkat tanpa pengguna.
Defaultnya adalah false.

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

### -IsFallbackPublicClient
Menentukan tipe aplikasi fallback sebagai klien publik, seperti aplikasi terinstal yang berjalan pada perangkat seluler.
Nilai default adalah false, yang berarti tipe aplikasi merupakan klien rahasia seperti aplikasi web.
Terdapat skenario tertentu ketika Azure AD tidak dapat menentukan tipe aplikasi klien.
Misalnya, aliran ROPC tempat aplikasi dikonfigurasi tanpa menentukan URI pengalihan.
Dalam kasus tersebut, Azure AD menginterpretasikan tipe aplikasi berdasarkan nilai properti ini.

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

### -KeyCredentials
kredensial kunci terkait dengan aplikasi.
Untuk membuat, lihat bagian CATATAN untuk properti KEYCREDENTIALS dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential[]
Parameter Sets: ApplicationWithKeyCredentialParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogoInputFile
File Input untuk Logo (Logo utama untuk aplikasi.
Not nullable.)

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

### -Note
Catatan yang relevan untuk manajemen aplikasi.

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

### -Oauth2RequirePostResponse
.

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

### -OptionalClaim
optionalClaims Untuk membangun, baca bagian CATATAN untuk properti OPTIONALCLAIM dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphOptionalClaims
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentalControlSetting
parentalControlSettings Untuk membangun, lihat bagian CATATAN untuk properti PARENTALCONTROLSETTING dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphParentalControlSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordCredentials
Kredensial kata sandi yang terkait dengan aplikasi.
Untuk membuat, lihat bagian CATATAN untuk properti PASSWORDCREDENTIALS dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential[]
Parameter Sets: ApplicationWithPasswordCredentialParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicClientRedirectUri

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

### -ReplyUrls
Url balasan aplikasi.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: WebRedirectUri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredResourceAccess
Menentukan sumber daya yang dibutuhkan aplikasi untuk diakses.
Properti ini juga menentukan kumpulan lingkup izin OAuth dan peran aplikasi yang diperlukannya untuk setiap sumber daya tersebut.
Konfigurasi akses ke sumber daya yang diperlukan ini akan mendorong pengalaman persetujuan.
Not nullable.
Mendukung $filter (eq, NOT, ge, le).
Untuk membuat, lihat bagian CATATAN untuk properti REQUIREDRESOURCEACCESS dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphRequiredResourceAccess[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignInAudience
Menentukan akun Microsoft yang didukung untuk aplikasi saat ini.
Nilai yang didukung adalah: AzureADMyOrg, AzureADMultipleOrgs, AzureADandPersonalMicrosoftAccount, PersonalMicrosoftAccount.
Lihat selengkapnya dalam tabel di bawah ini.
Mendukung $filter (eq, ne, NOT).

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

### -SPARedirectUri

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

### -StartDate
Tanggal mulai efektif penggunaan kredensial.
Nilai tanggal mulai default adalah hari ini.
Untuk kredensial tipe 'asimetris', kredensial ini harus diatur ke aktif atau setelah tanggal sertifikat X509 valid.

```yaml
Type: System.DateTime
Parameter Sets: ApplicationWithKeyPlainParameterSet, ApplicationWithPasswordPlainParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
String kustom yang bisa digunakan untuk mengkategorikan dan mengidentifikasi aplikasi.
Not nullable. Mendukung $filter (eq, NOT, ge, le, startsWith).

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

### -TokenEncryptionKeyId
Menentukan keyId dari kunci publik dari koleksi keyCredentials.
Ketika dikonfigurasi, Azure AD mengenkripsi semua token yang disimpan dengan menggunakan kunci yang ditugasi properti ini.
Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci pribadi yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.

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

### -TokenIssuancePolicy
.
Untuk membuat, lihat bagian CATATAN untuk properti TOKENISSUANCEPOLICY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphTokenIssuancePolicy[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TokenLifetimePolicy
TokenLifetimePolicies ditetapkan untuk aplikasi ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti TOKENLIFETIMEPOLICY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphTokenLifetimePolicy[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Web
webApplication To construct, lihat bagian CATATAN untuk properti WEB dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphWebApplication
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ADDIN <IMicrosoftGraphAddIn[]>: Menentukan perilaku kustom yang dapat digunakan oleh layanan yang digunakan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat menyajikan streaming file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'. Ini akan memungkinkan layanan Office 365 panggilan aplikasi dalam konteks dokumen yang sedang digunakan pengguna.
  - `[Id <String>]`: 
  - `[Property <IMicrosoftGraphKeyValue[]>]`: 
    - `[Key <String>]`: Kunci.
    - `[Value <String>]`: Nilai.
  - `[Type <String>]`: 

API <IMicrosoftGraphApiApplication>: apiApplication
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AcceptMappedClaim <Boolean?>]`: Bila benar, memperbolehkan aplikasi menggunakan pemetaan klaim tanpa menentukan kunci penandatanganan kustom.
  - `[KnownClientApplication <String[]>]`: Digunakan untuk persetujuan bunding jika Anda mempunyai solusi yang berisi dua komponen: aplikasi klien dan aplikasi web API kustom. Jika Anda menetapkan ID aplikasi aplikasi klien ke nilai ini, pengguna hanya menyetujui satu kali untuk aplikasi klien. Azure AD mengetahui bahwa persetujuan terhadap klien berarti secara implisit menyetujui API web dan secara otomatis menyediakan prinsipal layanan untuk kedua API secara bersamaan. Klien dan aplikasi API web harus terdaftar dalam penyewa yang sama.
  - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Definisi izin yang didelegasikan yang diekspos oleh API web yang diwakili oleh pendaftaran aplikasi ini. Izin yang didelegasikan ini mungkin diminta oleh aplikasi klien, dan dapat diberikan oleh pengguna atau administrator selama persetujuan. Izin yang didelegasikan terkadang disebut sebagai lingkup OAuth 2.0.
    - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin tingkat penyewa.
    - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
    - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik dalam kumpulan izin yang didelegasikan yang ditetapkan untuk aplikasi sumber daya.
    - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus diatur ke salah terlebih dahulu.  Pada tahap ini, dalam panggilan berikutnya, izin mungkin dihapus.
    - `[Origin <String>]`: 
    - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diperlukan untuk menyetujui izin. Ini akan menjadi perilaku default, tapi setiap pelanggan bisa memilih untuk mengkustomisasi perilaku di organisasi mereka (dengan mengizinkan, membatasi atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
    - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberi izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
    - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (lingkup) di token akses. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[PreAuthorizedApplication <IMicrosoftGraphPreAuthorizedApplication[]>]`: Mencantumkan aplikasi klien yang telah diberi otorisasi sebelumnya dengan izin delegasi tertentu untuk mengakses API aplikasi ini. Pengguna tidak diharuskan untuk menyetujui aplikasi apa pun yang telah diotorisasi (untuk izin yang ditentukan). Namun, setiap izin tambahan yang tidak tercantum dalam preAuthorizedApplications (diminta melalui persetujuan bertahap misalnya) akan memerlukan persetujuan pengguna.
    - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi.
    - `[DelegatedPermissionId <String[]>]`: Pengidentifikasi unik untuk oauth2PermissionScopes yang diperlukan aplikasi.
  - `[RequestedAccessTokenVersion <Int32?>]`: Menentukan versi token akses yang diharapkan oleh sumber daya ini. Hal ini akan mengubah versi dan format JWT yang dihasilkan terpisah dari titik akhir atau klien yang digunakan untuk meminta token akses.  Titik akhir yang digunakan, v1.0 atau v2.0, dipilih oleh klien dan hanya akan memengaruhi versi id_tokens. Sumber daya harus mengonfigurasi secara eksplisit requestedAccessTokenVersion untuk menunjukkan format token akses yang didukung.  Nilai yang mungkin untuk requestedAccessTokenVersion adalah 1, 2, atau null. Jika nilai null, defaultnya adalah 1, yang terkait dengan titik akhir v1.0.  Jika signInAudience pada aplikasi dikonfigurasi sebagai AzureADandPersonalMicrosoftAccount, nilai untuk properti ini harus 2

APPROLE <IMicrosoftGraphAppRole[]>: Kumpulan peran yang ditetapkan untuk aplikasi. Dengan penetapan peran aplikasi, peran ini dapat ditetapkan kepada pengguna, grup, atau prinsipal layanan yang terkait dengan aplikasi lainnya. Not nullable.
  - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan kepada pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lainnya (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke prinsipal layanan aplikasi lainnya juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditetapkan pada entitas aplikasi.
  - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
  - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam pengalaman penetapan peran dan persetujuan aplikasi.
  - `[Id <String>]`: Pengidentifikasi peran unik di dalam kumpulan peran aplikasi. Ketika membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
  - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus sebuah peran, ini harus terlebih dahulu disetel ke false.  Pada tahap ini, dalam panggilan berikutnya, peran ini mungkin dihapus.
  - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran di token ID dan token akses yang mengotentikan pengguna atau prinsipal layanan yang ditetapkan. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..

HOMEREALMDISCOVERYPOLICY <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>: .
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

INFO <IMicrosoftGraphInformationalUrl>: informationalUrl
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[MarketingUrl <String>]`: Menautkan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
  - `[PrivacyStatementUrl <String>]`: Menautkan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
  - `[SupportUrl <String>]`: Menautkan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
  - `[TermsOfServiceUrl <String>]`: Menautkan ke ketentuan pernyataan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice

KEYCREDENTIALS <IMicrosoftGraphKeyCredential[]>: kredensial kunci yang terkait dengan aplikasi.
  - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
  - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kunci tersebut. Opsional.
  - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kredensial kedaluwarsa. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
  - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus merupakan nilai berkodekan 64 basis.
  - `[KeyId <String>]`: Pengidentifikasi unik (GUID) kunci tersebut.
  - `[StartDateTime <DateTime?>]`: Tanggal dan waktu saat kredensial menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
  - `[Type <String>]`: Tipe kredensial kunci; misalnya, 'Simetri'.
  - `[Usage <String>]`: String yang menjelaskan tujuan untuk menggunakan kunci; misalnya, 'Verifikasi'.

OPTIONALCLAIM <IMicrosoftGraphOptionalClaims>: optionalClaims
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AccessToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan di token akses JWT.
    - `[AdditionalProperty <String[]>]`: Properti tambahan klaim. Jika ada properti dalam kumpulan ini, properti ini mengubah perilaku klaim opsional yang ditentukan dalam properti nama.
    - `[Essential <Boolean?>]`: Jika nilai tersebut benar, klaim yang ditentukan oleh klien diperlukan untuk memastikan pengalaman otorisasi yang lancar untuk tugas tertentu yang diminta oleh pengguna akhir. Nilai default adalah false.
    - `[Name <String>]`: Nama klaim opsional.
    - `[Source <String>]`: Sumber (objek direktori) klaim. Ada klaim yang sudah ditentukan sebelumnya dan klaim yang ditentukan pengguna dari properti ekstensi. Jika nilai sumber null, klaim adalah klaim opsional yang sudah ditentukan sebelumnya. Jika nilai sumber adalah pengguna, nilai dalam properti nama adalah properti ekstensi dari objek pengguna.
  - `[IdToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan di token JWT ID.
  - `[Saml2Token <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional dikembalikan dalam token SAML.

PARENTALCONTROLSETTING <IMicrosoftGraphParentalControlSettings>: parentalControlSettings
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[CountriesBlockedForMinor <String[]>]`: Menentukan kode negara ISO dua huruf. Akses ke aplikasi akan diblokir untuk pengguna di bawah umur dari negara yang ditentukan dalam daftar ini.
  - `[LegalAgeGroupRule <String>]`: Menentukan aturan grup usia legal yang berlaku bagi pengguna aplikasi. Dapat diatur ke salah satu nilai berikut: ValueDescriptionAllowDefault. Menerapkan minimum hukum. Ini berarti persetujuan orang tua diperlukan untuk anak di bawah umur di Uni Eropa dan Korea.RequireConsentForPrivacyServicesEnforces pengguna untuk menentukan tanggal lahir untuk mematuhi aturan COPPA. RequireConsentForMinorsRequires parental consent for ages below 18, regardless of country minor rules. RequireConsentForKidsRequires parental consent for ages below 14, regardless of country minor rules. BlockMinorsBlocks minors tidak menggunakan aplikasi.

PASSWORDCREDENTIALS <IMicrosoftGraphPasswordCredential[]>: Kredensial kata sandi yang terkait dengan aplikasi.
  - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
  - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kata sandi. Opsional.
  - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kata sandi kedaluwarsa yang dinyatakan menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
  - `[StartDateTime <DateTime?>]`: Tanggal dan waktu valid ketika kata sandi menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.

REQUIREDRESOURCEACCESS <IMicrosoftGraphRequiredResourceAccess[]>: Menentukan sumber daya yang dibutuhkan aplikasi untuk mengaksesnya. Properti ini juga menentukan kumpulan lingkup izin OAuth dan peran aplikasi yang diperlukannya untuk setiap sumber daya tersebut. Konfigurasi akses ke sumber daya yang diperlukan ini akan mendorong pengalaman persetujuan. Not nullable. Mendukung $filter (eq, NOT, ge, le).
  - `[ResourceAccess <IMicrosoftGraphResourceAccess[]>]`: Daftar lingkup izin OAuth2.0 dan peran aplikasi yang diperlukan aplikasi dari sumber daya yang ditentukan.
    - `[Id <String>]`: Pengidentifikasi unik untuk salah satu instans oauth2PermissionScopes atau appRole yang digunakan oleh aplikasi sumber daya.
    - `[Type <String>]`: Menentukan apakah properti id merujuk pada oauth2PermissionScopes atau appRole. Nilai yang mungkin adalah Lingkup atau Peran.
  - `[ResourceAppId <String>]`: Pengidentifikasi unik untuk sumber daya yang memerlukan akses aplikasi.  Ini harus sama dengan appId yang dideklarasikan pada aplikasi sumber daya target.

TOKENISSUANCEPOLICY <IMicrosoftGraphTokenIssuancePolicy[]>: .
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

TOKENLIFETIMEPOLICY <IMicrosoftGraphTokenLifetimePolicy[]>: TokenLifetimePolicies yang ditetapkan untuk aplikasi ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

WEB <IMicrosoftGraphWebApplication>: webApplication
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[HomePageUrl <String>]`: Laman atau halaman awal aplikasi.
  - `[ImplicitGrantSetting <IMicrosoftGraphImplicitGrantSettings>]`: implisitGrantSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[EnableAccessTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token akses menggunakan aliran implisit OAuth 2.0.
    - `[EnableIdTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token ID menggunakan aliran implisit OAuth 2.0.
  - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk membuat logo pengguna menggunakan protokol logout saluran depan, saluran belakang, atau SAML.
  - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi dan token akses OAuth 2.0 dikirim.

## RELATED LINKS

## RELATED LINKS
