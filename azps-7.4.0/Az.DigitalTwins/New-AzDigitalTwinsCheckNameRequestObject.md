---
external help file: ''
Module Name: Az.DigitalTwins
online version: https://docs.microsoft.com/powershell/module/az.DigitalTwins/new-AzDigitalTwinsCheckNameRequestObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DigitalTwins/help/New-AzDigitalTwinsCheckNameRequestObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DigitalTwins/help/New-AzDigitalTwinsCheckNameRequestObject.md
ms.openlocfilehash: a58601641d5399441acb997aef5259e51fbe66c4
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144692464"
---
# New-AzDigitalTwinsCheckNameRequestObject

## SYNOPSIS
Membuat objek dalam memori untuk CheckNameRequest

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.digitaltwins/new-azdigitaltwinschecknamerequestobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDigitalTwinsCheckNameRequestObject -Name <String> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk CheckNameRequest

## EXAMPLES

### Contoh 1: Membuat DigitalTwinsCheckNameRequestObject menurut nama
```powershell
New-AzDigitalTwinsCheckNameRequestObject -name youriTestName
```

```output
Name          Type
----          ----
youriTestName Microsoft.DigitalTwins/digitalTwinsInstances
```

Membuat DigitalTwinsCheckNameRequestObject menurut nama

## PARAMETERS

### -Name
Nama sumber daya.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DigitalTwins.Models.Api20201031.CheckNameRequest

## NOTES

ALIAS

## RELATED LINKS

