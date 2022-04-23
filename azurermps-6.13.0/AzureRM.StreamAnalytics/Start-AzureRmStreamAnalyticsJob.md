---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
Module Name: AzureRM.StreamAnalytics
ms.assetid: B5914F65-CAF8-4647-BA78-49B65DD6D67A
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.streamanalytics/start-azurermstreamanalyticsjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StreamAnalytics/Commands.StreamAnalytics/help/Start-AzureRmStreamAnalyticsJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StreamAnalytics/Commands.StreamAnalytics/help/Start-AzureRmStreamAnalyticsJob.md
ms.openlocfilehash: 20bd934a35fdf0cf907e83f22c8148fdfe5425db
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143212859"
---
# Start-AzureRmStreamAnalyticsJob

## SYNOPSIS
Memulai pekerjaan Stream Analytics.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Start-AzureRmStreamAnalyticsJob [-Name] <String> [[-OutputStartMode] <String>] [[-OutputStartTime] <DateTime>]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureRmStreamAnalyticsJob** secara asinkron menyebarkan dan memulai pekerjaan Stream Analytics di Azure.

## EXAMPLES

### CONTOH 1: Memulai pekerjaan Stream Analytics
```
PS C:\>Start-AzureRmStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -Name "StreamingJob" -OutputStartMode "CustomTime" -OutputStartTime "2014-07-03T01:00Z"
```

Perintah ini memulai pekerjaan StreamingJob dan menentukan bahwa streaming kejadian output harus dimulai pada cap waktu 2014-07-03T01:00Z.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama pekerjaan Azure Stream Analytics untuk memulai.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputStartMode
Menentukan mode mulai untuk pekerjaan tersebut.
Nilai yang valid adalah: 
- JobStartTime - Nilai ini menunjukkan bahwa titik awal streaming kejadian output harus dimulai ketika pekerjaan dimulai.
- CustomTime - Nilai ini menunjukkan bahwa titik awal streaming kejadian output harus dimulai pada waktu kustom yang ditentukan dalam parameter *OutputStartTime* . 
 -- LastOutputEventTime - Nilai ini menunjukkan bahwa titik awal streaming kejadian output harus dimulai dari waktu output kejadian terakhir.
Jika properti tidak ada, defaultnya adalah JobStartTime.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputStartTime
Menentukan waktu mulai output.
Nilai ini adalah stempel waktu yang diformat ISO-8601 yang menunjukkan titik awal aliran kejadian output, atau $Null untuk menunjukkan bahwa streaming kejadian output akan dimulai setiap kali pekerjaan streaming dimulai.
Properti ini harus memiliki nilai jika *OutputStartMode* diatur ke CustomTime.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat pekerjaan Azure Stream Analytics berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.DateTime, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzureRmStreamAnalyticsJob](./Get-AzureRmStreamAnalyticsJob.md)

[New-AzureRmStreamAnalyticsJob](./New-AzureRmStreamAnalyticsJob.md)

[Hapus-AzureRmStreamAnalyticsJob](./Remove-AzureRmStreamAnalyticsJob.md)

[Stop-AzureRmStreamAnalyticsJob](./Stop-AzureRmStreamAnalyticsJob.md)


