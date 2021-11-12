---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeAnalytics.dll-Help.xml
Module Name: Az.DataLakeAnalytics
online version: https://docs.microsoft.com/en-us/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticscomputepolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsComputePolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsComputePolicy.md
ms.openlocfilehash: 56b1a9378914a7fa2220e948b64c357b06f6f4dc
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132411469"
---
# Get-AzDataLakeAnalyticsComputePolicy

## SYNOPSIS
Mendapatkan kebijakan perhitungan Analitik Danau Data atau daftar kebijakan perhitungan.

## SINTAKS

```
Get-AzDataLakeAnalyticsComputePolicy [-ResourceGroupName <String>] [-Account] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
**Get-AzDataLakeAnalyticsComputePolicy** mendapatkan kebijakan perhitungan Analitik Danau Azure Data atau daftar kebijakan tertentu.

## CONTOH

### Contoh 1: Dapatkan kebijakan perhitungan tertentu
```
PS C:\>Get-AzDataLakeAnalyticsComputePolicy -Account "contosoadla" -Name myPolicy
```

Perintah ini mendapatkan kebijakan perhitungan tertentu dengan nama 'myPolicy' dalam akun 'contosoadla'.

### Contoh 2: Mendapatkan daftar semua kebijakan perhitungan di akun
```
PS C:\>Get-AzDataLakeAnalyticsComputePolicy -AccountName "contosoadla"
```

Perintah ini mendapatkan daftar semua kebijakan perhitungan dalam akun "contosoadla"

## PARAMETERS

### -Akun
Nama akun untuk mendapatkan kebijakan perhitungan atau kebijakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Nama kebijakan perhitungan untuk mendapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputePolicyName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat akun Anda berada.
Opsional dan akan berusaha mencari tahu jika tidak diberikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.PSDataLakeAnalyticsComputePolicy

## CATATAN

## LINK TERKAIT
