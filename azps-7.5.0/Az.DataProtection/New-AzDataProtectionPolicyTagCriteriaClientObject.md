---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionpolicytagcriteriaclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTagCriteriaClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTagCriteriaClientObject.md
ms.openlocfilehash: 610c251bff41669e5a85ff69d18f369b2a84ccb6
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145748836"
---
# New-AzDataProtectionPolicyTagCriteriaClientObject

## SYNOPSIS
Membuat objek kriteria baru

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/new-azdataprotectionpolicytagcriteriaclientobject) untuk informasi terbaru.

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

### MonthlyCriteria
```
New-AzDataProtectionPolicyTagCriteriaClientObject -DaysOfMonth <String[]> [-MonthsOfYear <MonthsOfYear[]>]
 [-ScheduleTimes <DateTime[]>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek kriteria baru

## EXAMPLES

### Contoh 1: Membuat tag dengan kriteria absolut 
```powershell
New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria FirstOfDay
```

```output
ObjectType                  AbsoluteCriterion DaysOfTheWeek MonthsOfYear ScheduleTime WeeksOfTheMonth
----------                  ----------------- ------------- ------------ ------------ ---------------
ScheduleBasedBackupCriteria {FirstOfDay}
```

Perintah ini membuat objek kriteria dengan kriteria absolut.

### Contoh 2: membuat tag dengan kriteria mingguan
```powershell
New-AzDataProtectionPolicyTagCriteriaClientObject -DaysOfWeek @("Sunday", "Monday")
```

```output
ObjectType                  AbsoluteCriterion DaysOfTheWeek    MonthsOfYear ScheduleTime WeeksOfTheMonth
----------                  ----------------- -------------    ------------ ------------ ---------------
ScheduleBasedBackupCriteria                   {Sunday, Monday}
```

Perintah ini membuat objek critetia dengan kriteria mingguan

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
Nilai yang diizinkan adalah 1 hingga 28 dan Terakhir

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
Hari dalam sepekan

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
Jadwalkan waktu.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IScheduleBasedBackupCriteria

## NOTES

ALIAS

## RELATED LINKS

