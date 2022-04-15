---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
Module Name: AzureRM.StreamAnalytics
ms.assetid: 04A6FD47-482C-4EA6-9375-D8B6FD1F2659
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.streamanalytics/get-azurermstreamanalyticsoutput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StreamAnalytics/Commands.StreamAnalytics/help/Get-AzureRmStreamAnalyticsOutput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StreamAnalytics/Commands.StreamAnalytics/help/Get-AzureRmStreamAnalyticsOutput.md
ms.openlocfilehash: c675a8da84e61b659c593cc1f963dd1b07c7f316
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142280375"
---
# Get-AzureRmStreamAnalyticsOutput

## SYNOPSIS
Mendapatkan output yang ditentukan dalam pekerjaan atau output Stream Analytics tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmStreamAnalyticsOutput [-JobName] <String> [[-Name] <String>] [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmStreamAnalyticsOutput** mencantumkan semua output yang ditentukan dalam pekerjaan Stream Analytics tertentu atau mendapatkan informasi tentang output tertentu.

## EXAMPLES

### CONTOH 1: Dapatkan informasi tentang output pekerjaan
```
PS C:\>Get-AzureRmStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob"
```

Perintah ini mengembalikan informasi tentang output yang ditentukan pada pekerjaan StreamingJob.

### CONTOH 2: Dapatkan informasi tentang output pekerjaan tertentu
```
PS C:\>Get-AzureRmStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamingJob" -Name "Output"
```

Perintah ini mengembalikan informasi tentang output bernama Output yang ditentukan pada pekerjaan StreamingJob.

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

### -JobName
Menentukan nama pekerjaan Azure Stream Analytics tempat output Azure Stream Analytics berada.

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

### -Nama
Menentukan nama output Azure Stream Analytics untuk diambil.

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat output Azure Stream Analytics berada.

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

## OUTPUTS

### Microsoft.Azure.Commands.StreamAnalytics.Models.PSOutput

## CATATAN

## RELATED LINKS

[New-AzureRmStreamAnalyticsOutput](./New-AzureRmStreamAnalyticsOutput.md)

[Hapus-AzureRmStreamAnalyticsOutput](./Remove-AzureRmStreamAnalyticsOutput.md)

[Uji-AzureRmStreamAnalyticsOutput](./Test-AzureRmStreamAnalyticsOutput.md)


