---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 65E9C4D5-4D2C-4039-A87B-4E693B97C4CB
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azvirtualnetworkgatewaydefaultsite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkGatewayDefaultSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkGatewayDefaultSite.md
ms.openlocfilehash: bfcd9368570ad616a501fc3a633ae6dc5aa89ff2
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136537052"
---
# Remove-AzVirtualNetworkGatewayDefaultSite

## SYNOPSIS
Menghapus situs default dari gateway jaringan virtual.

## SYNTAX

```
Remove-AzVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway <PSVirtualNetworkGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzVirtualNetworkGatewayDefaultSite** menghapus situs default paksa dari gateway jaringan virtual.
Paksa membantu menyediakan cara Anda mengalihkan lalu lintas terikat Internet dari mesin virtual Azure ke jaringan lokal; ini memungkinkan Anda untuk memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Upaya paksa dilakukan menggunakan vpn jaringan privat virtual (VPN, Virtual Private Network) vpn; dasbor ini memerlukan situs default, gateway lokal tempat semua lalu lintas terikat Internet Azure dialihkan.
**Remove-AzVirtualNetworkGatewayDefaultSite** menghapus situs default yang ditetapkan untuk gateway.
Jika Anda melakukan hal ini Anda akan perlu menggunakan Set-AzVirtualNetworkGatewayDefaultSite untuk menetapkan situs default baru sebelum gateway bisa digunakan untuk paksa bekerja.

## EXAMPLES

### Contoh 1: Menghapus situs default yang ditetapkan ke gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Remove-AzVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway $Gateway
```

Contoh ini menghapus situs default yang saat ini ditetapkan ke gateway jaringan virtual yang bernama ContosoVirtualGateway.
Perintah pertama menggunakan **Get-AzVirtualNetworkGateway** untuk membuat referensi objek ke gateway; referensi objek ini disimpan dalam variabel yang bernama $Gateway.
Perintah kedua lalu menggunakan **Remove-AzVirtualNetworkGatewayDefaultSite** untuk menghapus situs default yang ditetapkan untuk gateway itu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual yang berisi situs default yang akan dihapus.
Anda bisa membuat referensi objek ke gateway jaringan virtual dengan menggunakan Get-AzVirtualNetworkGateway dan menentukan nama gateway.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## CATATAN

## RELATED LINKS

[Get-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Set-AzVirtualNetworkGatewayDefaultSite](./Set-AzVirtualNetworkGatewayDefaultSite.md)


