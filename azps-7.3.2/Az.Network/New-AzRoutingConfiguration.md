---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azroutingconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzRoutingConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzRoutingConfiguration.md
ms.openlocfilehash: 2a81e02ff36b84fd33535bc3ee7c3f6d9f2e06fc
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139999726"
---
# New-AzRoutingConfiguration

## SYNOPSIS
Membuat objek RoutingConfiguration.

## SYNTAX

```powershell
New-AzRoutingConfiguration -AssociatedRouteTable <String> -Label <String[]> -Id <String[]> [-StaticRoute <PSStaticRoute[]>]  [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek RoutingConfiguration.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $rgName = "testRg"
PS C:\> $virtualHubName = "testHub"
PS C:\> $rt1 = Get-AzVHubRouteTable -ResourceGroupName $rgName -VirtualHubName $virtualHubName -Name "defaultRouteTable"
PS C:\> $rt2 = Get-AzVHubRouteTable -ResourceGroupName $rgName -VirtualHubName $virtualHubName -Name "noneRouteTable"
PS C:\> $route1 = New-AzStaticRoute -Name "route1" -AddressPrefix @("10.20.0.0/16", "10.30.0.0/16")-NextHopIpAddress "10.90.0.5"
PS C:\> New-AzRoutingConfiguration -AssociatedRouteTable $rt1.Id -Label @("testLabel") -Id @($rt2.Id) -StaticRoute @($route1)

AssociatedRouteTable  : "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testRg/providers/Microsoft.Network/virtualHubs/testHub/hubRouteTables/defaultRouteTable"
PropagatedRouteTables : {
                          "Labels": [
                            "testLabel"
                          ],
                          "Ids": [
                            {
                              "Id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testRg/providers/Microsoft.Network/virtualHubs/testHub/hubRouteTables/noneRouteTable"
                            }
                          ]
                        }
VnetRoutes            : {
                          "StaticRoutes": [
                            {
                              "Name": "route1",
                              "AddressPrefixes": [
                                "10.20.0.0/16",
                                "10.30.0.0/16"
                              ],
                              "NextHopIpAddress": "10.90.0.5"
                            }
                          ]
                        }
```

Perintah di atas akan membuat objek RoutingConfiguration yang kemudian bisa ditambahkan ke sumber daya koneksi. Rute statis hanya diperbolehkan dengan objek HubVirtualNetworkConnection. 

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssociatedRouteTable
Tabel rute hub terkait dengan konfigurasi perutean ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Daftar id sumber daya dari semua tabel rute hub untuk mengiklankan rute untuk properti PropagatedRouteTables.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Label
Daftar label untuk properti PropagatedRouteTables.

```yaml
Type: String[]
Parameter Sets: (all)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticRoute
Daftar rute yang mengontrol perutean dari VirtualHub ke dalam koneksi jaringan virtual.

```yaml
Type: PSStaticRoute[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSStaticRoute

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRoutingConfiguration

## CATATAN

## RELATED LINKS

[New-AzStaticRoute](./New-AzStaticRoute.md)

[New-AzExpressRouteConnection](./New-AzExpressRouteConnection.md)

[Set-AzExpressRouteConnection](./Set-AzExpressRouteConnection.md)

[New-AzVirtualHubVnetConnection](./New-AzVpnConnection.md)

[Update-AzVirtualHubVnetConnection](./Update-AzVpnConnection.md)

[New-AzP2sVpnGateway](./New-AzP2sVpnGateway.md)

[Update-AzP2sVpnGateway](./Update-AzP2sVpnGateway.md)

[New-AzVpnConnection](./New-AzVpnConnection.md)

[Update-AzVpnConnection](./Update-AzVpnConnection.md)