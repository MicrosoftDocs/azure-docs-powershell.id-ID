---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/get-azdatadogmarketplaceagreement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogMarketplaceAgreement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogMarketplaceAgreement.md
ms.openlocfilehash: bd3424ddf68bd05f715756566f8acf63adde1a8b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142178994"
---
# Get-AzDatadogMarketplaceAgreement

## SYNOPSIS
Cantumkan perjanjian marketplace Datadog dalam langganan.

## SYNTAX

```
Get-AzDatadogMarketplaceAgreement [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Cantumkan perjanjian marketplace Datadog dalam langganan.

## EXAMPLES

### Contoh 1: Mencantumkan perjanjian marketplace Datadog dalam langganan
```powershell
Get-AzDatadogMarketplaceAgreement
```

```output
Name        Type
----        ----
marketplace Microsoft.Datadog/agreements
Datadog     Microsoft.Datadog/agreements
```

Perintah ini mencantumkan perjanjian marketplace Datadog dalam langganan.

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
ID langganan target.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.IDatadogAgreementResource

## CATATAN

ALIAS

## RELATED LINKS

