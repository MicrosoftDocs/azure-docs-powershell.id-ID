---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig.md
ms.openlocfilehash: 52f562a6b90f8a03ed92405a024f7b920b1532b1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142108439"
---
# New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig

## SYNOPSIS
Membuat antarmuka terowongan dalam kumpulan alamat backend penyeimbang beban.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azloadbalancerbackendaddresspooltunnelinterfaceconfig) untuk informasi terbaru.

## SYNTAX

### CreateByNameParameterSet
```
New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig [-Type <String>] [-Protocol <String>] [-Identifier <UInt32>] [-Port <UInt32>]
```

## DESCRIPTION
Membuat antarmuka terowongan dalam kumpulan alamat backend penyeimbang beban. Ini digunakan untuk Load Balancer Gateway
## EXAMPLES

### Contoh 1: Menambahkan antarmuka tunnel ke konfigurasi kumpulan alamat backend ke load balancer
```powershell
## Get loadbalancer
PS C:\> $lb = Get-AzLoadBalancer -ResourceGroupName $resourceGroup -Name $loadBalancerName

## Create tunnel interface to backend address pool
PS C:\> $tunnelInterface1 = New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig -Protocol Vxlan -Type Internal -Port 2000 -Identifier 800 -BackendAddressPool $pool
PS C:\> $tunnelInterface2 = New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig -Protocol Vxlan -Type External -Port 2001 -Identifier 801 -BackendAddressPool $pool

## Set backend address pool
PS C:\> $pool = Set-AzLoadBalancerBackendAddressPool -Name "BackendAddressPool02" -TunnelInterface $tunnelInterface1, $tunnelInterface2
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

### -Tipe
Menentukan tipe antarmuka terowongan.

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

## CATATAN

## RELATED LINKS

[Add-AzLoadBalancerBackendAddressPoolConfig](./Add-AzLoadBalancerBackendAddressPoolConfig.md)

[Get-AzLoadBalancerBackendAddressPoolConfig](./Get-AzLoadBalancerBackendAddressPoolConfig.md)

[Remove-AzLoadBalancerBackendAddressPoolConfig](./Remove-AzLoadBalancerBackendAddressPoolConfig.md)
