---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 2C024C32-1B03-4BAA-AD31-4974D414C998
online version: https://docs.microsoft.com/powershell/module/az.network/set-azapplicationgatewayfrontendipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewayFrontendIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewayFrontendIPConfig.md
ms.openlocfilehash: 73cebe1327c6d17cab19d48fbbe837c6e70936f3
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140463995"
---
# Set-AzApplicationGatewayFrontendIPConfig

## SYNOPSIS
Mengubah konfigurasi alamat IP ujung-depan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/set-azapplicationgatewayfrontendipconfig) untuk informasi terkini.

## SYNTAX

### SetByResourceId
```
Set-AzApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-SubnetId <String>] [-PublicIPAddressId <String>]
 [-PrivateLinkConfigurationId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
Set-AzApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-Subnet <PSSubnet>] [-PublicIPAddress <PSPublicIpAddress>]
 [-PrivateLinkConfiguration <PSApplicationGatewayPrivateLinkConfiguration>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApplicationGatewayFrontendIPConfig** memperbarui konfigurasi IP front-end.
Gateway aplikasi mendukung dua tipe alamat IP ujung-depan: 
- Alamat IP publik
- Alamat IP privat di mana konfigurasi menggunakan Penyembang Muat Internal (ILB, Internal Load Balancing) Gateway aplikasi bisa memiliki paling banyak satu alamat IP publik dan satu alamat IP privat.
Alamat IP publik dan alamat IP privat harus ditambahkan secara terpisah sebagai alamat IP ujung-depan.

## EXAMPLES

### Contoh 1: Menyetel IP publik sebagai IP ujung-depan gateway aplikasi
```
PS C:\>$PublicIp = New-AzPublicIpAddress -ResourceGroupName "ResourceGroup01" -Name "PublicIp01" -location "West US" -AllocationMethod Dynamic
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontEndIp01" -PublicIPAddress $PublicIp
```

Perintah pertama membuat objek alamat IP publik dan menyimpannya di $PublicIp variabel.
Perintah kedua mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $AppGw lokal.
Perintah ketiga memperbarui konfigurasi IP ujung-depan bernama FrontEndIp01, untuk gateway di $AppGw, menggunakan alamat yang disimpan di $PublicIp.

### Contoh 2: Mengatur IP privat statis sebagai IP ujung-depan gateway aplikasi
```
PS C:\>$VNet = Get-AzVirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet -PrivateIPAddress 10.0.1.1
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $VNet sumber daya.
Perintah kedua mendapatkan konfigurasi subnet yang bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam $Subnet baru.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $AppGw lokal.
Perintah keempat menambahkan konfigurasi IP ujung-depan bernama FrontendIP02 menggunakan $Subnet dari perintah kedua dan alamat IP privat 10.0.1.1.

### Contoh 3: Mengatur IP privat dinamis sebagai IP ujung-depan gateway aplikasi
```
PS C:\>$VNet = Get-AzVirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $VNet sumber daya.
Perintah kedua mendapatkan konfigurasi subnet yang bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam $Subnet baru.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $AppGw lokal.
Perintah keempat menambahkan konfigurasi IP ujung-depan yang bernama FrontendIP02 menggunakan $Subnet dari perintah kedua.

## PARAMETERS

### -ApplicationGateway
Menentukan objek gateway aplikasi untuk memodifikasi konfigurasi IP front-end.

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

### -Nama
Menentukan nama konfigurasi IP ujung-depan yang dimodifikasi cmdlet ini.

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
Menentukan alamat IP privat.
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
Menentukan alamat IP publik.

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
Menentukan ID alamat IP publik.

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
Menentukan subnet yang digunakan gateway aplikasi.
Tentukan parameter ini jika gateway menggunakan alamat IP privat.
Jika alamat *PrivateIPAddress* ditentukan, alamat tersebut harus termasuk dalam subnet ini.
Jika *PrivateIPAddress* tidak ditentukan, salah satu alamat IP dari subnet ini dipilih secara dinamis sebagai alamat IP ujung-depan gateway aplikasi.

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
Menentukan ID subnet.
Tentukan parameter ini jika gateway menggunakan alamat IP privat.
Jika parameter *PrivateIPAddress* ditentukan, parameter tersebut harus termasuk dalam subnet ini.
Jika *PrivateIPAddress* tidak ditentukan, salah satu alamat IP dari subnet ini dipilih secara dinamis sebagai alamat IP ujung-depan gateway aplikasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Add-AzApplicationGatewayFrontendIPConfig](./Add-AzApplicationGatewayFrontendIPConfig.md)

[Add-AzApplicationGatewayFrontendIPConfig](./Add-AzApplicationGatewayFrontendIPConfig.md)

[Get-AzApplicationGatewayFrontendIPConfig](./Get-AzApplicationGatewayFrontendIPConfig.md)

[New-AzApplicationGatewayFrontendIPConfig](./New-AzApplicationGatewayFrontendIPConfig.md)

[Remove-AzApplicationGatewayFrontendIPConfig](./Remove-AzApplicationGatewayFrontendIPConfig.md)


