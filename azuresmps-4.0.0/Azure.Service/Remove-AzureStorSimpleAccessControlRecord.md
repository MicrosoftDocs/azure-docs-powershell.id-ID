---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: F92D18AC-B716-42CA-9C2D-1AB5A599F73E
online version: ''
schema: 2.0.0
ms.openlocfilehash: d02683982b2daf4fbc68e4c941ff19a05548592c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141772054"
---
# Remove-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Menghapus catatan kontrol akses dari konfigurasi layanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifikasiByName
```
Remove-AzureStorSimpleAccessControlRecord -ACRName <String> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifikasiByObject
```
Remove-AzureStorSimpleAccessControlRecord -ACR <AccessControlRecord> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureStorSimpleAccessControlRecord** menghapus catatan kontrol akses dari konfigurasi layanan.

## EXAMPLES

### Contoh 1: Menghapus kontrol Access Controlaccess kontrol recordaccess control
```
PS C:\>Remove-AzureStorSimpleAccessControlRecord -ACRName "Acr10" -WaitForComplete -Force
VERBOSE: ClientRequestId: 574aeb7f-fbc9-46d5-bc68-1bfe4487bd8b_PS
VERBOSE: ClientRequestId: 985afe84-ef95-47cb-8c8f-df094530334b_PS
VERBOSE: About to run a job to remove your ACR! 
VERBOSE: ClientRequestId: 7eb7e1a0-2288-44da-b64c-5bf86a6b9aaf_PS


JobId        : f7934db5-8363-4152-b38e-b9a5d91f97b9
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {}

VERBOSE: The job created for your delete operation has completed successfully.
```

Perintah ini menghapus catatan kontrol akses bernama Acr10.
Perintah ini menentukan parameter *WaitForComplete* , dan oleh karena itu, perintah menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo** .

### Contoh 2: Menghapus rekaman kontrol Controlaccess Access dengan menggunakan kontrol controlaccess Controlaccess PipelineAccess
```
PS C:\>Get-AzureStorSimpleAccessControlRecord -ACRName "Acr10" | Remove-AzureStorSimpleAccessControlRecord -Force 
VERBOSE: ClientRequestId: ff8d8bd6-4c92-4ab6-8fde-e9344a253da3_PS
VERBOSE: ClientRequestId: f71c74f3-33b9-40d1-b8d5-12363e98412f_PS
VERBOSE: ClientRequestId: d5d809d0-ec22-4e45-97ee-a56edc41e503_PS
VERBOSE: About to create a job to remove your ACR! 
VERBOSE: ClientRequestId: 6ffa6bc8-37b3-49ff-bafc-721b360f09cb_PS
294a0208-a43f-4d80-b824-2319cd77c5e6
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
294a0208-a43f-4d80-b824-2319cd77c5e6 for tracking the task's status
```

Perintah ini menggunakan **Get-AzureStorSimpleAccessControlRecord** untuk mendapatkan **AccessControlRecord** bernama Acr10, lalu mengirimkan objek tersebut ke cmdlet saat ini menggunakan operator saluran.
Perintah memulai operasi yang menghapus objek **AccessControlRecord** , lalu mengembalikan objek **TaskResponse** .
Untuk melihat status tugas, gunakan cmdlet **Get-AzureStorSimpleTask** .

## PARAMETERS

### -ACR
Menentukan objek **AccessControlRecord** untuk dihapus.
Untuk mendapatkan objek **AccessControlRecord** , gunakan cmdlet **Get-AzureStorSimpleAccessControlRecord** .

```yaml
Type: AccessControlRecord
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ACRName
Menentukan nama catatan kontrol akses untuk dihapus.

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

### -Paksa
Menunjukkan bahwa cmdlet ini tidak meminta konfirmasi kepada Anda.

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

### AccessControlRecord
Cmdlet ini menerima objek **AccessControlRecord** .
Objek **AccessControlRecord** berisi bidang berikut ini: 

- **GlobalId** (**String**) 
- **InisiatorName** (**String**) 
- **InstanceId** (**String**) 
- **Nama** (**String**) 
- **OperationInProgress** (**OperationInProgress**) 
- **VolumeCount** (**int**)

## OUTPUTS

### TaskStatusInfo, TaskResponse
Cmdlet ini mengembalikan objek **TaskStatusInfo** jika Anda menentukan parameter *WaitForComplete* .
Jika Anda tidak menentukan parameter tersebut, maka akan mengembalikan objek **TaskResponse** .

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleAccessControlRecord](./Get-AzureStorSimpleAccessControlRecord.md)

[Baru-AzureStorSimpleAccessControlRecord](./New-AzureStorSimpleAccessControlRecord.md)

[Set-AzureStorSimpleAccessControlRecord](./Set-AzureStorSimpleAccessControlRecord.md)

[Get-AzureStorSimpleJob](./Get-AzureStorSimpleJob.md)


