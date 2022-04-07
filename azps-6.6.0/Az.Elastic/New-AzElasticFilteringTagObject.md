---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.Elastic/new-AzElasticFilteringTagObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticFilteringTagObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticFilteringTagObject.md
ms.openlocfilehash: 9bebdf7abe1a684fdef1503d4de500156b66fa5a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140286367"
---
# New-AzElasticFilteringTagObject

## SYNOPSIS
Membuat objek dalam memori untuk FilteringTag

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.elastic/new-azelasticfilteringtagobject) untuk informasi terkini.

## SYNTAX

```
New-AzElasticFilteringTagObject [-Action <TagAction>] [-Name <String>] [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk FilteringTag

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk PemfilteranTag yang digunakan saat membuat aturan tag
```powershell
PS C:\> $ft = New-AzElasticFilteringTagObject -Action Include -Name key -Value '1'
PS C:\> New-AzElasticTagRule -ResourceGroupName azure-elastic-test -MonitorName elastic-pwsh02 -LogRuleFilteringTag $ft

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Elastis.Models.Api20200701.FilteringTag

## CATATAN

ALIAS

## RELATED LINKS

