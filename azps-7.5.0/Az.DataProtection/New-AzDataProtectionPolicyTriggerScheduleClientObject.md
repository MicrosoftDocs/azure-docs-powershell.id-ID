---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionpolicytriggerscheduleclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTriggerScheduleClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTriggerScheduleClientObject.md
ms.openlocfilehash: c6decc3e17c6e15d627780abc92445721946842a
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145748818"
---
# New-AzDataProtectionPolicyTriggerScheduleClientObject

## SYNOPSIS
Membuat objek Jadwal baru

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/new-azdataprotectionpolicytriggerscheduleclientobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataProtectionPolicyTriggerScheduleClientObject -IntervalCount <Int32> -IntervalType <BackupFrequency>
 -ScheduleDays <DateTime[]> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek Jadwal baru

## EXAMPLES

### Contoh 1: Membuat objek jadwal harian
```powershell
$date = Get-Date
New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays $date -IntervalType Daily -IntervalCount 1
```

```output
R/2021-03-03T12:49:55+05:30/P1D
```

Perintah ini membuat jadwal harian untuk Aturan Azure Backup

### Contoh 2: Membuat objek jadwal per jam
```powershell
$date = Get-Date
New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays $date -IntervalType Hourly -IntervalCount 4
```

```output
R/2021-03-03T12:49:55+05:30/PT4H
```

Perintah ini membuat scheudle per jam untuk Aturan Azure Backup.

## PARAMETERS

### -IntervalCount
Frekuensi pencadangan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntervalType
Freuquency cadangan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.BackupFrequency
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleDays
Hari di mana pencadangan akan dijadwalkan.

```yaml
Type: System.DateTime[]
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

## OUTPUTS

### System.String[]

## NOTES

ALIAS

## RELATED LINKS

