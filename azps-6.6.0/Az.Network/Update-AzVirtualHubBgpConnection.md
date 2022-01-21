---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/update-azvirtualhubbgpconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualHubBgpConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualHubBgpConnection.md
ms.openlocfilehash: bcda1cc3c5f3b4c8244b2eb64dd52c57a6b2daf3
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136389824"
---
# Update-AzVirtualHubBgpConnection

## SYNOPSIS
Cmdlet Update-AzVirtualHubBgpConnection memperbarui sumber daya HubBgpConnection yang sudah ada (Koneksi BGP Virtual WAN Hub).

## SYNTAX

### ByVirtualHubNameByHubVirtualNetworkConnectionObject (Default)
```
Update-AzVirtualHubBgpConnection -ResourceGroupName <String> -VirtualHubName <String> -Name <String>
 -PeerIp <String> -PeerAsn <UInt32> -VirtualHubVnetConnection <PSHubVirtualNetworkConnection> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubNameByHubVirtualNetworkConnectionResourceId
```
Update-AzVirtualHubBgpConnection -ResourceGroupName <String> -VirtualHubName <String> -Name <String>
 -PeerIp <String> -PeerAsn <UInt32> -VirtualHubVnetConnectionId <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubObjectByHubVirtualNetworkConnectionObject
```
Update-AzVirtualHubBgpConnection -Name <String> -PeerIp <String> -PeerAsn <UInt32>
 -VirtualHubVnetConnection <PSHubVirtualNetworkConnection> -VirtualHub <PSVirtualHub> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId
```
Update-AzVirtualHubBgpConnection -Name <String> -PeerIp <String> -PeerAsn <UInt32>
 -VirtualHubVnetConnectionId <String> -VirtualHub <PSVirtualHub> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionObject
```
Update-AzVirtualHubBgpConnection -PeerIp <String> -PeerAsn <UInt32>
 -VirtualHubVnetConnection <PSHubVirtualNetworkConnection> -ResourceId <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionResourceId
```
Update-AzVirtualHubBgpConnection -PeerIp <String> -PeerAsn <UInt32> -VirtualHubVnetConnectionId <String>
 -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByHubBgpConnectionObjectByHubVirtualNetworkConnectionObject
```
Update-AzVirtualHubBgpConnection [-PeerIp <String>] [-PeerAsn <UInt32>]
 -VirtualHubVnetConnection <PSHubVirtualNetworkConnection> -InputObject <PSBgpConnection> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByHubBgpConnectionObjectByHubVirtualNetworkConnectionResourceId
```
Update-AzVirtualHubBgpConnection [-PeerIp <String>] [-PeerAsn <UInt32>] -VirtualHubVnetConnectionId <String>
 -InputObject <PSBgpConnection> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByHubBgpConnectionObject
```
Update-AzVirtualHubBgpConnection [-PeerIp <String>] [-PeerAsn <UInt32>]
 [-VirtualHubVnetConnection <PSHubVirtualNetworkConnection>] [-VirtualHubVnetConnectionId <String>]
 -InputObject <PSBgpConnection> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Update-AzVirtualHubBgpConnection memperbarui sumber daya HubBgpConnection yang sudah ada (Koneksi BGP Virtual WAN Hub).

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
PS C:\> Update-AzVirtualHubBgpConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -PeerIp 192.168.1.6 -PeerAsn 20000 -Name "testBgpConnection" -VirtualHubVnetConnection $hubVnetConnection

Name                        : testBgpConnection
Id                          : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/bgpConnections/testBgpConnection
HubVirtualNetworkConnection : /subscriptions/{subscriptionId}/resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/testHub/hubVirtualNetworkConnections/testVnetConnection
PeerAsn                     : 20000
PeerIp                      : 192.168.1.6
```

Opsi di atas akan membuat grup sumber daya, Virtual WAN, Virtual Network, Virtual WAN Hub di AS Barat dan menyambungkan Virtual Network ke Virtual WAN Hub di grup sumber daya tersebut di Azure. Koneksi BGP Virtual WAN Hub akan dibuat setelah itu, yang akan membuat Virtual WAN Hub dengan peralatan jaringan yang digunakan di Jaringan Virtual. Koneksi BGP Virtual WAN Hub ini kemudian diperbarui agar memiliki IP Peer berbeda.

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

### -InputObject
Sumber daya koneksi bgp hub virtual.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSBgpConnection
Parameter Sets: ByHubBgpConnectionObjectByHubVirtualNetworkConnectionObject, ByHubBgpConnectionObjectByHubVirtualNetworkConnectionResourceId, ByHubBgpConnectionObject
Aliases: VirtualHubBgpConnection

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubNameByHubVirtualNetworkConnectionResourceId, ByVirtualHubObjectByHubVirtualNetworkConnectionObject, ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId
Aliases: ResourceName, BgpConnectionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerAsn
ASN peer.

```yaml
Type: System.UInt32
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubNameByHubVirtualNetworkConnectionResourceId, ByVirtualHubObjectByHubVirtualNetworkConnectionObject, ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId, ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionObject, ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.UInt32
Parameter Sets: ByHubBgpConnectionObjectByHubVirtualNetworkConnectionObject, ByHubBgpConnectionObjectByHubVirtualNetworkConnectionResourceId, ByHubBgpConnectionObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerIp
IP peer.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubNameByHubVirtualNetworkConnectionResourceId, ByVirtualHubObjectByHubVirtualNetworkConnectionObject, ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId, ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionObject, ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ByHubBgpConnectionObjectByHubVirtualNetworkConnectionObject, ByHubBgpConnectionObjectByHubVirtualNetworkConnectionResourceId, ByHubBgpConnectionObject
Aliases:

Required: False
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

### -ResourceId
Id sumber daya.

```yaml
Type: System.String
Parameter Sets: ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionObject, ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionResourceId
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
Parameter Sets: ByVirtualHubObjectByHubVirtualNetworkConnectionObject, ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId
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
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubNameByHubVirtualNetworkConnectionResourceId
Aliases: ParentResourceName, ParentVirtualHubName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHubvnetConnection
Sumber daya VirtualHubvnetConnection.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSHubVirtualNetworkConnection
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionObject, ByVirtualHubObjectByHubVirtualNetworkConnectionObject, ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionObject, ByHubBgpConnectionObjectByHubVirtualNetworkConnectionObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSHubVirtualNetworkConnection
Parameter Sets: ByHubBgpConnectionObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHubvnetConnectionId
Id sumber daya VirtualHubVnetConnection.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubNameByHubVirtualNetworkConnectionResourceId, ByVirtualHubObjectByHubVirtualNetworkConnectionResourceId, ByHubBgpConnectionResourceIdByHubVirtualNetworkConnectionResourceId, ByHubBgpConnectionObjectByHubVirtualNetworkConnectionResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ByHubBgpConnectionObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

### Microsoft.Azure.Commands.Network.Models.PSBgpConnection

### Microsoft.Azure.Commands.Network.Models.PSHubVirtualNetworkConnection

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBgpConnection

## CATATAN

## RELATED LINKS

[New-AzVirtualHubBgpConnection](./Update-AzVirtualHubBgpConnection.md)

[Get-AzVirtualHubBgpConnection](./Get-AzVirtualHubBgpConnection.md)

[Remove-AzVirtualHubBgpConnection](./Remove-AzVirtualHubBgpConnection.md)
