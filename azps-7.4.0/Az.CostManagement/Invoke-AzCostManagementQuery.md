---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.costmanagement/invoke-azcostmanagementquery
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Invoke-AzCostManagementQuery.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Invoke-AzCostManagementQuery.md
ms.openlocfilehash: d8db8bb75ec43d324ba12e85460071c77ebba6ba
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143125901"
---
# Invoke-AzCostManagementQuery

## SYNOPSIS
Buat kueri data penggunaan untuk lingkup yang ditentukan.

## SYNTAX

### UsageExpanded (Default)
```
Invoke-AzCostManagementQuery -Scope <String> -Timeframe <TimeframeType> -Type <ExportType>
 [-ConfigurationColumn <String[]>] [-DatasetAggregation <Hashtable>] [-DatasetFilter <IQueryFilter>]
 [-DatasetGranularity <GranularityType>] [-DatasetGrouping <IQueryGrouping[]>] [-TimePeriodFrom <DateTime>]
 [-TimePeriodTo <DateTime>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UsageExpanded1
```
Invoke-AzCostManagementQuery -ExternalCloudProviderId <String>
 -ExternalCloudProviderType <ExternalCloudProviderType> -Timeframe <TimeframeType> -Type <ExportType>
 [-ConfigurationColumn <String[]>] [-DatasetAggregation <Hashtable>] [-DatasetFilter <IQueryFilter>]
 [-DatasetGranularity <GranularityType>] [-DatasetGrouping <IQueryGrouping[]>] [-TimePeriodFrom <DateTime>]
 [-TimePeriodTo <DateTime>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Buat kueri data penggunaan untuk lingkup yang ditentukan.

## EXAMPLES

### Contoh 1: Invoke AzCostManagementQuery by Scope
```powershell
Invoke-AzCostManagementQuery -Scope "/subscriptions/***********" -Timeframe MonthToDate -Type Usage -DatasetGranularity 'Daily'
```

```output
Column                Row
------                ---
{UsageDate, Currency} {20201101 USD, 20201102 USD, 20201103 USD, 20201104 USD…}
```

Memanggil AzCostManagementQuery menurut Lingkup

### Contoh 2: Memanggil AzCostManagementQuery menurut Lingkup dengan Dimensi
```powershell
$dimensions = New-AzCostManagementQueryComparisonExpressionObject -Name 'ResourceGroup' -Value 'API'
$filter = New-AzCostManagementQueryFilterObject -Dimensions $dimensions
Invoke-AzCostManagementQuery -Type Usage -Scope "subscriptions/***********" -DatasetGranularity 'Monthly' -DatasetFilter $filter -Timeframe MonthToDate -Debug
```

```output
Column                   Row
------                   ---
{BillingMonth, Currency} {}
```

Memanggil AzCostManagementQuery menurut Lingkup dengan Dimensi

## PARAMETERS

### -ConfigurationColumn
Array nama kolom yang akan disertakan dalam kueri.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasetAggregation
Kamus ekspresi agregasi untuk digunakan dalam kueri.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasetFilter
Memiliki ekspresi filter untuk digunakan dalam kueri.
Untuk membangun, lihat bagian CATATAN untuk properti DATASETFILTER dan membuat tabel hash.

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

### -DatasetGranularity
Granularitas baris dalam kueri.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.GranularityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasetGrouping
Array grup menurut ekspresi untuk digunakan dalam kueri.
Untuk membangun, lihat bagian CATATAN untuk properti DATASETGROUPING dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryGrouping[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalCloudProviderId
Ini dapat berupa '{externalSubscriptionId}' untuk akun tertaut atau '{externalBillingAccountId}' untuk akun konsolidasi yang digunakan dengan operasi dimensi/kueri.

```yaml
Type: System.String
Parameter Sets: UsageExpanded1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalCloudProviderType
Tipe penyedia awan eksternal yang terkait dengan operasi dimensi/kueri.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.ExternalCloudProviderType
Parameter Sets: UsageExpanded1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Ini termasuk 'subscriptions/{subscriptionId}/' untuk lingkup langganan, 'subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}' untuk lingkup resourceGroup, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}' untuk lingkup Akun Penagihan dan 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/departments/{departmentId}' untuk lingkup Departemen, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/enrollmentAccounts/{ pendaftaranAccountId}' untuk lingkup EnrollmentAccount, 'providers/Microsoft.Management/managementGroups/{managementGroupId} untuk lingkup Grup Manajemen, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/billingProfiles/{billingProfileId}' untuk lingkup billingProfile, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/billingProfiles/{billingProfileId}/invoiceSections/{invoiceSectionId}' untuk lingkup invoiceSection, dan 'providers/Microsoft. Tagihan/tagihanAccounts/{billingAccountId}/customers/{customerId}' khusus untuk mitra.

```yaml
Type: System.String
Parameter Sets: UsageExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jangka waktu
Jangka waktu untuk menarik data untuk kueri.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.TimeframeType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimePeriodFrom
Tanggal mulai untuk menarik data dari.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimePeriodTo
Tanggal akhir untuk menarik data.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Tipe kueri.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.ExportType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryResult

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DATASETFILTER <IQueryFilter>: Memiliki ekspresi filter untuk digunakan dalam kueri.
  - `[And <IQueryFilter[]>]`: Ekspresi logika "AND". Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi logika "NOT".
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logika. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

DATASETGROUPING <IQueryGrouping[]>: Array grup menurut ekspresi untuk digunakan dalam kueri.
  - `Name <String>`: Nama kolom untuk dikelompokkan.
  - `Type <QueryColumnType>`: Memiliki tipe kolom untuk dikelompokkan.

## RELATED LINKS

