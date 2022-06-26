---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.CostManagement/new-AzCostManagementQueryFilterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryFilterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementQueryFilterObject.md
ms.openlocfilehash: 94a8d0c4c71dff519f45daa647ec0d6d19261158
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146635238"
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
Ekspresi "AND" logis.
Harus memiliki setidaknya 2 item.
Untuk membuat, lihat bagian CATATAN untuk properti AND dan buat tabel hash.

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

### -Tidak
Ekspresi "NOT" logis.
Untuk membuat, lihat bagian CATATAN untuk properti NOT dan buat tabel hash.

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
Ekspresi "OR" logis.
Harus memiliki setidaknya 2 item.
Untuk membuat, lihat bagian CATATAN untuk properti OR dan buat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.QueryFilter

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


AND <IQueryFilter[]>: Ekspresi "AND" logis. Harus memiliki setidaknya 2 item.
  - `[And <IQueryFilter[]>]`: Ekspresi "AND" logis. Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang akan digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi "NOT" logis.
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logis. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

DIMENSIONS `<IQueryComparisonExpression>`: Memiliki ekspresi perbandingan untuk dimensi.
  - `Name <String>`: Nama kolom yang akan digunakan sebagai perbandingan.
  - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan

NOT `<IQueryFilter>`: Ekspresi logis "NOT".
  - `[And <IQueryFilter[]>]`: Ekspresi "AND" logis. Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang akan digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi "NOT" logis.
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logis. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

OR <IQueryFilter[]>: Ekspresi "OR" logis. Harus memiliki setidaknya 2 item.
  - `[And <IQueryFilter[]>]`: Ekspresi "AND" logis. Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang akan digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi "NOT" logis.
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logis. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

TAG `<IQueryComparisonExpression>`: Memiliki ekspresi perbandingan untuk tag.
  - `Name <String>`: Nama kolom yang akan digunakan sebagai perbandingan.
  - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan

## RELATED LINKS

