---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayavailablewafruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayAvailableWafRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayAvailableWafRuleSet.md
ms.openlocfilehash: c8ea6e4cb9cdea9d34a1ea2f3ef8efaf8f01352f
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145809828"
---
# Get-AzApplicationGatewayAvailableWafRuleSet

## SYNOPSIS
Mendapatkan semua seperangkat aturan firewall aplikasi web yang tersedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azapplicationgatewayavailablewafruleset) untuk informasi terbaru.

## SYNTAX

```
Get-AzApplicationGatewayAvailableWafRuleSet [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayAvailableWafRuleSet** mendapatkan semua seperangkat aturan firewall aplikasi web yang tersedia.

## EXAMPLES

### Contoh 1
```powershell
$availableRuleSets = Get-AzApplicationGatewayAvailableWafRuleSet
```

Perintah ini mengembalikan semua seperangkat aturan firewall aplikasi web yang tersedia.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAvailableWafRuleSetsResult

## NOTES
**List-AzApplicationGatewayAvailableWafRuleSets** adalah alias untuk cmdlet **Get-AzApplicationGatewayAvailableWafRuleSet** .

## RELATED LINKS
