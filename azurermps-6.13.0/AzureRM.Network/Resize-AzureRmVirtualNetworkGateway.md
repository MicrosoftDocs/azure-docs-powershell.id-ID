---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: DE2441FC-9504-4F3F-AEAF-37EDCD9B7275
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/resize-azurermvirtualnetworkgateway
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Resize-AzureRmVirtualNetworkGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Resize-AzureRmVirtualNetworkGateway.md
ms.openlocfilehash: 0a8a5c4084813bac74ea907575d2bd26c3d8c5f3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141925899"
---
# Resize-AzureRmVirtualNetworkGateway

## SYNOPSIS
Mengubah ukuran gateway jaringan virtual yang sudah ada.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Resize-AzureRmVirtualNetworkGateway -VirtualNetworkGateway <PSVirtualNetworkGateway> -GatewaySku <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Resize-AzureRmVirtualNetworkGateway** memungkinkan Anda mengubah unit penyimpanan stok (SKU) untuk gateway jaringan virtual.
SKU menentukan kapabilitas gateway, termasuk hal-hal seperti throughput dan jumlah maksimal terowongan IP yang diperbolehkan.
Azure mendukung SKU Dasar, Standar, Berkinerja Tinggi, VpnGw1, VpnGw2, VpnGw1AZ, VpnGw2AZ, VpnGw3AZ, ErGw1AZ, ErGw2AZ, ErGw3AZ (terkadang disebut sebagai SKU Kecil, Sedang, dan Besar).
Untuk informasi mendetail tentang kapabilitas setiap tipe SKU, lihat https://azure.microsoft.com/en-us/documentation/articles/vpn-gateway-about-vpngateways/.
Ingatlah bahwa SKU berbeda dalam harga serta kemampuan.
Untuk informasi selengkapnya, lihat https://azure.microsoft.com/en-us/pricing/details/vpn-gateway/.

## EXAMPLES

### Contoh 1: Mengubah ukuran gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzureRmVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Resize-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $Gateway -GatewaySku "Basic"
```

Contoh ini mengubah ukuran gateway jaringan virtual bernama ContosoVirtualGateway.
Perintah pertama membuat referensi objek ke ContosoVirtualGateway; referensi objek ini disimpan dalam variabel bernama $Gateway.
Perintah kedua kemudian menggunakan cmdlet **Resize-AzureRmVirtualNetworkGateway** untuk mengatur properti *GatewaySku* ke Dasar.

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

### -Gatewaysku
Menentukan tipe baru SKU gateway.
Nilai yang dapat diterima untuk parameter ini adalah:
- Dasar
- Standar
- Kinerja Tinggi
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
Menentukan referensi objek ke gateway jaringan virtual untuk diubah ukurannya.
Anda bisa membuat referensi objek ini dengan menggunakan Get-AzureRmVirtualNetworkGateway dan menentukan nama gateway.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## CATATAN
Anda tidak dapat mengubah ukuran dari SKU Basic/Standard/HighPerformance ke SKU VpnGw1/VpnGw2/VpnGw3 yang baru. Ukuran lebih lanjut tidak diperbolehkan dari/ke VpnGw1AZ/VpnGw2AZ/VpnGw3AZ atau ErGw1AZ/ErGw2AZ/ErGw3AZ. Mengubah ukuran hanya diperbolehkan dalam 'seri' SKU, misalnya VpnGw1AZ dapat diubah ukurannya menjadi/dari VpnGw2AZ/VpnGw3AZ dan ErGw1AZ dapat diubah ukurannya menjadi/dari ErGw2AZ/ErGw3AZ. Lihat https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways instruksinya.

## RELATED LINKS

[Get-AzureRmVpnClientPackage](./Get-AzureRmVpnClientPackage.md)

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[Set-AzureRmVirtualNetworkGatewayVpnClientConfig](./Set-AzureRmVirtualNetworkGatewayVpnClientConfig.md)


