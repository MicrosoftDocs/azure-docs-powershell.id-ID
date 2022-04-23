---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 71CFCA9D-198E-481A-BB85-159477F25322
online version: ''
schema: 2.0.0
ms.openlocfilehash: 39fd44c3a57d704402eebdcc3e4ce35a28519d3a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143103188"
---
# Set-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Memperbarui IQN catatan kontrol akses.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureStorSimpleAccessControlRecord -ACRName <String> -IQNInitiatorName <String> [-WaitForComplete]
 [-NewName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStorSimpleAccessControlRecord** memperbarui nama iSCSI yang memenuhi syarat (IQN) dari catatan kontrol akses yang sudah ada.

## EXAMPLES

### Contoh 1: Memperbarui catatan kontrol akses
```
PS C:\>Set-AzureStorSimpleAccessControlRecord -ACRName "Acr10" -IQNInitiatorName "IqnUpdated" -WaitForComplete
VERBOSE: ClientRequestId: e4766335-f302-40e0-93bf-fad7aa488ae6_PS
VERBOSE: ClientRequestId: cfdbbd67-6ba5-4238-b743-b88f604079b9_PS
VERBOSE: About to run a task to update your Access Control Record! 
VERBOSE: ClientRequestId: d5cf2793-0ab5-40ff-ab6f-43e21bc4c0a4_PS


JobId        : 89502523-52fc-4ce2-b2d4-cb8c6692fb60
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {}

VERBOSE: The job created for your update operation has completed successfully. 
VERBOSE: ClientRequestId: cbd47519-3a3c-4365-b097-0fb7551c48ee_PS
GlobalId            : 
InitiatorName       : IqnUpdated
InstanceId          : 9bcfbc83-e196-4688-9016-827f51515c24
Name                : Acr10
OperationInProgress : None
VolumeCount         : 0
```

Perintah ini memperbarui catatan kontrol akses bernama Acr10 untuk inisiator iSCSI bernama IqnUpdated.
Perintah ini menentukan parameter *WaitForComplete* , dan oleh karena itu, perintah menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo** .

## PARAMETERS

### -ACRName
Menentukan nama catatan kontrol akses untuk diubah.

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

### -IQNInitiatorName
Menentukan IQN inisiator iSCSI tempat cmdlet ini menyediakan akses untuk volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IQN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Menentukan nama baru untuk catatan kontrol akses.

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

### TaskStatusInfo, TaskResponse
Cmdlet ini mengembalikan objek **TaskStatusInfo** jika Anda menentukan parameter *WaitForComplete* .
Jika Anda tidak menentukan parameter tersebut, maka akan mengembalikan objek **TaskResponse** .

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleAccessControlRecord](./Get-AzureStorSimpleAccessControlRecord.md)

[Baru-AzureStorSimpleAccessControlRecord](./New-AzureStorSimpleAccessControlRecord.md)

[Hapus-AzureStorSimpleAccessControlRecord](./Remove-AzureStorSimpleAccessControlRecord.md)


