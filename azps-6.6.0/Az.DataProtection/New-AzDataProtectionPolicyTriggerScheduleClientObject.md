---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionpolicytriggerscheduleclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTriggerScheduleClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionPolicyTriggerScheduleClientObject.md
ms.openlocfilehash: e580059cc59243af39f4b1e0995bec1044366999
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141958011"
---
# New-AzDataProtectionPolicyTriggerScheduleClientObject

## SYNOPSIS
Membuat objek Jadwal baru

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/new-azdataprotectionpolicytriggerscheduleclientobject) untuk informasi terbaru.

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
PS C:\> $date = get-date
PS C:\> New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays $date -IntervalType Daily -IntervalCount 1

R/2021-03-03T12:49:55+05:30/P1D
```

Perintah ini membuat jadwal harian untuk Aturan Azure Backup

### Contoh 2: Membuat objek jadwal per jam
```powershell
PS C:\> $date = get-date
PS C:\> New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays $date -IntervalType Hourly -IntervalCount 4

R/2021-03-03T12:49:55+05:30/PT4H
```

Perintah ini membuat scheudle per jam untuk Aturan Azure Backup.

## PARAMETERS

### -IntervalCount
Frekuensi cadangan.

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
Hari-hari di mana pencadangan akan dijadwalkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String[]

## CATATAN

ALIAS

## RELATED LINKS

