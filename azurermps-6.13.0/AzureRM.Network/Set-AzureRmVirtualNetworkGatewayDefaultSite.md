---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: A27EE9C0-C7F5-4BF6-AE52-58087BD1B1C3
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermvirtualnetworkgatewaydefaultsite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGatewayDefaultSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGatewayDefaultSite.md
ms.openlocfilehash: 9c0eec0f38929efe188d8ab0ba8e30d31a16b717
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142985760"
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
Cmdlet **Set-AzureRmVirtualNetworkGatewayDefaultSite** menetapkan situs default tunneling paksa ke gateway jaringan virtual.
Terowongan paksa menyediakan cara bagi Anda untuk mengalihkan lalu lintas terikat internet dari mesin virtual Azure ke jaringan lokal Anda; hal ini memungkinkan Anda memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Terowongan paksa dilakukan dengan menggunakan terowongan jaringan privat virtual (VPN); terowongan ini memerlukan situs default, gateway lokal di mana semua lalu lintas Azure yang terikat internet diarahkan ulang.
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
Referensi objek yang disimpan dalam variabel bernama $LocalGateway mewakili gateway untuk dikonfigurasi sebagai situs default.
Perintah kedua kemudian membuat referensi objek ke gateway jaringan virtual dan menyimpan hasilnya dalam variabel bernama $VirtualGateway.
Perintah ketiga menggunakan cmdlet **Set-AzureRmVirtualNetworkGatewayDefaultSite** untuk menetapkan situs default ke ContosoVirtualGateway.

## PARAMETERS

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

### -GatewayDefaultSite
Menentukan referensi objek ke gateway jaringan lokal untuk ditetapkan sebagai situs default untuk jaringan maya yang ditentukan.
Anda bisa menggunakan cmdlet Get-AzureRmLocalNetworkGateway untuk membuat referensi objek ke gateway lokal.

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
Variabel $VirtualGateway kemudian dapat digunakan sebagai nilai parameter untuk parameter *VirtualNetworkGateway* :

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway
Parameter: VirtualNetworkGateway (ByValue)

### Microsoft.Azure.Commands.Network.Models.PSLocalNetworkGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## NOTES

## RELATED LINKS

[Get-AzureRmLocalNetworkGateway](./Get-AzureRmLocalNetworkGateway.md)

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[Hapus-AzureRmVirtualNetworkGatewayDefaultSite](./Remove-AzureRmVirtualNetworkGatewayDefaultSite.md)


