---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.dll-Help.xml
Module Name: Az.StreamAnalytics
ms.assetid: ECD0950F-2490-49E2-85E6-5FA2A59364E6
online version: https://docs.microsoft.com/en-us/powershell/module/az.streamanalytics/get-azstreamanalyticsquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/StreamAnalytics/StreamAnalytics/help/Get-AzStreamAnalyticsQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/StreamAnalytics/StreamAnalytics/help/Get-AzStreamAnalyticsQuota.md
ms.openlocfilehash: abce6b39b0dfa77ed4aa815ed9551b3ebff427ef
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132409861"
---
# Get-AzStreamAnalyticsQuota

## SYNOPSIS
Mendapatkan informasi tentang kuota Unit Streaming untuk satu kawasan.

## SINTAKS

```
Get-AzStreamAnalyticsQuota [-Location] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzStreamAnalyticsQuota** mendapatkan informasi tentang kuota Unit Streaming untuk suatu kawasan.

## CONTOH

### CONTOH 1: Dapatkan informasi tentang kuota Unit Streaming untuk suatu kawasan
```
PS C:\>Get-AzStreamAnalyticsQuota -Location "West US"
```

Perintah ini mengembalikan informasi tentang kuota dan penggunaan Unit Streaming di kawasan AS Barat.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan nama lokasi kawasan atau pusat data Azure yang akan mendapatkan informasi kuota Unit Streaming.
http://azure.microsoft.com/en-us/regions/#serviceshttp://azure.microsoft.com/en-us/regions/#servicesLihat daftar kawasan Azure yang didukung.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.StreamAnalytics.Models.PSQuota

## CATATAN

## LINK TERKAIT

[Cmdlet Analitik Azure Stream](./Az.StreamAnalytics.md)


