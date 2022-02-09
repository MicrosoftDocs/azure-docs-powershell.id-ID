---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/remove-azlabservicesschedule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Remove-AzLabServicesSchedule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Remove-AzLabServicesSchedule.md
ms.openlocfilehash: 7d3aeaf2776f6d42575c9f85877441226ddcd286
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138255595"
---
# Remove-AzLabServicesSchedule

## SYNOPSIS
Operasi untuk menghapus sumber daya jadwal.

## SYNTAX

### ResourceId (Default)
```
Remove-AzLabServicesSchedule -ResourceId <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Hapus
```
Remove-AzLabServicesSchedule -LabName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Jadwalkan
```
Remove-AzLabServicesSchedule -Schedule <Schedule> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk menghapus sumber daya jadwal.

## EXAMPLES

### Contoh 1: Menghapus jadwal dari lab.
```powershell
PS C:\> Remove-AzLabServicesSchedule -ResourceGroupName "Group Name" -LabName "Lab Name" -Name "Schedule Name"

```

Menghapus jadwal dari lab.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LabName
Nama lab yang secara unik mengidentifikasinya di dalam berisi akun lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama jadwal yang secara unik mengidentifikasinya di dalam berisi lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: ScheduleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -PassThru
Mengembalikan true saat perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId


```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Schedule
Untuk membuat, lihat bagian CATATAN untuk properti JADWAL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.Schedule
Parameter Sets: Schedule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.Schedule

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


JADWAL <Schedule>: 
  - `[Note <String>]`: Catatan untuk jadwal ini.
  - `[RecurrencePatternExpirationDate <DateTime?>]`: Ketika pengulangan akan kedaluwarsa. Tanggal ini bersifat inklusif.
  - `[RecurrencePatternFrequency <RecurrenceFrequency?>]`: Frekuensi pengulangan.
  - `[RecurrencePatternInterval <Int32?>]`: Interval untuk menjalankan jadwal sesuai jadwal. Misalnya, interval = 2 dan PengulanganFrekuensi.Daily akan dijalankan setiap 2 hari. Ketika tidak ada interval yang disertakan, interval 1 digunakan.
  - `[RecurrencePatternWeekDay <WeekDay[]>]`: Hari-hari minggu sesuai jadwal berjalan. Digunakan ketika Frekuensi diatur ke Mingguan.
  - `[StartAt <DateTime?>]`: Saat mesin virtual pengguna lab akan dimulai. Offset timestamp akan diabaikan dan timeZoneId digunakan sebagai gantinya.
  - `[StopAt <DateTime?>]`: Saat mesin virtual pengguna lab akan dihentikan. Offset timestamp akan diabaikan dan timeZoneId digunakan sebagai gantinya.
  - `[SystemDataCreatedAt <DateTime?>]`: Timestamp pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Timestamp sumber daya modifikasi terakhir (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir diubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir diubah sumber daya.
  - `[TimeZoneId <String>]`: Id zona waktu IANA untuk jadwal.

## RELATED LINKS

