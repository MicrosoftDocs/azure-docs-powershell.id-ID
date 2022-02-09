---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/get-azmanagedservicesmarketplacedefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesMarketplaceDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesMarketplaceDefinition.md
ms.openlocfilehash: 5669dabe493aa93f6a0f3a723fbeb8c80bf9f5c4
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138295548"
---
# Get-AzManagedServicesMarketplaceDefinition

## SYNOPSIS
Dapatkan definisi registrasi marketplace untuk pengidentifikasi marketplace.

## SYNTAX

### ListWithScope (Default)
```
Get-AzManagedServicesMarketplaceDefinition [-Scope <String>] [-Filter <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzManagedServicesMarketplaceDefinition -InputObject <IManagedServicesIdentity>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetWithoutScope
```
Get-AzManagedServicesMarketplaceDefinition -MarketplaceIdentifier <String> -Tenant
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetWithScope
```
Get-AzManagedServicesMarketplaceDefinition -MarketplaceIdentifier <String> [-Scope <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ListWithoutScope
```
Get-AzManagedServicesMarketplaceDefinition -Tenant [-Filter <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan definisi registrasi marketplace untuk pengidentifikasi marketplace.

## EXAMPLES

### Contoh 1: Dapatkan definisi pendaftaran Azure Lighthouse Marketplace yang menawarkan detail
```powershell
PS C:\> Get-AzManagedServicesMarketplaceDefinition -MarketplaceIdentifier marketplace_test.managed_offer.managed_plan1.1.0.1 | Format-List Id, PlanProduct, PlanPublisher, PlanName, PlanVersion

Id            : /providers/Microsoft.ManagedServices/marketplaceRegistrationDefinitions/marketplace_test.managed_offer.managed_plan1.1.0.1
PlanProduct   : managed_offer
PlanPublisher : marketplace_test
PlanName      : managed_plan1
PlanVersion   : 1.0.1
```

Dapatkan detail penawaran definisi pendaftaran Azure Lighthouse Marketplace.

## PARAMETERS

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

### -Filter
Filter parameter kueri untuk memfilter definisi registrasi marketplace menurut pengidentifikasi rencana, publisher, versi dll.

```yaml
Type: System.String
Parameter Sets: ListWithoutScope, ListWithScope
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.IManagedServicesIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MarketplaceIdentifier
Pengidentifikasi Azure Marketplace.
Format yang diharapkan: {publisher}. {product[-preview]}. {planName}. {version} atau {publisher}. {product[-preview]}. {planName} atau {publisher}. {product[-preview]} atau {publisher}).

```yaml
Type: System.String
Parameter Sets: GetWithoutScope, GetWithScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup sumber daya.

```yaml
Type: System.String
Parameter Sets: GetWithScope, ListWithScope
Aliases:

Required: False
Position: Named
Default value: "subscriptions/" + (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Penyewa
Filter parameter kueri untuk memfilter definisi registrasi marketplace menurut pengidentifikasi rencana, publisher, versi dll.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetWithoutScope, ListWithoutScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.IManagedServicesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IMarketplaceRegistrationDefinition

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IManagedServicesIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MarketplaceIdentifier <String>]`: Pengidentifikasi Azure Marketplace. Format yang diharapkan: {publisher}. {product[-preview]}. {planName}. {version} atau {publisher}. {product[-preview]}. {planName} atau {publisher}. {product[-preview]} atau {publisher}).
  - `[RegistrationAssignmentId <String>]`: GUID penetapan pendaftaran.
  - `[RegistrationDefinitionId <String>]`: GUID definisi registrasi.
  - `[Scope <String>]`: Lingkup sumber daya.

## RELATED LINKS

