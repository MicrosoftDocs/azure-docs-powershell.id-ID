---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 71302FB6-7E2B-4972-A743-AB537AC7CD79
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1532e519ddf7f4ca1df0a1813497c21ce818c656
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142916975"
---
# Get-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Mendapatkan catatan kontrol akses dalam konfigurasi layanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorSimpleAccessControlRecord [-ACRName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleAccessControlRecord** mendapatkan catatan kontrol akses dalam konfigurasi layanan StorSimple Manager.
Cmdlet ini mendapatkan semua rekaman atau rekaman bernama.

Catatan kontrol Access adalah wadah parameter inisiator iSCSI.
Parameter ini menentukan inisiator mana yang dapat mengakses volume.
Saat inisiator iSCSI mencoba menyambungkan ke volume, peralatan Anda memeriksa catatan kontrol akses yang ditetapkan ke volume tersebut.
Jika parameter inisiator iSCSI cocok dengan salah satu entri dalam rekaman kontrol akses yang dipetakan ke volume tersebut, inisiator iSCSI dapat tersambung.

## EXAMPLES

### Contoh 1: Dapatkan semua catatan kontrol akses
```
PS C:\>Get-AzureStorSimpleAccessControlRecord
InstanceId                           Name                        InitiatorName               VolumeCount
----------                           ----                        -------------               -----------
01a31aa5-14de-4b77-b926-2842577f540e Windows_XYUSFL718-RV_ACR    iqn.1991-05.com.microsof... 3
071c282d-0cd2-4c5f-b687-48966037ba48 Linux_XYUSFL719_ACR         iqn.1994-05.com.redhat:a... 3
4600eade-71f8-4d04-baec-0e7cf1d1e8fb Windows_XYUSFL720_ACR       iqn.1991-05.com.microsof... 9
d508d6f0-fcda-4624-b223-c0b307d6113e Linux_XYUSFL350_ACR         iqn.1991-05.com.microsof... 9
```

Perintah ini mendapatkan semua catatan kontrol akses.

### Contoh 2: Mendapatkan catatan kontrol akses tertentu
```
PS C:\>Get-AzureStorSimpleAccessControlRecord -ACRName "Acr11"
VERBOSE: ClientRequestId: 61f261c7-acd3-4bcc-922a-ddfd85eb767b_PS
VERBOSE: ClientRequestId: 49c6a4c7-d299-46fd-a553-034c52b47487_PS

GlobalId            : 
InitiatorName       : iqn-contoso63
InstanceId          : 55f24643-ab3a-4098-ade2-aa2b1a3ab18c
Name                : Acr11
OperationInProgress : None
VolumeCount         : 6

VERBOSE: Access Control Record with given name Acr11 is found!
```

Perintah ini mendapatkan catatan kontrol akses bernama Acr11.

## PARAMETERS

### -ACRName
Menentukan nama catatan kontrol akses untuk didapatkan.

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

### AccessControlRecord, IList\<AccessControlRecord\>
Cmdlet ini mengembalikan objek **AccessControlRecord** atau objek **IList\<AccessControlRecord\>** .
Objek **AccessControlRecord** berisi bidang berikut ini: 

- **GlobalId** (**String**) 
- **InisiatorName** (**String**) 
- **InstanceId** (**String**) 
- **Nama** (**String**) 
- **OperationInProgress** (**OperationInProgress**) 
- **VolumeCount** (**int**)

## NOTES

## RELATED LINKS

[Baru-AzureStorSimpleAccessControlRecord](./New-AzureStorSimpleAccessControlRecord.md)

[Hapus-AzureStorSimpleAccessControlRecord](./Remove-AzureStorSimpleAccessControlRecord.md)

[Set-AzureStorSimpleAccessControlRecord](./Set-AzureStorSimpleAccessControlRecord.md)


