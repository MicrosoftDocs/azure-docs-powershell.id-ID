---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: C50959BB-7481-4898-BF4B-C5ABF8758473
online version: ''
schema: 2.0.0
ms.openlocfilehash: c154df7bb593d7e084b15b7bb944adc1ba382896
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426532"
---
# Remove-AzureStorSimpleDeviceVolumeContainer

## SYNOPSIS
Menghapus wadah volume dari perangkat StorSimple.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureStorSimpleDeviceVolumeContainer -DeviceName <String> -VolumeContainer <DataContainer>
 [-WaitForComplete] [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureStorSimpleDeviceVolumeContainer** menghapus objek wadah volume dari perangkat StorSimple.
Cmdlet ini akan meminta konfirmasi kecuali Anda menentukan parameter *Paksa.*

## EXAMPLES

### Contoh 1: Menghapus wadah dengan menggunakan saluran
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "Container08" | Remove-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -Force
VERBOSE: ClientRequestId: 0efbb4fc-ceb0-4311-bc49-0e08161d0a37_PS
VERBOSE: ClientRequestId: bf5b615f-47e3-4868-91b6-f2d12217a302_PS
VERBOSE: ClientRequestId: 5590c87e-0602-4197-b6c3-cf58b0e7a7b3_PS
VERBOSE: ClientRequestId: b33c71ac-c345-44ff-8213-d7fdf9f8480a_PS
VERBOSE: ClientRequestId: 903d42ef-58f4-4e89-ba7f-5f234262356d_PS
VERBOSE: About to create a job to remove your Volume container! 
VERBOSE: ClientRequestId: 2279575f-5115-4344-9c6f-9ef599bd203e_PS
e9ddec89-67ac-4e2e-a2ed-820de3547bb0
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
e9ddec89-67ac-4e2e-a2ed-820de3547bb0 for tracking the task's status
VERBOSE: Volume container with name: Container08 is found.
```

Perintah ini mengambil wadah volume yang bernama Container08 pada perangkat yang bernama Contoso63-AppVm dengan menggunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer.**
Perintah tersebut melewati wadah volume ke cmdlet saat ini menggunakan operator pipeline.
Perintah ini memulai tugas untuk menghapus wadah, lalu mengembalikan objek **TaskResponse.**
Untuk melihat status tugas, gunakan cmdlet **Get-AzureStorSimpleTask.**
Perintah ini menentukan parameter *Paksa,* sehingga tidak meminta konfirmasi kepada Anda.

## PARAMETERS

### -DeviceName
Tentukan nama perangkat StorSimple yang menjadi tempat penampung volume untuk dihapus.

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

### -VolumeContainer
Menentukan wadah volume yang akan dihapus, sebagai objek **DataContainer.**
Untuk mendapatkan objek **DataContainer,** gunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer.**

```yaml
Type: DataContainer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### DataContainer
Cmdlet ini menerima objek **DataContainer** yang akan dihapus.

## OUTPUTS

### TaskStatusInfo
Cmdlet ini mengembalikan **objek TaskStatusInfo,** jika Anda menentukan parameter *WaitForComplete.*

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolumeContainer](./Get-AzureStorSimpleDeviceVolumeContainer.md)

[New-AzureStorSimpleDeviceVolumeContainer](./New-AzureStorSimpleDeviceVolumeContainer.md)


