---
external help file: Microsoft.Azure.PowerShell.Cmdlets.FrontDoor.dll-Help.xml
Module Name: Az.FrontDoor
online version: https://docs.microsoft.com/powershell/module/az.frontdoor/get-azfrontdoorwafmanagedrulesetdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FrontDoor/FrontDoor/help/Get-AzFrontDoorWafManagedRuleSetDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FrontDoor/FrontDoor/help/Get-AzFrontDoorWafManagedRuleSetDefinition.md
ms.openlocfilehash: 29c638ed70143927aa9b5efb4746037f722a56de
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144737740"
---
# Get-AzFrontDoorWafManagedRuleSetDefinition

## SYNOPSIS
Mendapatkan definisi seperangkat aturan terkelola WAF

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.frontdoor/get-azfrontdoorwafmanagedrulesetdefinition) untuk informasi terbaru.

## SYNTAX

```
Get-AzFrontDoorWafManagedRuleSetDefinition [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar definisi seperangkat aturan terkelola WAF untuk digunakan sebagai referensi

## EXAMPLES

### Contoh 1
```powershell
Get-AzFrontDoorWafManagedRuleSetDefinition
```

```output
ProvisioningState RuleSetType                 RuleSetVersion RuleGroups
----------------- -----------                 -------------- ----------
Succeeded         DefaultRuleSet              1.0            {PROTOCOL-ATTACK, LFI, RFI, RCE...}
Succeeded         Microsoft_BotManagerRuleSet 1.0            {BadBots, GoodBots, UnknownBots}
Succeeded         DefaultRuleSet              preview-0.1    {LFI, RFI, RCE, PHP...}
Succeeded         BotProtection               preview-0.1    {KnownBadBots}
```

Mendapatkan definisi seperangkat aturan terkelola WAF.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.FrontDoor.Models.PSManagedRuleSetDefinition

## NOTES

## RELATED LINKS

[New-AzFrontDoorWafManagedRuleObject](./New-AzFrontDoorWafManagedRuleObject.md)
 [New-AzFrontDoorWafManagedRuleOverrideObject](./New-AzFrontDoorWafManagedRuleOverrideObject.md)
 [New-AzFrontDoorWafRuleGroupOverrideObject](./New-AzFrontDoorWafRuleGroupOverrideObject.md)
