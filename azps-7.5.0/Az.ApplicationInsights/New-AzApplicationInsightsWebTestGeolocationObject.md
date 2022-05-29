---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.ApplicationInsights/new-AzApplicationInsightsWebTestGeolocationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
ms.openlocfilehash: fd161ef529250d57e23e9638d2ebc71183c71695
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145685290"
---
# New-AzApplicationInsightsWebTestGeolocationObject

## SYNOPSIS
Buat objek dalam memori untuk WebTestGeolocation.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.applicationinsights/new-azapplicationinsightswebtestgeolocationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzApplicationInsightsWebTestGeolocationObject [-Location <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk WebTestGeolocation.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk WebTestGeolocation
```powershell
New-AzApplicationInsightsWebTestGeolocationObject -Location "emea-nl-ams-azr"
```
```output
Location
--------
emea-nl-ams-azr
```

Perintah ini membuat objek memori untuk WebTestGeolocation.
Sebagai nilai `GeoLocation` parameter di `New-AzApplicationInsightsWebTest`.

## PARAMETERS

### -Lokasi
ID Lokasi untuk WebTest yang akan dijalankan.

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

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.WebTestGeolocation

## NOTES

ALIAS

## RELATED LINKS

