---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig.md
ms.openlocfilehash: 750baa9eaf0d3fa6b172187c0f82a3c10709733f
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136564547"
---
# New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig

## SYNOPSIS
Membuat antarmuka interface dalam pool alamat backend yang berisi penyeimbang muat.

## SYNTAX

### CreateByNameParameterSet
```
New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig [-Type <String>] [-Protocol <String>] [-Identifier <UInt32>] [-Port <UInt32>]
```

## DESCRIPTION
Membuat antarmuka interface dalam pool alamat backend yang berisi penyeimbang muat. Ini digunakan untuk Penyeimbang Muat Gateway
## EXAMPLES

### Contoh 1: Menambahkan antarmuka penghubung ke konfigurasi pool alamat backend ke penyeimbang muat
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

### -Protocol
Menentukan protokol antarmuka protocol of interface.

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
Menentukan tipe antarmuka antarmuka antar muka.

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
Menentukan port antarmuka antar muka.

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
Menentukan pengidentifikasi antarmuka antar muka.

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
