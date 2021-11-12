---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 403AD2BF-5D03-4B48-A635-E08216FFFC0B
online version: ''
schema: 2.0.0
ms.openlocfilehash: f826427cd6ce31e25ef9af7659f45ddee14ae99af8d094771bc71257b907f25e
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417681"
---
# Start-AzureStorSimpleBackupCloneJob

## SYNOPSIS
Memulai pekerjaan yang kloning cadangan pada perangkat.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Kosong (Default)
```
Start-AzureStorSimpleBackupCloneJob -BackupId <String> -Snapshot <Snapshot> -CloneVolumeName <String>
 [-TargetAccessControlRecords <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByName
```
Start-AzureStorSimpleBackupCloneJob -SourceDeviceName <String> -TargetDeviceName <String> -BackupId <String>
 -Snapshot <Snapshot> -CloneVolumeName <String>
 [-TargetAccessControlRecords <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyById
```
Start-AzureStorSimpleBackupCloneJob -SourceDeviceId <String> -TargetDeviceId <String> -BackupId <String>
 -Snapshot <Snapshot> -CloneVolumeName <String>
 [-TargetAccessControlRecords <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureStorSimpleBackupCloneJob** memulai pekerjaan yang kloning cadangan yang sudah ada di perangkat StorSimple.

## EXAMPLES

### Contoh 1: Kloning cadangan ke volume berbeda dengan menggunakan nama perangkat
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "ContosoDev07" -First 1
PS C:\> $Acrs = Get-AzureStorSimpleAccessControlRecord -ACRName "Acr01"
PS C:\> Start-AzureStorSimpleBackupCloneJob -SourceDeviceName "ContosoDev07 -TargetDeviceName "ContosoDev07" -BackupId $Backup.InstanceId -Snapshot $Backup.Snapshots[0] -CloneVolumeName "cloned_volume11" -TargetAccessControlRecords $Acrs
VERBOSE: ClientRequestId: 43d8b4dc-39da-4ec5-92f6-be1f499155e9_PS
VERBOSE: ClientRequestId: be7a73a7-980c-4ba2-82d4-f6a7ee0eac0a_PS
VERBOSE: ClientRequestId: ee02aaae-d366-43d2-a229-8761d6db39f1_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 9b81d9f9-3e31-49be-a8cd-1b1c6afdb744_PS
bd05baee-36d0-48f4-8b1e-8119c4133446
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId bd05baee-36d0-48f4-8b1e-8119c4133446 for tracking the job's status
```

Perintah pertama mendapatkan cadangan pertama untuk perangkat yang bernama ContosoDev07 dengan menggunakan cmdlet **Get-AzureStorSimpleDeviceBackup.**
Perintah menyimpan cadangan tersebut dalam $Backup nilai.

Perintah kedua mendapatkan catatan kontrol akses menggunakan cmdlet **Get-AzureStorSimpleAccessControlRecord.**
Perintah menyimpan hasil di dalam $Acrs variabel.

Perintah terakhir memulai pekerjaan yang kloning cadangan volume tertentu di perangkat ke volume yang berbeda di perangkat yang sama.
Contoh ini menentukan perangkat berdasarkan nama.
Perintah menggunakan nilai yang disimpan di $Backup dan $Acrs.
Perintah mengembalikan ID pekerjaan.

### Contoh 2: Kloning cadangan ke volume berbeda dengan menggunakan ID perangkat
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName ContosoDev07 -First 1
PS C:\> $Acrs = Get-AzureStorSimpleAccessControlRecord -ACRName "Acr01"
PS C:\> Start-AzureStorSimpleBackupCloneJob -SourceDeviceId "be7a73a7-980c-4ba2-82d4-f6a7ee0eacbb" -TargetDeviceId "be7a73a7-980c-4ba2-82d4-f6a7ee0eacbb" -BackupId $Backup.InstanceId -Snapshot $Backup.Snapshots[0] -CloneVolumeName "cloned_volume11" -TargetAccessControlRecords $Acrs
VERBOSE: ClientRequestId: 43d8b4dc-39da-4ec5-92f6-be1f499155e9_PS
VERBOSE: ClientRequestId: be7a73a7-980c-4ba2-82d4-f6a7ee0eac0a_PS
VERBOSE: ClientRequestId: ee02aaae-d366-43d2-a229-8761d6db39f1_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 9b81d9f9-3e31-49be-a8cd-1b1c6afdb744_PS
bd05baee-36d0-48f4-8b1e-8119c4133446
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId bd05baee-36d0-48f4-8b1e-8119c4133446 for tracking the job's status
```

Perintah pertama mendapatkan cadangan pertama untuk perangkat yang bernama ContosoDev07 dengan menggunakan cmdlet **Get-AzureStorSimpleDeviceBackup.**
Perintah menyimpan cadangan tersebut dalam $Backup nilai.

Perintah kedua mendapatkan catatan kontrol akses menggunakan cmdlet **Get-AzureStorSimpleAccessControlRecord.**
Perintah menyimpan hasil di dalam $Acrs variabel.

Perintah terakhir memulai pekerjaan yang kloning cadangan volume tertentu di perangkat ke volume yang berbeda di perangkat yang sama.
Contoh ini menentukan perangkat berdasarkan ID perangkat.
Perintah menggunakan nilai yang disimpan di $Backup dan $Acrs.
Perintah mengembalikan ID pekerjaan.

### Contoh 3: Kloning cadangan ke volume di perangkat berbeda dengan menggunakan nama perangkat
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "ContosoDev07" -First 1
PS C:\> $Acrs = Get-AzureStorSimpleAccessControlRecord -ACRName "Acr01"
PS C:\> Start-AzureStorSimpleBackupCloneJob -SourceDeviceName "ContosoDev07" -TargetDeviceName "ContosoDev12" -BackupId $Backup.InstanceId -Snapshot $Backup.Snapshots[0] -CloneVolumeName "cloned_volume11" -TargetAccessControlRecords $Acrs
VERBOSE: ClientRequestId: 43d8b4dc-39da-4ec5-92f6-be1f499155e9_PS
VERBOSE: ClientRequestId: be7a73a7-980c-4ba2-82d4-f6a7ee0eac0a_PS
VERBOSE: ClientRequestId: ee02aaae-d366-43d2-a229-8761d6db39f1_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 9b81d9f9-3e31-49be-a8cd-1b1c6afdb744_PS
bd05baee-36d0-48f4-8b1e-8119c4133446
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId bd05baee-36d0-48f4-8b1e-8119c4133446 for tracking the job's status
```

Perintah pertama mendapatkan cadangan pertama untuk perangkat yang bernama ContosoDev07 dengan menggunakan cmdlet **Get-AzureStorSimpleDeviceBackup.**
Perintah menyimpan cadangan tersebut dalam $Backup nilai.

Perintah kedua mendapatkan catatan kontrol akses menggunakan cmdlet **Get-AzureStorSimpleAccessControlRecord.**
Perintah menyimpan hasil di dalam $Acrs variabel.

Perintah terakhir memulai pekerjaan yang kloning cadangan volume tertentu di perangkat ke volume di perangkat lain.
Contoh ini menentukan perangkat berdasarkan nama.
Perintah menggunakan nilai yang disimpan di $Backup dan $Acrs.
Perintah mengembalikan ID pekerjaan.

### Contoh 4: Kloning cadangan ke volume berbeda dengan menggunakan nama perangkat dan operator pipeline
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName ContosoDev1 -First 1
PS C:\> Get-AzureStorSimpleAccessControlRecord -ACRName acr1 | Start-AzureStorSimpleBackupCloneJob -SourceDeviceName ContosoDev1 -TargetDeviceName ContosoDev1 -BackupId $backup.InstanceId -Snapshot $backup.Snapshots[0] -CloneVolumeName "cloned_vol1" 
VERBOSE: ClientRequestId: 1183a29d-63a9-408a-9065-032c92d317ee_PS
VERBOSE: ClientRequestId: e195717c-5920-4133-bdf0-c1201ebabf6f_PS
VERBOSE: ClientRequestId: ac16644d-bfd8-4edf-b1ad-f5df4ceb4df7_PS
VERBOSE: ClientRequestId: dcdcab7f-2aaa-496d-8a18-2e7449a70227_PS
VERBOSE: ClientRequestId: 6f92e422-eda9-4087-aefb-2257a49f5beb_PS

Confirm
Are you sure you want to clone the backup with backupId fca748a0-4154-49e0-9550-07fa481cbd2d? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 646b280c-b51c-4812-b5c5-b7ca215f1c90_PS
a747d2dc-2876-474e-aea6-6546b255427e
VERBOSE: The start job is triggered successfully. Please use the command Get-AzureStorSimpleJob -InstanceId a747d2dc-2876-474e-aea6-6546b255427e for tracking the job's status
VERBOSE: Access Control Record with given name acr11 is found!
```

Perintah pertama mendapatkan cadangan pertama untuk perangkat yang bernama ContosoDev07 dengan menggunakan cmdlet **Get-AzureStorSimpleDeviceBackup.**
Perintah menyimpan cadangan tersebut dalam $Backup nilai.

Perintah kedua mendapatkan catatan kontrol akses menggunakan cmdlet **Get-AzureStorSimpleAccessControlRecord.**
Perintah itu menyampaikan hasilnya ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini memulai pekerjaan yang kloning cadangan volume tertentu di perangkat, ke volume berbeda di perangkat yang sama.
Contoh ini menentukan perangkat berdasarkan nama.
Perintah menggunakan nilai yang disimpan di $Backup.
Perintah mengambil nilai parameter *TargetAccessControlRecords* dari saluran.
Perintah mengembalikan ID pekerjaan.

## PARAMETERS

### -BackupId
Menentukan ID instans cadangan untuk kloning.

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

### -KlonVolumeName
Menentukan nama untuk volume kloning baru di perangkat target.

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

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -Snapshot
Menentukan objek snapshot yang dikloning cmdlet ini.

```yaml
Type: Snapshot
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SourceDeviceId
Menentukan ID instans perangkat sumber.
Cmdlet ini kloning kembali dari perangkat sumber.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDeviceName
Menentukan nama perangkat sumber.
Cmdlet ini kloning kembali dari perangkat sumber.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetAccessControlRecords
Menentukan data kontrol akses.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetDeviceId
Menentukan ID instans dari perangkat target.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDeviceName
Menentukan nama perangkat tempat cmdlet kloning cadangan ini.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Snapshot, Daftar AccessControlRecord
Anda bisa pipa **objek Snapshot** atau daftar objek **AccessControlRecord** ke cmdlet ini.

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackup](./Get-AzureStorSimpleDeviceBackup.md)

[Get-AzureStorSimpleAccessControlRecord](./Get-AzureStorSimpleAccessControlRecord.md)


