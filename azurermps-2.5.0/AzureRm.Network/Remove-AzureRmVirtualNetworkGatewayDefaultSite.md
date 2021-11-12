---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 65E9C4D5-4D2C-4039-A87B-4E693B97C4CB
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/remove-azurermvirtualnetworkgatewaydefaultsite
schema: 2.0.0
ms.openlocfilehash: 5e1aadc295c418d6d97e143f4eddf5758a308157e82a90828c952dcf9b021cd0
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416610"
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
Cmdlet **Remove-AzureRmVirtualNetworkGatewayDefaultSite** menghapus situs default paksa dari gateway jaringan virtual.
Paksa membantu menyediakan cara Anda mengalihkan lalu lintas terikat Internet dari mesin virtual Azure ke jaringan lokal; ini memungkinkan Anda untuk memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Upaya paksa dilakukan menggunakan vpn jaringan privat virtual (VPN, Virtual Private Network) vpn; dasbor ini memerlukan situs default, gateway lokal tempat semua lalu lintas terikat Internet Azure dialihkan.

**Remove-AzureRmVirtualNetworkGatewayDefaultSite** menghapus situs default yang ditetapkan ke gateway.
Jika Anda melakukan hal ini Anda akan perlu menggunakan Set-AzureRmVirtualNetworkGatewayDefaultSite untuk menetapkan situs default baru sebelum gateway bisa digunakan untuk paksa bekerja.

## EXAMPLES

### Contoh 1: Menghapus situs default yang ditetapkan ke gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzureRmVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Remove-AzureRmVirtualNetworkGatewayDefaultSite -VirtualNetworknGateway $Gateway
```

Contoh ini menghapus situs default yang saat ini ditetapkan ke gateway jaringan virtual yang bernama ContosoVirtualGateway.

Perintah pertama menggunakan **Get-AzureRmVirtualNetworkGateway** untuk membuat referensi objek ke gateway; referensi objek ini disimpan dalam variabel yang bernama $Gateway.

Perintah kedua lalu menggunakan **Remove-AzureRmVirtualNetworkGatewayDefaultSite** untuk menghapus situs default yang ditetapkan untuk gateway tersebut.

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

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual yang berisi situs default yang akan dihapus.
Anda bisa membuat referensi objek ke gateway jaringan virtual dengan menggunakan Get-AzureRmVirtualNetworkGateway dan menentukan nama gateway.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

###  
Cmdlet ini menerima contoh pipelined dari objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway.**

## OUTPUTS

###  
Cmdlet ini memodifikasi contoh contoh **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway yang** sudah ada.

## CATATAN

## RELATED LINKS

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[Set-AzureRmVirtualNetworkGatewayDefaultSite](./Set-AzureRmVirtualNetworkGatewayDefaultSite.md)


