---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/get-azmapssubscriptionoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsSubscriptionOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsSubscriptionOperation.md
ms.openlocfilehash: 826862417ffef5e66ebdb7a581640b90de005223
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142229761"
---
# Get-AzMapsSubscriptionOperation

## SYNOPSIS
Operasi daftar tersedia untuk Penyedia Sumber Daya Peta

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.maps/get-azmapssubscriptionoperation) untuk informasi terbaru.

## SYNTAX

```
Get-AzMapsSubscriptionOperation [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Operasi daftar tersedia untuk Penyedia Sumber Daya Peta

## EXAMPLES

### Contoh 1: Operasi daftar tersedia untuk Penyedia Sumber Daya Peta
```powershell
PS C:\> Get-AzMapsSubscriptionOperation

IsDataAction Name                                                                          Origin
------------ ----                                                                          ------
             Microsoft.Maps/resourceTypes/read
             Microsoft.Maps/unregister/action
             Microsoft.Maps/operations/read
             Microsoft.Maps/register/action
             Microsoft.Maps/accounts/write
             Microsoft.Maps/accounts/read
             Microsoft.Maps/accounts/delete
             Microsoft.Maps/accounts/listKeys/action
             Microsoft.Maps/accounts/regenerateKey/action
             Microsoft.Maps/accounts/eventGridFilters/delete
             Microsoft.Maps/accounts/eventGridFilters/read
             Microsoft.Maps/accounts/eventGridFilters/write
             Microsoft.Maps/accounts/providers/Microsoft.Insights/metricDefinitions/read   system
             Microsoft.Maps/accounts/providers/Microsoft.Insights/diagnosticSettings/read  system
             Microsoft.Maps/accounts/providers/Microsoft.Insights/diagnosticSettings/write system
True         Microsoft.Maps/accounts/services/render/read
True         Microsoft.Maps/accounts/services/geolocation/read
True         Microsoft.Maps/accounts/services/mobility/read
True         Microsoft.Maps/accounts/services/route/read
True         Microsoft.Maps/accounts/services/search/read
True         Microsoft.Maps/accounts/services/timezone/read
True         Microsoft.Maps/accounts/services/traffic/read
True         Microsoft.Maps/accounts/services/weather/read
True         Microsoft.Maps/accounts/services/data/read
True         Microsoft.Maps/accounts/services/data/delete
True         Microsoft.Maps/accounts/services/data/write
True         Microsoft.Maps/accounts/services/spatial/read
True         Microsoft.Maps/accounts/services/spatial/write
True         Microsoft.Maps/accounts/services/turnbyturn/read
True         Microsoft.Maps/accounts/services/elevation/read
True         Microsoft.Maps/accounts/services/dataordering/read
True         Microsoft.Maps/accounts/services/dataordering/write
True         Microsoft.Maps/accounts/services/analytics/read
True         Microsoft.Maps/accounts/services/analytics/delete
True         Microsoft.Maps/accounts/services/analytics/write
             Microsoft.Maps/accounts/creators/write
             Microsoft.Maps/accounts/creators/read
             Microsoft.Maps/accounts/creators/delete
```

Perintah ini mencantumkan operasi yang tersedia untuk Penyedia Sumber Daya Peta.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Maps.Models.Api20210201.IOperationDetail

## CATATAN

ALIAS

## RELATED LINKS

