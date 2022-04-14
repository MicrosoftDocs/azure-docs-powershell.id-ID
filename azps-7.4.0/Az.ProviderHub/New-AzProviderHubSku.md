---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/new-azproviderhubsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubSku.md
ms.openlocfilehash: 940c3996ed885a92c1215b1a672695424084d3cf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142175534"
---
# New-AzProviderHubSku

## SYNOPSIS
Membuat atau memperbarui sku tipe sumber daya dalam tipe sumber daya tertentu.

## SYNTAX

```
New-AzProviderHubSku -ProviderNamespace <String> -ResourceType <String> -Sku <String>
 -SkuSetting <ISkuSetting[]> [-SubscriptionId <String>] [-ProvisioningState <ProvisioningState>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui sku tipe sumber daya dalam tipe sumber daya tertentu.

## EXAMPLES

### Contoh 1: Buat/Perbarui definisi SKU sumber daya.
```powershell
New-AzProviderHubSku -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType" -Sku "default" -SkuSetting @{Name = "freeSku"; Tier = "Tier1"; Kind = "Standard"}
```

```output
Name      Type
----      ----
default   Microsoft.ProviderHub/providerRegistrations/skus
```

Membuat/Memperbarui definisi SKU sumber daya.

### Contoh 2: Buat/Perbarui definisi SKU tipe sumber daya bertumpuk.
```powershell
New-AzProviderHubSku -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType/nestedResourceType" -Sku "default" -SkuSetting @{Name = "freeSku"; Tier = "Tier1"; Kind = "Standard"}
```

```output
Name      Type
----      ----
default   Microsoft.ProviderHub/providerRegistrations/skus
```

Membuat/Memperbarui definisi SKU tipe sumber daya bertumpuk.

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
Tipe sumber daya.

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
Untuk membuat, lihat bagian CATATAN untuk properti SKUSETTING dan membuat tabel hash.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.ISkuResource

## CATATAN

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

