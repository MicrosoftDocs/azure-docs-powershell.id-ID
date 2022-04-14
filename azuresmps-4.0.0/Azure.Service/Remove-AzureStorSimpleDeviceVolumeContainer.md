---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: C50959BB-7481-4898-BF4B-C5ABF8758473
online version: ''
schema: 2.0.0
ms.openlocfilehash: c154df7bb593d7e084b15b7bb944adc1ba382896
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141816416"
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
Cmdlet ini meminta konfirmasi kecuali Anda menentukan parameter *Paksa* .

## EXAMPLES

### Contoh 1: Menghapus wadah menggunakan pipeline
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

Perintah ini mendapatkan wadah volume bernama Container08 di perangkat bernama Contoso63-AppVm dengan menggunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** .
Perintah melewati wadah volume ke cmdlet saat ini menggunakan operator pipeline.
Perintah ini memulai tugas untuk menghapus wadah, lalu mengembalikan objek **TaskResponse** .
Untuk melihat status tugas, gunakan cmdlet **Get-AzureStorSimpleTask** .
Perintah ini menentukan parameter *Paksa* , sehingga tidak meminta konfirmasi kepada Anda.

## PARAMETERS

### -DeviceName
Menentukan nama perangkat StorSimple tempat wadah volume untuk dihapus ada.

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

### -VolumeContainer
Menentukan wadah volume untuk dihapus, sebagai objek **DataContainer** .
Untuk mendapatkan objek **DataContainer** , gunakan cmdlet **Get-AzureStorSimpleDeviceVolumeContainer** .

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

### DataContainer
Cmdlet ini menerima objek **DataContainer** untuk dihapus.

## OUTPUTS

### TaskStatusInfo
Cmdlet ini mengembalikan objek **TaskStatusInfo** , jika Anda menentukan parameter *WaitForComplete* .

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolumeContainer](./Get-AzureStorSimpleDeviceVolumeContainer.md)

[Baru-AzureStorSimpleDeviceVolumeContainer](./New-AzureStorSimpleDeviceVolumeContainer.md)


