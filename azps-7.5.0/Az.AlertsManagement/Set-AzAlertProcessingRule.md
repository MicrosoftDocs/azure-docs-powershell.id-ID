---
external help file: Microsoft.Azure.PowerShell.Cmdlets.AlertsManagement.dll-Help.xml
Module Name: Az.AlertsManagement
online version: https://docs.microsoft.com/powershell/module/az.alertsmanagement/set-azactionrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Set-AzAlertProcessingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Set-AzAlertProcessingRule.md
ms.openlocfilehash: d28f1f2318c6d32847d928b201d0c7ad115089e0
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145775532"
---
# Set-AzAlertProcessingRule

## SYNOPSIS
Membuat atau memperbarui aturan pemrosesan pemberitahuan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.alertsmanagement/set-azalertprocessingrule) untuk informasi terbaru.

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
**Set-AzAlertProcessingRule** membuat atau memperbarui aturan pemrosesan pemberitahuan.

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

Cmdlet ini membuat aturan yang menambahkan dua grup tindakan ke semua pemberitahuan Sev0 dan Sev1

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

### -Name
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
Jenis aturan Pemrosesan Pemberitahuan. Nilai yang diizinkan: AddActionGroups, RemoveAllActionGroups.

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

### -Cakupan
Daftar ID sumber daya, Daftar nilai yang dipisahkan koma Aturan akan berlaku untuk pemberitahuan yang diaktifkan pada sumber daya dalam cakupan tersebut

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
Id Grup Tindakan yang akan diberi tahu, Daftar nilai yang dipisahkan koma Diperlukan hanya jika jenis aturan pemrosesan pemberitahuan adalah AddActionGroups.


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

### -Diaktifkan
Tunjukkan apakah aturan pemrosesan pemberitahuan yang diberikan diaktifkan atau dinonaktifkan (default diaktifkan).  Nilai yang diizinkan: False, True.

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
Misalnya
@{"tag1" = "key1";" tag2" = "key2"} Gunakan {} untuk menghapus tag yang ada. 

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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya. Berisi:smartgroups

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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
Equals:/subscriptions/MySubscriptionId/resourceGroups/abvarma/providers/microsoft.insights/metricAlerts/test-mrmc-vm-abvarma

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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
Equals:ARM Name Test1,ARM Name Test2
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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
Contains:Test Alert

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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
Sama dengan:Platform,Analitik Log

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
Format yang diharapkan - tingkat keparahan {\<operation\>:\<comma separated list of values\>}: salah satu <Sev0, Sev1, Sev2, Sev3, Sev4>.
Misalnya
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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
Equals:mySQLDataBaseName

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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
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
Format yang diharapkan - operasi {\<operation\>:\<comma separated list of values\>}: salah satu dari <Equals, NotEquals, Contains, DoesNotContain> Misalnya.
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
Waktu Tanggal Mulai. Format 2022-09-21 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

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
Waktu Tanggal Selesai. Format 2022-09-21 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

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
Daftar nilai pola pengulangan Format yang diharapkan Untuk jenis pengulangan mingguan.
daftar nilai yang dipisahkan koma Misalnya. Senin, Sabtu

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
Daftar nilai pola pengulangan Format yang diharapkan Untuk jenis pengulangan bulanan.
daftar nilai yang dipisahkan koma Misalnya. 1,3,12

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
Waktu Mulai Keakuratan dalam zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan, atau Bulanan.

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
Waktu Mulai Keakuratan dalam zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan, atau Bulanan.

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
Daftar nilai pola pengulangan Format yang diharapkan Untuk jenis pengulangan mingguan.
daftar nilai yang dipisahkan koma Misalnya. Senin, Sabtu

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
Daftar nilai pola pengulangan Format yang diharapkan Untuk jenis pengulangan bulanan.
daftar nilai yang dipisahkan koma Misalnya. 1,3,12

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
Waktu Mulai Ketepatan Ulang di zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

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
Waktu Mulai Ketepatan Ulang di zona waktu parameter ScheduleTimeZone. Format 06:00:00 Harus disebutkan dalam kasus Jadwal Berulang - Harian, Mingguan atau Bulanan.

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


### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSActionRule

## OUTPUTS

### Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSActionRule

## NOTES

## RELATED LINKS
