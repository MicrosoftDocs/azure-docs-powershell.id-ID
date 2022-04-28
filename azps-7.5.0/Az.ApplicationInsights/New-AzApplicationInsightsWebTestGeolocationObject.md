---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.ApplicationInsights/new-AzApplicationInsightsWebTestGeolocationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTestGeolocationObject.md
ms.openlocfilehash: 402417d188976fc4eb557f61e601375c791fdda2
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144221135"
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

