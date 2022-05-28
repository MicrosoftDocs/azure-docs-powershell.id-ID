---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azscheduledqueryrulelogmetrictrigger
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzScheduledQueryRuleLogMetricTrigger.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzScheduledQueryRuleLogMetricTrigger.md
ms.openlocfilehash: 0f87b5052a3004af092f37d963eefe91f958f987
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145563383"
---
# New-AzScheduledQueryRuleLogMetricTrigger

## SYNOPSIS
Membuat objek jenis Pemicu Metrik Log.

## SYNTAX

```
New-AzScheduledQueryRuleLogMetricTrigger -ThresholdOperator <String> -Threshold <Double>
 -MetricTriggerType <String> -MetricColumn <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek jenis Pemicu Metrik Log dan bersifat opsional.
Ini adalah kondisi pemicu untuk aturan kueri metrik, yang akan digunakan saat Anda perlu menyatakan jenis pemberitahuan pengukuran metrik.

## EXAMPLES

### Contoh 1
```powershell
$metricTrigger = New-AzScheduledQueryRuleLogMetricTrigger -ThresholdOperator "GreaterThan" -Threshold 5 -MetricTriggerType "Consecutive" -MetricColumn "Computer"
```

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

### -MetricColumn
Kolom tempat nilai metrik diagregasi.
Input tidak divalidasi. Ini pertama-tama akan divalidasi ketika New-AzScheduledQueryRule akhirnya dipanggil.

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

### -MetricTriggerType
Jenis pemicu metrik.
Input tidak divalidasi. Ini pertama-tama akan divalidasi ketika New-AzScheduledQueryRule akhirnya dipanggil.

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

### -Ambang batas
Nilai ambang batas metrik: Berturut-turut, Total.
Input tidak divalidasi. Ini pertama-tama akan divalidasi ketika New-AzScheduledQueryRule akhirnya dipanggil.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThresholdOperator
Operator ambang batas metrik : GreaterThan, LessThan, Equal.
Input tidak divalidasi. Ini pertama-tama akan divalidasi ketika New-AzScheduledQueryRule akhirnya dipanggil.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSScheduledQueryRuleLogMetricTrigger

## NOTES

## RELATED LINKS
