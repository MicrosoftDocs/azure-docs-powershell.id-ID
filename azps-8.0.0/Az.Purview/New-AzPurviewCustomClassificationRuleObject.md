---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewCustomClassificationRuleObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewCustomClassificationRuleObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewCustomClassificationRuleObject.md
ms.openlocfilehash: 4076b5577fe0c9519e04e26921c5c1942aa4f2ce
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145563131"
---
# New-AzPurviewCustomClassificationRuleObject

## SYNOPSIS
Buat objek dalam memori untuk CustomClassificationRule.

## SYNTAX

```
New-AzPurviewCustomClassificationRuleObject -Kind <ClassificationRuleType> [-ClassificationName <String>]
 [-ColumnPattern <IClassificationRulePattern[]>] [-DataPattern <IClassificationRulePattern[]>]
 [-Description <String>] [-MinimumPercentageMatch <Double>] [-RuleStatus <ClassificationRuleStatus>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk CustomClassificationRule.

## EXAMPLES

### Contoh 1: Membuat objek aturan klasifikasi kustom
```powershell
PS C:\> $reg1 = New-AzPurviewRegexClassificationRulePatternObject -Pattern '^col1$'
$reg2 = New-AzPurviewRegexClassificationRulePatternObject -Pattern '^col2$'
$regexarr = @($reg1, $reg2)
New-AzPurviewCustomClassificationRuleObject -Kind 'Custom' -ClassificationName ClassificationRule4 -MinimumPercentageMatch 60 -RuleStatus 'Enabled' -Description 'This is a rule2' -ColumnPattern $regexarr

ClassificationAction   :
ClassificationName     : ClassificationRule4
ColumnPattern          : {{
                           "kind": "Regex",
                           "pattern": "^col1$"
                         }, {
                           "kind": "Regex",
                           "pattern": "^col2$"
                         }}
CreatedAt              :
DataPattern            :
Description            : This is a rule2
Id                     :
Kind                   : Custom
LastModifiedAt         :
MinimumPercentageMatch : 60
Name                   :
RuleStatus             : Enabled
Version                :
```

Membuat objek aturan klasifikasi kustom

## PARAMETERS

### -ClassificationName

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

### -ColumnPattern

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IClassificationRulePattern[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataPattern

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IClassificationRulePattern[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi

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

### -Kind

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.ClassificationRuleType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumPercentageMatch

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleStatus

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.ClassificationRuleStatus
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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.CustomClassificationRule

## NOTES

ALIAS

## RELATED LINKS
