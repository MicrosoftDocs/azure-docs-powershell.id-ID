---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azdatacollectionrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzDataCollectionRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzDataCollectionRule.md
ms.openlocfilehash: 9ad114e674d6ef39e92159eb3403a3c618ea3bdb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143180927"
---
# New-AzDataCollectionRule

## SYNOPSIS
Membuat aturan pengumpulan data.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.monitor/new-azdatacollectionrule) untuk informasi terbaru.

## SYNTAX

### ByFile (Default)
```
New-AzDataCollectionRule
   -Location <string>
   -ResourceGroupName <string>
   -RuleName <string>
   -RuleFile <string>
   [-Description <string>]
   [-Tag <hashtable>]
   [-DefaultProfile <IAzureContextContainer>]
   [-WhatIf]
   [-Confirm]
   [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDataCollectionRule** membuat aturan pengumpulan data.

Aturan Pengumpulan Data (DCR) menentukan data yang masuk ke Azure Monitor dan menentukan di mana data tersebut harus dikirim atau disimpan. Berikut adalah [artikel gambaran umum DCR](https://docs.microsoft.com/azure/azure-monitor/platform/data-collection-rule-overview) lengkap.

Untuk menggunakan parameter -RuleFile, buat file json yang berisi tiga properti: dataSources, tujuan, dataFlows (lihat Contoh #1)

Anda mungkin menemukan [detail skema](https://docs.microsoft.com/rest/api/monitor/datacollectionrules/create) di sini.

Output DCR yang diserialisasi dengan cmdlet ConvertTo-Json juga didukung (lihat Contoh #2).

## EXAMPLES

### Contoh 1: Membuat aturan pengumpulan data, JSON dari Rest API
```powershell
PS C:\>New-AzDataCollectionRule -Location 'East US 2 EUAP' -ResourceGroupName 'testdcr' `
                                -RuleName 'newDcrEx1' -RuleFile 'C:\samples\dcrEx1.json' `
                                -Description 'Dcr description' `
                                -Tag @{"tag1"="value1"; "tag2"="value2"}

Description       : Dcr description
DataSources       : Microsoft.Azure.Commands.Insights.OutputClasses.PSDataCollectionRuleDataSources
Destinations      : Microsoft.Azure.Commands.Insights.OutputClasses.PSDataCollectionRuleDestinations
DataFlows         : {Microsoft.Azure.Commands.Insights.OutputClasses.PSDataFlow}
ProvisioningState : Succeeded
Etag              : "{etag}"
Id                : /subscriptions/{subId}/resourceGroups/testdcr/providers/Microsoft.Insights/dataCollectionRules/newDcrEx1
Name              : newDcrEx1
Type              : Microsoft.Insights/dataCollectionRules
Location          : East US 2 EUAP
Tags              : {[tag2, value2], [tag1, value1]}

# Note: Content of C:\samples\dcrEx1.json
{
  "properties": {
    "dataSources": {
      "performanceCounters": [
        {
          "streams": [
            "Microsoft-InsightsMetrics"
          ],
          "scheduledTransferPeriod": "PT1M",
          "samplingFrequencyInSeconds": 10,
          "counterSpecifiers": [
            "\\Processor Information(_Total)\\% Processor Time"
          ],
          "name": "perfCounter01"
        }
      ]
    },
    "destinations": {
      "azureMonitorMetrics": {
        "name": "azureMonitorMetrics-default"
      }
    },
    "dataFlows": [
      {
        "streams": [
          "Microsoft-InsightsMetrics"
        ],
        "destinations": [
          "azureMonitorMetrics-default"
        ]
      }
    ]
  }
}
```

Perintah ini membuat aturan pengumpulan data untuk langganan saat ini.

## PARAMETERS

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

### -Lokasi
Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: ByFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: ByFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleName
Nama sumber daya

```yaml
Type: System.String
Parameter Sets: ByFile
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleFile
Jalur file JSON

```yaml
Type: System.String
Parameter Sets: ByFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi
Deskripsi sumber daya

```yaml
Type: System.String
Parameter Sets: ByFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: ByFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Insights.OutputClasses.PSDataCollectionRuleResource

## NOTES

## RELATED LINKS

[Set-AzDataCollectionRule](./Set-AzDataCollectionRule.md)
 [Remove-AzDataCollectionRule](./Remove-AzDataCollectionRule.md)
 [Get-AzDataCollectionRule](./Get-AzDataCollectionRule.md)
 [Update-AzDataCollectionRule](./Update-AzDataCollectionRule.md)
