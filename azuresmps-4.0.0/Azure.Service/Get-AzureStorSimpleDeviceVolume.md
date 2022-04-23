---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 79EE846E-D5BE-4808-BC6F-E3B16A308AB0
online version: ''
schema: 2.0.0
ms.openlocfilehash: abd7d74374df9662b5688f821ecd0b9d5b6abbd4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143158697"
---
# Get-AzureStorSimpleDeviceVolume

## SYNOPSIS
Mendapatkan volume di perangkat.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifiByParentObject
```
Get-AzureStorSimpleDeviceVolume -DeviceName <String> -VolumeContainer <DataContainer>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifikasiByName
```
Get-AzureStorSimpleDeviceVolume -DeviceName <String> -VolumeName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleDeviceVolume** mendapatkan daftar volume untuk wadah volume tertentu, atau volume yang memiliki nama yang ditentukan.
Objek yang dikembalikan berisi properti berikut ini: 

- **AccessType**
- **AcrList**
- **AppType**
- **DataContainer**
- **DataContainerId**
- **InstanceId**
- **IsBackupEnabled**
- **IsDefaultBackupEnabled**
- **IsMonitoringEnabled**
- **Nama**
- **Online**
- **OperationInProgress**
- **SizeInByte**
- **VSN**

## EXAMPLES

### Contoh 1: Mendapatkan volume dalam wadah tertentu
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "Container03" | Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm"
InstanceId             : BA-1503262017214433280-ade42af6-dabb-449d-b66b-4f5d06891d4c
Name                   : Volume 1 Clone
Online                 : True
SizeInBytes            : 3298534883328
AccessType             : ReadWrite
AcrList                : {Windows_XYUSFL718-RV_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : BA-1503262017214433280-ade42af6-dabb-449d-b66b-4f5d06891d4c

InstanceId             : BA-1503262017366008684-cf8bb1a3-21e5-4cfc-ba0d-bfe238d77ebe
Name                   : Volume 3 Clone
Online                 : True
SizeInBytes            : 1717986918400
AccessType             : ReadWrite
AcrList                : {Linux_XYUSFL719_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : BA-1503262017366008684-cf8bb1a3-21e5-4cfc-ba0d-bfe238d77ebe

InstanceId             : SS-VOL-2180be94-36f1-473e-a42b-a3ebd2cdb481
Name                   : Volume 4
Online                 : True
SizeInBytes            : 1610612736000
AccessType             : ReadWrite
AcrList                : {Linux_XYUSFL719_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : SS-VOL-2180be94-36f1-473e-a42b-a3ebd2cdb481
```

Perintah ini mendapatkan wadah volume bernama Container03 di perangkat yang bernama Contoso63-AppVm menggunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** .
Perintah menggunakan operator pipeline untuk meneruskan kontainer tersebut ke cmdlet saat ini.
Cmdlet itu mendapatkan semua volume dalam wadah tersebut untuk perangkat bernama Contoso63-AppVm.

### Contoh 2: Dapatkan volume menggunakan namanya
```
PS C:\>Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18"
InstanceId             : SS-VOL-c75e9636-1dcf-43db-92df-3af1ecf3f18a
Name                   : Volume18
Online                 : True
SizeInBytes            : 2748779069440
AccessType             : ReadWrite
AcrList                : {Windows_XYUSFL718-RV_ACR}
AppType                : Invalid
DataContainerId        : 127135b6-92de-4f53-850d-70e1f9a38cbe
IsBackupEnabled        : True
IsDefaultBackupEnabled : False
IsMonitoringEnabled    : False
VSN                    : SS-VOL-c75e9636-1dcf-43db-92df-3af1ecf3f18a
```

Perintah ini mendapatkan volume bernama Volume18 di perangkat bernama Contoso63-AppVm.

## PARAMETERS

### -DeviceName
Menentukan nama perangkat StorSimple untuk mendapatkan volume.

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

### -VolumeContainer
Menentukan wadah volume, sebagai objek **DataContainer** , yang menyertakan volume yang akan didapatkan.
Untuk mendapatkan **DataContainer**, gunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** .

```yaml
Type: DataContainer
Parameter Sets: IdentifyByParentObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeName
Menentukan nama volume yang akan didapatkan.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### DataContainer
Cmdlet ini menerima objek **DataContainer** yang berisi volume yang akan didapatkan.

## OUTPUTS

### VirtualDisk, IList\<VirtualDisk\>
Cmdlet ini mengembalikan objek **VirtualDisk** jika Anda menentukan parameter *VolumeName* .
Jika Anda menentukan *VolumeContainer*, cmdlet ini mengembalikan objek **IList\<VirtualDisk\>** .

## NOTES

## RELATED LINKS

[New-AzureStorSimpleDeviceVolume](./New-AzureStorSimpleDeviceVolume.md)

[Hapus-AzureStorSimpleDeviceVolume](./Remove-AzureStorSimpleDeviceVolume.md)

[Set-AzureStorSimpleDeviceVolume](./Set-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleDeviceVolumeContainer](./Get-AzureStorSimpleDeviceVolumeContainer.md)


