---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 65E9C4D5-4D2C-4039-A87B-4E693B97C4CB
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/remove-azurermvirtualnetworkgatewaydefaultsite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmVirtualNetworkGatewayDefaultSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmVirtualNetworkGatewayDefaultSite.md
ms.openlocfilehash: a2c6c51a1f9f22130436e7d0a0d5fd888bccfb99
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141882825"
---
# Remove-AzureRmVirtualNetworkGatewayDefaultSite

## SYNOPSIS
Menghapus situs default dari gateway jaringan virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway <PSVirtualNetworkGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmVirtualNetworkGatewayDefaultSite** menghapus situs default tunneling paksa dari gateway jaringan virtual.
Terowongan paksa menyediakan cara bagi Anda untuk mengalihkan lalu lintas terikat internet dari mesin virtual Azure ke jaringan lokal Anda; hal ini memungkinkan Anda memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Terowongan paksa dilakukan dengan menggunakan terowongan jaringan privat virtual (VPN); terowongan ini memerlukan situs default, gateway lokal di mana semua lalu lintas Azure yang terikat internet diarahkan ulang.
**Remove-AzureRmVirtualNetworkGatewayDefaultSite** menghapus situs default yang ditetapkan ke gateway.
Jika Anda melakukan ini, Anda perlu menggunakan Set-AzureRmVirtualNetworkGatewayDefaultSite untuk menetapkan situs default baru sebelum gateway bisa digunakan untuk pembuatan terowongan paksa.

## EXAMPLES

### Contoh 1: Menghapus situs default yang ditetapkan ke gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzureRmVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Remove-AzureRmVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway $Gateway
```

Contoh ini menghapus situs default yang saat ini ditetapkan ke gateway jaringan virtual bernama ContosoVirtualGateway.
Perintah pertama menggunakan **Get-AzureRmVirtualNetworkGateway** untuk membuat referensi objek ke gateway; referensi objek ini disimpan dalam variabel bernama $Gateway.
Perintah kedua kemudian menggunakan **Remove-AzureRmVirtualNetworkGatewayDefaultSite** untuk menghapus situs default yang ditetapkan ke gateway tersebut.

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

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual yang berisi situs default yang akan dihapus.
Anda bisa membuat referensi objek ke gateway jaringan virtual dengan menggunakan Get-AzureRmVirtualNetworkGateway dan menentukan nama gateway.

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

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## CATATAN

## RELATED LINKS

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[Set-AzureRmVirtualNetworkGatewayDefaultSite](./Set-AzureRmVirtualNetworkGatewayDefaultSite.md)


