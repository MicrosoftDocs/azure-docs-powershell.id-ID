---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewCustomClassificationRuleObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewCustomClassificationRuleObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewCustomClassificationRuleObject.md
ms.openlocfilehash: 364f88a4504286f222e824bad2600989fe8ff1e0
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144672964"
---
# New-AzPurviewCustomClassificationRuleObject

## SYNOPSIS
Buat objek dalam memori untuk CustomClassificationRule.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewcustomclassificationruleobject) untuk informasi terbaru.

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
