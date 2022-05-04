---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.Quota/New-AzQuotaLimitObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuotaLimitObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuotaLimitObject.md
ms.openlocfilehash: f8a53078a4bb3c958676f62a9eb0e30909adfd90
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144577299"
---
# New-AzQuotaLimitObject

## SYNOPSIS
Buat objek dalam memori untuk LimitObject.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.quota/new-azquotalimitobject) untuk informasi terbaru.

## SYNTAX

```
New-AzQuotaLimitObject -Value <Int32> [-LimitType <QuotaLimitTypes>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk LimitObject.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk LimitValue
```powershell
New-AzQuotaLimitObject -Value 1003
```

```output
LimitObjectType LimitType Value
--------------- --------- -----
LimitValue                1003
```

Perintah ini membuat objek dalam memori untuk LimitValue sebagai nilai Batas parameter dalam cmdlet New/Update-AzQuota.

## PARAMETERS

### -LimitType
Jenis batas kuota atau penggunaan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Quota.Support.QuotaLimitTypes
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nilai
Nilai kuota/batas.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.LimitObject

## NOTES

ALIAS

## RELATED LINKS

