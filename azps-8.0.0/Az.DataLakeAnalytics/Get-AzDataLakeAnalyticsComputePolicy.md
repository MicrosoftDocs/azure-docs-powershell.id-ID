---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeAnalytics.dll-Help.xml
Module Name: Az.DataLakeAnalytics
online version: https://docs.microsoft.com/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticscomputepolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsComputePolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsComputePolicy.md
ms.openlocfilehash: 1964aeb80c53e830929d7b4e16cc08e2d1a668ef
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145541504"
---
# Get-AzDataLakeAnalyticsComputePolicy

## SYNOPSIS
Mendapatkan kebijakan komputasi Data Lake Analytics atau daftar kebijakan komputasi.

## SYNTAX

```
Get-AzDataLakeAnalyticsComputePolicy [-ResourceGroupName <String>] [-Account] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Get-AzDataLakeAnalyticsComputePolicy** mendapatkan kebijakan komputasi Data Lake Analytics Azure tertentu atau daftar kebijakan.

## EXAMPLES

### Contoh 1: Mendapatkan kebijakan komputasi yang ditentukan
```powershell
Get-AzDataLakeAnalyticsComputePolicy -Account "contosoadla" -Name myPolicy
```

Perintah ini mendapatkan kebijakan komputasi yang ditentukan dengan nama 'myPolicy' di akun 'contosoadla'.

### Contoh 2: Mendapatkan daftar semua kebijakan komputasi di akun
```powershell
Get-AzDataLakeAnalyticsComputePolicy -AccountName "contosoadla"
```

Perintah ini mendapatkan daftar semua kebijakan komputasi di akun "contosoadla"

## PARAMETERS

### -Akun
Nama akun untuk mendapatkan kebijakan atau kebijakan komputasi.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Name
Nama kebijakan komputasi yang akan didapatkan.

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
Nama grup sumber daya tempat Akun Anda berada.
Opsional dan akan mencoba untuk menemukan jika tidak disediakan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.PSDataLakeAnalyticsComputePolicy

## NOTES

## RELATED LINKS
