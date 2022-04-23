---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 049201C9-590F-47EB-9030-25F80CD8DFA5
online version: ''
schema: 2.0.0
ms.openlocfilehash: 22273f9ce959e5fd446eb47ce391517a50263b85
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143158247"
---
# New-AzureStorSimpleDeviceVolume

## SYNOPSIS
Membuat volume dalam wadah volume tertentu.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorSimpleDeviceVolume -DeviceName <String> -VolumeContainer <DataContainer> -VolumeName <String>
 -VolumeSizeInBytes <Int64>
 -AccessControlRecords <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]>
 -VolumeAppType <AppType> -Online <Boolean> -EnableDefaultBackup <Boolean> -EnableMonitoring <Boolean>
 [-WaitForComplete] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorSimpleDeviceVolume** membuat volume dalam wadah volume tertentu.
Cmdlet ini mengaitkan setiap volume dengan satu atau beberapa catatan kontrol akses.
Untuk mendapatkan objek **AccessControlRecord** , gunakan cmdlet **Get-AzureStorSimpleAccessControlRecord** .
Tentukan nama, ukuran, dan AppType untuk volume.
Juga, tentukan apakah akan membuat volume secara online, apakah akan mengaktifkan cadangan default, dan apakah mengaktifkan pemantauan.

## EXAMPLES

### Contoh 1: Membuat volume
```
PS C:\>$AcrList = Get-AzureStorSimpleAccessControlRecord
PS C:\> Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "VolumeContainer07" | New-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18" -Size 2000000000 -AccessControlRecords $AcrList -VolumeAppType PrimaryVolume -Online $True -EnableDefaultBackup $False -EnableMonitoring $False

VERBOSE: ClientRequestId: a29d1a84-1f81-4f20-9130-7adfe45e41fb_PS
VERBOSE: ClientRequestId: 8fa63df1-3f81-4029-a536-b536a70068ad_PS
VERBOSE: ClientRequestId: 964c5744-8bb1-4f70-beda-95ca4c7f3eb6_PS
VERBOSE: ClientRequestId: f09fff3a-54fa-4a0e-93db-b079260ed2dd_PS
VERBOSE: ClientRequestId: 59aa29e3-8044-411a-adae-b64a2681ffed_PS
VERBOSE: ClientRequestId: 0ffd0297-19be-40fe-a64e-6a2947d831b4_PS
c3b1ad53-7a51-49d7-ae83-94ff1ff3ab90
VERBOSE: The create task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
c3b1ad53-7a51-49d7-ae83-94ff1ff3ab90 for tracking the task's status
VERBOSE: Volume container with name: VolumeContainer07 is found.
```

Perintah pertama mendapatkan catatan kontrol akses dalam konfigurasi layanan StorSimple Manager menggunakan cmdlet **Get-AzureStorSimpleAccessControlRecord** , lalu menyimpannya dalam variabel $AcrList.

Perintah kedua mendapatkan wadah volume bernama VolumeContainer07 untuk perangkat yang bernama Contoso63-AppVm menggunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** .
Perintah melewati kontainer ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet ini menciptakan volume.
Perintah menentukan nama untuk volume, ukuran, dan rekaman kontrol akses yang disimpan di $AcrList.
Perintah ini memulai pekerjaan, lalu mengembalikan objek **TaskResponse** .
Untuk melihat status pekerjaan, gunakan cmdlet **Get-AzureStorSimpleTask** .

### Contoh 2: Membuat volume tanpa kontrol Controlaccess Accessaks kontrolaks kontrol
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "VolumeContainer01" | New-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume22" -Size 2000000000 -AccessControlRecords @() -VolumeAppType PrimaryVolume -Online $True -EnableDefaultBackup $False -EnableMonitoring $False -WaitForComplete
VERBOSE: ClientRequestId: 3f359790-7e1f-48e7-acf8-ecabba850966_PS
VERBOSE: ClientRequestId: 2723ebcf-cd72-47bb-99b5-0c099d45641b_PS
VERBOSE: ClientRequestId: e605091f-dd63-42a7-bda2-24753cbc1f9a_PS
VERBOSE: ClientRequestId: b3fd08c3-67c5-4309-9591-15d92c360469_PS
VERBOSE: ClientRequestId: 15a024a3-b0c9-4f83-9c34-0ed8b95d024b_PS
VERBOSE: ClientRequestId: c13f92f9-aea1-40dd-af80-3affe273adbe_PS


TaskId       : ceef657e-390e-4f7a-aab7-669a29c29e7f
TaskResult   : Succeeded
TaskStatus   : Completed
ErrorCode    : 
ErrorMessage : 
TaskSteps    : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The task created for your create operation has completed successfully. 
VERBOSE: ClientRequestId: 1d79febf-f752-4255-af2d-230d40773bc6_PS
AccessType             : NoAccess
AcrIdList              : {}
AcrList                : {}
AppType                : PrimaryVolume
DataContainer          : Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainer
DataContainerId        : 68b63d15-6aa5-4e69-9f9d-4a0bc607d6e9
InstanceId             : SS-VOL-d73b7eec-76fc-4310-b347-69b160de8cdd
InternalInstanceId     : 
IsBackupEnabled        : False
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
Name                   : Volume22
Online                 : True
OperationInProgress    : None
SizeInBytes            : 2000000000
VSN                    : SS-VOL-d73b7eec-76fc-4310-b347-69b160de8cdd

VERBOSE: Volume container with name: VolumeContainer01 is found.
```

Perintah ini mendapatkan wadah volume bernama VolumeContainer01 untuk perangkat yang bernama Contoso63-AppVm menggunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** .
Perintah melewati kontainer ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet ini menciptakan volume.
Perintah menentukan nama untuk volume, ukuran, dan nilai kosong untuk rekaman kontrol akses.
Perintah ini menentukan parameter *WaitForComplete* , sehingga mengembalikan **TaskStatusInfo** setelah membuat volume.

Karena perintah tidak menentukan rekaman kontrol akses, volume ini tidak dapat diakses.
Anda dapat menambahkan akses, nantinya, dengan menggunakan cmdlet **Set-AzureStorSimpleDeviceVolume** .

## PARAMETERS

### -AccessControlRecords
Menentukan daftar rekaman kontrol akses untuk dikaitkan dengan volume.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.AccessControlRecord]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DeviceName
Menentukan nama perangkat StorSimple tempat untuk membuat volume.

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

### -EnableDefaultBackup
Menentukan apakah akan mengaktifkan cadangan asali untuk volume.

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

### -EnableMonitoring
Menentukan apakah akan mengaktifkan pemantauan untuk volume.

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

### -Online
Menentukan apakah akan membuat volume secara online.

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

### -VolumeAppType
Menentukan apakah akan membuat volume utama atau arsip.
Nilai yang valid adalah: PrimaryVolume dan ArchiveVolume.

```yaml
Type: AppType
Parameter Sets: (All)
Aliases: AppType

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeContainer
Menentukan wadah, sebagai objek **DataContainer** , tempat untuk membuat volume.
Untuk mendapatkan objek **VirtualDisk** , gunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** .

```yaml
Type: DataContainer
Parameter Sets: (All)
Aliases: Container

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeName
Menentukan nama untuk volume baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeSizeInBytes
Menentukan ukuran volume dalam byte.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: SizeInBytes

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

### DataContainer, Daftar\<AccessControlRecord\>
Cmdlet ini menerima objek **DataContainer** dan daftar objek **AccessControlRecord** untuk volume baru.

## OUTPUTS

### TaskStatusInfo
Cmdlet ini mengembalikan objek **TaskStatusInfo** , jika Anda menentukan parameter *WaitForComplete* .

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolume](./Get-AzureStorSimpleDeviceVolume.md)

[Hapus-AzureStorSimpleDeviceVolume](./Remove-AzureStorSimpleDeviceVolume.md)

[Set-AzureStorSimpleDeviceVolume](./Set-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleAccessControlRecord](./Get-AzureStorSimpleAccessControlRecord.md)

[Get-AzureStorSimpleDeviceVolumeContainer](./Get-AzureStorSimpleDeviceVolumeContainer.md)

[Get-AzureStorSimpleJob](./Get-AzureStorSimpleJob.md)


