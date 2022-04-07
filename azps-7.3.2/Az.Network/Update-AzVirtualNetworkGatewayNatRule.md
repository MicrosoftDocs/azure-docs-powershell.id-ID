---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/update-azvirtualnetworkgatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualNetworkGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualNetworkGatewayNatRule.md
ms.openlocfilehash: 9dc76129c807638f1355ca46b1791d003d4bf5ab
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140392175"
---
# Update-AzVirtualNetworkGatewayNatRule

## SYNOPSIS
Memperbarui NatRule Gateway Jaringan Virtual.

## SYNTAX

### ByVirtualNetworkGatewayNatRuleName (Default)
```
Update-AzVirtualNetworkGatewayNatRule -ResourceGroupName <String> -ParentResourceName <String> -Name <String>
 [-InternalMapping <String[]>] [-ExternalMapping <String[]>] [-InternalPortRange <String[]>]
 [-ExternalPortRange <String[]>] [-IpConfigurationId <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualNetworkGatewayNatRuleResourceId
```
Update-AzVirtualNetworkGatewayNatRule -ResourceId <String> [-InternalMapping <String[]>]
 [-ExternalMapping <String[]>] [-InternalPortRange <String[]>] [-ExternalPortRange <String[]>]
 [-IpConfigurationId <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByVirtualNetworkGatewayNatRuleObject
```
Update-AzVirtualNetworkGatewayNatRule -InputObject <PSVirtualNetworkGatewayNatRule>
 [-InternalMapping <String[]>] [-ExternalMapping <String[]>] [-InternalPortRange <String[]>]
 [-ExternalPortRange <String[]>] [-IpConfigurationId <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Update-AzVirtualNetworkGatewayNatRule** mengatur atau memperbarui aturan nat gateway jaringan virtual.

## EXAMPLES

### Contoh 1:
```
$natRule1 = get-azVirtualNetworkGatewayNatRule -ResourceGroupName "rg1" -Name "natRule1" -ParentResourceName "gw1"
 Update-AzVirtualNetworkGatewayNatRule -InputObject $natRule1 -ExternalMapping @("30.0.0.0/16") -InternalMapping @("25.0.0.0/16") -IpConfigurationId "/subscriptions/7afd8f92-c220-4f53-886e-1df53a69afd4/resourceGroups/rg1/providers/Microsoft.Network/virtualNetworkGateways/gw1/ipConfigurations/default"
Name              : natRule1
ProvisioningState : Succeeded
Type              : Static
Mode              : IngressSnat
InternalMappings  : [
                      {
                        "AddressSpace": "25.0.0.0/16"
                      }
                    ]
ExternalMappings  : [
                      {
                        "AddressSpace": "30.0.0.0/16"
                      }
                    ]
IpConfigurationId : /subscriptions/7afd8f92-c220-4f53-886e-1df53a69afd4/resourceGroups/rg1/providers/Microsoft.Network/virtualNetworkGateways/gw1/ipConfigurations/default
Id                : /subscriptions/7afd8f92-c220-4f53-886e-1df53a69afd4/resourceGroups/rg1/providers/Microsoft.Network/virtualNetworkGateways/gw1/natRules/natRule1
Etag              : W/"5150d788-e165-42ba-99c4-8138a545fce9"
```

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

Required: False
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

### -InputObject
Objek VirtualNetworkGatewayNatRule untuk diperbarui.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule
Parameter Sets: ByVirtualNetworkGatewayNatRuleObject
Aliases: VirtualNetworkGatewayNatRule

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InternalMapping
Daftar pemetaan internal subnet alamat IP privat untuk NAT

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

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualNetworkGatewayNatRuleName
Aliases: ResourceName, VirtualNetworkGatewayNatRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentResourceName
Nama sumber daya induk.

```yaml
Type: System.String
Parameter Sets: ByVirtualNetworkGatewayNatRuleName
Aliases: ParentVirtualNetworkGatewayName, VirtualNetworkGatewayName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualNetworkGatewayNatRuleName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya objek VirtualNetworkGatewayNatRule diperbarui.

```yaml
Type: System.String
Parameter Sets: ByVirtualNetworkGatewayNatRuleResourceId
Aliases: VirtualNetworkGatewayNatRuleResourceId

Required: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule

## CATATAN

## RELATED LINKS

[Get-AzVirtualNetworkGatewayNatRule](./Get-AzVirtualNetworkGatewayNatRule.md)

[Remove-AzVirtualNetworkGatewayNatRule](./Remove-AzVirtualNetworkGatewayNatRule.md)

[New-AzVirtualNetworkGatewayNatRule](./New-AzVirtualNetworkGatewayNatRule.md)
