---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionpolicytagcriteriaclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTagCriteriaClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTagCriteriaClientObject.md
ms.openlocfilehash: a8d06397c2208b462897f474da96a0dfa2cfce11
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136363170"
---
# New-AzDataProtectionPolicyTagCriteriaClientObject

## SYNOPSIS
Membuat objek kriteria baru

## SYNTAX

### ScheduleCriteria (Default)
```
New-AzDataProtectionPolicyTagCriteriaClientObject [-DaysOfWeek <DaysOfWeek[]>]
 [-MonthsOfYear <MonthsOfYear[]>] [-ScheduleTimes <DateTime[]>] [-WeeksOfMonth <WeeksOfMonth[]>]
 [<CommonParameters>]
```

### AbsoluteCriteria
```
New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria <AbsoluteTagCriteria> [<CommonParameters>]
```

### Kriteria Bulanan
```
New-AzDataProtectionPolicyTagCriteriaClientObject -DaysOfMonth <String[]> [-MonthsOfYear <MonthsOfYear[]>]
 [-ScheduleTimes <DateTime[]>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek kriteria baru

## EXAMPLES

### Contoh 1: Buat tag dengan kriteria absolut 
```powershell
PS C:\> New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria FirstOfDay

ObjectType                  AbsoluteCriterion DaysOfTheWeek MonthsOfYear ScheduleTime WeeksOfTheMonth
----------                  ----------------- ------------- ------------ ------------ ---------------
ScheduleBasedBackupCriteria {FirstOfDay}
```

Perintah ini membuat objek kriteria dengan kriteria absolut.

### Contoh 2: membuat tag dengan kriteria mingguan
```powershell
PS C:\> New-AzDataProtectionPolicyTagCriteriaClientObject -DaysOfWeek @("Sunday", "Monday")

ObjectType                  AbsoluteCriterion DaysOfTheWeek    MonthsOfYear ScheduleTime WeeksOfTheMonth
----------                  ----------------- -------------    ------------ ------------ ---------------
ScheduleBasedBackupCriteria                   {Sunday, Monday}
```

Perintah ini membuat objek kriteria dengan kriteria mingguan

## PARAMETERS

### -AbsoluteCriteria
Kriteria absolut

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.AbsoluteTagCriteria
Parameter Sets: AbsoluteCriteria
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfMonth
Hari dalam sebulan.
Nilai yang diperbolehkan adalah dari 1 sampai 28 dan Terakhir

```yaml
Type: System.String[]
Parameter Sets: MonthlyCriteria
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Hari dalam seminggu

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DaysOfWeek[]
Parameter Sets: ScheduleCriteria
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthsOfYear
Bulan dalam setahun.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.MonthsOfYear[]
Parameter Sets: MonthlyCriteria, ScheduleCriteria
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleTimes
Waktu jadwal.

```yaml
Type: System.DateTime[]
Parameter Sets: MonthlyCriteria, ScheduleCriteria
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksOfMonth
Minggu dalam sebulan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.WeeksOfMonth[]
Parameter Sets: ScheduleCriteria
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IScheduleBasedBackupCriteria

## CATATAN

ALIAS

## RELATED LINKS

