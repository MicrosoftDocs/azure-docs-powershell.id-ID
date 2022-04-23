---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 9436E1AB-870F-4717-ABE0-55A90C07F7E4
online version: ''
schema: 2.0.0
ms.openlocfilehash: c76f170a0f2a0fe974d2c3b6aaeca1d320d22a88
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143211311"
---
# Get-AzureStorSimpleDeviceConnectedInitiator

## SYNOPSIS
Dapatkan koneksi iSCSI yang tersedia untuk perangkat StorSimple.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifikasiById
```
Get-AzureStorSimpleDeviceConnectedInitiator -DeviceId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifikasiByName
```
Get-AzureStorSimpleDeviceConnectedInitiator -DeviceName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleDeviceConnectedInitiator** mendapatkan daftar koneksi iSCSI yang tersedia untuk perangkat StorSimple.
Objek koneksi iSCSI yang dikembalikan cmdlet ini berisi properti berikut:

- **AcrInstanceId**
- **AcrName**
- **AllowedVolumeNames**
- **InisiatorAddress**
- **Antarmuka**
- **Iqn**
- **IscsiConnectionId**

Cmdlet ini mendapatkan objek koneksi hanya jika koneksi iSCSI diaktifkan untuk perangkat.
Secara default, koneksi dinonaktifkan.

## EXAMPLES

### Contoh 1: Dapatkan semua koneksi untuk perangkat
```
PS C:\>Get-AzureStorSimpleDeviceConnectedInitiator -DeviceName "Contoso63-AppVm"
VERBOSE: ClientRequestId: bec615b9-79ab-4671-88b0-287adeb6bf68_PS
VERBOSE: ClientRequestId: ef976c58-2660-41c8-aa15-c84e70c9d01c_PS
VERBOSE: ClientRequestId: 9b306b96-8e76-47ed-beda-d3bd2fb2bb82_PS
VERBOSE: ClientRequestId: 0f4fc743-0b60-45da-a45a-27f4b0f32bd2_PS

AcrInstanceId      : 55f24643-ab3a-4098-ade2-aa2b1a3ab18c
AcrName            : Contoso63-AppVm
AllowedVolumeNames : {Policyvolume1_Default}
InitiatorAddress   : 
Interfaces         : {Data0}
Iqn                : iqn10
IscsiConnectionId  : cfc144cb-00f1-44b1-9655-80b431f2161b

VERBOSE: 1 Iscsi Connection found!
```

Perintah ini mendapatkan semua koneksi iSCSI untuk perangkat bernama Contoso63-AppVm.
Perintah ini mengembalikan koneksi hanya jika koneksi diaktifkan untuk perangkat.

## PARAMETERS

### -DeviceId
Menentukan ID instans perangkat StorSimple untuk mendapatkan inisiator iSCSI.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: ID

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Menentukan nama perangkat StorSimple untuk mendapatkan inisiator iSCSI.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Daftar\<IscsiConnection\>
Cmdlet ini mengembalikan objek koneksi iSCSI yang berisi properti berikut: 

- **AcrInstanceId**
- **AcrName**
- **AllowedVolumeNames**
- **InisiatorAddress**
- **Antarmuka**
- **Iqn**
- **IscsiConnectionId**

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleAccessControlRecord](./Get-AzureStorSimpleAccessControlRecord.md)


