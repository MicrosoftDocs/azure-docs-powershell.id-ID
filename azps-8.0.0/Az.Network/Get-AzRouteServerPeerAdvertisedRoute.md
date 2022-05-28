---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azrouteserverpeeradvertisedroute
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteServerPeerAdvertisedRoute.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteServerPeerAdvertisedRoute.md
ms.openlocfilehash: 44a212db31f91fbbba8c4aa41b062e4a4367ce0b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145542232"
---
# Get-AzRouteServerPeerAdvertisedRoute

## SYNOPSIS
Mencantumkan rute yang diiklankan oleh peer server rute tertentu

## SYNTAX

### RouteServerPeerNameParameterSet (Default)
```
Get-AzRouteServerPeerAdvertisedRoute -ResourceGroupName <String> -RouteServerName <String>
 -PeerName <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### RouteServerPeerObjectParameterSet
```
Get-AzRouteServerPeerAdvertisedRoute -InputObject <PSRouteServerPeer> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mengingat peer server rute baik berdasarkan nama atau objek , hitung rute yang diiklankan ke peer tersebut oleh server rute tertentu.

## EXAMPLES

### Contoh 1
```powershell
Get-AzRouteServerPeerAdvertisedRoute -ResourceGroupName $resourceGroupName -RouteServerName $routeServerName -PeerName $peerName
```

### Contoh 2
```powershell
$routeServerPeer = Get-AzRouteServerPeer -ResourceGroupName $resourceGroupName -RouteServerName $routeServerName -PeerName $peerName
Get-AzRouteServerPeerAdvertisedRoute -InputObject $routeServerPeer
```

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
Objek input peer server rute.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSRouteServerPeer
Parameter Sets: RouteServerPeerObjectParameterSet
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PeerName
Nama peer server rute

```yaml
Type: System.String
Parameter Sets: RouteServerPeerNameParameterSet
Aliases: ResourceName
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya peer server rute

```yaml
Type: System.String
Parameter Sets: RouteServerPeerNameParameterSet
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteServerName
Nama Route Server

```yaml
Type: System.String
Parameter Sets: RouteServerPeerNameParameterSet
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSRouteServerPeer

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPeerRoute

## NOTES

## RELATED LINKS