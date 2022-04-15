---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 7610228A-61F9-41B8-A42A-CD7C793BB33F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/add-azurermnetworkinterfaceipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmNetworkInterfaceIpConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmNetworkInterfaceIpConfig.md
ms.openlocfilehash: 46c08913b36958bb9cd0bd75393b87ed887a0f1d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142386461"
---
# Add-AzureRmNetworkInterfaceIpConfig

## SYNOPSIS
Menambahkan konfigurasi IP antarmuka jaringan ke antarmuka jaringan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResource (Default)
```
Add-AzureRmNetworkInterfaceIpConfig -Name <String> -NetworkInterface <PSNetworkInterface>
 [-PrivateIpAddressVersion <String>] [-PrivateIpAddress <String>] [-Primary] [-Subnet <PSSubnet>]
 [-PublicIpAddress <PSPublicIpAddress>]
 [-LoadBalancerBackendAddressPool <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool]>]
 [-LoadBalancerInboundNatRule <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSInboundNatRule]>]
 [-ApplicationGatewayBackendAddressPool <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool]>]
 [-ApplicationSecurityGroup <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResourceId
```
Add-AzureRmNetworkInterfaceIpConfig -Name <String> -NetworkInterface <PSNetworkInterface>
 [-PrivateIpAddressVersion <String>] [-PrivateIpAddress <String>] [-Primary] [-SubnetId <String>]
 [-PublicIpAddressId <String>]
 [-LoadBalancerBackendAddressPoolId <System.Collections.Generic.List`1[System.String]>]
 [-LoadBalancerInboundNatRuleId <System.Collections.Generic.List`1[System.String]>]
 [-ApplicationGatewayBackendAddressPoolId <System.Collections.Generic.List`1[System.String]>]
 [-ApplicationSecurityGroupId <System.Collections.Generic.List`1[System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmNetworkInterfaceIpConfig** menambahkan konfigurasi IP antarmuka jaringan ke antarmuka jaringan Azure.

## EXAMPLES

### Contoh 1: Menambahkan konfigurasi IP baru dengan grup keamanan aplikasi
```
$subnet = New-AzureRmVirtualNetworkSubnetConfig -Name MySubnet -AddressPrefix 10.0.1.0/24
$vnet = New-AzureRmvirtualNetwork -Name MyVNET -ResourceGroupName MyResourceGroup -Location "West US" -AddressPrefix 10.0.0.0/16 -Subnet $subnet

$nic = New-AzureRmNetworkInterface -Name MyNetworkInterface -ResourceGroupName MyResourceGroup -Location "West US"  -Subnet $vnet.Subnets[0]

$asg = New-AzureRmApplicationSecurityGroup -ResourceGroupName MyResourceGroup -Name MyASG -Location "West US"

$nic | Set-AzureRmNetworkInterfaceIpConfig -Name $nic.IpConfigurations[0].Name -Subnet $vnet.Subnets[0] -ApplicationSecurityGroup $asg | Set-AzureRmNetworkInterface

$nic | Add-AzureRmNetworkInterfaceIpConfig -Name MyNewIpConfig -Subnet $vnet.Subnets[0] -ApplicationSecurityGroup $asg  | Set-AzureRmNetworkInterface
```

Dalam contoh ini, kami membuat antarmuka jaringan baru MyNetworkInterface yang termasuk dalam subnet di jaringan virtual baru MyVNET. Kami juga membuat grup keamanan aplikasi kosong MyASG untuk mengaitkan dengan konfigurasi IP di antarmuka jaringan. Setelah kedua objek dibuat, kami menautkan konfigurasi IP default ke objek MyASG. Akhirnya, kami membuat konfigurasi IP baru di antarmuka jaringan yang juga terkait dengan objek grup keamanan aplikasi.

## PARAMETERS

### -ApplicationGatewayBackendAddressPool
Menentukan kumpulan referensi kumpulan alamat backend gateway aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationGatewayBackendAddressPoolId
Menentukan kumpulan referensi kumpulan alamat backend gateway aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationSecurityGroup
Menentukan kumpulan referensi grup keamanan aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationSecurityGroupId
Menentukan kumpulan referensi grup keamanan aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerBackendAddressPool
Menentukan kumpulan referensi kumpulan alamat backend load balancer tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerBackendAddressPoolId
Menentukan kumpulan referensi kumpulan alamat backend load balancer tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerInboundNatRule
Menentukan kumpulan referensi aturan terjemahan alamat jaringan masuk (NAT) penyeimbang muat tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSInboundNatRule]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerInboundNatRuleId
Menentukan kumpulan referensi aturan NAT masuk penyeimbang muatan tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi IP antarmuka jaringan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkInterface
Menentukan objek **NetworkInterface** .
Cmdlet ini menambahkan konfigurasi IP antarmuka jaringan ke objek yang ditentukan parameter ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkInterface
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Primer
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

### -PrivateIpAddress
Menentukan alamat IP statis dari konfigurasi IP antarmuka jaringan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateIpAddressVersion
Menentukan versi alamat IP dari konfigurasi IP antarmuka jaringan.
Nilai yang dapat diterima untuk parameter ini adalah:
- IPv4
- IPv6

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIpAddress
Menentukan objek **PublicIPAddress** .
Cmdlet ini membuat referensi ke Alamat IP publik untuk dikaitkan dengan konfigurasi IP antarmuka jaringan ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIpAddressId
Cmdlet ini membuat referensi ke Alamat IP publik untuk dikaitkan dengan konfigurasi IP antarmuka jaringan ini.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Menentukan objek **Subnet** .
Cmdlet ini membuat referensi ke subnet tempat konfigurasi IP antarmuka jaringan ini dibuat.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSSubnet
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Cmdlet ini membuat referensi ke subnet tempat konfigurasi IP antarmuka jaringan ini dibuat.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
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

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface
Parameter: NetworkInterface (ByValue)

### System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool, Microsoft.Azure.Commands.Network, Version=6.4.1.0, Culture=netral, PublicKeyToken=null]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.PSInboundNatRule, Microsoft.Azure.Commands.Network, Version=6.4.1.0, Culture=netral, PublicKeyToken=null]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool, Microsoft.Azure.Commands.Network, Version=6.4.1.0, Culture=netral, PublicKeyToken=null]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup, Microsoft.Azure.Commands.Network, Version=6.4.1.0, Culture=netral, PublicKeyToken=null]]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface

## CATATAN
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, jaringan, jaringan

## RELATED LINKS

[Get-AzureRmNetworkInterfaceIpConfig](./Get-AzureRmNetworkInterfaceIpConfig.md)

[New-AzureRmNetworkInterfaceIpConfig](./New-AzureRmNetworkInterfaceIpConfig.md)

[Hapus-AzureRmNetworkInterfaceIpConfig](./Remove-AzureRmNetworkInterfaceIpConfig.md)

[Set-AzureRmNetworkInterfaceIpConfig](./Set-AzureRmNetworkInterfaceIpConfig.md)


