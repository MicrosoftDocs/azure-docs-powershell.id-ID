---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: b48af0f1b95e388882e13a5cf2d2e34be4e7ffb5e83f4a6b0cffe006e0523b78
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132413732"
---
# Get-AzsDelegatedProvider

## SYNOPSIS
Dapatkan daftar delegasiProviders.

## SYNTAX

### Daftar (Default)
```
Get-AzsDelegatedProvider [<CommonParameters>]
```

### Dapatkan
```
Get-AzsDelegatedProvider [-DelegatedProviderId] <Guid> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar delegasiProviders.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsDelegatedProvider
```

Dapatkan daftar penyedia yang didelegasikan.

### -------------------------- CONTOH 2 --------------------------
```
Get-AzsDelegatedProvider -DelegatedProviderId "c90173b1-de7a-4b1d-8600-b832b0e65946"
```

Dapatkan penyedia tertentu yang didelegasikan.

## PARAMETERS

### -DelegatedProviderId
Pengidentifikasi DelegasiProvider.

```yaml
Type: Guid
Parameter Sets: Get
Aliases: 

Required: True
Position: 1
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

