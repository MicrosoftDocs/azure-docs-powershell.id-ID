---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: A27EE9C0-C7F5-4BF6-AE52-58087BD1B1C3
online version: https://docs.microsoft.com/powershell/module/az.network/set-azvirtualnetworkgatewaydefaultsite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzVirtualNetworkGatewayDefaultSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzVirtualNetworkGatewayDefaultSite.md
ms.openlocfilehash: 8287bbf3b57a7bc29b844e7998f04ecdf8d1359e
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144704856"
---
# Set-AzVirtualNetworkGatewayDefaultSite

## SYNOPSIS
Menyetel situs default untuk gateway jaringan virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azvirtualnetworkgatewaydefaultsite) untuk informasi terbaru.

## SYNTAX

```
Set-AzVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway <PSVirtualNetworkGateway>
 -GatewayDefaultSite <PSLocalNetworkGateway> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVirtualNetworkGatewayDefaultSite** menetapkan situs default penerowongan paksa ke gateway jaringan virtual.
Penerowongan paksa menyediakan cara bagi Anda untuk mengalihkan lalu lintas yang terikat Internet dari komputer virtual Azure ke jaringan lokal Anda; ini memungkinkan Anda untuk memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Penerowongan paksa dilakukan dengan menggunakan terowongan jaringan privat maya (VPN) ; terowongan ini memerlukan situs default, gateway lokal tempat semua lalu lintas terikat Azure Internet dialihkan.
**Set-AzVirtualNetworkGatewayDefaultSite** menyediakan cara untuk mengubah situs default yang ditetapkan ke gateway.

## EXAMPLES

### Contoh 1: Menetapkan situs default ke gateway jaringan virtual
```powershell
$LocalGateway = Get-AzLocalNetworkGateway -Name "ContosoLocalGateway " -ResourceGroup "ContosoResourceGroup"
$VirtualGateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
Set-AzVirtualNetworkGatewayDefaultSite -GatewayDefaultSite $LocalGateway -VirtualNetworkGateway $VirtualGateway
```

Contoh ini menetapkan situs default ke gateway jaringan virtual bernama ContosoVirtualGateway.
Perintah pertama membuat referensi objek ke gateway lokal bernama ContosoLocalGateway.
Referensi objek yang disimpan dalam variabel bernama $LocalGateway mewakili gateway yang akan dikonfigurasi sebagai situs default .
Perintah kedua kemudian membuat referensi objek ke gateway jaringan virtual dan menyimpan hasilnya dalam variabel bernama $VirtualGateway.
Perintah ketiga menggunakan cmdlet **Set-AzVirtualNetworkGatewayDefaultSite** untuk menetapkan situs default ke ContosoVirtualGateway.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayDefaultSite
Menentukan referensi objek ke gateway jaringan lokal yang akan ditetapkan sebagai situs default untuk jaringan virtual yang ditentukan.
Anda bisa menggunakan cmdlet Get-AzLocalNetworkGateway untuk membuat referensi objek ke gateway lokal.

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
Anda dapat membuat referensi objek ke gateway jaringan virtual dengan menggunakan **Get-AzVirtualNetworkGateway** dan menentukan nama gateway.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

### Microsoft.Azure.Commands.Network.Models.PSLocalNetworkGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## NOTES

## RELATED LINKS

[Get-AzLocalNetworkGateway](./Get-AzLocalNetworkGateway.md)

[Dapatkan-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Remove-AzVirtualNetworkGatewayDefaultSite](./Remove-AzVirtualNetworkGatewayDefaultSite.md)


