---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.Datadog/new-AzDatadogFilteringTagObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogFilteringTagObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogFilteringTagObject.md
ms.openlocfilehash: 8090ba34b65879072cdf7c1d29946303a4c55c8d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144218015"
---
# New-AzDatadogFilteringTagObject

## SYNOPSIS
Membuat objek dalam memori untuk FilteringTag

## SYNTAX

```
New-AzDatadogFilteringTagObject [-Action <TagAction>] [-Name <String>] [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk FilteringTag

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk FilteringTag
```powershell
New-AzDatadogFilteringTagObject -Action "Include" -Value "Prod" -Name "Environment"
```

Perintah ini Membuat objek dalam memori untuk FilteringTag.

## PARAMETERS

### -Tindakan
Tindakan yang valid untuk tag pemfilteran.
Pengecualian lebih diprioritaskan daripada penyertaan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Support.TagAction
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

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.FilteringTag

## NOTES

ALIAS

## RELATED LINKS

