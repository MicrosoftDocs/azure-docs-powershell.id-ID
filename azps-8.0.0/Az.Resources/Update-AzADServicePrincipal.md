---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/update-azadserviceprincipal
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzADServicePrincipal.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzADServicePrincipal.md
ms.openlocfilehash: fc63981956f11c574e40596305a8f9526b8a533a
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146597676"
---
# Update-AzADServicePrincipal

## SYNOPSIS
entitas Updates dalam perwakilan layanan

## SYNTAX

### SpObjectIdWithDisplayNameParameterSet (Default)
```
Update-AzADServicePrincipal -ObjectId <String> [-KeyCredential <IMicrosoftGraphKeyCredential[]>]
 [-PasswordCredential <IMicrosoftGraphPasswordCredential[]>] [-IdentifierUri <String[]>] [-Homepage <String>]
 [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-DisplayName <String>] [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>] [-ReplyUrl <String[]>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalType <String>]
 [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SpApplicationIdWithDisplayNameParameterSet
```
Update-AzADServicePrincipal [-KeyCredential <IMicrosoftGraphKeyCredential[]>]
 [-PasswordCredential <IMicrosoftGraphPasswordCredential[]>] [-IdentifierUri <String[]>] [-Homepage <String>]
 [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-DisplayName <String>] [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>] [-ReplyUrl <String[]>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalType <String>]
 [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -ApplicationId <Guid> [-DefaultProfile <PSObject>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectWithDisplayNameParameterSet
```
Update-AzADServicePrincipal [-KeyCredential <IMicrosoftGraphKeyCredential[]>]
 [-PasswordCredential <IMicrosoftGraphPasswordCredential[]>] [-IdentifierUri <String[]>] [-Homepage <String>]
 [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-DisplayName <String>] [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>] [-ReplyUrl <String[]>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalType <String>]
 [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -InputObject <IMicrosoftGraphServicePrincipal>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SPNWithDisplayNameParameterSet
```
Update-AzADServicePrincipal [-KeyCredential <IMicrosoftGraphKeyCredential[]>]
 [-PasswordCredential <IMicrosoftGraphPasswordCredential[]>] [-IdentifierUri <String[]>] [-Homepage <String>]
 [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-DisplayName <String>] [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>] [-ReplyUrl <String[]>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalType <String>]
 [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -ServicePrincipalName <String>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
entitas Updates dalam perwakilan layanan

## EXAMPLES

### Contoh 1: Memperbarui perwakilan layanan dan aplikasi terkait berdasarkan nama tampilan
```powershell
Update-AzADServicePrincipal -DisplayName $name -IdentifierUri $uri
```

Memperbarui perwakilan layanan dan aplikasi terkait dengan nama tampilan, 'IdentifierUri', 'PasswordCredential', 'KeyCredential' akan ditetapkan ke aplikasi

### Contoh 2: Memperbarui perwakilan layanan menurut input alur
```powershell
Get-AzADServicePrincipal -ObjectId $id | Update-AzADServicePrincipal -Note $note
```

Memperbarui perwakilan layanan dan aplikasi terkait dengan nama tampilan, 'IdentifierUri', 'PasswordCredential', 'KeyCredential' akan ditetapkan ke aplikasi

## PARAMETERS

### -AccountEnabled
true jika akun perwakilan layanan diaktifkan; jika tidak, salah.
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

### -AddIn
Mendefinisikan perilaku khusus yang layanan yang memanfaatkan dapat gunakan untuk memanggil aplikasi dalam konteks tertentu.
Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'-nya.
Ini akan memungkinkan layanan seperti Microsoft 365 memanggil aplikasi dalam konteks dokumen yang sedang di kerjakan pengguna.
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

### -AlternativeName
Digunakan untuk mengambil perwakilan layanan berdasarkan langganan, mengidentifikasi grup sumber daya dan id sumber daya lengkap untuk identitas terkelola.
Mendukung $filter (eq, NOT, ge, le, startsWith).

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

### -AppDescription
Deskripsi yang diekspos oleh aplikasi terkait.

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

### -ApplicationId
Pengidentifikasi unik untuk aplikasi terkait (properti appId-nya).

```yaml
Type: System.Guid
Parameter Sets: SpApplicationIdWithDisplayNameParameterSet
Aliases: AppId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppOwnerOrganizationId
Berisi id penyewa tempat aplikasi didaftarkan.
Ini hanya berlaku untuk perwakilan layanan yang didukung oleh aplikasi. Mendukung $filter (eq, ne, NOT, ge, le).

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
Peran yang diekspos oleh aplikasi yang diwakili oleh perwakilan layanan ini.
Untuk informasi selengkapnya, lihat definisi properti appRoles pada entitas aplikasi.
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

### -AppRoleAssignedTo
Penetapan peran aplikasi untuk aplikasi atau layanan ini, diberikan kepada pengguna, grup, dan perwakilan layanan lainnya. Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti APPROLEASSIGNEDTO dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphAppRoleAssignment[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppRoleAssignment
Penetapan peran aplikasi untuk aplikasi atau layanan lain, diberikan kepada perwakilan layanan ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti APPROLEASSIGNMENT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphAppRoleAssignment[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppRoleAssignmentRequired
Menentukan apakah pengguna atau perwakilan layanan lainnya perlu diberikan penetapan peran aplikasi untuk perwakilan layanan ini sebelum pengguna dapat masuk atau aplikasi bisa mendapatkan token.
Nilai defaultnya adalah false.
Tidak dapat diubah ke null.
Mendukung $filter (eq, ne, NOT).

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

### -ClaimsMappingPolicy
ClaimsMappingPolicies yang ditetapkan untuk perwakilan layanan ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti CLAIMSMAPPINGPOLICY dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphClaimsMappingPolicy[]
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

### -DelegatedPermissionClassification
Klasifikasi izin untuk izin yang didelegasikan yang diekspos oleh aplikasi yang diwakili oleh perwakilan layanan ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti DELEGATEDPERMISSIONCLASSIFICATION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDelegatedPermissionClassification[]
Parameter Sets: (All)
Aliases:

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
Bidang teks gratis untuk memberikan deskripsi internal yang dihadapi pengguna akhir tentang perwakilan layanan.
Portal pengguna akhir seperti MyApps akan menampilkan deskripsi aplikasi di bidang ini.
Ukuran maksimum yang diizinkan adalah 1024 karakter.
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
Nama tampilan untuk perwakilan layanan.
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

### -Titik akhir
Titik akhir tersedia untuk penemuan.
Layanan seperti Sharepoint mengisi properti ini dengan titik akhir SharePoint spesifik penyewa yang dapat ditemukan dan digunakan aplikasi lain dalam pengalaman mereka.
Untuk membuat, lihat bagian CATATAN untuk properti TITIK AKHIR dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphEndpoint[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Beranda
Halaman beranda atau halaman arahan aplikasi.

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

### -HomeRealmDiscoveryPolicy
HomeRealmDiscoveryPolicies yang ditetapkan untuk perwakilan layanan ini.
Mendukung $expand.
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
Aliases:

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
objek perwakilan layanan Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal
Parameter Sets: InputObjectWithDisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyCredential
Kumpulan kredensial utama yang terkait dengan aplikasi.
Tidak dapat diubah ke null.
Mendukung $filter (eq, NOT, ge, le).
Untuk membuat, lihat bagian CATATAN untuk properti KEYCREDENTIALS dan buat tabel hash.
Untuk membuat, lihat bagian CATATAN untuk properti KEYCREDENTIAL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoginUrl
Menentukan URL tempat penyedia layanan mengalihkan pengguna ke Azure AD untuk mengautentikasi.
Azure AD menggunakan URL untuk meluncurkan aplikasi dari Microsoft 365 atau Azure AD Aplikasi Saya.
Jika kosong, Azure AD melakukan masuk yang dimulai IdP untuk aplikasi yang dikonfigurasi dengan akses menyeluruh berbasis SAML.
Pengguna meluncurkan aplikasi dari Microsoft 365, Azure AD Aplikasi Saya, atau URL SSO Azure AD.

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

### -LogoutUrl
Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk keluar dari pengguna menggunakan OpenId Koneksi protokol keluar saluran depan, saluran belakang, atau SAML.

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
Bidang teks gratis untuk mengambil informasi tentang perwakilan layanan, biasanya digunakan untuk tujuan operasional.
Ukuran maksimum yang diizinkan adalah 1024 karakter.

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

### -NotificationEmailAddress
Menentukan daftar alamat email tempat Azure AD mengirim pemberitahuan saat sertifikat aktif mendekati tanggal kedaluwarsa.
Ini hanya untuk sertifikat yang digunakan untuk menandatangani token SAML yang dikeluarkan untuk aplikasi Azure AD Gallery.

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

### -Oauth2PermissionScope
Izin yang didelegasikan yang diekspos oleh aplikasi.
Untuk informasi selengkapnya, lihat properti oauth2PermissionScopes pada properti api entitas aplikasi.
Tidak dapat diubah ke null.
Untuk membuat, lihat bagian CATATAN untuk properti OAUTH2PERMISSIONSCOPE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPermissionScope[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
kunci: id servicePrincipal

```yaml
Type: System.String
Parameter Sets: SpObjectIdWithDisplayNameParameterSet
Aliases: ServicePrincipalId, Id, ServicePrincipalObjectId

Required: True
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

### -PasswordCredential
Kumpulan kredensial kata sandi yang terkait dengan aplikasi.
Tidak dapat diubah ke null.
Untuk membuat, lihat bagian CATATAN untuk properti PASSWORDCREDENTIALS dan buat tabel hash.
Untuk membuat, lihat bagian CATATAN untuk properti PASSWORDCREDENTIAL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredSingleSignOnMode
Menentukan mode akses menyeluruh yang dikonfigurasi untuk aplikasi ini.
Azure AD menggunakan mode akses menyeluruh pilihan untuk meluncurkan aplikasi dari Microsoft 365 atau Azure AD Aplikasi Saya.
Nilai yang didukung adalah kata sandi, saml, notSupported, dan oidc.

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

### -PreferredTokenSigningKeyThumbprint
Dicadangkan untuk penggunaan internal saja.
Jangan menulis atau mengandalkan properti ini.
Dapat dihapus dalam versi yang akan datang.

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

### -ReplyUrl
URL yang dikirim token pengguna untuk masuk dengan aplikasi terkait, atau URI pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim untuk aplikasi terkait.
Tidak dapat diubah ke null.

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

### -SamlSingleSignOnSetting
samlSingleSignOnSettings Untuk membangun, lihat bagian CATATAN untuk properti SAMLSINGLESIGNONSETTING dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphSamlSingleSignOnSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipalName
Berisi daftar identifiersUris, yang disalin dari aplikasi terkait.
Nilai tambahan dapat ditambahkan ke aplikasi hibrid.
Nilai-nilai ini dapat digunakan untuk mengidentifikasi izin yang diekspos oleh aplikasi ini dalam Azure AD.
Misalnya, aplikasi Klien dapat menentukan URI sumber daya yang didasarkan pada nilai properti ini untuk memperoleh token akses, yang merupakan URI yang dikembalikan dalam klaim 'aud'. Operator apa pun diperlukan untuk ekspresi filter pada properti multinilai.
Tidak dapat diubah ke null.
Mendukung $filter (eq, NOT, ge, le, startsWith).

```yaml
Type: System.String
Parameter Sets: SPNWithDisplayNameParameterSet
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipalType
Mengidentifikasi apakah perwakilan layanan mewakili aplikasi atau identitas terkelola.
Ini diatur oleh Azure AD secara internal.
Untuk perwakilan layanan yang mewakili aplikasi, ini ditetapkan sebagai Aplikasi.
Untuk perwakilan layanan yang mewakili identitas terkelola, ini ditetapkan sebagai ManagedIdentity.

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

### -Tag
String kustom yang dapat digunakan untuk mengategorikan dan mengidentifikasi perwakilan layanan.
Tidak dapat diubah ke null.
Mendukung $filter (eq, NOT, ge, le, startsWith).

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
Saat dikonfigurasi, Azure AD mengeluarkan token untuk aplikasi ini yang dienkripsi menggunakan kunci yang ditentukan oleh properti ini.
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
TokenIssuancePolicies yang ditetapkan ke perwakilan layanan ini.
Mendukung $expand.
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
TokenLifetimePolicies yang ditetapkan untuk perwakilan layanan ini.
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

### -TransitiveMemberOf
.
Untuk membuat, lihat bagian CATATAN untuk properti TRANSITIVEMEMBEROF dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDirectoryObject[]
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

Set-AzADServicePrincipal

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ADDIN <IMicrosoftGraphAddIn[]>: Menentukan perilaku kustom yang dapat digunakan layanan penggunaan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'-nya. Ini akan memungkinkan layanan seperti Microsoft 365 memanggil aplikasi dalam konteks dokumen yang sedang di kerjakan pengguna.
  - `[Id <String>]`: 
  - `[Property <IMicrosoftGraphKeyValue[]>]`: 
    - `[Key <String>]`: Kunci.
    - `[Value <String>]`: Nilai.
  - `[Type <String>]`: 

APPROLE <IMicrosoftGraphAppRole[]>: Peran yang diekspos oleh aplikasi yang diwakili oleh perwakilan layanan ini. Untuk informasi selengkapnya, lihat definisi properti appRoles pada entitas aplikasi. Tidak dapat diubah ke null.
  - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan ke pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lain (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke perwakilan layanan aplikasi lain juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditentukan pada entitas aplikasi.
  - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
  - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam penetapan peran aplikasi dan pengalaman persetujuan.
  - `[Id <String>]`: Pengidentifikasi peran unik di dalam koleksi appRoles. Saat membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
  - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus peran, ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, peran ini dapat dihapus.
  - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran dalam token ID dan token akses yang mengautentikasi pengguna atau perwakilan layanan yang ditetapkan. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..

APPROLEASSIGNEDTO <IMicrosoftGraphAppRoleAssignment[]>: Penetapan peran aplikasi untuk aplikasi atau layanan ini, diberikan kepada pengguna, grup, dan perwakilan layanan lainnya. Mendukung $expand.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan ke prinsipal. Peran aplikasi ini harus diekspos di properti appRoles pada perwakilan layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default 00000000-0000-0000-0000-000000000000 dapat ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan ke aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan untuk membuat.
  - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup, atau perwakilan layanan yang diberikan peran aplikasi. Diperlukan untuk membuat.
  - `[ResourceDisplayName <String>]`: Nama tampilan perwakilan layanan aplikasi sumber daya tempat penugasan dibuat.
  - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk perwakilan layanan sumber daya tempat penugasan dibuat. Diperlukan untuk membuat. Mendukung $filter (eq saja).

APPROLEASSIGNMENT <IMicrosoftGraphAppRoleAssignment[]>: Penetapan peran aplikasi untuk aplikasi atau layanan lain, diberikan kepada perwakilan layanan ini. Mendukung $expand.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan ke prinsipal. Peran aplikasi ini harus diekspos di properti appRoles pada perwakilan layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default 00000000-0000-0000-0000-000000000000 dapat ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan ke aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan untuk membuat.
  - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup, atau perwakilan layanan yang diberikan peran aplikasi. Diperlukan untuk membuat.
  - `[ResourceDisplayName <String>]`: Nama tampilan perwakilan layanan aplikasi sumber daya tempat penugasan dibuat.
  - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk perwakilan layanan sumber daya tempat penugasan dibuat. Diperlukan untuk membuat. Mendukung $filter (eq saja).

CLAIMSMAPPINGPOLICY <IMicrosoftGraphClaimsMappingPolicy[]>: ClaimsMappingPolicies yang ditetapkan untuk perwakilan layanan ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

DELEGATEDPERMISSIONCLASSIFICATION <IMicrosoftGraphDelegatedPermissionClassification[]>: Klasifikasi izin untuk izin yang didelegasikan yang diekspos oleh aplikasi yang diwakili perwakilan layanan ini. Mendukung $expand.
  - `[Classification <String>]`: permissionClassificationType
  - `[PermissionId <String>]`: Pengidentifikasi unik (id) untuk izin yang didelegasikan yang tercantum dalam koleksi servicePrincipal yang diterbitkan. Diperlukan untuk membuat. Tidak mendukung $filter.
  - `[PermissionName <String>]`: Nilai klaim (nilai) untuk izin yang didelegasikan yang tercantum dalam kumpulan servicePrincipal yang diterbitkan. Tidak mendukung $filter.

ENDPOINT <IMicrosoftGraphEndpoint[]>: Titik akhir tersedia untuk penemuan. Layanan seperti Sharepoint mengisi properti ini dengan penyewa tertentu SharePoint titik akhir yang dapat ditemukan dan digunakan aplikasi lain dalam pengalaman mereka.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

HOMEREALMDISCOVERYPOLICY <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>: HomeRealmDiscoveryPolicies yang ditetapkan untuk perwakilan layanan ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

INFO `<IMicrosoftGraphInformationalUrl>`: informationalUrl
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[MarketingUrl <String>]`: Tautan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
  - `[PrivacyStatementUrl <String>]`: Tautan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
  - `[SupportUrl <String>]`: Tautan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
  - `[TermsOfServiceUrl <String>]`: Tautkan ke pernyataan ketentuan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice

INPUTOBJECT `<IMicrosoftGraphServicePrincipal>`: objek perwakilan layanan
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[AccountEnabled <Boolean?>]`: true jika akun perwakilan layanan diaktifkan; jika tidak, salah. Mendukung $filter (eq, ne, NOT, in).
  - `[AddIn <IMicrosoftGraphAddIn[]>]`: Menentukan perilaku kustom yang dapat digunakan layanan yang menggunakan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat merender aliran file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'- nya. Ini akan memungkinkan layanan seperti Microsoft 365 memanggil aplikasi dalam konteks dokumen yang sedang digarap pengguna.
    - `[Id <String>]`: 
    - `[Property <IMicrosoftGraphKeyValue[]>]`: 
      - `[Key <String>]`: Kunci.
      - `[Value <String>]`: Nilai.
    - `[Type <String>]`: 
  - `[AlternativeName <String[]>]`: Digunakan untuk mengambil perwakilan layanan berdasarkan langganan, mengidentifikasi grup sumber daya dan id sumber daya lengkap untuk identitas terkelola. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[AppDescription <String>]`: Deskripsi yang diekspos oleh aplikasi terkait.
  - `[AppDisplayName <String>]`: Nama tampilan yang diekspos oleh aplikasi terkait.
  - `[AppId <String>]`: Pengidentifikasi unik untuk aplikasi terkait (properti appId-nya).
  - `[AppOwnerOrganizationId <String>]`: Berisi id penyewa tempat aplikasi terdaftar. Ini hanya berlaku untuk perwakilan layanan yang didukung oleh aplikasi. Mendukung $filter (eq, ne, NOT, ge, le).
  - `[AppRole <IMicrosoftGraphAppRole[]>]`: Peran yang diekspos oleh aplikasi yang diwakili oleh perwakilan layanan ini. Untuk informasi selengkapnya, lihat definisi properti appRoles pada entitas aplikasi. Tidak dapat diubah ke null.
    - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan ke pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lain (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke perwakilan layanan aplikasi lain juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditentukan pada entitas aplikasi.
    - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan ketika peran aplikasi sedang ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
    - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam penetapan peran aplikasi dan pengalaman persetujuan.
    - `[Id <String>]`: Pengidentifikasi peran unik di dalam koleksi appRoles. Saat membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
    - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus peran, ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, peran ini dapat dihapus.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran dalam token ID dan token akses yang mengautentikasi pengguna atau perwakilan layanan yang ditetapkan. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]`: Penetapan peran aplikasi untuk aplikasi atau layanan ini, diberikan kepada pengguna, grup, dan perwakilan layanan lainnya. Mendukung $expand.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan ke prinsipal. Peran aplikasi ini harus diekspos di properti appRoles pada perwakilan layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default 00000000-0000-0000-0000-000000000000 dapat ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan ke aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan untuk membuat.
    - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup, atau perwakilan layanan yang diberikan peran aplikasi. Diperlukan untuk membuat.
    - `[ResourceDisplayName <String>]`: Nama tampilan perwakilan layanan aplikasi sumber daya tempat penugasan dibuat.
    - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk perwakilan layanan sumber daya tempat penugasan dibuat. Diperlukan untuk membuat. Mendukung $filter (eq saja).
  - `[AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>]`: Penetapan peran aplikasi untuk aplikasi atau layanan lain, diberikan kepada perwakilan layanan ini. Mendukung $expand.
  - `[AppRoleAssignmentRequired <Boolean?>]`: Menentukan apakah pengguna atau perwakilan layanan lain perlu diberikan penetapan peran aplikasi untuk perwakilan layanan ini sebelum pengguna dapat masuk atau aplikasi bisa mendapatkan token. Nilai defaultnya adalah false. Tidak dapat diubah ke null. Mendukung $filter (eq, ne, NOT).
  - `[ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]`: ClaimsMappingPolicies yang ditetapkan ke perwakilan layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
      - `[DeletedDateTime <DateTime?>]`: 
      - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
    - `[Definition <String[]>]`: Koleksi string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]`: Klasifikasi izin untuk izin yang didelegasikan yang diekspos oleh aplikasi yang diwakili oleh perwakilan layanan ini. Mendukung $expand.
    - `[Classification <String>]`: permissionClassificationType
    - `[PermissionId <String>]`: Pengidentifikasi unik (id) untuk izin yang didelegasikan yang tercantum dalam koleksi servicePrincipal yang diterbitkan. Diperlukan untuk membuat. Tidak mendukung $filter.
    - `[PermissionName <String>]`: Nilai klaim (nilai) untuk izin yang didelegasikan yang tercantum dalam kumpulan servicePrincipal yang diterbitkan. Tidak mendukung $filter.
  - `[Description <String>]`: Bidang teks gratis untuk memberikan deskripsi internal yang dihadapi pengguna akhir dari perwakilan layanan. Portal pengguna akhir seperti MyApps akan menampilkan deskripsi aplikasi di bidang ini. Ukuran maksimum yang diizinkan adalah 1024 karakter. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[DisabledByMicrosoftStatus <String>]`: Menentukan apakah Microsoft telah menonaktifkan aplikasi terdaftar. Nilai yang mungkin adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasannya mungkin termasuk aktivitas yang mencurigakan, melecehkan, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).  Mendukung $filter (eq, ne, NOT).
  - `[Endpoint <IMicrosoftGraphEndpoint[]>]`: Titik akhir tersedia untuk penemuan. Layanan seperti Sharepoint mengisi properti ini dengan titik akhir SharePoint spesifik penyewa yang dapat ditemukan dan digunakan aplikasi lain dalam pengalaman mereka.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]`: HomeRealmDiscoveryPolicies yang ditetapkan untuk perwakilan layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Koleksi string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Homepage <String>]`: Halaman beranda atau halaman arahan aplikasi.
  - `[Info <IMicrosoftGraphInformationalUrl>]`: informationalUrl
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[MarketingUrl <String>]`: Tautkan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
    - `[PrivacyStatementUrl <String>]`: Tautkan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
    - `[SupportUrl <String>]`: Tautkan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
    - `[TermsOfServiceUrl <String>]`: Tautkan ke ketentuan pernyataan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice
  - `[KeyCredentials <IMicrosoftGraphKeyCredential[]>]`: Pengumpulan kredensial utama yang terkait dengan perwakilan layanan. Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le).
    - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
    - `[DisplayName <String>]`: Nama yang mudah diingat untuk kunci. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu kedaluwarsa kredensial. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, tengah malam UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus berupa nilai dasar 64 yang dikodekan.
    - `[KeyId <String>]`: Pengidentifikasi unik (GUID) untuk kunci.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu di mana kredensial menjadi valid. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, tengah malam UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Type <String>]`: Jenis kredensial kunci; misalnya, 'Simetris'.
    - `[Usage <String>]`: String yang menjelaskan tujuan kunci dapat digunakan; misalnya, 'Verifikasi'.
  - `[LoginUrl <String>]`: Menentukan URL tempat penyedia layanan mengalihkan pengguna ke Azure AD untuk mengautentikasi. Azure AD menggunakan URL untuk meluncurkan aplikasi dari Microsoft 365 atau Azure AD Aplikasi Saya. Jika kosong, Azure AD melakukan masuk yang dimulai IdP untuk aplikasi yang dikonfigurasi dengan akses menyeluruh berbasis SAML. Pengguna meluncurkan aplikasi dari Microsoft 365, Azure AD Aplikasi Saya, atau URL SSO Azure AD.
  - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk keluar dari pengguna menggunakan OpenId Koneksi protokol keluar saluran depan, saluran belakang, atau SAML.
  - `[Note <String>]`: Bidang teks gratis untuk mengambil informasi tentang perwakilan layanan, biasanya digunakan untuk tujuan operasional. Ukuran maksimum yang diizinkan adalah 1024 karakter.
  - `[NotificationEmailAddress <String[]>]`: Menentukan daftar alamat email tempat Azure AD mengirim pemberitahuan saat sertifikat aktif mendekati tanggal kedaluwarsa. Ini hanya untuk sertifikat yang digunakan untuk menandatangani token SAML yang dikeluarkan untuk aplikasi Azure AD Gallery.
  - `[Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]`: Izin yang didelegasikan yang diekspos oleh aplikasi. Untuk informasi selengkapnya, lihat properti oauth2PermissionScopes pada properti api entitas aplikasi. Tidak dapat diubah ke null.
    - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin di seluruh penyewa.
    - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
    - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik di dalam kumpulan izin yang didelegasikan yang ditentukan untuk aplikasi sumber daya.
    - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, izin dapat dihapus.
    - `[Origin <String>]`: 
    - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diminta untuk menyetujui izin. Ini akan menjadi perilaku default, tetapi setiap pelanggan dapat memilih untuk menyesuaikan perilaku di organisasi mereka (dengan mengizinkan, membatasi, atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
    - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
    - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (cakupan) dalam token akses. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[PasswordCredentials <IMicrosoftGraphPasswordCredential[]>]`: Pengumpulan kredensial kata sandi yang terkait dengan perwakilan layanan. Tidak dapat diubah ke null.
    - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
    - `[DisplayName <String>]`: Nama yang mudah diingat untuk kata sandi. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu saat kata sandi kedaluwarsa diwakili menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Pilihan.
    - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu kata sandi menjadi valid. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Pilihan.
  - `[PreferredSingleSignOnMode <String>]`: Menentukan mode akses menyeluruh yang dikonfigurasi untuk aplikasi ini. Azure AD menggunakan mode akses menyeluruh pilihan untuk meluncurkan aplikasi dari Microsoft 365 atau Azure AD Aplikasi Saya. Nilai yang didukung adalah kata sandi, saml, notSupported, dan oidc.
  - `[PreferredTokenSigningKeyThumbprint <String>]`: Hanya dicadangkan untuk penggunaan internal. Jangan menulis atau mengandalkan properti ini. Dapat dihapus dalam versi yang akan datang.
  - `[ReplyUrl <String[]>]`: URL yang dikirim token pengguna untuk masuk dengan aplikasi terkait, atau URI pengalihan tempat kode otorisasi OAuth 2.0 dan token akses dikirim untuk aplikasi terkait. Tidak dapat diubah ke null.
  - `[SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>]`: samlSingleSignOnSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RelayState <String>]`: URI relatif yang akan dialihkan penyedia layanan setelah penyelesaian alur akses menyeluruh.
  - `[ServicePrincipalName <String[]>]`: Berisi daftar identifiersUris, yang disalin dari aplikasi terkait. Nilai tambahan dapat ditambahkan ke aplikasi hibrid. Nilai-nilai ini dapat digunakan untuk mengidentifikasi izin yang diekspos oleh aplikasi ini dalam Azure AD. Misalnya, aplikasi Klien dapat menentukan URI sumber daya yang didasarkan pada nilai properti ini untuk memperoleh token akses, yang merupakan URI yang dikembalikan dalam klaim 'aud'. Operator apa pun diperlukan untuk ekspresi filter pada properti multinilai. Tidak dapat diubah ke null.  Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[ServicePrincipalType <String>]`: Mengidentifikasi apakah perwakilan layanan mewakili aplikasi atau identitas terkelola. Ini diatur oleh Azure AD secara internal. Untuk perwakilan layanan yang mewakili aplikasi, ini ditetapkan sebagai Aplikasi. Untuk perwakilan layanan yang mewakili identitas terkelola, ini ditetapkan sebagai ManagedIdentity.
  - `[Tag <String[]>]`: String kustom yang dapat digunakan untuk mengategorikan dan mengidentifikasi perwakilan layanan. Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[TokenEncryptionKeyId <String>]`: Menentukan keyId kunci publik dari koleksi keyCredentials. Saat dikonfigurasi, Azure AD mengeluarkan token untuk aplikasi ini yang dienkripsi menggunakan kunci yang ditentukan oleh properti ini. Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci privat yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.
  - `[TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]`: TokenIssuancePolicies yang ditetapkan ke perwakilan layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Koleksi string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]`: TokenLifetimePolicies yang ditetapkan ke perwakilan layanan ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Koleksi string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>]`: 

KEYCREDENTIAL <IMicrosoftGraphKeyCredential[]>: Kumpulan kredensial kunci yang terkait dengan aplikasi. Tidak dapat diubah ke null. Mendukung $filter (eq, NOT, ge, le). Untuk membuat, lihat bagian CATATAN untuk properti KEYCREDENTIALS dan buat tabel hash.
  - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
  - `[DisplayName <String>]`: Nama yang mudah diingat untuk kunci. Opsional.
  - `[EndDateTime <DateTime?>]`: Tanggal dan waktu kedaluwarsa kredensial. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, tengah malam UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
  - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus menjadi nilai dasar 64 yang dikodekan.
  - `[KeyId <String>]`: Pengidentifikasi unik (GUID) untuk kunci.
  - `[StartDateTime <DateTime?>]`: Tanggal dan waktu di mana kredensial menjadi valid. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
  - `[Type <String>]`: Jenis kredensial kunci; misalnya, 'Simetris'.
  - `[Usage <String>]`: String yang menjelaskan tujuan kunci dapat digunakan; misalnya, 'Verifikasi'.

OAUTH2PERMISSIONSCOPE <IMicrosoftGraphPermissionScope[]>: Izin yang didelegasikan yang diekspos oleh aplikasi. Untuk informasi selengkapnya, lihat properti oauth2PermissionScopes pada properti api entitas aplikasi. Tidak dapat diubah ke null.
  - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin di seluruh penyewa.
  - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
  - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik di dalam kumpulan izin yang didelegasikan yang ditentukan untuk aplikasi sumber daya.
  - `[IsEnabled <Boolean?>]`: Saat membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus terlebih dahulu diatur ke false.  Pada saat itu, dalam panggilan berikutnya, izin dapat dihapus.
  - `[Origin <String>]`: 
  - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diminta untuk menyetujui izin. Ini akan menjadi perilaku default, tetapi setiap pelanggan dapat memilih untuk menyesuaikan perilaku di organisasi mereka (dengan mengizinkan, membatasi, atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
  - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
  - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul dalam pengalaman persetujuan di mana pengguna hanya menyetujui atas nama mereka sendiri.
  - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (cakupan) dalam token akses. Panjang tidak boleh melebihi 120 karakter. Karakter yang diizinkan adalah : ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lainnya, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..

PASSWORDCREDENTIAL <IMicrosoftGraphPasswordCredential[]>: Pengumpulan kredensial kata sandi yang terkait dengan aplikasi. Tidak dapat diubah ke null. Untuk membuat, lihat bagian CATATAN untuk properti PASSWORDCREDENTIALS dan buat tabel hash.
  - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
  - `[DisplayName <String>]`: Nama yang mudah diingat untuk kata sandi. Pilihan.
  - `[EndDateTime <DateTime?>]`: Tanggal dan waktu saat kata sandi kedaluwarsa diwakili menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Pilihan.
  - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
  - `[StartDateTime <DateTime?>]`: Tanggal dan waktu kata sandi menjadi valid. Jenis Tanda waktu mewakili informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, UTC tengah malam pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Pilihan.

SAMLSINGLESIGNONSETTING `<IMicrosoftGraphSamlSingleSignOnSettings>`: samlSingleSignOnSettings
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[RelayState <String>]`: URI relatif yang akan dialihkan penyedia layanan setelah menyelesaikan alur akses menyeluruh.

TOKENISSUANCEPOLICY <IMicrosoftGraphTokenIssuancePolicy[]>: TokenIssuancePolicies yang ditetapkan untuk perwakilan layanan ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

TOKENLIFETIMEPOLICY <IMicrosoftGraphTokenLifetimePolicy[]>: TokenLifetimePolicies yang ditetapkan untuk perwakilan layanan ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap jenis kebijakan turunan. Wajib diisi.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diatur ke true, mengaktifkan kebijakan ini. Mungkin ada banyak kebijakan untuk jenis kebijakan yang sama, tetapi hanya satu yang dapat diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

TRANSITIVEMEMBEROF <IMicrosoftGraphDirectoryObject[]>: .
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama yang ditampilkan dalam direktori

## RELATED LINKS

## RELATED LINKS
