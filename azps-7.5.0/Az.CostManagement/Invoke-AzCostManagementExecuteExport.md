---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.costmanagement/invoke-azcostmanagementexecuteexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Invoke-AzCostManagementExecuteExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Invoke-AzCostManagementExecuteExport.md
ms.openlocfilehash: 5ad17fdbf3b297d41ac11c77daee1d646e7b5679
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146620498"
---
# Invoke-AzCostManagementExecuteExport

## SYNOPSIS
Operasi untuk menjalankan ekspor.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.costmanagement/invoke-azcostmanagementexecuteexport) untuk informasi terbaru.

## SYNTAX

### Jalankan (Default)
```
Invoke-AzCostManagementExecuteExport -ExportName <String> -Scope <String> [-DefaultProfile <PSObject>]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ExecuteViaIdentity
```
Invoke-AzCostManagementExecuteExport -InputObject <ICostManagementIdentity> [-DefaultProfile <PSObject>]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk menjalankan ekspor.

## EXAMPLES

### Contoh 1: Panggil Ekspor menurut ExportName dan Cakupan
```powershell
Invoke-AzCostManagementExecuteExport -ExportName 'TestExport' -Scope 'subscriptions/**********'
```

Panggil Ekspor menurut ExportName dan Cakupan

### Contoh 2: Panggil Ekspor oleh InputObject
```powershell
$getExport = Get-AzCostManagementExport -Name 'TestExport' -Scope 'subscriptions/**********'
Invoke-AzCostManagementExecuteExport -InputObject $getExport
```

Panggil Ekspor oleh InputObject

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

### -ExportName
Nama Ekspor.

```yaml
Type: System.String
Parameter Sets: Execute
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.ICostManagementIdentity
Parameter Sets: ExecuteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Cakupan
Parameter ini mendefinisikan cakupan costmanagement dari perspektif yang berbeda 'Langganan','ResourceGroup' dan 'Sediakan Layanan'.

```yaml
Type: System.String
Parameter Sets: Execute
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
  - `[ExternalCloudProviderId <String>]`: Ini bisa menjadi '{externalSubscriptionId}' untuk akun tertaut atau '{externalBillingAccountId}' untuk akun konsolidasi yang digunakan dengan operasi dimensi/kueri.
  - `[ExternalCloudProviderType <ExternalCloudProviderType?>]`: Jenis penyedia cloud eksternal yang terkait dengan operasi dimensi/kueri. Ini termasuk 'externalSubscriptions' untuk akun tertaut dan 'externalBillingAccounts' untuk akun konsolidasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Scope <String>]`: Cakupan yang terkait dengan operasi tampilan. Ini termasuk 'subscriptions/{subscriptionId}' untuk cakupan langganan, 'subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}' untuk cakupan resourceGroup, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}' for Billing Account scope, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/departments/{departmentId}' for Department scope, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/enrollmentAccounts/{ enrollmentAccountId}' untuk cakupan EnrollmentAccount, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/billingProfiles/{billingProfileId}' untuk cakupan BillingProfile, 'providers/Microsoft.Billing/billingAccounts/{billingAccountId}/invoiceSections/{invoiceSectionId}' untuk cakupan InvoiceSection, 'providers/Microsoft.Management/managementGroups/{managementGroupId}' untuk cakupan Grup Manajemen, 'providers/Microsoft.CostManagement/externalBillingAccounts/{ externalBillingAccountName}' untuk cakupan Akun Penagihan Eksternal dan 'providers/Microsoft.CostManagement/externalSubscriptions/{externalSubscriptionName}' untuk cakupan Langganan Eksternal.
  - `[ViewName <String>]`: Nama tampilan

## RELATED LINKS

