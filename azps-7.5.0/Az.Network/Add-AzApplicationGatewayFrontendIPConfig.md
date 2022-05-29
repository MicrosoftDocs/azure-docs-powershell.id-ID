---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 0ECE4232-EA5D-46A0-8260-69646E27FA9A
online version: https://docs.microsoft.com/powershell/module/az.network/add-azapplicationgatewayfrontendipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzApplicationGatewayFrontendIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzApplicationGatewayFrontendIPConfig.md
ms.openlocfilehash: ef2f475149a5deac33523035c8a2d1c6eb64a42a
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145778806"
---
# Add-AzApplicationGatewayFrontendIPConfig

## SYNOPSIS
Menambahkan konfigurasi IP front-end ke gateway aplikasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/add-azapplicationgatewayfrontendipconfig) untuk informasi terbaru.

## SYNTAX

### SetByResourceId
```
Add-AzApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-SubnetId <String>] [-PublicIPAddressId <String>]
 [-PrivateLinkConfigurationId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
Add-AzApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-Subnet <PSSubnet>] [-PublicIPAddress <PSPublicIpAddress>]
 [-PrivateLinkConfiguration <PSApplicationGatewayPrivateLinkConfiguration>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzApplicationGatewayFrontendIPConfig** menambahkan konfigurasi IP front-end ke gateway aplikasi.
Gateway aplikasi mendukung dua jenis konfigurasi IP front-end: 
- Alamat IP Publik
- Alamat IP privat menggunakan penyeimbangan beban internal (ILB) Gateway aplikasi dapat memiliki paling banyak satu IP publik dan satu IP privat.
Tambahkan alamat IP publik dan alamat IP privat sebagai IP front-end terpisah.

## EXAMPLES

### Contoh 1: Menambahkan IP publik sebagai alamat IP front-end
```powershell
$PublicIp = New-AzPublicIpAddress -ResourceGroupName "ResourceGroup01" -Name "PublicIp01" -location "West US" -AllocationMethod Dynamic
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$AppGw = Add-AzApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontEndIp01" -PublicIPAddress $PublicIp
```

Perintah pertama membuat objek alamat IP publik dan menyimpannya dalam variabel $PublicIp.
Perintah kedua mendapatkan gateway aplikasi bernama ApplicationGateway01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah ketiga menambahkan konfigurasi IP front-end bernama FrontEndIp01, untuk gateway di $AppGw, menggunakan alamat yang disimpan di $PublicIp.

### Contoh 2: Menambahkan IP privat statis sebagai alamat IP front-end
```powershell
$VNet = Get-AzVirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
$Subnet = Get-AzVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$AppGw = Add-AzApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet -PrivateIPAddress 10.0.1.1
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $VNet.
Perintah kedua mendapatkan konfigurasi subnet bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam variabel $Subnet.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah keempat menambahkan konfigurasi IP front-end bernama FrontendIP02 menggunakan $Subnet dari perintah kedua dan alamat IP privat 10.0.1.1.

### Contoh 3: Menambahkan IP privat dinamis sebagai alamat IP front-end
```powershell
$VNet = Get-AzVirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
$Subnet = Get-AzVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$AppGw = Add-AzApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $VNet.
Perintah kedua mendapatkan konfigurasi subnet bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam variabel $Subnet.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah keempat menambahkan konfigurasi IP front-end bernama FrontendIP02 menggunakan $Subnet dari perintah kedua.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat cmdlet ini menambahkan konfigurasi IP front-end.

```yaml
Type: PSApplicationGateway
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Menentukan nama konfigurasi IP front-end yang akan ditambahkan.

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

### -PrivateIPAddress
Menentukan alamat IP privat untuk ditambahkan sebagai IP front-end untuk gateway aplikasi.
Jika ditentukan, IP ini dialokasikan secara statis dari subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateLinkConfiguration
PrivateLinkConfiguration

```yaml
Type: PSApplicationGatewayPrivateLinkConfiguration
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateLinkConfigurationId
PrivateLinkConfigurationId

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIPAddress
Menentukan alamat IP publik yang ditambahkan cmdlet ini sebagai alamat IP front-end untuk gateway aplikasi.

```yaml
Type: PSPublicIpAddress
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIPAddressId
Menentukan ID alamat IP publik yang ditambahkan cmdlet ini sebagai alamat IP front-end untuk gateway aplikasi.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Menentukan subnet yang ditambahkan cmdlet ini sebagai konfigurasi IP front-end.
Jika Anda menentukan parameter ini, itu menyiratkan bahwa gateway aplikasi mendukung konfigurasi berbasis IP privat.
Jika parameter *PrivateIPAddress* ditentukan, parameter tersebut harus milik subnet ini.
Jika *PrivateIPAddress* tidak ditentukan, salah satu alamat IP dari subnet ini diambil secara dinamis sebagai alamat IP front-end gateway aplikasi.

```yaml
Type: PSSubnet
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Menentukan ID subnet yang ditambahkan cmdlet ini sebagai konfigurasi IP front-end.
Meneruskan subnet menyiratkan IP privat.
Jika parameter *PrivateIPAddress* ditentukan, parameter tersebut harus milik subnet ini.
Jika tidak, salah satu IP dari subnet ini secara dinamis diambil sebagai IP front-end gateway aplikasi.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Get-AzApplicationGatewayFrontendIPConfig](./Get-AzApplicationGatewayFrontendIPConfig.md)

[New-AzApplicationGatewayFrontendIPConfig](./New-AzApplicationGatewayFrontendIPConfig.md)

[Remove-AzApplicationGatewayFrontendIPConfig](./Remove-AzApplicationGatewayFrontendIPConfig.md)

[Set-AzApplicationGatewayFrontendIPConfig](./Set-AzApplicationGatewayFrontendIPConfig.md)


