---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 47650E39-758C-4D3C-9653-B70576CA0979
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5deaac344c1fafa215b5243fff69aa5d76c6ea45
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142787623"
---
# Remove-AzureStorSimpleDeviceBackup

## SYNOPSIS
Menghapus objek cadangan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifiById (Default)
```
Remove-AzureStorSimpleDeviceBackup -DeviceName <String> -BackupId <String> [-Force] [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifikasiByObject
```
Remove-AzureStorSimpleDeviceBackup -DeviceName <String> -Backup <Backup> [-Force] [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureStorSimpleDeviceBackup** menghapus satu objek cadangan.
Jika Anda mencoba menghapus cadangan yang telah dihapus, cmdlet ini mengembalikan kesalahan.

## EXAMPLES

### Contoh 1: Menghapus cadangan untuk perangkat
```
PS C:\>Remove-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -BackupId "dcb5c991-0485-400f-8d0a-03a1341ee989" -Force
The remove job is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId 6c73aff2-f5a1-4b5e-
9a4e-857e128dc216 for tracking the job status
```

Perintah ini menghapus cadangan yang memiliki ID tertentu untuk perangkat bernama Contoso63-AppVm.
Perintah memulai operasi yang menghapus objek **Cadangan** , lalu mengembalikan objek **TaskResponse** .
Untuk melihat status tugas, gunakan cmdlet **Get-AzureStorSimpleTask** .

### Contoh 2: Hapus cadangan pertama untuk perangkat dengan menggunakan ID-nya
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm"
PS C:\> Remove-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -BackupId $Backup[0].InstanceId -WaitForComplete
Error      : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
JobId      : 53a656c3-c082-4e1f-afb7-bff3db45c791
JobSteps   : {}
Result     : Succeeded
Status     : Completed
TaskResult : Succeeded
StatusCode : OK
RequestId  : f4411f38d07f68b88095682dbeedd9e9
```

Perintah pertama mendapatkan cadangan untuk perangkat bernama Contoso63-AppVm, lalu menyimpannya dalam variabel $Backup.

Perintah kedua menghapus cadangan dari perangkat bernama Contoso63-AppVm.
Perintah menggunakan notasi titik standar untuk merujuk ke properti **InstanceId** elemen pertama array $Backup.
Perintah ini menentukan parameter *WaitForComplete* , dan oleh karena itu, perintah menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo** .

### Contoh 3: Menghapus cadangan pertama untuk perangkat dengan menggunakan saluran
```
PS C:\>$Backup = Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso-AppVm" -WaitForComplete
PS C:\> $Backup[0] | Remove-AzureStorSimpleDeviceBackup -DeviceName "Contoso-AppVm" -Force -WaitForComplete
Error      : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
JobId      : 48059fd8-e355-4b91-9385-630d24f31df6
JobSteps   : {}
Result     : Succeeded
Status     : Completed
TaskResult : Succeeded
StatusCode : OK
RequestId  : e1753f3bf68e6e44ab719436b5111e41
```

Perintah pertama mendapatkan cadangan untuk perangkat bernama Contoso63-AppVm, lalu menyimpannya dalam variabel $Backup.

Perintah kedua melewati objek pertama yang disimpan dalam array $Backup ke cmdlet saat ini.
Cmdlet itu menghapus cadangan dari perangkat bernama Contoso63-AppVm.
Perintah ini menentukan parameter *WaitForComplete* , dan oleh karena itu, perintah menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo** .

## PARAMETERS

### -Cadangan
Menentukan objek **Cadangan** untuk dihapus.
Untuk mendapatkan objek **Cadangan** , gunakan cmdlet **Get-AzureStorSimpleDeviceBackup** .

```yaml
Type: Backup
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupId
Menentukan ID instans cadangan untuk dihapus.

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
Menentukan nama perangkat StorSimple untuk menghapus cadangan.

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

### Cadangan

## OUTPUTS

### TaskStatusInfo, TaskResponse
Cmdlet ini mengembalikan objek **TaskStatusInfo** jika Anda menentukan parameter *WaitForComplete* Jika Anda tidak menentukan parameter tersebut, maka akan mengembalikan objek **TaskResponse** .

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackup](./Get-AzureStorSimpleDeviceBackup.md)


