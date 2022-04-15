---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderFilterablePropertyObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
ms.openlocfilehash: eecf7e5235808c399649dcddd7671295daa8a7e4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142258009"
---
# New-AzEdgeOrderFilterablePropertyObject

## SYNOPSIS
Membuat objek dalam memori untuk FilterableProperty.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.edgeorder/new-azedgeorderfilterablepropertyobject) untuk informasi terbaru.

## SYNTAX

```
New-AzEdgeOrderFilterablePropertyObject -SupportedValue <String[]> -Type <SupportedFilterTypes>
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk FilterableProperty.

## EXAMPLES

### Contoh 1: Objek properti yang dapat difilter 
```powershell
PS C:\> $filterableProperty = New-AzEdgeOrderFilterablePropertyObject -Type "ShipToCountries" -SupportedValue @("US")
PS C:\> $filterableProperty | fl

SupportedValue : {US}
Type           : ShipToCountries
```

ShipToCountries adalah tipe yang dapat difilter wajib, SupportedValue dapat berupa daftar kode negara ISO 2 huruf yang valid.

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

### -Tipe
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.FilterableProperty

## CATATAN

ALIAS

## RELATED LINKS

