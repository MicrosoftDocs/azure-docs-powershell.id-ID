---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet.md
ms.openlocfilehash: 330be4785f259522b62d8a0dc96591ddd35bcf8a
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144706080"
---
# New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet

## SYNOPSIS
Membuat ExclusionManagedRuleSet untuk pengecualian firewallPolicy

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedruleset) untuk informasi terbaru.

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
