---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/get-azstreamanalyticsquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsQuota.md
ms.openlocfilehash: e149b9ecf6f52367b7c1ccb22321882ce29762a7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142754758"
---
# Get-AzStreamAnalyticsQuota

## SYNOPSIS
Mengambil informasi kuota langganan saat ini di kawasan tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.streamanalytics/get-azstreamanalyticsquota) untuk informasi terbaru.

## SYNTAX

```
Get-AzStreamAnalyticsQuota -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengambil informasi kuota langganan saat ini di kawasan tertentu.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang kuota Unit Streaming untuk wilayah
```powershell
PS C:\> Get-AzStreamAnalyticsQuota -Location 'WestCentralUS'

Name              Type
----              ----
StreamingUnits    Microsoft.StreamAnalytics/quotas
StreamingClusters Microsoft.StreamAnalytics/quotas
```

Perintah ini mengembalikan informasi tentang kuota dan penggunaan Unit Streaming di kawasan WestCentralUS.

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
Kawasan tempat untuk mengambil informasi kuota langganan.
Anda dapat mengetahui kawasan mana Azure Stream Analytics didukung di sini: https://azure.microsoft.com/en-us/regions/

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.ISubscriptionQuota

## NOTES

ALIAS

## RELATED LINKS

