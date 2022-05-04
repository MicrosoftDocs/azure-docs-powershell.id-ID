---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvirtualhubbgpconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualHubBgpConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualHubBgpConnection.md
ms.openlocfilehash: 3c5f8937c3b7af484cafd5ac11243dc2a1deb1e3
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144604220"
---
# New-AzVirtualHubBgpConnection

## SYNOPSIS
Cmdlet New-AzVirtualHubBgpConnection membuat sumber daya HubBgpConnection yang mengintip Router Azure Virtual WAN Hub dengan serekan berkemampuan BGP di jaringan virtual yang terhubung ke Virtual WAN Hub.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azvirtualhubbgpconnection) untuk informasi terbaru.

## SYNTAX

### ByVirtualHubNameByHubVirtualNetworkConnectionObject (Default)
```
New-AzVirtualHubBgpConnection -ResourceGroupName <String> -VirtualHubName <String> -PeerIp <String>
 -PeerAsn <UInt32> -Name <String> -VirtualHubVnetConnection <PSHubVirtualNetworkConnection> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubNameByHubVirtualNetworkConnectionResourceId
```
New-AzVirtualHubBgpConnection -ResourceGroupName <String> -VirtualHubName <String> -PeerIp <String>
 -PeerAsn <UInt32> -Name <String> -VirtualHubVnetConnectionId <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubObjectByHubVirtualNetworkConnectionObject
```
New-AzVirtualHubBgpConnection -PeerIp <String> -PeerAsn <UInt32> -Name <String>
 -VirtualHubVnetConnection <PSHubVirtualNetworkConnection> -VirtualHub <PSVirtualHub> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubResourceIdByHubVirtualNetworkConnectionObject
```
New-AzVirtualHubBgpConnection -PeerIp <String> -PeerAsn <UInt32> -Name <String>
 -VirtualHubVnetConnection <PSHubVirtualNetworkConnection> -VirtualHubId <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId
```
New-AzVirtualHubBgpConnection -PeerIp <String> -PeerAsn <UInt32> -Name <String>
 -VirtualHubVnetConnectionId <String> -VirtualHub <PSVirtualHub> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubResourceIdByHubVirtualNetworkConnectionResourceId
```
New-AzVirtualHubBgpConnection -PeerIp <String> -PeerAsn <UInt32> -Name <String>
 -VirtualHubVnetConnectionId <String> -VirtualHubId <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzVirtualHubBgpConnection membuat sumber daya HubBgpConnection yang mengintip Router Azure Virtual WAN Hub dengan serekan berkemampuan BGP di jaringan virtual yang terhubung ke Virtual WAN Hub.

## EXAMPLES

### Contoh 1
```powershell
New-AzResourceGroup -Location "West US" -Name "testRG"
$frontendSubnet = New-AzVirtualNetworkSubnetConfig -Name frontendSubnet -AddressPrefix "192.168.1.0/24"
$backendSubnet  = New-AzVirtualNetworkSubnetConfig -Name backendSubnet  -AddressPrefix "192.168.2.0/24"
$remoteVirtualNetwork = New-AzVirtualNetwork -Name "testVirtualNetwork" -ResourceGroupName "testRG" -Location "West US" -AddressPrefix "192.168.0.0/16" -Subnet $frontendSubnet,$backendSubnet
$virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "testWan" -Location "West US"
New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "testHub" -AddressPrefix "10.0.1.0/24"
$hubVnetConnection = New-AzVirtualHubVnetConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -Name "testVnetConnection" -RemoteVirtualNetwork $remoteVirtualNetwork
New-AzVirtualHubBgpConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -PeerIp 192.168.1.5 -PeerAsn 20000 -Name "testBgpConnection" -VirtualHubVnetConnection $hubVnetConnection
```

```output
Name                        : testBgpConnection
Id                          : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/bgpConnections/testBgpConnection
HubVirtualNetworkConnection : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/hubVirtualNetworkConnections/testVnetConnection
PeerAsn                     : 20000
PeerIp                      : 192.168.1.5
```

Hal di atas akan membuat grup sumber daya, Virtual WAN, Virtual Network, Virtual WAN Hub di US Barat dan menyambungkan Virtual Network ke Virtual WAN Hub di grup sumber daya tersebut di Azure. Koneksi BGP Virtual WAN Hub akan dibuat setelahnya yang akan melakukan peering Virtual WAN Hub dengan appliance jaringan yang disebarkan di Virtual Network.

### Contoh 2
```powershell
$hubVnetConnection = Get-AzVirtualHubVnetConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -Name "testVnetConnection"
Get-AzVirtualHub -ResourceGroupName "testRG" -Name "testHub" | New-AzVirtualHubBgpConnection -PeerIp 192.168.1.5 -PeerAsn 20000 -Name "testBgpConnection" -VirtualHubVnetConnection $hubVnetConnection
```

```output
Name                        : testBgpConnection
Id                          : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/bgpConnections/testBgpConnection
HubVirtualNetworkConnection : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/hubVirtualNetworkConnections/testVnetConnection
PeerAsn                     : 20000
PeerIp                      : 192.168.1.5
```

Hal di atas akan membuat Virtual WAN Hub BGP Connection untuk Virtual WAN Hub yang ada dan Virtual WAN Hub Vnet Connection menggunakan powershell piping pada output dari Get-AzVirtualHub.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Name
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerAsn
ASN serekan.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerIp
IP serekan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubNameByHubVirtualNetworkConnectionResourceId
Aliases:

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
Parameter Sets: ByVirtualHubObjectByHubVirtualNetworkConnectionObject, ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId
Aliases: ParentObject, ParentVirtualHub

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHubId
Id sumber daya hub virtual.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubResourceIdByHubVirtualNetworkConnectionObject, ByVirtualHubResourceIdByHubVirtualNetworkConnectionResourceId
Aliases: ParentResourceId, ParentVirtualHubId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHubName
Nama hub virtual.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubNameByHubVirtualNetworkConnectionResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHubVnetConnection
Sumber daya VirtualHubVnetConnection.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSHubVirtualNetworkConnection
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubObjectByHubVirtualNetworkConnectionObject, ByVirtualHubResourceIdByHubVirtualNetworkConnectionObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHubVnetConnectionId
Id sumber daya VirtualHubVnetConnection.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionResourceId, ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId, ByVirtualHubResourceIdByHubVirtualNetworkConnectionResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

### Microsoft.Azure.Commands.Network.Models.PSHubVirtualNetworkConnection

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBgpConnection

## NOTES

## RELATED LINKS

[Get-AzVirtualHubgpConnection](./Get-AzVirtualHubBgpConnection.md)

[Remove-AzVirtualHubgpConnection](./Remove-AzVirtualHubBgpConnection.md)

[Update-AzVirtualHubgpConnection](./Update-AzVirtualHubBgpConnection.md)
