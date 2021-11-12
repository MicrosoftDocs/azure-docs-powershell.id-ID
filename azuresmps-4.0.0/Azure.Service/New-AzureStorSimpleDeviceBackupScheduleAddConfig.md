---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: EE7EC812-640B-4672-B23C-673F912F0EDC
online version: ''
schema: 2.0.0
ms.openlocfilehash: e2c7c0a76da53b2696b4ce5c4375311d228c6d5c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423220"
---
# New-AzureStorSimpleDeviceBackupScheduleAddConfig

## SYNOPSIS
Membuat objek konfigurasi jadwal cadangan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorSimpleDeviceBackupScheduleAddConfig -BackupType <String> -RecurrenceType <String>
 -RecurrenceValue <Int32> -RetentionCount <Int64> [-StartFromDateTime <String>] -Enabled <Boolean>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorSimpleDeviceBackupScheduleAddConfig** membuat **objek konfigurasi BackupScheduleBase.**
Gunakan objek konfigurasi ini untuk membuat kebijakan pencadangan baru dengan menggunakan cmdlet **New-AzureStorSimpleDeviceBackupPolicy.**

## EXAMPLES

### Contoh 1: Membuat objek konfigurasi cadangan
```
PS C:\>New-AzureStorSimpleDeviceBackupScheduleAddConfig -BackupType CloudSnapshot -RecurrenceType Daily -RecurrenceValue 1 -RetentionCount 100 -Enabled $True
VERBOSE: ClientRequestId: 426a79ee-fed3-4d3d-9123-e371f83222b3_PS


BackupType     : CloudSnapshot
Recurrence     : Microsoft.WindowsAzure.Management.StorSimple.Models.ScheduleRecurrence
RetentionCount : 100
StartTime      : 2014-12-16T00:37:19+05:30
Status         : Enabled
```

Perintah ini membuat cadangan objek dasar jadwal untuk pencadangan snapshot awan.
Cadangan terjadi setiap hari, dan cadangan disimpan selama 100 hari.
Jadwal ini diaktifkan dari waktu default, yang merupakan waktu saat ini.

## PARAMETERS

### -BackupType
Menentukan tipe cadangan.
Nilai yang valid adalah: LocalSnapshot dan CloudSnapshot.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Menunjukkan apakah akan mengaktifkan jadwal pencadangan.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrenceType
Menentukan tipe pengulangan untuk jadwal pencadangan ini.
Nilai valid adalah: 

- Menit
- Per jam
- Harian
- Mingguan

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrenceValue
Menentukan seberapa sering membuat cadangan.
Parameter ini menggunakan unit yang ditentukan oleh parameter *RecurrenceType.*

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionCount
Menentukan jumlah hari untuk menyimpan cadangan.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartFromDateTime
Menentukan tanggal untuk mulai membuat cadangan.
Nilai default adalah waktu saat ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### BackupScheduleBase
Cmdlet ini mengembalikan objek **BackupScheduleBase.**
Gunakan **BackupScheduleBase untuk** menyusun kebijakan pencadangan baru.

## CATATAN

## RELATED LINKS

[New-AzureStorSimpleDeviceBackupScheduleUpdateConfig](./New-AzureStorSimpleDeviceBackupScheduleUpdateConfig.md)

[New-AzureStorSimpleDeviceBackupPolicy](./New-AzureStorSimpleDeviceBackupPolicy.md)


