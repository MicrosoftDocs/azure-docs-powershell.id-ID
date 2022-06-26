---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.costmanagement/invoke-azcostmanagementquery
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Invoke-AzCostManagementQuery.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Invoke-AzCostManagementQuery.md
ms.openlocfilehash: 8e9c9ff2964f453ace91a5e4c540bfdaaf279bcd
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146597172"
---
# Invoke-AzCostManagementQuery

## SYNOPSIS
Kueri data penggunaan untuk cakupan yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.costmanagement/invoke-azcostmanagementquery) untuk informasi terbaru.

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
Kueri data penggunaan untuk cakupan yang ditentukan.

## EXAMPLES

### Contoh 1: Memanggil AzCostManagementQuery berdasarkan Cakupan
```powershell
Invoke-AzCostManagementQuery -Scope "/subscriptions/***********" -Timeframe MonthToDate -Type Usage -DatasetGranularity 'Daily'
```

```output
Column                Row
------                ---
{UsageDate, Currency} {20201101 USD, 20201102 USD, 20201103 USD, 20201104 USD…}
```

Panggil AzCostManagementQuery berdasarkan Cakupan

### Contoh 2: Memanggil AzCostManagementQuery berdasarkan Cakupan dengan Dimensi
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

Panggil AzCostManagementQuery berdasarkan Cakupan dengan Dimensi

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
Untuk membuat, lihat bagian CATATAN untuk properti DATASETFILTER dan buat tabel hash.

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
Untuk membuat, lihat bagian CATATAN untuk properti DATASETGROUPING dan buat tabel hash.

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
Ini bisa menjadi '{externalSubscriptionId}' untuk akun tertaut atau '{externalBillingAccountId}' untuk akun terkonsolidasi yang digunakan dengan operasi dimensi/kueri.

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
Jenis penyedia cloud eksternal yang terkait dengan operasi dimensi/kueri.

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

### -Cakupan
Ini termasuk 'subscriptions/{subscriptionId}/' untuk cakupan langganan, 'subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}' untuk cakupan resourceGroup, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}' untuk cakupan Akun Penagihan dan 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/departments/{departmentId}' untuk lingkup Departemen, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/enrollmentAccounts/{ enrollmentAccountId}' untuk cakupan EnrollmentAccount, 'providers/Microsoft.Management/managementGroups/{managementGroupId} untuk cakupan Grup Manajemen, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/billingProfiles/{billingProfileId}' untuk cakupan billingProfile, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/billingProfiles/{billingProfileId}/invoiceSections/{invoiceSectionId}' untuk cakupan invoiceSection, dan 'providers/Microsoft. Billing/billingAccounts/{billingAccountId}/customers/{customerId}' khusus untuk mitra.

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
Tanggal mulai untuk menarik data.

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

### -Type
Jenis kueri.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IQueryResult

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DATASETFILTER `<IQueryFilter>`: Memiliki ekspresi filter untuk digunakan dalam kueri.
  - `[And <IQueryFilter[]>]`: Ekspresi "AND" logis. Harus memiliki setidaknya 2 item.
  - `[Dimensions <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk dimensi
    - `Name <String>`: Nama kolom yang akan digunakan sebagai perbandingan.
    - `Value <String[]>`: Array nilai yang akan digunakan untuk perbandingan
  - `[Not <IQueryFilter>]`: Ekspresi "NOT" logis.
  - `[Or <IQueryFilter[]>]`: Ekspresi "OR" logis. Harus memiliki setidaknya 2 item.
  - `[Tag <IQueryComparisonExpression>]`: Memiliki ekspresi perbandingan untuk tag

DATASETGROUPING <IQueryGrouping[]>: Array grup menurut ekspresi untuk digunakan dalam kueri.
  - `Name <String>`: Nama kolom untuk dikelompokkan.
  - `Type <QueryColumnType>`: Memiliki jenis kolom untuk dikelompokkan.

## RELATED LINKS

