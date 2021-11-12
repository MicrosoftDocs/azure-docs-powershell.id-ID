---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 53580FF1-D905-40FD-A5F0-D5FBCD036E0B
online version: ''
schema: 2.0.0
ms.openlocfilehash: c63d30dde7fa16d5c4649d1a39e9e44dc261ebba
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428031"
---
# Start-AzureStorSimpleDeviceFailoverJob

## SYNOPSIS
Memulai operasi failover grup wadah volume.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Kosong (Default)
```
Start-AzureStorSimpleDeviceFailoverJob
 -VolumecontainerGroups <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]>
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyById
```
Start-AzureStorSimpleDeviceFailoverJob -DeviceId <String>
 -VolumecontainerGroups <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]>
 -TargetDeviceId <String> [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByName
```
Start-AzureStorSimpleDeviceFailoverJob -DeviceName <String>
 -VolumecontainerGroups <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]>
 -TargetDeviceName <String> [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureStorSimpleDeviceFailoverJob** memulai operasi failover dari satu atau beberapa grup wadah volume dari satu perangkat ke perangkat lain.

## EXAMPLES

### Contoh 1: Memulai pekerjaan failover untuk perangkat bernama dan perangkat target bernama
```
PS C:\>(Get-AzureStorSimpleFailoverVolumeContainers -DeviceName "ChewD_App7") | Where-Object {$_.IsDCGroupEligibleForDR -eq $True} | Start-AzureStorSimpleDeviceFailoverJob -DeviceName "ChewD_App7" -TargetDeviceName "Fuller05" -Force
a3d902be-8ffb-42a4-bbf8-0a1b30db71b2_0ee59ae9-0293-46e2-ae56-bc308c8e5520
```

Perintah ini mendapatkan wadah volume failover untuk perangkat yang bernama ChewD_App7 menggunakan cmdlet **Get-AzureStorSimpleFailoverVolumeContainers.**
Perintah lolos hasil ke cmdlet **Where-Object,** yang menghasilkan wadah yang memiliki nilai selain $True untuk **properti IsDCGroupEligibleForDR.**
Untuk informasi selengkapnya, ketik `Get-Help Where-Object` .
Cmdlet saat ini memulai pekerjaan failover untuk sisa wadah volume failover.
Perintah menentukan nama perangkat dan nama perangkat target.
Perintah mengembalikan ID contoh pekerjaan yang dijalankan cmdlet.

### Contoh 2: Memulai pekerjaan failover untuk perangkat dan perangkat target yang ditentukan berdasarkan ID
```
PS C:\>(Get-AzureStorSimpleFailoverVolumeContainers -DeviceId "3825f272-1efb-4c14-b63f-22605ce3b925") | Where-Object {$_.IsDCGroupEligibleForDR -eq $True} | Select-Object -First 1 | Start-AzureStorSimpleDeviceFailoverJob -DeviceId "3825f272-1efb-4c14-b63f-22605ce3b925" -TargetDeviceId "0ee59ae9-0293-46e2-ae56-bc308c8e5520" -Force
4c5ac0d0-4b66-465c-98f5-aec90505ad12_0ee59ae9-0293-46e2-ae56-bc308c8e5520
```

Perintah ini mendapatkan wadah volume failover untuk perangkat yang bernama ChewD_App7 menggunakan **Get-AzureStorSimpleFailoverVolumeContainers**.
Perintah lolos hasil ke **Where-Object,** yang menghasilkan containters yang memiliki nilai selain $True untuk **properti IsDCGroupEligibleForDR.**
Cmdlet passes the results to the **Select-Object** cmdlet, which selects the first object to pass to the current cmdlet.
Untuk informasi selengkapnya, ketik `Get-Help Select-Object` .
Cmdlet saat ini memulai pekerjaan failover untuk wadah volume failover yang dipilih.
Perintah menentukan ID perangkat dan ID perangkat target.
Perintah mengembalikan ID contoh pekerjaan yang dijalankan cmdlet.

## PARAMETERS

### -DeviceId
Menentukan ID instans dari perangkat StorSimple tempat grup wadah volume berada.

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
Menentukan nama perangkat StorSimple tempat grup wadah volume berada.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -TargetDeviceId
Menentukan ID instans perangkat StorSimple yang gagal dilakukan cmdlet ini melalui grup wadah volume.

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

### -TargetDeviceName
Menentukan nama perangkat StorSimple yang gagal dilakukan cmdlet ini pada grup wadah volume.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumecontainerGroups
Menentukan daftar grup wadah volume yang gagal cmdlet ini pada perangkat lain.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Daftar\<DataContainerGroup\>
Anda dapat pipakan daftar grup wadah volume ke cmdlet ini.

## OUTPUTS

### String

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleFailoverVolumeContainers](./Get-AzureStorSimpleFailoverVolumeContainers.md)


