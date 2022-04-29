---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedrulegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup.md
ms.openlocfilehash: af8a92ad26985c98080e84f8b05b3e95df83d28c
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144217187"
---
# New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup

## SYNOPSIS
Membuat entri ExclusionManagedRuleGroup di ExclusionManagedRuleSets untuk pengecualian kebijakan firewall.

## SYNTAX

```
New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup -RuleGroupName <String>
 [-Rule <PSApplicationGatewayFirewallPolicyExclusionManagedRule[]>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
**New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup** membuat entri exclusionManagedRuleGroup dalam exclusionManagedRuleSet untuk pengecualian kebijakan firewall.

## EXAMPLES

### Contoh 1
```powershell
$ruleGroupEntry = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup -RuleGroupName $ruleName -Rules $rule1,$rule2
```

Membuat entri ExclusionManagedRuleGroup dengan nama grup sebagai $ruleName dan Aturan sebagai $rule 1, $rule 2. Menetapkan hal yang sama untuk $ruleGroupEntry

### Contoh 2
```powershell
$ruleGroupEntry = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup -RuleGroupName $ruleName
```

Membuat entri ExclusionManagedRuleGroup dengan nama grup sebagai $ruleName. Menetapkan hal yang sama untuk $ruleGroupEntry

## PARAMETERS

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

### -Aturan
Daftar Aturan.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleGroupName
Tentukan ruleGroupName dalam entri RuleGroup pengecualian.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleGroup

## NOTES

## RELATED LINKS
