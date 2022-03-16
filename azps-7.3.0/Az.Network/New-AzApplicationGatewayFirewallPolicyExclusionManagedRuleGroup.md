---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedrulegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup.md
ms.openlocfilehash: ad66f3af00e5589d276cf53361bd241d17f65b53
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140003470"
---
# New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup

## SYNOPSIS
Membuat entri ExclusionManagedRuleGroup dalam ExclusionManagedRuleSets untuk pengecualian kebijakan firewall.

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
PS C:\> $ruleGroupEntry = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup -RuleGroupName $ruleName -Rules $rule1,$rule2
```

Membuat entri ExclusionManagedRuleGroup dengan nama grup sebagai $ruleName dan Aturan sebagai $rule 1, $rule 2. Menetapkan tugas yang sama $ruleGroupEntry

### Contoh 2
```powershell
PS C:\> $ruleGroupEntry = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup -RuleGroupName $ruleName
```

Membuat entri ExclusionManagedRuleGroup dengan nama grup sebagai $ruleName. Menetapkan tugas yang sama $ruleGroupEntry

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

### -Rule
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
Tentukan aturanGroupName dalam entri pengecualian Grup Aturan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleGroup

## CATATAN

## RELATED LINKS
