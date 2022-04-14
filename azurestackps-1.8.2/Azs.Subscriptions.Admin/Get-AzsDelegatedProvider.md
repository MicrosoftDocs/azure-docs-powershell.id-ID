---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: afc99afebed095da96d826918cc6912f197d1899
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142333709"
---
# Get-AzsDelegatedProvider

## SYNOPSIS
Dapatkan daftar delegasiProvider.

## SYNTAX

### Daftar (Default)
```
Get-AzsDelegatedProvider [<CommonParameters>]
```

### Mendapatkan
```
Get-AzsDelegatedProvider [-DelegatedProviderId] <Guid> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar delegasiProvider.

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
{{Fill DelegatedProviderId Description}}

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Subscriptions.Admin.Models.Subscription

## CATATAN

## RELATED LINKS

