---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderFilterablePropertyObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
ms.openlocfilehash: 2aaefe6aa2ddef4eec7ddf2beee0ebc0fca5e1bc
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144715160"
---
# New-AzEdgeOrderFilterablePropertyObject

## SYNOPSIS
Buat objek dalam memori untuk FilterableProperty.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.edgeorder/new-azedgeorderfilterablepropertyobject) untuk informasi terbaru.

## SYNTAX

```
New-AzEdgeOrderFilterablePropertyObject -SupportedValue <String[]> -Type <SupportedFilterTypes>
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk FilterableProperty.

## EXAMPLES

### Contoh 1: Objek properti yang dapat difilter 
```powershell
$filterableProperty = New-AzEdgeOrderFilterablePropertyObject -Type "ShipToCountries" -SupportedValue @("US")
$filterableProperty | Format-List
```

```output
SupportedValue : {US}
Type           : ShipToCountries
```

ShipToCountries adalah jenis yang dapat difilter wajib, SupportedValue dapat menjadi daftar kode negara ISO yang valid 2 huruf.

## PARAMETERS

### -SupportedValue
Nilai yang akan difilter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Jenis filter produk.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Support.SupportedFilterTypes
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.FilterableProperty

## NOTES

ALIAS

## RELATED LINKS

