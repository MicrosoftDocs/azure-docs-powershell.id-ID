---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 2001E040-5551-40C3-81D2-9A8334DE02BF
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5f11e9fb786afdae848dde2c1567e17a4f66cfee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142656352"
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
Tentukan parameter lain untuk membatasi pekerjaan yang didapat cmdlet ini.

Cmdlet ini mengembalikan maksimal 200 pekerjaan.
Jika ada lebih dari 200 pekerjaan, dapatkan sisa pekerjaan dengan menggunakan parameter *Pertama* dan *Lewati* .
Jika Anda menentukan nilai 100 untuk *Lewati* dan 50 untuk *Pertama*, cmdlet ini tidak mengembalikan 100 hasil pertama.
Mengembalikan 50 hasil berikutnya setelah 100 yang dilewatinya.

## EXAMPLES

### Contoh 1: Dapatkan pekerjaan dengan menggunakan ID
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

Perintah ini mendapatkan informasi untuk pekerjaan yang memiliki ID yang ditentukan.

### Contoh 2: Dapatkan pekerjaan dengan menggunakan nama perangkat
```
PS C:\>Get-AzureStorSimpleJob -DeviceName "8600-Bravo 001" -First 2
InstanceId                           Type                         Status                                          DeviceName                                      StartTime                                       Progress                                       
----------                           ----                         ------                                          ----------                                      ---------                                       --------                                       
1997c33f-bfcc-4d08-9aba-28068340a1f9 Backup                       Running                                         8600-Bravo 001                                  4/15/2015 1:30:02 PM                            92                                             
85074062-ef6a-408a-b6c9-2a0904bb99ca Backup                       Completed                                       8600-Bravo 001                                  4/15/2015 1:30:02 PM                            100
```

Perintah ini mendapatkan informasi untuk pekerjaan untuk perangkat bernama 8600-Bravo 001.
Perintah akan mendapatkan dua pekerjaan pertama untuk perangkat tersebut.

### Contoh 3: Dapatkan pekerjaan yang sudah selesai
```
PS C:\>Get-AzureStorSimpleJob -Status "Completed" -Skip 10 -First 2
```

Perintah ini akan menyelesaikan pekerjaan.
Perintah hanya mendapatkan dua pekerjaan pertama setelah melewati sepuluh pekerjaan pertama.

### Contoh 4: Dapatkan pekerjaan pencadangan manual
```
PS C:\>Get-AzureStorSimpleJob -Type "ManualBackup"
```

Perintah ini mendapatkan pekerjaan dari tipe pencadangan manual.

### Contoh 5: Dapatkan pekerjaan di antara waktu yang ditentukan
```
PS C:\>$StartTime = Get-Date -Year 2015 -Month 3 -Day 10
PS C:\> $EndTime = Get-Date -Year 2015 -Month 3 -Day 11 -Hour 12 -Minute 15
PS C:\>Get-AzureStorSimpleJob -DeviceName "Device07" -From $StartTime -To $EndTime
```

Dua perintah pertama membuat objek **DateTime** menggunakan cmdlet Get-Date.
Perintah menyimpan waktu baru dalam variabel $StartTime dan $EndTime.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Date`

Perintah terakhir mendapatkan pekerjaan untuk perangkat bernama Device07 antara waktu yang disimpan di $StartTime dan $EndTime.

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

### -Pertama
Hanya mendapatkan jumlah objek yang ditentukan.
Masukkan jumlah objek yang akan didapatkan.

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
Menentukan tanggal dan waktu mulai untuk pekerjaan yang didapat cmdlet ini.

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
Menentukan ID pekerjaan yang akan didapatkan.

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Mengabaikan jumlah objek yang ditentukan lalu mendapatkan objek yang tersisa.
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

- Menjalankan
- Selesai
- Dibatalkan
- Gagal
- Membatalkan
- SelesaiWithErrors

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

### -Kepada
Menentukan tanggal dan waktu akhir untuk pekerjaan yang didapat cmdlet ini.

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

- Cadangan
- ManualBackup
- Mengembalikan
- CloneWorkflow
- DeviceRestore
- Update
- Paket Dukungan
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda tidak dapat menyalurkan input ke cmdlet ini.

## OUTPUTS

### IList\<DeviceJobDetails\>, DeviceJobDetails
Cmdlet ini mengembalikan daftar objek detail pekerjaan, atau, jika Anda menentukan parameter *InstanceID* , cmdlet ini mengembalikan objek detail pekerjaan tunggal.

## NOTES

## RELATED LINKS

[Stop-AzureStorSimpleJob](./Stop-AzureStorSimpleJob.md)


