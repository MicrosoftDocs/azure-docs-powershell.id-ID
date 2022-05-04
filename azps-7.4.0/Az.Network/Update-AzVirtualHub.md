---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/update-azvirtualhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualHub.md
ms.openlocfilehash: 2815f1cc9a7b58eacdc517e3e01b99a80fb7e9c2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144694982"
---
# Update-AzVirtualHub

## SYNOPSIS
Memperbarui hub virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/update-azvirtualhub) untuk informasi terbaru.

## SYNTAX

### ByVirtualHubName (Default)
```
Update-AzVirtualHub -ResourceGroupName <String> -Name <String> [-AddressPrefix <String>]
 [-HubVnetConnection <PSHubVirtualNetworkConnection[]>] [-RouteTable <PSVirtualHubRouteTable>]
 [-Tag <Hashtable>] [-Sku <String>] [-PreferredRoutingGateway <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubResourceId
```
Update-AzVirtualHub -ResourceId <String> [-AddressPrefix <String>]
 [-HubVnetConnection <PSHubVirtualNetworkConnection[]>] [-RouteTable <PSVirtualHubRouteTable>]
 [-Tag <Hashtable>] [-Sku <String>] [-PreferredRoutingGateway <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubObject
```
Update-AzVirtualHub -InputObject <PSVirtualHub> [-AddressPrefix <String>]
 [-HubVnetConnection <PSHubVirtualNetworkConnection[]>] [-RouteTable <PSVirtualHubRouteTable>]
 [-Tag <Hashtable>] [-Sku <String>] [-PreferredRoutingGateway <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzVirtualHub** memperbarui hub virtual.

## EXAMPLES

### Contoh 1

```powershell
New-AzResourceGroup -Location "West US" -Name "testRG"
$virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "myVirtualWAN" -Location "West US"
New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.1.0/24"
Update-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.2.0/24"
```

```output
VirtualWan                : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualWans/myVirtualWAN
ResourceGroupName         : testRG
Name                      : westushub
Id                        : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/westushub
AddressPrefix             : 10.0.2.0/24
RouteTable                : 
VirtualNetworkConnections : {}
Location                  : West US
Sku                  : Standard
Type                      : Microsoft.Network/virtualHubs
ProvisioningState         : Succeeded
```

Di atas akan membuat grup sumber daya "testRG", Virtual WAN dan Hub Virtual di AS Barat dalam grup sumber daya tersebut di Azure. Hub virtual akan memiliki ruang alamat "10.0.1.0/24".

### Contoh 2

```powershell
New-AzResourceGroup -Location "West US" -Name "testRG"
$virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "myVirtualWAN" -Location "West US"
New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.1.0/24"
$route1 = New-AzVirtualHubRoute -AddressPrefix @("10.0.0.0/16", "11.0.0.0/16") -NextHopIpAddress "12.0.0.5"
$route2 = New-AzVirtualHubRoute -AddressPrefix @("13.0.0.0/16") -NextHopIpAddress "14.0.0.5"
$routeTable = New-AzVirtualHubRouteTable -Route @($route1, $route2)
Update-AzVirtualHub -ResourceGroupName "testRG" -Name "westushub" -RouteTable $routeTable
```

```output
VirtualWan                : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualWans/myVirtualWAN
ResourceGroupName         : testRG
Name                      : westushub
Id                        : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/westushub
AddressPrefix             : 192.168.2.0/24
RouteTable                : Microsoft.Azure.Commands.Network.Models.PSVirtualHubRouteTable
VirtualNetworkConnections : {}
Location                  : West US
Sku                  : Standard
Type                      : Microsoft.Network/virtualHubs
ProvisioningState         : Succeeded
```

Di atas akan membuat grup sumber daya "testRG", Virtual WAN dan Hub Virtual di AS Barat dalam grup sumber daya tersebut di Azure. Hub virtual akan memiliki ruang alamat "10.0.1.0/24".
Contoh ini mirip dengan Contoh 1, tetapi juga melampirkan tabel rute ke hub virtual.

### Contoh 3

```powershell
New-AzResourceGroup -Location "West US" -Name "testRG"
$virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "myVirtualWAN" -Location "West US"
New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.1.0/24"
Update-AzVirtualHub -ResourceGroupName "testRG" -Name "westushub" -PreferredRoutingGateway "VpnGateway"    
```

```output
VirtualWan                : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualWans/myVirtualWAN
ResourceGroupName         : testRG
Name                      : westushub
Id                        : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/westushub
AddressPrefix             : 10.0.1.0/24
RouteTable                :
Location                  : West US
Sku                  : Standard 
PreferredRoutingGateway   : VpnGateway
VirtualNetworkConnections : {}
Location                  : West US
Type                      : Microsoft.Network/virtualHubs
ProvisioningState         : Succeeded
```

Di atas akan membuat grup sumber daya "testRG", Virtual WAN dan Hub Virtual di AS Barat dalam grup sumber daya tersebut di Azure. Hub virtual akan memiliki gateway perutean yang lebih disukai sebagai ExpressRoute pada awalnya dan kemudian akan diperbarui ke VpnGateway.

## PARAMETERS

### -AddressPrefix
String ruang alamat untuk hub virtual ini.

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

### -HubVnetConnection
Koneksi jaringan virtual hub yang terkait dengan Hub Virtual ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSHubVirtualNetworkConnection[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Hub virtual yang akan dimodifikasi.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualHub
Parameter Sets: ByVirtualHubObject
Aliases: VirtualHub

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName
Aliases: ResourceName, VirtualHubName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredRoutingGateway
Gateway Perutean Pilihan untuk Merutekan lalu lintas Lokal dari VNET

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ExpressRoute, VpnGateway

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
Parameter Sets: ByVirtualHubName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya hub Virtual yang akan dimodifikasi.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubResourceId
Aliases: VirtualHubId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteTable
Tabel rute yang terkait dengan Hub Virtual ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualHubRouteTable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Sku Hub Virtual.

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

### -Tag
Hashtable yang mewakili tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
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

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

## NOTES

## RELATED LINKS

[Get-AzVirtualHub](./Get-AzVirtualHub.md)

[New-AzVirtualHub](./New-AzVirtualHub.md)

[Remove-AzVirtualHub](./Remove-AzVirtualHub.md)
