---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/set-azbastion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzBastion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzBastion.md
ms.openlocfilehash: 8804d56cd3f3d4e30f2ca81790cb79182d26a527
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142227277"
---
# Set-AzBastion

## SYNOPSIS
Memperbarui Sumber Daya Bastion.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azbastion) untuk informasi terbaru.

## SYNTAX

```
Set-AzBastion -InputObject <PSBastion> [-Sku <String>] [-ScaleUnit <Int32>] [-Tag <Hashtable>] [-Force]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzBastion** dapat digunakan untuk memperbarui Sku, Unit Skala atau Tag sumber daya BastionHost yang sudah ada.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzBastion -InputObject $bastionObj -Sku "Standard" -ScaleUnit 10 -Force
Name                 : MyBastion
Id                   : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/bastionHosts/MyBastion
Etag                 : W/"000"
Type                 : Microsoft.Network/bastionHosts
Location             : westus2
Tag                  :
TagsTable            :
ResourceGroupName    : MyRg
DnsName              : bst-00000000-0000-0000-0000-000000000001.test.bastion.azure.com
ResourceGuid         :
ProvisioningState    : Succeeded
IpConfigurationsText : [
                         {
                           "Subnet": {
                             "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/virtualNetworks/MyVnet/subnets/AzureBastionSubnet"
                           },
                           "PublicIpAddress": {
                             "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/publicIPAddresses/PublicIp1"
                           },
                           "ProvisioningState": "Succeeded",
                           "PrivateIpAllocationMethod": "Dynamic",
                           "Name": "IpConf",
                           "Etag": "W/\"000\"",
                           "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/bastionHosts/MyBastion/bastionHostIpConfigurations/IpConf"
                         }
                       ]
Sku                  : {
                         "Name": "Standard"
                       }
Scale Units          : 10
```

Memperbarui sumber daya BastionHost dengan Sku Dasar dan 2 Unit Skala ke Standar Sku dan 10 Unit Skala

### Contoh 2
```powershell
PS C:\> $bastionObj = Get-AzBastion -ResourceGroupName "MyRg" -Name "MyBastion"
PS C:\> $bastionObj
Name                 : MyBastion
Id                   : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/bastionHosts/MyBastion
Etag                 : W/"000"
Type                 : Microsoft.Network/bastionHosts
Location             : westus2
Tag                  :
TagsTable            :
ResourceGroupName    : MyRg
DnsName              : bst-00000000-0000-0000-0000-000000000001.test.bastion.azure.com
ResourceGuid         :
ProvisioningState    : Succeeded
IpConfigurationsText : [
                         {
                           "Subnet": {
                             "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/virtualNetworks/MyVnet/subnets/AzureBastionSubnet"
                           },
                           "PublicIpAddress": {
                             "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/publicIPAddresses/PublicIp1"
                           },
                           "ProvisioningState": "Succeeded",
                           "PrivateIpAllocationMethod": "Dynamic",
                           "Name": "IpConf",
                           "Etag": "W/\"000\"",
                           "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/bastionHosts/MyBastion/bastionHostIpConfigurations/IpConf"
                         }
                       ]
Sku                  : {
                         "Name": "Basic"
                       }
Scale Units          : 2

PS C:\> $bastionObj.Sku.Name = "Standard"
PS C:\> $bastionObj.ScaleUnit = 50
PS C:\> Set-AzBastion -InputObject $bastionObj -Force
Name                 : MyBastion
Id                   : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/bastionHosts/MyBastion
Etag                 : W/"000"
Type                 : Microsoft.Network/bastionHosts
Location             : westus2
Tag                  :
TagsTable            :
ResourceGroupName    : MyRg
DnsName              : bst-00000000-0000-0000-0000-000000000001.test.bastion.azure.com
ResourceGuid         :
ProvisioningState    : Succeeded
IpConfigurationsText : [
                         {
                           "Subnet": {
                             "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/virtualNetworks/MyVnet/subnets/AzureBastionSubnet"
                           },
                           "PublicIpAddress": {
                             "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/publicIPAddresses/PublicIp1"
                           },
                           "ProvisioningState": "Succeeded",
                           "PrivateIpAllocationMethod": "Dynamic",
                           "Name": "IpConf",
                           "Etag": "W/\"000\"",
                           "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyRg/providers/Microsoft.Network/bastionHosts/MyBastion/bastionHostIpConfigurations/IpConf"
                         }
                       ]
Sku                  : {
                         "Name": "Standard"
                       }
Scale Units          : 50
```

Pembaruan sumber daya BastionHost dengan Unit Skala Sku Dasar dan 2 ke Unit Skala Sku Standar dan 50

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Objek BastionHost

```yaml
Type: PSBastion
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paksa
Minta konfirmasi jika Anda ingin menimpa sumber daya

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ScaleUnit
Unit Skala Bastion

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Sku
The Bastion Sku Tier

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard

Required: False
Position: Named
Default value: Basic
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tag
Sebuah hashtable yang mewakili tag sumber daya.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSBastion

### System.String

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=5.0.0.0,0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Collections.Hashtable

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBastion

## CATATAN

## RELATED LINKS
[New-AzBastion](./New-AzBastion.md)

[Get-AzBastion](./Get-AzBastion.md)

[Remove-AzBastion](./Remove-AzBastion.md)
