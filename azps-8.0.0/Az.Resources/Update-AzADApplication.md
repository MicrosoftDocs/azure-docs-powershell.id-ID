---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/update-azadapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzADApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzADApplication.md
ms.openlocfilehash: 9ae5fb38d83401b33a4e077afad4107160e1feb5
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145536531"
---
# Update-AzADApplication

## SYNOPSIS
Memperbarui entitas dalam aplikasi

## SYNTAX

### ApplicationObjectIdWithUpdateParamsParameterSet (Default)
```
Update-AzADApplication -ObjectId <String> [-HomePage <String>] [-ReplyUrl <String[]>]
 [-AvailableToOtherTenants <Boolean>] [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>]
 [-AppRole <IMicrosoftGraphAppRole[]>] [-ApplicationTemplateId <String>]
 [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>] [-Description <String>]
 [-DisabledByMicrosoftStatus <String>] [-DisplayName <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>] [-IdentifierUri <String[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationIdWithUpdateParamsParameterSet
```
Update-AzADApplication -ApplicationId <Guid> [-HomePage <String>] [-ReplyUrl <String[]>]
 [-AvailableToOtherTenants <Boolean>] [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>]
 [-AppRole <IMicrosoftGraphAppRole[]>] [-ApplicationTemplateId <String>]
 [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>] [-Description <String>]
 [-DisabledByMicrosoftStatus <String>] [-DisplayName <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>] [-IdentifierUri <String[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectWithUpdateParamsParameterSet
```
Update-AzADApplication -InputObject <IMicrosoftGraphApplication> [-HomePage <String>] [-ReplyUrl <String[]>]
 [-AvailableToOtherTenants <Boolean>] [-AddIn <IMicrosoftGraphAddIn[]>] [-Api <IMicrosoftGraphApiApplication>]
 [-AppRole <IMicrosoftGraphAppRole[]>] [-ApplicationTemplateId <String>]
 [-CreatedOnBehalfOfDeletedDateTime <DateTime>] [-DeletedDateTime <DateTime>] [-Description <String>]
 [-DisabledByMicrosoftStatus <String>] [-DisplayName <String>] [-GroupMembershipClaim <String>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>] [-IdentifierUri <String[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-IsDeviceOnlyAuthSupported] [-IsFallbackPublicClient]
 [-LogoInputFile <String>] [-Note <String>] [-Oauth2RequirePostResponse]
 [-OptionalClaim <IMicrosoftGraphOptionalClaims>]
 [-ParentalControlSetting <IMicrosoftGraphParentalControlSettings>] [-PublicClientRedirectUri <String[]>]
 [-RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>] [-SignInAudience <String>]
 [-SPARedirectUri <String[]>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>] [-Web <IMicrosoftGraphWebApplication>]
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui entitas dalam aplikasi

## EXAMPLES

### Contoh 1: Memperbarui aplikasi berdasarkan nama tampilan
```powershell
Update-AzADApplication -DisplayName $name -HomePage $homepage
```

Perbarui aplikasi menurut nama tampilan

### Contoh 2: Memperbarui aplikasi berdasarkan input alur
```powershell
Get-AzADApplication -ObjectId $id | Update-AzADApplication -ReplyUrl $replyurl
```

Memperbarui aplikasi berdasarkan input alur

## PARAMETERS

### -AddIn
Mendefinisikan perilaku khusus yang layanan yang memanfaatkan dapat gunakan untuk memanggil aplikasi dalam konteks tertentu.
Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'-nya.
Ini akan memungkinkan layanan seperti Office 365 memanggil aplikasi dalam konteks dokumen yang sedang digabungkan pengguna.
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
apiApplication Untuk membangun, lihat bagian CATATAN untuk properti API dan membuat tabel hash.

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

### -ApplicationId
kunci: id aplikasi

```yaml
Type: System.Guid
Parameter Sets: ApplicationIdWithUpdateParamsParameterSet
Aliases: AppId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTemplateId
Pengidentifikasi unik dari applicationTemplate.

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
Kumpulan peran yang ditetapkan ke aplikasi.
Dengan penetapan peran aplikasi, peran ini dapat ditetapkan ke pengguna, grup, atau perwakilan layanan yang terkait dengan aplikasi lain.
Tidak dapat diubah ke null.
Untuk membuat, lihat bagian CATATAN untuk properti APPROLE dan buat tabel hash.

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
Nilai yang menentukan apakah aplikasi adalah penyewa tunggal atau multi-penyewa.
Setara dengan '-SignInAudience AzureADMultipleOrgs' saat aktif

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
Deskripsi opsional aplikasi.
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
Menentukan apakah Microsoft telah menonaktifkan aplikasi terdaftar.
Nilai yang mungkin adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasannya mungkin termasuk aktivitas yang mencurigakan, melecehkan, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupMembershipClaim
Mengonfigurasi klaim grup yang dikeluarkan dalam token akses pengguna atau OAuth 2.0 yang diharapkan aplikasi.
Untuk mengatur atribut ini, gunakan salah satu nilai string berikut: Tidak ada, SecurityGroup (untuk grup keamanan dan peran Azure AD), Semua (ini mendapatkan semua grup keamanan, grup distribusi, dan peran direktori Azure AD tempat pengguna yang masuk adalah anggotanya).

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

### -Beranda
url halaman beranda untuk web

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
Untuk membuat, lihat bagian CATATAN untuk properti HOMEREALMDISCOVERYPOLICY dan buat tabel hash.

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
URI yang mengidentifikasi aplikasi dalam penyewa Azure AD, atau dalam domain kustom terverifikasi jika aplikasi adalah multi-penyewa.
Untuk informasi selengkapnya, lihat Objek Aplikasi dan Objek Perwakilan Layanan.
Operator apa pun diperlukan untuk ekspresi filter pada properti multinilai.
Tidak dapat diubah ke null.
Mendukung $filter (eq, ne, ge, le, startsWith).

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
informationalUrl To construct, lihat bagian NOTES untuk properti INFO dan membuat tabel hash.

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

### -InputObject
kunci: objek aplikasi Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication
Parameter Sets: InputObjectWithUpdateParamsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsDeviceOnlyAuthSupported
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
Menentukan jenis aplikasi fallback sebagai klien publik, seperti aplikasi yang diinstal yang berjalan pada perangkat seluler.
Nilai default adalah false yang berarti jenis aplikasi fallback adalah klien rahasia seperti aplikasi web.
Ada skenario tertentu di mana Azure AD tidak dapat menentukan jenis aplikasi klien.
Misalnya, alur ROPC tempat aplikasi dikonfigurasi tanpa menentukan URI pengalihan.
Dalam kasus tersebut Azure AD menginterpretasikan jenis aplikasi berdasarkan nilai properti ini.

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

### -LogoInputFile
File Input untuk Logo (Logo utama untuk aplikasi.
Tidak dapat diubah ke null.)

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

### -Catatan
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

### -ObjectId
kunci: id aplikasi

```yaml
Type: System.String
Parameter Sets: ApplicationObjectIdWithUpdateParamsParameterSet
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptionalClaim
optionalClaims To construct, lihat bagian NOTES untuk properti OPTIONALCLAIM dan buat tabel hash.

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
parentalControlSettings Untuk membangun, lihat bagian CATATAN untuk properti PARENTALCONTROLSETTING dan buat tabel hash.

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

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ReplyUrl
Url balasan aplikasi.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ReplyUrls, WebRedirectUri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredResourceAccess
Menentukan sumber daya yang perlu diakses aplikasi.
Properti ini juga menentukan kumpulan cakupan izin OAuth dan peran aplikasi yang dibutuhkan untuk masing-masing sumber daya tersebut.
Konfigurasi akses ke sumber daya yang diperlukan ini mendorong pengalaman persetujuan.
Tidak dapat diubah ke null.
Mendukung $filter (eq, NOT, ge, le).
Untuk membuat, lihat bagian CATATAN untuk properti REQUIREDRESOURCEACCESS dan buat tabel hash.

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

### -Tag
String kustom yang dapat digunakan untuk mengategorikan dan mengidentifikasi aplikasi.
Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le, startsWith).

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
Menentukan keyId kunci publik dari koleksi keyCredentials.
Saat dikonfigurasi, Azure AD mengenkripsi semua token yang dikeluarkannya dengan menggunakan kunci yang ditunjukkan properti ini.
Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci privat yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.

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
TokenLifetimePolicies yang ditetapkan ke aplikasi ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti TOKENLIFETIMEPOLICY dan buat tabel hash.

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
webApplication Untuk membangun, lihat bagian CATATAN untuk properti WEB dan membuat tabel hash.

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

Set-AzADApplication

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ADDIN <IMicrosoftGraphAddIn[]>: Menentukan perilaku kustom yang dapat digunakan layanan penggunaan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'-nya. Ini akan memungkinkan layanan seperti Office 365 memanggil aplikasi dalam konteks dokumen yang sedang digabungkan pengguna.
  - `[Id <String>]`: 
  - `[Property <IMicrosoftGraphKeyValue[]>]`: 
    - `[Key <String>]`: Kunci.
    - `[Value <String>]`: Nilai.
  - `[Type <String>]`: 

API <IMicrosoftGraphApiApplication>: apiApplication
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AcceptMappedClaim <Boolean?>]`: Jika true, memungkinkan aplikasi untuk menggunakan pemetaan klaim tanpa menentukan kunci penandatanganan kustom.
  - `[KnownClientApplication <String[]>]`: Digunakan untuk persetujuan bundling jika Anda memiliki solusi yang berisi dua bagian: aplikasi klien dan aplikasi API web kustom. Jika Anda mengatur appID aplikasi klien ke nilai ini, pengguna hanya menyetujui sekali ke aplikasi klien. Azure AD tahu bahwa menyetujui klien berarti secara implisit menyetujui API web dan secara otomatis memprovisikan perwakilan layanan untuk kedua API secara bersamaan. Baik klien dan aplikasi API web harus terdaftar pada penyewa yang sama.
  - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Definisi izin yang didelegasikan yang diekspos oleh API web yang diwakili oleh pendaftaran aplikasi ini. Izin yang didelegasikan ini dapat diminta oleh aplikasi klien, dan dapat diberikan oleh pengguna atau administrator selama persetujuan. Izin yang didelegasikan terkadang disebut sebagai cakupan OAuth 2.0.
    - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin di seluruh penyewa.
    - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
    - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik di dalam kumpulan izin yang didelegasikan yang ditentukan untuk aplikasi sumber daya.
    - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, izin dapat dihapus.
    - `[Origin <String>]`: 
    - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diminta untuk menyetujui izin. Ini akan menjadi perilaku default, tetapi setiap pelanggan dapat memilih untuk menyesuaikan perilaku di organisasi mereka (dengan mengizinkan, membatasi, atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
    - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
    - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (cakupan) dalam token akses. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[PreAuthorizedApplication <IMicrosoftGraphPreAuthorizedApplication[]>]`: Mencantumkan aplikasi klien yang telah diotorisasi sebelumnya dengan izin yang didelegasikan yang ditentukan untuk mengakses API aplikasi ini. Pengguna tidak diharuskan menyetujui aplikasi pra-otorisasi apa pun (untuk izin yang ditentukan). Namun, izin tambahan apa pun yang tidak tercantum dalam preAuthorizedApplications (diminta melalui persetujuan inkremental misalnya) akan memerlukan persetujuan pengguna.
    - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi.
    - `[DelegatedPermissionId <String[]>]`: Pengidentifikasi unik untuk oauth2PermissionScopes yang dibutuhkan aplikasi.
  - `[RequestedAccessTokenVersion <Int32?>]`: Menentukan versi token akses yang diharapkan oleh sumber daya ini. Ini mengubah versi dan format JWT yang diproduksi independen dari titik akhir atau klien yang digunakan untuk meminta token akses.  Titik akhir yang digunakan, v1.0 atau v2.0, dipilih oleh klien dan hanya berdampak pada versi id_tokens. Sumber daya perlu secara eksplisit mengonfigurasi requestedAccessTokenVersion untuk menunjukkan format token akses yang didukung.  Nilai yang mungkin untuk requestedAccessTokenVersion adalah 1, 2, atau null. Jika nilainya null, nilai ini default ke 1, yang sesuai dengan titik akhir v1.0.  Jika signInAudience pada aplikasi dikonfigurasi sebagai AzureADandPersonalMicrosoftAccount, nilai untuk properti ini harus 2

APPROLE <IMicrosoftGraphAppRole[]>: Kumpulan peran yang ditetapkan ke aplikasi. Dengan penetapan peran aplikasi, peran ini dapat ditetapkan ke pengguna, grup, atau perwakilan layanan yang terkait dengan aplikasi lain. Tidak dapat diubah ke null.
  - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan ke pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lain (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke perwakilan layanan aplikasi lain juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditentukan pada entitas aplikasi.
  - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
  - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam penetapan peran aplikasi dan pengalaman persetujuan.
  - `[Id <String>]`: Pengidentifikasi peran unik di dalam koleksi appRoles. Saat membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
  - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus peran, ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, peran ini dapat dihapus.
  - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran dalam token ID dan token akses yang mengautentikasi pengguna atau perwakilan layanan yang ditetapkan. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..

HOMEREALMDISCOVERYPOLICY <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>: .
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

INFO <IMicrosoftGraphInformationalUrl>: informationalUrl
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[MarketingUrl <String>]`: Tautan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
  - `[PrivacyStatementUrl <String>]`: Tautan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
  - `[SupportUrl <String>]`: Tautan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
  - `[TermsOfServiceUrl <String>]`: Tautkan ke pernyataan ketentuan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice

INPUTOBJECT <IMicrosoftGraphApplication>: kunci: objek aplikasi
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AddIn <IMicrosoftGraphAddIn[]>]`: Menentukan perilaku kustom yang dapat digunakan layanan yang menggunakan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'- nya. Ini akan memungkinkan layanan seperti Office 365 memanggil aplikasi dalam konteks dokumen yang sedang digarap pengguna.
    - `[Id <String>]`: 
    - `[Property <IMicrosoftGraphKeyValue[]>]`: 
      - `[Key <String>]`: Kunci.
      - `[Value <String>]`: Nilai.
    - `[Type <String>]`: 
  - `[Api <IMicrosoftGraphApiApplication>]`: apiApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[AcceptMappedClaim <Boolean?>]`: Jika true, memungkinkan aplikasi untuk menggunakan pemetaan klaim tanpa menentukan kunci penandatanganan kustom.
    - `[KnownClientApplication <String[]>]`: Digunakan untuk persetujuan bundling jika Anda memiliki solusi yang berisi dua bagian: aplikasi klien dan aplikasi API web kustom. Jika Anda mengatur appID aplikasi klien ke nilai ini, pengguna hanya menyetujui sekali ke aplikasi klien. Azure AD tahu bahwa menyetujui klien berarti secara implisit menyetujui API web dan secara otomatis menyediakan perwakilan layanan untuk kedua API secara bersamaan. Baik klien dan aplikasi API web harus terdaftar pada penyewa yang sama.
    - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Definisi izin yang didelegasikan yang diekspos oleh API web yang diwakili oleh pendaftaran aplikasi ini. Izin yang didelegasikan ini dapat diminta oleh aplikasi klien, dan dapat diberikan oleh pengguna atau administrator selama persetujuan. Izin yang didelegasikan terkadang disebut sebagai cakupan OAuth 2.0.
      - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin di seluruh penyewa.
      - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
      - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik di dalam kumpulan izin yang didelegasikan yang ditentukan untuk aplikasi sumber daya.
      - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, izin dapat dihapus.
      - `[Origin <String>]`: 
      - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diminta untuk menyetujui izin. Ini akan menjadi perilaku default, tetapi setiap pelanggan dapat memilih untuk menyesuaikan perilaku di organisasi mereka (dengan mengizinkan, membatasi, atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
      - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
      - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
      - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (cakupan) dalam token akses. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
    - `[PreAuthorizedApplication <IMicrosoftGraphPreAuthorizedApplication[]>]`: Mencantumkan aplikasi klien yang telah diotorisasi sebelumnya dengan izin yang didelegasikan yang ditentukan untuk mengakses API aplikasi ini. Pengguna tidak diharuskan menyetujui aplikasi yang telah diotorisasi sebelumnya (untuk izin yang ditentukan). Namun, setiap izin tambahan yang tidak tercantum dalam preAuthorizedApplications (diminta melalui persetujuan inkremental misalnya) akan memerlukan persetujuan pengguna.
      - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi.
      - `[DelegatedPermissionId <String[]>]`: Pengidentifikasi unik untuk oauth2PermissionScopes yang diperlukan aplikasi.
    - `[RequestedAccessTokenVersion <Int32?>]`: Menentukan versi token akses yang diharapkan oleh sumber daya ini. Ini mengubah versi dan format JWT yang diproduksi secara independen dari titik akhir atau klien yang digunakan untuk meminta token akses.  Titik akhir yang digunakan, v1.0 atau v2.0, dipilih oleh klien dan hanya berdampak pada versi id_tokens. Sumber daya perlu secara eksplisit mengonfigurasi requestedAccessTokenVersion untuk menunjukkan format token akses yang didukung.  Nilai yang mungkin untuk requestedAccessTokenVersion adalah 1, 2, atau null. Jika nilainya null, ini default ke 1, yang sesuai dengan titik akhir v1.0.  Jika signInAudience pada aplikasi dikonfigurasi sebagai AzureADandPersonalMicrosoftAccount, nilai untuk properti ini harus 2
  - `[AppRole <IMicrosoftGraphAppRole[]>]`: Kumpulan peran yang ditetapkan ke aplikasi. Dengan penetapan peran aplikasi, peran ini dapat ditetapkan ke pengguna, grup, atau perwakilan layanan yang terkait dengan aplikasi lain. Tidak dapat diubah ke null.
    - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan ke pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lain (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke perwakilan layanan aplikasi lain juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditentukan pada entitas aplikasi.
    - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan ketika peran aplikasi sedang ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
    - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam penetapan peran aplikasi dan pengalaman persetujuan.
    - `[Id <String>]`: Pengidentifikasi peran unik di dalam koleksi appRoles. Saat membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
    - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus peran, ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, peran ini dapat dihapus.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran dalam token ID dan token akses yang mengautentikasi pengguna atau perwakilan layanan yang ditetapkan. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[ApplicationTemplateId <String>]`: Pengidentifikasi unik applicationTemplate.
  - `[CreatedOnBehalfOfDeletedDateTime <DateTime?>]`: 
  - `[CreatedOnBehalfOfDisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Description <String>]`: Deskripsi opsional aplikasi. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[DisabledByMicrosoftStatus <String>]`: Menentukan apakah Microsoft telah menonaktifkan aplikasi terdaftar. Nilai yang mungkin adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasannya mungkin termasuk aktivitas yang mencurigakan, kasar, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).  Mendukung $filter (eq, ne, NOT).
  - `[GroupMembershipClaim <String>]`: Mengonfigurasi klaim grup yang dikeluarkan dalam token akses pengguna atau OAuth 2.0 yang diharapkan aplikasi. Untuk mengatur atribut ini, gunakan salah satu nilai string berikut: Tidak ada, SecurityGroup (untuk grup keamanan dan peran Azure AD), Semua (ini mendapatkan semua grup keamanan, grup distribusi, dan peran direktori Azure AD tempat pengguna yang masuk menjadi anggotanya).
  - `[HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
      - `[DeletedDateTime <DateTime?>]`: 
      - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[IdentifierUri <String[]>]`: URI yang mengidentifikasi aplikasi dalam penyewa Azure AD, atau dalam domain kustom terverifikasi jika aplikasi adalah multi-penyewa. Untuk informasi selengkapnya, lihat Objek Aplikasi dan Objek Perwakilan Layanan. Operator apa pun diperlukan untuk ekspresi filter pada properti multinilai. Tidak dapat diubah ke null. Mendukung $filter (eq, ne, ge, le, startsWith).
  - `[Info <IMicrosoftGraphInformationalUrl>]`: informationalUrl
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[MarketingUrl <String>]`: Tautan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
    - `[PrivacyStatementUrl <String>]`: Tautan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
    - `[SupportUrl <String>]`: Tautan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
    - `[TermsOfServiceUrl <String>]`: Tautkan ke pernyataan ketentuan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice
  - `[IsDeviceOnlyAuthSupported <Boolean?>]`: Menentukan apakah aplikasi ini mendukung autentikasi perangkat tanpa pengguna. Defaultnya adalah false.
  - `[IsFallbackPublicClient <Boolean?>]`: Menentukan jenis aplikasi fallback sebagai klien publik, seperti aplikasi yang diinstal yang berjalan di perangkat seluler. Nilai default adalah false yang berarti jenis aplikasi fallback adalah klien rahasia seperti aplikasi web. Ada skenario tertentu di mana Azure AD tidak dapat menentukan jenis aplikasi klien. Misalnya, alur ROPC tempat aplikasi dikonfigurasi tanpa menentukan URI pengalihan. Dalam kasus tersebut Azure AD menafsirkan jenis aplikasi berdasarkan nilai properti ini.
  - `[KeyCredentials <IMicrosoftGraphKeyCredential[]>]`: Pengumpulan kredensial kunci yang terkait dengan aplikasi. Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le).
    - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
    - `[DisplayName <String>]`: Nama yang mudah diingat untuk kunci. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu kedaluwarsa kredensial. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus menjadi nilai dasar 64 yang dikodekan.
    - `[KeyId <String>]`: Pengidentifikasi unik (GUID) untuk kunci.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu di mana kredensial menjadi valid. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Type <String>]`: Jenis kredensial kunci; misalnya, 'Simetris'.
    - `[Usage <String>]`: String yang menjelaskan tujuan kunci dapat digunakan; misalnya, 'Verifikasi'.
  - `[Logo <Byte[]>]`: Logo utama untuk aplikasi. Tidak dapat diubah ke null.
  - `[Note <String>]`: Catatan yang relevan untuk manajemen aplikasi.
  - `[Oauth2RequirePostResponse <Boolean?>]`: 
  - `[OptionalClaim <IMicrosoftGraphOptionalClaims>]`: optionalClaims
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[AccessToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token akses JWT.
      - `[AdditionalProperty <String[]>]`: Properti tambahan dari klaim. Jika properti ada dalam kumpulan ini, properti akan menyesuaikan sifat klaim opsional yang ditentukan dalam properti nama.
      - `[Essential <Boolean?>]`: Jika nilainya benar, klaim yang ditentukan oleh klien diperlukan untuk memastikan pengalaman otorisasi yang lancar untuk tugas tertentu yang diminta oleh pengguna akhir. Nilai defaultnya adalah false.
      - `[Name <String>]`: Nama klaim opsional.
      - `[Source <String>]`: Sumber (objek direktori) klaim. Ada klaim yang ditentukan sebelumnya dan klaim yang ditentukan pengguna dari properti ekstensi. Jika nilai sumber null, klaimnya adalah klaim opsional yang ditentukan. Jika nilai sumber adalah pengguna, nilai dalam properti nama adalah properti ekstensi dari objek pengguna.
    - `[IdToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token ID JWT.
    - `[Saml2Token <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token SAML.
  - `[ParentalControlSetting <IMicrosoftGraphParentalControlSettings>]`: parentalControlSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[CountriesBlockedForMinor <String[]>]`: Menentukan kode negara ISO dua huruf. Akses ke aplikasi akan diblokir untuk anak di bawah umur dari negara-negara yang ditentukan dalam daftar ini.
    - `[LegalAgeGroupRule <String>]`: Menentukan aturan grup usia hukum yang berlaku untuk pengguna aplikasi. Dapat diatur ke salah satu nilai berikut: ValueDescriptionAllowDefault. Memberlakukan minimum hukum. Ini berarti persetujuan orang tua diperlukan untuk anak di bawah umur di Uni Eropa dan Korea.RequireConsentForPrivacyServicesEnforces pengguna untuk menentukan tanggal lahir untuk mematuhi aturan COPPA. RequireConsentForMinorsPerlukan persetujuan orang tua untuk usia di bawah 18 tahun, terlepas dari aturan minor negara. RequireConsentForKidsPerlukan persetujuan orang tua untuk usia di bawah 14 tahun, terlepas dari aturan minor negara. BlockMinorsBlocks anak di bawah umur dari menggunakan aplikasi.
  - `[PasswordCredentials <IMicrosoftGraphPasswordCredential[]>]`: Pengumpulan kredensial kata sandi yang terkait dengan aplikasi. Tidak dapat diubah ke null.
    - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
    - `[DisplayName <String>]`: Nama yang mudah diingat untuk kata sandi. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu saat kata sandi kedaluwarsa diwakili menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
    - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu kata sandi menjadi valid. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[PublicClient <IMicrosoftGraphPublicClientApplication>]`: publicClientApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim.
  - `[RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>]`: Menentukan sumber daya yang perlu diakses aplikasi. Properti ini juga menentukan sekumpulan cakupan izin OAuth dan peran aplikasi yang dibutuhkan untuk setiap sumber daya tersebut. Konfigurasi akses ke sumber daya yang diperlukan ini mendorong pengalaman persetujuan. Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le).
    - `[ResourceAccess <IMicrosoftGraphResourceAccess[]>]`: Daftar cakupan izin OAuth2.0 dan peran aplikasi yang diperlukan aplikasi dari sumber daya yang ditentukan.
      - `[Id <String>]`: Pengidentifikasi unik untuk salah satu instans oauth2PermissionScopes atau appRole yang diekspos aplikasi sumber daya.
      - `[Type <String>]`: Menentukan apakah properti id mereferensikan oauth2PermissionScopes atau appRole. Nilai yang mungkin adalah Cakupan atau Peran.
    - `[ResourceAppId <String>]`: Pengidentifikasi unik untuk sumber daya yang memerlukan akses aplikasi.  Ini harus sama dengan appId yang dideklarasikan pada aplikasi sumber daya target.
  - `[SignInAudience <String>]`: Menentukan akun Microsoft yang didukung untuk aplikasi saat ini. Nilai yang didukung adalah: AzureADMyOrg, AzureADMultipleOrgs, AzureADandPersonalMicrosoftAccount, PersonalMicrosoftAccount. Lihat selengkapnya dalam tabel di bawah ini. Mendukung $filter (eq, ne, NOT).
  - `[Spa <IMicrosoftGraphSpaApplication>]`: spaAplikasi
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim.
  - `[Tag <String[]>]`: String kustom yang dapat digunakan untuk mengategorikan dan mengidentifikasi aplikasi. Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[TokenEncryptionKeyId <String>]`: Menentukan keyId kunci publik dari koleksi keyCredentials. Saat dikonfigurasi, Azure AD mengenkripsi semua token yang dikeluarkannya dengan menggunakan kunci yang ditunjukkan properti ini. Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci privat yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.
  - `[TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]`: TokenLifetimePolicies yang ditetapkan ke aplikasi ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Web <IMicrosoftGraphWebApplication>]`: webApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[HomePageUrl <String>]`: Halaman beranda atau halaman arahan aplikasi.
    - `[ImplicitGrantSetting <IMicrosoftGraphImplicitGrantSettings>]`: implicitGrantSettings
      - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
      - `[EnableAccessTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token akses menggunakan alur implisit OAuth 2.0.
      - `[EnableIdTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token ID menggunakan alur implisit OAuth 2.0.
    - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk keluar dari pengguna menggunakan protokol keluar saluran depan, saluran belakang, atau SAML.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim.

OPTIONALCLAIM <IMicrosoftGraphOptionalClaims>: optionalClaims
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AccessToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token akses JWT.
    - `[AdditionalProperty <String[]>]`: Properti tambahan dari klaim. Jika properti ada dalam kumpulan ini, properti akan menyesuaikan sifat klaim opsional yang ditentukan dalam properti nama.
    - `[Essential <Boolean?>]`: Jika nilainya benar, klaim yang ditentukan oleh klien diperlukan untuk memastikan pengalaman otorisasi yang lancar untuk tugas tertentu yang diminta oleh pengguna akhir. Nilai defaultnya adalah false.
    - `[Name <String>]`: Nama klaim opsional.
    - `[Source <String>]`: Sumber (objek direktori) klaim. Ada klaim yang ditentukan sebelumnya dan klaim yang ditentukan pengguna dari properti ekstensi. Jika nilai sumber null, klaimnya adalah klaim opsional yang ditentukan. Jika nilai sumber adalah pengguna, nilai dalam properti nama adalah properti ekstensi dari objek pengguna.
  - `[IdToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token ID JWT.
  - `[Saml2Token <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan dalam token SAML.

PARENTALCONTROLSETTING <IMicrosoftGraphParentalControlSettings>: parentalControlSettings
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[CountriesBlockedForMinor <String[]>]`: Menentukan kode negara ISO dua huruf. Akses ke aplikasi akan diblokir untuk anak di bawah umur dari negara-negara yang ditentukan dalam daftar ini.
  - `[LegalAgeGroupRule <String>]`: Menentukan aturan grup usia hukum yang berlaku untuk pengguna aplikasi. Dapat diatur ke salah satu nilai berikut: ValueDescriptionAllowDefault. Memberlakukan minimum hukum. Ini berarti persetujuan orang tua diperlukan untuk anak di bawah umur di Uni Eropa dan Korea.RequireConsentForPrivacyServicesEnforces pengguna untuk menentukan tanggal lahir untuk mematuhi aturan COPPA. RequireConsentForMinorsPerlukan persetujuan orang tua untuk usia di bawah 18 tahun, terlepas dari aturan minor negara. RequireConsentForKidsPerlukan persetujuan orang tua untuk usia di bawah 14 tahun, terlepas dari aturan minor negara. BlockMinorsBlocks anak di bawah umur dari menggunakan aplikasi.

REQUIREDRESOURCEACCESS <IMicrosoftGraphRequiredResourceAccess[]>: Menentukan sumber daya yang perlu diakses aplikasi. Properti ini juga menentukan sekumpulan cakupan izin OAuth dan peran aplikasi yang dibutuhkan untuk setiap sumber daya tersebut. Konfigurasi akses ke sumber daya yang diperlukan ini mendorong pengalaman persetujuan. Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le).
  - `[ResourceAccess <IMicrosoftGraphResourceAccess[]>]`: Daftar cakupan izin OAuth2.0 dan peran aplikasi yang diperlukan aplikasi dari sumber daya yang ditentukan.
    - `[Id <String>]`: Pengidentifikasi unik untuk salah satu instans oauth2PermissionScopes atau appRole yang diekspos aplikasi sumber daya.
    - `[Type <String>]`: Menentukan apakah properti id mereferensikan oauth2PermissionScopes atau appRole. Nilai yang mungkin adalah Cakupan atau Peran.
  - `[ResourceAppId <String>]`: Pengidentifikasi unik untuk sumber daya yang memerlukan akses aplikasi.  Ini harus sama dengan appId yang dideklarasikan pada aplikasi sumber daya target.

TOKENISSUANCEPOLICY <IMicrosoftGraphTokenIssuancePolicy[]>: .
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

TOKENLIFETIMEPOLICY <IMicrosoftGraphTokenLifetimePolicy[]>: TokenLifetimePolicies yang ditetapkan untuk aplikasi ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

WEB <IMicrosoftGraphWebApplication>: webApplication
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[HomePageUrl <String>]`: Halaman beranda atau halaman arahan aplikasi.
  - `[ImplicitGrantSetting <IMicrosoftGraphImplicitGrantSettings>]`: implicitGrantSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[EnableAccessTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token akses menggunakan alur implisit OAuth 2.0.
    - `[EnableIdTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token ID menggunakan alur implisit OAuth 2.0.
  - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk keluar dari pengguna menggunakan protokol keluar saluran depan, saluran belakang, atau SAML.
  - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim.

## RELATED LINKS

## RELATED LINKS
