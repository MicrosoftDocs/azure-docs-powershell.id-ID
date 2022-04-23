---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: DE2441FC-9504-4F3F-AEAF-37EDCD9B7275
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/resize-azvirtualnetworkgateway
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Resize-AzVirtualNetworkGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Resize-AzVirtualNetworkGateway.md
ms.openlocfilehash: bd42d7cec30b7d42dcb1cdb3657f6681bf2cb6b0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143153368"
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
Cmdlet **Resize-AzVirtualNetworkGateway** memungkinkan Anda mengubah unit penyimpanan stok (SKU) untuk gateway jaringan virtual.
SKU menentukan kapabilitas gateway, termasuk hal-hal seperti throughput dan jumlah maksimal terowongan IP yang diperbolehkan.
Azure mendukung SKU Dasar, Standar, Berkinerja Tinggi, VpnGw1, VpnGw2 dan VpnGw3 (terkadang disebut sebagai SKU Kecil, Sedang, dan Besar).
Untuk informasi mendetail tentang kapabilitas setiap tipe SKU, lihat https://azure.microsoft.com/en-us/documentation/articles/vpn-gateway-about-vpngateways/.

Ingatlah bahwa SKU berbeda dalam harga serta kemampuan.
Untuk informasi selengkapnya, lihat https://azure.microsoft.com/en-us/pricing/details/vpn-gateway/.

## EXAMPLES

### Contoh 1: Mengubah ukuran gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Resize-AzVirtualNetworkGateway -VirtualNetworkGateway $Gateway -GatewaySku "Basic"
```

Contoh ini mengubah ukuran gateway jaringan virtual bernama ContosoVirtualGateway.

Perintah pertama membuat referensi objek ke ContosoVirtualGateway; referensi objek ini disimpan dalam variabel bernama $Gateway.

Perintah kedua kemudian menggunakan cmdlet **Resize-AzVirtualNetworkGateway** untuk mengatur properti *GatewaySku* ke Dasar.

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

### -Gatewaysku
Menentukan tipe baru SKU gateway.
Nilai yang dapat diterima untuk parameter ini adalah:

- Dasar
- Standar
- Kinerja Tinggi
- VpnGw1
- VpnGw2
- VpnGw3

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Basic, Standard, HighPerformance, UltraPerformance, VpnGw1, VpnGw2, VpnGw3

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual untuk diubah ukurannya.
Anda bisa membuat referensi objek ini dengan menggunakan Get-AzVirtualNetworkGateway dan menentukan nama gateway.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Cmdlet ini menerima instans pipelin objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway** .

## OUTPUTS

###  
Cmdlet ini mengubah instans objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway** yang sudah ada.

## NOTES
Anda tidak dapat mengubah ukuran dari SKU Basic/Standard/HighPerformance ke SKU VpnGw1/VpnGw2/VpnGw3 yang baru. Lihat https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways instruksinya.

## RELATED LINKS

[Get-AzVpnClientPackage](./Get-AzVpnClientPackage.md)

[Get-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Set-AzVirtualNetworkGatewayVpnClientConfig](./Set-AzVirtualNetworkGatewayVpnClientConfig.md)


