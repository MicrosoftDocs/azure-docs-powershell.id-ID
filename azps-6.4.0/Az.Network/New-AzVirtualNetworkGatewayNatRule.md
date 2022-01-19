---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvirtualnetworkgatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualNetworkGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualNetworkGatewayNatRule.md
ms.openlocfilehash: 998272dffabf311ce357449ab7b59783bdd0037d
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136210807"
---
# New-AzVirtualNetworkGatewayNatRule

## SYNOPSIS
Membuat objek gateway jaringan virtual natRule.

## SYNTAX

```
New-AzVirtualNetworkGatewayNatRule -Name <String> -Type <String> -Mode <String> -InternalMapping <String[]>
 -ExternalMapping <String[]> [-IpConfigurationId <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet New-AzVirtualNetworkGatewayNatRule** membuat objek PSVirtualNetworkGatewayNatRule yang mewakili properti natRules di gateway jaringan virtual Anda.

## EXAMPLES

### Contoh 1
```
$gateway = Get-AzVirtualNetworkGateway -ResourceGroupName myRg -Name gw1
$natRule = New-AzVirtualNetworkGatewayNatRule -Name "natRule1" -Type "Static" -Mode "IngressSnat" -InternalMapping @("25.0.0.0/16") -ExternalMapping @("30.0.0.0/16")
Set-AzVirtualNetworkGateway -VirtualNetworkGateway $gateway -NatRule $natRule
```
Perintah pertama mendapatkan gateway jaringan virtual bernama gw1 yang dimiliki oleh grup sumber daya myRg dan menyimpannya ke variabel bernama $gateway Perintah kedua membuat objek PSVirtualNetworkGatewayNatRuleirtual yang baru.
Perintah ketiga memperbarui gateway jaringan virtual gw1 dengan natRule yang baru ditambahkan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
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
Type: IAzureContextContainer
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
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalMapping
Daftar pemetaan internal subnet alamat IP privat untuk NAT

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpConfigurationId
ID Konfigurasi IP aturan NAT ini berlaku untuk

```yaml
Type: String
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
Type: String
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
Type: String
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
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Static, Dynamic

Required: True
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
