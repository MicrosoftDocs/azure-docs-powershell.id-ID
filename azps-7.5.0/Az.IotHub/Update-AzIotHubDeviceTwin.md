---
external help file: Microsoft.Azure.PowerShell.Cmdlets.IotHub.dll-Help.xml
Module Name: Az.IotHub
online version: https://docs.microsoft.com/powershell/module/az.iothub/update-aziothubdevicetwin
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/Update-AzIotHubDeviceTwin.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/Update-AzIotHubDeviceTwin.md
ms.openlocfilehash: 5f1ac140bcf09b4d1a2e9d9bd548445e7ac1679b
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145815642"
---
# Update-AzIotHubDeviceTwin

## SYNOPSIS
Memperbarui tag dan properti yang diinginkan dari perangkat kembar.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.iothub/update-aziothubdevicetwin) untuk informasi terbaru.

## SYNTAX

### ResourceSet (Default)
```
Update-AzIotHubDeviceTwin [-ResourceGroupName] <String> [-IotHubName] <String> [-DeviceId] <String>
 [-Tag <Hashtable>] [-Desired <Hashtable>] [-Partial] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectSet
```
Update-AzIotHubDeviceTwin [-InputObject] <PSIotHub> [-DeviceId] <String> [-Tag <Hashtable>]
 [-Desired <Hashtable>] [-Partial] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceIdSet
```
Update-AzIotHubDeviceTwin [-ResourceId] <String> [-DeviceId] <String> [-Tag <Hashtable>] [-Desired <Hashtable>]
 [-Partial] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui atau mengganti kembar perangkat. Lihat https://docs.microsoft.com/azure/iot-hub/iot-hub-devguide-device-twins untuk informasi lebih lanjut.

## EXAMPLES

### Contoh 1
```powershell
Update-AzIotHubDeviceTwin -ResourceGroupName "myresourcegroup" -IotHubName "myiothub" -DeviceId "myDevice1" -Tag $updatedTag -Desired $updatedDesired -Partial
```

Mengembalikan objek kembar perangkat yang diperbarui.

### Contoh 2
```powershell
Update-AzIotHubDeviceTwin -ResourceGroupName "myresourcegroup" -IotHubName "myiothub" -DeviceId "myDevice1" -Desired $updatedDesired -Partial
```

Mengembalikan objek kembar perangkat dengan properti yang diinginkan yang diperbarui.

### Contoh: 3
```powershell
Update-AzIotHubDeviceTwin -ResourceGroupName "myresourcegroup" -IotHubName "myiothub" -DeviceId "myDevice1" -Tag $updatedTag -Partial
```

Mengembalikan objek kembar perangkat dengan properti tag yang diperbarui.

### Contoh 4
```powershell
$updatedTag = @{}
$updatedTag.add("key0","value0")
$updatedDesired =@{}
$updatedDesired.add("desiredkey","desiredvalue")
Update-AzIotHubDeviceTwin -ResourceGroupName "myresourcegroup" -IotHubName "myiothub" -DeviceId "myDevice1" -Tag $updatedTag -Desired $updatedDesired
```

Mengembalikan objek kembar perangkat yang diganti.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Desired
Tambahkan atau perbarui properti yang diinginkan di perangkat kembar.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceId
Id Perangkat Target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek IotHub

```yaml
Type: Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHub
Parameter Sets: InputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IotHubName
Nama Iot Hub

```yaml
Type: System.String
Parameter Sets: ResourceSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parsial
Memungkinkan untuk hanya memperbarui sebagian tag dan properti yang diinginkan dari kembar perangkat.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: ResourceSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya IotHub

```yaml
Type: System.String
Parameter Sets: ResourceIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Menambahkan atau memperbarui properti tag di perangkat kembar.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHub

### System.String

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS
