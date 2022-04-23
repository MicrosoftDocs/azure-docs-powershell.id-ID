---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4403232b45b2a1e69d6148a118e69ccaf80e4a1e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143101403"
---
# Get-AzsUserSubscription

## SYNOPSIS
Dapatkan daftar langganan pengguna sebagai administrator.

## SYNTAX

### Daftar (Default)
```
Get-AzsUserSubscription [-Filter <String>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzsUserSubscription -SubscriptionId <Guid> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar langganan pengguna sebagai administrator.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsUserSubscription
```

Dapatkan daftar langganan pengguna sebagai administrator.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Subscriptions.Admin.Models.Subscription

## NOTES

## RELATED LINKS

