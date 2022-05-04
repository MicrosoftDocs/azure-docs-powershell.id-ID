---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: DE2441FC-9504-4F3F-AEAF-37EDCD9B7275
online version: https://docs.microsoft.com/powershell/module/az.network/resize-azvirtualnetworkgateway
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Resize-AzVirtualNetworkGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Resize-AzVirtualNetworkGateway.md
ms.openlocfilehash: 1b1025f351f6265cf40627aa076dd4d9fe893907
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144702351"
---
# Resize-AzVirtualNetworkGateway

## SYNOPSIS
Mengubah ukuran gateway jaringan virtual yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/resize-azvirtualnetworkgateway) untuk informasi terbaru.

## SYNTAX

```
Resize-AzVirtualNetworkGateway -VirtualNetworkGateway <PSVirtualNetworkGateway> -GatewaySku <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Resize-AzVirtualNetworkGateway** memungkinkan Anda mengubah unit penyimpanan stok (SKU) untuk gateway jaringan virtual.
SKU menentukan kemampuan gateway, termasuk hal-hal seperti throughput dan jumlah maksimum terowongan IP yang diizinkan.
Azure mendukung SKU Dasar, Standar, Performa Tinggi, VpnGw1, VpnGw2, VpnGw3, VpnGw1AZ, VpnGw2AZ, VpnGw3AZ, ErGw1AZ, ErGw2AZ, ErGw3AZ (terkadang disebut sebagai SKU Kecil, Sedang, dan Besar).
Untuk informasi terperinci tentang kemampuan setiap jenis SKU, lihat https://azure.microsoft.com/en-us/documentation/articles/vpn-gateway-about-vpngateways/.
Perlu diingat bahwa SKU berbeda dalam harga serta kemampuan.
Untuk informasi selengkapnya, lihat https://azure.microsoft.com/en-us/pricing/details/vpn-gateway/.

## EXAMPLES

### Contoh 1: Mengubah ukuran gateway jaringan virtual
```powershell
$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
Resize-AzVirtualNetworkGateway -VirtualNetworkGateway $Gateway -GatewaySku "Basic"
```

Contoh ini mengubah ukuran gateway jaringan virtual bernama ContosoVirtualGateway.
Perintah pertama membuat referensi objek ke ContosoVirtualGateway; referensi objek ini disimpan dalam variabel bernama $Gateway.
Perintah kedua kemudian menggunakan cmdlet **Resize-AzVirtualNetworkGateway** untuk mengatur properti *GatewaySku* ke Dasar.

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

### -GatewaySku
Menentukan jenis SKU gateway baru.
Nilai yang dapat diterima untuk parameter ini adalah:
- Dasar
- Standard
- Performa Tinggi
- VpnGw1
- VpnGw2
- VpnGw3
- VpnGw1AZ
- VpnGw2AZ
- VpnGw3AZ
- ErGw1AZ
- ErGw2AZ
- ErGw3AZ

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard, HighPerformance, UltraPerformance, VpnGw1, VpnGw2, VpnGw3, VpnGw1AZ, VpnGw2AZ, VpnGw3AZ, ErGw1AZ, ErGw2AZ, ErGw3AZ

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual yang akan diubah ukurannya.
Anda bisa membuat referensi objek ini dengan menggunakan Get-AzVirtualNetworkGateway dan menentukan nama gateway.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## NOTES
Anda tidak dapat mengubah ukuran dari SKU Dasar/Standar/HighPerformance ke SKU VpnGw1/VpnGw2/VpnGw3 baru. Mengubah ukuran lebih lanjut tidak diizinkan dari/ke VpnGw1AZ/VpnGw2AZ/VpnGw3AZ atau ErGw1AZ/ErGw2AZ/ErGw3AZ. Mengubah ukuran hanya diperbolehkan dalam 'seri' SKU, misalnya VpnGw1AZ dapat diubah ukurannya menjadi/dari VpnGw2AZ/VpnGw3AZ dan ErGw1AZ dapat diubah ukurannya menjadi/dari ErGw2AZ/ErGw3AZ. Lihat https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways untuk petunjuknya.

## RELATED LINKS

[Dapatkan-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Baru-GatewayJaringanVirtualAz](./New-AzVirtualNetworkGateway.md)

[Remove-AzVirtualNetworkGateway](./Remove-AzVirtualNetworkGateway.md)

[Reset-AzVirtualNetworkGateway](./Reset-AzVirtualNetworkGateway.md)

[Set-AzVirtualNetworkGateway](./Set-AzVirtualNetworkGateway.md)

[Get-AzVpnClientPackage](./Get-AzVpnClientPackage.md)
