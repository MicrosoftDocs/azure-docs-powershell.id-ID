---
external help file: ''
Module Name: Az.CostManagement
online version: https://docs.microsoft.com/powershell/module/az.costmanagement/get-azcostmanagementexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Get-AzCostManagementExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CostManagement/help/Get-AzCostManagementExport.md
ms.openlocfilehash: 034ed6a3e647dc82219348e64d4849571f42e150
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146635204"
---
# Get-AzCostManagementExport

## SYNOPSIS
Operasi untuk mendapatkan ekspor untuk cakupan yang ditentukan berdasarkan nama ekspor.

## SYNTAX

### Daftar (Default)
```
Get-AzCostManagementExport -Scope <String> [-Expand <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzCostManagementExport -Name <String> -Scope <String> [-Expand <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzCostManagementExport -InputObject <ICostManagementIdentity> [-Expand <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk mendapatkan ekspor untuk cakupan yang ditentukan berdasarkan nama ekspor.

## EXAMPLES

### Contoh 1: Dapatkan semua AzCostManagementExports menurut cakupan
```powershell
Get-AzCostManagementExport -Scope 'subscriptions/**********'
```

```output
ETag              Name                               Type
----              ----                               ----
"************" TestExport                         Microsoft.CostManagement/exports
"************" TestExport1                        Microsoft.CostManagement/exports
"************" TestExport2                        Microsoft.CostManagement/exports
```

Dapatkan semua AzCostManagementExports berdasarkan Cakupan

### Contoh 2: Dapatkan AzCostManagementExport berdasarkan Nama dan cakupan
```powershell
Get-AzCostManagementExport -Name 'TestExport' -Scope 'subscriptions/**********'
```

```output
ETag              Name       Type
----              ----       ----
"************" TestExport Microsoft.CostManagement/exports
```

Dapatkan AzCostManagementExport berdasarkan Nama dan cakupan

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

### -Perluas
Dapat digunakan untuk memperluas properti dalam ekspor.
Saat ini hanya 'runHistory' yang didukung dan akan mengembalikan informasi untuk 10 eksekusi terakhir ekspor.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.ICostManagementIdentity
Parameter Sets: GetViaIdentity
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
Parameter Sets: Get
Aliases: ExportName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Parameter ini mendefinisikan cakupan costmanagement dari perspektif 'Langganan' yang berbeda,'ResourceGroup' dan 'Berikan Layanan'.

```yaml
Type: System.String
Parameter Sets: Get, List
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

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.ICostManagementIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CostManagement.Models.Api20200601.IExport

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

