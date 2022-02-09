---
title: Semua perubahan dari AzureRM ke Azure PowerShell Az 1.0.0
description: Panduan migrasi ini berisi daftar perubahan melanggar yang dilakukan untuk Azure PowerShell dalam rilis Az versi 1.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 817ee183ba7b567c427d03e4bebecb938c1eabd9
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335057"
---
# <a name="breaking-changes-for-az-100"></a>Melanggar perubahan untuk Az 1.0.0

Dokumen ini memberikan informasi terperinci tentang perubahan antara AzureRM 6.x dan modul Az baru, versi 1.x dan yang lebih baru. Daftar isi akan membantu memandu Anda melalui jalur migrasi penuh, termasuk perubahan khusus modul yang dapat memengaruhi skrip Anda.

Untuk saran umum tentang memulai migrasi dari AzureRM ke Az, lihat [Mulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).

> [!IMPORTANT]
> Ada perubahan yang melanggar antara Az 1.0.0 dan Az 2.0.0 juga. Setelah mengikuti panduan ini untuk memperbarui dari AzureRM ke Az, lihat [az 2.0.0 melanggar perubahan](migrate-az-2.0.0.md) untuk mengetahui apakah Anda perlu membuat perubahan tambahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Perubahan yang melanggar umum](#general-breaking-changes)
  - [Perubahan awalan kata benda Cmdlet](#cmdlet-noun-prefix-changes)
  - [Perubahan nama modul](#module-name-changes)
  - [Modul yang dihapus](#removed-modules)
  - [Windows PowerShell 5.1 dan .NET 4.7.2](#windows-powershell-51-and-net-472)
  - [Penghapusan sementara login pengguna menggunakan PSCredential](#temporary-removal-of-user-login-using-pscredential)
  - [Login kode perangkat default alih-alih prompt browser web](#default-device-code-login-instead-of-web-browser-prompt)
- [Perubahan pemecahan modul](#module-breaking-changes)
  - [Az.ApiManagement (sebelumnya AzureRM.ApiManagement)](#azapimanagement-previously-azurermapimanagement)
  - [Az.Billing (sebelumnya AzureRM.Billing, AzureRM.Consumption, dan AzureRM.UsageAggregates)](#azbilling-previously-azurermbilling-azurermconsumption-and-azurermusageaggregates)
  - [Az.CognitiveServices (sebelumnya AzureRM.CognitiveServices)](#azcognitiveservices-previously-azurermcognitiveservices)
  - [Az.Compute (sebelumnya AzureRM.Compute)](#azcompute-previously-azurermcompute)
  - [Az.DataFactory (sebelumnya AzureRM.DataFactories dan AzureRM.DataFactoryV2)](#azdatafactory-previously-azurermdatafactories-and-azurermdatafactoryv2)
  - [Az.DataLakeAnalytics (sebelumnya AzureRM.DataLakeAnalytics)](#azdatalakeanalytics-previously-azurermdatalakeanalytics)
  - [Az.DataLakeStore (sebelumnya AzureRM.DataLakeStore)](#azdatalakestore-previously-azurermdatalakestore)
  - [Az.KeyVault (sebelumnya AzureRM.KeyVault)](#azkeyvault-previously-azurermkeyvault)
  - [Az.Media (sebelumnya AzureRM.Media)](#azmedia-previously-azurermmedia)
  - [Az.Monitor (sebelumnya AzureRM.Insights)](#azmonitor-previously-azurerminsights)
  - [Az.Network (sebelumnya AzureRM.Network)](#aznetwork-previously-azurermnetwork)
  - [Az.OperationalInsights (sebelumnya AzureRM.OperationalInsights)](#azoperationalinsights-previously-azurermoperationalinsights)
  - [Az.RecoveryServices (sebelumnya AzureRM.RecoveryServices, AzureRM.RecoveryServices.Backup, dan AzureRM.RecoveryServices.SiteRecovery)](#azrecoveryservices-previously-azurermrecoveryservices-azurermrecoveryservicesbackup-and-azurermrecoveryservicessiterecovery)
  - [Az.Resources (sebelumnya AzureRM.Resources)](#azresources-previously-azurermresources)
  - [Az.ServiceFabric (sebelumnya AzureRM.ServiceFabric)](#azservicefabric-previously-azurermservicefabric)
  - [Az.Sql (sebelumnya AzureRM.Sql)](#azsql-previously-azurermsql)
  - [Az.Storage (sebelumnya Azure.Storage dan AzureRM.Storage)](#azstorage-previously-azurestorage-and-azurermstorage)
  - [Az.Websites (sebelumnya AzureRM.Websites)](#azwebsites-previously-azurermwebsites)

## <a name="general-breaking-changes"></a>Perubahan yang melanggar umum

Bagian ini merinci perubahan pemecahan umum yang merupakan bagian dari desain ulang modul Az.

### <a name="cmdlet-noun-prefix-changes"></a>Perubahan Awalan Cmdlet Noun

Dalam modul AzureRM, cmdlet digunakan baik `AzureRM` atau `Azure` sebagai awalan kata benda.  Az menyederhanakan dan menormalkan nama cmdlet, sehingga semua cmdlet menggunakan 'Az' sebagai awalan kata benda cmdlet mereka. Contohnya:

```azurepowershell-interactive
Get-AzureRMVM
Get-AzureKeyVaultSecret
```

Telah berubah menjadi:

```azurepowershell-interactive
Get-AzVM
Get-AzKeyVaultSecret
```

Untuk mempermudah transisi ke nama cmdlet baru ini, Az memperkenalkan dua cmdlet baru, [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) dan [Disable-AzureRmAlias](/powershell/module/az.accounts/disable-azurermalias).  `Enable-AzureRmAlias` membuat alias untuk nama cmdlet lama di AzureRM yang memetakan ke nama cmdlet Az yang lebih baru. `-Scope` Menggunakan argumen dengan `Enable-AzureRmAlias` memungkinkan Anda untuk memilih di mana alias diaktifkan.

Misalnya, skrip berikut di AzureRM:

```azurepowershell-interactive
#Requires -Modules AzureRM.Storage
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

Dapat dijalankan dengan perubahan minimal menggunakan `Enable-AzureRmAlias`:

```azurepowershell-interactive
#Requires -Modules Az.Storage
Enable-AzureRmAlias -Scope Process
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

Menjalankan `Enable-AzureRmAlias -Scope CurrentUser` akan mengaktifkan alias untuk semua sesi PowerShell yang Anda buka, sehingga setelah menjalankan cmdlet ini, skrip seperti ini tidak perlu diubah sama sekali:

```azurepowershell-interactive
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

Untuk detail lengkap tentang penggunaan cmdlet alias, lihat [referensi Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias).

Saat Anda siap menonaktifkan alias, `Disable-AzureRmAlias` hapus alias yang dibuat. Untuk detail selengkapnya, lihat [referensi Disable-AzureRmAlias](/powershell/module/az.accounts/disable-azurermalias).

> [!IMPORTANT]
> Saat menonaktifkan alias, pastikan bahwa mereka dinonaktifkan untuk _semua_ cakupan yang memiliki alias diaktifkan.

### <a name="module-name-changes"></a>Perubahan Nama Modul

Nama modul telah berubah dari `AzureRM.*` ke `Az.*`, kecuali untuk modul berikut:

| AzureRM module | Modul Az |
|----------------|-----------|
| Azure.Storage | Az.Storage |
| Azure.AnalysisServices | Az.AnalysisServices |
| AzureRM.Profile | Az.Accounts |
| AzureRM. Insights | Az.Monitor |
| AzureRM.DataFactories | Az.DataFactory |
| AzureRM.DataFactoryV2 | Az.DataFactory |
| AzureRM.RecoveryServices.Backup | Az.RecoveryServices |
| AzureRM.RecoveryServices.SiteRecovery | Az.RecoveryServices |
| AzureRM.Tags | Az.Resources |
| AzureRM.MachineLearningCompute | Az.MachineLearning |
| AzureRM.UsageAggregates | Az.Billing |
| AzureRM.Consumption | Az.Billing |

Perubahan dalam nama modul berarti bahwa setiap skrip yang menggunakan `#Requires` atau `Import-Module` memuat modul tertentu perlu diubah untuk menggunakan modul baru sebagai gantinya. Untuk modul di mana akhiran cmdlet tidak berubah, ini berarti bahwa meskipun nama modul telah berubah, akhiran yang menunjukkan ruang operasi _belum_.

#### <a name="migrating-requires-and-import-module-statements"></a>Migrasi pernyataan #Requires dan Import-Module

Skrip yang menggunakan `#Requires` atau `Import-Module` mendeklarasikan dependensi pada modul AzureRM harus diperbarui untuk menggunakan nama modul baru. Contohnya:

```azurepowershell-interactive
#Requires -Module AzureRM.Compute
```

Harus diubah menjadi:

```azurepowershell-interactive
#Requires -Module Az.Compute
```

Untuk `Import-Module`:

```azurepowershell-interactive
Import-Module -Name AzureRM.Compute
```

Harus diubah menjadi:

```azurepowershell-interactive
Import-Module -Name Az.Compute
```

### <a name="migrating-fully-qualified-cmdlet-invocations"></a>Doa cmdlet Fully-Qualified bermigrasi

Skrip yang menggunakan pemanggilan cmdlet yang memenuhi syarat modul, seperti:

```azurepowershell-interactive
AzureRM.Compute\Get-AzureRmVM
```

Harus diubah untuk menggunakan modul baru dan nama cmdlet:

```azurepowershell-interactive
Az.Compute\Get-AzVM
```

### <a name="migrating-module-manifest-dependencies"></a>Migrasi dependensi manifes modul

Modul yang mengekspresikan dependensi pada modul AzureRM melalui file manifes modul (.psd1) perlu memperbarui nama modul di bagiannya `RequiredModules` :

```powershell
RequiredModules = @(@{ModuleName="AzureRM.Profile"; ModuleVersion="5.8.2"})
```

Harus diubah menjadi:

```powershell
RequiredModules = @(@{ModuleName="Az.Profile"; ModuleVersion="1.0.0"})
```

### <a name="removed-modules"></a>Modul yang dihapus

Modul-modul berikut telah dihapus:

- `AzureRM.Backup`
- `AzureRM.Compute.ManagedService`
- `AzureRM.Scheduler`

Alat untuk layanan ini tidak lagi didukung secara aktif.  Pelanggan didorong untuk pindah ke layanan alternatif segera setelah nyaman.

### <a name="windows-powershell-51-and-net-472"></a>Windows PowerShell 5.1 dan .NET 4.7.2

Menggunakan Az dengan PowerShell 5.1 untuk Windows memerlukan instalasi .NET Framework 4.7.2. Menggunakan PowerShell Core 6.x atau yang lebih baru tidak memerlukan .NET Framework.

### <a name="temporary-removal-of-user-login-using-pscredential"></a>Penghapusan sementara login Pengguna menggunakan PSCredential

Karena perubahan alur autentikasi untuk .NET Standard, kami untuk sementara menghapus login pengguna melalui PSCredential. Kemampuan ini akan diperkenalkan kembali dalam rilis 1/15/2019 untuk PowerShell 5.1 untuk Windows. Hal ini dibahas secara rinci dalam [masalah GitHub ini.](https://github.com/Azure/azure-powershell/issues/7430)

### <a name="default-device-code-login-instead-of-web-browser-prompt"></a>Login kode perangkat default alih-alih prompt browser web

Karena perubahan dalam alur otentikasi untuk .NET Standard, kami menggunakan login perangkat sebagai aliran login default selama login interaktif. Login berbasis browser web akan diperkenalkan kembali untuk PowerShell 5.1 untuk Windows sebagai default dalam rilis 1/1/2019. Pada saat itu, pengguna akan dapat memilih login perangkat menggunakan parameter Switch.

## <a name="module-breaking-changes"></a>Perubahan pemecahan modul

Bagian ini merinci perubahan pemecahan spesifik untuk modul dan cmdlet individual.

### <a name="azapimanagement-previously-azurermapimanagement"></a>Az.ApiManagement (sebelumnya AzureRM.ApiManagement)

- Menghapus cmdlet berikut:
  - New-AzureRmApiManagementHostnameConfiguration
  - Set-AzureRmApiManagementHostnames
  - Update-AzureRmApiManagementDeployment
  - Import-AzureRmApiManagementHostnameCertificate
  - Gunakan **cmdlet Set-AzApiMenagement** untuk mengatur properti ini sebagai gantinya
- Menghapus properti berikut:
  - Properti `PortalHostnameConfiguration`yang dihapus, `ProxyHostnameConfiguration`, `ManagementHostnameConfiguration` dan `ScmHostnameConfiguration` jenis `PsApiManagementHostnameConfiguration` dari `PsApiManagementContext`. Sebagai gantinya gunakan `PortalCustomHostnameConfiguration`, `ProxyCustomHostnameConfiguration`dan `ManagementCustomHostnameConfiguration` `ScmCustomHostnameConfiguration` jenis `PsApiManagementCustomHostNameConfiguration`.
  - Properti yang `StaticIPs` dihapus dari PsApiManagementContext. Properti telah dibagi menjadi `PublicIPAddresses` dan `PrivateIPAddresses`.
  - Menghapus properti yang `Location` diperlukan dari cmdlet New-AzureApiManagementVirtualNetwork.

### <a name="azbilling-previously-azurermbilling-azurermconsumption-and-azurermusageaggregates"></a>Az.Billing (sebelumnya AzureRM.Billing, AzureRM.Consumption, dan AzureRM.UsageAggregates)

- Parameter `InvoiceName` telah dihapus dari `Get-AzConsumptionUsageDetail` cmdlet.  Skrip harus menggunakan parameter identitas lain untuk faktur.

### <a name="azcognitiveservices-previously-azurermcognitiveservices"></a>Az.CognitiveServices (sebelumnya AzureRM.CognitiveServices)

- Parameter dihapus `GetSkusWithAccountParamSetName` diatur dari `Get-AzCognitiveServicesAccountSkus` cmdlet.  Anda harus mendapatkan Skus berdasarkan Jenis dan Lokasi Akun, alih-alih menggunakan ResourceGroupName dan Nama Akun.

### <a name="azcompute-previously-azurermcompute"></a>Az.Compute (sebelumnya AzureRM.Compute)

- `IdentityIds` dihapus dari `Identity` properti dan `PSVirtualMachine` `PSVirtualMachineScaleSet` objek Skrip tidak boleh lagi menggunakan nilai bidang ini untuk membuat keputusan pemrosesan.
- Jenis `InstanceView` properti `PSVirtualMachineScaleSetVM` objek diubah dari `VirtualMachineInstanceView` menjadi `VirtualMachineScaleSetVMInstanceView`
- `AutoOSUpgradePolicy` dan `AutomaticOSUpgrade` properti dihapus dari `UpgradePolicy` properti
- Jenis `Sku` properti dalam `PSSnapshotUpdate` objek diubah dari `DiskSku` menjadi `SnapshotSku`
- `VmScaleSetVMParameterSet` dihapus dari `Add-AzVMDataDisk` cmdlet, Anda tidak dapat lagi menambahkan disk data secara individual ke ScaleSet VM.

### <a name="azdatafactory-previously-azurermdatafactories-and-azurermdatafactoryv2"></a>Az.DataFactory (sebelumnya AzureRM.DataFactories dan AzureRM.DataFactoryV2)

- Parameter `GatewayName` telah menjadi wajib dalam `New-AzDataFactoryEncryptValue` cmdlet
- Cmdlet yang dihapus `New-AzDataFactoryGatewayKey`
- Parameter yang dihapus `LinkedServiceName` dari `Get-AzDataFactoryV2ActivityRun` Skrip cmdlet seharusnya tidak lagi menggunakan nilai bidang ini untuk membuat keputusan pemrosesan.

### <a name="azdatalakeanalytics-previously-azurermdatalakeanalytics"></a>Az.DataLakeAnalytics (sebelumnya AzureRM.DataLakeAnalytics)

- Dihapus cmdlet usang: `New-AzDataLakeAnalyticsCatalogSecret`, , `Remove-AzDataLakeAnalyticsCatalogSecret`dan `Set-AzDataLakeAnalyticsCatalogSecret`

### <a name="azdatalakestore-previously-azurermdatalakestore"></a>Az.DataLakeStore (sebelumnya AzureRM.DataLakeStore)

- Cmdlet berikut telah mengubah `Encoding` parameter dari jenis `FileSystemCmdletProviderEncoding` menjadi `System.Text.Encoding`. Perubahan ini menghapus nilai `String` pengkodean dan `Oem`. Semua nilai pengkodean sebelumnya lainnya tetap ada.
  - New-AzureRmDataLakeStoreItem
  - Add-AzureRmDataLakeStoreItemContent
  - Get-AzureRmDataLakeStoreItemContent
- Menghapus alias properti yang `Tags` tidak digunakan lagi dari `New-AzDataLakeStoreAccount` dan `Set-AzDataLakeStoreAccount` cmdlet

  Skrip menggunakan
  ```azurepowershell-interactive
  New-AzureRMDataLakeStoreAccount -Tags @{TagName="TagValue"}
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  New-AzDataLakeStoreAccount -Tag @{TagName="TagValue"}
  ```

- Menghapus properti `Identity`usang , , `EncryptionState`, `EncryptionConfig``EncryptionProvisioningState`, `FirewallState`, `FirewallRules`, `VirtualNetworkRules`, , `TrustedIdProviderState`, `TrustedIdProviders`, `DefaultGroup`, , `NewTier`, `CurrentTier``FirewallAllowAzureIps` dari `PSDataLakeStoreAccountBasic` objek.  Skrip apa pun yang menggunakan `PSDatalakeStoreAccount` yang `Get-AzDataLakeStoreAccount` dikembalikan tidak boleh mereferensikan properti ini.

### <a name="azkeyvault-previously-azurermkeyvault"></a>Az.KeyVault (sebelumnya AzureRM.KeyVault)

- Properti `PurgeDisabled` telah dihapus dari `PSKeyVaultKeyAttributes`skrip, `PSKeyVaultKeyIdentityItem`dan `PSKeyVaultSecretAttributes` objek seharusnya tidak lagi merujuk ```PurgeDisabled``` properti untuk membuat keputusan pemrosesan.

### <a name="azmedia-previously-azurermmedia"></a>Az.Media (sebelumnya AzureRM.Media)

- Menghapus alias properti usang `Tags` dari `New-AzMediaService` skrip cmdlet menggunakan
  ```azurepowershell-interactive
  New-AzureRMMediaService -Tags @{TagName="TagValue"}
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  New-AzMediaService -Tag @{TagName="TagValue"}
  ```

### <a name="azmonitor-previously-azurerminsights"></a>Az.Monitor (sebelumnya AzureRM.Insights)

- Menghapus nama `Categories` dan `Timegrains` parameter jamak yang mendukung nama parameter tunggal dari `Set-AzDiagnosticSetting` Skrip cmdlet menggunakan
  ```azurepowershell-interactive
  Set-AzureRmDiagnosticSetting -Timegrains PT1M -Categories Category1, Category2
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  Set-AzDiagnosticSetting -Timegrain PT1M -Category Category1, Category2
  ```

### <a name="aznetwork-previously-azurermnetwork"></a>Az.Network (sebelumnya AzureRM.Network)

- Menghapus parameter yang `ResourceId` tidak digunakan lagi dari `Get-AzServiceEndpointPolicyDefinition` cmdlet
- Menghapus properti yang `EnableVmProtection` tidak digunakan lagi dari `PSVirtualNetwork` objek
- Dihapus cmdlet usang `Set-AzVirtualNetworkGatewayVpnClientConfig`

Skrip seharusnya tidak lagi membuat keputusan pemrosesan berdasarkan nilai-nilai di bidang ini.

### <a name="azoperationalinsights-previously-azurermoperationalinsights"></a>Az.OperationalInsights (sebelumnya AzureRM.OperationalInsights)

- Parameter default yang ditetapkan untuk `Get-AzOperationalInsightsDataSource` dihapus, dan `ByWorkspaceNameByKind` telah menjadi kumpulan parameter default

  Skrip yang mencantumkan sumber data menggunakan
  ```azurepowershell-interactive
  Get-AzureRmOperationalInsightsDataSource
  ```

  Harus diubah untuk menentukan Jenis
  ```azurepowershell-interactive
  Get-AzOperationalInsightsDataSource -Kind AzureActivityLog
  ```

### <a name="azrecoveryservices-previously-azurermrecoveryservices-azurermrecoveryservicesbackup-and-azurermrecoveryservicessiterecovery"></a>Az.RecoveryServices (sebelumnya AzureRM.RecoveryServices, AzureRM.RecoveryServices.Backup, dan AzureRM.RecoveryServices.SiteRecovery)

- Parameter dihapus `Encryption` dari `New/Set-AzRecoveryServicesAsrPolicy` cmdlet
- `TargetStorageAccountName` parameter sekarang wajib untuk pemulihan disk terkelola dalam `Restore-AzRecoveryServicesBackupItem` cmdlet
- Dihapus `StorageAccountName` dan `StorageAccountResourceGroupName` parameter dalam `Restore-AzRecoveryServicesBackupItem` cmdlet
- Parameter dihapus `Name`dalam `Get-AzRecoveryServicesBackupContainer` cmdlet

### <a name="azresources-previously-azurermresources"></a>Az.Resources (sebelumnya AzureRM.Resources)

- Parameter dihapus `Sku` dari `New/Set-AzPolicyAssignment` cmdlet
- Parameter yang dihapus `Password` dari `New-AzADServicePrincipal` dan `New-AzADSpCredential` cmdlet Kata sandi dibuat secara otomatis, skrip yang menyediakan kata sandi:

  ```azurepowershell-interactive
  New-AzAdSpCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476 -Password $secPassword
  ```

  Harus diubah untuk mengambil kata sandi dari output:

  ```azurepowershell-interactive
  $credential = New-AzAdSpCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476
  $secPassword = $credential.Secret
  ```

### <a name="azservicefabric-previously-azurermservicefabric"></a>Az.ServiceFabric (sebelumnya AzureRM.ServiceFabric)

- Jenis pengembalian cmdlet berikut telah diubah:
  - Properti `ServiceTypeHealthPolicies` jenis `ApplicationHealthPolicy` telah dihapus.
  - Properti `ApplicationHealthPolicies` jenis `ClusterUpgradeDeltaHealthPolicy` telah dihapus.
  - Properti `OverrideUserUpgradePolicy` jenis `ClusterUpgradePolicy` telah dihapus.
  - Perubahan ini memengaruhi cmdlet berikut:
    - Add-AzServiceFabricClientCertificate
    - Add-AzServiceFabricClusterCertificate
    - Add-AzServiceFabricNode
    - Add-AzServiceFabricNodeType
    - Get-AzServiceFabricCluster
    - Remove-AzServiceFabricClientCertificate
    - Remove-AzServiceFabricClusterCertificate
    - Remove-AzServiceFabricNode
    - Remove-AzServiceFabricNodeType
    - Remove-AzServiceFabricSetting
    - Set-AzServiceFabricSetting
    - Set-AzServiceFabricUpgradeType
    - Update-AzServiceFabricDurability
    - Update-AzServiceFabricReliability

### <a name="azsql-previously-azurermsql"></a>Az.Sql (sebelumnya AzureRM.Sql)

- Dihapus `State` dan `ResourceId` parameter dari `Set-AzSqlDatabaseBackupLongTermRetentionPolicy` cmdlet
- Cmdlet yang tidak digunakan lagi: `Get/Set-AzSqlServerBackupLongTermRetentionVault`, `Get/Start/Stop-AzSqlServerUpgrade`, `Get/Set-AzSqlDatabaseAuditingPolicy`, `Get/Set-AzSqlServerAuditingPolicy`, `Remove-AzSqlDatabaseAuditing``Remove-AzSqlServerAuditing`
- Menghapus parameter `Current` yang tidak digunakan lagi dari `Get-AzSqlDatabaseBackupLongTermRetentionPolicy` cmdlet
- Menghapus parameter `DatabaseName` yang tidak digunakan lagi dari `Get-AzSqlServerServiceObjective` cmdlet
- Menghapus parameter `PrivilegedLogin` yang tidak digunakan lagi dari `Set-AzSqlDatabaseDataMaskingPolicy` cmdlet

### <a name="azstorage-previously-azurestorage-and-azurermstorage"></a>Az.Storage (sebelumnya Azure.Storage dan AzureRM.Storage)

- Untuk mendukung pembuatan konteks penyimpanan Oauth hanya dengan nama akun penyimpanan, kumpulan parameter default telah diubah menjadi `OAuthParameterSet`
  - Contoh: `$ctx = New-AzureStorageContext -StorageAccountName $accountName`
- Parameter `Location` telah menjadi wajib dalam `Get-AzStorageUsage` cmdlet
- Metode API Storage sekarang menggunakan Pola Asinkron berbasis Tugas (TAP), bukan panggilan API sinkron. Contoh-contoh berikut menunjukkan perintah asinkron baru:

#### <a name="blob-snapshot"></a>Blob Snapshot

AzureRM:

```azurepowershell-interactive
$b = Get-AzureStorageBlob -Container $containerName -Blob $blobName -Context $ctx
$b.ICloudBlob.Snapshot()
```

Az:

```azurepowershell-interactive
$b = Get-AzStorageBlob -Container $containerName -Blob $blobName -Context $ctx
$task = $b.ICloudBlob.SnapshotAsync()
$task.Wait()
$snapshot = $task.Result
```

#### <a name="share-snapshot"></a>Bagi Snapshot

AzureRM:

```azurepowershell-interactive
$Share = Get-AzureStorageShare -Name $containerName -Context $ctx
$snapshot = $Share.Snapshot()
```

Az:

```azurepowershell-interactive
$Share = Get-AzStorageShare -Name $containerName -Context $ctx
$task = $Share.SnapshotAsync()
$task.Wait()
$snapshot = $task.Result
```

#### <a name="undelete-soft-deleted-blob"></a>Undelete soft-deleted blob

AzureRM:

```azurepowershell-interactive
$b = Get-AzureStorageBlob -Container $containerName -Blob $blobName -IncludeDeleted -Context $ctx
$b.ICloudBlob.Undelete()
```

Az:

```azurepowershell-interactive
$b = Get-AzStorageBlob -Container $containerName -Blob $blobName -IncludeDeleted -Context $ctx
$task = $b.ICloudBlob.UndeleteAsync()
$task.Wait()
```

#### <a name="set-blob-tier"></a>Atur Tingkat Blob

AzureRM:

```azurepowershell-interactive
$blockBlob = Get-AzureStorageBlob -Container $containerName -Blob $blockBlobName -Context $ctx
$blockBlob.ICloudBlob.SetStandardBlobTier("hot")

$pageBlob = Get-AzureStorageBlob -Container $containerName -Blob $pageBlobName -Context $ctx
$pageBlob.ICloudBlob.SetPremiumBlobTier("P4")
```

Az:

```azurepowershell-interactive
$blockBlob = Get-AzStorageBlob -Container $containerName -Blob $blockBlobName -Context $ctx
$task = $blockBlob.ICloudBlob.SetStandardBlobTierAsync("hot")
$task.Wait()

$pageBlob = Get-AzStorageBlob -Container $containerName -Blob $pageBlobName -Context $ctx
$task = $pageBlob.ICloudBlob.SetPremiumBlobTierAsync("P4")
$task.Wait()
```

### <a name="azwebsites-previously-azurermwebsites"></a>Az.Websites (sebelumnya AzureRM.Websites)

- Menghapus properti yang tidak digunakan lagi dari `PSAppServicePlan`, `PSCertificate`, `PSCloningInfo`, dan `PSSite` objek
