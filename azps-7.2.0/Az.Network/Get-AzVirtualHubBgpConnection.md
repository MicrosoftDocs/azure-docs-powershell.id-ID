---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azvirtualhubbgpconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVirtualHubBgpConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVirtualHubBgpConnection.md
ms.openlocfilehash: ad38939d9eb82066a32ad0abcef5fe995ee6709e
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138270107"
---
# Get-AzVirtualHubBgpConnection

## SYNOPSIS
Cmdlet Get-AzVirtualHubBgpConnection mendapatkan Koneksi BGP Virtual WAN Hub di Virtual WAN Hub atau mencantumkan semua Koneksi BGP Virtual WAN Hub di Virtual WAN Hub.

## SYNTAX

### ByVirtualHubName (Default)
```
Get-AzVirtualHubBgpConnection -ResourceGroupName <String> -VirtualHubName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByVirtualHubObject
```
Get-AzVirtualHubBgpConnection [-Name <String>] -VirtualHub <PSVirtualHub>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByHubBgpConnectionResourceId
```
Get-AzVirtualHubBgpConnection -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzVirtualHubBgpConnection mendapatkan Koneksi BGP Virtual WAN Hub di Virtual WAN Hub atau mencantumkan semua Koneksi BGP Virtual WAN Hub di Virtual WAN Hub.

## EXAMPLES

### Contoh 1

```powershell
PS C:\> New-AzResourceGroup -Location "West US" -Name "testRG"
PS C:\> $frontendSubnet = New-AzVirtualNetworkSubnetConfig -Name frontendSubnet -AddressPrefix "192.168.1.0/24"
PS C:\> $backendSubnet  = New-AzVirtualNetworkSubnetConfig -Name backendSubnet  -AddressPrefix "192.168.2.0/24"
PS C:\> $remoteVirtualNetwork = New-AzVirtualNetwork -Name "testVirtualNetwork" -ResourceGroupName "testRG" -Location "West US" -AddressPrefix "192.168.0.0/16" -Subnet $frontendSubnet,$backendSubnet
PS C:\> $virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "testWan" -Location "West US"
PS C:\> New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "testHub" -AddressPrefix "10.0.1.0/24"
PS C:\> $hubVnetConnection = New-AzVirtualHubVnetConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -Name "testVnetConnection" -RemoteVirtualNetwork $remoteVirtualNetwork
PS C:\> New-AzVirtualHubBgpConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -PeerIp 192.168.1.5 -PeerAsn 20000 -Name "testBgpConnection" -VirtualHubVnetConnection $hubVnetConnection

PS C:\> Get-AzVirtualHubBgpConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -Name "testBgpConnection"

Name                        : testBgpConnection
Id                          : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/bgpConnections/testBgpConnection
HubVirtualNetworkConnection : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/hubVirtualNetworkConnections/testVnetConnection
PeerAsn                     : 20000
PeerIp                      : 192.168.1.5
```

Opsi di atas akan membuat grup sumber daya, Virtual WAN, Virtual Network, Virtual WAN Hub di AS Barat dan menyambungkan Virtual Network ke Virtual WAN Hub di grup sumber daya tersebut di Azure. Koneksi BGP Virtual WAN Hub akan dibuat setelah itu, yang akan membuat Virtual WAN Hub dengan peralatan jaringan yang digunakan di Jaringan Virtual.

Setelah Koneksi BGP Virtual WAN Hub dibuat, Koneksi BGP akan mendapatkan Koneksi BGP menggunakan nama grup sumber dayanya, nama Virtual WAN Hub dan nama Koneksi BGP.

### Contoh 2

```powershell
PS C:\> Get-AzVirtualHubBgpConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -Name test*

Name                        : testBgpConnection1
Id                          : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/bgpConnections/testBgpConnection1
HubVirtualNetworkConnection : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/hubVirtualNetworkConnections/testVnetConnection
PeerAsn                     : 20000
PeerIp                      : 192.168.1.5

Name                        : testBgpConnection2
Id                          : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/bgpConnections/testBgpConnection2
HubVirtualNetworkConnection : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/hubVirtualNetworkConnections/testVnetConnection
PeerAsn                     : 20000
PeerIp                      : 192.168.1.6
```

Cmdlet ini mencantumkan semua Koneksi BGP Virtual WAN Hub dimulai dengan "uji" menggunakan nama grup sumber daya dan nama Virtual WAN Hub.

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
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName, ByVirtualHubObject
Aliases: ResourceName, BgpConnectionName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: System.String
Parameter Sets: ByHubBgpConnectionResourceId
Aliases: BgpConnectionId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHub
Sumber daya hub virtual.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualHub
Parameter Sets: ByVirtualHubObject
Aliases: ParentObject, ParentVirtualHub

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHubName
Nama hub virtual.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName
Aliases: ParentResourceName, ParentVirtualHubName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBgpConnection

## CATATAN

## RELATED LINKS

[New-AzVirtualHubBgpConnection](./Get-AzVirtualHubBgpConnection.md)

[Remove-AzVirtualHubBgpConnection](./Remove-AzVirtualHubBgpConnection.md)

[Update-AzVirtualHubBgpConnection](./Update-AzVirtualHubBgpConnection.md)