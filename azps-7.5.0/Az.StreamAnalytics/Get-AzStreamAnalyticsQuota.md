---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/get-azstreamanalyticsquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsQuota.md
ms.openlocfilehash: cbaaddb5fe0e4f08f37ee59f77033e012ef64b51
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145712260"
---
# Get-AzStreamAnalyticsQuota

## SYNOPSIS
Mengambil informasi kuota langganan saat ini di wilayah tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.streamanalytics/get-azstreamanalyticsquota) untuk informasi terbaru.

## SYNTAX

```
Get-AzStreamAnalyticsQuota -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengambil informasi kuota langganan saat ini di wilayah tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang kuota Unit Streaming untuk suatu wilayah
```powershell
Get-AzStreamAnalyticsQuota -Location 'WestCentralUS'
```
```output
Name              Type
----              ----
StreamingUnits    Microsoft.StreamAnalytics/quotas
StreamingClusters Microsoft.StreamAnalytics/quotas
```

Perintah ini mengembalikan informasi tentang kuota dan penggunaan Unit Streaming di wilayah WestCentralUS.

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

### -Lokasi
Wilayah tempat untuk mengambil informasi kuota langganan.
Anda dapat mengetahui wilayah mana yang didukung Azure Stream Analytics di sini: https://azure.microsoft.com/en-us/regions/

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.ISubscriptionQuota

## NOTES

ALIAS

## RELATED LINKS

