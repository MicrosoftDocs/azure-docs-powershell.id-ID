---
external help file: Azs.Subscriptions-help.xml
Module Name: Azs.Subscriptions
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1556e058b4069c372f067b8d14ff8818768be7f92eedeca692c00f2ae54a6f57
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415952"
---
# Get-AzsOffer

## SYNOPSIS
Dapatkan daftar penawaran publik.

## SYNTAX

```
Get-AzsOffer [[-Skip] <Int32>] [[-Top] <Int32>] [[-Provider] <String>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar penawaran publik.

## EXAMPLES

### CONTOH 1
```
Get-AzsOffer | fl
```

Dapatkan daftar penawaran publik.

## PARAMETERS

### -Lewati
Lewati item N pertama seperti yang ditentukan oleh nilai parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Mengembalikan item N teratas seperti yang ditentukan oleh nilai parameter.
Berlaku setelah parameter -Skip.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Provider
Parameter opsional untuk menentukan nama penyedia yang didelegasikan. Parameter ini tidak digunakan dan akan tidak digunakan lagi di masa mendatang.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Subscription.Models.Offer

## CATATAN

## RELATED LINKS
