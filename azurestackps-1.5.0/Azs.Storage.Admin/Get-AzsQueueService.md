---
external help file: Azs.Storage.Admin-help.xml
Module Name: Azs.Storage.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8eaea2f6651a6b3bd0282f5f8a120dd381a6bcd4d773491f518142f29d2b16f9
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417542"
---
# Get-AzsQueueService

## SYNOPSIS
Mengembalikan layanan antrean.

## SYNTAX

```
Get-AzsQueueService [-FarmName] <String> [-ResourceGroupName <String>] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan layanan antrean.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsQueueService -FarmName f9b8e2e2-e4b4-44e0-9d92-6a848b1a5376
```

Dapatkan layanan antrean.

## PARAMETERS

### -FarmName
Id Farm.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management. Storage. Admin.Models.QueueService

## CATATAN

## RELATED LINKS

