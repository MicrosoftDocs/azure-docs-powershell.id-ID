---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.costmanagement/remove-azcostmanagementexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Remove-AzCostManagementExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Remove-AzCostManagementExport.md
ms.openlocfilehash: 557a7468bd0c1e369e24d894a97ede7156b12536
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146607143"
---
# Remove-AzCostManagementExport

## SYNOPSIS
Operasi untuk menghapus ekspor.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.costmanagement/remove-azcostmanagementexport) untuk informasi terbaru.

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

### Contoh 1: Hapus AzCostManagementExport berdasarkan Cakupan dan Nama
```powershell
Remove-AzCostManagementExport -Scope 'subscriptions/********' -name 'TestExportDatasetAggregationInfoYouri'
```

Menghapus AzCostManagementExport By Scope dan ExportName

### Contoh 2: Hapus Objek AzCostManagementExport by Export
```powershell
$getExport = Get-AzCostManagementExport -Scope 'subscriptions/*********' -name 'TestExportDatasetAggregationYouori'
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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Name
Nama Ekspor.

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
Mengembalikan true ketika perintah berhasil

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

### -Cakupan
Parameter ini mendefinisikan cakupan costmanagement dari perspektif 'Langganan' yang berbeda,'ResourceGroup' dan 'Berikan Layanan'.

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

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.ICostManagementIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<ICostManagementIdentity>`: Parameter Identitas
  - `[AlertId <String>]`: ID Pemberitahuan
  - `[ExportName <String>]`: Nama Ekspor.
  - `[ExternalCloudProviderId <String>]`: Ini bisa berupa '{externalSubscriptionId}' untuk akun tertaut atau '{externalBillingAccountId}' untuk akun konsolidasi yang digunakan dengan operasi dimensi/kueri.
  - `[ExternalCloudProviderType <ExternalCloudProviderType?>]`: Jenis penyedia cloud eksternal yang terkait dengan operasi dimensi/kueri. Ini termasuk 'externalSubscriptions' untuk akun tertaut dan 'externalBillingAccounts' untuk akun konsolidasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Scope <String>]`: Cakupan yang terkait dengan operasi tampilan. Ini termasuk 'subscriptions/{subscriptionId}' untuk cakupan langganan, 'subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}' untuk cakupan resourceGroup, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}' for Billing Account scope, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/departments/{departmentId}' for Department scope, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/enrollmentAccounts/{ enrollmentAccountId}' untuk cakupan EnrollmentAccount, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/billingProfiles/{billingProfileId}' untuk cakupan BillingProfile, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/invoiceSections/{invoiceSectionId}' untuk cakupan InvoiceSection, 'providers/Microsoft.Management/managementGroups/{managementGroupId}' untuk cakupan Grup Manajemen, 'providers/Microsoft.CostManagement/externalBillingAccounts/{ externalBillingAccountName}' untuk cakupan Akun Penagihan Eksternal dan 'providers/Microsoft.CostManagement/externalSubscriptions/{externalSubscriptionName}' untuk cakupan Langganan Eksternal.
  - `[ViewName <String>]`: Nama tampilan

## RELATED LINKS

