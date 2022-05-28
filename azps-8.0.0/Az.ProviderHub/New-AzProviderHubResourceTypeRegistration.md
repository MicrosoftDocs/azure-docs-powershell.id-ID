---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/new-azproviderhubresourcetyperegistration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubResourceTypeRegistration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubResourceTypeRegistration.md
ms.openlocfilehash: 3ddc60740cc3c65ac1b65a7ea7d6b557c9b6f76d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145620072"
---
# New-AzProviderHubResourceTypeRegistration

## SYNOPSIS
Membuat atau memperbarui jenis sumber daya.

## SYNTAX

```
New-AzProviderHubResourceTypeRegistration -ProviderNamespace <String> -ResourceType <String>
 [-SubscriptionId <String>] [-AllowedUnauthorizedAction <String[]>]
 [-AuthorizationActionMapping <IAuthorizationActionMapping[]>]
 [-CheckNameAvailabilitySpecificationEnableDefaultValidation]
 [-CheckNameAvailabilitySpecificationResourceTypesWithCustomValidation <String[]>]
 [-DefaultApiVersion <String>] [-DisallowedActionVerb <String[]>] [-EnableAsyncOperation]
 [-EnableThirdPartyS2S] [-Endpoint <IResourceTypeEndpoint[]>] [-ExtendedLocation <IExtendedLocationOptions[]>]
 [-FeatureRuleRequiredFeaturesPolicy <String>] [-IdentityManagementApplicationId <String>]
 [-IdentityManagementType <IdentityManagementTypes>] [-IsPureProxy]
 [-LinkedAccessCheck <ILinkedAccessCheck[]>] [-LoggingRule <ILoggingRule[]>] [-MarketplaceType <String>]
 [-ProvisioningState <ProvisioningState>] [-Regionality <Regionality>]
 [-RequestHeaderOptionOptInHeader <OptInHeaderType>] [-RequiredFeature <String[]>]
 [-ResourceCreationBeginRequest <ExtensionOptionType[]>]
 [-ResourceCreationBeginResponse <ExtensionOptionType[]>] [-ResourceDeletionPolicy <ResourceDeletionPolicy>]
 [-ResourceMovePolicyCrossResourceGroupMoveEnabled] [-ResourceMovePolicyCrossSubscriptionMoveEnabled]
 [-ResourceMovePolicyValidationRequired] [-RoutingType <RoutingType>] [-ServiceTreeInfo <IServiceTreeInfo[]>]
 [-SubscriptionLifecycleNotificationSpecificationSoftDeleteTtl <TimeSpan>]
 [-SubscriptionLifecycleNotificationSpecificationSubscriptionStateOverrideAction <ISubscriptionStateOverrideAction[]>]
 [-SubscriptionStateRule <ISubscriptionStateRule[]>] [-SwaggerSpecification <ISwaggerSpecification[]>]
 [-TemplateDeploymentOptionPreflightOption <PreflightOption[]>] [-TemplateDeploymentOptionPreflightSupported]
 [-ThrottlingRule <IThrottlingRule[]>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui jenis sumber daya.

## EXAMPLES

### Contoh 1: Membuat/Memperbarui pendaftaran jenis sumber daya.
```powershell
New-AzProviderHubResourceTypeRegistration -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType" -RoutingType "Default" -Regionality "Regional" -Endpoint @{ApiVersion = "2021-01-01-preview"; Location = "West US 2", "East US 2 EUAP"; RequiredFeature = "Microsoft.Contoso/SampleApp" } -SwaggerSpecification @{ApiVersion = "2021-01-01-preview"; SwaggerSpecFolderUri = "https://github.com/Azure/azure-rest-api-specs-pr/blob/RPSaaSMaster/specification/rpsaas/resource-manager/Microsoft.Contoso/" } -EnableAsyncOperation
```

```output
Name                  Type
----                  ----
testResourceType      Microsoft.ProviderHub/providerRegistrations/resourceTypeRegistrations
```

Membuat/Memperbarui pendaftaran jenis sumber daya.

### Contoh 2: Membuat/Memperbarui pendaftaran jenis sumber daya berlapis.
```powershell
New-AzProviderHubResourceTypeRegistration -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType/nestedResourceType" -RoutingType "Default" -Regionality "Global" -Endpoint @{ApiVersion = "2021-01-01-preview"; Location = ""; RequiredFeature = "Microsoft.Contoso/SampleApp" } -SwaggerSpecification @{ApiVersion = "2021-01-01-preview"; SwaggerSpecFolderUri = "https://github.com/Azure/azure-rest-api-specs-pr/blob/RPSaaSMaster/specification/rpsaas/resource-manager/Microsoft.Contoso/" }
```

```output
Name                                     Type
----                                     ----
testResourceType/nestedResourceType      Microsoft.ProviderHub/providerRegistrations/resourceTypeRegistrations
```

Membuat/Memperbarui pendaftaran jenis sumber daya berlapis.

## PARAMETERS

### -AllowedUnauthorizedAction
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

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -AuthorizationActionMapping
.
Untuk membuat, lihat bagian CATATAN untuk properti AUTHORIZATIONACTIONMAPPING dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IAuthorizationActionMapping[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CheckNameAvailabilitySpecificationEnableDefaultValidation
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

### -CheckNameAvailabilitySpecificationResourceTypesWithCustomValidation
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

### -DefaultApiVersion
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

### -DisallowedActionVerb
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

### -EnableAsyncOperation
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

### -EnableThirdPartyS2S
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

### -Titik akhir
.
Untuk membuat, lihat bagian CATATAN untuk properti TITIK AKHIR dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceTypeEndpoint[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedLocation
.
Untuk membuat, lihat bagian CATATAN untuk properti EXTENDEDLOCATION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IExtendedLocationOptions[]
Parameter Sets: (All)
Aliases:

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

### -IdentityManagementApplicationId
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

### -IdentityManagementType
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.IdentityManagementTypes
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPureProxy
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

### -LinkedAccessCheck
.
Untuk membuat, lihat bagian CATATAN untuk properti LINKEDACCESSCHECK dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ILinkedAccessCheck[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoggingRule
.
Untuk membuat, lihat bagian CATATAN untuk properti LOGGINGRULE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ILoggingRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarketplaceType
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
Jalankan perintah secara asinkron

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

### -Regionalitas
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.Regionality
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

### -ResourceCreationBeginRequest
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.ExtensionOptionType[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceCreationBeginResponse
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.ExtensionOptionType[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceDeletionPolicy
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.ResourceDeletionPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceMovePolicyCrossResourceGroupMoveEnabled
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

### -ResourceMovePolicyCrossSubscriptionMoveEnabled
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

### -ResourceMovePolicyValidationRequired
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

### -ResourceType
Jenis sumber daya.

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

### -RoutingType
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.RoutingType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceTreeInfo
.
Untuk membuat, lihat bagian CATATAN untuk properti SERVICETREEINFO dan buat tabel hash.

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
Untuk membuat, lihat bagian CATATAN untuk properti SUBSCRIPTIONLIFECYCLENOTIFICATIONSPECIFICATIONSUBSCRIPTIONSTATEOVERRIDEACTION dan buat tabel hash.

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

### -SubscriptionStateRule
.
Untuk membuat, lihat bagian CATATAN untuk properti SUBSCRIPTIONSTATERULE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ISubscriptionStateRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwaggerSpecification
.
Untuk membuat, lihat bagian CATATAN untuk properti SWAGGERSPECIFICATION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ISwaggerSpecification[]
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

### -ThrottlingRule
.
Untuk membuat, lihat bagian CATATAN untuk properti THROTTLINGRULE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IThrottlingRule[]
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceTypeRegistration

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AUTHORIZATIONACTIONMAPPING <IAuthorizationActionMapping[]>: .
  - `[Desired <String>]`: 
  - `[Original <String>]`: 

TITIK AKHIR <IResourceTypeEndpoint[]>: .
  - `[ApiVersion <String[]>]`: 
  - `[Enabled <Boolean?>]`: 
  - `[Extension <IResourceTypeExtension[]>]`: 
    - `[EndpointUri <String>]`: 
    - `[ExtensionCategory <ExtensionCategory[]>]`: 
    - `[Timeout <TimeSpan?>]`: 
  - `[FeatureRuleRequiredFeaturesPolicy <String>]`: 
  - `[Location <String[]>]`: 
  - `[RequiredFeature <String[]>]`: 
  - `[Timeout <TimeSpan?>]`: 

EXTENDEDLOCATION <IExtendedLocationOptions[]>: .
  - `[SupportedPolicy <String>]`: 
  - `[Type <String>]`: 

LINKEDACCESSCHECK <ILinkedAccessCheck[]>: .
  - `[ActionName <String>]`: 
  - `[LinkedAction <String>]`: 
  - `[LinkedActionVerb <String>]`: 
  - `[LinkedProperty <String>]`: 
  - `[LinkedType <String>]`: 

LOGGINGRULE <ILoggingRule[]>: .
  - `Action <String>`: 
  - `DetailLevel <LoggingDetails>`: 
  - `Direction <LoggingDirections>`: 
  - `[HiddenPropertyPathHiddenPathsOnRequest <String[]>]`: 
  - `[HiddenPropertyPathHiddenPathsOnResponse <String[]>]`: 

SERVICETREEINFO <IServiceTreeInfo[]>: .
  - `[ComponentId <String>]`: 
  - `[ServiceId <String>]`: 

SUBSCRIPTIONLIFECYCLENOTIFICATIONSPECIFICATIONSUBSCRIPTIONSTATEOVERRIDEACTION <ISubscriptionStateOverrideAction[]>: .
  - `Action <SubscriptionNotificationOperation>`: 
  - `State <SubscriptionTransitioningState>`: 

SUBSCRIPTIONSTATERULE <ISubscriptionStateRule[]>: .
  - `[AllowedAction <String[]>]`: 
  - `[State <SubscriptionState?>]`: 

SWAGGERSPECIFICATION <ISwaggerSpecification[]>: .
  - `[ApiVersion <String[]>]`: 
  - `[SwaggerSpecFolderUri <String>]`: 

THROTTLINGRULE <IThrottlingRule[]>: .
  - `Action <String>`: 
  - `Metric <IThrottlingMetric[]>`: 
    - `Limit <Int64>`: 
    - `Type <ThrottlingMetricType>`: 
    - `[Interval <TimeSpan?>]`: 
  - `[RequiredFeature <String[]>]`: 

## RELATED LINKS

