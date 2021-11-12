---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: AE8E26F2-CF8E-4340-936D-230731B5BA32
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azapplicationgatewayfrontendipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/New-AzApplicationGatewayFrontendIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/New-AzApplicationGatewayFrontendIPConfig.md
ms.openlocfilehash: dfbdebf2815bf94fcda5fb5a69804b55bb226d67
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425760"
---
# New-AzApplicationGatewayFrontendIPConfig

## SYNOPSIS
Membuat konfigurasi IP front-end untuk gateway aplikasi.

## SYNTAX

### SetByResourceId
```
New-AzApplicationGatewayFrontendIPConfig -Name <String> [-PrivateIPAddress <String>] [-SubnetId <String>]
 [-PublicIPAddressId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
New-AzApplicationGatewayFrontendIPConfig -Name <String> [-PrivateIPAddress <String>] [-Subnet <PSSubnet>]
 [-PublicIPAddress <PSPublicIpAddress>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewayFrontendIPConfig** membuat konfigurasi IP ujung-depan untuk gateway aplikasi Azure.
Gateway aplikasi mendukung dua tipe konfigurasi IP ujung-depan: 

- Alamat IP publik , alamat IP privat menggunakan penyeimbangan muat internal (ILB, Internal Load Balancing).

Gateway aplikasi bisa memiliki paling banyak satu alamat IP publik dan satu alamat IP privat.
Alamat IP publik dan alamat IP privat harus ditambahkan secara terpisah sebagai alamat IP ujung-depan.

## EXAMPLES

### Contoh 1: Membuat konfigurasi IP ujung-depan menggunakan objek sumber daya IP publik
```
PS C:\>$PublicIP = New-AzPublicIpAddress -ResourceGroupName "ResourceGroup01" -Name "PublicIP01" -location "West US" -AllocationMethod Dynamic
PS C:\> $FrontEnd = New-AzApplicationGatewayFrontendIPConfig -Name "FrontEndIP01" -PublicIPAddress $PublicIP
```

Perintah pertama membuat objek sumber daya IP publik dan menyimpannya di $PublicIP sumber daya.
Perintah kedua menggunakan $PublicIP untuk membuat konfigurasi IP ujung-depan baru bernama FrontEndIP01 dan menyimpannya dalam variabel $FrontEnd nya.

### Contoh 2: Membuat IP privat statis sebagai alamat IP ujung-depan
```
PS C:\>$VNet = Get-AzvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $FrontEnd = New-AzApplicationGatewayFrontendIPConfig -Name "FrontendIP02" -Subnet $Subnet -PrivateIPAddress 10.0.1.1
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $VNet sumber daya.
Perintah kedua mendapatkan konfigurasi subnet yang bernama Subnet01 $VNet dari perintah pertama dan menyimpannya dalam $Subnet baru.
Perintah ketiga membuat konfigurasi IP ujung-depan bernama FrontEndIP02 menggunakan $Subnet dari perintah kedua dan alamat IP privat 10.0.1.1, lalu menyimpannya dalam variabel $FrontEnd.

### Contoh 3: Buat IP privat dinamis sebagai alamat IP front-end
```
PS C:\>$VNet = Get-AzvirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet
PS C:\> $FrontEnd = New-AzApplicationGatewayFrontendIPConfig -Name "FrontendIP03" -Subnet $Subnet
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $VNet sumber daya.
Perintah kedua mendapatkan konfigurasi subnet yang bernama Subnet01 $VNet dari perintah pertama dan menyimpannya dalam $Subnet baru.
Perintah ketiga membuat konfigurasi IP ujung-depan bernama FrontEndIP03 menggunakan $Subnet dari perintah kedua, dan menyimpannya dalam variabel $FrontEnd bervariasi.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi IP ujung-depan yang dibuat cmdlet ini.

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
Menentukan alamat IP privat yang terkait cmdlet ini dengan alamat IP front-end gateway aplikasi.
Ini hanya dapat ditentukan jika subnet ditentukan.
IP ini dialokasikan secara statis dari subnet.

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

### -PublicIPAddress
Menentukan objek alamat IP publik yang terkait cmdlet ini dengan alamat IP front-end gateway aplikasi.

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
Menentukan ID alamat IP publik yang terkait cmdlet ini dengan IP front-end gateway aplikasi.

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
Menentukan objek subnet yang terkait dengan alamat IP front-end gateway aplikasi.
Jika Anda menentukan parameter ini, itu berarti bahwa gateway menggunakan alamat IP privat.
Jika parameter *PrivateIPAddresss* ditentukan, parameter harus berada dalam subnet yang ditentukan oleh parameter ini.
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
Menentukan ID subnet yang terkait dengan konfigurasi IP front-end gateway aplikasi.
Jika Anda menentukan parameter *Subnet,* maka gateway menggunakan alamat IP privat.
Jika parameter *PrivateIPAddress* ditentukan, parameter seharusnya termasuk ke subnet yang ditentukan oleh *Subnet*.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration

## CATATAN

## RELATED LINKS

[Add-AzApplicationGatewayFrontendIPConfig](./Add-AzApplicationGatewayFrontendIPConfig.md)

[Get-AzApplicationGatewayFrontendIPConfig](./Get-AzApplicationGatewayFrontendIPConfig.md)

[Remove-AzApplicationGatewayFrontendIPConfig](./Remove-AzApplicationGatewayFrontendIPConfig.md)

[Set-AzApplicationGatewayFrontendIPConfig](./Set-AzApplicationGatewayFrontendIPConfig.md)


