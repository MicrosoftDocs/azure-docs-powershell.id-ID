---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.ApplicationInsights/new-AzApplicationInsightsWebTestHeaderFieldObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestHeaderFieldObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestHeaderFieldObject.md
ms.openlocfilehash: 898256661dccf3e6970ca9a1496aaacf76b49b9b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141856328"
---
# New-AzApplicationInsightsWebTestHeaderFieldObject

## SYNOPSIS
Membuat objek dalam memori untuk HeaderField

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.applicationinsights/new-azapplicationinsightswebtestheaderfieldobject) untuk informasi terbaru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.HeaderField

## CATATAN

ALIAS

## RELATED LINKS

