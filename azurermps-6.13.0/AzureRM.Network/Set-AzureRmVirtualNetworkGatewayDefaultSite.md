---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: A27EE9C0-C7F5-4BF6-AE52-58087BD1B1C3
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermvirtualnetworkgatewaydefaultsite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGatewayDefaultSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGatewayDefaultSite.md
ms.openlocfilehash: cd290b7fb9874d03c6bb5dc4fff11bd01777fae1648c2e1938d448b5f13782a3
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132414662"
---
# Set-AzureRmVirtualNetworkGatewayDefaultSite

## SYNOPSIS
Mengatur situs default untuk gateway jaringan virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway <PSVirtualNetworkGateway>
 -GatewayDefaultSite <PSLocalNetworkGateway> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVirtualNetworkGatewayDefaultSite** menetapkan situs default bawaan paksa ke gateway jaringan virtual.
Paksa membantu menyediakan cara Anda mengalihkan lalu lintas terikat Internet dari mesin virtual Azure ke jaringan lokal; ini memungkinkan Anda untuk memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Upaya paksa dilakukan menggunakan vpn jaringan privat virtual (VPN, Virtual Private Network) vpn; dasbor ini memerlukan situs default, gateway lokal tempat semua lalu lintas terikat Internet Azure dialihkan.
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
Referensi objek yang disimpan dalam variabel yang bernama $LocalGateway mewakili gateway yang akan dikonfigurasi sebagai situs default.
Perintah kedua lalu membuat referensi objek ke gateway jaringan virtual dan menyimpan hasilnya dalam variabel yang bernama $VirtualGateway.
Perintah ketiga menggunakan cmdlet **Set-AzureRmVirtualNetworkGatewayDefaultSite** untuk menetapkan situs default ke ContosoVirtualGateway.

## PARAMETERS

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

### -GatewayDefaultSite
Menentukan referensi objek ke gateway jaringan lokal untuk ditetapkan sebagai situs default untuk jaringan virtual yang ditentukan.
Anda bisa menggunakan cmdlet Get-AzureRmLocalNetworkGateway cmdlet untuk membuat referensi objek ke gateway lokal.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSLocalNetworkGateway
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
Anda bisa membuat referensi objek ke gateway jaringan virtual dengan menggunakan **Get-AzureRmVirtualNetworkGateway** dan menentukan nama gateway.
Variabel $VirtualGateway lalu bisa digunakan sebagai nilai parameter untuk parameter *VirtualNetworkGateway:*

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway
Parameter: VirtualNetworkGateway (ByValue)

### Microsoft.Azure.Commands.Network.Models.PSLocalNetworkGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## CATATAN

## RELATED LINKS

[Get-AzureRmLocalNetworkGateway](./Get-AzureRmLocalNetworkGateway.md)

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[Remove-AzureRmVirtualNetworkGatewayDefaultSite](./Remove-AzureRmVirtualNetworkGatewayDefaultSite.md)


