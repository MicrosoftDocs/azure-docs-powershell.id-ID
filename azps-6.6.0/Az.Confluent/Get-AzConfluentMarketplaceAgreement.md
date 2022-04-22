---
external help file: ''
Module Name: Az.Confluent
online version: https://docs.microsoft.com/powershell/module/az.confluent/get-azconfluentmarketplaceagreement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Confluent/help/Get-AzConfluentMarketplaceAgreement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Confluent/help/Get-AzConfluentMarketplaceAgreement.md
ms.openlocfilehash: 08eaf93f1b4d669907a87c9e7dc8080ed4f04d82
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143032139"
---
# Get-AzConfluentMarketplaceAgreement

## SYNOPSIS
Cantumkan perjanjian marketplace konfluen dalam langganan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.confluent/get-azconfluentmarketplaceagreement) untuk informasi terbaru.

## SYNTAX

```
Get-AzConfluentMarketplaceAgreement [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Cantumkan perjanjian marketplace konfluen dalam langganan.

## EXAMPLES

### Contoh 1: Cantumkan semua perjanjian marketplace confluent di bawah langganan
```powershell
PS C:\> Get-AzConfluentMarketplaceAgreement

Name        Type
----        ----
marketplace Microsoft.Confluent/agreements
confluent   Microsoft.Confluent/offertypes
```

Perintah ini mencantumkan semua perjanjian marketplace konferensi di bawah langganan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Confluent.Models.Api20200301.IConfluentAgreementResource

## NOTES

ALIAS

## RELATED LINKS

