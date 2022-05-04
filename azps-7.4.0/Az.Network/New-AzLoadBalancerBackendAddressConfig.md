---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azloadbalancerbackendaddressconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressConfig.md
ms.openlocfilehash: 48380bbc15dbb5e989a0b92bfc96e89b85f1f740
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144600836"
---
# New-AzLoadBalancerBackendAddressConfig

## SYNOPSIS
Mengembalikan konfigurasi alamat backend load balancer. 

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azloadbalancerbackendaddressconfig) untuk informasi terbaru.

## SYNTAX

### SetByIpAndSubnet (Default)
```
New-AzLoadBalancerBackendAddressConfig -IpAddress <String> -Name <String> -SubnetId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByIpAndVnet
```
New-AzLoadBalancerBackendAddressConfig -IpAddress <String> -Name <String> -VirtualNetworkId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceFrontendIPConfiguration
```
New-AzLoadBalancerBackendAddressConfig -Name <String> -LoadBalancerFrontendIPConfigurationId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan konfigurasi alamat backend load balancer. 

## EXAMPLES

### Contoh 1: Konfigurasi alamat loadbalancer baru dengan referensi jaringan virtual
```powershell
$virtualNetwork = Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $resourceGroup
New-AzLoadBalancerBackendAddressConfig -IpAddress "10.0.0.5" -Name "TestVNetRef" -VirtualNetworkId $virtualNetwork.Id
```
### Contoh 2: Konfigurasi alamat loadbalancer baru dengan referensi subnet
```powershell
$virtualNetwork = Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $resourceGroup
$subnet = Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $virtualNetwork
New-AzLoadBalancerBackendAddressConfig -IpAddress "10.0.0.5" -Name "TestVNetRef" -SubnetId $subnet.Id
```

### Contoh 3: Konfigurasi alamat loadbalancer baru dengan referensi konfigurasi ip frontend loadbalancer
```powershell
$frontend = New-AzLoadBalancerFrontendIpConfig -Name $frontendName -PublicIpAddress $publicip
New-AzLoadBalancerBackendAddressConfig -LoadBalancerFrontendIPConfigurationId $frontend.Id -Name "TestLBFERef"
```

## PARAMETERS

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

### -IpAddress
IPAddress untuk ditambahkan ke kumpulan backend

```yaml
Type: System.String
Parameter Sets: SetByIpAndSubnet, SetByIpAndVnet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerFrontendIPConfigurationId
Konfigurasi ip frontend load balancer yang terkait dengan konfigurasi Alamat Backend

```yaml
Type: System.String
Parameter Sets: SetByResourceFrontendIPConfiguration
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama konfigurasi Alamat Backend

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetId
Subnet yang terkait dengan konfigurasi Alamat Backend

```yaml
Type: System.String
Parameter Sets: SetByIpAndSubnet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkId
Jaringan virtual yang terkait dengan konfigurasi Alamat Backend

```yaml
Type: System.String
Parameter Sets: SetByIpAndVnet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancerBackendAddress

## NOTES

## RELATED LINKS
