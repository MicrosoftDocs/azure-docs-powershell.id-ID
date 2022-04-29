---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.ApplicationInsights/new-AzApplicationInsightsWebTestHeaderFieldObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestHeaderFieldObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestHeaderFieldObject.md
ms.openlocfilehash: 589cf8e1913ee9d0b38a969c4de3a734a77ba127
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144221126"
---
# New-AzApplicationInsightsWebTestHeaderFieldObject

## SYNOPSIS
Membuat objek dalam memori untuk HeaderField

## SYNTAX

```
New-AzApplicationInsightsWebTestHeaderFieldObject [-Name <String>] [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk HeaderField

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk HeaderField
```powershell
New-AzApplicationInsightsWebTestHeaderFieldObject -Name 'version' -Value '2.0.1'
```
```output
Name    Value
----    -----
version 2.0.1
```

Perintah ini membuat objek dalam memori untuk HeaderField, Sebagai nilai `RequestHeader` parameter di `New-AzApplicationInsightsWebTest`.

## PARAMETERS

### -Name
Nama header.

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
Nilai header.

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

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.HeaderField

## NOTES

ALIAS

## RELATED LINKS

