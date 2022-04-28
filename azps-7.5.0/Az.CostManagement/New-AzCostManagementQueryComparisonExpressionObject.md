---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.CostManagement/new-AzCostManagementQueryComparisonExpressionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryComparisonExpressionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryComparisonExpressionObject.md
ms.openlocfilehash: be0fa1af1d598a88fe2a113180111e8956f764f2
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205406"
---
# New-AzCostManagementQueryComparisonExpressionObject

## SYNOPSIS
Membuat objek dalam memori untuk QueryComparisonExpression

## SYNTAX

```
New-AzCostManagementQueryComparisonExpressionObject -Name <String> -Operator <OperatorType> -Value <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk QueryComparisonExpression

## EXAMPLES

### Contoh 1: Membuat objek ekspresi perbandingan kueri untuk ekspor manajemen biaya
```powershell
New-AzCostManagementQueryComparisonExpressionObject -Name 'ResourceLocation' -Value @('East US', 'West Europe')
```

```output
Name             Operator Value
----             -------- -----
ResourceLocation In       {East US, West Europe}
```

Perintah ini membuat objek ekspresi perbandingan kueri untuk ekspor manajemen biaya.

## PARAMETERS

### -Name
Nama kolom yang akan digunakan sebagai perbandingan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operator
Operator yang digunakan untuk perbandingan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.OperatorType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nilai
Array nilai yang akan digunakan untuk perbandingan.

```yaml
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.QueryComparisonExpression

## NOTES

ALIAS

## RELATED LINKS

