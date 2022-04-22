---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewTriggerObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewTriggerObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewTriggerObject.md
ms.openlocfilehash: 12551a3f2ccc506d007b336b86611b8a2764dc07
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142868806"
---
# New-AzPurviewTriggerObject

## SYNOPSIS
Buat objek dalam memori untuk Pemicu.

## SYNTAX

```
New-AzPurviewTriggerObject [-IncrementalScanStartTime <DateTime>] [-Interval <Int32>]
 [-RecurrenceEndTime <DateTime>] [-RecurrenceFrequency <TriggerFrequency>] [-RecurrenceInterval <String>]
 [-RecurrenceStartTime <DateTime>] [-RecurrenceTimeZone <String>] [-ScanLevel <ScanLevelType>]
 [-ScheduleAdditionalProperty <IRecurrenceScheduleAdditionalProperties>] [-ScheduleHour <Int32[]>]
 [-ScheduleMinute <Int32[]>] [-ScheduleMonthDay <Int32[]>]
 [-ScheduleMonthlyOccurrence <IRecurrenceScheduleOccurrence[]>] [-ScheduleWeekDay <DaysOfWeek[]>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk Pemicu.

## EXAMPLES

### Contoh 1: Membuat objek pemicu
```powershell
PS C:\> New-AzPurviewTriggerObject -RecurrenceEndTime '7/20/2022 12:00:00 AM' -RecurrenceStartTime '2/17/2022 1:32:00 PM' -Interval 1 -RecurrenceFrequency 'Month' -ScanLevel 'Full' -ScheduleHour $(9) -ScheduleMinute $(0) -ScheduleMonthDay $(10)

CreatedAt                  :
Id                         :
IncrementalScanStartTime   :
Interval                   : 1
LastModifiedAt             :
LastScheduled              :
Name                       :
RecurrenceEndTime          : 7/20/2022 12:00:00 AM
RecurrenceFrequency        : Month
RecurrenceInterval         :
RecurrenceStartTime        : 2/17/2022 1:32:00 PM
RecurrenceTimeZone         :
ResourceGroupName          :
ScanLevel                  : Full
ScheduleAdditionalProperty : {
                             }
ScheduleHour               : {9}
ScheduleMinute             : {0}
ScheduleMonthDay           : {10}
ScheduleMonthlyOccurrence  :
ScheduleWeekDay            :
```

Membuat objek pemicu

## PARAMETERS

### -IncrementalScanStartTime

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interval

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

### -RecurrenceEndTime

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrenceFrequency

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.TriggerFrequency
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrenceInterval

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrenceStartTime

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrenceTimeZone

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanLevel

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.ScanLevelType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleAdditionalProperty
Kamus .\<any\>
Untuk membuat, lihat bagian CATATAN untuk properti SCHEDULEADDITIONALPROPERTY dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IRecurrenceScheduleAdditionalProperties
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleHour

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleMinute

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleMonthDay

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleMonthlyOccurrence
Untuk membuat, lihat bagian CATATAN untuk properti SCHEDULEMONTHLYOCCURRENCE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IRecurrenceScheduleOccurrence[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleWeekDay

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.DaysOfWeek[]
Parameter Sets: (All)
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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.Trigger

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


SCHEDULEADDITIONALPROPERTY <IRecurrenceScheduleAdditionalProperties>: Kamus <any>.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

SCHEDULEMONTHLYOCCURRENCE <IRecurrenceScheduleOccurrence[]>: 
  - `[AdditionalProperty <IRecurrenceScheduleOccurrenceAdditionalProperties>]`: Kamus dari <any>
    - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[Day <DayOfWeek?>]`: 
  - `[Occurrence <Int32?>]`: 

## RELATED LINKS
