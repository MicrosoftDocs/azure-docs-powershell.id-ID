---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/new-azproviderhubsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubSku.md
ms.openlocfilehash: a32dec7d6b0bc02bf0223ed2a125e892835d3760
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142962317"
---
# New-AzProviderHubSku

## SYNOPSIS
Membuat atau memperbarui sku jenis sumber daya dalam jenis sumber daya yang diberikan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.providerhub/new-azproviderhubsku) untuk informasi terbaru.

## SYNTAX

```
New-AzProviderHubSku -ProviderNamespace <String> -ResourceType <String> -Sku <String>
 -SkuSetting <ISkuSetting[]> [-SubscriptionId <String>] [-ProvisioningState <ProvisioningState>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui sku jenis sumber daya dalam jenis sumber daya yang diberikan.

## EXAMPLES

### Contoh 1: Membuat/Memperbarui definisi SKU sumber daya.
```powershell
PS C:\> New-AzProviderHubSku -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType" -Sku "default" -SkuSetting @{Name = "freeSku"; Tier = "Tier1"; Kind = "Standard"}

Name      Type
----      ----
default   Microsoft.ProviderHub/providerRegistrations/skus
```

Membuat/Memperbarui definisi SKU sumber daya.

### Contoh 2: Membuat/Memperbarui definisi SKU jenis sumber daya berlapis.
```powershell
PS C:\> New-AzProviderHubSku -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType/nestedResourceType" -Sku "default" -SkuSetting @{Name = "freeSku"; Tier = "Tier1"; Kind = "Standard"}

Name      Type
----      ----
default   Microsoft.ProviderHub/providerRegistrations/skus
```

Membuat/Memperbarui definisi SKU jenis sumber daya berlapis.

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

### -Sku
The SKU.

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

### -SkuSetting
.
Untuk membuat, lihat bagian CATATAN untuk properti SKUSETTING dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ISkuSetting[]
Parameter Sets: (All)
Aliases:

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ISkuResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


SKUSETTING <ISkuSetting[]>: .
  - `Name <String>`: 
  - `[Capability <ISkuCapability[]>]`: 
    - `Name <String>`: 
    - `Value <String>`: 
  - `[CapacityDefault <Int32?>]`: 
  - `[CapacityMaximum <Int32?>]`: 
  - `[CapacityMinimum <Int32?>]`: 
  - `[CapacityScaleType <SkuScaleType?>]`: 
  - `[Cost <ISkuCost[]>]`: 
    - `MeterId <String>`: 
    - `[ExtendedUnit <String>]`: 
    - `[Quantity <Int32?>]`: 
  - `[Family <String>]`: 
  - `[Kind <String>]`: 
  - `[Location <String[]>]`: 
  - `[LocationInfo <ISkuLocationInfo[]>]`: 
    - `Location <String>`: 
    - `[ExtendedLocation <String[]>]`: 
    - `[Type <String>]`: 
    - `[Zone <String[]>]`: 
    - `[ZoneDetail <ISkuZoneDetail[]>]`: 
      - `[Capability <ISkuCapability[]>]`: 
      - `[Name <String[]>]`: 
  - `[RequiredFeature <String[]>]`: 
  - `[RequiredQuotaId <String[]>]`: 
  - `[Size <String>]`: 
  - `[Tier <String>]`: 

## RELATED LINKS

