---
external help file: Microsoft.Azure.PowerShell.Cmdlets.AlertsManagement.dll-Help.xml
Module Name: Az.AlertsManagement
online version: https://docs.microsoft.com/powershell/module/az.alertsmanagement/set-azactionrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Set-AzAlertProcessingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Set-AzAlertProcessingRule.md
ms.openlocfilehash: 4e469a570915550c8d7409e11ecea24e3630b8ea
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142688608"
---
# Set-AzAlertProcessingRule

## SYNOPSIS
Membuat atau memperbarui aturan pemrosesan pemberitahuan.

## SYNTAX

### BySimplifiedFormatSuppressionAlertProcessingRule (Default)
```
Set-AzAlertProcessingRule -ResourceGroupName <String> -Name <String> [-Description <String>] -AlertProcessingRuleRuleType <String> 
 -Scope <System.Collections.Generic.List`1[System.String]> -Enabled <String> [-Tag <Hashtable>] 
 [-FilterSeverity <String>] [-FilterMonitorService <String>] [-FilterMonitorCondition <String>] [-FilterTargetResourceType <String>] 
 [-FilterTargetResource <String>] [-FilterTargetResourceGroup <String>] [-FilterAlertRuleId <String>] [-FilterAlertRuleNam <String>]
 [-FilterDescription <String>] [-FilterAlertContext <String>] [-FilterSignalType <String>]
 [-ScheduleStartDateTime <String>] [-ScheduleEndDateTime <String>] [-ScheduleTimeZone <String>]
 [-ScheduleReccurenceType <String>] [-ScheduleReccurenceDaysOfWeek <String>] [-ScheduleReccurenceDaysOfMonth <String>] [-ScheduleReccurenceStartTime <String>]  
 [-ScheduleReccurenceEndTime <String>]
 [-ScheduleReccurence2Type <String>] [-ScheduleReccurence2DaysOfWeek <String>] [-ScheduleReccurence2DaysOfMonth <String>] [-ScheduleReccurence2StartTime <String>]
  [-ScheduleReccurence2EndTime <String>] 
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySimplifiedFormatActionGroupAlertProcessingRule 
```
Set-AzAlertProcessingRule -ResourceGroupName <String> -Name <String> [-Description <String>] -AlertProcessingRuleRuleType <String> 
 -Scope <System.Collections.Generic.List`1[System.String]> -Enabled <String> [-Tag <Hashtable>] 
 [-FilterSeverity <String>] [-FilterMonitorService <String>] [-FilterMonitorCondition <String>] [-FilterTargetResourceType <String>] 
 [-FilterTargetResource <String>] [-FilterTargetResourceGroup <String>] [-FilterAlertRuleId <String>] [-FilterAlertRuleName <String>]
 [-FilterDescription <String>] [-FilterAlertContext <String>] [-FilterSignalType <String>]
 [-ScheduleStartDateTime <String>] [-ScheduleEndDateTime <String>] [-ScheduleTimeZone <String>]
 [-ScheduleReccurenceType <String>] [-ScheduleReccurenceDaysOfWeek <String>] [-ScheduleReccurenceDaysOfMonth <String>] [-ScheduleReccurenceStartTime <String>]
 [-ScheduleReccurenceEndTime <String>]
 [-ScheduleReccurence2Type <String>] [-ScheduleReccurence2DaysOfWeek <String>] [-ScheduleReccurence2DaysOfMonth <String>] [-ScheduleReccurence2StartTime <String>]
 [-ScheduleReccurence2EndTime <String>] 
 -ActionGroupId <String> 
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Set-AzAlertProcessingRule -InputObject <PSAlertProcessingRule> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Set-AzAlertProcessingRule** membuat atau memperbarui aturan pemrosesan peringatan.

## EXAMPLES

### Contoh 1
```powershell
Set-AzAlertProcessingRule -ResourceGroupName "test-rg" -Name "AddActionGroupToSubscription" -Scope "/subscriptions/MySubscriptionId" -Description "Add ActionGroup1 to all alerts in the subscription" -Enabled "True" -AlertProcessingRuleType "AddActionGroups" -ActionGroupId "/subscriptions/MySubscriptionId/resourcegroups/MyResourceGroup1/providers/microsoft.insights/actiongroups/ActionGroup1" 
```

Cmdlet ini membuat aturan pemrosesan pemberitahuan yang menambahkan grup tindakan ke semua pemberitahuan dalam grup sumber daya.

### Contoh 2
```powershell
Set-AzAlertProcessingRule -ResourceGroupName "test-rg" -Name "AddActionGroupsBySeverity" -Scope "/subscriptions/MySubscriptionId" -Description "Add AGId1 and AGId2 to all Sev0 and Sev1 alerts in these resourceGroups" -Enabled "True" -AlertProcessingRuleType "AddActionGroups" -ActionGroupId "/subscriptions/MySubscriptionId/resourcegroups/MyResourceGroup1/providers/microsoft.insights/actiongroups/ActionGroup1,
/subscriptions/MySubscriptionId/resourceGroups/MyResourceGroup2/providers/microsoft.insights/actionGroups/MyActionGroup2" -MonitorServiceCondition "Equals:Sev0,Sev1"
```

Cmdlet ini membuat aturan yang menambahkan dua grup tindakan ke semua peringatan Sev0 dan Sev1

## PARAMETERS

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Aturan Pemrosesan Pemberitahuan

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi
Deskripsi Aturan Pemrosesan Pemberitahuan

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlertProcessingRuleType
Tipe aturan Pemrosesan Pemberitahuan. Nilai yang diperbolehkan: AddActionGroups, RemoveAllActionGroups.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Daftar ID sumber daya, Daftar nilai yang dipisahkan koma Aturan akan berlaku untuk pemberitahuan yang diterapkan pada sumber daya dalam lingkup tersebut

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActionGroupId
Id Grup Tindakan yang akan diberi tahu, Koma memisahkan daftar nilai Diperlukan hanya jika tipe aturan pemrosesan pemberitahuan adalah AddActionGroups.


```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Difungsikan
Menunjukkan apakah aturan pemrosesan pemberitahuan yang diberikan diaktifkan atau dinonaktifkan (default diaktifkan).  Nilai yang diperbolehkan: False, True.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag aturan Pemrosesan Pemberitahuan.
Misalnya.
@{"tag1" = "key1";" tag2" = "key2"} Gunakan {} untuk menghapus tag yang sudah ada. 

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterAlertContext
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya. Berisi:smartgroups

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterAlertRuleId
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
Sama dengan:/subscriptions/MySubscriptionId/resourceGroups/abvarma/providers/microsoft.insights/metricAlerts/test-mrmc-vm-abvarma

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterAlertRuleName
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
Sama dengan:ARM Name Test1,ARM Name Test2
```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterDescription
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
Berisi:Peringatan Uji

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterMonitorCondition
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
NotEquals:Resolved

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterMonitorService
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
Sama dengan:Platform,Log Analytics

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterSeverity
Format yang diharapkan - {\<operation\>:\<comma separated list of values\>} keparahan: salah satu <Sev0, Sev1, Sev2, Sev3, Sev4>.
Misalnya.
Sama dengan:Sev0,Sev1

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterTargetResource
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
Sama dengan:mySQLDataBaseName

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterTargetResourceType
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
Berisi:Virtual Machines,akun Storage

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterTargetResourceGroup
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
NotEquals:/subscriptions/\<subscriptionID\>/resourceGroups/test

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterSignalType
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Sama Dengan, NotEquals, Berisi, DoesNotContain> Untuk misalnya.
Sama dengan:Metrik

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupActionRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleStartDateTime
Waktu Mulai Tanggal. Format 2022-09-21 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleEndDateTime
Waktu Tanggal Berakhir. Format 2022-09-21 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -ScheduleTimeZone
Jadwalkan zona waktu.  Default: UTC.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurenceType
Menentukan kapan aturan pemrosesan harus diterapkan.
Nilai yang diizinkan: Harian, Bulanan, Mingguan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurenceDaysOfWeek
Daftar nilai pola pengulangan Format yang diharapkan Untuk tipe pengulangan mingguan.
daftar nilai yang dipisahkan koma Untuk misalnya. Senin,Sabtu

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurenceDaysOfMonth
Daftar nilai pola pengulangan Format yang diharapkan Untuk tipe pengulangan bulanan.
daftar nilai yang dipisahkan koma Untuk misalnya. 1,3,12

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurenceStartTime
Waktu Mulai Pengulangan dalam zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurenceEndTime
Waktu Mulai Pengulangan dalam zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurence2Type
Menentukan kapan aturan pemrosesan harus diterapkan.
Nilai yang diizinkan: Harian, Bulanan, Mingguan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurence2DaysOfWeek
Daftar nilai pola pengulangan Format yang diharapkan Untuk tipe pengulangan mingguan.
daftar nilai yang dipisahkan koma Untuk misalnya. Senin,Sabtu

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurence2DaysOfMonth
Daftar nilai pola pengulangan Format yang diharapkan Untuk tipe pengulangan bulanan.
daftar nilai yang dipisahkan koma Untuk misalnya. 1,3,12

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurence2StartTime
Waktu Mulai Pengulangan dalam zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleReccurence2EndTime
Waktu Mulai Pengulangan dalam zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

```yaml
Type: System.String
Parameter Sets: BySimplifiedFormatActionGroupAlertProcessingRule, BySimplifiedFormatSuppressionAlertProcessingRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Sumber daya aturan pemrosesan pemberitahuan

```yaml
Type: Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSAlertProcessingRule
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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


### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSActionRule

## OUTPUTS

### Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSActionRule

## NOTES

## RELATED LINKS
