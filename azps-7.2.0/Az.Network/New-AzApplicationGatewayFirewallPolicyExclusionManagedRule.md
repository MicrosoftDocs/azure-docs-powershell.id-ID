---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusionmanagedrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusionManagedRule.md
ms.openlocfilehash: 3e0fb694bbe55f20028826699819a75d591c38fd
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138311196"
---
# New-AzApplicationGatewayFirewallPolicyExclusionManagedRule

## SYNOPSIS
Membuat entri exclusionManagedRule untuk entri ExclusionManagedRuleGroup.

## SYNTAX

```
New-AzApplicationGatewayFirewallPolicyExclusionManagedRule -RuleId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**New-AzApplicationGatewayFirewallPolicyExclusionManagedRule** membuat entri aturan pengecualian.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $ruleOverrideEntry = New-AzApplicationGatewayFirewallPolicyExclusionManagedRule -RuleId $ruleId
```

Membuat aturan pengecualian Entri dengan RuleId sebagai $ruleId.

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

### -RuleId
Tentukan RuleId dalam entri aturan pengecualian.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRule

## CATATAN

## RELATED LINKS
