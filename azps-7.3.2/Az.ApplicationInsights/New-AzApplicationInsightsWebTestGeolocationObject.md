---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.ApplicationInsights/new-AzApplicationInsightsWebTestGeolocationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
ms.openlocfilehash: fd161ef529250d57e23e9638d2ebc71183c71695
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141792193"
---
# New-AzApplicationInsightsWebTestGeolocationObject

## SYNOPSIS
Membuat objek dalam memori untuk WebTestGeolocation.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.applicationinsights/new-azapplicationinsightswebtestgeolocationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzApplicationInsightsWebTestGeolocationObject [-Location <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk WebTestGeolocation.

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
Sebagai nilai `GeoLocation` parameter dalam `New-AzApplicationInsightsWebTest`.

## PARAMETERS

### -Lokasi
ID Lokasi untuk webTest yang dijalankan.

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

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.WebTestGeolocation

## CATATAN

ALIAS

## RELATED LINKS

