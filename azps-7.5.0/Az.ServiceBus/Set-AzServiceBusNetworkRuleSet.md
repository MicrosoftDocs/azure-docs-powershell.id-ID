---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.dll-Help.xml
Module Name: Az.ServiceBus
online version: https://docs.microsoft.com/powershell/module/az.servicebus/set-azservicebusnetworkruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Set-AzServiceBusNetworkRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Set-AzServiceBusNetworkRuleSet.md
ms.openlocfilehash: 0da45e55279a5eda1d40310bd23b56b53f7db64e
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144215639"
---
# Set-AzServiceBusNetworkRuleSet

## SYNOPSIS
Perbarui NetworkruleSet dari Namespace yang diberikan di langganan Azure saat ini.

## SYNTAX

### NetworkRuleSetPropertiesSet (Default)
```
Set-AzServiceBusNetworkRuleSet [-ResourceGroupName] <String> [-Name] <String> [-DefaultAction <String>]
 [-IPRule] <PSNWRuleSetIpRulesAttributes[]> [-VirtualNetworkRule] <PSNWRuleSetVirtualNetworkRulesAttributes[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NetwrokruleSetInputObjectSet
```
Set-AzServiceBusNetworkRuleSet [-ResourceGroupName] <String> [-Name] <String>
 [-InputObject] <PSNetworkRuleSetAttributes> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NetworkRuleSetResourceIdParameterSet
```
Set-AzServiceBusNetworkRuleSet [-ResourceGroupName] <String> [-Name] <String> [-ResourceId] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perbarui NetwrokruleSet dari Namespace yang diberikan di langganan Azure saat ini.

## EXAMPLES

### Contoh 1 
```powershell
$IpRules = @([Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetIpRulesAttributes] @{IpMask = "4.4.4.4";Action = "Allow"},[Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetIpRulesAttributes] @{IpMask = "3.3.3.3";Action = "Allow"})
$VirtualNetworkRules = @([Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetVirtualNetworkRulesAttributes]@{Subnet=@{Id="/subscriptions/subscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.Network/virtualNetworks/sbehvnettest1/subnets/default"};IgnoreMissingVnetServiceEndpoint=$True})
Set-AzServiceBusNetworkRuleSet -ResourceGroupName v-ajnavtest -Namespace ServiceBus-Namespace1-1375 -IPRule $IpRules -VirtualNetworkRule $VirtualNetworkRules -DefaultAction "Allow" -Debug

```

```output
Name                : default
DefaultAction       : Allow
Id                  : /subscriptions/subscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/ServiceBus-Namespace-1122/networkRuleSets/default
Type                : Microsoft.ServiceBus/Namespaces/NetworkRuleSet
IpRules             : {4.4.4.4, Allow, 3.3.3.3, Allow}
VirtualNetworkRules : {/subscriptions/subscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.Network/virtualNetworks/sbehvnettest1/subnets/default, True}
```
Perbarui NetworkRuleSet menggunakan parameter -IPRule dan -VirtualNetworkRule

### Contoh 2
```powershell
$getresult = Get-AzServiceBusNetworkRuleSet -ResourceGroupName v-ajnavtest -Namespace ServiceBus-Namespace1-1375
Set-AzServiceBusNetworkRuleSet -ResourceGroupName v-ajnavtest -Namespace ServiceBus-Namespace1-1375 -InputObject $getresult
```

```output
Name                : default
DefaultAction       : Allow
Id                  : /subscriptions/subscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/ServiceBus-Namespace-1122/networkRuleSets/default
Type                : Microsoft.ServiceBus/Namespaces/NetworkRuleSet
IpRules             : {4.4.4.4, Allow, 3.3.3.3, Allow}
VirtualNetworkRules : {/subscriptions/subscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.Network/virtualNetworks/sbehvnettest1/subnets/default, True}
```
Memperbarui NetworkRuleSet menggunakan -InputObject


### Contoh 3
```powershell
Set-AzServiceBusNetworkRuleSet -ResourceGroupName v-ajnavtest -Namespace ServiceBus-Namespace1-1375 -ResourceId /subscriptions/SubscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/ServiceBus-Namespace1-1375
```

```output
Name                : default
DefaultAction       : Allow
Id                  : /subscriptions/subscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/ServiceBus-Namespace-1122/networkRuleSets/default
Type                : Microsoft.ServiceBus/Namespaces/NetworkRuleSet
IpRules             : {4.4.4.4, Allow, 3.3.3.3, Allow}
VirtualNetworkRules : {/subscriptions/subscriptionId/resourcegroups/ResourceGroup/providers/Microsoft.Network/virtualNetworks/sbehvnettest1/subnets/default, True}
```
Perbarui NetworkRuleSet menggunakan -ResourceId dari namespace lainnya.

## PARAMETERS

### -DefaultAction
Tindakan Default untuk NetworkRuleSet

```yaml
Type: System.String
Parameter Sets: NetworkRuleSetPropertiesSet
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

### -InputObject
Objek Konfigurasi NetworkruleSet

```yaml
Type: Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes
Parameter Sets: NetwrokruleSetInputObjectSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IPRule
Daftar IPRuleSet

```yaml
Type: Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetIpRulesAttributes[]
Parameter Sets: NetworkRuleSetPropertiesSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama Namespace ServiceBus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccess
Akses Jaringan Publik untuk NetwrokeuleSet

```yaml
Type: System.String
Parameter Sets: NetworkRuleSetPropertiesSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya Namespace

```yaml
Type: System.String
Parameter Sets: NetworkRuleSetResourceIdParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkRule
Daftar VirtualNetworkRules

```yaml
Type: Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetVirtualNetworkRulesAttributes[]
Parameter Sets: NetworkRuleSetPropertiesSet
Aliases: VirtualNteworkRule

Required: True
Position: 3
Default value: None
Accept pipeline input: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes

## NOTES

## RELATED LINKS