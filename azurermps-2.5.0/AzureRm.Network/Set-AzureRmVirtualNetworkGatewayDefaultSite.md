---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: A27EE9C0-C7F5-4BF6-AE52-58087BD1B1C3
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermvirtualnetworkgatewaydefaultsite
schema: 2.0.0
ms.openlocfilehash: 463951ca6b6679671f330a3ddb0f9460a878a3d3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143168085"
---
# Set-AzureRmVirtualNetworkGatewayDefaultSite

## SYNOPSIS
Menyetel situs default untuk gateway jaringan virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway <PSVirtualNetworkGateway>
 -GatewayDefaultSite <PSLocalNetworkGateway> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVirtualNetworkGatewayDefaultSite** menetapkan situs default penerowongan paksa ke gateway jaringan virtual.
Penerowongan paksa menyediakan cara bagi Anda untuk mengalihkan lalu lintas yang terikat Internet dari komputer virtual Azure ke jaringan lokal Anda; ini memungkinkan Anda untuk memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Penerowongan paksa dilakukan dengan menggunakan terowongan jaringan privat maya (VPN) ; terowongan ini memerlukan situs default, gateway lokal tempat semua lalu lintas terikat Azure Internet dialihkan.
**Set-AzureRmVirtualNetworkGatewayDefaultSite** menyediakan cara untuk mengubah situs default yang ditetapkan ke gateway.

## EXAMPLES

### Contoh 1: Menetapkan situs default ke gateway jaringan virtual
```
PS C:\>$LocalGateway = Get-AzureRmLocalNetworkGateway -Name "ContosoLocalGateway " -ResourceGroup "ContosoResourceGroup"
PS C:\> $VirtualGateway = Get-AzureRmVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Set-AzureRmVirtualNetworkGatewayDefaultSite -GatewayDefaultSite $LocalGateway -VirtualNetworkGateway $VirtualGateway
```

Contoh ini menetapkan situs default ke gateway jaringan virtual bernama ContosoVirtualGateway.

Perintah pertama membuat referensi objek ke gateway lokal bernama ContosoLocalGateway.
Referensi objek yang disimpan dalam variabel bernama $LocalGateway mewakili gateway yang akan dikonfigurasi sebagai situs default

.
Perintah kedua kemudian membuat referensi objek ke gateway jaringan virtual dan menyimpan hasilnya dalam variabel bernama $VirtualGateway.

Perintah ketiga menggunakan cmdlet **Set-AzureRmVirtualNetworkGatewayDefaultSite** untuk menetapkan situs default ke ContosoVirtualGateway.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -GatewayDefaultSite
Menentukan referensi objek ke gateway jaringan lokal yang akan ditetapkan sebagai situs default untuk jaringan virtual yang ditentukan.
Anda bisa menggunakan cmdlet Get-AzureRmLocalNetworkGateway untuk membuat referensi objek ke gateway lokal.

```yaml
Type: PSLocalNetworkGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual tempat situs default akan ditetapkan.
Anda dapat membuat referensi objek ke gateway jaringan virtual dengan menggunakan **Get-AzureRmVirtualNetworkGateway** dan menentukan nama gateway.

Variabel $VirtualGateway kemudian dapat digunakan sebagai nilai parameter untuk parameter *VirtualNetworkGateway* :

```yaml
Type: PSVirtualNetworkGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Cmdlet ini menerima instans yang disalurkan dari objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway** .

## OUTPUTS

###  
Cmdlet ini memodifikasi instans objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway yang ada** .

## NOTES

## RELATED LINKS

[Get-AzureRmLocalNetworkGateway](./Get-AzureRmLocalNetworkGateway.md)

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[Remove-AzureRmVirtualNetworkGatewayDefaultSite](./Remove-AzureRmVirtualNetworkGatewayDefaultSite.md)


