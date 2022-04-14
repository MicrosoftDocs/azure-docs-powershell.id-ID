---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 47FE9EF4-6000-4096-8F04-26A0C6661FDB
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azvirtualnetworksubnetconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkSubnetConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkSubnetConfig.md
ms.openlocfilehash: 0583eef8709758716418e02e922dfb2aa6bc2a3c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142079725"
---
# Remove-AzVirtualNetworkSubnetConfig

## SYNOPSIS
Menghapus konfigurasi subnet dari jaringan virtual.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azvirtualnetworksubnetconfig) untuk informasi terbaru.

## SYNTAX

```
Remove-AzVirtualNetworkSubnetConfig [-Name <String>] -VirtualNetwork <PSVirtualNetwork>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzVirtualNetworkSubnetConfig** menghapus subnet dari jaringan virtual Azure.

## EXAMPLES

### 1: Menghapus subnet dari jaringan virtual dan memperbarui jaringan virtual
```
New-AzResourceGroup -Name TestResourceGroup -Location centralus
    $frontendSubnet = New-AzVirtualNetworkSubnetConfig -Name frontendSubnet 
    -AddressPrefix "10.0.1.0/24"

$backendSubnet = New-AzVirtualNetworkSubnetConfig -Name backendSubnet -AddressPrefix 
    "10.0.2.0/24"

$virtualNetwork = New-AzVirtualNetwork -Name MyVirtualNetwork -ResourceGroupName 
    TestResourceGroup -Location centralus -AddressPrefix "10.0.0.0/16" -Subnet 
    $frontendSubnet,$backendSubnet

Remove-AzVirtualNetworkSubnetConfig -Name backendSubnet -VirtualNetwork 
    $virtualNetwork
    $virtualNetwork | Set-AzVirtualNetwork
```

Contoh ini membuat grup sumber daya dan jaringan virtual dengan dua subnet. Kemudian menggunakan perintah Remove-AzVirtualNetworkSubnetConfig untuk menghapus subnet backend dari representasi dalam memori jaringan virtual. Set-AzVirtualNetwork kemudian dipanggil untuk mengubah jaringan virtual di sisi server.

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

### -Nama
Menentukan nama konfigurasi subnet untuk dihapus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Menentukan objek **VirtualNetwork** yang berisi konfigurasi subnet untuk dihapus.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters] (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork

## CATATAN

## RELATED LINKS

[Add-AzVirtualNetworkSubnetConfig](./Add-AzVirtualNetworkSubnetConfig.md)

[Get-AzVirtualNetworkSubnetConfig](./Get-AzVirtualNetworkSubnetConfig.md)

[New-AzVirtualNetworkSubnetConfig](./New-AzVirtualNetworkSubnetConfig.md)

[Set-AzVirtualNetworkSubnetConfig](./Set-AzVirtualNetworkSubnetConfig.md)


