---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 7EF20FC0-3E2A-4AFC-AC02-9B11C8952DB8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2df8617c292e1f3903b0a9bbe82dd7a3c83d269a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141921453"
---
# Get-AzureStorSimpleDeviceVolumeContainer

## SYNOPSIS
Mendapatkan wadah volume di perangkat.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorSimpleDeviceVolumeContainer -DeviceName <String> [-VolumeContainerName <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** mendapatkan daftar wadah volume di perangkat, atau wadah volume yang memiliki nama tertentu.
Objek yang dikembalikan berisi properti berikut ini: 

- **BandwidthRate**
- **EncryptionKey**
- **InstanceId**
- **Isdefault**
- **IsEncryptionEnabled**
- **Nama**
- **OperationInProgress**
- **Dimiliki**
- **PrimaryStorageAccountCredential**
- **SecretsEncryptionThumbprint**
- **VolumeCount**

## EXAMPLES

### Contoh 1: Dapatkan semua kontainer di perangkat
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "8600-Bravo 001"
InstanceId                           Name                                             IsEncryptionEnabled  Owned BandwidthRate                                    PrimaryStorageAccountCredential                 VolumeCount                                    
----------                           ----                                             -------------------  ----- -------------                                    -------------------------------                 -----------                                    
127135b6-92de-4f53-850d-70e1f9a38cbe Test_Container                                   False                True  0                                                Test_Account                                    6
```

Perintah ini mendapatkan daftar wadah volume di perangkat bernama 8600-Bravo 001.

### Contoh 2: Dapatkan wadah dengan menggunakan namanya
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "Container08"
VERBOSE: ClientRequestId: 8027c66a-869b-4ea3-97a2-e17d98ec751c_PS
VERBOSE: ClientRequestId: 344f9be5-0887-4d37-98ef-e45c557774f1_PS
VERBOSE: ClientRequestId: 14919be5-d6f5-4f81-b7f1-d7fafff2238c_PS


BandwidthRate                   : 256
EncryptionKey                   : 
InstanceId                      : 04ea9aad-7a56-4a50-b195-86061b0a810a
IsDefault                       : False
IsEncryptionEnabled             : False
Name                            : Container03
OperationInProgress             : None
Owned                           : True
PrimaryStorageAccountCredential : Microsoft.WindowsAzure.Management.StorSimple.Models.StorageAccountCredentialResponse
SecretsEncryptionThumbprint     : 
VolumeCount                     : 5

VERBOSE: Volume container with name: Container03 is found.
```

Perintah ini mendapatkan wadah volume bernama Container08 di perangkat bernama Contoso63-AppVm.

## PARAMETERS

### -DeviceName
Menentukan nama perangkat StorSimple.
Cmdlet ini mendapatkan wadah volume dari perangkat yang ditentukan parameter ini.

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

### -VolumeContainerName
Menentukan nama wadah volume yang akan didapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

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

### DataContainer, IList\<DataContainer\>
Cmdlet ini mengembalikan objek **DataContainer** , jika Anda menentukan parameter *VolumeContainerName* .
Jika Anda tidak menentukan parameter tersebut, cmdlet ini mengembalikan objek **IList\<DataContainer\>** .

## CATATAN

## RELATED LINKS

[Baru-AzureStorSimpleDeviceVolumeContainer](./New-AzureStorSimpleDeviceVolumeContainer.md)

[Hapus-AzureStorSimpleDeviceVolumeContainer](./Remove-AzureStorSimpleDeviceVolumeContainer.md)


