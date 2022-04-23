---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: EFAE7117-9B8B-4CB9-B4D9-3F08DCE1816E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 11654814dca5869be3902409003e1e9bb89acd6e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143158336"
---
# New-AzureStorSimpleDeviceBackupPolicy

## SYNOPSIS
Membuat kebijakan cadangan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorSimpleDeviceBackupPolicy -DeviceName <String> -BackupPolicyName <String>
 -BackupSchedulesToAdd <PSObject[]> -VolumeIdsToAdd <PSObject[]> [-WaitForComplete] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorSimpleDeviceBackupPolicy** membuat kebijakan cadangan.
Kebijakan cadangan berisi satu atau beberapa jadwal cadangan yang dapat berjalan pada satu atau beberapa volume.
Untuk membuat jadwal cadangan, gunakan cmdlet **New-AzureStorSimpleDeviceBackupScheduleAddConfig** .

## EXAMPLES

### Contoh 1: Membuat kebijakan cadangan
```
PS C:\>$Schedule01 = New-AzureStorSimpleDeviceBackupScheduleAddConfig -BackupType LocalSnapshot -RecurrenceType Daily -RecurrenceValue 10 -RetentionCount 5 -Enabled $True
PS C:\> $Schedule02 = New-AzureStorSimpleDeviceBackupScheduleAddConfig -BackupType CloudSnapshot -RecurrenceType Hourly -RecurrenceValue 1 -RetentionCount 5 -Enabled $True
PS C:\> $ScheduleArray = @()
PS C:\> $ScheduleArray += $Schedule01
PS C:\> $ScheduleArray += $Schedule02
PS C:\> $DeviceContainer = Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm"
PS C:\> $Volume = $(Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeContainer $DeviceContainer[0])
PS C:\> $VolumeArray = @()
PS C:\> $VolumeArray += $Volume[0].InstanceId
PS C:\> New-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyName "GeneralPolicy07" -BackupSchedulesToAdd $ScheduleArray -VolumeIdsToAdd $VolumeArray
VERBOSE: ClientRequestId: e9d6771e-c323-47b9-b424-cb98f8ed0273_PS
VERBOSE: ClientRequestId: db0e7c86-d0d2-4a5a-b1cb-182494cba027_PS
VERBOSE: ClientRequestId: 77708dfd-a386-4999-b7ed-5d53e288ae83_PS


JobId        : d4ce5340-d5d1-4471-9cc8-013193f021b3
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, 
               Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, 
               Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The job created for your add operation has completed successfully. 
VERBOSE: ClientRequestId: bbf7e9b9-b493-40b3-8348-f15bcfc4da8a_PS
BackupSchedules          : {36d21096-bbd1-47b7-91b5-40ad1792d992, 505fc91f-deb5-4dca-bfcb-98c20b75ebcc}
Volumes                  : {volume03}
BackupPolicyCreationType : BySaaS
LastBackup               : 01-01-2010 05:30:00
NextBackup               : 16-12-2014 01:13:43
SchedulesCount           : 2
SSMHostName              : 
VolumesCount             : 1
InstanceId               : 8799c2f0-8850-4e91-aa23-ee18c67da8bd
Name                     : GeneralPolicy07
OperationInProgress      : None
```

Perintah pertama membuat objek konfigurasi jadwal cadangan menggunakan cmdlet **New-AzureStorSimpleDeviceBackupScheduleAddConfig** , lalu menyimpan objek tersebut dalam variabel $Schedule 01.

Perintah kedua membuat objek konfigurasi cadangan lain menggunakan **New-AzureStorSimpleDeviceBackupScheduleAddConfig**, lalu menyimpan objek tersebut dalam variabel $Schedule 02.

Perintah ketiga membuat variabel array kosong, bernama $ScheduleArray.
Dua perintah berikutnya menambahkan objek yang dibuat dalam dua perintah pertama ke $ScheduleArray.

Perintah keenam mendapatkan wadah volume untuk perangkat yang bernama Contoso63-AppVm menggunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** , lalu menyimpan objek kontainer tersebut dalam variabel $DeviceContainer.

Perintah ketujuh mendapatkan volume untuk wadah volume yang disimpan di anggota pertama $DeviceContainer menggunakan cmdlet **Get-AzureStorSimpleDeviceVolume** , lalu menyimpan volume tersebut dalam variabel $Volume.

Perintah kedelapan membuat variabel array kosong, bernama $VolumeArray.
Perintah berikutnya menambahkan ID volume ke $VolumeArray.
Nilai ini mengidentifikasi volume, disimpan di $Volume, tempat kebijakan cadangan berjalan.
Anda dapat menambahkan ID volume tambahan ke $VolumeArray.

Perintah akhir membuat kebijakan cadangan bernama GeneralPolicy07 untuk perangkat bernama Contoso63-AppVm.
Perintah menentukan jadwal objek konfigurasi yang disimpan di $ScheduleArray.
Perintah menentukan volume atau volume yang digunakan untuk menerapkan kebijakan dalam $VolumeArray.
Anda dapat memverifikasi kebijakan cadangan menggunakan cmdlet **Get-AzureStorSimpleDeviceBackupPolicy** .

## PARAMETERS

### -BackupPolicyName
Menentukan nama kebijakan cadangan.

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

### -BackupSchedulesToAdd
Menentukan array objek **BackupScheduleBase** untuk ditambahkan ke kebijakan.
Setiap objek mewakili jadwal.
Kebijakan cadangan berisi satu atau beberapa jadwal.
Untuk mendapatkan objek **BackupScheduleBase** , gunakan cmdlet **New-AzureStorSimpleDeviceBackupScheduleAddConfig** .

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Menentukan nama perangkat StorSimple untuk membuat kebijakan cadangan.

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

### -VolumeIdsToAdd
Menentukan array ID volume untuk ditambahkan ke kebijakan cadangan.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForComplete
Menunjukkan bahwa cmdlet ini menunggu operasi selesai sebelum mengembalikan kontrol ke konsol Windows PowerShell.

```yaml
Type: SwitchParameter
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

### BackupPolicy
Cmdlet ini mengembalikan objek **BackupPolicy** yang berisi jadwal dan volume baru.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackupPolicy](./Get-AzureStorSimpleDeviceBackupPolicy.md)

[Get-AzureStorSimpleDeviceVolume](./Get-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleDeviceVolumeContainer](./Get-AzureStorSimpleDeviceVolumeContainer.md)

[Hapus-AzureStorSimpleDeviceBackupPolicy](./Remove-AzureStorSimpleDeviceBackupPolicy.md)

[Set-AzureStorSimpleDeviceBackupPolicy](./Set-AzureStorSimpleDeviceBackupPolicy.md)

[New-AzureStorSimpleDeviceBackupScheduleAddConfig](./New-AzureStorSimpleDeviceBackupScheduleAddConfig.md)


