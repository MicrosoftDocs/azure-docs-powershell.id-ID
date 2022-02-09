---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/new-azproviderhubdefaultrollout
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubDefaultRollout.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubDefaultRollout.md
ms.openlocfilehash: 4344f8d7fc9e60a778e79c5e16954fe11dbba356
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138283084"
---
# New-AzProviderHubDefaultRollout

## SYNOPSIS
Membuat atau memperbarui detail peluncuran.

## SYNTAX

```
New-AzProviderHubDefaultRollout -ProviderNamespace <String> -RolloutName <String> [-SubscriptionId <String>]
 [-CanaryRegion <String[]>] [-CanarySkipRegion <String[]>] [-HighTrafficRegion <String[]>]
 [-HighTrafficWaitDuration <TimeSpan>] [-LowTrafficRegion <String[]>] [-LowTrafficWaitDuration <TimeSpan>]
 [-MediumTrafficRegion <String[]>] [-MediumTrafficWaitDuration <TimeSpan>]
 [-ProvisioningState <ProvisioningState>] [-RestOfTheWorldGroupOneRegion <String[]>]
 [-RestOfTheWorldGroupOneWaitDuration <TimeSpan>] [-RestOfTheWorldGroupTwoRegion <String[]>]
 [-RestOfTheWorldGroupTwoWaitDuration <TimeSpan>] [-SpecificationProviderRegistration <IProviderRegistration>]
 [-SpecificationResourceTypeRegistration <IResourceTypeRegistration[]>] [-StatusCompletedRegion <String[]>]
 [-StatusFailedOrSkippedRegion <Hashtable>] [-StatusNextTrafficRegion <TrafficRegionCategory>]
 [-StatusNextTrafficRegionScheduledTime <DateTime>]
 [-StatusSubscriptionReregistrationResult <SubscriptionReregistrationResult>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui detail peluncuran.

## EXAMPLES

### Contoh 1: Buat/Perbarui peluncuran default penyedia sumber daya.
```powershell
PS C:\> New-AzProviderHubDefaultRollout -ProviderNamespace "Microsoft.Contoso" -RolloutName "defaultRollout2021w10" -CanarySkipRegion "brazilus" -NoWait

Name                      Type
----                      ----
defaultRollout2021w10     Microsoft.ProviderHub/providerRegistrations/defaultRollouts
```

Membuat/Memperbarui peluncuran default penyedia sumber daya.

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

### -CanaryRegion
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

### -CanarySkipRegion
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

### -HighTrafficRegion
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

### -HighTrafficWaitDuration
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

### -LowTrafficRegion
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

### -LowTrafficWaitDuration
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

### -MediumTrafficRegion
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

### -MediumTrafficWaitDuration
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

### -RestOfTheWorldGroupOneRegion
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

### -RestOfTheWorldGroupOneWaitDuration
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

### -RestOfTheWorldGrouptwoRegion
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

### -RestOfTheWorldGrouptwoWaitDuration
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

### -RolloutName
Nama peluncuran.

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

### -SpecificationProviderRegistration
.
Untuk membuat, lihat bagian CATATAN untuk SPESIFIKASI PROPERTIPROVIDERREGISTRATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IProviderRegistration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpecificationResourceTypeRegistration
.
Untuk membangun, lihat bagian CATATAN untuk properti SPECIFICATIONRESOURCETYPEREGISTRATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceTypeRegistration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusCompletedRegion
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

### -StatusFailedOrSkippedRegion
Kamus dari \<ExtendedErrorInfo\>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusNextTrafficRegion
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.TrafficRegionCategory
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusNextTrafficRegionScheduledTime
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

### -StatusSubscriptionReregistrationResult
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.SubscriptionReregistrationResult
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

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IDefaultRollout

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


SPECIFICATIONPROVIDERREGISTRATION <IProviderRegistration>: .
  - `[Capability <IResourceProviderCapabilities[]>]`: 
    - `Effect <ResourceProviderCapabilitiesEffect>`: 
    - `QuotaId <String>`: 
    - `[RequiredFeature <String[]>]`: 
  - `[FeatureRuleRequiredFeaturesPolicy <String>]`: 
  - `[ManagementIncidentContactEmail <String>]`: 
  - `[ManagementIncidentRoutingService <String>]`: 
  - `[ManagementIncidentRoutingTeam <String>]`: 
  - `[ManagementManifestOwner <String[]>]`: 
  - `[ManagementResourceAccessPolicy <String>]`: 
  - `[ManagementResourceAccessRole <IAny[]>]`: 
  - `[ManagementSchemaOwner <String[]>]`: 
  - `[ManagementServiceTreeInfo <IServiceTreeInfo[]>]`: 
    - `[ComponentId <String>]`: 
    - `[ServiceId <String>]`: 
  - `[Metadata <IAny>]`: Objek apa pun
  - `[Namespace <String>]`: 
  - `[ProviderAuthenticationAllowedAudience <String[]>]`: 
  - `[ProviderAuthorization <IResourceProviderAuthorization[]>]`: 
    - `[ApplicationId <String>]`: 
    - `[ManagedByRoleDefinitionId <String>]`: 
    - `[RoleDefinitionId <String>]`: 
  - `[ProviderHubMetadataProviderAuthenticationAllowedAudience <String[]>]`: 
  - `[ProviderHubMetadataProviderAuthorization <IResourceProviderAuthorization[]>]`: 
  - `[ProviderType <ResourceProviderType?>]`: 
  - `[ProviderVersion <String>]`: 
  - `[ProvisioningState <ProvisioningState?>]`: 
  - `[RequestHeaderOptionOptInHeader <OptInHeaderType?>]`: 
  - `[RequiredFeature <String[]>]`: 
  - `[SubscriptionLifecycleNotificationSpecificationSoftDeleteTtl <TimeSpan?>]`: 
  - `[SubscriptionLifecycleNotificationSpecificationSubscriptionStateOverrideAction <ISubscriptionStateOverrideAction[]>]`: 
    - `Action <SubscriptionNotificationOperation>`: 
    - `State <SubscriptionTransitioningState>`: 
  - `[TemplateDeploymentOptionPreflightOption <PreflightOption[]>]`: 
  - `[TemplateDeploymentOptionPreflightSupported <Boolean?>]`: 
  - `[ThirdPartyProviderAuthorizationAuthorization <ILightHouseAuthorization[]>]`: 
    - `PrincipalId <String>`: 
    - `RoleDefinitionId <String>`: 
  - `[ThirdPartyProviderAuthorizationManagedByTenantId <String>]`: 

SPECIFICATIONRESOURCETYPEREGISTRATION <IResourceTypeRegistration[]>: .
  - `[AllowedUnauthorizedAction <String[]>]`: 
  - `[AuthorizationActionMapping <IAuthorizationActionMapping[]>]`: 
    - `[Desired <String>]`: 
    - `[Original <String>]`: 
  - `[CheckNameAvailabilitySpecificationEnableDefaultValidation <Boolean?>]`: 
  - `[CheckNameAvailabilitySpecificationResourceTypesWithCustomValidation <String[]>]`: 
  - `[DefaultApiVersion <String>]`: 
  - `[DisallowedActionVerb <String[]>]`: 
  - `[EnableAsyncOperation <Boolean?>]`: 
  - `[EnableThirdPartyS2S <Boolean?>]`: 
  - `[Endpoint <IResourceTypeEndpoint[]>]`: 
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
  - `[ExtendedLocation <IExtendedLocationOptions[]>]`: 
    - `[SupportedPolicy <String>]`: 
    - `[Type <String>]`: 
  - `[FeatureRuleRequiredFeaturesPolicy <String>]`: 
  - `[IdentityManagementApplicationId <String>]`: 
  - `[IdentityManagementType <IdentityManagementTypes?>]`: 
  - `[IsPureProxy <Boolean?>]`: 
  - `[LinkedAccessCheck <ILinkedAccessCheck[]>]`: 
    - `[ActionName <String>]`: 
    - `[LinkedAction <String>]`: 
    - `[LinkedActionVerb <String>]`: 
    - `[LinkedProperty <String>]`: 
    - `[LinkedType <String>]`: 
  - `[LoggingRule <ILoggingRule[]>]`: 
    - `Action <String>`: 
    - `DetailLevel <LoggingDetails>`: 
    - `Direction <LoggingDirections>`: 
    - `[HiddenPropertyPathHiddenPathsOnRequest <String[]>]`: 
    - `[HiddenPropertyPathHiddenPathsOnResponse <String[]>]`: 
  - `[MarketplaceType <String>]`: 
  - `[ProvisioningState <ProvisioningState?>]`: 
  - `[Regionality <Regionality?>]`: 
  - `[RequestHeaderOptionOptInHeader <OptInHeaderType?>]`: 
  - `[RequiredFeature <String[]>]`: 
  - `[ResourceCreationBeginRequest <ExtensionOptionType[]>]`: 
  - `[ResourceCreationBeginResponse <ExtensionOptionType[]>]`: 
  - `[ResourceDeletionPolicy <ResourceDeletionPolicy?>]`: 
  - `[ResourceMovePolicyCrossResourceGroupMoveEnabled <Boolean?>]`: 
  - `[ResourceMovePolicyCrossSubscriptionMoveEnabled <Boolean?>]`: 
  - `[ResourceMovePolicyValidationRequired <Boolean?>]`: 
  - `[RoutingType <RoutingType?>]`: 
  - `[ServiceTreeInfo <IServiceTreeInfo[]>]`: 
    - `[ComponentId <String>]`: 
    - `[ServiceId <String>]`: 
  - `[SubscriptionLifecycleNotificationSpecificationSoftDeleteTtl <TimeSpan?>]`: 
  - `[SubscriptionLifecycleNotificationSpecificationSubscriptionStateOverrideAction <ISubscriptionStateOverrideAction[]>]`: 
    - `Action <SubscriptionNotificationOperation>`: 
    - `State <SubscriptionTransitioningState>`: 
  - `[SubscriptionStateRule <ISubscriptionStateRule[]>]`: 
    - `[AllowedAction <String[]>]`: 
    - `[State <SubscriptionState?>]`: 
  - `[SwaggerSpecification <ISwaggerSpecification[]>]`: 
    - `[ApiVersion <String[]>]`: 
    - `[SwaggerSpecFolderUri <String>]`: 
  - `[TemplateDeploymentOptionPreflightOption <PreflightOption[]>]`: 
  - `[TemplateDeploymentOptionPreflightSupported <Boolean?>]`: 
  - `[ThrottlingRule <IThrottlingRule[]>]`: 
    - `Action <String>`: 
    - `Metric <IThrottlingMetric[]>`: 
      - `Limit <Int64>`: 
      - `Type <ThrottlingMetricType>`: 
      - `[Interval <TimeSpan?>]`: 
    - `[RequiredFeature <String[]>]`: 

## RELATED LINKS

