---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.ApplicationInsights/new-AzApplicationInsightsWebTestGeolocationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
ms.openlocfilehash: ad5c66a29a66803ef770f7445e9789fc904ecd51
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136571771"
---
# New-AzApplicationInsightsWebTestGeolocationObject

## SYNOPSIS
Buat objek dalam memori untuk WebTestGeolocation.

## SYNTAX

```
New-AzApplicationInsightsWebTestGeolocationObject [-Location <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk WebTestGeolocation.

## EXAMPLES

### Contoh 1: Buat objek dalam memori untuk WebTestGeolocation
```powershell
PS C:\> New-AzApplicationInsightsWebTestGeolocationObject -Location "emea-nl-ams-azr"

Location
--------
emea-nl-ams-azr
```

Perintah ini membuat objek memori untuk WebTestGeolocation.
Sebagai nilai `GeoLocation` dari parameter dalam `New-AzApplicationInsightsWebTest` .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.WebTestGeolocation

## CATATAN

ALIAS

## RELATED LINKS

