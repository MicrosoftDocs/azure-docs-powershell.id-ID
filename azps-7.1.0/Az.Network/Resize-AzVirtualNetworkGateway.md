---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: DE2441FC-9504-4F3F-AEAF-37EDCD9B7275
online version: https://docs.microsoft.com/powershell/module/az.network/resize-azvirtualnetworkgateway
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Resize-AzVirtualNetworkGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Resize-AzVirtualNetworkGateway.md
ms.openlocfilehash: cb764a859d369feeffefbab365cfc3a6e6b998a7
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136722307"
---
# Resize-AzVirtualNetworkGateway

## SYNOPSIS
Mengubah ukuran gateway jaringan virtual yang sudah ada.

## SYNTAX

```
Resize-AzVirtualNetworkGateway -VirtualNetworkGateway <PSVirtualNetworkGateway> -GatewaySku <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Resize-AzVirtualNetworkGateway** memungkinkan Anda untuk mengubah unit stock-keeping (SKU) untuk gateway jaringan virtual.
SKU menentukan kapabilitas gateway, termasuk hal-hal seperti throughput dan jumlah maksimum IP yang diperbolehkan.
Azure mendukung Dasar, Standar, Performa Tinggi, VpnGw1, VpnGw2, VpnGw3, VpnGw1AZ, VpnGw2AZ, VpnGw3AZ, ErGw1AZ, ErGw2AZ, SKU ErGw3AZ (terkadang disebut sebagai SKU Kecil, Sedang, dan Besar).
Untuk informasi lebih lanjut tentang kemampuan setiap tipe SKU, lihat https://azure.microsoft.com/en-us/documentation/articles/vpn-gateway-about-vpngateways/ .
Perlu diingat bahwa SKU berbeda dalam harga dan kemampuannya.
Untuk informasi selengkapnya, lihat https://azure.microsoft.com/en-us/pricing/details/vpn-gateway/ .

## EXAMPLES

### Contoh 1: Mengubah ukuran gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Resize-AzVirtualNetworkGateway -VirtualNetworkGateway $Gateway -GatewaySku "Basic"
```

Contoh ini mengubah ukuran gateway jaringan virtual yang bernama ContosoVirtualGateway.
Perintah pertama membuat referensi objek ke ContosoVirtualGateway; referensi objek ini disimpan dalam variabel yang bernama $Gateway.
Perintah kedua lalu menggunakan cmdlet **Resize-AzVirtualNetworkGateway** untuk mengatur properti *GatewaySku* ke Basic.

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

### -GatewaySku
Menentukan tipe baru SKU gateway.
Nilai yang dapat diterima untuk parameter ini adalah:
- Dasar
- Standar
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## CATATAN
Anda tidak dapat mengubah ukuran dari SKU Dasar/Standar/HighPerformance ke SKU VpnGw1/VpnGw2/VpnGw3 yang baru. Ukuran lebih lanjut tidak diperbolehkan dari/ke VpnGw1AZ/VpnGw2AZ/VpnGw3AZ atau ErGw1AZ/ErGw2AZ/ErGw3AZ. Ubah ukuran hanya diperbolehkan dalam SKU 'seri' misalnya VpnGw1AZ dapat diubah ukurannya ke/dari VpnGw2AZ/VpnGw3AZ dan ErGw1AZ dapat diubah ukurannya ke/dari ErGw2AZ/ErGw3AZ. Lihat https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways untuk instruksi.

## RELATED LINKS

[Get-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[New-AzVirtualNetworkGateway](./New-AzVirtualNetworkGateway.md)

[Remove-AzVirtualNetworkGateway](./Remove-AzVirtualNetworkGateway.md)

[Reset-AzVirtualNetworkGateway](./Reset-AzVirtualNetworkGateway.md)

[Set-AzVirtualNetworkGateway](./Set-AzVirtualNetworkGateway.md)

[Get-AzVpnClientPackage](./Get-AzVpnClientPackage.md)
