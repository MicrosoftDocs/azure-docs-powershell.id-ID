---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet.md
ms.openlocfilehash: d0608a4103e62ab188387c30236639f345820a91
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145509034"
---
# New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet

## SYNOPSIS
Membuat ExclusionManagedRuleSet untuk pengecualian firewallPolicy

## SYNTAX

```
New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet -RuleSetType <String> -RuleSetVersion <String>
 [-RuleGroup <PSApplicationGatewayFirewallPolicyExclusionManagedRuleGroup[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet** membuat aturan terkelola pengecualian untuk pengecualian kebijakan firewall.

## EXAMPLES

### Contoh 1
```powershell
$managedRuleSet = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet -RuleSetType $ruleSetType 
-RuleSetVersion $ruleSetVersion -RuleGroup $ruleGroup1, $ruleGroup2
```

Membuat ExclusionManagedRuleSet dengan ruleSetType sebagai $ruleSetType, ruleSetVersion sebagai $ruleSetVersion dan RuleGroups sebagai daftar dengan keseluruhan sebagai $ruleGroup 1, $ruleGroup 2 ExclusionManagedRuleSet baru ditetapkan ke $managedRuleSet

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

### -RuleGroup
Penimpaan Grup Aturan.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleGroup[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleSetType
Tentukan RuleSetType dalam exclusionManagedRuleSet

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

### -RuleSetVersion
Tentukan RuleSetVersion dalam exclusionManagedRuleSet

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleSet

## NOTES

## RELATED LINKS
