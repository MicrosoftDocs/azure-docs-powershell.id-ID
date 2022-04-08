---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderFilterablePropertyObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
ms.openlocfilehash: c3f6d12ab2bc088a39b5f1f719e5ca29f0a57f0b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140402867"
---
# New-AzEdgeOrderFilterablePropertyObject

## SYNOPSIS
Buat objek dalam memori untuk FilterableProperty.

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
PS C:\> $filterableProperty = New-AzEdgeOrderFilterablePropertyObject -Type "ShipToCountries" -SupportedValue @("US")
PS C:\> $filterableProperty | fl

SupportedValue : {US}
Type           : ShipToCountries
```

ShipToCountries adalah tipe wajib yang dapat difilter, SupportedValue dapat mencantumkan 2 huruf kode negara ISO yang valid.

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
Tipe filter produk.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.FilterableProperty

## CATATAN

ALIAS

## RELATED LINKS

