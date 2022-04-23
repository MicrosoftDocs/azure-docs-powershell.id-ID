---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: ED6CDEA3-0A5D-47E6-B9D7-47D1862212DF
online version: ''
schema: 2.0.0
ms.openlocfilehash: b2d81021e56b1bda5b2c4a4256577c407b82a4ef
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143158355"
---
# New-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Membuat catatan kontrol akses.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorSimpleAccessControlRecord -ACRName <String> -IQNInitiatorName <String> [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorSimpleAccessControlRecord** membuat catatan kontrol akses.
Anda dapat menggunakan objek **AccessControlRecord** untuk mengonfigurasi volume.

## EXAMPLES

### Contoh 1: Membuat catatan kontrol Access Controlaccess dan menunggu kontrol resultaccess
```
PS C:\>New-AzureStorSimpleAccessControlRecord -ACRName "Acr10" -IQNInitiatorName "Iqn10" -WaitForComplete
Error      : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
JobId      : 08719243-3a76-43a5-a88b-e5f2b63ed3d9
JobSteps   : {}
Result     : Succeeded
Status     : Completed
TaskResult : Succeeded
StatusCode : OK
RequestId  : e12362c2c06615108ba8436cf85fcd40
```

Perintah ini membuat catatan kontrol akses bernama Acr10 untuk inisiator iSCSI bernama Iqn10.
Perintah ini menentukan parameter *WaitForComplete* , dan oleh karena itu, perintah menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo** .

### Contoh 2: Membuat kontrol Controlaccess Access kontrol recordaccess control
```
PS C:\>New-AzureStorSimpleAccessControlRecord -ACRName "Acr11" -IQNInitiatorName "Iqn11"
VERBOSE: The create job is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
2bd56fbb-4b95-4f2c-b99f-6321231a018d for tracking the job status
```

Perintah ini membuat catatan kontrol akses bernama Acr11 untuk inisiator iSCSI bernama Iqn11.
Perintah ini tidak menentukan parameter *WaitForComplete* , dan oleh karena itu, perintah memulai tugas, lalu mengembalikan objek **TaskResponse** .
Untuk melihat status tugas, gunakan cmdlet **Get-AzureStorSimpleTask** .

## PARAMETERS

### -ACRName
Menentukan nama untuk catatan kontrol akses.

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
Menentukan nama iSCSI yang memenuhi syarat (IQN) dari inisiator iSCSI tempat cmdlet ini menyediakan akses untuk volume.

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

[Hapus-AzureStorSimpleAccessControlRecord](./Remove-AzureStorSimpleAccessControlRecord.md)

[Set-AzureStorSimpleAccessControlRecord](./Set-AzureStorSimpleAccessControlRecord.md)

[Get-AzureStorSimpleJob](./Get-AzureStorSimpleJob.md)


