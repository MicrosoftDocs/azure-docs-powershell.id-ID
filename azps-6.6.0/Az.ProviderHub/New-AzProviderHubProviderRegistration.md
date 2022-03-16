---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/new-azproviderhubproviderregistration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubProviderRegistration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubProviderRegistration.md
ms.openlocfilehash: 94f63b73645597a8a04999bfae22f53924cad69b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139970691"
---
# New-AzProviderHubProviderRegistration

## SYNOPSIS
Membuat atau memperbarui pendaftaran penyedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.providerhub/new-azproviderhubproviderregistration) untuk informasi terkini.

## SYNTAX

```
New-AzProviderHubProviderRegistration -ProviderNamespace <String> [-SubscriptionId <String>]
 [-Capability <IResourceProviderCapabilities[]>] [-FeatureRuleRequiredFeaturesPolicy <String>]
 [-ManagementIncidentContactEmail <String>] [-ManagementIncidentRoutingService <String>]
 [-ManagementIncidentRoutingTeam <String>] [-ManagementManifestOwner <String[]>]
 [-ManagementResourceAccessPolicy <String>] [-ManagementResourceAccessRole <IAny[]>]
 [-ManagementSchemaOwner <String[]>] [-ManagementServiceTreeInfo <IServiceTreeInfo[]>] [-Metadata <IAny>]
 [-Namespace <String>] [-ProviderAuthenticationAllowedAudience <String[]>]
 [-ProviderAuthorization <IResourceProviderAuthorization[]>]
 [-ProviderHubMetadataProviderAuthenticationAllowedAudience <String[]>]
 [-ProviderHubMetadataProviderAuthorization <IResourceProviderAuthorization[]>]
 [-ProviderType <ResourceProviderType>] [-ProviderVersion <String>] [-ProvisioningState <ProvisioningState>]
 [-RequestHeaderOptionOptInHeader <OptInHeaderType>] [-RequiredFeature <String[]>]
 [-SubscriptionLifecycleNotificationSpecificationSoftDeleteTtl <TimeSpan>]
 [-SubscriptionLifecycleNotificationSpecificationSubscriptionStateOverrideAction <ISubscriptionStateOverrideAction[]>]
 [-TemplateDeploymentOptionPreflightOption <PreflightOption[]>] [-TemplateDeploymentOptionPreflightSupported]
 [-ThirdPartyProviderAuthorizationAuthorization <ILightHouseAuthorization[]>]
 [-ThirdPartyProviderAuthorizationManagedByTenantId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui pendaftaran penyedia.

## EXAMPLES

### Contoh 1: Buat/Perbarui pendaftaran penyedia.
```powershell
PS C:\> New-AzProviderHubProviderRegistration -ProviderNamespace "Microsoft.Contoso" -ProviderHubMetadataProviderAuthenticationAllowedAudience "https://management.core.windows.net/" -ProviderHubMetadataProviderAuthorization @{ApplicationId = "00000000-0000-0000-0000-000000000000"; RoleDefinitionId = "00000000-0000-0000-0000-000000000000"} -Namespace "Microsoft.Contoso" -ProviderVersion "2.0" -ProviderType "Internal" -ManagementManifestOwner "SPARTA-PlatformServiceAdministrator" -ManagementIncidentContactEmail "help@microsoft.com" -ManagementIncidentRoutingService "Contoso Service" -ManagementIncidentRoutingTeam "Contoso Team" -ManagementServiceTreeInfo @{ComponentId = "00000000-0000-0000-0000-000000000000"; ServiceId = "00000000-0000-0000-0000-000000000000"} -Capability @{QuotaId = "CSP_2015-05-01"; Effect = "Allow"}, @{QuotaId = "CSP_MG_2017-12-01"; Effect = "Allow"}

Name                Type
----                ----
Microsoft.Contoso   Microsoft.ProviderHub/providerRegistrations
```

Buat/Perbarui pendaftaran penyedia.

### Contoh 2: Buat/Perbarui pendaftaran penyedia.
```powershell
PS C:\> New-AzProviderHubProviderRegistration -ProviderNamespace "Microsoft.Contoso" -ProviderHubMetadataProviderAuthenticationAllowedAudience "https://management.core.windows.net/" -ProviderHubMetadataProviderAuthorization @{ApplicationId = "00000000-0000-0000-0000-000000000000"; RoleDefinitionId = "00000000-0000-0000-0000-000000000000"} -Namespace "Microsoft.Contoso" -ProviderVersion "2.0" -ProviderType "Hidden" -ManagementManifestOwner "SPARTA-PlatformServiceAdministrator" -ManagementIncidentContactEmail "help@microsoft.com" -ManagementIncidentRoutingService "Contoso Service" -ManagementIncidentRoutingTeam "Contoso Team" -ManagementServiceTreeInfo @{ComponentId = "00000000-0000-0000-0000-000000000000"; ServiceId = "00000000-0000-0000-0000-000000000000"} -Capability @{QuotaId = "CSP_2015-05-01"; Effect = "Allow"}, @{QuotaId = "CSP_MG_2017-12-01"; Effect = "Allow"}

Name                Type
----                ----
Microsoft.Contoso   Microsoft.ProviderHub/providerRegistrations
```

Buat/Perbarui pendaftaran penyedia.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -Capability
.
Untuk membuat, lihat bagian CATATAN untuk properti CAPABILITY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceProviderCapabilities[]
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

### -FeatureRuleRequiredFeaturesPolicy
.

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

### -ManagementIncidentContactEmail
.

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

### -ManagementIncidentRoutingService
.

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

### -ManagementIncidentRoutingTeam
.

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

### -ManagementBerfestOwner
.

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

### -ManagementResourceAccessPolicy
.

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

### -ManagementResourceAccessRole
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IAny[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementSchemaOwner
.

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

### -ManagementServiceTreeInfo
.
Untuk membuat, lihat bagian CATATAN untuk properti MANAGEMENTSERVICETREEINFO dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IServiceTreeInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metadata
Objek apa pun

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IAny
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
.

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

### -NoWait
Menjalankan perintah secara asinkron

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

### -ProviderAuthenticationAllowedAudience
.

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

### -ProviderAuthorization
.
Untuk membuat, lihat bagian CATATAN untuk properti PROVIDERAUTHORIZATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceProviderAuthorization[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderHubMetadataProviderAuthenticationAllowedAudience
.

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

### -ProviderHubMetadataProviderAuthorization
.
Untuk membuat, lihat bagian CATATAN untuk properti PROVIDERHUBMETADATAPROVIDERAUTHORIZATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceProviderAuthorization[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderNamespace
Nama penyedia sumber daya yang dihosting dalam ProviderHub.

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

### -ProviderType
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.ResourceProviderType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderVersion
.

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

### -ProvisioningState
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.ProvisioningState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestHeaderOptionOptInHeader
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.OptInHeaderType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredFeature
.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionLifecycleNotificationSpecificationSoftDeleteTtl
.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionLifecycleNotificationSpecificationSubscriptionStateOverrideAction
.
Untuk selanjutnya, lihat bagian CATATAN untuk PROPERTI SUBSCRIPTIONLIFECYCLENOTIFICATIONSPECIFICATIONSUBSCRIPTIONSTATEOVERRIDEACTION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ISubscriptionStateOverrideAction[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateDeploymentOptionPreflightOption
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.PreflightOption[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateDeploymentOptionPreflightSupported
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

### -ThirdPartyProviderAuthorizationAuthorization
.
Untuk membuat, lihat bagian CATATAN untuk properti THIRDPARTYPROVIDERAUTHORIZATIONAUTHORIZATION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ILightHouseAuthorization[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThirdPartyProviderAuthorizationManagedByTenantId
.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IProviderRegistration

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CAPABILITY <iResourceProviderCapabilities[]>: .
  - `Effect <ResourceProviderCapabilitiesEffect>`: 
  - `QuotaId <String>`: 
  - `[RequiredFeature <String[]>]`: 

MANAGEMENTSERVICETREEINFO <IServiceTreeInfo[]>: .
  - `[ComponentId <String>]`: 
  - `[ServiceId <String>]`: 

PROVIDERAUTHORIZATION <IResourceProviderAuthorization[]>: .
  - `[ApplicationId <String>]`: 
  - `[ManagedByRoleDefinitionId <String>]`: 
  - `[RoleDefinitionId <String>]`: 

PROVIDERHUBMETADATAPROVIDERAUTHORIZATION <IResourceProviderAuthorization[]>: .
  - `[ApplicationId <String>]`: 
  - `[ManagedByRoleDefinitionId <String>]`: 
  - `[RoleDefinitionId <String>]`: 

SUBSCRIPTIONLIFECYCLENOTIFICATIONSPECIFICATIONSUBSCRIPTIONSTATEOVERRIDEACTION <ISubscriptionStateOverrideAction[]>: .
  - `Action <SubscriptionNotificationOperation>`: 
  - `State <SubscriptionTransitioningState>`: 

THIRDPARTYPROVIDERAUTHORIZATIONAUTHORIZATION <ILightHouseAuthorization[]>: .
  - `PrincipalId <String>`: 
  - `RoleDefinitionId <String>`: 

## RELATED LINKS

