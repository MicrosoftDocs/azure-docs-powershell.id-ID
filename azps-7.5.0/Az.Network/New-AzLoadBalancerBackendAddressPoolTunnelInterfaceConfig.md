---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig.md
ms.openlocfilehash: c432c50250877ec50f264f869f8e222dbdaa9f8b
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145675012"
---
# New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig

## SYNOPSIS
Membuat antarmuka terowongan di kumpulan alamat backend load balancer.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azloadbalancerbackendaddresspooltunnelinterfaceconfig) untuk informasi terbaru.

## SYNTAX

### CreateByNameParameterSet
```
New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig [-Type <String>] [-Protocol <String>] [-Identifier <UInt32>] [-Port <UInt32>]
```

## DESCRIPTION
Membuat antarmuka terowongan di kumpulan alamat backend load balancer. Ini digunakan untuk gateway Load Balancer
## EXAMPLES

### Contoh 1: Menambahkan antarmuka terowongan ke konfigurasi kumpulan alamat backend ke load balancer
```powershell
## Get loadbalancer
$lb = Get-AzLoadBalancer -ResourceGroupName $resourceGroup -Name $loadBalancerName

## Create tunnel interface to backend address pool
$tunnelInterface1 = New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig -Protocol Vxlan -Type Internal -Port 2000 -Identifier 800 -BackendAddressPool $pool
$tunnelInterface2 = New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig -Protocol Vxlan -Type External -Port 2001 -Identifier 801 -BackendAddressPool $pool

## Set backend address pool
$pool = Set-AzLoadBalancerBackendAddressPool -Name "BackendAddressPool02" -TunnelInterface $tunnelInterface1, $tunnelInterface2
```
Jika properti tidak disediakan, properti akan diganti dengan nilai default.

## PARAMETERS

### -Protokol
Menentukan protokol antarmuka terowongan.

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

### -Type
Menentukan jenis antarmuka terowongan.

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

### -Port
Menentukan port antarmuka terowongan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identifier
Menentukan pengidentifikasi antarmuka terowongan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### System.String

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSTunnelInterface

## NOTES

## RELATED LINKS

[Add-AzLoadBalancerBackendAddressPoolConfig](./Add-AzLoadBalancerBackendAddressPoolConfig.md)

[Get-AzLoadBalancerBackendAddressPoolConfig](./Get-AzLoadBalancerBackendAddressPoolConfig.md)

[Remove-AzLoadBalancerBackendAddressPoolConfig](./Remove-AzLoadBalancerBackendAddressPoolConfig.md)
