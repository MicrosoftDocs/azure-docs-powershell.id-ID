---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedrulegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup.md
ms.openlocfilehash: af8a92ad26985c98080e84f8b05b3e95df83d28c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141834992"
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
**New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup** membuat entri exclusionManagedRuleGroup dalam pengecualianManagedRuleSet untuk pengecualian kebijakan firewall.

## EXAMPLES

### Contoh 1
```powershell
$ruleGroupEntry = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup -RuleGroupName $ruleName -Rules $rule1,$rule2
```

Membuat entri ExclusionManagedRuleGroup dengan nama grup sebagai $ruleName dan Aturan sebagai $rule 1, $rule 2. Menetapkan hal yang sama ke $ruleGroupEntry

### Contoh 2
```powershell
$ruleGroupEntry = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup -RuleGroupName $ruleName
```

Membuat entri ExclusionManagedRuleGroup dengan nama grup sebagai $ruleName. Menetapkan hal yang sama ke $ruleGroupEntry

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
Tentukan ruleGroupName dalam entri pengecualian RuleGroup.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleGroup

## CATATAN

## RELATED LINKS
