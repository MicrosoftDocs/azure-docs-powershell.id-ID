---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 2001E040-5551-40C3-81D2-9A8334DE02BF
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5f11e9fb786afdae848dde2c1567e17a4f66cfee
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420270"
---
# Get-AzureStorSimpleJob

## SYNOPSIS
Mendapatkan pekerjaan StorSimple.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorSimpleJob [-DeviceName <String>] [-InstanceId <String>] [-Status <String>] [-Type <String>]
 [-From <DateTime>] [-To <DateTime>] [-Skip <Int32>] [-First <Int32>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleJob** mendapatkan pekerjaan Azure StorSimple.
Tentukan ID instans untuk mendapatkan pekerjaan tertentu.
Tentukan parameter lain untuk membatasi pekerjaan yang cmdlet ini dapatkan.

Cmdlet ini mengembalikan maksimum 200 pekerjaan.
Jika ada lebih dari 200 pekerjaan, dapatkan pekerjaan tersisa dengan menggunakan *parameter Pertama* *dan* Lewati.
Jika Anda menentukan nilai 100 untuk Lewati dan 50 untuk *Pertama,* cmdlet ini tidak mengembalikan 100 hasil pertama. 
Fungsi akan mengembalikan 50 hasil berikutnya setelah 100 yang dilewati.

## EXAMPLES

### Contoh 1: Mendapatkan pekerjaan menggunakan ID
```
PS C:\>Get-AzureStorSimpleJob -InstanceId "574f47e0-44e9-495c-b8a5-0203c57ebf6d"
BackupPolicy             : 
BackupTimeStamp          : 1/1/0001 12:00:00 AM
BackupType               : CloudSnapshot
DataStats                : Microsoft.WindowsAzure.Management.StorSimple.Models.DataStatistics
Device                   : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
Entity                   : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
ErrorDetails             : {}
HideProgressDetails      : False
InstanceId               : 574f47e0-44e9-495c-b8a5-0203c57ebf6d
IsInstantRestoreComplete : False
IsJobCancellable         : True
JobDetails               : Microsoft.WindowsAzure.Management.StorSimple.Models.JobStatusInfo
Name                     : 26447caf-59bb-41c9-a028-3224d296c7dc
Progress                 : 100
SourceDevice             : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
SourceEntity             : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
SourceVolume             : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
Status                   : Completed
TimeStats                : Microsoft.WindowsAzure.Management.StorSimple.Models.TimeStatistics
Type                     : Backup
Volume                   : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
```

Perintah ini mendapatkan informasi pekerjaan dengan ID tertentu.

### Contoh 2: Mendapatkan pekerjaan menggunakan nama perangkat
```
PS C:\>Get-AzureStorSimpleJob -DeviceName "8600-Bravo 001" -First 2
InstanceId                           Type                         Status                                          DeviceName                                      StartTime                                       Progress                                       
----------                           ----                         ------                                          ----------                                      ---------                                       --------                                       
1997c33f-bfcc-4d08-9aba-28068340a1f9 Backup                       Running                                         8600-Bravo 001                                  4/15/2015 1:30:02 PM                            92                                             
85074062-ef6a-408a-b6c9-2a0904bb99ca Backup                       Completed                                       8600-Bravo 001                                  4/15/2015 1:30:02 PM                            100
```

Perintah ini mendapatkan informasi untuk pekerjaan perangkat bernama 8600-Bravo 001.
Perintah tersebut mendapatkan dua pekerjaan pertama untuk perangkat tersebut.

### Contoh 3: Mendapatkan pekerjaan yang telah selesai
```
PS C:\>Get-AzureStorSimpleJob -Status "Completed" -Skip 10 -First 2
```

Perintah ini akan menyelesaikan pekerjaan.
Perintah hanya mendapatkan dua pekerjaan pertama setelah melewati sepuluh pekerjaan pertama.

### Contoh 4: Mendapatkan pekerjaan pencadangan manual
```
PS C:\>Get-AzureStorSimpleJob -Type "ManualBackup"
```

Perintah ini mendapatkan pekerjaan dari tipe cadangan manual.

### Contoh 5: Mendapatkan pekerjaan di antara waktu tertentu
```
PS C:\>$StartTime = Get-Date -Year 2015 -Month 3 -Day 10
PS C:\> $EndTime = Get-Date -Year 2015 -Month 3 -Day 11 -Hour 12 -Minute 15
PS C:\>Get-AzureStorSimpleJob -DeviceName "Device07" -From $StartTime -To $EndTime
```

Dua perintah pertama membuat **objek DateTime** dengan menggunakan Get-Date cmdlet.
Perintah menyimpan waktu baru dalam variabel $StartTime $EndTime baru.
Untuk informasi selengkapnya, ketik `Get-Help Get-Date` .

Perintah terakhir mendapatkan pekerjaan untuk perangkat bernama Device07 di antara waktu yang disimpan di $StartTime dan $EndTime.

## PARAMETERS

### -DeviceName
Menentukan nama perangkat StorSimple.

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

### -First
Hanya mendapatkan jumlah objek yang ditentukan.
Masukkan jumlah objek yang akan dapatkan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dari
Menentukan tanggal dan waktu mulai untuk pekerjaan yang cmdlet ini dapatkan.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId
Menentukan ID pekerjaan untuk mendapatkan.

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

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### -Lewati
Mengabaikan jumlah objek tertentu lalu mendapatkan objek yang tersisa.
Masukkan jumlah objek yang akan dilewati.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Menentukan status.
Nilai yang dapat diterima untuk parameter ini adalah:

- Berjalan
- Selesai
- Dibatalkan
- Gagal
- Membatalkan
- CompletedWithErrors

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

### -Ke
Menentukan tanggal dan waktu akhir untuk pekerjaan yang cmdlet ini dapatkan.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe pekerjaan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Pencadangan
- ManualBackup
- Pulihkan
- KloningWorkflow
- DeviceRestore
- Perbarui
- SupportPackage
- VirtualApplianceProvisioning

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
Anda tidak dapat pipa input ke cmdlet ini.

## OUTPUTS

### \<DeviceJobDetails\>IList, DeviceJobDetails
Cmdlet ini mengembalikan daftar objek detail pekerjaan, atau, jika Anda menentukan parameter *InstanceID,* maka akan mengembalikan sebuah objek detail pekerjaan tunggal.

## CATATAN

## RELATED LINKS

[Stop-AzureStorSimpleJob](./Stop-AzureStorSimpleJob.md)


