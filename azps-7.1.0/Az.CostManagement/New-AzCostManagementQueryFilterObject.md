---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.CostManagement/new-AzCostManagementQueryFilterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryFilterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryFilterObject.md
ms.openlocfilehash: 8a22844ca59f1f4ae77ec89cfe5a9e4c9c8d552b
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136749004"
---
# New-AzCostManagementQueryFilterObject

## SYNOPSIS
Membuat objek dalam memori untuk QueryFilter

## SYNTAX

```
New-AzCostManagementQueryFilterObject [-And <IQueryFilter[]>] [-Dimensions <IQueryComparisonExpression>]
 [-Not <IQueryFilter>] [-Or <IQueryFilter[]>] [-Tag <IQueryComparisonExpression>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk QueryFilter

## EXAMPLES

### Contoh 1: Membuat objek filter kueri untuk ekspor manajemen biaya
```powershell
PS C:\> $orDimension = New-AzCostManagementQueryComparisonExpressionObject -Name 'ResourceLocation' -Value @('East US', 'West Europe')
PS C:\> $orTag = New-AzCostManagementQueryComparisonExpressionObject -Name 'Environment' -Value @('UAT', 'Prod')
PS C:\> New-AzCostManagementQueryFilterObject -or @((New-AzCostManagementQueryFilterObject -Dimension $orDimension), (New-AzCostManagementQueryFilterObject -Tag $orTag))

And       :
Dimension : Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryComparisonExpression
Not       : Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryFilter
Or        : {Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryFilter, Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryFilter}
Tag       : Microsoft.Azure.PowerShell.Cmdlets.Cost.Models.Api20200601.QueryComparisonExpression
```

perintah ini membuat objek filter kueri untuk ekspor manajemen biaya.

## PARAMETERS

### -And
Ekspresi "AND" logika.
Harus memiliki setidaknya 2 item.
Untuk membuat, lihat bagian CATATAN untuk properti AND dan membuat tabel hash.

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

### -Dimensions
Memiliki ekspresi perbandingan untuk dimensi.
Untuk membuat, lihat bagian CATATAN untuk properti DIMENSIONS dan membuat tabel hash.

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

### -Not
Ekspresi "NOT" logika.
Untuk membuat, lihat bagian CATATAN untuk properti NOT dan membuat tabel hash.

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
Untuk membuat, lihat bagian CATATAN untuk properti OR dan membuat tabel hash.

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
Untuk membuat, lihat bagian CATATAN untuk properti TAG dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.QueryFilter

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AND <IQueryFilter[]>: Ekspresi "AND" logika. Harus memiliki setidaknya 2 item.
  - `[And <IQueryFilter[]>]`: Ekspresi "AND" logika. Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang akan digunakan jika dibandingkan.
    - `Value <String[]>`: Array nilai yang digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi "NOT" logika.
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

DIMENSIONS <IQueryComparisonExpression> : Memiliki ekspresi perbandingan untuk dimensi.
  - `Name <String>`: Nama kolom yang akan digunakan jika dibandingkan.
  - `Value <String[]>`: Array nilai yang digunakan untuk perbandingan

NOT <IQueryFilter> : Ekspresi "NOT" logika.
  - `[And <IQueryFilter[]>]`: Ekspresi "AND" logika. Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang akan digunakan jika dibandingkan.
    - `Value <String[]>`: Array nilai yang digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi "NOT" logika.
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

ATAU <IQueryFilter[]>: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[And <IQueryFilter[]>]`: Ekspresi "AND" logika. Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang akan digunakan jika dibandingkan.
    - `Value <String[]>`: Array nilai yang digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi "NOT" logika.
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

TAG <IQueryComparisonExpression> : Memiliki ekspresi perbandingan untuk tag.
  - `Name <String>`: Nama kolom yang akan digunakan jika dibandingkan.
  - `Value <String[]>`: Array nilai yang digunakan untuk perbandingan

## RELATED LINKS

