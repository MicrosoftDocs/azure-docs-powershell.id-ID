---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 5AB916CB-A141-4662-8220-6C1FBB58FC69
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1c29a3f8da13fc27916347aad621400d1ac00d8f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421121"
---
# Remove-AzureStorSimpleDeviceBackupPolicy

## SYNOPSIS
Menghapus kebijakan cadangan yang sudah ada.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifyById (Default)
```
Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName <String> -BackupPolicyId <String> [-Force]
 [-WaitForComplete] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName <String> -BackupPolicy <BackupPolicyDetails> [-Force]
 [-WaitForComplete] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureStorSimpleDeviceBackupPolicy** menghapus objek **BackupPolicy yang sudah** ada.
Setelah Anda menghapus kebijakan pencadangan, tidak ada pencadangan lebih lanjut yang terjadi berdasarkan kebijakan itu.
Cmdlet ini juga menghapus semua jadwal terkait dengan kebijakan yang dihapus.

## EXAMPLES

### Contoh 1: Menghapus kebijakan cadangan
```
PS C:\>Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyId "03710b4c-82c1-40ca-be5c-40289dc49642" -Force
VERBOSE: ClientRequestId: b3e4d485-eae4-4cf4-a43b-815f3abcd2dd_PS
VERBOSE: ClientRequestId: a260ee98-46aa-49e0-91ac-31d4155f4cae_PS
VERBOSE: About to create a job to remove your backuppolicy! 
VERBOSE: ClientRequestId: 92a9c264-90df-4345-a495-92767dd266f2_PS
695be190-ac81-4cf2-b1c5-03ef6b08d005
VERBOSE: The remove task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
695be190-ac81-4cf2-b1c5-03ef6b08d005 for tracking the task's status
```

Perintah ini menghapus **BackupPolicy** yang mempunyai instans ID 03710b4c-82c1-40ca-be5c-40289dc49642, sehingga tidak ada lagi pencadangan yang dibuat berdasarkan kebijakan ini.
Perintah tersebut juga menghapus semua jadwal yang terkait dengan kebijakan ini.
Perintah ini memulai operasi yang menghapus objek **BackupPolicy,** lalu mengembalikan objek **TaskResponse.**
Untuk melihat status tugas, gunakan cmdlet **Get-AzureStorSimpleTask.**

### Contoh 2: Menghapus kebijakan pencadangan pertama untuk perangkat
```
PS C:\>$Policies = Get-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm"
PS C:\> Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyId $Policies[0].InstanceId -Force -WaitForComplete
VERBOSE: ClientRequestId: db3b49fa-cffa-446d-ba52-daa6802e00f7_PS
VERBOSE: ClientRequestId: 70e2b56f-c2df-40d0-a1e5-d7a4d7e25962_PS
VERBOSE: About to run a job to remove your backuppolicy! 
VERBOSE: ClientRequestId: f8eb3d4d-2c57-4fc9-9f40-79d0f2ea1b6a_PS


JobId        : 820a246e-54b6-41a9-bdd5-15d5daea9b0a
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, 
               Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The job created for your remove operation has completed successfully.
```

Perintah pertama mendapatkan kebijakan pencadangan untuk perangkat bernama Contoso63-AppVm, lalu menyimpannya dalam $Policies baru.

Perintah kedua menghapus kebijakan cadangan pertama dari Contoso63-AppVm.
Perintah menggunakan sintaks titik standar untuk mengidentifikasi **properti InstanceId** dari item pertama dalam $Policies.
Perintah ini menentukan parameter *WaitForComplete,* sehingga perintah menyelesaikan tugas, lalu mengembalikan objek **TaskStatusInfo** untuk tugas tersebut.

### Contoh 3: Hapus kebijakan pencadangan dengan menggunakan saluran
```
PS C:\>Get-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyName "TSQAVolume01_Default" | Remove-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -Force -WaitForComplete
VERBOSE: ClientRequestId: 60080fb1-2f88-4c17-bfd7-21aa73440a9c_PS
VERBOSE: ClientRequestId: 04c91121-50d7-4796-9af6-fc6a7d6b6a0e_PS
VERBOSE: ClientRequestId: 47ceb37c-672f-42e8-bd19-1190925c46cd_PS
VERBOSE: ClientRequestId: cbc39757-f2cc-4cc5-93ea-4ec0fbfb0ca8_PS
VERBOSE: ClientRequestId: 3614d47a-51fc-4500-a5f1-5401301ca4e3_PS
VERBOSE: About to create a job to remove your backuppolicy! 
VERBOSE: ClientRequestId: dbd7166e-1888-4b11-9af9-8d49712a8c8b_PS
702ad240-5730-4015-b051-56055bd2c2d3
VERBOSE: The remove task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
702ad240-5730-4015-b051-56055bd2c2d3 for tracking the task's status
VERBOSE: BackupPolicy with id bfe0bf8a-2d09-4690-93da-38a4f24e9f4f found!
```

Perintah ini mendapatkan objek **BackupPolicyDetails** menggunakan **Get-AzureStorSimpleDeviceBackupPolicy**, lalu meneruskannya ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini menghapus kebijakan pencadangan yang bernama TSQAVolume01_Default.

## PARAMETERS

### -BackupPolicy
Menentukan objek **BackupPolicyDetails** yang akan dihapus.
Untuk mendapatkan objek **BackupPolicyDetails,** gunakan cmdlet **Get-AzureStorSimpleDeviceBackupPolicy.**

```yaml
Type: BackupPolicyDetails
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupPolicyId
Menentukan ID contoh objek **BackupPolicy** yang akan dihapus.

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

### -DeviceName
Tentukan nama perangkat StorSimple yang akan dihapus kebijakan pencadangannya.

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
Mengindikasikan bahwa cmdlet ini tidak meminta konfirmasi Anda.

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
Menunjukkan bahwa cmdlet ini menunggu hingga operasi selesai sebelum mengembalikan kontrol ke Windows PowerShell konsol.

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

### BackupPolicyDetails
Cmdlet ini menerima objek **BackupPolicyDetails** untuk dihapus.

## OUTPUTS

### TaskStatusInfo, TaskResponse
Cmdlet ini mengembalikan objek **TaskStatusInfo** jika Anda menentukan parameter *WaitForComplete.*
Jika Anda tidak menentukan parameter itu, parameter itu mengembalikan **objek TaskResponse.**

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackupPolicy](./Get-AzureStorSimpleDeviceBackupPolicy.md)

[New-AzureStorSimpleDeviceBackupPolicy](./New-AzureStorSimpleDeviceBackupPolicy.md)

[Set-AzureStorSimpleDeviceBackupPolicy](./Set-AzureStorSimpleDeviceBackupPolicy.md)

[Get-AzureStorSimpleJob](./Get-AzureStorSimpleJob.md)


