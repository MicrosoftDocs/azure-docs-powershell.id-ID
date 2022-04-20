---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.Elastic/new-AzElasticFilteringTagObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticFilteringTagObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticFilteringTagObject.md
ms.openlocfilehash: f3abdc802df070de20d60f6b2843a3fff814c683
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142684000"
---
# New-AzElasticFilteringTagObject

## SYNOPSIS
Membuat objek dalam memori untuk FilteringTag

## SYNTAX

```
New-AzElasticFilteringTagObject [-Action <TagAction>] [-Name <String>] [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk FilteringTag

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk FilteringTag yang digunakan saat membuat aturan tag
```powershell
$ft = New-AzElasticFilteringTagObject -Action Include -Name key -Value '1'
New-AzElasticTagRule -ResourceGroupName azure-elastic-test -MonitorName elastic-pwsh02 -LogRuleFilteringTag $ft
```

```output
Name    Type
----    ----
default microsoft.elastic/monitors/tagrules
```

Perintah ini membuat objek dalam memori untuk FilteringTag yang digunakan saat membuat aturan tag

## PARAMETERS

### -Tindakan
Tindakan valid untuk tag pemfilteran.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Elastic.Support.TagAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama (juga dikenal sebagai kunci) tag.

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

### -Value
Nilai tag.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.Api20200701.FilteringTag

## NOTES

ALIAS

## RELATED LINKS

