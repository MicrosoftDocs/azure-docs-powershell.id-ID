---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/update-azvirtualnetworkgatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualNetworkGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualNetworkGatewayNatRule.md
ms.openlocfilehash: 770318dd01cce4e4fab8f0190c8754ace0a1b72f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142870372"
---
# Update-AzVirtualNetworkGatewayNatRule

## SYNOPSIS
Memperbarui Virtual Network Gateway NatRule.

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
**Pembaruan-AzVirtualNetworkGatewayNatRule** cmdlet mengatur atau memperbarui aturan nat gateway jaringan virtual.

## EXAMPLES

### Contoh 1:
```powershell
$natRule1 = get-azVirtualNetworkGatewayNatRule -ResourceGroupName "rg1" -Name "natRule1" -ParentResourceName "gw1"
 Update-AzVirtualNetworkGatewayNatRule -InputObject $natRule1 -ExternalMapping @("30.0.0.0/16") -InternalMapping @("25.0.0.0/16") -IpConfigurationId "/subscriptions/7afd8f92-c220-4f53-886e-1df53a69afd4/resourceGroups/rg1/providers/Microsoft.Network/virtualNetworkGateways/gw1/ipConfigurations/default"
 ```

```output
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
Menjalankan cmdlet di latar belakang

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
Daftar pemetaan eksternal subnet alamat IP pribadi untuk NAT

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
Daftar pemetaan internal subnet alamat IP pribadi untuk NAT

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
Id sumber daya objek VirtualNetworkGatewayNatRule untuk diperbarui.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule

## NOTES

## RELATED LINKS

[Get-AzVirtualNetworkGatewayNatRule](./Get-AzVirtualNetworkGatewayNatRule.md)

[Remove-AzVirtualNetworkGatewayNatRule](./Remove-AzVirtualNetworkGatewayNatRule.md)

[New-AzVirtualNetworkGatewayNatRule](./New-AzVirtualNetworkGatewayNatRule.md)
