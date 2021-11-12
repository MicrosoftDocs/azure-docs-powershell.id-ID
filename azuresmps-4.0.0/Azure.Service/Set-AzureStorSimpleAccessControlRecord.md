---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 71CFCA9D-198E-481A-BB85-159477F25322
online version: ''
schema: 2.0.0
ms.openlocfilehash: 39fd44c3a57d704402eebdcc3e4ce35a28519d3a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423188"
---
# Set-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Memperbarui IQN dari catatan kontrol akses.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureStorSimpleAccessControlRecord -ACRName <String> -IQNInitiatorName <String> [-WaitForComplete]
 [-NewName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStorSimpleAccessControlRecord** memperbarui nama yang memenuhi syarat iSCSI (IQN) dari catatan kontrol akses yang sudah ada.

## EXAMPLES

### Contoh 1: Memperbarui rekaman kontrol akses
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

Perintah ini memperbarui catatan kontrol akses yang bernama Acr10 untuk inisiator iSCSI bernama IqnUpdated.
Perintah ini menentukan parameter *WaitForComplete,* dan oleh karena itu, perintah akan menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo.**

## PARAMETERS

### -ACRName
Menentukan nama rekaman kontrol akses untuk diubah.

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
Menentukan IQN dari inisiator iSCSI yang menyediakan akses untuk volume cmdlet ini.

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
Menunjukkan bahwa cmdlet ini menunggu hingga operasi selesai sebelum mengembalikan kontrol ke Windows PowerShell baru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### TaskStatusInfo, TaskResponse
Cmdlet ini mengembalikan objek **TaskStatusInfo** jika Anda menentukan parameter *WaitForComplete.*
Jika Anda tidak menentukan parameter itu, parameter itu mengembalikan **objek TaskResponse.**

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleAccessControlRecord](./Get-AzureStorSimpleAccessControlRecord.md)

[New-AzureStorSimpleAccessControlRecord](./New-AzureStorSimpleAccessControlRecord.md)

[Remove-AzureStorSimpleAccessControlRecord](./Remove-AzureStorSimpleAccessControlRecord.md)


