---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 2C024C32-1B03-4BAA-AD31-4974D414C998
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermapplicationgatewayfrontendipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmApplicationGatewayFrontendIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmApplicationGatewayFrontendIPConfig.md
ms.openlocfilehash: e5bbe82276cb356da1e5a66c45145c7daa1d8769
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141777083"
---
# Set-AzureRmApplicationGatewayFrontendIPConfig

## SYNOPSIS
Mengubah konfigurasi alamat IP ujung depan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResourceId
```
Set-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-SubnetId <String>] [-PublicIPAddressId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
Set-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-PrivateIPAddress <String>] [-Subnet <PSSubnet>] [-PublicIPAddress <PSPublicIpAddress>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmApplicationGatewayFrontendIPConfig** memperbarui konfigurasi IP front-end.
Gateway aplikasi mendukung dua tipe alamat IP ujung depan: 
- Alamat IP publik
- Alamat IP privat yang konfigurasinya menggunakan Internal Load Balancing (ILB) Gateway aplikasi bisa memiliki paling banyak satu alamat IP publik dan satu alamat IP privat.
Alamat IP publik dan alamat IP pribadi harus ditambahkan secara terpisah sebagai alamat IP ujung depan.

## EXAMPLES

### Contoh 1: Mengatur IP publik sebagai IP ujung depan gateway aplikasi
```
PS C:\>$PublicIp = New-AzureRmPublicIpAddress -ResourceGroupName "ResourceGroup01" -Name "PublicIp01" -location "West US" -AllocationMethod Dynamic
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontEndIp01" -PublicIPAddress $PublicIp
```

Perintah pertama membuat objek alamat IP publik dan menyimpannya dalam variabel $PublicIp.
Perintah kedua mendapatkan gateway aplikasi bernama ApplicationGateway01 milik grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah ketiga memperbarui konfigurasi IP ujung depan bernama FrontEndIp01, untuk gateway di $AppGw, menggunakan alamat yang disimpan di $PublicIp.

### Contoh 2: Mengatur IP privat statis sebagai IP ujung depan gateway aplikasi
```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet -PrivateIPAddress 10.0.1.1
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $VNet.
Perintah kedua mendapatkan konfigurasi subnet bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam variabel $Subnet.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 milik grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah keempat menambahkan konfigurasi IP front-end bernama FrontendIP02 menggunakan $Subnet dari perintah kedua dan alamat IP pribadi 10.0.1.1.

### Contoh 3: Mengatur IP privat dinamis sebagai IP ujung depan gateway aplikasi
```
PS C:\>$VNet = Get-AzureRmvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureRmApplicationGatewayFrontendIPConfig -ApplicationGateway $AppGw -Name "FrontendIP02" -Subnet $Subnet
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $VNet.
Perintah kedua mendapatkan konfigurasi subnet bernama Subnet01 menggunakan $VNet dari perintah pertama dan menyimpannya dalam variabel $Subnet.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 milik grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah keempat menambahkan konfigurasi IP ujung depan bernama FrontendIP02 menggunakan $Subnet dari perintah kedua.

## PARAMETERS

### -ApplicationGateway
Menentukan objek gateway aplikasi untuk mengubah konfigurasi IP ujung depan.

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
Menentukan nama konfigurasi IP ujung depan yang diubah cmdlet ini.

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
Menentukan alamat IP privat.
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
Menentukan alamat IP publik.

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
Menentukan ID alamat IP publik.

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
Menentukan subnet yang digunakan gateway aplikasi.
Tentukan parameter ini jika gateway menggunakan alamat IP privat.
Jika alamat *PrivateIPAddress* ditentukan, alamat harus berada dalam subnet ini.
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
Menentukan ID subnet.
Tentukan parameter ini jika gateway menggunakan alamat IP privat.
Jika parameter *PrivateIPAddress* ditentukan, parameter tersebut harus dimiliki oleh subnet ini.
Jika *PrivateIPAddress* tidak ditentukan, salah satu alamat IP dari subnet ini dipilih secara dinamis sebagai alamat IP ujung depan gateway aplikasi.

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

[Add-AzureRmApplicationGatewayFrontendIPConfig](./Add-AzureRmApplicationGatewayFrontendIPConfig.md)

[Add-AzureRmApplicationGatewayFrontendIPConfig](./Add-AzureRmApplicationGatewayFrontendIPConfig.md)

[Get-AzureRmApplicationGatewayFrontendIPConfig](./Get-AzureRmApplicationGatewayFrontendIPConfig.md)

[New-AzureRmApplicationGatewayFrontendIPConfig](./New-AzureRmApplicationGatewayFrontendIPConfig.md)

[Hapus-AzureRmApplicationGatewayFrontendIPConfig](./Remove-AzureRmApplicationGatewayFrontendIPConfig.md)


