---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8305928648530220ca5f067455ec4014d5d212a966bd811efbf480c2d9ac9248
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415979"
---
# Move-AzsSubscription

## SYNOPSIS
Pindahkan langganan di antara penawaran penyedia yang didelegasikan.

## SYNTAX

```
Move-AzsSubscription [[-DestinationDelegatedProviderOffer] <String>] [-ResourceId] <String[]> [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
Pindahkan langganan di antara penawaran penyedia yang didelegasikan.
Proses ini hanya akan melakukan rebranding, penawaran, paket, dan kuota langganan yang mendasarinya tidak akan diubah.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Move user subscriptions to a delegated provider offer.
```

Move-AzsSubscription \` -DestinationDelegatedProviderOffer "/subscriptions/45ec4d39-8dea-4d26-a373-c176ec53717a/providers/Microsoft.Subscriptions.Admin/delegatedProviders/798568b7-c6f1-4bf7-bb8f-2c8bebc7c777/offers/ro1" -ResourceId "/subscriptions/45ec4d39-8dea-4d26-a373-c176ec53717a/providers/Microsoft.Subscriptions.Admin/subscriptions/ce4c7fdb-5a38-46f5-8bbc-b8b328a87ab6","/subscriptions/45ec4d39-8dea-4d26-a373-c176ec53717a/providers/Microsoft.Subscriptions. Admin/langganan/a0d1a71c-0b27-4e73-abfc-169512576f7d"

### -------------------------- CONTOH 2 --------------------------
```
Move user subscriptions from a delegated provider to the Default Provider.
```

$resourceIds = Get-AzsUserSubscription -Filter "offerName eq 'o1'" | di mana {$_. DelegatedProviderSubscriptionId -eq "798568b7-c6f1-4bf7-bb8f-2c8bebc7c777"} | Pilih -ExpandProperty Id Move-AzsSubscription -ResourceId $resourceIds

## PARAMETERS

### -AsJob
Menentukan apakah operasi pemindahan akan dijalankan sebagai pekerjaan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationDelegatedProviderOffer
Menentukan penawaran penyedia terdelegasi yang sepenuhnya memenuhi syarat untuk memindahkan langganan cmdlet ini.
NULL jika langganan akan dipindahkan kembali ke Penyedia Default.

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

### -ResourceId
Menentukan array pengidentifikasi sumber daya langganan yang sepenuhnya memenuhi syarat yang di pindahkan cmdlet ini.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

