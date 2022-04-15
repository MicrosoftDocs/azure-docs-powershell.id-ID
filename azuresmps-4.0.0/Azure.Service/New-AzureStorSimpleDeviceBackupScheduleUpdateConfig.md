---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 22C6845E-D7BD-4BBC-B373-394A23488A94
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6a3c2bcfe13108842ffa83b2daf44a9c05b5bbf6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142335055"
---
# New-AzureStorSimpleDeviceBackupScheduleUpdateConfig

## SYNOPSIS
Membuat objek konfigurasi pembaruan jadwal cadangan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorSimpleDeviceBackupScheduleUpdateConfig -Id <String> -BackupType <String> -RecurrenceType <String>
 -RecurrenceValue <Int32> -RetentionCount <Int64> [-StartFromDateTime <String>] [-Enabled <Boolean>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet New-AzureStorSimpleDeviceBackupScheduleUpdateConfig** membuat objek konfigurasi **BackupScheduleUpdateRequest**.
Gunakan objek konfigurasi ini untuk memperbarui kebijakan pencadangan menggunakan cmdlet **Set-AzureStorSimpleDeviceBackupPolicy** .

## EXAMPLES

### Contoh 1: Membuat permintaan pembaruan jadwal
```
PS C:\>New-AzureStorSimpleDeviceBackupScheduleUpdateConfig -Id "147f734d-a31a-4473-8501-6ba38be2cb30" -BackupType CloudSnapshot -RecurrenceType Hourly -RecurrenceValue 1 -RetentionCount 50 -Enabled $True
VERBOSE: ClientRequestId: ef346641-54b4-4273-8898-7f863e7c5b7e_PS


BackupType     : CloudSnapshot
Id             : 147f734d-a31a-4473-8501-6ba38be2cb30
Recurrence     : Microsoft.WindowsAzure.Management.StorSimple.Models.ScheduleRecurrence
RetentionCount : 50
StartTime      : 2014-12-16T00:39:32+05:30
Status         : Enabled
```

Perintah ini membuat permintaan pembaruan jadwal cadangan untuk jadwal yang memiliki ID tertentu.
Permintaannya adalah membuat jadwal cadangan snapshot awan yang berulang setiap jam.
Cadangan disimpan selama 50 hari.
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

### -Difungsikan
Menunjukkan apakah akan mengaktifkan jadwal cadangan.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID instans jadwal pencadangan untuk diperbarui.

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
Menentukan tipe pengulangan untuk jadwal cadangan ini.
Nilai yang valid adalah: 

- Menit
- Setiap jam
- Harian
- Unduhan

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
Parameter ini menggunakan unit yang ditentukan oleh parameter *RecurrenceType* .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### BackupScheduleUpdateRequest
Cmdlet ini mengembalikan objek **BackupScheduleUpdateRequest** yang berisi informasi tentang jadwal cadangan yang diperbarui.

## CATATAN

## RELATED LINKS

[New-AzureStorSimpleDeviceBackupScheduleAddConfig](./New-AzureStorSimpleDeviceBackupScheduleAddConfig.md)

[Set-AzureStorSimpleDeviceBackupPolicy](./Set-AzureStorSimpleDeviceBackupPolicy.md)


