---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DeviceProvisioningServices.dll-Help.xml
Module Name: Az.DeviceProvisioningServices
online version: https://docs.microsoft.com/powershell/module/az.deviceprovisioningservices/remove-aziotdeviceprovisioningserviceaccesspolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DeviceProvisioningServices/DeviceProvisioningServices/help/Remove-AzIoTDeviceProvisioningServiceAccessPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DeviceProvisioningServices/DeviceProvisioningServices/help/Remove-AzIoTDeviceProvisioningServiceAccessPolicy.md
ms.openlocfilehash: e1b35dfec4da00a78f4a852ad62730a08e279775
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136570234"
---
# Remove-AzIoTDeviceProvisioningServiceAccessPolicy

## SYNOPSIS
Hapus kebijakan akses bersama dalam layanan penyediaan perangkat Azure IoT Hub.

## SYNTAX

### ResourceSet (Default)
```
Remove-AzIoTDeviceProvisioningServiceAccessPolicy [-ResourceGroupName] <String> [-Name] <String>
 [-KeyName] <String> [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectSet
```
Remove-AzIoTDeviceProvisioningServiceAccessPolicy
 [-InputObject] <PSSharedAccessSignatureAuthorizationRuleAccessRightsDescription> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdSet
```
Remove-AzIoTDeviceProvisioningServiceAccessPolicy [-ResourceId] <String> [-KeyName] <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Untuk pengenalan layanan penyediaan perangkat Azure IoT Hub, lihat https://docs.microsoft.com/azure/iot-dps/about-iot-dps .

## EXAMPLES

### Contoh 1
```
PS C:\> Remove-AzIoTDeviceProvisioningServiceAccessPolicy -ResourceGroupName "myresourcegroup" -Name "myiotdps" -KeyName "mypolicy" -PassThru

True
```

Hapus kebijakan akses bersama "mypolicy" dalam layanan penyediaan perangkat Azure IoT Hub.

### Contoh 2
```
PS C:\> Get-AzIoTDpsAccessPolicy -ResourceGroupName "myresourcegroup" -Name "myiotdps" -KeyName "mypolicy" | Remove-AzIoTDpsAccessPolicy
```

Hapus kebijakan akses bersama "mypolicy" dalam layanan penyediaan perangkat Azure IoT Hub menggunakan pipeline.

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

### -InputObject
Objek Layanan Penyediaan Perangkat IoT

```yaml
Type: Microsoft.Azure.Commands.Management.DeviceProvisioningServices.Models.PSSharedAccessSignatureAuthorizationRuleAccessRightsDescription
Parameter Sets: InputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyName
Nama kunci kebijakan akses Layanan Penyediaan Perangkat IoT

```yaml
Type: System.String
Parameter Sets: ResourceSet, ResourceIdSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Layanan Penyediaan Perangkat IoT

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

### -PassThru
{{fill passThru Description}}

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
Id Sumber Daya Layanan Penyediaan Perangkat Iot

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Management.DeviceProvisioningServices.Models.PSSharedAccessSignatureAuthorizationRuleAccessRightsDescription

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
