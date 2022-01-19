---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azdiagnosticdetailsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzDiagnosticDetailSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzDiagnosticDetailSetting.md
ms.openlocfilehash: a1cc6d975aad5c04f0f00cc32e1352b372ab1442
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136214293"
---
# New-AzDiagnosticDetailSetting

## SYNOPSIS
Buat Objek PSDiagnosticDetailSetting, tipe bisa metrik atau log

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
Membuat objek PSMetricSettings atau PSLogSettings. Anda bisa mendapatkan kategori dengan menggunakan `Get-AzDiagnosticSettingCategory` .

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $TimeGrain=New-TimeSpan -Days 90
PS C:\> New-AzDiagnosticDetailSetting -Metric -RetentionInDays 1 -RetentionEnabled -Category AllMetrics -Enabled -TimeGrain $TimeGrain
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
PS C:\> New-AzDiagnosticDetailSetting -Log -RetentionInDays 1 -RetentionEnabled -Category Audit -Enabled
Category Enabled RetentionPolicy               CategoryType
-------- ------- ---------------               ------------
Audit       True …                                     Logs
```

Membuat objek PSLogSettings.

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

### -Enabled
Mengaktifkan pengaturan

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

### -Metric
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
Mengaktifkan kebijakan Penyimpanan

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSDiagnosticDetailSettings

## CATATAN

## RELATED LINKS
