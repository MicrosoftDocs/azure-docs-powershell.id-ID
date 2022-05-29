---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.Elastic/new-AzElasticFilteringTagObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticFilteringTagObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticFilteringTagObject.md
ms.openlocfilehash: 1a63a4ddc2555a1f5cdb4a9bc312728e6b5f9a9f
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145781056"
---
# New-AzElasticFilteringTagObject

## SYNOPSIS
Membuat objek dalam memori untuk FilteringTag

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.elastic/new-azelasticfilteringtagobject) untuk informasi terbaru.

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
Tindakan yang valid untuk tag pemfilteran.

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

### -Name
Nama (juga dikenal sebagai kunci) dari tag.

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

### -Nilai
Nilai dari tag.

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

### Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.Api20200701.FilteringTag

## NOTES

ALIAS

## RELATED LINKS

