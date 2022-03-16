---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.ApplicationInsights/new-AzApplicationInsightsWebTestHeaderFieldObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestHeaderFieldObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestHeaderFieldObject.md
ms.openlocfilehash: 6f1cb43706f2c5c6f2ae4c002dbbfcb9be654d4d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139964373"
---
# New-AzApplicationInsightsWebTestHeaderFieldObject

## SYNOPSIS
Membuat objek dalam memori untuk HeaderField

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.applicationinsights/new-azapplicationinsightswebtestheaderfieldobject) untuk informasi terkini.

## SYNTAX

```
New-AzApplicationInsightsWebTestHeaderFieldObject [-Name <String>] [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk HeaderField

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk HeaderField
```powershell
PS C:\> New-AzApplicationInsightsWebTestHeaderFieldObject -Name 'version' -Value '2.0.1'

Name    Value
----    -----
version 2.0.1
```

Perintah ini membuat objek dalam memori untuk HeaderField, Sebagai nilai `RequestHeader` parameter dalam `New-AzApplicationInsightsWebTest`.

## PARAMETERS

### -Nama
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

### -Value
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.HeaderField

## CATATAN

ALIAS

## RELATED LINKS

