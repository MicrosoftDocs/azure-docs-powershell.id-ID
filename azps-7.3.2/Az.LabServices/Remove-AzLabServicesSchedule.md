---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/remove-azlabservicesschedule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Remove-AzLabServicesSchedule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Remove-AzLabServicesSchedule.md
ms.openlocfilehash: 43a96b6281819ab20dfd7c2a08bdb7b5394dd285
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142887724"
---
# Remove-AzLabServicesSchedule

## SYNOPSIS
Operasi untuk menghapus sumber daya jadwal.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.labservices/remove-azlabservicesschedule) untuk informasi terbaru.

## SYNTAX

### ResourceId (Default)
```
Remove-AzLabServicesSchedule -ResourceId <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Menghapus
```
Remove-AzLabServicesSchedule -LabName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Jadwal
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
Nama lab yang mengidentifikasinya secara unik di dalamnya berisi akun lab.
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
Nama jadwal yang mengidentifikasinya secara unik di dalam lab.
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
Jalankan perintah secara asinkron

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
Mengembalikan true ketika perintah berhasil

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
Nama ini tidak peka huruf besar kecil.

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

### -Jadwal
Untuk membangun, lihat bagian CATATAN untuk properti SCHEDULE dan membuat tabel hash.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.Schedule

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


JADWAL <Schedule>: 
  - `[Note <String>]`: Catatan untuk jadwal ini.
  - `[RecurrencePatternExpirationDate <DateTime?>]`: Saat pengulangan akan kedaluwarsa. Tanggal ini inklusif.
  - `[RecurrencePatternFrequency <RecurrenceFrequency?>]`: Frekuensi pengulangan.
  - `[RecurrencePatternInterval <Int32?>]`: Interval untuk mengaktifkan jadwal. Misalnya, interval = 2 dan RecurrenceFrequency.Daily akan berjalan setiap 2 hari. Ketika tidak ada interval yang disediakan, interval 1 digunakan.
  - `[RecurrencePatternWeekDay <WeekDay[]>]`: Hari dalam seminggu jadwal berjalan. Digunakan saat Frekuensi diatur ke Mingguan.
  - `[StartAt <DateTime?>]`: Ketika mesin virtual pengguna lab akan dimulai. Offset stempel waktu akan diabaikan dan timeZoneId digunakan sebagai gantinya.
  - `[StopAt <DateTime?>]`: Ketika mesin virtual pengguna lab akan dihentikan. Offset stempel waktu akan diabaikan dan timeZoneId digunakan sebagai gantinya.
  - `[SystemDataCreatedAt <DateTime?>]`: Stempel waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Cap waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir mengubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir mengubah sumber daya.
  - `[TimeZoneId <String>]`: Id zona waktu IANA untuk jadwal.

## RELATED LINKS

