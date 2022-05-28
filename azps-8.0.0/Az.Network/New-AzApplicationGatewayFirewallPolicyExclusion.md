---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusion.md
ms.openlocfilehash: 3847179dbfbd3c71765cc36e78157fefb0bd4d3e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145520326"
---
# New-AzApplicationGatewayFirewallPolicyExclusion

## SYNOPSIS
Membuat pengecualian pada Kebijakan Firewall

## SYNTAX

```
New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable <String> -SelectorMatchOperator <String>
 -Selector <String> [-ExclusionManagedRuleSet <PSApplicationGatewayFirewallPolicyExclusionManagedRuleSet[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewayFirewallPolicyExclusion** daftar aturan pengecualian baru untuk kebijakan firewall.

## EXAMPLES

### Contoh 1
```powershell
$exclusionEntry = New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable "RequestHeaderNames" -SelectorMatchOperator "StartsWith" -Selector "xyz"
```

Perintah ini membuat entri pengecualian baru untuk variabel bernama RequestHeaderNames dan operator bernama StartsWith dan Selector bernama xyz. Entri pengecualian disimpan dalam $exclusionEntry.

### Contoh 2
```powershell
$exclusionEntry = New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable "RequestHeaderKeys" -SelectorMatchOperator "Contains" -Selector "abc"
```

Perintah ini membuat entri pengecualian baru untuk variabel bernama RequestHeaderKeys dan operator bernama Contains and Selector bernama abc. Entri pengecualian disimpan dalam $exclusionEntry.

### Contoh: 3
```powershell
$exclusionEntry = New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable "RequestHeaderNames" -SelectorMatchOperator "StartsWith" -Selector "xyz" -ExclusionManagedRuleSet $exclusionManagedRuleSet
```

Perintah ini membuat exclusion-entry baru untuk variabel bernama RequestHeaderNames dan operator bernama StartsWith, Selector bernama xyz dan ExclusionManagedRuleSet bernama $exclusionManagedRuleSet. Entri pengecualian disimpan dalam $exclusionEntry.

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

### -MatchVariable
Variabel yang akan dikecualikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: RequestHeaderNames, RequestCookieNames, RequestArgNames, RequestHeaderKeys, RequestCookieKeys, RequestArgKeys, RequestHeaderValues, RequestCookieValues, RequestArgValues

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pemilih
Ketika variabel adalah koleksi, operator digunakan untuk menentukan elemen mana dalam koleksi tempat pengecualian ini berlaku.

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

### -SelectorMatchOperator
Ketika variabel adalah koleksi, operasikan pada pemilih untuk menentukan elemen mana dalam koleksi tempat pengecualian ini berlaku.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Equals, Contains, StartsWith, EndsWith, EqualsAny

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionManagedRuleSet
Daftar Sekumpulan Aturan Terkelola Pengecualian.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleSet[]
Parameter Sets: (All)
Aliases:

Required: False
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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusion

## NOTES

## RELATED LINKS
