---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: e629aeea32bd4dcdd3b54de5515884a51f3267a9b712798dc9f581af0e7f23f0
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418787"
---
# Get-AzsUserSubscription

## SYNOPSIS
Dapatkan daftar langganan pengguna sebagai administrator.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Subscriptions.Admin.Models.Subscription

## CATATAN

## RELATED LINKS

