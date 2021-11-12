---
title: Memutus perubahan untuk modul PowerShell AzureRM 6.0.0
description: Panduan migrasi ini berisi daftar perubahan yang telah dibuat pada modul PowerShell AzureRM dalam rilis versi 6.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 19763f84d33fead74e79e6b448f7b3dcbe183c17
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429356"
---
# <a name="breaking-changes-for-the-azurerm-powershell-module-600"></a>Memutus perubahan untuk modul PowerShell AzureRM 6.0.0

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dokumen ini berfungsi sebagai pemberitahuan perubahan terbaru dan panduan migrasi bagi konsumen Microsoft Azure PowerShell cmdlets. Setiap bagian menjelaskan impetus untuk perubahan pecah dan jalur migrasi dari resistansi paling sedikit. Untuk konteks yang lebih mendalam, silakan lihat permintaan tarik terkait dengan setiap perubahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Perubahan umum yang tidak berubah](#general-breaking-changes)
  - [Versi PowerShell minimum diperlukan benturan 5,0](#minimum-powershell-version-required-bumped-to-50)
  - [Konteks disimpan otomatis diaktifkan secara default](#context-autosave-enabled-by-default)
  - [Penghapusan alias Tag](#removal-of-tags-alias)
- [Memutus perubahan pada cmdlet AzureRM.Compute](#breaking-changes-to-azurermcompute-cmdlets)
- [Memutus perubahan pada cmdlet AzureRM.DataLakeStore](#breaking-changes-to-azurermdatalakestore-cmdlets)
- [Memutus perubahan pada cmdlet AzureRM.Dns](#breaking-changes-to-azurermdns-cmdlets)
- [Memutus perubahan pada AzureRM. Insights cmdlets](#breaking-changes-to-azurerminsights-cmdlets)
- [Memutus perubahan pada cmdlet AzureRM.KeyVault](#breaking-changes-to-azurermkeyvault-cmdlets)
- [Memutus perubahan pada cmdlet AzureRM.Network](#breaking-changes-to-azurermnetwork-cmdlets)
- [Memutus perubahan pada cmdlet AzureRM.RedisCache](#breaking-changes-to-azurermrediscache-cmdlets)
- [Memutus perubahan pada cmdlet AzureRM.Resources](#breaking-changes-to-azurermresources-cmdlets)
- [Memutus perubahan pada AzureRM. cmdlet Storage baru](#breaking-changes-to-azurermstorage-cmdlets)
- [Modul yang dihapus](#removed-modules)
  - [`AzureRM.ServerManagement`](#azurermservermanagement)
  - [`AzureRM.SiteRecovery`](#azurermsiterecovery)

## <a name="general-breaking-changes"></a>Perubahan umum yang tidak berubah

### <a name="minimum-powershell-version-required-bumped-to-50"></a>Versi PowerShell minimum diperlukan benturan 5,0

Sebelumnya, Azure PowerShell _powerShell_ versi 3.0 diperlukan untuk menjalankan cmdlet apa pun. Ke depannya, persyaratan ini akan ditingkatkan ke PowerShell versi 5.0. Untuk informasi tentang pemutakhiran ke PowerShell 5.0, lihat [tabel ini.](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)

### <a name="context-autosave-enabled-by-default"></a>Simpan otomatis konteks diaktifkan secara default

Simpan otomatis konteks adalah penyimpanan informasi masuk Azure yang dapat digunakan antara sesi PowerShell baru dan yang berbeda. Untuk informasi selengkapnya tentang simpan otomatis konteks, silakan lihat [dokumen ini](/powershell/azure/context-persistence).

Sebelumnya, simpan otomatis konteks dinonaktifkan, yang berarti informasi autentikasi Azure pengguna tidak disimpan di antara sesi hingga mereka menjalankan cmdlet untuk mengaktifkan `Enable-AzureRmContextAutosave` persistensi konteks. Ke depannya, simpan otomatis konteks akan diaktifkan secara  default, yang berarti bahwa pengguna tanpa pengaturan simpan otomatis konteks yang disimpan akan menyimpan konteksnya pada kali berikutnya mereka masuk. Pengguna dapat menolak fungsionalitas ini menggunakan `Disable-AzureRmContextAutosave` cmdlet.

> [!NOTE]
> Pengguna yang sebelumnya menonaktifkan simpan otomatis konteks atau pengguna dengan simpan otomatis konteks yang diaktifkan dan konteks yang sudah ada tidak akan terpengaruh oleh perubahan ini.

### <a name="removal-of-tags-alias"></a>Penghapusan alias Tag

Alias `Tags` untuk `Tag` parameter ini telah dihapus di berbagai cmdlet. Di bawah ini adalah daftar modul (dan cmdlet terkait) yang terpengaruh oleh masalah ini:

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

## <a name="breaking-changes-to-azurermcompute-cmdlets"></a>Memutus perubahan pada cmdlet AzureRM.Compute

**Miscellaneous**

- Properti nama sku ditum menyediakan jenis `PSDisk` dan diubah dari dan `PSSnapshot` `StandardLRS` `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

```powershell
$disk = Get-AzureRmDisk -ResourceGroupName 'MyResourceGroup' -DiskName 'MyDiskName'
$disk.Sku.Name       # This will now return Standard_LRS or Premium_LRS

$snapshot = Get-AzureRmSnapshot -ResourceGroupName 'MyResourceGroup' -SnapshotName 'MySnapshotName'
$snapshot.Sku.Name   # This will now return Standard_LRS or Premium_LRS
```

- Properti tipe akun penyimpanan ditum menyediakan `PSVirtualMachine` tipe, `PSVirtualMachineScaleSet` serta diubah dari `PSImage` dan `StandardLRS` `PremiumLRS` `Standard_LRS` ke, secara `Premium_LRS` berurutan

```powershell
$vm = Get-AzureRmVM -ResourceGroupName "MyResourceGroup" -Name "MyVM"
$vm.StorageProfile.DataDisks[0].ManagedDisk.StorageAccountType   # This will now return Standard_LRS or Premium_LRS
```

**Add-AzureRmImageDataDisk**

- Nilai yang diterima untuk parameter `StorageAccountType` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**Add-AzureRmVMDataDisk**

- Nilai yang diterima untuk parameter `StorageAccountType` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**Add-AzureRmVmssDataDisk**

- Nilai yang diterima untuk parameter `StorageAccountType` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**New-AzureRmAvailabilitySet**
- Parameter `Managed` tersebut dihapus untuk membantu `Sku`

```powershell
# Old
New-AzureRmAvailabilitySet -ResourceGroupName "MyRG" -Name "MyAvailabilitySet" -Location "West US" -Managed

# New
New-AzureRmAvailabilitySet -ResourceGroupName "MyRG" -Name "MyAvailabilitySet" -Location "West US" -Sku "Aligned"
```

**New-AzureRmDiskConfig**
- Nilai yang diterima untuk parameter `SkuName` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**New-AzureRmDiskUpdateConfig**
- Nilai yang diterima untuk parameter `SkuName` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**New-AzureRmSnapshotConfig**
- Nilai yang diterima untuk parameter `SkuName` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**New-AzureRmSnapshotUpdateConfig**
- Nilai yang diterima untuk parameter `SkuName` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**Set-AzureRmImageOsDisk**
- Nilai yang diterima untuk parameter `StorageAccountType` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**Set-AzureRmVMAEMExtension**
- Parameter `DisableWAD` telah dihapus
    -  Windows Diagnostik Azure dinonaktifkan secara default

**Set-AzureRmVMDataDisk**
- Nilai yang diterima untuk parameter `StorageAccountType` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**Set-AzureRmVMOSDisk**
- Nilai yang diterima untuk parameter `StorageAccountType` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**Set-AzureRmVmssStorageProfile**
- Nilai yang diterima untuk parameter `ManagedDisk` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

**Update-AzureRmVmss**
- Nilai yang diterima untuk parameter `ManagedDiskStorageAccountType` diubah `StandardLRS` dari dan `PremiumLRS` `Standard_LRS` `Premium_LRS` ke, secara berurutan

## <a name="breaking-changes-to-azurermdatalakestore-cmdlets"></a>Memutus perubahan pada cmdlet AzureRM.DataLakeStore

**Export-AzureRmDataLakeStoreItem**
- Parameter `PerFileThreadCount` dan `ConcurrentFileCount` telah dihapus. Harap gunakan `Concurrency` parameter ke depan

```powershell
# Old
Export-AzureRmDataLakeStoreItem -Account contoso -Path /test -Destination C:\test -Recurse -Resume -PerFileThreadCount 2 -ConcurrentFileCount 80

# New
Export-AzureRmDataLakeStoreItem -Account contoso -Path /test -Destination C:\test -Recurse -Resume -Concurrency 160
```

**Import-AzureRmDataLakeStoreItem**
- Parameter `PerFileThreadCount` dan `ConcurrentFileCount` telah dihapus. Harap gunakan `Concurrency` parameter ke depan

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

## <a name="breaking-changes-to-azurermdns-cmdlets"></a>Memutus perubahan pada cmdlet AzureRM.Dns

**New-AzureRmDnsRecordSet**
- Parameter `Force` telah dihapus

**Remove-AzureRmDnsRecordSet**
- Parameter `Force` telah dihapus

**Remove-AzureRmDnsZone**
- Parameter `Force` telah dihapus

## <a name="breaking-changes-to-azurerminsights-cmdlets"></a>Memutus perubahan pada AzureRM. cmdlet Insights baru

**Add-AzureRmAutoscaleSetting**
- Alias parameter `AutoscaleProfiles` dan `Notifications` telah dihapus

**Add-AzureRmLogProfile**
- Alias parameter `Categories` dan `Locations` telah dihapus

**Add-AzureRmMetricAlertRule**
- Alias parameter `Actions` telah dihapus

**Add-AzureRmWebtestAlertRule**
- Alias parameter `Actions` telah dihapus

**Get-AzureRmLog**
- Alias parameter `MaxRecords` dan `MaxEvents` telah dihapus

**Get-AzureRmMetricDefinition**
- Alias parameter `MetricNames` telah dihapus

**New-AzureRmAlertRuleEmail**
- Alias parameter `CustomEmails` dan `SendToServiceOwners` telah dihapus

**New-AzureRmAlertRuleWebhook**
- Alias parameter `Properties` telah dihapus

**New-AzureRmAutoscaleNotification**
- Alias parameter `CustomEmails` , `SendEmailToSubscriptionCoAdministrators` `Webhooks` dan telah dihapus

**New-AzureRmAutoscaleProfile**
- Alias parameter `Rules` , `ScheduleDays` , dan `ScheduleHours` `ScheduleMinutes` dihapus

**New-AzureRmAutoscaleWebhook**
- Alias parameter `Properties` telah dihapus

## <a name="breaking-changes-to-azurermkeyvault-cmdlets"></a>Memutus perubahan pada cmdlet AzureRM.KeyVault

**Add-AzureKeyVaultCertificate**
- Parameter `CertificatePolicy` ini telah menjadi wajib.

**Set-AzureKeyVaultManagedStorageSasDefinition**
- Cmdlet tidak lagi menerima parameter individu yang membuat token akses; sebaliknya, cmdlet menggantikan parameter token eksplisit, seperti atau , dengan parameter umum, yang terkait dengan token akses sampel yang ditentukan di tempat lain (kemungkinan besar menggunakan cmdlet PowerShell Storage, atau dibuat secara manual menurut `Service` `Permissions` dokumentasi `TemplateUri` Storage.) Cmdlet mempertahankan `ValidityPeriod` parameter.

Untuk informasi selengkapnya tentang membuat token akses bersama untuk Azure Storage, silakan lihat halaman dokumentasi masing-masing:

- [Membangun Service SAS](/rest/api/storageservices/Constructing-a-Service-SAS)
- [Menyusun Sas Akun](/rest/api/storageservices/constructing-an-account-sas)

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
- Parameter `IssuerProvider` ini telah menjadi wajib.

**Undo-AzureKeyVaultCertificateRemoval**
- Output cmdlet ini telah berubah `CertificateBundle` menjadi `PSKeyVaultCertificate` .

**Undo-AzureRmKeyVaultRemoval**
- `ResourceGroupName` telah dihapus dari `InputObject` kumpulan parameter, dan diperoleh dari `InputObject` properti `ResourceId` parameter.

**Set-AzureRmKeyVaultAccessPolicy**
- Izin `all` dihapus dari , , dan `PermissionsToKeys` `PermissionsToSecrets` `PermissionsToCertificates` .

**Umum**
- Properti `ValueFromPipelineByPropertyName` telah dihapus dari semua cmdlet tempat pemipaan oleh `InputObject` diaktifkan. Cmdlet yang terpengaruh adalah:
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

- `ConfirmImpact` tingkat dihapus dari semua cmdlet.  Cmdlet yang terpengaruh adalah:
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

- Opsi `IKeyVaultDataServiceClient` ini diperbarui sehingga semua operasi Sertifikat mengembalikan PSTypes, bukan tipe SDK. Ini termasuk:
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

## <a name="breaking-changes-to-azurermnetwork-cmdlets"></a>Memutus perubahan pada cmdlet AzureRM.Network


**Add-AzureRmApplicationGatewayBackendHttpSettings**
- Parameter `ProbeEnabled` telah dihapus

**Add-AzureRmVirtualNetworkPeering**
- Alias parameter `AlloowGatewayTransit` telah dihapus

**New-AzureRmApplicationGatewayBackendHttpSettings**
- Parameter `ProbeEnabled` telah dihapus

**Set-AzureRmApplicationGatewayBackendHttpSettings**
- Parameter `ProbeEnabled` telah dihapus

## <a name="breaking-changes-to-azurermrediscache-cmdlets"></a>Memutus perubahan pada cmdlet AzureRM.RedisCache

**New-AzureRmRedisCache**
- Parameter `Subnet` `VirtualNetwork` dan dihapus untuk mendukung `SubnetId`
- Parameter `RedisVersion` telah dihapus
- Parameter `MaxMemoryPolicy` tersebut dihapus untuk membantu `RedisConfiguration`

```powershell
# Old
New-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -Location "North Central US" -MaxMemoryPolicy "allkeys-lru"

# New
New-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -Location "North Central US" -RedisConfiguration @{"maxmemory-policy" = "allkeys-lru"}
```

**Set-AzureRmRedisCache**
- Parameter `MaxMemoryPolicy` tersebut dihapus untuk membantu `RedisConfiguration`

```powershell
# Old
Set-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -MaxMemoryPolicy "allkeys-lru"

# New
Set-AzureRmRedisCache -ResourceGroupName "MyRG" -Name "MyRedisCache" -RedisConfiguration @{"maxmemory-policy" = "allkeys-lru"}
```

## <a name="breaking-changes-to-azurermresources-cmdlets"></a>Memutus perubahan pada cmdlet AzureRM.Resources

**Find-AzureRmResource**
- Cmdlet ini dihapus dan fungsionalitasnya dipindahkan ke `Get-AzureRmResource`

```powershell
# Old
Find-AzureRmResource -ResourceType "Microsoft.Web/sites" -ResourceGroupNameContains "ResourceGroup"
Find-AzureRmResource -ResourceType "Microsoft.Web/sites" -ResourceNameContains "test"

# New
Get-AzureRmResource -ResourceType "Microsoft.Web/sites" -ResourceGroupName "*ResourceGroup*"
Get-AzureRmResource -ResourceType "Microsoft.Web/sites" -Name "*test*"
```

**Find-AzureRmResourceGroup**
- Cmdlet ini dihapus dan fungsionalitasnya dipindahkan ke `Get-AzureRmResourceGroup`

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

## <a name="breaking-changes-to-azurermstorage-cmdlets"></a>Memutus perubahan pada AzureRM. Storage cmdlets

**New-AzureRmStorageAccount**
- Parameter `EnableEncryptionService` telah dihapus

**Set-AzureRmStorageAccount**
- Parameter `EnableEncryptionService` dan `DisableEncryptionService` telah dihapus

## <a name="removed-modules"></a>Modul yang dihapus

### `AzureRM.ServerManagement`

Layanan Alat Manajemen Server telah [dihentikan](https://blogs.technet.microsoft.com/servermanagement/2017/05/17/smt-preview-service-is-being-retired-on-june-30-2017/)tahun lalu, dan akibatnya, modul terkait untuk SMT, , dihapus dari dan `AzureRM.ServerManagement` akan menghentikan pengiriman ke `AzureRM` depannya.

### `AzureRM.SiteRecovery`

Modul ini menggantikan , yang merupakan superset fungsional modul dan `AzureRM.SiteRecovery` menyertakan rangkaian baru cmdlet yang `AzureRM.RecoveryServices.SiteRecovery` `AzureRM.SiteRecovery` ekuivalen. Daftar lengkap pemetaan dari cmdlet lama ke baru dapat ditemukan di bawah ini:

| Cmdlet yang tidak lagi dipakai                                        | Cmdlet yang setara                                                | Alias                                  |
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
