---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: a4bd00dc1709a3060da9777ab4755ae1c6a28ec4
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136577570"
---
# Test-AzsNameAvailability

## SYNOPSIS
Mengembalikan ketersediaan tipe sumber daya langganan dan nama yang ditentukan

## SYNTAX

```
Test-AzsNameAvailability -Name <String> -ResourceType <String> [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan ketersediaan tipe sumber daya langganan dan nama yang ditentukan

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Test-AzsNameAvailability -ResourceType "Microsoft.Subscriptions.Admin/offers" -Name offername1
```

Mengembalikan ketersediaan tipe sumber daya langganan dan nama yang ditentukan

## PARAMETERS

### -Nama
Nama sumber daya untuk memverifikasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Tipe sumber daya untuk memverifikasi.

```yaml
Type: String
Parameter Sets: (All)
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

### Microsoft.AzureStack.Management.Subscriptions.Admin.Models.CheckNameAvailabilityResponse

## CATATAN

## RELATED LINKS

