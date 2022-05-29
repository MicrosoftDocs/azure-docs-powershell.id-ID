---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 4AA587F8-4967-439D-84B6-EDC24235D3F5
online version: https://docs.microsoft.com/powershell/module/az.network/new-azloadbalancerinboundnatruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerInboundNatRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerInboundNatRuleConfig.md
ms.openlocfilehash: f772d2d7ebbf86200f8d110af9105bba038204c3
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145674904"
---
# New-AzLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Membuat konfigurasi aturan NAT yang masuk untuk load balancer.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azloadbalancerinboundnatruleconfig) untuk informasi terbaru.

## SYNTAX

### SetByResource (Default)
```
New-AzLoadBalancerInboundNatRuleConfig -Name <String> [-Protocol <String>] [-FrontendPort <Int32>]
 [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP] [-EnableTcpReset]
 [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-FrontendPortRangeStart <Int32>]
 [-FrontendPortRangeEnd <Int32>] [-BackendAddressPool <PSBackendAddressPool>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetByResourceId
```
New-AzLoadBalancerInboundNatRuleConfig -Name <String> [-Protocol <String>] [-FrontendPort <Int32>]
 [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP] [-EnableTcpReset]
 [-FrontendIpConfigurationId <String>] [-FrontendPortRangeStart <Int32>]
 [-FrontendPortRangeEnd <Int32>] [-BackendAddressPoolId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzLoadBalancerInboundNatRuleConfig** membuat konfigurasi aturan terjemahan alamat jaringan masuk (NAT) untuk load balancer Azure.

## EXAMPLES

### Contoh 1: Membuat konfigurasi aturan NAT masuk untuk load balancer
```powershell
$publicip = New-AzPublicIpAddress -ResourceGroupName "MyResourceGroup" -Name "MyPublicIP" -Location "West US" -AllocationMethod "Dynamic"
$frontend = New-AzLoadBalancerFrontendIpConfig -Name "FrontendIpConfig01" -PublicIpAddress $publicip
New-AzLoadBalancerInboundNatRuleConfig -Name "MyInboundNatRule" -FrontendIPConfiguration $frontend -Protocol "Tcp" -FrontendPort 3389 -BackendPort 3389
```

Perintah pertama membuat alamat IP publik bernama MyPublicIP di grup sumber daya bernama MyResourceGroup, lalu menyimpannya dalam variabel $publicip.
Perintah kedua membuat konfigurasi IP front-end bernama FrontendIpConfig01 menggunakan alamat IP publik di $publicip, lalu menyimpannya dalam variabel $frontend.
Perintah ketiga membuat konfigurasi aturan NAT masuk bernama MyInboundNatRule menggunakan objek front-end di $frontend.
Protokol TCP ditentukan dan port front-end adalah 3389, sama dengan port backend dalam kasus ini.
Parameter *FrontendIpConfiguration*, *Protocol*, *FrontendPort*, dan *BackendPort* semuanya diperlukan untuk membuat konfigurasi aturan NAT masuk.

### Contoh 2: Membuat konfigurasi aturan NAT masuk V2 untuk load balancer
```powershell
$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
$natRuleV2 = New-AzLoadBalancerInboundNatRuleConfig -Name natRuleV2 -Protocol "Tcp" -FrontendIpConfiguration $slb.FrontendIpConfigurations[0] -FrontendPortRangeStart 3390 -FrontendPortRangeEnd 4001 -BackendAddressPool $slb.BackendAddressPools[0] -IdleTimeoutInMinutes 4 -BackendPort 3389
```

Perintah pertama mendapatkan load balancer bernama MyloadBalancer, lalu menyimpannya dalam variabel $slb.
Perintah kedua membuat konfigurasi aturan NAT masuk bernama natRuleV2.Parameter *FrontendIpConfiguration*, *BackendAddressPool*, *Protocol*, *FrontendPortRangeStart*, *FrontendPortRangeEnd* , dan *BackendPort* semuanya diperlukan untuk membuat konfigurasi aturan NAT masuk V2.

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
Menentukan daftar alamat IP front-end untuk dikaitkan dengan konfigurasi aturan load balancer.

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
Menentukan lamanya waktu, dalam menit, yang status percakapannya dipertahankan dalam load balancer.

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

### -Name
Menentukan nama konfigurasi aturan yang dibuat cmdlet ini.

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
Menentukan protokol.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tcp
- Udp

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

### System.String

### System.Int32

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

### Microsoft.Azure.Commands.Network.Models.PSFrontendIPConfiguration

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSInboundNatRule

## NOTES

## RELATED LINKS

[Add-AzLoadBalancerInboundNatRuleConfig](./Add-AzLoadBalancerInboundNatRuleConfig.md)

[Get-AzLoadBalancerInboundNatRuleConfig](./Get-AzLoadBalancerInboundNatRuleConfig.md)

[New-AzLoadBalancerFrontendIpConfig](./New-AzLoadBalancerFrontendIpConfig.md)

[New-AzPublicIpAddress](./New-AzPublicIpAddress.md)

[Remove-AzLoadBalancerInboundNatRuleConfig](./Remove-AzLoadBalancerInboundNatRuleConfig.md)

[Set-AzLoadBalancerInboundNatRuleConfig](./Set-AzLoadBalancerInboundNatRuleConfig.md)
