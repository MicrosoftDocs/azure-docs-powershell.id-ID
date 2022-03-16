---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 4AA587F8-4967-439D-84B6-EDC24235D3F5
online version: https://docs.microsoft.com/powershell/module/az.network/new-azloadbalancerinboundnatruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerInboundNatRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerInboundNatRuleConfig.md
ms.openlocfilehash: 9f45ab63ad07882113ca3bb3a37511b3422bf988
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140191108"
---
# New-AzLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Membuat konfigurasi aturan NAT masuk untuk penyeimbang muat.

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
Cmdlet **New-AzLoadBalancerInboundNatRuleConfig membuat konfigurasi aturan penerjemahan alamat jaringan masuk (NAT, In-AzLoadBalancerInboundNatRuleConfig** ) yang membuat konfigurasi aturan penerjemahan alamat jaringan masuk (NAT) untuk penyeimbang muat Azure.

## EXAMPLES

### Contoh 1: Membuat konfigurasi aturan NAT masuk untuk penyeimbang muat
```
PS C:\>$publicip = New-AzPublicIpAddress -ResourceGroupName "MyResourceGroup" -Name "MyPublicIP" -Location "West US" -AllocationMethod "Dynamic"
PS C:\> $frontend = New-AzLoadBalancerFrontendIpConfig -Name "FrontendIpConfig01" -PublicIpAddress $publicip
PS C:\> New-AzLoadBalancerInboundNatRuleConfig -Name "MyInboundNatRule" -FrontendIPConfiguration $frontend -Protocol "Tcp" -FrontendPort 3389 -BackendPort 3389
```

Perintah pertama membuat alamat IP publik bernama MyPublicIP dalam grup sumber daya yang bernama MyResourceGroup, lalu menyimpannya di $publicip lokal.
Perintah kedua membuat konfigurasi IP front-end bernama FrontendIpConfig01 menggunakan alamat IP publik dalam $publicip, lalu menyimpannya dalam variabel $frontend.
Perintah ketiga membuat konfigurasi aturan NAT masuk bernama MyInboundNatRule menggunakan objek front-end dalam $frontend.
Protokol TCP ditentukan dan port ujung-depan adalah 3389, sama dengan port backend dalam kasus ini.
Parameter *FrontendIpConfiguration*, *Protocol*, *FrontendPort*, dan *BackendPort* semuanya diperlukan untuk membuat konfigurasi aturan NAT masuk.

### Contoh 2: Buat konfigurasi aturan NAT masuk V2 untuk penyeimbang muat
```
PS C:\>$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\>$natRuleV2 = New-AzLoadBalancerInboundNatRuleConfig -Name natRuleV2 -Protocol "Tcp" -FrontendIpConfiguration $slb.FrontendIpConfigurations[0] -FrontendPortRangeStart 3390 -FrontendPortRangeEnd 4001 -BackendAddressPool $slb.BackendAddressPools[0] -IdleTimeoutInMinutes 4 -BackendPort 3389
```

Perintah pertama mendapatkan penyeimbang muat bernama MyloadBalancer, lalu menyimpannya dalam variabel $slb.
Perintah kedua membuat konfigurasi aturan NAT masuk bernama natRuleV2.Parameter *FrontendIpConfiguration*, *BackendAddressPool*, *Protocol*, *FrontendPortRangeStart*, *parameter FrontendPortRangeEnd* dan *BackendPort* semuanya diperlukan untuk membuat konfigurasi aturan NAT V2 masuk.

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
Menentukan daftar alamat IP ujung-depan untuk dikaitkan dengan konfigurasi aturan penyeimbang muat.

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
Menentukan durasi waktu, dalam menit, di mana status percakapan dipertahankan dalam penyeimbang muat.

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

### -Nama
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

### -Protocol
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

### System.String

### System.Int32

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

### Microsoft.Azure.Commands.Network.Models.PSFrontendIPConfiguration

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSInboundNatRule

## CATATAN

## RELATED LINKS

[Add-AzLoadBalancerInboundNatRuleConfig](./Add-AzLoadBalancerInboundNatRuleConfig.md)

[Get-AzLoadBalancerInboundNatRuleConfig](./Get-AzLoadBalancerInboundNatRuleConfig.md)

[New-AzLoadBalancerFrontendIpConfig](./New-AzLoadBalancerFrontendIpConfig.md)

[New-AzPublicIpAddress](./New-AzPublicIpAddress.md)

[Remove-AzLoadBalancerInboundNatRuleConfig](./Remove-AzLoadBalancerInboundNatRuleConfig.md)

[Set-AzLoadBalancerInboundNatRuleConfig](./Set-AzLoadBalancerInboundNatRuleConfig.md)
