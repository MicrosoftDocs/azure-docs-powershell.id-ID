---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvirtualhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualHub.md
ms.openlocfilehash: 6f48151300cdee9fa9449b3d0819c18a21b9581c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142080265"
---
# New-AzVirtualHub

## SYNOPSIS
Membuat sumber daya Azure VirtualHub.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azvirtualhub) untuk informasi terbaru.

## SYNTAX

### ByVirtualWanObject (Default)
```
New-AzVirtualHub -ResourceGroupName <String> -Name <String> -VirtualWan <PSVirtualWan> -AddressPrefix <String>
 -Location <String> [-HubVnetConnection <PSHubVirtualNetworkConnection[]>]
 [-RouteTable <PSVirtualHubRouteTable[]>] [-Tag <Hashtable>] [-Sku <String>] [-PreferredRoutingGateway <String>]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualWanResourceId
```
New-AzVirtualHub -ResourceGroupName <String> -Name <String> -VirtualWanId <String> -AddressPrefix <String>
 -Location <String> [-HubVnetConnection <PSHubVirtualNetworkConnection[]>]
 [-RouteTable <PSVirtualHubRouteTable[]>] [-Tag <Hashtable>] [-Sku <String>] [-PreferredRoutingGateway <String>]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat sumber daya Azure VirtualHub.

## EXAMPLES

### Contoh 1

```powershell
PS C:\> New-AzResourceGroup -Location "West US" -Name "testRG"
PS C:\> $virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "myVirtualWAN" -Location "West US"
PS C:\> New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.1.0/24"

VirtualWan                : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualWans/myVirtualWAN
ResourceGroupName         : testRG
Name                      : westushub
Id                        : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/westushub
AddressPrefix             : 10.0.1.0/24
RouteTable                : 
VirtualNetworkConnections : {}
RouteTables                           : {}
Location                  : West US
Sku                  : Standard
PreferredRoutingGateway   : ExpressRoute
Type                      : Microsoft.Network/virtualHubs
ProvisioningState         : Succeeded
```

Hal di atas akan membuat grup sumber daya "testRG", Virtual WAN, dan Hub Virtual di AS Barat dalam grup sumber daya tersebut di Azure. Hub virtual akan memiliki ruang alamat "10.0.1.0/24".

### Contoh 2

```powershell
PS C:\> New-AzResourceGroup -Location "West US" -Name "testRG"
PS C:\> $virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "myVirtualWAN" -Location "West US"
PS C:\> New-AzVirtualHub -VirtualWanId $virtualWan.Id -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.1.0/24" -Location "West US"

VirtualWan                : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualWans/myVirtualWAN
ResourceGroupName         : testRG
Name                      : westushub
Id                        : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/westushub
AddressPrefix             : 10.0.1.0/24
RouteTable                : 
VirtualNetworkConnections : {}
RouteTables                           : {}
Location                  : West US
Sku                  : Standard
PreferredRoutingGateway   : ExpressRoute
Type                      : Microsoft.Network/virtualHubs
ProvisioningState         : Succeeded
```

Hal di atas akan membuat grup sumber daya "testRG", Virtual WAN, dan Hub Virtual di AS Barat dalam grup sumber daya tersebut di Azure. Hub virtual akan memiliki ruang alamat "10.0.1.0/24". 

Contoh ini mirip dengan Contoh 1, tetapi menggunakan Id sumber daya untuk mereferensikan Virtual WAN yang diperlukan untuk membuat Hub virtual.

### Contoh 3

```powershell
PS C:\> New-AzResourceGroup -Location "West US" -Name "testRG"
PS C:\> $virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "myVirtualWAN" -Location "West US"
PS C:\> $route1 = New-AzVirtualHubRoute -AddressPrefix @("10.0.0.0/16", "11.0.0.0/16") -NextHopIpAddress "12.0.0.5"
PS C:\> $route2 = New-AzVirtualHubRoute -AddressPrefix @("13.0.0.0/16") -NextHopIpAddress "14.0.0.5"
PS C:\> $routeTable = New-AzVirtualHubRouteTable -Route @($route1, $route2)
PS C:\> New-AzVirtualHub -VirtualWanId $virtualWan.Id -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.1.0/24" -RouteTable $routeTable

VirtualWan                : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualWans/myVirtualWAN
ResourceGroupName         : testRG
Name                      : westushub
Id                        : /subscriptions/{subscriptionId}resourceGroups/testRG/providers/Microsoft.Network/virtualHubs/westushub
AddressPrefix             : 10.0.1.0/24
RouteTable                : Microsoft.Azure.Commands.Network.Models.PSVirtualHubRouteTable
VirtualNetworkConnections : {}
RouteTables                           : {}
Location                  : West US
Sku                  : Standard
PreferredRoutingGateway   : ExpressRoute
Type                      : Microsoft.Network/virtualHubs
ProvisioningState         : Succeeded
```

Hal di atas akan membuat grup sumber daya "testRG", Virtual WAN, dan Hub Virtual di AS Barat dalam grup sumber daya tersebut di Azure. Hub virtual akan memiliki ruang alamat "10.0.1.0/24" dan tabel rute yang terpasang.

Contoh ini mirip dengan Contoh 2, tetapi juga melampirkan tabel rute ke hub virtual.

### Contoh 4

```powershell
PS C:\> New-AzResourceGroup -Location "West US" -Name "testRG"
PS C:\> $virtualWan = New-AzVirtualWan -ResourceGroupName "testRG" -Name "myVirtualWAN" -Location "West US"
PS C:\> New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.1.0/24" -PreferredRoutingGateway "VpnGateway"    

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

Hal di atas akan membuat grup sumber daya "testRG", Virtual WAN, dan Hub Virtual di AS Barat dalam grup sumber daya tersebut di Azure. Hub virtual akan memiliki gateway perutean yang lebih disukai sebagai VPNGateway.

## PARAMETERS

### -AddressPrefix
String spasi alamat untuk hub virtual ini.

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

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -Lokasi
Lokasi.

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

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName, VirtualHubName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredRoutingGateway
Gateway Perutean Pilihan untuk Rute lalu lintas Lokal dari VNET

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Sebuah hashtable yang mewakili tag sumber daya.

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

### -VirtualWan
Objek wan virtual tempat hub ini ditautkan.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualWan
Parameter Sets: ByVirtualWanObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualWanId
Id objek wan virtual tempat hub ini ditautkan.

```yaml
Type: System.String
Parameter Sets: ByVirtualWanResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualWan

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

## CATATAN

## RELATED LINKS

[Get-AzVirtualHub](./Get-AzVirtualHub.md)

[Remove-AzVirtualHub](./Remove-AzVirtualHub.md)

[Perbarui-AzVirtualHub](./Update-AzVirtualHub.md)
