---
external help file: ''
Module Name: Az.Confluent
online version: https://docs.microsoft.com/powershell/module/az.confluent/get-azconfluentmarketplaceagreement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Confluent/help/Get-AzConfluentMarketplaceAgreement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Confluent/help/Get-AzConfluentMarketplaceAgreement.md
ms.openlocfilehash: 23d15034be85e11f2973ebac0419a4f8acfc11b1
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145777638"
---
# Get-AzConfluentMarketplaceAgreement

## SYNOPSIS
Mencantumkan perjanjian marketplace Confluent dalam langganan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.confluent/get-azconfluentmarketplaceagreement) untuk informasi terbaru.

## SYNTAX

```
Get-AzConfluentMarketplaceAgreement [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan perjanjian marketplace Confluent dalam langganan.

## EXAMPLES

### Contoh 1: Mencantumkan semua perjanjian marketplace confluent berdasarkan langganan
```powershell
Get-AzConfluentMarketplaceAgreement
```

```output
Name        Type
----        ----
marketplace Microsoft.Confluent/agreements
confluent   Microsoft.Confluent/offertypes
```

Perintah ini mencantumkan semua perjanjian marketplace confluent berdasarkan langganan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
id langganan Microsoft Azure

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Confluent.Models.Api20200301.IConfluentAgreementResource

## NOTES

ALIAS

## RELATED LINKS

