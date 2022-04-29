---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewRegexClassificationRulePatternObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewRegexClassificationRulePatternObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewRegexClassificationRulePatternObject.md
ms.openlocfilehash: f605a04107a0a8b00ee082b1e664b995ef33094a
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144223946"
---
# New-AzPurviewRegexClassificationRulePatternObject

## SYNOPSIS
Buat objek dalam memori untuk RegexClassificationRulePattern.

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

Membuat Objek Pola Aturan Klasifikasi Regex

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
