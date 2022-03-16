---
external help file: ''
Module Name: Az.DigitalTwins
online version: https://docs.microsoft.com/powershell/module/az.DigitalTwins/new-AzDigitalTwinsCheckNameRequestObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DigitalTwins/help/New-AzDigitalTwinsCheckNameRequestObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DigitalTwins/help/New-AzDigitalTwinsCheckNameRequestObject.md
ms.openlocfilehash: 7fb9f3daa786d9d0f5c9c4d1aff27949ffcba92f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140001006"
---
# New-AzDigitalTwinsCheckNameRequestObject

## SYNOPSIS
Membuat objek dalam memori untuk CheckNameRequest

## SYNTAX

```
New-AzDigitalTwinsCheckNameRequestObject -Name <String> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk CheckNameRequest

## EXAMPLES

### Contoh 1: Create a DigitalTwinsCheckNameRequestObject by name
```powershell
PS C:\> New-AzDigitalTwinsCheckNameRequestObject -name youriTestName

Name          Type
----          ----
youriTestName Microsoft.DigitalTwins/digitalTwinsInstances
```

Membuat DigitalTwinsCheckNameRequestObject menurut nama

## PARAMETERS

### -Nama
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DigitalTwins.Models.Api20201031.CheckNameRequest

## CATATAN

ALIAS

## RELATED LINKS

