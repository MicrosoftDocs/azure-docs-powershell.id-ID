---
title: Perubahan yang melanggar untuk modul AzureRM PowerShell 6.0.0
description: Panduan migrasi ini berisi daftar perubahan yang melanggar yang dibuat pada modul AzureRM PowerShell dalam rilis versi 6.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 19763f84d33fead74e79e6b448f7b3dcbe183c17
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429356"
---
# <a name="breaking-changes-for-the-azurerm-powershell-module-600"></a>Perubahan yang melanggar untuk modul AzureRM PowerShell 6.0.0

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dokumen ini berfungsi sebagai pemberitahuan perubahan dan panduan migrasi bagi konsumen cmdlet Microsoft Azure PowerShell. Setiap bagian menggambarkan dorongan untuk perubahan yang melanggar dan jalur migrasi resistensi paling sedikit. Untuk konteks mendalam, silakan lihat permintaan pull yang terkait dengan setiap perubahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Perubahan umum yang dapat menyebabkan gangguan](#general-breaking-changes)
  - [Versi PowerShell minimum yang diperlukan terbentur ke 5.0](#minimum-powershell-version-required-bumped-to-50)
  - [Konteks disimpan secara otomatis yang diaktifkan secara default](#context-autosave-enabled-by-default)
  - [Penghapusan Tag alias](#removal-of-tags-alias)
- [Perubahan yang melanggar ke cmdlet AzureRM.Compute](#breaking-changes-to-azurermcompute-cmdlets)
- [Perubahan yang melanggar ke cmdlet AzureRM.DataLakeStore](#breaking-changes-to-azurermdatalakestore-cmdlets)
- [Perubahan yang melanggar ke cmdlet AzureRM.Dns](#breaking-changes-to-azurermdns-cmdlets)
- [Perubahan yang melanggar ke AzureRM. cmdlet Insights](#breaking-changes-to-azurerminsights-cmdlets)
- [Perubahan yang melanggar ke cmdlet AzureRM.KeyVault](#breaking-changes-to-azurermkeyvault-cmdlets)
- [Perubahan yang melanggar ke cmdlet AzureRM.Network](#breaking-changes-to-azurermnetwork-cmdlets)
- [Perubahan yang melanggar ke cmdlet AzureRM.RedisCache](#breaking-changes-to-azurermrediscache-cmdlets)
- [Perubahan yang melanggar ke cmdlet AzureRM.Resources](#breaking-changes-to-azurermresources-cmdlets)
- [Perubahan yang melanggar ke AzureRM. cmdlet Storage](#breaking-changes-to-azurermstorage-cmdlets)
- [Modul yang dihapus](#removed-modules)
  - [`AzureRM.ServerManagement`](#azurermservermanagement)
  - [`AzureRM.SiteRecovery`](#azurermsiterecovery)

## <a name="general-breaking-changes"></a>Perubahan umum yang dapat menyebabkan gangguan

### <a name="minimum-powershell-version-required-bumped-to-50"></a>Versi PowerShell minimum yang diperlukan terbentur ke 5.0

Sebelumnya, Azure PowerShell membutuhkan _setidaknya_ versi 3.0 dari PowerShell untuk menjalankan cmdlet apa pun. Ke depan, persyaratan ini akan dinaikkan ke versi 5.0 dari PowerShell. Untuk informasi tentang peningkatan ke PowerShell 5.0, lihat [tabel ini](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).

### <a name="context-autosave-enabled-by-default"></a>Simpan otomatis konteks diaktifkan secara default

Context simpan-otomatis adalah penyimpanan informasi masuk Azure yang dapat digunakan antara sesi PowerShell baru dan berbeda. Untuk informasi selengkapnya tentang simpan-otomatis konteks, lihat [dokumen ini](/powershell/azure/context-persistence).

Sebelumnya secara default, simpan-otomatis konteks dinonaktifkan, yang berarti informasi autentikasi Azure pengguna tidak disimpan di antara sesi sampai menjalankan cmdlet `Enable-AzureRmContextAutosave` untuk mengaktifkan persistensi konteks. Ke depan, simpan-otomatis konteks akan diaktifkan secara default, yang berarti bahwa pengguna _tanpa pengaturan penyimpanan otomatis konteks yang disimpan_ akan menyimpan konteksnya saat berikutnya mereka masuk. Pengguna dapat memilih keluar dari fungsi ini dengan menggunakan cmdlet `Disable-AzureRmContextAutosave`.

> [!NOTE]
> Pengguna yang sebelumnya menonaktifkan simpan-otomatis konteks atau pengguna dengan simpan-otomatis konteks diaktifkan dan konteks yang ada tidak akan terpengaruh oleh perubahan ini.

### <a name="removal-of-tags-alias"></a>Penghapusan Tag alias

Alias `Tags` untuk parameter `Tag` telah dihapus di berbagai cmdlet. Di bawah ini adalah daftar modul (dan cmdlet yang sesuai) yang terpengaruh oleh ini:

#### `AzureRM.ApiManagement`

- `New-AzureRmApiManagement`
- `New-AzureRmApiManagementProperty`
- `Set-AzureRmApiManagementProperty`

#### `AzureRM.Automation`
- `Set-AzureRmAutomationRunbook`

#### `AzureRM.Cdn`
- `New-AzureRmCdnEndpoint`
- `New-AzureRmCdnProfile`

#### `AzureRM.Compute`
- `New-AzureRmVM`
- `Update-AzureRmVM`

#### `AzureRM.DataFactories`
- `New-AzureRmDataFactories`

#### `AzureRM.DataLakeAnalytics`
- `New-AzureRmDataLakeAnalyticsAccount`

#### `AzureRM.DataLakeStore`
- `New-AzureRmDataLakeStoreAccount`
- `Set-AzureRmDataLakeStoreAccount`

#### `AzureRM.MachineLearning`
- `Update-AzureRmMlCommitmentPlan`

#### `AzureRM.Media`
- `Set-AzureRmMediaService`

#### `AzureRM.OperationalInsights`
- `New-AzureRmOperationalInsightsSavedSearch`
- `New-AzureRmOperationalInsightsWorkspace`
- `Set-AzureRmOperationalInsightsSavedSearch`
- `Set-AzureRmOperationalInsightsWorkspace`

## <a name="breaking-changes-to-azurermcompute-cmdlets"></a>Perubahan yang melanggar ke cmdlet AzureRM.Compute

**Lain-Lain**

- Properti nama sku bersarang dalam jenis `PSDisk` dan `PSSnapshot` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

```powershell
$disk = Get-AzureRmDisk -ResourceGroupName 'MyResourceGroup' -DiskName 'MyDiskName'
$disk.Sku.Name       # This will now return Standard_LRS or Premium_LRS

$snapshot = Get-AzureRmSnapshot -ResourceGroupName 'MyResourceGroup' -SnapshotName 'MySnapshotName'
$snapshot.Sku.Name   # This will now return Standard_LRS or Premium_LRS
```

- Properti jenis akun penyimpanan bersarang dalam jenis `PSVirtualMachine`, `PSVirtualMachineScaleSet` dan `PSImage` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

```powershell
$vm = Get-AzureRmVM -ResourceGroupName "MyResourceGroup" -Name "MyVM"
$vm.StorageProfile.DataDisks[0].ManagedDisk.StorageAccountType   # This will now return Standard_LRS or Premium_LRS
```

**Add-AzureRmImageDataDisk**

- Nilai yang diterima untuk parameter `StorageAccountType` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**Add-AzureRmVMDataDisk**

- Nilai yang diterima untuk parameter `StorageAccountType` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**Add-AzureRmVmssDataDisk**

- Nilai yang diterima untuk parameter `StorageAccountType` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**New-AzureRmAvailabilitySet**
- Parameter `Managed` dihapus untuk mendukung `Sku`

```powershell
# Old
New-AzureRmAvailabilitySet -ResourceGroupName "MyRG" -Name "MyAvailabilitySet" -Location "West US" -Managed

# New
New-AzureRmAvailabilitySet -ResourceGroupName "MyRG" -Name "MyAvailabilitySet" -Location "West US" -Sku "Aligned"
```

**New-AzureRmDiskConfig**
- Nilai yang diterima untuk parameter `SkuName` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**New-AzureRmDiskUpdateConfig**
- Nilai yang diterima untuk parameter `SkuName` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**New-AzureRmSnapshotConfig**
- Nilai yang diterima untuk parameter `SkuName` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**New-AzureRmSnapshotUpdateConfig**
- Nilai yang diterima untuk parameter `SkuName` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**Set-AzureRmImageOsDisk**
- Nilai yang diterima untuk parameter `StorageAccountType` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**Set-AzureRmVMAEMExtension**
- Parameter `DisableWAD` telah dihapus
    -  Windows Azure Diagnostics dinonaktifkan secara default

**Set-AzureRmVMDataDisk**
- Nilai yang diterima untuk parameter `StorageAccountType` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**Set-AzureRmVMOSDisk**
- Nilai yang diterima untuk parameter `StorageAccountType` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**Set-AzureRmVmssStorageProfile**
- Nilai yang diterima untuk parameter `ManagedDisk` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

**Update-AzureRmVmss**
- Nilai yang diterima untuk parameter `ManagedDiskStorageAccountType` berubah dari `StandardLRS` dan `PremiumLRS` ke `Standard_LRS` dan `Premium_LRS`, masing-masing

## <a name="breaking-changes-to-azurermdatalakestore-cmdlets"></a>Perubahan yang melanggar ke cmdlet AzureRM.DataLakeStore

**Export-AzureRmDataLakeStoreItem**
- Parameter `PerFileThreadCount` dan `ConcurrentFileCount` dihapus. Gunakan parameter `Concurrency` yang bergerak maju

```powershell
# Old
Export-AzureRmDataLakeStoreItem -Account contoso -Path /test -Destination C:\test -Recurse -Resume -PerFileThreadCount 2 -ConcurrentFileCount 80

# New
Export-AzureRmDataLakeStoreItem -Account contoso -Path /test -Destination C:\test -Recurse -Resume -Concurrency 160
```

**Import-AzureRmDataLakeStoreItem**
- Parameter `PerFileThreadCount` dan `ConcurrentFileCount` dihapus. Gunakan parameter `Concurrency` yang bergerak maju

```powershell
# Old
Import-AzureRmDataLakeStoreItem -Account contoso -Path C:\test -Destination /test -Recurse -Resume -ForceBinary -PerFileThreadCount 2 -ConcurrentFileCount 80

# New
Import-AzureRmDataLakeStoreItem -Account contoso -Path C:\test -Destination /test -Recurse -Resume -ForceBinary -Concurrency 160
```

**Remove-AzureRmDataLakeStoreItem**
- Parameter `Clean` telah dihapus

```powershell
# Old
Remove-AzureRmDataLakeStoreItem -Account "ContosoADL" -path /myFolder -Recurse -Clean

# New
Remove-AzureRmDataLakeStoreItem -Account "ContosoADL" -path /myFolder -Recurse
```

## <a name="breaking-changes-to-azurermdns-cmdlets"></a>Melanggar perubahan pada cmdlet AzureRM.Dns

**New-AzureRmDnsRecordSet**
- Parameter `Force` telah dihapus

**Remove-AzureRmDnsRecordSet**
- Parameter `Force` telah dihapus

**Remove-AzureRmDnsZone**
- Parameter `Force` telah dihapus

## <a name="breaking-changes-to-azurerminsights-cmdlets"></a>Perubahan yang melanggar ke AzureRM. cmdlet Insights

**Add-AzureRmAutoscaleSetting**
- Parameter alias `AutoscaleProfiles` dan `Notifications` dihapus

**Add-AzureRmLogProfile**
- Parameter alias `Categories` dan `Locations` dihapus

**Add-AzureRmMetricAlertRule**
- Alias `Actions` parameter telah dihapus

**Add-AzureRmWebtestAlertRule**
- Alias `Actions` parameter telah dihapus

**Get-AzureRmLog**
- Parameter alias `MaxRecords` dan `MaxEvents` dihapus

**Get-AzureRmMetricDefinition**
- Parameter alias `MetricNames` telah dihapus

**New-AzureRmAlertRuleEmail**
- Parameter alias `CustomEmails` dan `SendToServiceOwners` dihapus

**New-AzureRmAlertRuleWebhook**
- Parameter alias `Properties` telah dihapus

**New-AzureRmAutoscaleNotification**
- Parameter alias `CustomEmails`, `SendEmailToSubscriptionCoAdministrators`, dan `Webhooks` dihapus

**New-AzureRmAutoscaleProfile**
- Parameter alias `Rules`, `ScheduleDays`, `ScheduleHours`, dan `ScheduleMinutes` telah dihapus

**New-AzureRmAutoscaleWebhook**
- Parameter alias `Properties` telah dihapus

## <a name="breaking-changes-to-azurermkeyvault-cmdlets"></a>Perubahan yang melanggar ke cmdlet AzureRM.KeyVault

**Add-AzureKeyVaultCertificate**
- Parameter `CertificatePolicy` telah menjadi wajib.

**Set-AzureKeyVaultManagedStorageSasDefinition**
- Cmdlet tidak lagi menerima parameter individual yang menyusun token akses; sebagai gantinya, cmdlet menggantikan parameter token eksplisit, seperti `Service` atau `Permissions`, dengan parameter `TemplateUri` umum, sesuai dengan token akses sampel yang ditentukan di tempat lain (mungkin menggunakan cmdlet PowerShell Storage, atau disusun secara manual sesuai dengan dokumentasi Storage.) Cmdlet mempertahankan parameter `ValidityPeriod`.

Untuk informasi selengkapnya tentang menyusun token akses bersama untuk Azure Storage, silakan lihat halaman dokumentasi, masing-masing:

- [Membangun SAS Layanan](/rest/api/storageservices/Constructing-a-Service-SAS)
- [Membangun SAS Akun](/rest/api/storageservices/constructing-an-account-sas)

```powershell
# Old
$sas = Set-AzureKeyVaultManagedStorageSasDefinition -VaultName myVault -Name myKey -Service Blob -Permissions 'rcw' -ValidityPeriod 180d

# New
$sctx=New-AzureStorageContext -StorageAccountName $sa.StorageAccountName -Protocol Https -StorageAccountKey Key1
$start=[System.DateTime]::Now.AddDays(-1)
$end=[System.DateTime]::Now.AddMonths(1)
$at=New-AzureStorageAccountSasToken -Service blob -ResourceType Service,Container,Object -Permission "racwdlup" -Protocol HttpsOnly -StartTime $start -ExpiryTime $end -Context $sctx
$sas=Set-AzureKeyVaultManagedStorageSasDefinition -AccountName $sa.StorageAccountName -VaultName $kv.VaultName -Name accountsas -TemplateUri $at -SasType 'account' -ValidityPeriod ([System.Timespan]::FromDays(30))
```

**Set-AzureKeyVaultCertificateIssuer**
- Parameter `IssuerProvider` telah menjadi wajib.

**Undo-AzureKeyVaultCertificateRemoval**
- Output dari cmdlet ini telah berubah dari `CertificateBundle` menjadi `PSKeyVaultCertificate`.

**Undo-AzureRmKeyVaultRemoval**
- `ResourceGroupName` telah dihapus dari set parameter `InputObject`, dan malah diperoleh dari properti `ResourceId` parameter `InputObject`.

**Set-AzureRmKeyVaultAccessPolicy**
- Izin `all` telah dihapus dari `PermissionsToKeys`, `PermissionsToSecrets`, dan `PermissionsToCertificates`.

**Umum**
- Properti `ValueFromPipelineByPropertyName` telah dihapus dari semua cmdlet saat alur `InputObject` diaktifkan. Cmdlet yang terpengaruh adalah:
    - `Add-AzureKeyVaultCertificate`
    - `Add-AzureKeyVaultCertificateContact`
    - `Add-AzureKeyVaultKey`
    - `Backup-AzureKeyVaultKey`
    - `Backup-AzureKeyVaultSecret`
    - `Get-AzureKeyVaultCertficate`
    - `Get-AzureKeyVaultCertificateContact`
    - `Get-AzureKeyVaultCertificateIssuer`
    - `Get-AzureKeyVaultCertificateOperation`
    - `Get-AzureKeyVaultCertificatePolicy`
    - `Get-AzureKeyVaultKey`
    - `Get-AzureKeyVaultManagedStorageAccount`
    - `Get-AzureKeyVaultManagedStorageSasDefinition`
    - `Get-AzureKeyVaultSecret`
    - `Remove-AzureRmKeyVault`
    - `Remove-AzureRmKeyVaultAccessPolicy`
    - `Remove-AzureKeyVaultCertificate`
    - `Remove-AzureKeyVaultCertificateContact`
    - `Remove-AzureKeyVaultCertificateIssuer`
    - `Remove-AzureKeyVaultCertificateOperation`
    - `Remove-AzureKeyVaultKey`
    - `Remove-AzureKeyVaultManagedStorageAccount`
    - `Remove-AzureKeyVaultManagedStorageSasDefinition`
    - `Remove-AzureKeyVaultSecret`
    - `Restore-AzureKeyVaultKey`
    - `Restore-AzureKeyVaultSecret`
    - `Set-AzureRmKeyVaultAccessPolicy`
    - `Set-AzureKeyVaultCertificateAttribute`
    - `Set-AzureKeyVaultCertificateIssuer`
    - `Set-AzureKeyVaultCertificatePolicy`
    - `Set-AzureKeyVaultKeyAttribute`
    - `Set-AzureKeyVaultManagedStorageSasDefinition`
    - `Set-AzureKeyVaultSecret`
    - `Set-AzureKeyVaultSecretAttribute`
    - `Stop-AzureKeyVaultCertificateOperation`
    - `Undo-AzureKeyVaultCertificateRemoval`
    - `Undo-AzureKeyVaultKeyRemoval`
    - `Undo-AzureRmKeyVaultRemoval`
    - `Undo-AzureKeyVaultSecretRemoval`
    - `Update-AzureKeyVaultManagedStorageAccount`
    - `Update-AzureKeyVaultManagedStorageAccountKey`

- `ConfirmImpact` level telah dihapus dari semua cmdlet.  Cmdlet yang terpengaruh adalah:
    - `Remove-AzureRmKeyVault`
    - `Remove-AzureKeyVaultCertificate`
    - `Remove-AzureKeyVaultCertificateIssuer`
    - `Remove-AzureKeyVaultCertificateOperation`
    - `Remove-AzureKeyVaultKey`
    - `Remove-AzureKeyVaultManagedStorageAccount`
    - `Remove-AzureKeyVaultManagedStorageSasDefinition`
    - `Remove-AzureKeyVaultSecret`
    - `Stop-AzureKeyVaultCertificateOperation`
    - `Update-AzureKeyVaultManagedStorageAccountKey`

- `IKeyVaultDataServiceClient` diperbarui sehingga semua operasi Sertifikat mengembalikan PSTypes, bukan jenis SDK. Hal ini termasuk:
    - `SetCertificateContacts`
    - `GetCertificateContacts`
    - `GetCertificate`
    - `GetDeletedCertificate`
    - `MergeCertificate`
    - `ImportCertificate`
    - `DeleteCertificate`
    - `RecoverCertificate`
    - `EnrollCertificate`
    - `UpdateCertificate`
    - `GetCertificateOperation`
    - `DeleteCertificateOperation`
    - `CancelCertificateOperation`
    - `GetCertificatePolicy`
    - `UpdateCertificatePolicy`
    - `GetCertificateIssuer`
    - `SetCertificateIssuer`
    - `DeleteCertificateIssuer`

## <a name="breaking-changes-to-azurermnetwork-cmdlets"></a>Perubahan yang melanggar ke cmdlet AzureRM.Network


**Add-AzureRmApplicationGatewayBackendHttpSettings**
- Parameter `ProbeEnabled` telah dihapus

**Add-AzureRmVirtualNetworkPeering**
- Parameter alias `AlloowGatewayTransit` telah dihapus

**New-AzureRmApplicationGatewayBackendHttpSettings**
- Parameter `ProbeEnabled` telah dihapus

**Set-AzureRmApplicationGatewayBackendHttpSettings**
- Parameter `ProbeEnabled` telah dihapus

## <a name="breaking-changes-to-azurermrediscache-cmdlets"></a>Perubahan yang melanggar ke cmdlet AzureRM.RedisCache

**New-AzureRmRedisCache**
- Parameter `Subnet` dan `VirtualNetwork` dihapus untuk mendukung `SubnetId`
- Parameter `RedisVersion` telah dihapus
- Parameter `MaxMemoryPolicy` dihapus untuk mendukung `RedisConfiguration`

```powershell
# Old
New-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -Location "North Central US" -MaxMemoryPolicy "allkeys-lru"

# New
New-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -Location "North Central US" -RedisConfiguration @{"maxmemory-policy" = "allkeys-lru"}
```

**Set-AzureRmRedisCache**
- Parameter `MaxMemoryPolicy` dihapus untuk mendukung `RedisConfiguration`

```powershell
# Old
Set-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -MaxMemoryPolicy "allkeys-lru"

# New
Set-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -RedisConfiguration @{"maxmemory-policy" = "allkeys-lru"}
```

## <a name="breaking-changes-to-azurermresources-cmdlets"></a>Perubahan yang melanggar ke cmdlet AzureRM.Resources

**Find-AzureRmResource**
- Cmdlet ini telah dihapus dan fungsinya dipindahkan ke `Get-AzureRmResource`

```powershell
# Old
Find-AzureRmResource -ResourceType "Microsoft.Web/sites" -ResourceGroupNameContains "ResourceGroup"
Find-AzureRmResource -ResourceType "Microsoft.Web/sites" -ResourceNameContains "test"

# New
Get-AzureRmResource -ResourceType "Microsoft.Web/sites" -ResourceGroupName "*ResourceGroup*"
Get-AzureRmResource -ResourceType "Microsoft.Web/sites" -Name "*test*"
```

**Find-AzureRmResourceGroup**
- Cmdlet ini telah dihapus dan fungsinya dipindahkan ke `Get-AzureRmResourceGroup`

```powershell
# Old
Find-AzureRmResourceGroup
Find-AzureRmResourceGroup -Tag @{ "testtag" = $null }
Find-AzureRmResourceGroup -Tag @{ "testtag" = "testval" }

# New
Get-AzureRmResourceGroup
Get-AzureRmResourceGroup -Tag @{ "testtag" = $null }
Get-AzureRmResourceGroup -Tag @{ "testtag" = "testval" }
```

**Get-AzureRmRoleDefinition**
- Parameter `AtScopeAndBelow` telah dihapus.

```powershell

# Old
Get-AzureRmRoleDefinition [other required parameters] -AtScopeAndBelow

# New
Get-AzureRmRoleDefinition [other required parameters]
```

## <a name="breaking-changes-to-azurermstorage-cmdlets"></a>Perubahan yang melanggar ke AzureRM. cmdlet Storage

**New-AzureRmStorageAccount**
- Parameter `EnableEncryptionService` telah dihapus

**Set-AzureRmStorageAccount**
- Parameter `EnableEncryptionService` dan `DisableEncryptionService` dihapus

## <a name="removed-modules"></a>Modul yang dihapus

### `AzureRM.ServerManagement`

Layanan Alat Manajemen Server [dihentikan tahun lalu](https://blogs.technet.microsoft.com/servermanagement/2017/05/17/smt-preview-service-is-being-retired-on-june-30-2017/), dan sebagai hasilnya, modul yang sesuai untuk SMT, `AzureRM.ServerManagement`, telah dihapus dari `AzureRM` dan akan menghentikan pengiriman dilanjutkan.

### `AzureRM.SiteRecovery`

Modul `AzureRM.SiteRecovery` sedang digantikan oleh `AzureRM.RecoveryServices.SiteRecovery`, yang merupakan superset fungsional modul `AzureRM.SiteRecovery` dan mencakup satu set baru cmdlet setara. Daftar lengkap pemetaan dari cmdlet lama hingga baru dapat ditemukan di bawah ini:

| Cmdlet yang tidak digunakan lagi                                        | Cmdlet yang setara                                                | Alias                                  |
|----------------------------------------------------------|------------------------------------------------------------------|------------------------------------------|
| `Edit-AzureRmSiteRecoveryRecoveryPlan`                   | `Edit-AzureRmRecoveryServicesAsrRecoveryPlan`                    | `Edit-ASRRecoveryPlan`                   |
| `Get-AzureRmSiteRecoveryFabric`                          | `Get-AzureRmRecoveryServicesAsrFabric`                           | `Get-ASRFabric`                          |
| `Get-AzureRmSiteRecoveryJob`                             | `Get-AzureRmRecoveryServicesAsrJob`                              | `Get-ASRJob`                             |
| `Get-AzureRmSiteRecoveryNetwork`                         | `Get-AzureRmRecoveryServicesAsrNetwork`                          | `Get-ASRNetwork`                         |
| `Get-AzureRmSiteRecoveryNetworkMapping`                  | `Get-AzureRmRecoveryServicesAsrNetworkMapping`                   | `Get-ASRNetworkMapping`                  |
| `Get-AzureRmSiteRecoveryPolicy`                          | `Get-AzureRmRecoveryServicesAsrPolicy`                           | `Get-ASRPolicy`                          |
| `Get-AzureRmSiteRecoveryProtectableItem`                 | `Get-AzureRmRecoveryServicesAsrProtectableItem`                  | `Get-ASRProtectableItem`                 |
| `Get-AzureRmSiteRecoveryProtectionContainer`             | `Get-AzureRmRecoveryServicesAsrProtectionContainer`              | `Get-ASRProtectionContainer`             |
| `Get-AzureRmSiteRecoveryProtectionContainerMapping`      | `Get-AzureRmRecoveryServicesAsrProtectionContainerMapping`       | `Get-ASRProtectionContainerMapping`      |
| `Get-AzureRmSiteRecoveryProtectionEntity`                | `Get-AzureRmRecoveryServicesAsrProtectableItem`                  | `Get-ASRProtectableItem`                 |
| `Get-AzureRmSiteRecoveryRecoveryPlan`                    | `Get-AzureRmRecoveryServicesAsrRecoveryPlan`                     | `Get-ASRRecoveryPlan`                    |
| `Get-AzureRmSiteRecoveryRecoveryPoint`                   | `Get-AzureRmRecoveryServicesAsrRecoveryPoint`                    | `Get-ASRRecoveryPoint`                   |
| `Get-AzureRmSiteRecoveryReplicationProtectedItem`        | `Get-AzureRmRecoveryServicesAsrReplicationProtectedItem`         | `Get-ASRReplicationProtectedItem`        |
| `Get-AzureRmSiteRecoveryServer`                          | `Get-AzureRmRecoveryServicesAsrServicesProvider`                 | `Get-ASRServicesProvider`                |
| `Get-AzureRmSiteRecoveryServicesProvider`                | `Get-AzureRmRecoveryServicesAsrServicesProvider`                 | `Get-ASRServicesProvider`                |
| `Get-AzureRmSiteRecoverySite`                            | `Get-AzureRmRecoveryServicesAsrFabric`                           | `Get-ASRFabric`                          |
| `Get-AzureRmSiteRecoveryStorageClassification`           | `Get-AzureRmRecoveryServicesAsrStorageClassification`            | `Get-ASRStorageClassification`           |
| `Get-AzureRmSiteRecoveryStorageClassificationMapping`    | `Get-AzureRmRecoveryServicesAsrStorageClassificationMapping`     | `Get-ASRStorageClassificationMapping`    |
| `Get-AzureRmSiteRecoveryVault`                           | `Get-AzureRmRecoveryServicesVault`                               |                                          |
| `Get-AzureRmSiteRecoveryVaultSettings`                   | `Get-AzureRmRecoveryServicesAsrVaultContext`                     |                                          |
| `Get-AzureRmSiteRecoveryVaultSettingsFile`               | `Get-AzureRmRecoveryServicesVaultSettingsFile`                   |                                          |
| `Get-AzureRmSiteRecoveryVM`                              | `Get-AzureRmRecoveryServicesAsrReplicationProtectedItem`         | `Get-ASRReplicationProtectedItem`        |
| `Import-AzureRmSiteRecoveryVaultSettingsFile`            | `Import-AzureRmRecoveryServicesAsrVaultSettingsFile`             |                                          |
| `New-AzureRmSiteRecoveryFabric`                          | `New-AzureRmRecoveryServicesAsrFabric`                           | `New-ASRFabric`                          |
| `New-AzureRmSiteRecoveryNetworkMapping`                  | `New-AzureRmRecoveryServicesAsrNetworkMapping`                   | `New-ASRNetworkMapping`                  |
| `New-AzureRmSiteRecoveryPolicy`                          | `New-AzureRmRecoveryServicesAsrPolicy`                           | `New-ASRPolicy`                          |
| `New-AzureRmSiteRecoveryProtectionContainerMapping`      | `New-AzureRmRecoveryServicesAsrProtectionContainerMapping`       | `New-ASRProtectionContainerMapping`      |
| `New-AzureRmSiteRecoveryRecoveryPlan`                    | `New-AzureRmRecoveryServicesAsrRecoveryPlan`                     | `New-ASRRecoveryPlan`                    |
| `New-AzureRmSiteRecoveryReplicationProtectedItem`        | `New-AzureRmRecoveryServicesAsrReplicationProtectedItem`         | `New-ASRReplicationProtectedItem`        |
| `New-AzureRmSiteRecoverySite`                            | `New-AzureRmRecoveryServicesAsrFabric`                           | `New-ASRFabric`                          |
| `New-AzureRmSiteRecoveryStorageClassificationMapping`    | `New-AzureRmRecoveryServicesAsrStorageClassificationMapping`     | `New-ASRStorageClassificationMapping`    |
| `New-AzureRmSiteRecoveryVault`                           | `New-AzureRmRecoveryServicesVault`                               |                                          |
| `Remove-AzureRmSiteRecoveryFabric`                       | `Remove-AzureRmRecoveryServicesAsrFabric`                        | `Remove-ASRFabric`                       |
| `Remove-AzureRmSiteRecoveryNetworkMapping`               | `Remove-AzureRmRecoveryServicesAsrNetworkMapping`                | `Remove-ASRNetworkMapping`               |
| `Remove-AzureRmSiteRecoveryPolicy`                       | `Remove-AzureRmRecoveryServicesAsrPolicy`                        | `Remove-ASRPolicy`                       |
| `Remove-AzureRmSiteRecoveryProtectionContainerMapping`   | `Remove-AzureRmRecoveryServicesAsrProtectionContainerMapping`    | `Remove-ASRProtectionContainerMapping`   |
| `Remove-AzureRmSiteRecoveryRecoveryPlan`                 | `Remove-AzureRmRecoveryServicesAsrRecoveryPlan`                  | `Remove-ASRRecoveryPlan`                 |
| `Remove-AzureRmSiteRecoveryReplicationProtectedItem`     | `Remove-AzureRmRecoveryServicesAsrReplicationProtectedItem`      | `Remove-ASRReplicationProtectedItem`     |
| `Remove-AzureRmSiteRecoveryServer`                       | `Remove-AzureRmRecoveryServicesAsrServicesProvider`              |                                          |
| `Remove-AzureRmSiteRecoveryServicesProvider`             | `Remove-AzureRmRecoveryServicesAsrServicesProvider`              | `Remove-ASRServicesProvider`             |
| `Remove-AzureRmSiteRecoverySite`                         | `Remove-AzureRmRecoveryServicesAsrFabric`                        | `Remove-ASRFabric`                       |
| `Remove-AzureRmSiteRecoveryStorageClassificationMapping` | `Remove-AzureRmRecoveryServicesAsrStorageClassificationMapping`  | `Remove-ASRStorageClassificationMapping` |
| `Remove-AzureRmSiteRecoveryVault`                        | `Remove-AzureRmRecoveryServicesVault`                            |                                          |
| `Restart-AzureRmSiteRecoveryJob`                         | `Restart-AzureRmRecoveryServicesAsrJob`                          | `Restart-ASRJob`                         |
| `Resume-AzureRmSiteRecoveryJob`                          | `Resume-AzureRmRecoveryServicesAsrJob`                           | `Resume-ASRJob`                          |
| `Set-AzureRmSiteRecoveryProtectionEntity`                | `New-AzureRmRecoveryServicesAsrReplicationProtectedItem`         | `New-ASRReplicationProtectedItem`        |
| `Set-AzureRmSiteRecoveryReplicationProtectedItem`        | `Set-AzureRmRecoveryServicesAsrReplicationProtectedItem`         | `Set-ASRReplicationProtectedItem`        |
| `Set-AzureRmSiteRecoveryVaultSettings`                   | `Set-AzureRmRecoveryServicesAsrVaultContext`                     | `Set-ASRVaultContext`                    |
| `Set-AzureRmSiteRecoveryVM`                              | `Set-AzureRmRecoveryServicesAsrReplicationProtectedItem`         | `Set-ASRReplicationProtectedItem`        |
| `Start-AzureRmSiteRecoveryApplyRecoveryPoint`            | `Start-AzureRmRecoveryServicesAsrApplyRecoveryPoint`             | `Start-ASRApplyRecoveryPoint`            |
| `Start-AzureRmSiteRecoveryCommitFailoverJob`             | `Start-AzureRmRecoveryServicesAsrCommitFailoverJob`              | `Start-ASRCommitFailoverJob`             |
| `Start-AzureRmSiteRecoveryPlannedFailoverJob`            | `Start-AzureRmRecoveryServicesAsrPlannedFailoverJob`             | `Start-ASRPlannedFailoverJob`            |
| `Start-AzureRmSiteRecoveryPolicyAssociationJob`          | `New-AzureRmRecoveryServicesAsrProtectionContainerMapping`       | `New-ASRProtectionContainerMapping`      |
| `Start-AzureRmSiteRecoveryPolicyDissociationJob`         | `Remove-AzureRmRecoveryServicesAsrProtectionContainerMapping`    | `Remove-ASRProtectionContainerMapping`   |
| `Start-AzureRmSiteRecoveryTestFailoverJob`               | `Start-AzureRmRecoveryServicesAsrTestFailoverJob`                | `Start-ASRTestFailoverJob`               |
| `Start-AzureRmSiteRecoveryUnplannedFailoverJob`          | `Start-AzureRmRecoveryServicesAsrUnplannedFailoverJob`           | `Start-ASRUnplannedFailoverJob`          |
| `Stop-AzureRmSiteRecoveryJob`                            | `Stop-AzureRmRecoveryServicesAsrJob`                             | `Stop-ASRJob`                            |
| `Update-AzureRmSiteRecoveryPolicy`                       | `Update-AzureRmRecoveryServicesAsrPolicy`                        | `Update-ASRPolicy`                       |
| `Update-AzureRmSiteRecoveryProtectionDirection`          | `Update-AzureRmRecoveryServicesAsrProtectionDirection`           | `Update-ASRProtectionDirection`          |
| `Update-AzureRmSiteRecoveryRecoveryPlan`                 | `Update-AzureRmRecoveryServicesAsrRecoveryPlan`                  | `Update-ASRRecoveryPlan`                 |
| `Update-AzureRmSiteRecoveryServer`                       | `Update-AzureRmRecoveryServicesAsrServicesProvider`              | `Update-ASRServicesProvider`             |
| `Update-AzureRmSiteRecoveryServicesProvider`             | `Update-AzureRmRecoveryServicesAsrvCenter`                       | `Update-ASRvCenter`                      |
