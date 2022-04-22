---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azscheduledqueryrulelogmetrictrigger
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzScheduledQueryRuleLogMetricTrigger.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzScheduledQueryRuleLogMetricTrigger.md
ms.openlocfilehash: 980032e97891455c54de6eb1d05f2653c52e6839
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142964369"
---
# New-AzScheduledQueryRuleLogMetricTrigger

## SYNOPSIS
Membuat objek dari tipe Pemicu Metrik Log.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.monitor/new-azscheduledqueryrulelogmetrictrigger) untuk informasi terbaru.

## SYNTAX

```
New-AzScheduledQueryRuleLogMetricTrigger -ThresholdOperator <String> -Threshold <Double>
 -MetricTriggerType <String> -MetricColumn <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dari tipe Pemicu Metrik Log dan bersifat opsional.
Ini adalah kondisi pemicu untuk aturan kueri metrik, yang akan digunakan saat Anda perlu menyatakan tipe pengukuran metrik pemberitahuan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $metricTrigger = New-AzScheduledQueryRuleLogMetricTrigger -ThresholdOperator "GreaterThan" -Threshold 5 -MetricTriggerType "Consecutive" -MetricColumn "Computer"
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
Kolom yang nilai metriknya akan diagregasikan.
Input tidak divalidasi. Ini akan divalidasi terlebih dahulu ketika New-AzScheduledQueryRule akhirnya dipanggil.

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
Tipe pemicu metrik.
Input tidak divalidasi. Ini akan divalidasi terlebih dahulu ketika New-AzScheduledQueryRule akhirnya dipanggil.

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
Input tidak divalidasi. Ini akan divalidasi terlebih dahulu ketika New-AzScheduledQueryRule akhirnya dipanggil.

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

### -Ambang BatasOperator
Operator ambang batas metrik : GreaterThan, LessThan, Equal.
Input tidak divalidasi. Ini akan divalidasi terlebih dahulu ketika New-AzScheduledQueryRule akhirnya dipanggil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSScheduledQueryRuleLogMetricTrigger

## NOTES

## RELATED LINKS
