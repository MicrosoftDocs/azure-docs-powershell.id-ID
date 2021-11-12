---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 0ECE4232-EA5D-46A0-8260-69646E27FA9A
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/add-azurermapplicationgatewayfrontendipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmApplicationGatewayFrontendIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmApplicationGatewayFrontendIPConfig.md
ms.openlocfilehash: d19f5489adff642ad9b02a7f3bb364338bd1e566
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426622"
---
# Add-AzureRmApplicationGatewayFrontendIPConfig

## SYNOPSIS
Menambahkan konfigurasi IP front-end ke gateway aplikasi.

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
Cmdlet **Add-AzureRmApplicationGatewayFrontendIPConfig** menambahkan konfigurasi IP front-end ke gateway aplikasi.
Gateway aplikasi mendukung dua tipe konfigurasi IP front-end: 
- Alamat IP publik
- Alamat IP privat yang menggunakan penyeimbangan muat internal (ILB, Internal Load-Balancing) Gateway aplikasi paling bisa memiliki satu IP publik dan satu IP privat.
Tambahkan alamat IP publik dan alamat IP privat sebagai IP front-end terpisah.

## EXAMPLES

### Contoh 1: Menambahkan IP publik sebagai alamat IP ujung-depan
```
PS C:\>$PublicIp = New-AzureRmPublicIpAddress -ResourceGroupName "ResourceGroup01" -Name "PublicIp01" -location "West US" -AllocationMethod Dynamic
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontEndIp01" -PublicIPAddress $PublicIp
```

Perintah pertama membuat objek alamat IP publik dan menyimpannya di $PublicIp variabel.
Perintah kedua mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $AppGw sumber daya tersebut.
Perintah ketiga menambahkan konfigurasi IP ujung-depan bernama FrontEndIp01, untuk gateway dalam $AppGw, menggunakan alamat yang disimpan di $PublicIp.

### Contoh 2: Menambahkan IP privat statis sebagai alamat IP ujung-depan
```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet -PrivateIPAddress 10.0.1.1
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $VNet sumber daya.
Perintah kedua mendapatkan konfigurasi subnet yang bernama Subnet01 $VNet dari perintah pertama dan menyimpannya dalam $Subnet tertentu.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $AppGw lokal.
Perintah keempat menambahkan konfigurasi IP ujung-depan bernama FrontendIP02 menggunakan $Subnet dari perintah kedua dan alamat IP privat 10.0.1.1.

### Contoh 3: Tambahkan IP privat dinamis sebagai alamat IP front-end
```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $VNet sumber daya.
Perintah kedua mendapatkan konfigurasi subnet yang bernama Subnet01 $VNet dari perintah pertama dan menyimpannya dalam $Subnet tertentu.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $AppGw lokal.
Perintah keempat menambahkan konfigurasi IP ujung-depan yang bernama FrontendIP02 menggunakan $Subnet dari perintah kedua.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi di mana cmdlet ini menambahkan konfigurasi IP front-end.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Menentukan alamat IP privat untuk ditambahkan sebagai IP ujung-depan untuk gateway aplikasi.
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
Menentukan alamat IP publik yang tambahkan cmdlet ini sebagai alamat IP front-end untuk gateway aplikasi.

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
Menentukan ID alamat IP publik yang tambahkan cmdlet ini sebagai alamat IP ujung-depan untuk gateway aplikasi.

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
Menentukan subnet yang tambahkan cmdlet ini sebagai konfigurasi IP ujung-depan.
Jika Anda menentukan parameter ini, itu berarti bahwa gateway aplikasi mendukung konfigurasi berbasis IP privat.
Jika parameter *PrivateIPAddress* ditentukan, parameter tersebut harus termasuk dalam subnet ini.
Jika *PrivateIPAddress* tidak ditentukan, salah satu alamat IP dari subnet ini dipilih secara dinamis sebagai alamat IP ujung-depan gateway aplikasi.

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
Menentukan ID subnet yang tambahkan cmdlet ini sebagai konfigurasi IP front-end.
Menyampaikan subnet berarti IP privat.
Jika parameter *PrivateIPAddresss* ditentukan, parameter tersebut harus termasuk dalam subnet ini.
Jika tidak, salah satu IP dari subnet ini dipilih secara dinamis sebagai IP ujung-depan gateway aplikasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway
Parameter: ApplicationGateway (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Get-AzureRmApplicationGatewayFrontendIPConfig](./Get-AzureRmApplicationGatewayFrontendIPConfig.md)

[New-AzureRmApplicationGatewayFrontendIPConfig](./New-AzureRmApplicationGatewayFrontendIPConfig.md)

[Remove-AzureRmApplicationGatewayFrontendIPConfig](./Remove-AzureRmApplicationGatewayFrontendIPConfig.md)

[Set-AzureRmApplicationGatewayFrontendIPConfig](./Set-AzureRmApplicationGatewayFrontendIPConfig.md)


