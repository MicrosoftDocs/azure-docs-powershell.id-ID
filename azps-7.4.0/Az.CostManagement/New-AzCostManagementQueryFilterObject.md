---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.CostManagement/new-AzCostManagementQueryFilterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryFilterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryFilterObject.md
ms.openlocfilehash: 12ae43996d5855ba7ce769352bd5d03a93c108cc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141839107"
---
# New-AzCostManagementQueryFilterObject

## SYNOPSIS
Membuat objek dalam memori untuk Filter Kueri

## SYNTAX

```
New-AzCostManagementQueryFilterObject [-And <IQueryFilter[]>] [-Dimensions <IQueryComparisonExpression>]
 [-Not <IQueryFilter>] [-Or <IQueryFilter[]>] [-Tag <IQueryComparisonExpression>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Filter Kueri

## EXAMPLES

### Contoh 1: Membuat objek filter kueri untuk ekspor manajemen biaya
```powershell
$orDimension = New-AzCostManagementQueryComparisonExpressionObject -Name 'ResourceLocation' -Value @('East US', 'West Europe')
$orTag = New-AzCostManagementQueryComparisonExpressionObject -Name 'Environment' -Value @('UAT', 'Prod')
New-AzCostManagementQueryFilterObject -or @((New-AzCostManagementQueryFilterObject -Dimensions $orDimension), (New-AzCostManagementQueryFilterObject -Tag $orTag))
```

```output
And       :
Dimension : Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryComparisonExpression
Not       : Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryFilter
Or        : {Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryFilter, Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryFilter}
Tag       : Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryComparisonExpression
```

perintah ini membuat objek filter kueri untuk ekspor manajemen biaya.

## PARAMETERS

### -Dan
Ekspresi "AND" logika.
Harus memiliki setidaknya 2 item.
Untuk membangun, lihat bagian CATATAN untuk properti AND dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryFilter[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dimensi
Memiliki ekspresi perbandingan untuk dimensi.
Untuk membangun, lihat bagian CATATAN untuk properti DIMENSI dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryComparisonExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tidak
Ekspresi logika "NOT".
Untuk membangun, lihat bagian CATATAN untuk properti NOT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryFilter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atau
Ekspresi "OR" logika.
Harus memiliki setidaknya 2 item.
Untuk membangun, lihat bagian CATATAN untuk properti OR dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryFilter[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Memiliki ekspresi perbandingan untuk tag.
Untuk membangun, lihat bagian CATATAN untuk properti TAG dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryComparisonExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.QueryFilter

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AND <IQueryFilter[]>: Ekspresi "AND" logika. Harus memiliki setidaknya 2 item.
  - `[And <IQueryFilter[]>]`: Ekspresi logika "AND". Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi logika "NOT".
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

DIMENSI <IQueryComparisonExpression>: Memiliki ekspresi perbandingan untuk dimensi.
  - `Name <String>`: Nama kolom yang digunakan sebagai perbandingan.
  - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan

NOT <IQueryFilter>: Ekspresi logika "NOT".
  - `[And <IQueryFilter[]>]`: Ekspresi logika "AND". Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi logika "NOT".
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

OR <IQueryFilter[]>: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[And <IQueryFilter[]>]`: Ekspresi logika "AND". Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi logika "NOT".
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

TAG <IQueryComparisonExpression>: Memiliki ekspresi perbandingan untuk tag.
  - `Name <String>`: Nama kolom yang digunakan sebagai perbandingan.
  - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan

## RELATED LINKS

