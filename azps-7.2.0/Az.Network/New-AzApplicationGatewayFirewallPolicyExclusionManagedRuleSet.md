---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet.md
ms.openlocfilehash: 07ff21c6b15c0405fafe2f068613aa2717afba06
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140230777"
---
# New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet

## SYNOPSIS
Membuat ExclusionManagedRuleSet untuk pengecualian firewallPolicy

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedruleset) untuk informasi terkini.

## SYNTAX

```
New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet -RuleSetType <String> -RuleSetVersion <String>
 [-RuleGroup <PSApplicationGatewayFirewallPolicyExclusionManagedRuleGroup[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet** membuat pengecualian aturan terkelola untuk pengecualian kebijakan firewall.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $managedRuleSet = New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet -RuleSetType $ruleSetType 
-RuleSetVersion $ruleSetVersion -RuleGroup $ruleGroup1, $ruleGroup2
```

Membuat ExclusionManagedRuleSet dengan ruleSetType sebagai $ruleSetType, ruleSetVersion sebagai $ruleSetVersion dan RuleGroups sebagai daftar dengan seluruh sebagai $ruleGroup 1, $ruleGroup 2 ExclusionManagedRuleSet baru ditetapkan untuk $managedRuleSet

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
Pengabaian Grup Aturan.

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
Menentukan RuleSetType dalam pengecualianManagedRuleSet

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
Menentukan RuleSetVersion dalam pengecualianManagedRuleSet

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleSet

## CATATAN

## RELATED LINKS
