---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.costmanagement/new-azcostmanagementexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/New-AzCostManagementExport.md
ms.openlocfilehash: b95e66ce652b0ef3b9408d19dcd7a2e1f1ac7574
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142113785"
---
# New-AzCostManagementExport

## SYNOPSIS
Operasi untuk membuat atau memperbarui ekspor.
Operasi pembaruan memerlukan eTag terbaru untuk diatur dalam permintaan.
Anda dapat memperoleh eTag terbaru dengan melakukan operasi get.
Operasi Buat tidak memerlukan eTag.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.costmanagement/new-azcostmanagementexport) untuk informasi terbaru.

## SYNTAX

```
New-AzCostManagementExport -Name <String> -Scope <String> [-ConfigurationColumn <String[]>]
 [-DataSetGranularity <GranularityType>] [-DefinitionTimeframe <TimeframeType>] [-DefinitionType <ExportType>]
 [-DestinationContainer <String>] [-DestinationResourceId <String>] [-DestinationRootFolderPath <String>]
 [-Format <FormatType>] [-RecurrencePeriodFrom <DateTime>] [-RecurrencePeriodTo <DateTime>]
 [-ScheduleRecurrence <RecurrenceType>] [-ScheduleStatus <StatusType>] [-TimePeriodFrom <DateTime>]
 [-TimePeriodTo <DateTime>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk membuat atau memperbarui ekspor.
Operasi pembaruan memerlukan eTag terbaru untuk diatur dalam permintaan.
Anda dapat memperoleh eTag terbaru dengan melakukan operasi get.
Operasi Buat tidak memerlukan eTag.

## EXAMPLES

### Contoh 1: Create an AzCostManagementExport
```powershell
New-AzCostManagementExport -Scope "subscriptions/***********" -Name "CostManagementExportTest" -ScheduleStatus "Active" -ScheduleRecurrence "Daily" -RecurrencePeriodFrom "2020-10-31T20:00:00Z" -RecurrencePeriodTo "2020-11-30T00:00:00Z" -Format "Csv" -DestinationResourceId "/subscriptions/*************/resourceGroups/ResourceGroupTest/providers/Microsoft.Storage/storageAccounts/storageAccountTest" `  -DestinationContainer "exports" -DestinationRootFolderPath "ad-hoc" -DefinitionType "Usage" -DefinitionTimeframe "MonthToDate" -DatasetGranularity "Daily"
```

```output
ETag              Name                                      Type
----              ----                                      ----
"********" TestExportDatasetAggregationInfosagdhaghj Microsoft.CostManagement/exports
```

Membuat AzCostManagementExport

## PARAMETERS

### -ConfigurationColumn
Array nama kolom yang akan disertakan dalam ekspor.
Jika tidak disediakan, ekspor akan menyertakan semua kolom yang tersedia.
Kolom yang tersedia dapat bervariasi menurut saluran pelanggan (lihat contoh).

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

### -DataSetGranularity
Granularitas baris dalam ekspor.
Saat ini hanya 'Harian' yang didukung.

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

### -DefinitionTimeframe
Jangka waktu untuk menarik data untuk ekspor.
Jika kustom, maka periode waktu tertentu harus disediakan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.TimeframeType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionType
Tipe ekspor.
Perhatikan bahwa 'Penggunaan' setara dengan 'ActualCost' dan berlaku untuk ekspor yang belum menyediakan data untuk biaya atau amortisasi untuk reservasi layanan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.ExportType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationContainer
Nama wadah tempat ekspor akan diunggah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationResourceId
Id sumber daya akun penyimpanan tempat ekspor akan dikirimkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationRootFolderPath
Nama direktori tempat ekspor akan diunggah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Format
Format ekspor yang dikirimkan.
Saat ini hanya 'Csv' yang didukung.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.FormatType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Ekspor Nama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExportName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrencePeriodFrom
Tanggal mulai pengulangan.

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

### -RecurrencePeriodTo
Tanggal akhir pengulangan.

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

### -ScheduleRecurrence
Pengulangan jadwal.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.RecurrenceType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleStatus
Status jadwal ekspor.
Jika 'Tidak Aktif', jadwal ekspor akan dijeda.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Support.StatusType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Parameter ini menentukan lingkup costmanagement dari perspektif berbeda 'Subscription','ResourceGroup' dan 'Provide Service'.

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

### -TimePeriodFrom
Tanggal mulai untuk mengekspor data.

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
Tanggal akhir untuk mengekspor data.

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

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IExport

## CATATAN

ALIAS

## RELATED LINKS

