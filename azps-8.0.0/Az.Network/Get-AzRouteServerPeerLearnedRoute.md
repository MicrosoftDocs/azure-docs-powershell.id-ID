---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azrouteserverpeerlearnedroute
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteServerPeerLearnedRoute.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteServerPeerLearnedRoute.md
ms.openlocfilehash: b3cf25704134ec5b2294fea234526a404da8edb8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145617824"
---
# Get-AzRouteServerPeerLearnedRoute

## SYNOPSIS
Mencantumkan rute yang dipelajari oleh peer server rute tertentu

## SYNTAX

### RouteServerPeerNameParameterSet (Default)
```
Get-AzRouteServerPeerLearnedRoute -ResourceGroupName <String> -RouteServerName <String> -PeerName <String>
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### RouteServerPeerObjectParameterSet
```
Get-AzRouteServerPeerLearnedRoute -InputObject <PSRouteServerPeer> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Menghitung rute yang dipelajari oleh peer server rute dari sumber lain.

## EXAMPLES

### Contoh 1
```powershell
Get-AzRouteServerPeerLearnedRoute -ResourceGroupName $resourceGroupName -RouteServerName $routeServerName -PeerName $peerName
```

### Contoh 2
```powershell
$routerServerPeer = Get-AzRouteServerPeer -ResourceGroupName $resourceGroupName -RouteServerName $routeServerName -PeerName $peerName
Get-AzRouteServerPeerLearnedRoute -InputObject $routerServerPeer
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
Nama server rute

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