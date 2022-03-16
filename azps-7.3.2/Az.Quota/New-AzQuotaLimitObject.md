---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.Quota/New-AzQuotaLimitObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuotaLimitObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuotaLimitObject.md
ms.openlocfilehash: a94bfc8ef63991ae52db17e6b453c5c04d72de56
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140196391"
---
# New-AzQuotaLimitObject

## SYNOPSIS
Buat objek dalam memori untuk LimitObject.

## SYNTAX

```
New-AzQuotaLimitObject -Value <Int32> [-LimitType <QuotaLimitTypes>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk LimitObject.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk LimitValue
```powershell
PS C:\> New-AzQuotaLimitObject -Value 1003

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.LimitObject

## CATATAN

ALIAS

## RELATED LINKS

