---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azdiagnosticdetailsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzDiagnosticDetailSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzDiagnosticDetailSetting.md
ms.openlocfilehash: 106431db086879c172eb067364e5be28261e0f7c
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145776306"
---
# New-AzDiagnosticDetailSetting

## SYNOPSIS
Membuat Objek PSDiagnosticDetailSetting, jenisnya bisa berupa metrik atau log

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/new-azdiagnosticdetailsetting) untuk informasi terbaru.

## SYNTAX

### LogSettingParameterSet
```
New-AzDiagnosticDetailSetting -Log [-RetentionInDays <Int32>] [-RetentionEnabled] -Category <String>
 [-Enabled] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### MetricSettingParameterSet
```
New-AzDiagnosticDetailSetting -Metric [-RetentionInDays <Int32>] [-RetentionEnabled] -Category <String>
 [-Enabled] [-TimeGrain <TimeSpan>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek PSMetricSettings atau PSLogSettings. Anda bisa mendapatkan kategori dengan menggunakan `Get-AzDiagnosticSettingCategory`.

## EXAMPLES

### Contoh 1
```powershell
$TimeGrain=New-TimeSpan -Days 90
New-AzDiagnosticDetailSetting -Metric -RetentionInDays 1 -RetentionEnabled -Category AllMetrics -Enabled -TimeGrain $TimeGrain
```

```output
TimeGrain       : 90.00:00:00
Category        : AllMetrics
Enabled         : True
RetentionPolicy :
                  Enabled : True
                  Days    : 1
CategoryType    : Metrics
```

Membuat objek PSMetricSettings.

### Contoh 2
```powershell
New-AzDiagnosticDetailSetting -Log -RetentionInDays 1 -RetentionEnabled -Category Audit -Enabled
```

```output
Category Enabled RetentionPolicy               CategoryType
-------- ------- ---------------               ------------
Audit       True …                                     Logs
```

Buat objek PSLogSettings.

## PARAMETERS

### -Kategori
Kategori pengaturan

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

### -Diaktifkan
Aktifkan pengaturan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Log
Untuk membuat pengaturan log

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogSettingParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metrik
Untuk membuat pengaturan metrik

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MetricSettingParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionEnabled
Mengaktifkan kebijakan Retensi

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionInDays
Hari penyimpanan untuk kebijakan penyimpanan

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeGrain
TimeGrain untuk pengaturan metrik

```yaml
Type: System.Nullable`1[System.TimeSpan]
Parameter Sets: MetricSettingParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSDiagnosticDetailSettings

## NOTES

## RELATED LINKS
