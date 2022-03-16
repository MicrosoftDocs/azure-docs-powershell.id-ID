---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.costmanagement/remove-azcostmanagementexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Remove-AzCostManagementExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Remove-AzCostManagementExport.md
ms.openlocfilehash: 55bb1daf367d0d2dc0112811ee47b1bc3e13502d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140059331"
---
# Remove-AzCostManagementExport

## SYNOPSIS
Operasi untuk menghapus ekspor.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.costmanagement/remove-azcostmanagementexport) untuk informasi terkini.

## SYNTAX

### Hapus (Default)
```
Remove-AzCostManagementExport -Name <String> -Scope <String> [-DefaultProfile <PSObject>] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzCostManagementExport -InputObject <ICostManagementIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk menghapus ekspor.

## EXAMPLES

### Contoh 1: Delete the AzCostManagementExport by Scope and Name
```powershell
PS C:\> Remove-AzCostManagementExport -Scope 'subscriptions/********' -name 'TestExportDatasetAggregationInfoYouri'


```

Hapus AzCostManagementExport Menurut Lingkup dan ExportName

### Contoh 2: Delete the AzCostManagementExport by Export Object
```powershell
PS C:\> $getExport = Get-AzCostManagementExport -Scope 'subscriptions/*********' -name 'TestExportDatasetAggregationYouori'
Remove-AzCostManagementExport -InputObject $getExport


```

Menghapus AzCostManagementExport By InputObject

## PARAMETERS

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.ICostManagementIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Ekspor Nama.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: ExportName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Parameter ini menentukan lingkup pengelolaan biaya dari perspektif berbeda 'Langganan','ResourceGroup' dan 'Sediakan Layanan'.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.ICostManagementIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICostManagementIdentity>: Parameter Identitas
  - `[AlertId <String>]`: ID Pemberitahuan
  - `[ExportName <String>]`: Ekspor Nama.
  - `[ExternalCloudProviderId <String>]`: Dapat juga merupakan '{externalSubscriptionId}' untuk akun tertaut atau '{externalBillingAccountId}' untuk akun konsolidasi yang digunakan dengan operasi dimensi/kueri.
  - `[ExternalCloudProviderType <ExternalCloudProviderType?>]`: Tipe penyedia awan eksternal terkait dengan operasi dimensi/kueri. Hal ini mencakup 'externalSubscriptions' untuk akun tertaut dan 'externalBillingAccounts' untuk akun konsolidasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Scope <String>]`: Lingkup terkait dengan operasi tampilan. Ini mencakup 'subscriptions/{subscriptionId}' untuk lingkup langganan, 'subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}' untuk lingkup resourceGroup, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}' untuk lingkup Akun Tagihan, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/departments/{departmentId}' untuk lingkup Departemen, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/enrollmentAccounts/{ enrollmentAccountId}' untuk Pendaftaran Cakupan akun, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/billingProfiles/{billingProfileId}' untuk lingkup BillingProfile, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/invoiceSections/{invoiceSectionId}' untuk lingkup InvoiceSection, 'providers/Microsoft.Management/managementGroups/{managementGroupId}' untuk lingkup Grup Manajemen, 'providers/Microsoft.CostManagement/externalBillingAccounts/{ externalBillingAccountName}' untuk lingkup Akun Tagihan Eksternal dan 'providers/Microsoft.CostManagement/externalSubscriptions/{externalSubscriptionName}' untuk lingkup Langganan Eksternal.
  - `[ViewName <String>]`: Nama tampilan

## RELATED LINKS

