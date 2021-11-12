---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 617FB2F9-05EA-4224-B9A9-2F00A7599486
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azvirtualnetworkgatewayconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzVirtualNetworkGatewayConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzVirtualNetworkGatewayConnection.md
ms.openlocfilehash: d3695216cdbda51ae3583218f7d0993894f472eb
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408891"
---
# Get-AzVirtualNetworkGatewayConnection

## SYNOPSIS
Mendapatkan Koneksi Gateway Jaringan Virtual

## SINTAKS

```
Get-AzVirtualNetworkGatewayConnection [-Name <String>] -ResourceGroupName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Virtual Network Gateway Connection adalah objek yang mewakili IPsec portal (Site-to-Site atau Vnet-to-Vnet) yang tersambung ke Virtual Network Gateway di Azure.
Cmdlet **Get-AzVirtualNetworkGatewayConnection** mengembalikan objek koneksi Anda berdasarkan Nama dan Nama Grup Sumber Daya.
Jika cmdlet **Get-AzVirtualNetworkGatewayConnection** diterbitkan tanpa menentukan parameter -Name, output tidak akan memperlihatkan detail ConnectionStatus dan SharedKey.

## CONTOH

### 1: Dapatkan Koneksi Gateway Jaringan Virtual
```
Get-AzVirtualNetworkGatewayConnection -Name myTunnel -ResourceGroupName myRG
```

Mengembalikan objek Koneksi Gateway Jaringan Virtual dengan nama "myTunnel" dalam grup sumber daya "myRG"

### 2: Mendapatkan semua Koneksi Gateway Jaringan Virtual menggunakan pemfilteran
```
Get-AzVirtualNetworkGatewayConnection -Name myTunnel* -ResourceGroupName myRG
```

Mengembalikan semua Koneksi Gateway Jaringan Virtual yang dimulai dengan "myTunnel" dalam grup sumber daya "myRG"

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

### -Nama
```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceGroupName
```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayConnection

## CATATAN

## LINK TERKAIT

[New-AzVirtualNetworkGatewayConnection](./New-AzVirtualNetworkGatewayConnection.md)

[Remove-AzVirtualNetworkGatewayConnection](./Remove-AzVirtualNetworkGatewayConnection.md)

[Set-AzVirtualNetworkGatewayConnection](./Set-AzVirtualNetworkGatewayConnection.md)
