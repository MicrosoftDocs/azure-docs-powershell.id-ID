---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9b34256b06e5bd9de7da3ae35f66f6955a3c0c5a71776d5a7fd7315f094f8d65
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419047"
---
# Get-AzsUserSubscription

## SYNOPSIS
Dapatkan daftar langganan pengguna sebagai operator.

## SYNTAX

### Daftar (Default)
```
Get-AzsUserSubscription [-Filter <String>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsUserSubscription -SubscriptionId <Guid> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar langganan pengguna sebagai operator.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsUserSubscription
```

Dapatkan daftar langganan pengguna sebagai operator.

## PARAMETERS

### -Filter
Parameter filter OData.

```yaml
Type: String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Parameter Id Langganan.

```yaml
Type: Guid
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Subscriptions.Admin.Models.Subscription

## CATATAN

## RELATED LINKS

