---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewRegexClassificationRulePatternObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewRegexClassificationRulePatternObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewRegexClassificationRulePatternObject.md
ms.openlocfilehash: 60f818390c3079ee9380e444abd88809f12bc4c8
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145652296"
---
# New-AzPurviewRegexClassificationRulePatternObject

## SYNOPSIS
Buat objek dalam memori untuk RegexClassificationRulePattern.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewregexclassificationrulepatternobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewRegexClassificationRulePatternObject [-Pattern <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk RegexClassificationRulePattern.

## EXAMPLES

### Contoh 1: Buat Objek Pola Aturan Klasifikasi Regex
```powershell
PS C:\> New-AzPurviewRegexClassificationRulePatternObject -Pattern '^col1$'

Kind  Pattern
----  -------
Regex ^col1$
```

Buat Objek Pola Aturan Klasifikasi Regex

## PARAMETERS

### -Pola

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.RegexClassificationRulePattern

## NOTES

ALIAS

## RELATED LINKS
