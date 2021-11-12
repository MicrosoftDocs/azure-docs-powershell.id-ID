---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: e329c948969d49f07f5ee592219bdc7bddbc37b281295436d92ec67015fd5fdb
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417248"
---
# New-AzsAddonPlanDefinitionObject

## SYNOPSIS
Berisi nama rencana yang diinginkan untuk ditautkan atau tidak ditautkan dari penawaran.

## SYNTAX

```
New-AzsAddonPlanDefinitionObject [[-PlanId] <String>] [[-MaxAcquisitionCount] <Int64>] [<CommonParameters>]
```

## DESCRIPTION
Berisi nama rencana yang diinginkan untuk ditautkan atau tidak ditautkan dari penawaran.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
New-AzsAddonPlanDefinitionObject -PlanId $planIdentifier -MaxAcquisitionCount 500
```

Buat objek definisi rencana baru untuk paket tertentu dengan batas akuisisi 500.

## PARAMETERS

### -MaxAcquisitionCount
Jumlah maksimum instans yang dapat diperoleh dengan satu langganan.
Jika tidak ditentukan, nilai yang diasumsikan adalah 1.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlanId
Merencanakan pengidentifikasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

