---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 87818605-EFA6-422E-9ECD-0A0BF269DCFD
online version: https://docs.microsoft.com/powershell/module/az.network/set-azloadbalancerinboundnatruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzLoadBalancerInboundNatRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzLoadBalancerInboundNatRuleConfig.md
ms.openlocfilehash: b8ac5525be02f54f9f9498f4d54eecd92385c441
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140190772"
---
# Set-AzLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Mengatur konfigurasi aturan NAT masuk untuk penyeimbang muat.

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
Cmdlet **Set-AzLoadBalancerInboundNatRuleConfig** mengatur konfigurasi aturan inbound network address translation (NAT) untuk penyeimbang muat Azure.

## EXAMPLES

### Contoh 1: Mengubah konfigurasi aturan NAT masuk pada penyeimbang muat
```powershell
PS C:\>$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> $slb | Add-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350 -EnableFloatingIP
PS C:\> $slb | Set-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350
```

Perintah pertama mendapatkan penyeimbang muat bernama MyLoadBalancer, lalu menyimpannya di $slb variabel.
Perintah kedua menggunakan operator pipeline untuk melewati penyeimbang muat di $slb ke Add-AzLoadBalancerInboundNatRuleConfig, yang menambahkan konfigurasi aturan NAT masuk ke dalamnya.
Perintah ketiga melewati penyeimbang muat ke **Set-AzLoadBalancerInboundNatRuleConfig**, yang menyimpan dan memperbarui konfigurasi aturan NAT masuk.
Perhatikan bahwa konfigurasi aturan telah diatur tanpa mengaktifkan IP terapung, yang telah diaktifkan oleh perintah sebelumnya.

### Contoh 2

Mengatur konfigurasi aturan NAT masuk untuk penyeimbang muat. (otomatisgenerated)

<!-- Aladdin Generated Example -->
```powershell
Set-AzLoadBalancerInboundNatRuleConfig -BackendPort 3350 -FrontendIpConfigurationId <String> -FrontendPort 3350 -LoadBalancer <PSLoadBalancer> -Name 'NewNatRule' -Protocol 'Tcp'
```

### Contoh 3: Mengubah konfigurasi aturan NAT masuk V2 pada penyeimbang muat
```powershell
PS C:\>$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> $slb | Add-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRuleV2" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -IdleTimeoutInMinutes 10 -FrontendPortRangeStart 3389 -FrontendPortRangeEnd 4000 -BackendAddressPool $slb.BackendAddressPools[0] -BackendPort 3389
PS C:\> $slb | Set-AzLoadBalancerInboundNatRuleConfig -Name "NewNatRuleV2" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -IdleTimeoutInMinutes 10 -FrontendPortRangeStart 3370 -FrontendPortRangeEnd 3389 -BackendAddressPool $slb.BackendAddressPools[0] -BackendPort 3380
```

Perintah pertama mendapatkan penyeimbang muat bernama MyLoadBalancer, lalu menyimpannya di $slb variabel.
Perintah kedua menggunakan operator pipeline untuk memasukkan penyeimbang muat di $slb ke Add-AzLoadBalancerInboundNatRuleConfig, yang menambahkan konfigurasi aturan NAT V2 masuk ke dalamnya.
Perintah ketiga melewati penyeimbang muat ke **Set-AzLoadBalancerInboundNatRuleConfig**, yang menyimpan dan memperbarui konfigurasi aturan NAT V2 masuk.
Perhatikan bahwa FrontendPortRangeStart, FrontendPortRangeEnd dan BackendPort diubah dalam konfigurasi aturan.

## PARAMETERS

### -BackendPort
Menentukan port backend untuk lalu lintas yang sesuai dengan konfigurasi aturan ini.

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

### -EnableFloatingIP
Mengindikasikan bahwa cmdlet ini mengaktifkan alamat IP mengambang untuk konfigurasi aturan.

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
Menerima Reset TCP dua arah pada waktu habis habis arus TCP atau pemutusan koneksi yang tidak diharapkan. Elemen ini hanya digunakan saat protokol diatur ke TCP.

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
Menentukan daftar alamat IP ujung depan untuk dikaitkan dengan konfigurasi aturan NAT masuk.

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
Menentukan ID untuk konfigurasi alamat IP ujung-depan.

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
Menentukan port ujung-depan yang sesuai dengan konfigurasi aturan penyeimbang muat.

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
Menentukan durasi waktu, dalam menit, bahwa status percakapan dipertahankan dalam penyeimbang muat.

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
Menentukan penyeimbang muat.
Cmdlet ini mengatur konfigurasi aturan NAT masuk untuk penyeimbang muat yang ditentukan parameter ini.

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

### -Nama
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

### -Protocol
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
Menentukan nomor port pertama dalam rentang port eksternal yang digunakan oleh konfigurasi aturan. Rentang nilai yang dapat diterima antara 1 hingga 65534.

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
Menentukan nomor port terakhir dalam rentang port eksternal yang digunakan oleh konfigurasi aturan. Rentang nilai yang dapat diterima antara 1 hingga 65535.

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
Menentukan pool alamat backend untuk dikaitkan dengan konfigurasi aturan NAT masuk.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

## CATATAN

## RELATED LINKS

[Add-AzLoadBalancerInboundNatRuleConfig](./Add-AzLoadBalancerInboundNatRuleConfig.md)

[Get-AzLoadBalancer](./Get-AzLoadBalancer.md)

[Get-AzLoadBalancerInboundNatRuleConfig](./Get-AzLoadBalancerInboundNatRuleConfig.md)

[New-AzLoadBalancerInboundNatRuleConfig](./New-AzLoadBalancerInboundNatRuleConfig.md)

[Remove-AzLoadBalancerInboundNatRuleConfig](./Remove-AzLoadBalancerInboundNatRuleConfig.md)
