---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 87818605-EFA6-422E-9ECD-0A0BF269DCFD
online version: https://docs.microsoft.com/powershell/module/az.network/set-azloadbalancerinboundnatruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzLoadBalancerInboundNatRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzLoadBalancerInboundNatRuleConfig.md
ms.openlocfilehash: 22a542d4324f803b1a6c733eee60813f1dbe5fd8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145619335"
---
# Set-AzLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Mengatur konfigurasi aturan NAT masuk untuk load balancer.

## SYNTAX

### SetByResource (Default)
```
Set-AzLoadBalancerInboundNatRuleConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Protocol <String>]
 [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP]
 [-EnableTcpReset] [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-FrontendPortRangeStart <Int32>]
 [-FrontendPortRangeEnd <Int32>] [-BackendAddressPool <PSBackendAddressPool>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceId
```
Set-AzLoadBalancerInboundNatRuleConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Protocol <String>]
 [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP]
 [-EnableTcpReset] [-FrontendIpConfigurationId <String>] [-FrontendPortRangeStart <Int32>]
 [-FrontendPortRangeEnd <Int32>] [-BackendAddressPoolId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzLoadBalancerInboundNatRuleConfig** menetapkan konfigurasi aturan terjemahan alamat jaringan masuk (NAT) untuk load balancer Azure.

## EXAMPLES

### Contoh 1: Mengubah konfigurasi aturan NAT masuk pada load balancer
```powershell
$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
$slb | Add-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350 -EnableFloatingIP
$slb | Set-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350
```

Perintah pertama mendapatkan load balancer bernama MyLoadBalancer, lalu menyimpannya dalam variabel $slb.
Perintah kedua menggunakan operator alur untuk meneruskan load balancer di $slb ke Add-AzLoadBalancerInboundNatRuleConfig, yang menambahkan konfigurasi aturan NAT masuk ke dalamnya.
Perintah ketiga meneruskan load balancer ke **Set-AzLoadBalancerInboundNatRuleConfig**, yang menyimpan dan memperbarui konfigurasi aturan NAT masuk.
Perhatikan bahwa konfigurasi aturan diatur tanpa mengaktifkan IP mengambang, yang telah diaktifkan oleh perintah sebelumnya.

### Contoh 2

Mengatur konfigurasi aturan NAT masuk untuk load balancer. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Set-AzLoadBalancerInboundNatRuleConfig -BackendPort 3350 -FrontendIpConfigurationId <String> -FrontendPort 3350 -LoadBalancer <PSLoadBalancer> -Name 'NewNatRule' -Protocol 'Tcp'
```

### Contoh 3: Mengubah konfigurasi aturan NAT masuk V2 pada load balancer
```powershell
$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
$slb | Add-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRuleV2" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -IdleTimeoutInMinutes 10 -FrontendPortRangeStart 3389 -FrontendPortRangeEnd 4000 -BackendAddressPool $slb.BackendAddressPools[0] -BackendPort 3389
$slb | Set-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRuleV2" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -IdleTimeoutInMinutes 10 -FrontendPortRangeStart 3370 -FrontendPortRangeEnd 3389 -BackendAddressPool $slb.BackendAddressPools[0] -BackendPort 3380
```

Perintah pertama mendapatkan load balancer bernama MyLoadBalancer, lalu menyimpannya dalam variabel $slb.
Perintah kedua menggunakan operator alur untuk meneruskan load balancer di $slb ke Add-AzLoadBalancerInboundNatRuleConfig, yang menambahkan konfigurasi ATURAN NAT masuk V2 ke dalamnya.
Perintah ketiga meneruskan load balancer ke **Set-AzLoadBalancerInboundNatRuleConfig**, yang menyimpan dan memperbarui konfigurasi aturan NAT masuk V2.
Perhatikan bahwa FrontendPortRangeStart, FrontendPortRangeEnd, dan BackendPort diubah dalam konfigurasi aturan.

## PARAMETERS

### -BackendPort
Menentukan port ujung belakang untuk lalu lintas yang cocok dengan konfigurasi aturan ini.

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
Menentukan port front-end yang cocok dengan konfigurasi aturan load balancer.

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
Menentukan lamanya waktu, dalam menit, bahwa status percakapan dipertahankan dalam load balancer.

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
Menentukan load balancer.
Cmdlet ini menetapkan konfigurasi aturan NAT masuk untuk load balancer yang ditentukan parameter ini.

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
Menentukan nama konfigurasi aturan NAT masuk.

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
Menentukan protokol yang cocok dengan konfigurasi aturan NAT masuk.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

[Add-AzLoadBalancerInboundNatRuleConfig](./Add-AzLoadBalancerInboundNatRuleConfig.md)

[Dapatkan-AzLoadBalancer](./Get-AzLoadBalancer.md)

[Get-AzLoadBalancerInboundNatRuleConfig](./Get-AzLoadBalancerInboundNatRuleConfig.md)

[Baru-AzLoadBalancerInboundNatRuleConfig](./New-AzLoadBalancerInboundNatRuleConfig.md)

[Remove-AzLoadBalancerInboundNatRuleConfig](./Remove-AzLoadBalancerInboundNatRuleConfig.md)
