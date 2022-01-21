---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvirtualnetworkgatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualNetworkGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualNetworkGatewayNatRule.md
ms.openlocfilehash: 0c0ad74f6d8b43767cf73ee9a75b6388e35e45d7
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136530884"
---
# New-AzVirtualNetworkGatewayNatRule

## SYNOPSIS
Membuat objek gateway jaringan virtual natRule.

## SYNTAX

```
New-AzVirtualNetworkGatewayNatRule -Name <String> -Type <String> -Mode <String> -InternalMapping <String[]>
 -ExternalMapping <String[]> [-InternalPortRange <String[]>] [-ExternalPortRange <String[]>]
 [-IpConfigurationId <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet New-AzVirtualNetworkGatewayNatRule** membuat objek PSVirtualNetworkGatewayNatRule yang mewakili properti natRules di gateway jaringan virtual Anda.

## EXAMPLES

### Contoh 1
```
$gateway = Get-AzVirtualNetworkGateway -ResourceGroupName myRg -Name gw1
$natRule = New-AzVirtualNetworkGatewayNatRule -Name "natRule1" -Type "Static" -Mode "IngressSnat" -InternalMapping @("25.0.0.0/16") -ExternalMapping @("30.0.0.0/16") -InternalPortRange @("100-100") -ExternalPortRange @("200-200")
Set-AzVirtualNetworkGateway -VirtualNetworkGateway $gateway -NatRule $natRule
```

Perintah pertama mendapatkan gateway jaringan virtual bernama gw1 yang dimiliki oleh grup sumber daya myRg dan menyimpannya ke variabel bernama $gateway Perintah kedua membuat objek PSVirtualNetworkGatewayNatRuleirtual yang baru.
Perintah ketiga memperbarui gateway jaringan virtual gw1 dengan natRule yang baru ditambahkan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -ExternalMapping
Daftar pemetaan eksternal subnet alamat IP privat untuk NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPortRange
Daftar pemetaan rentang port eksternal untuk subnet NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalMapping
Daftar pemetaan internal subnet alamat IP privat untuk NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalPortRange
Daftar pemetaan rentang port internal untuk subnet NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpConfigurationId
ID Konfigurasi IP aturan NAT ini berlaku untuk

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

### -Mode
Arah NAT Sumber dari VPN NAT

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: EgressSnat, IngressSnat

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName, VirtualNetworkGatewayNatRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Tipe aturan NAT untuk VPN NAT

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Static, Dynamic

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule

## CATATAN

## RELATED LINKS

[Get-AzVirtualNetworkGatewayNatRule](./Get-AzVirtualNetworkGatewayNatRule.md)

[Remove-AzVirtualNetworkGatewayNatRule](./Remove-AzVirtualNetworkGatewayNatRule.md)

[Update-AzVirtualNetworkGatewayNatRule](./Update-AzVirtualNetworkGatewayNatRule.md)
