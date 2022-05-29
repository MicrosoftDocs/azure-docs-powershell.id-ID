---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: EE8F5D57-1ECE-4F23-9A5B-F226DD2C5ECB
online version: https://docs.microsoft.com/powershell/module/az.network/add-azloadbalancerinboundnatruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzLoadBalancerInboundNatRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzLoadBalancerInboundNatRuleConfig.md
ms.openlocfilehash: 82e24c4b7446d3b36cd517e8e720424391bc134c
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145810134"
---
# Add-AzLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Menambahkan konfigurasi aturan NAT masuk ke load balancer.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/add-azloadbalancerinboundnatruleconfig) untuk informasi terbaru.

## SYNTAX

### SetByResource (Default)
```
Add-AzLoadBalancerInboundNatRuleConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Protocol <String>]
 [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP]
 [-EnableTcpReset] [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-FrontendPortRangeStart <Int32>]
 [-FrontendPortRangeEnd <Int32>] [-BackendAddressPool <PSBackendAddressPool>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceId
```
Add-AzLoadBalancerInboundNatRuleConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Protocol <String>]
 [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP]
 [-EnableTcpReset] [-FrontendIpConfigurationId <String>] [-FrontendPortRangeStart <Int32>]
 [-FrontendPortRangeEnd <Int32>] [-BackendAddressPoolId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzLoadBalancerInboundNatRuleConfig** menambahkan konfigurasi aturan terjemahan alamat jaringan masuk (NAT) ke load balancer Azure.

## EXAMPLES

### Contoh 1: Menambahkan konfigurasi aturan NAT masuk ke load balancer
```powershell
$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
$slb | Add-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350 -EnableFloatingIP
$slb | Set-AzLoadBalancer
```

Perintah pertama mendapatkan load balancer bernama MyloadBalancer, lalu menyimpannya dalam variabel $slb.
Perintah kedua menggunakan operator alur untuk meneruskan load balancer di $slb ke **Add-AzLoadBalancerInboundNatRuleConfig**, yang menambahkan konfigurasi aturan NAT masuk ke load balancer.
Perintah terakhir mengatur konfigurasi ke loadbalancer, jika Anda tidak melakukan Set-AzLoadBalancer, perubahan Anda tidak akan diterapkan ke loadbalancer.

### Contoh 2: Menambahkan konfigurasi aturan NAT masuk V2 ke load balancer
```powershell
$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
$slb | Add-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRuleV2" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -IdleTimeoutInMinutes 10 -FrontendPortRangeStart 3389 -FrontendPortRangeEnd 4000 -BackendAddressPool $slb.BackendAddressPools[0] -BackendPort 3389
$slb | Set-AzLoadBalancer
```

Perintah pertama mendapatkan load balancer bernama MyloadBalancer, lalu menyimpannya dalam variabel $slb.
Perintah kedua menggunakan operator alur untuk meneruskan load balancer di $slb ke **Add-AzLoadBalancerInboundNatRuleConfig**, yang menambahkan konfigurasi NAT rule V2 masuk ke load balancer.
Perintah terakhir mengatur konfigurasi ke loadbalancer, jika Anda tidak melakukan Set-AzLoadBalancer, perubahan Anda tidak akan diterapkan ke loadbalancer.

## PARAMETERS

### -BackendPort
Menentukan port backend untuk lalu lintas yang cocok dengan konfigurasi aturan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -EnableFloatingIP
Menunjukkan bahwa cmdlet ini memungkinkan alamat IP mengambang untuk konfigurasi aturan.

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

### -EnableTcpReset
Terima Pengaturan Ulang TCP dua arah pada batas waktu diam aliran TCP atau penghentian koneksi yang tidak terduga. Elemen ini hanya digunakan ketika protokol diatur ke TCP.

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

### -FrontendIpConfiguration
Menentukan daftar alamat IP front-end untuk dikaitkan dengan konfigurasi aturan NAT masuk.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSFrontendIPConfiguration
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FrontendIpConfigurationId
Menentukan ID untuk konfigurasi alamat IP front-end.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FrontendPort
Menentukan port front-end yang cocok dengan konfigurasi aturan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Menentukan lamanya waktu, dalam menit, bahwa status percakapan dipertahankan dalam penyeimbang muatan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancer
Menentukan objek **LoadBalancer** .
Cmdlet ini menambahkan konfigurasi aturan NAT masuk ke load balancer yang ditentukan parameter ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSLoadBalancer
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Menentukan nama konfigurasi aturan NAT masuk yang akan ditambahkan.

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

### -Protokol
Menentukan protokol yang cocok dengan aturan NAT masuk.
Nilai yang dapat diterima untuk parameter ini adalah: Tcp atau Udp.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FrontendPortRangeStart
Menentukan nomor port pertama dalam rentang port eksternal yang digunakan oleh konfigurasi aturan. Rentang nilai yang dapat diterima antara 1 dan 65534.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FrontendPortRangeEnd
Menentukan nomor port terakhir dalam rentang port eksternal yang digunakan oleh konfigurasi aturan. Rentang nilai yang dapat diterima antara 1 dan 65535.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendAddressPool
Menentukan kumpulan alamat backend untuk dikaitkan dengan konfigurasi aturan NAT masuk.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendAddressPoolId
Menentukan ID objek BackendAddressPool untuk dikaitkan dengan konfigurasi aturan NAT masuk.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: False
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

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

### System.String

### System.Int32

### Microsoft.Azure.Commands.Network.Models.PSFrontendIPConfiguration

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## NOTES

## RELATED LINKS

[Dapatkan-AzLoadBalancer](./Get-AzLoadBalancer.md)

[Get-AzLoadBalancerInboundNatRuleConfig](./Get-AzLoadBalancerInboundNatRuleConfig.md)

[Baru-AzLoadBalancerInboundNatRuleConfig](./New-AzLoadBalancerInboundNatRuleConfig.md)

[Remove-AzLoadBalancerInboundNatRuleConfig](./Remove-AzLoadBalancerInboundNatRuleConfig.md)

[Atur-AzLoadBalancer](./Set-AzLoadBalancer.md)

[Set-AzLoadBalancerInboundNatRuleConfig](./Set-AzLoadBalancerInboundNatRuleConfig.md)
