---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
ms.assetid: 3992E6B5-F794-4C7A-BB59-C8D60E2CD7BC
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/set-azoperationalinsightsdatasource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Set-AzOperationalInsightsDataSource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Set-AzOperationalInsightsDataSource.md
ms.openlocfilehash: 3c2c81562dbd2405ce3a2009e6a0a40a26104cc3
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145660702"
---
# Set-AzOperationalInsightsDataSource

## SYNOPSIS
Memperbarui sumber data.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.operationalinsights/set-azoperationalinsightsdatasource) untuk informasi terbaru.

## SYNTAX

```
Set-AzOperationalInsightsDataSource [-DataSource] <PSDataSource> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzOperationalInsightsDataSource** memperbarui sumber data.

## EXAMPLES
### Contoh 1
```powershell
$datasource = Get-AzOperationalInsightsDataSource -Kind CustomLog -ResourceGroupName testrg -WorkspaceName LogAnalyticsWorkspace
Set-AzOperationalInsightsDataSource -DataSource $datasource
```
```output
Name              : DataSource_CustomLog_Customlog_CL
ResourceGroupName : testrg
WorkspaceName     : LogAnalyticsWorkspace
ResourceId        : /subscriptions/xxxx-xxxx-xxxx-xxxx-xxxx/resourceGroups/testrg/providers/Microsoft.Ope
                    rationalInsights/workspaces/LogAnalyticsWorkspace/datasources/DataSource_CustomLog_Customlog_
                    CL
Kind              : CustomLog
Properties        : {"customLogName":"Customlog_CL","description":"","extractions":[{"extractionName":"TimeGenerated","
                    extractionProperties":{"dateTimeExtraction":{"joinStringRegex":null,"regex":null,"formatString":nul
                    l}},"extractionType":"DateTime"}],"inputs":[{"location":{"fileSystemLocations":{"linuxFileTypeLogPa
                    ths":null,"windowsFileTypeLogPaths":["D:\\logs.txt"]}},"recordDelimiter":{"regexDelimiter":{"matchI
                    ndex":0,"numberdGroup":null,"pattern":"\\n"}}}]}
```
Memperbarui sumber data.
## PARAMETERS

### -Sumber Data
Menentukan sumber data yang diperbarui cmdlet ini.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSDataSource
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataSource

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataSource

## NOTES
* Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, operasional, wawasan

## RELATED LINKS

[Get-AzOperationalInsightsDataSource](./Get-AzOperationalInsightsDataSource.md)

[Remove-AzOperationalInsightsDataSource](./Remove-AzOperationalInsightsDataSource.md)


