---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 0ECE4232-EA5D-46A0-8260-69646E27FA9A
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/add-azurermapplicationgatewayfrontendipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmApplicationGatewayFrontendIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmApplicationGatewayFrontendIPConfig.md
ms.openlocfilehash: d19f5489adff642ad9b02a7f3bb364338bd1e566
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141926408"
---
# Add-AzureRmApplicationGatewayFrontendIPConfig

## SYNOPSIS
Menambahkan konfigurasi IP ujung depan ke gateway aplikasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResourceId
```
Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-SubnetId <String>] [-PublicIPAddressId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-Subnet <PSSubnet>] [-PublicIPAddress <PSPublicIpAddress>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmApplicationGatewayFrontendIPConfig** menambahkan konfigurasi IP ujung depan ke gateway aplikasi.
Gateway aplikasi mendukung dua tipe konfigurasi IP ujung depan: 
- Alamat IP publik
- Alamat IP privat menggunakan load-balancing internal (ILB) Gateway aplikasi bisa memiliki paling banyak satu IP publik dan satu IP pribadi.
Tambahkan alamat IP publik dan alamat IP pribadi sebagai IP front-end terpisah.

## EXAMPLES

### Contoh 1: Menambahkan IP publik sebagai alamat IP ujung depan
```
PS C:\>$PublicIp = New-AzureRmPublicIpAddress -ResourceGroupName "ResourceGroup01" -Name "PublicIp01" -location "West US" -AllocationMethod Dynamic
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontEndIp01" -PublicIPAddress $PublicIp
```

Perintah pertama membuat objek alamat IP publik dan menyimpannya dalam variabel $PublicIp.
Perintah kedua mendapatkan gateway aplikasi bernama ApplicationGateway01 milik grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah ketiga menambahkan konfigurasi IP ujung depan bernama FrontEndIp01, untuk gateway di $AppGw, menggunakan alamat yang disimpan di $PublicIp.

### Contoh 2: Menambahkan IP pribadi statis sebagai alamat IP ujung depan
```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet -PrivateIPAddress 10.0.1.1
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $VNet.
Perintah kedua mendapatkan konfigurasi subnet bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam variabel $Subnet.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 milik grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah keempat menambahkan konfigurasi IP front-end bernama FrontendIP02 menggunakan $Subnet dari perintah kedua dan alamat IP pribadi 10.0.1.1.

### Contoh 3: Menambahkan IP privat dinamis sebagai alamat IP front-end
```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $VNet.
Perintah kedua mendapatkan konfigurasi subnet bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam variabel $Subnet.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 milik grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah keempat menambahkan konfigurasi IP ujung depan bernama FrontendIP02 menggunakan $Subnet dari perintah kedua.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat cmdlet ini menambahkan konfigurasi IP ujung depan.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Nama
Menentukan nama konfigurasi IP ujung-depan untuk ditambahkan.

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

### -PrivateIPAddress
Menentukan alamat IP privat untuk ditambahkan sebagai IP ujung depan untuk gateway aplikasi.
Jika ditentukan, IP ini dialokasikan secara statis dari subnet.

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

### -PublicIPAddress
Menentukan alamat IP publik yang ditambahkan cmdlet ini sebagai alamat IP ujung depan untuk gateway aplikasi.

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

### -PublicIPAddressId
Menentukan ID alamat IP publik yang ditambahkan cmdlet ini sebagai alamat IP ujung depan untuk gateway aplikasi.

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
Menentukan subnet yang ditambahkan cmdlet ini sebagai konfigurasi IP ujung depan.
Jika Anda menentukan parameter ini, artinya gateway aplikasi mendukung konfigurasi berbasis IP privat.
Jika parameter *PrivateIPAddress* ditentukan, parameter tersebut harus dimiliki oleh subnet ini.
Jika *PrivateIPAddress* tidak ditentukan, salah satu alamat IP dari subnet ini dipilih secara dinamis sebagai alamat IP ujung depan gateway aplikasi.

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
Menentukan ID subnet yang ditambahkan cmdlet ini sebagai konfigurasi IP ujung depan.
Subnet yang lolos menyiratkan IP pribadi.
Jika parameter *PrivateIPAddresss* ditentukan, parameter tersebut harus dimiliki oleh subnet ini.
Jika tidak, salah satu IP dari subnet ini dipilih secara dinamis sebagai IP ujung depan gateway aplikasi.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway
Parameter: ApplicationGateway (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Get-AzureRmApplicationGatewayFrontendIPConfig](./Get-AzureRmApplicationGatewayFrontendIPConfig.md)

[New-AzureRmApplicationGatewayFrontendIPConfig](./New-AzureRmApplicationGatewayFrontendIPConfig.md)

[Hapus-AzureRmApplicationGatewayFrontendIPConfig](./Remove-AzureRmApplicationGatewayFrontendIPConfig.md)

[Set-AzureRmApplicationGatewayFrontendIPConfig](./Set-AzureRmApplicationGatewayFrontendIPConfig.md)


