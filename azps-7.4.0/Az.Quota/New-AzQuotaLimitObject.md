---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.Quota/New-AzQuotaLimitObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuotaLimitObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuotaLimitObject.md
ms.openlocfilehash: f60fb72cb6532e4bb0faeec8ffd0b4baaf398fd1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143310887"
---
# New-AzQuotaLimitObject

## SYNOPSIS
Membuat objek dalam memori untuk LimitObject.

## SYNTAX

```
New-AzQuotaLimitObject -Value <Int32> [-LimitType <QuotaLimitTypes>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk LimitObject.

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

Perintah ini membuat objek dalam memori untuk LimitValue sebagai nilai batas parameter dalam cmdlet Baru/Pembaruan-AzQuota.

## PARAMETERS

### -LimitType
Tipe batas kuota atau penggunaan.

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

### -Value
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.LimitObject

## NOTES

ALIAS

## RELATED LINKS

