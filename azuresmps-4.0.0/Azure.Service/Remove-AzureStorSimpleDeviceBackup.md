---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 47650E39-758C-4D3C-9653-B70576CA0979
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5deaac344c1fafa215b5243fff69aa5d76c6ea45
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421124"
---
# Remove-AzureStorSimpleDeviceBackup

## SYNOPSIS
Menghapus objek cadangan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifyById (Default)
```
Remove-AzureStorSimpleDeviceBackup -DeviceName <String> -BackupId <String> [-Force] [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Remove-AzureStorSimpleDeviceBackup -DeviceName <String> -Backup <Backup> [-Force] [-WaitForComplete]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureStorSimpleDeviceBackup** menghapus satu objek cadangan.
Jika Anda berusaha menghapus cadangan yang telah dihapus, cmdlet ini akan mengembalikan kesalahan.

## EXAMPLES

### Contoh 1: Menghapus cadangan untuk perangkat
```
PS C:\>Remove-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -BackupId "dcb5c991-0485-400f-8d0a-03a1341ee989" -Force
The remove job is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId 6c73aff2-f5a1-4b5e-
9a4e-857e128dc216 for tracking the job status
```

Perintah ini akan menghapus cadangan yang memiliki ID tertentu untuk perangkat bernama Contoso63-AppVm.
Perintah ini memulai operasi yang menghapus objek **Backup,** lalu mengembalikan objek **TaskResponse.**
Untuk melihat status tugas, gunakan cmdlet **Get-AzureStorSimpleTask.**

### Contoh 2: Menghapus cadangan pertama untuk perangkat menggunakan ID-nya
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

Perintah pertama mendapatkan cadangan untuk perangkat bernama Contoso63-AppVm, lalu menyimpannya dalam $Backup bidang.

Perintah kedua menghapus cadangan dari perangkat bernama Contoso63-AppVm.
Perintah menggunakan notasi titik standar untuk merujuk ke properti **InstanceId** dari elemen pertama elemen $Backup array.
Perintah ini menentukan parameter *WaitForComplete,* dan oleh karena itu, perintah akan menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo.**

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

Perintah pertama mendapatkan cadangan untuk perangkat bernama Contoso63-AppVm, lalu menyimpannya dalam $Backup bidang.

Perintah kedua melewati objek pertama yang disimpan dalam $Backup array ke cmdlet saat ini.
Cmdlet tersebut menghapus cadangan itu dari perangkat yang bernama Contoso63-AppVm.
Perintah ini menentukan parameter *WaitForComplete,* dan oleh karena itu, perintah akan menunggu hingga operasi selesai, lalu mengembalikan objek **TaskStatusInfo.**

## PARAMETERS

### -Backup
Menentukan objek **Cadangkan** untuk dihapus.
Untuk mendapatkan objek **Cadangan,** gunakan cmdlet **Get-AzureStorSimpleDeviceBackup.**

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
Menentukan nama perangkat StorSimple yang digunakan untuk menghapus cadangan.

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

### Pencadangan

## OUTPUTS

### TaskStatusInfo, TaskResponse
Cmdlet ini mengembalikan objek **TaskStatusInfo** jika Anda menentukan parameter *WaitForComplete* Jika tidak menentukan parameter tersebut, parameter tersebut akan mengembalikan objek **TaskResponse.**

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleDeviceBackup](./Get-AzureStorSimpleDeviceBackup.md)


