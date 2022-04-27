---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azloadbalanceroutboundruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerOutboundRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerOutboundRuleConfig.md
ms.openlocfilehash: ffd47534ad299ca8c8efb5e8af9e876b983c5d77
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144208031"
---
# New-AzLoadBalancerOutboundRuleConfig

## SYNOPSIS
Membuat konfigurasi aturan keluar untuk load balancer.

## SYNTAX

### SetByResource (Default)
```
New-AzLoadBalancerOutboundRuleConfig -Name <String> [-AllocatedOutboundPort <Int32>] -Protocol <String>
 [-EnableTcpReset] [-IdleTimeoutInMinutes <Int32>] -FrontendIpConfiguration <PSResourceId[]>
 -BackendAddressPool <PSBackendAddressPool> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByResourceId
```
New-AzLoadBalancerOutboundRuleConfig -Name <String> [-AllocatedOutboundPort <Int32>] -Protocol <String>
 [-EnableTcpReset] [-IdleTimeoutInMinutes <Int32>] -FrontendIpConfiguration <PSResourceId[]>
 -BackendAddressPoolId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzLoadBalancerOutboundRuleConfig** membuat konfigurasi aturan keluar untuk load balancer Azure.

## EXAMPLES

### Contoh 1: Membuat konfigurasi aturan keluar untuk load balancer
```powershell
$publicip = New-AzPublicIpAddress -ResourceGroupName "MyResourceGroup" -Name "MyPublicIP" -Location "West US" -AllocationMethod "Dynamic" -Sku "Standard"
$frontend = New-AzLoadBalancerFrontendIpConfig -Name "FrontendIpConfig01" -PublicIpAddress $publicip
$backend = New-AzLoadBalancerBackendAddressPoolConfig -Name "BackendAddressPool01"
New-AzLoadBalancerOutboundRuleConfig -Name "MyOutboundRule" -Protocol "Tcp" -FrontendIPConfiguration $frontend -BackendAddressPool $backend
```

Perintah pertama membuat alamat IP publik bernama MyPublicIP di grup sumber daya bernama MyResourceGroup, lalu menyimpannya dalam variabel $publicip.
Perintah kedua membuat konfigurasi IP front-end bernama FrontendIpConfig01 menggunakan alamat IP publik di $publicip, lalu menyimpannya dalam variabel $frontend.
Perintah ketiga membuat konfigurasi kumpulan alamat back-end bernama BackendAddressPool01, lalu menyimpannya dalam variabel $backend.
Perintah keempat membuat konfigurasi aturan keluar bernama MyOutboundRule menggunakan objek front-end dan back-end di $frontend dan $backend.
*Parameter Protocol*, *FrontendIPConfiguration*, dan *BackendAddressPool* semuanya diperlukan untuk membuat konfigurasi aturan keluar.

### Contoh 2

Membuat konfigurasi aturan keluar untuk load balancer. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
New-AzLoadBalancerOutboundRuleConfig -BackendAddressPool <PSBackendAddressPool> -EnableTcpReset -FrontendIpConfiguration <PSResourceId[]> -Name 'MyOutboundRule' -Protocol 'Tcp'
```

## PARAMETERS

### -AllocatedOutboundPort
Jumlah port keluar yang akan digunakan untuk NAT.

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
Referensi ke kumpulan DIP.
Lalu lintas keluar secara acak dimuat seimbang di seluruh IP di IP backend.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool
Parameter Sets: SetByResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendAddressPoolId
Referensi ke kumpulan DIP.
Lalu lintas keluar secara acak dimuat seimbang di seluruh IP di IP backend.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: True
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

### -EnableTcpReset
Terima Pengaturan Ulang TCP dua arah pada batas waktu diam aliran TCP atau penghentian koneksi yang tidak terduga.
Elemen ini hanya digunakan ketika protokol diatur ke TCP.

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
Alamat IP Frontend dari load balancer.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSResourceId[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Batas waktu untuk koneksi diam TCP

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
Nama aturan keluar.

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
Protokol - TCP, UDP, atau Semua

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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

### System.Int32

### System.String

### Microsoft.Azure.Commands.Network.Models.PSResourceId[]

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSOutboundRule

## NOTES

## RELATED LINKS

[Add-AzLoadBalancerOutboundRuleConfig](./Add-AzLoadBalancerOutboundRuleConfig.md)

[Get-AzLoadBalancerOutboundRuleConfig](./Get-AzLoadBalancerOutboundRuleConfig.md)

[Remove-AzLoadBalancerOutboundRuleConfig](./Remove-AzLoadBalancerOutboundRuleConfig.md)

[Set-AzLoadBalancerOutboundRuleConfig](./Set-AzLoadBalancerOutboundRuleConfig.md)
