---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azadserviceprincipal
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADServicePrincipal.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADServicePrincipal.md
ms.openlocfilehash: 88771e08fa7642538976c43ac8f0b33f04edf15a
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138282988"
---
# New-AzADServicePrincipal

## SYNOPSIS
Menambahkan entitas baru ke servicePrincipals

## SYNTAX

### SimpleParameterSet (Default)
```
New-AzADServicePrincipal [-DisplayName <String>] [-ApplicationId <Guid>] [-Role <String>] [-Scope <String>]
 [-Homepage <String>] [-ReplyUrl <String[]>] [-StartDate <DateTime>] [-EndDate <DateTime>] [-AccountEnabled]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayNameWithPasswordCredentialParameterSet
```
New-AzADServicePrincipal -DisplayName <String> [-Role <String>] [-Scope <String>] [-Homepage <String>]
 [-ReplyUrl <String[]>] [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>]
 [-AppDescription <String>] [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>]
 -PasswordCredential <IMicrosoftGraphPasswordCredential[]> [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayNameWithKeyCredentialParameterSet
```
New-AzADServicePrincipal -DisplayName <String> [-Role <String>] [-Scope <String>] [-Homepage <String>]
 [-ReplyUrl <String[]>] [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>]
 [-AppDescription <String>] [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -KeyCredential <IMicrosoftGraphKeyCredential[]>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayNameWithKeyPlainParameterSet
```
New-AzADServicePrincipal -DisplayName <String> [-Role <String>] [-Scope <String>] [-Homepage <String>]
 [-ReplyUrl <String[]>] [-StartDate <DateTime>] [-EndDate <DateTime>] [-AccountEnabled]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -CertValue <String> [-DefaultProfile <PSObject>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithPasswordCredentialParameterSet
```
New-AzADServicePrincipal -ApplicationId <Guid> [-Role <String>] [-Scope <String>] [-Homepage <String>]
 [-ReplyUrl <String[]>] [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>]
 [-AppDescription <String>] [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>]
 -PasswordCredential <IMicrosoftGraphPasswordCredential[]> [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationWithKeyCredentialParameterSet
```
New-AzADServicePrincipal -ApplicationId <Guid> [-Role <String>] [-Scope <String>] [-Homepage <String>]
 [-ReplyUrl <String[]>] [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>]
 [-AppDescription <String>] [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -KeyCredential <IMicrosoftGraphKeyCredential[]>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithKeyPlainParameterSet
```
New-AzADServicePrincipal -ApplicationId <Guid> [-Role <String>] [-Scope <String>] [-Homepage <String>]
 [-ReplyUrl <String[]>] [-StartDate <DateTime>] [-EndDate <DateTime>] [-AccountEnabled]
 [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -CertValue <String> [-DefaultProfile <PSObject>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObjectWithPasswordPlainParameterSet
```
New-AzADServicePrincipal [-Role <String>] [-Scope <String>] [-Homepage <String>] [-ReplyUrl <String[]>]
 [-StartDate <DateTime>] [-EndDate <DateTime>] [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>]
 [-AlternativeName <String[]>] [-AppDescription <String>] [-AppOwnerOrganizationId <String>]
 [-AppRole <IMicrosoftGraphAppRole[]>] [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -ApplicationObject <IMicrosoftGraphApplication>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObjectWithKeyPlainParameterSet
```
New-AzADServicePrincipal [-Role <String>] [-Scope <String>] [-Homepage <String>] [-ReplyUrl <String[]>]
 [-StartDate <DateTime>] [-EndDate <DateTime>] [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>]
 [-AlternativeName <String[]>] [-AppDescription <String>] [-AppOwnerOrganizationId <String>]
 [-AppRole <IMicrosoftGraphAppRole[]>] [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -CertValue <String>
 -ApplicationObject <IMicrosoftGraphApplication> [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationObjectWithKeyCredentialParameterSet
```
New-AzADServicePrincipal [-Role <String>] [-Scope <String>] [-Homepage <String>] [-ReplyUrl <String[]>]
 [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>] -KeyCredential <IMicrosoftGraphKeyCredential[]>
 -ApplicationObject <IMicrosoftGraphApplication> [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationObjectWithPasswordCredentialParameterSet
```
New-AzADServicePrincipal [-Role <String>] [-Scope <String>] [-Homepage <String>] [-ReplyUrl <String[]>]
 [-AccountEnabled] [-AddIn <IMicrosoftGraphAddIn[]>] [-AlternativeName <String[]>] [-AppDescription <String>]
 [-AppOwnerOrganizationId <String>] [-AppRole <IMicrosoftGraphAppRole[]>]
 [-AppRoleAssignedTo <IMicrosoftGraphAppRoleAssignment[]>]
 [-AppRoleAssignment <IMicrosoftGraphAppRoleAssignment[]>] [-AppRoleAssignmentRequired]
 [-ClaimsMappingPolicy <IMicrosoftGraphClaimsMappingPolicy[]>]
 [-DelegatedPermissionClassification <IMicrosoftGraphDelegatedPermissionClassification[]>]
 [-DeletedDateTime <DateTime>] [-Description <String>] [-DisabledByMicrosoftStatus <String>]
 [-Endpoint <IMicrosoftGraphEndpoint[]>]
 [-HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]
 [-Info <IMicrosoftGraphInformationalUrl>] [-LoginUrl <String>] [-LogoutUrl <String>] [-Note <String>]
 [-NotificationEmailAddress <String[]>] [-Oauth2PermissionScope <IMicrosoftGraphPermissionScope[]>]
 [-PreferredSingleSignOnMode <String>] [-PreferredTokenSigningKeyThumbprint <String>]
 [-SamlSingleSignOnSetting <IMicrosoftGraphSamlSingleSignOnSettings>] [-ServicePrincipalName <String[]>]
 [-ServicePrincipalType <String>] [-Tag <String[]>] [-TokenEncryptionKeyId <String>]
 [-TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]
 [-TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]
 [-TransitiveMemberOf <IMicrosoftGraphDirectoryObject[]>]
 -PasswordCredential <IMicrosoftGraphPasswordCredential[]> -ApplicationObject <IMicrosoftGraphApplication>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menambahkan entitas baru ke servicePrincipals

## EXAMPLES

### Contoh 1: Buat prinsipal layanan tanpa nama aplikasi atau tampilan
```powershell
PS C:\> New-AzADServicePrincipal
```

Membuat aplikasi dengan nama tampilan "azure-powershell-MM-dd-yyyy-HH-mm-ss" dan asosiasi prinsipal layanan baru dengannya

### Contoh 2: Buat prinsipal layanan dengan aplikasi yang sudah ada
```powershell
PS C:\> New-AzADServicePrincipal -ApplicationId $appid
```

Membuat prinsipal layanan dengan aplikasi yang sudah ada

### Contoh 3: Buat aplikasi dengan nama tampilan dan prinsipal layanan baru terkait dengannya
```powershell
PS C:\> New-AzADServicePrincipal -DisplayName $name
```

Buat aplikasi dengan nama tampilan dan layanan baru yang terkait dengannya

## PARAMETERS

### -AccountEnabled
true jika akun prinsipal layanan diaktifkan; jika tidak, false.
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
Menentukan perilaku kustom yang dapat digunakan oleh layanan untuk memanggil aplikasi dalam konteks tertentu.
Misalnya, aplikasi yang dapat menyajikan streaming file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'.
Ini akan memungkinkan layanan Microsoft 365 panggilan aplikasi dalam konteks dokumen yang sedang digunakan pengguna.
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
Digunakan untuk mengambil prinsipal layanan menurut langganan, mengidentifikasi grup sumber daya dan id sumber daya lengkap untuk identitas yang dikelola.
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
Parameter Sets: SimpleParameterSet
Aliases: AppId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Guid
Parameter Sets: ApplicationWithPasswordCredentialParameterSet, ApplicationWithKeyCredentialParameterSet, ApplicationWithKeyPlainParameterSet
Aliases: AppId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationObject
Objek aplikasi, dapat digunakan sebagai input saluran.
Untuk membuat, lihat bagian CATATAN untuk properti APPLICATIONOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication
Parameter Sets: ApplicationObjectWithPasswordPlainParameterSet, ApplicationObjectWithKeyPlainParameterSet, ApplicationObjectWithKeyCredentialParameterSet, ApplicationObjectWithPasswordCredentialParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AppOwnerOrganizationId
Berisi id penyewa tempat aplikasi didaftarkan.
Hal ini hanya berlaku pada prinsipal layanan yang didukung oleh aplikasi. Mendukung $filter (eq, ne, NOT, ge, le).

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
Peran yang diekspos oleh aplikasi yang diwakili prinsipal layanan ini.
Untuk informasi selengkapnya, lihat definisi properti appRoles di entitas aplikasi.
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

### -AppRoleAssignedTo
Penetapan peran aplikasi untuk aplikasi atau layanan ini, diberikan kepada pengguna, grup, dan prinsipal layanan lainnya. Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti APPROLEASSIGNEDTO dan membuat tabel hash.

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
Penetapan peran aplikasi untuk aplikasi atau layanan lain, yang diberikan kepada prinsipal layanan ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti APPROLEASSIGNMENT dan membuat tabel hash.

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
Menentukan apakah pengguna atau prinsipal layanan lain perlu diberi peran aplikasi untuk prinsipal layanan ini sebelum pengguna bisa masuk atau aplikasi bisa mendapatkan token.
Nilai default adalah false.
Not nullable.
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

### -CertValue
Nilai tipe kredensial 'asimetris'.
Kode ini mewakili sertifikat berkode basis 64.

```yaml
Type: System.String
Parameter Sets: DisplayNameWithKeyPlainParameterSet, ApplicationWithKeyPlainParameterSet, ApplicationObjectWithKeyPlainParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClaimsMappingPolicy
ClaimsMappingPolicies ditetapkan untuk prinsipal layanan ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti CLAIMSMAPPINGPOLICY dan membuat tabel hash.

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
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelegatedPermissionClassification
Klasifikasi izin untuk izin yang didelegasikan yang diekspos oleh aplikasi yang diwakili oleh prinsipal layanan ini.
Mendukung $expand.
Untuk membuat, lihat bagian CATATAN untuk properti DELEGATEDPERMISSIONCLASSIFICATION dan membuat tabel hash.

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
Bidang teks gratis untuk menyediakan deskripsi prinsipal layanan yang dihadapi pengguna akhir internal.
Portal pengguna akhir seperti AplikasiSaya akan menampilkan deskripsi aplikasi dalam bidang ini.
Ukuran maksimal yang diperbolehkan adalah 1024 karakter.
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
Nama tampilan untuk prinsipal layanan.
Mendukung $filter (eq, ne, NOT, ge, le, in, startsWith), $search, dan $orderBy.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: DisplayNameWithPasswordCredentialParameterSet, DisplayNameWithKeyCredentialParameterSet, DisplayNameWithKeyPlainParameterSet
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
Parameter Sets: SimpleParameterSet, DisplayNameWithKeyPlainParameterSet, ApplicationWithKeyPlainParameterSet, ApplicationObjectWithPasswordPlainParameterSet, ApplicationObjectWithKeyPlainParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Titik akhir
Titik akhir yang tersedia untuk penemuan.
Layanan seperti Sharepoint akan mengisi properti ini dengan titik akhir khusus SharePoint penyewa yang dapat ditemukan dan digunakan aplikasi lain dalam pengalaman mereka.
Untuk membuat, lihat bagian CATATAN untuk properti ENDPOINT dan membuat tabel hash.

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

### -Homepage
Laman atau halaman awal aplikasi.

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
HomeRealmDiscoveryPolicies yang ditetapkan pada prinsipal layanan ini.
Mendukung $expand.
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

### -KeyCredential
kredensial kunci yang terkait dengan prinsipal layanan.
Untuk membuat, lihat bagian CATATAN untuk properti KEYCREDENTIAL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential[]
Parameter Sets: DisplayNameWithKeyCredentialParameterSet, ApplicationWithKeyCredentialParameterSet, ApplicationObjectWithKeyCredentialParameterSet
Aliases: KeyCredentials

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoginUrl
Menentukan URL tempat penyedia layanan mengalihkan pengguna ke Azure AD untuk mengautentikasi.
Azure AD menggunakan URL untuk meluncurkan aplikasi dari Microsoft 365 atau Aplikasi Saya Azure AD.
Ketika kosong, Azure AD melakukan masuk yang dimulai IdP untuk aplikasi yang dikonfigurasi dengan akses masuk tunggal berbasis SAML.
Pengguna meluncurkan aplikasi tersebut dari Microsoft 365, URL Azure AD My Apps, atau SSO Azure AD.

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
Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk membuat logout pengguna menggunakan protokol OpenId Koneksi saluran depan, saluran belakang, atau logout SAML.

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
Bidang teks gratis untuk merekam informasi tentang prinsipal layanan, biasanya digunakan untuk tujuan operasional.
Ukuran maksimal yang diperbolehkan adalah 1024 karakter.

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
Menentukan daftar alamat email di mana Azure AD mengirimkan pemberitahuan ketika sertifikat aktif mendekati tanggal kedaluwarsa.
Ini hanya untuk sertifikat yang digunakan untuk menandatangani token SAML yang dikeluarkan untuk aplikasi Galeri Azure AD.

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
Izin yang didelegasikan diekspos oleh aplikasi.
Untuk informasi selengkapnya, lihat properti oauth2PermissionScopes pada properti api entitas aplikasi.
Not nullable.
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

### -PasswordCredential
Kredensial kata sandi yang terkait dengan prinsipal layanan.
Untuk membuat, lihat bagian CATATAN untuk properti PASSWORDCREDENTIAL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential[]
Parameter Sets: DisplayNameWithPasswordCredentialParameterSet, ApplicationWithPasswordCredentialParameterSet, ApplicationObjectWithPasswordCredentialParameterSet
Aliases: PasswordCredentials

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredSingleSignOnMode
Menentukan mode masuk tunggal yang dikonfigurasi untuk aplikasi ini.
Azure AD menggunakan mode masuk tunggal pilihan untuk meluncurkan aplikasi dari Microsoft 365 atau Aplikasi Saya Azure AD.
Nilai yang didukung adalah kata sandi, saml, tidak Didukung, danoidc.

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
Khusus untuk penggunaan internal saja.
Jangan menulis atau mengandalkan properti ini.
Mungkin akan dihapus dalam versi yang akan datang.

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
URL yang dikirimkan token pengguna untuk masuk dengan aplikasi terkait, atau URI pengalihan yang kode otorisasi dan token akses OAuth 2.0 dikirim ke aplikasi terkait.
Not nullable.

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

### -Peran
Peran prinsipal layanan ada di atas lingkupnya.

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

### -SamlSingleSignOnSetting
samlSingleSignOnSettings Untuk membuat, lihat bagian CATATAN untuk properti SAMLSINGLES PIVOTSETTING dan membuat tabel hash.

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

### -Lingkup
Cakupan prinsipal layanan tersebut memiliki izin.

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

### -ServicePrincipalName
Berisi daftar pengidentifikasiUris, disalin dari aplikasi terkait.
Nilai tambahan dapat ditambahkan ke aplikasi hibrid.
Nilai ini dapat digunakan untuk mengidentifikasi izin yang diekspos oleh aplikasi ini dalam Azure AD.
Misalnya, aplikasi Klien dapat menentukan URI sumber daya yang didasarkan pada nilai properti ini untuk memperoleh token akses, yang merupakan URI yang dikembalikan dalam klaim 'aud'. Operator ini diperlukan untuk memfilter ekspresi pada properti multinilai.
Not nullable.
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

### -ServicePrincipalType
Mengidentifikasi jika prinsipal layanan mewakili aplikasi atau identitas terkelola.
Hal ini diatur oleh Azure AD secara internal.
Untuk prinsipal layanan yang mewakili aplikasi, ini diatur sebagai Aplikasi.
Untuk prinsipal layanan yang mewakili identitas terkelola ini diatur sebagai Identitas Terkelola.

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

### -StartDate
Tanggal mulai efektif penggunaan kredensial.
Nilai tanggal mulai default adalah hari ini.
Untuk kredensial tipe 'asimetris', kredensial ini harus diatur ke aktif atau setelah tanggal sertifikat X509 valid.

```yaml
Type: System.DateTime
Parameter Sets: SimpleParameterSet, DisplayNameWithKeyPlainParameterSet, ApplicationWithKeyPlainParameterSet, ApplicationObjectWithPasswordPlainParameterSet, ApplicationObjectWithKeyPlainParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
String kustom yang bisa digunakan untuk mengkategorikan dan mengidentifikasi prinsipal layanan.
Not nullable.
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
Menentukan keyId dari kunci publik dari koleksi keyCredentials.
Saat dikonfigurasi, Azure AD memberikan token untuk aplikasi ini yang dienkripsi menggunakan kunci yang ditentukan oleh properti ini.
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
TokenIssuancePolicies ditetapkan untuk prinsipal layanan ini.
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
TokenLifetimePolicies yang ditetapkan untuk prinsipal layanan ini.
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

### -TransitiveMemberOf
.
Untuk membuat, lihat bagian CATATAN untuk properti TRANSITIVEMEMBEROF dan membuat tabel hash.

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ADDIN <IMicrosoftGraphAddIn[]>: Menentukan perilaku kustom yang dapat digunakan oleh layanan yang digunakan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat menyajikan streaming file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'. Ini akan memungkinkan layanan Microsoft 365 panggilan aplikasi dalam konteks dokumen yang sedang digunakan pengguna.
  - `[Id <String>]`: 
  - `[Property <IMicrosoftGraphKeyValue[]>]`: 
    - `[Key <String>]`: Kunci.
    - `[Value <String>]`: Nilai.
  - `[Type <String>]`: 

APPLICATIONOBJECT <IMicrosoftGraphApplication>: Objek aplikasi, bisa digunakan sebagai input saluran.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[AddIn <IMicrosoftGraphAddIn[]>]`: Menentukan perilaku kustom yang dapat digunakan oleh layanan untuk memanggil aplikasi dalam konteks tertentu. Misalnya, aplikasi yang dapat menyajikan streaming file dapat mengatur properti addIns untuk fungsionalitas 'FileHandler'. Ini akan memungkinkan layanan Office 365 panggilan aplikasi dalam konteks dokumen yang sedang digunakan pengguna.
    - `[Id <String>]`: 
    - `[Property <IMicrosoftGraphKeyValue[]>]`: 
      - `[Key <String>]`: Kunci.
      - `[Value <String>]`: Nilai.
    - `[Type <String>]`: 
  - `[Api <IMicrosoftGraphApiApplication>]`: apiApplication
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
  - `[AppRole <IMicrosoftGraphAppRole[]>]`: Kumpulan peran yang ditetapkan pada aplikasi. Dengan penetapan peran aplikasi, peran ini dapat ditetapkan kepada pengguna, grup, atau prinsipal layanan yang terkait dengan aplikasi lainnya. Not nullable.
    - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan kepada pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lainnya (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke prinsipal layanan aplikasi lainnya juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditetapkan pada entitas aplikasi.
    - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
    - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam pengalaman penetapan peran dan persetujuan aplikasi.
    - `[Id <String>]`: Pengidentifikasi peran unik di dalam kumpulan peran aplikasi. Ketika membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
    - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus sebuah peran, ini harus terlebih dahulu disetel ke false.  Pada tahap ini, dalam panggilan berikutnya, peran ini mungkin dihapus.
    - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran di token ID dan token akses yang mengotentikan pengguna atau prinsipal layanan yang ditetapkan. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..
  - `[ApplicationTemplateId <String>]`: Pengidentifikasi unik aplikasiTemplate.
  - `[CreatedOnBehalfOfDeletedDateTime <DateTime?>]`: 
  - `[CreatedOnBehalfOfDisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Description <String>]`: Deskripsi opsional dari aplikasi. Dikembalikan secara default. Mendukung $filter (eq, ne, NOT, ge, le, startsWith) dan $search.
  - `[DisabledByMicrosoftStatus <String>]`: Menentukan apakah Microsoft telah menonaktifkan aplikasi yang terdaftar. Nilai yang mungkin adalah: null (nilai default), NotDisabled, dan DisabledDueToViolationOfServicesAgreement (alasan dapat mencantumkan aktivitas yang mencurigakan, melecehkan, atau berbahaya, atau pelanggaran Perjanjian Layanan Microsoft).  Mendukung $filter (eq, ne, NOT).
  - `[GroupMembershipClaim <String>]`: Mengonfigurasi klaim grup yang diterbitkan di pengguna atau token akses OAuth 2.0 yang diharapkan oleh aplikasi. Untuk mengatur atribut ini, gunakan salah satu dari nilai string berikut ini: Tidak Ada, Grup Keamanan (untuk grup keamanan dan peran Azure AD), Semua (ini mendapatkan semua grup keamanan, grup distribusi, dan peran direktori Azure AD di mana pengguna yang masuk adalah anggotanya).
  - `[HomeRealmDiscoveryPolicy <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
      - `[DeletedDateTime <DateTime?>]`: 
      - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[IdentifierUri <String[]>]`: URI yang mengidentifikasi aplikasi di dalam penyewa Azure AD-nya, atau di dalam domain kustom terverifikasi jika aplikasi tersebut multi-penyewa. Untuk informasi selengkapnya, lihat Objek Aplikasi dan Objek Prinsipal Layanan. Operator ini diperlukan untuk memfilter ekspresi pada properti multinilai. Not nullable. Mendukung $filter (eq, ne, ge, le, startsWith).
  - `[Info <IMicrosoftGraphInformationalUrl>]`: informationalUrl
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[MarketingUrl <String>]`: Menautkan ke halaman pemasaran aplikasi. Misalnya, https://www.contoso.com/app/marketing
    - `[PrivacyStatementUrl <String>]`: Menautkan ke pernyataan privasi aplikasi. Misalnya, https://www.contoso.com/app/privacy
    - `[SupportUrl <String>]`: Menautkan ke halaman dukungan aplikasi. Misalnya, https://www.contoso.com/app/support
    - `[TermsOfServiceUrl <String>]`: Menautkan ke ketentuan pernyataan layanan aplikasi. Misalnya, https://www.contoso.com/app/termsofservice
  - `[IsDeviceOnlyAuthSupported <Boolean?>]`: Menentukan apakah aplikasi ini mendukung autentikasi perangkat tanpa pengguna. Defaultnya adalah false.
  - `[IsFallbackPublicClient <Boolean?>]`: Menentukan tipe aplikasi fallback sebagai klien publik, seperti aplikasi terinstal yang berjalan pada perangkat seluler. Nilai default adalah false, yang berarti tipe aplikasi merupakan klien rahasia seperti aplikasi web. Terdapat skenario tertentu ketika Azure AD tidak dapat menentukan tipe aplikasi klien. Misalnya, aliran ROPC tempat aplikasi dikonfigurasi tanpa menentukan URI pengalihan. Dalam kasus tersebut, Azure AD menginterpretasikan tipe aplikasi berdasarkan nilai properti ini.
  - `[KeyCredentials <IMicrosoftGraphKeyCredential[]>]`: Kumpulan kredensial kunci yang terkait dengan aplikasi. Not nullable. Mendukung $filter (eq, NOT, ge, le).
    - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
    - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kunci tersebut. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kredensial kedaluwarsa. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus merupakan nilai berkodekan 64 basis.
    - `[KeyId <String>]`: Pengidentifikasi unik (GUID) kunci tersebut.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu saat kredensial menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
    - `[Type <String>]`: Tipe kredensial kunci; misalnya, 'Simetri'.
    - `[Usage <String>]`: String yang menjelaskan tujuan untuk menggunakan kunci; misalnya, 'Verifikasi'.
  - `[Logo <Byte[]>]`: Logo utama aplikasi. Not nullable.
  - `[Note <String>]`: Catatan yang relevan untuk manajemen aplikasi.
  - `[Oauth2RequirePostResponse <Boolean?>]`: 
  - `[OptionalClaim <IMicrosoftGraphOptionalClaims>]`: optionalClaims
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[AccessToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan di token akses JWT.
      - `[AdditionalProperty <String[]>]`: Properti tambahan klaim. Jika ada properti dalam kumpulan ini, properti ini mengubah perilaku klaim opsional yang ditentukan dalam properti nama.
      - `[Essential <Boolean?>]`: Jika nilai tersebut benar, klaim yang ditentukan oleh klien diperlukan untuk memastikan pengalaman otorisasi yang lancar untuk tugas tertentu yang diminta oleh pengguna akhir. Nilai default adalah false.
      - `[Name <String>]`: Nama klaim opsional.
      - `[Source <String>]`: Sumber (objek direktori) klaim. Ada klaim yang sudah ditentukan sebelumnya dan klaim yang ditentukan pengguna dari properti ekstensi. Jika nilai sumber null, klaim adalah klaim opsional yang sudah ditentukan sebelumnya. Jika nilai sumber adalah pengguna, nilai dalam properti nama adalah properti ekstensi dari objek pengguna.
    - `[IdToken <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional yang dikembalikan di token JWT ID.
    - `[Saml2Token <IMicrosoftGraphOptionalClaim[]>]`: Klaim opsional dikembalikan dalam token SAML.
  - `[ParentalControlSetting <IMicrosoftGraphParentalControlSettings>]`: parentalControlSettings
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[CountriesBlockedForMinor <String[]>]`: Menentukan kode negara ISO dua huruf. Akses ke aplikasi akan diblokir untuk pengguna di bawah umur dari negara yang ditentukan dalam daftar ini.
    - `[LegalAgeGroupRule <String>]`: Menentukan aturan grup usia legal yang berlaku bagi pengguna aplikasi. Dapat diatur ke salah satu nilai berikut: ValueDescriptionAllowDefault. Menerapkan minimum hukum. Ini berarti persetujuan orang tua diperlukan untuk anak di bawah umur di Uni Eropa dan Korea.RequireConsentForPrivacyServicesEnforces pengguna untuk menentukan tanggal lahir untuk mematuhi aturan COPPA. RequireConsentForMinorsRequires parental consent for ages below 18, regardless of country minor rules. RequireConsentForKidsRequires parental consent for ages below 14, regardless of country minor rules. BlockMinorsBlocks minors tidak menggunakan aplikasi.
  - `[PasswordCredentials <IMicrosoftGraphPasswordCredential[]>]`: Kumpulan kredensial kata sandi yang terkait dengan aplikasi. Not nullable.
    - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
    - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kata sandi. Opsional.
    - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kata sandi kedaluwarsa yang dinyatakan menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
    - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
    - `[StartDateTime <DateTime?>]`: Tanggal dan waktu valid ketika kata sandi menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[PublicClient <IMicrosoftGraphPublicClientApplication>]`: publicClientApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi dan token akses OAuth 2.0 dikirim.
  - `[RequiredResourceAccess <IMicrosoftGraphRequiredResourceAccess[]>]`: Menentukan sumber daya yang perlu diakses oleh aplikasi. Properti ini juga menentukan kumpulan lingkup izin OAuth dan peran aplikasi yang diperlukannya untuk setiap sumber daya tersebut. Konfigurasi akses ke sumber daya yang diperlukan ini akan mendorong pengalaman persetujuan. Not nullable. Mendukung $filter (eq, NOT, ge, le).
    - `[ResourceAccess <IMicrosoftGraphResourceAccess[]>]`: Daftar lingkup izin OAuth2.0 dan peran aplikasi yang diperlukan aplikasi dari sumber daya yang ditentukan.
      - `[Id <String>]`: Pengidentifikasi unik untuk salah satu instans oauth2PermissionScopes atau appRole yang digunakan oleh aplikasi sumber daya.
      - `[Type <String>]`: Menentukan apakah properti id merujuk pada oauth2PermissionScopes atau appRole. Nilai yang mungkin adalah Lingkup atau Peran.
    - `[ResourceAppId <String>]`: Pengidentifikasi unik untuk sumber daya yang memerlukan akses aplikasi.  Ini harus sama dengan appId yang dideklarasikan pada aplikasi sumber daya target.
  - `[SignInAudience <String>]`: Menentukan akun Microsoft yang didukung untuk aplikasi saat ini. Nilai yang didukung adalah: AzureADMyOrg, AzureADMultipleOrgs, AzureADandPersonalMicrosoftAccount, PersonalMicrosoftAccount. Lihat selengkapnya dalam tabel di bawah ini. Mendukung $filter (eq, ne, NOT).
  - `[Spa <IMicrosoftGraphSpaApplication>]`: spaApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi dan token akses OAuth 2.0 dikirim.
  - `[Tag <String[]>]`: String kustom yang bisa digunakan untuk mengkategorikan dan mengidentifikasi aplikasi. Not nullable. Mendukung $filter (eq, NOT, ge, le, startsWith).
  - `[TokenEncryptionKeyId <String>]`: Menentukan keyId dari kunci publik dari koleksi keyCredentials. Ketika dikonfigurasi, Azure AD mengenkripsi semua token yang disimpan dengan menggunakan kunci yang ditugasi properti ini. Kode aplikasi yang menerima token terenkripsi harus menggunakan kunci pribadi yang cocok untuk mendekripsi token sebelum dapat digunakan untuk pengguna yang masuk.
  - `[TokenIssuancePolicy <IMicrosoftGraphTokenIssuancePolicy[]>]`: 
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[TokenLifetimePolicy <IMicrosoftGraphTokenLifetimePolicy[]>]`: TokenLifetimePolicies ditetapkan untuk aplikasi ini. Mendukung $expand.
    - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
    - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
    - `[Description <String>]`: Deskripsi untuk kebijakan ini.
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Web <IMicrosoftGraphWebApplication>]`: webApplication
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
    - `[HomePageUrl <String>]`: Laman atau halaman awal aplikasi.
    - `[ImplicitGrantSetting <IMicrosoftGraphImplicitGrantSettings>]`: implisitGrantSettings
      - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
      - `[EnableAccessTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token akses menggunakan aliran implisit OAuth 2.0.
      - `[EnableIdTokenIssuance <Boolean?>]`: Menentukan apakah aplikasi web ini dapat meminta token ID menggunakan aliran implisit OAuth 2.0.
    - `[LogoutUrl <String>]`: Menentukan URL yang akan digunakan oleh layanan otorisasi Microsoft untuk membuat logo pengguna menggunakan protokol logout saluran depan, saluran belakang, atau SAML.
    - `[RedirectUri <String[]>]`: Menentukan URL tempat token pengguna dikirim untuk masuk, atau URI pengalihan tempat kode otorisasi dan token akses OAuth 2.0 dikirim.

APPROLE <IMicrosoftGraphAppRole[]>: Peran yang diekspos oleh aplikasi yang diwakili prinsipal layanan ini. Untuk informasi selengkapnya, lihat definisi properti appRoles di entitas aplikasi. Not nullable.
  - `[AllowedMemberType <String[]>]`: Menentukan apakah peran aplikasi ini dapat ditetapkan kepada pengguna dan grup (dengan mengatur ke ['Pengguna']), ke aplikasi lainnya (dengan mengatur ke ['Aplikasi'], atau keduanya (dengan mengatur ke ['Pengguna', 'Aplikasi']). Peran aplikasi yang mendukung penugasan ke prinsipal layanan aplikasi lainnya juga dikenal sebagai izin aplikasi. Nilai 'Aplikasi' hanya didukung untuk peran aplikasi yang ditetapkan pada entitas aplikasi.
  - `[Description <String>]`: Deskripsi untuk peran aplikasi. Ini ditampilkan saat peran aplikasi ditetapkan dan, jika peran aplikasi berfungsi sebagai izin aplikasi, selama pengalaman persetujuan.
  - `[DisplayName <String>]`: Nama tampilan untuk izin yang muncul dalam pengalaman penetapan peran dan persetujuan aplikasi.
  - `[Id <String>]`: Pengidentifikasi peran unik di dalam kumpulan peran aplikasi. Ketika membuat peran aplikasi baru, pengidentifikasi Guid baru harus disediakan.
  - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui peran aplikasi, ini harus diatur ke true (yang merupakan default). Untuk menghapus sebuah peran, ini harus terlebih dahulu disetel ke false.  Pada tahap ini, dalam panggilan berikutnya, peran ini mungkin dihapus.
  - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim peran di token ID dan token akses yang mengotentikan pengguna atau prinsipal layanan yang ditetapkan. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..

APPROLEASSIGNEDTO <IMicrosoftGraphAppRoleAssignment[]>: Penetapan peran aplikasi untuk aplikasi atau layanan ini, diberikan kepada pengguna, grup, dan prinsipal layanan lainnya. Mendukung $expand.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan sebagai pokok aplikasi. Peran aplikasi ini harus diekspos dalam properti appRoles pada prinsipal layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default dari 00000000-0000-0000-000000000000 bisa ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan untuk aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan pada saat membuat.
  - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup atau prinsipal layanan yang diberikan peran aplikasi. Diperlukan pada saat membuat.
  - `[ResourceDisplayName <String>]`: Nama tampilan prinsipal layanan aplikasi sumber daya tempat penetapan dilakukan.
  - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk prinsipal layanan sumber daya tempat penetapan dilakukan. Diperlukan pada saat membuat. Mendukung $filter (eq saja).

APPROLEASSIGNMENT <IMicrosoftGraphAppRoleAssignment[]>: Penetapan peran aplikasi untuk aplikasi atau layanan lain, diberikan kepada prinsipal layanan ini. Mendukung $expand.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[AppRoleId <String>]`: Pengidentifikasi (id) untuk peran aplikasi yang ditetapkan sebagai pokok aplikasi. Peran aplikasi ini harus diekspos dalam properti appRoles pada prinsipal layanan aplikasi sumber daya (resourceId). Jika aplikasi sumber daya belum mendeklarasikan peran aplikasi apa pun, ID peran aplikasi default dari 00000000-0000-0000-000000000000 bisa ditentukan untuk memberi sinyal bahwa prinsipal ditetapkan untuk aplikasi sumber daya tanpa peran aplikasi tertentu. Diperlukan pada saat membuat.
  - `[PrincipalId <String>]`: Pengidentifikasi unik (id) untuk pengguna, grup atau prinsipal layanan yang diberikan peran aplikasi. Diperlukan pada saat membuat.
  - `[ResourceDisplayName <String>]`: Nama tampilan prinsipal layanan aplikasi sumber daya tempat penetapan dilakukan.
  - `[ResourceId <String>]`: Pengidentifikasi unik (id) untuk prinsipal layanan sumber daya tempat penetapan dilakukan. Diperlukan pada saat membuat. Mendukung $filter (eq saja).

CLAIMSMAPPINGPOLICY <IMicrosoftGraphClaimsMappingPolicy[]>: The claimsMappingPolicies assigned to this service principal. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

DELEGATEDPERMISSIONCLASSIFICATION <IMicrosoftGraphDelegatedPermissionClassification[]>: Klasifikasi izin untuk izin yang didelegasikan yang diekspos oleh aplikasi yang diwakili oleh prinsipal layanan ini. Mendukung $expand.
  - `[Classification <String>]`: permissionClassificationType
  - `[PermissionId <String>]`: Pengidentifikasi unik (id) untuk izin yang didelegasikan tercantum dalam kumpulan servicePrincipal yang diterbitkanPermissionScopes. Diperlukan pada saat membuat. Tidak mendukung $filter.
  - `[PermissionName <String>]`: Nilai klaim (nilai) untuk izin yang didelegasikan tercantum dalam kumpulan servicePrincipal yang diterbitkanPermissionScopes. Tidak mendukung $filter.

ENDPOINT <IMicrosoftGraphEndpoint[]>: Titik akhir yang tersedia untuk penemuan. Layanan seperti Sharepoint akan mengisi properti ini dengan titik akhir khusus SharePoint penyewa yang dapat ditemukan dan digunakan aplikasi lain dalam pengalaman mereka.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

HOMEREALMDISCOVERYPOLICY <IMicrosoftGraphHomeRealmDiscoveryPolicy[]>: The homeRealmDiscoveryPolicies ditetapkan untuk prinsipal layanan ini. Mendukung $expand.
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

KEYCREDENTIAL <IMicrosoftGraphKeyCredential[]>: kredensial kunci yang terkait dengan prinsipal layanan.
  - `[CustomKeyIdentifier <Byte[]>]`: Pengidentifikasi kunci kustom
  - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kunci tersebut. Opsional.
  - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kredensial kedaluwarsa. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
  - `[Key <Byte[]>]`: Nilai untuk kredensial kunci. Harus merupakan nilai berkodekan 64 basis.
  - `[KeyId <String>]`: Pengidentifikasi unik (GUID) kunci tersebut.
  - `[StartDateTime <DateTime?>]`: Tanggal dan waktu saat kredensial menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z
  - `[Type <String>]`: Tipe kredensial kunci; misalnya, 'Simetri'.
  - `[Usage <String>]`: String yang menjelaskan tujuan untuk menggunakan kunci; misalnya, 'Verifikasi'.

OAUTH2PERMISSIONSCOPE <IMicrosoftGraphPermissionScope[]>: Izin yang didelegasikan diekspos oleh aplikasi. Untuk informasi selengkapnya, lihat properti oauth2PermissionScopes pada properti api entitas aplikasi. Not nullable.
  - `[AdminConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna. Teks ini muncul dalam pengalaman persetujuan admin tingkat penyewa.
  - `[AdminConsentDisplayName <String>]`: Judul izin, dimaksudkan untuk dibaca oleh administrator yang memberikan izin atas nama semua pengguna.
  - `[Id <String>]`: Pengidentifikasi izin yang didelegasikan unik dalam kumpulan izin yang didelegasikan yang ditetapkan untuk aplikasi sumber daya.
  - `[IsEnabled <Boolean?>]`: Ketika membuat atau memperbarui izin, properti ini harus diatur ke true (yang merupakan default). Untuk menghapus izin, properti ini harus diatur ke salah terlebih dahulu.  Pada tahap ini, dalam panggilan berikutnya, izin mungkin dihapus.
  - `[Origin <String>]`: 
  - `[Type <String>]`: Menentukan apakah izin yang didelegasikan ini harus dianggap aman bagi pengguna non-admin untuk menyetujui atas nama mereka sendiri, atau apakah administrator harus diperlukan untuk menyetujui izin. Ini akan menjadi perilaku default, tapi setiap pelanggan bisa memilih untuk mengkustomisasi perilaku di organisasi mereka (dengan mengizinkan, membatasi atau membatasi persetujuan pengguna untuk izin yang didelegasikan ini.)
  - `[UserConsentDescription <String>]`: Deskripsi izin yang didelegasikan, dimaksudkan untuk dibaca oleh pengguna yang memberi izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
  - `[UserConsentDisplayName <String>]`: Judul untuk izin, dimaksudkan untuk dibaca oleh pengguna yang memberikan izin atas nama mereka sendiri. Teks ini muncul di pengalaman persetujuan di mana pengguna menyetujui hanya atas nama mereka sendiri.
  - `[Value <String>]`: Menentukan nilai yang akan disertakan dalam klaim scp (lingkup) di token akses. Panjangnya tidak boleh melebihi 120 karakter. Karakter yang diperbolehkan adalah: ! # $ % & ' ( ) * + , - . / : ;  =  ? @ [ ] ^ + _ { } ~, serta karakter dalam rentang 0-9, A-Z dan a-z. Karakter lain, termasuk karakter spasi, tidak diperbolehkan. Mungkin tidak dimulai dengan ..

PASSWORDCREDENTIAL <IMicrosoftGraphPasswordCredential[]>: Kredensial kata sandi yang terkait dengan prinsipal layanan.
  - `[CustomKeyIdentifier <Byte[]>]`: Jangan gunakan.
  - `[DisplayName <String>]`: Nama yang mudah digunakan untuk kata sandi. Opsional.
  - `[EndDateTime <DateTime?>]`: Tanggal dan waktu ketika kata sandi kedaluwarsa yang dinyatakan menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.
  - `[KeyId <String>]`: Pengidentifikasi unik untuk kata sandi.
  - `[StartDateTime <DateTime?>]`: Tanggal dan waktu valid ketika kata sandi menjadi valid. Tipe Timestamp menunjukkan informasi tanggal dan waktu menggunakan format ISO 8601 dan selalu dalam waktu UTC. Misalnya, midnight UTC pada 1 Jan 2014 adalah 2014-01-01T00:00:00Z. Opsional.

SAMLSINGLESKORELASISETTING <IMicrosoftGraphSamlSingleSignOnSettings>: samlSingleSignOnSettings
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[RelayState <String>]`: URI relatif dari penyedia layanan akan dialihkan setelah penyelesaian aliran masuk tunggal.

TOKENISSUANCEPOLICY <IMicrosoftGraphTokenIssuancePolicy[]>: TokenIssuancePolicies yang ditetapkan untuk prinsipal layanan ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

TOKENLIFETIMEPOLICY <IMicrosoftGraphTokenLifetimePolicy[]>: TokenLifetimePolicies yang ditetapkan untuk prinsipal layanan ini. Mendukung $expand.
  - `[AppliesTo <IMicrosoftGraphDirectoryObject[]>]`: 
    - `[DeletedDateTime <DateTime?>]`: 
    - `[DisplayName <String>]`: Nama ditampilkan dalam direktori
  - `[Definition <String[]>]`: Kumpulan string yang berisi string JSON yang menentukan aturan dan pengaturan untuk kebijakan. Sintaks untuk definisi berbeda untuk setiap tipe kebijakan turunan. Diperlukan.
  - `[IsOrganizationDefault <Boolean?>]`: Jika diset ke true, aktifkan kebijakan ini. Bisa terdapat banyak kebijakan untuk tipe kebijakan yang sama, tapi hanya satu yang bisa diaktifkan sebagai default organisasi. Opsional, nilai default adalah false.
  - `[Description <String>]`: Deskripsi untuk kebijakan ini.
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

TRANSITIVEMEMBEROF <IMicrosoftGraphDirectoryObject[]>: .
  - `[DeletedDateTime <DateTime?>]`: 
  - `[DisplayName <String>]`: Nama ditampilkan dalam direktori

## RELATED LINKS

## RELATED LINKS
