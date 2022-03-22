---
title: Semua perubahan daro AzureRM menjadi Azure PowerShell Az 1.0.0
description: Panduan migrasi ini berisi daftar perubahan pemecahan yang dibuat untuk Azure PowerShell dalam rilis Az versi 1.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: d4a46e88da17966b10a5cda0eed381b4d47106c4
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429506"
---
# <a name="breaking-changes-for-az-100"></a>Perubahan yang dapat menyebabkan gangguan untuk Az 1.0.0

Dokumen ini memberikan informasi detail tentang perubahan antara AzureRM 6.x dan modul Az baru, versi 1.x dan yang lebih baru. Daftar isi akan membantu memandu Anda menyelesaikan jalur migrasi penuh, termasuk perubahan khusus modul yang dapat memengaruhi skrip Anda.

Untuk saran umum tentang memulai dengan migrasi dari AzureRM ke Az, lihat [Memulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).

> [!IMPORTANT]
> Telah terdapat pula perubahan pemecahan antara Az 1.0.0 dan Az 2.0.0. Setelah mengikuti panduan ini untuk memperbarui dari AzureRM ke Az, lihat [perubahan pemecahan Az 2.0.0](migrate-az-2.0.0.md) untuk mengetahui apakah Anda harus membuat perubahan tambahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Perubahan umum yang dapat menyebabkan gangguan](#general-breaking-changes)
  - [Perubahan awalan kata benda cmdlet](#cmdlet-noun-prefix-changes)
  - [Perubahan nama modul](#module-name-changes)
  - [Modul yang dihapus](#removed-modules)
  - [Windows PowerShell 5.1 and .NET 4.7.2](#windows-powershell-51-and-net-472)
  - [Penghapusan sementara masuk pengguna menggunakan PSCredential](#temporary-removal-of-user-login-using-pscredential)
  - [Masuk kode perangkat default sebagai ganti perintah browser web](#default-device-code-login-instead-of-web-browser-prompt)
- [Perubahan modul yang dapat menyebabkan gangguan](#module-breaking-changes)
  - [Az.ApiManagement (previously AzureRM.ApiManagement)](#azapimanagement-previously-azurermapimanagement)
  - [Az.Billing (previously AzureRM.Billing, AzureRM.Consumption, and AzureRM.UsageAggregates)](#azbilling-previously-azurermbilling-azurermconsumption-and-azurermusageaggregates)
  - [Az.CognitiveServices (previously AzureRM.CognitiveServices)](#azcognitiveservices-previously-azurermcognitiveservices)
  - [Az.Compute (previously AzureRM.Compute)](#azcompute-previously-azurermcompute)
  - [Az.DataFactory (sebelumnya AzureRM.DataFactories dan AzureRM.DataFactoryV2)](#azdatafactory-previously-azurermdatafactories-and-azurermdatafactoryv2)
  - [Az.DataLakeAnalytics (previously AzureRM.DataLakeAnalytics)](#azdatalakeanalytics-previously-azurermdatalakeanalytics)
  - [Az.DataLakeStore (previously AzureRM.DataLakeStore)](#azdatalakestore-previously-azurermdatalakestore)
  - [Az.KeyVault (previously AzureRM.KeyVault)](#azkeyvault-previously-azurermkeyvault)
  - [Az.Media (previously AzureRM.Media)](#azmedia-previously-azurermmedia)
  - [Az.Monitor (previously AzureRM.Insights)](#azmonitor-previously-azurerminsights)
  - [Az.Network (previously AzureRM.Network)](#aznetwork-previously-azurermnetwork)
  - [Az.OperationalInsights (sebelumnya AzureRM.OperationalInsights)](#azoperationalinsights-previously-azurermoperationalinsights)
  - [Az.RecoveryServices (sebelumnya AzureRM.RecoveryServices, AzureRM.RecoveryServices.Backup, dan AzureRM.RecoveryServices.SiteRecovery)](#azrecoveryservices-previously-azurermrecoveryservices-azurermrecoveryservicesbackup-and-azurermrecoveryservicessiterecovery)
  - [Az.Resources (previously AzureRM.Resources)](#azresources-previously-azurermresources)
  - [Az.ServiceFabric (previously AzureRM.ServiceFabric)](#azservicefabric-previously-azurermservicefabric)
  - [Az.Sql (sebelumnya AzureRM.Sql)](#azsql-previously-azurermsql)
  - [Az.Storage (previously Azure.Storage and AzureRM.Storage)](#azstorage-previously-azurestorage-and-azurermstorage)
  - [Az.Websites (previously AzureRM.Websites)](#azwebsites-previously-azurermwebsites)

## <a name="general-breaking-changes"></a>Perubahan umum yang dapat menyebabkan gangguan

Bagian ini merinci perubahan umum yang dapat menyebabkan gangguan yang merupakan bagian dari desain ulang modul Az.

### <a name="cmdlet-noun-prefix-changes"></a>Perubahan awalan kata benda cmdlet

Di modul AzureRM, cmdlet menggunakan `AzureRM` atau `Azure` sebagai awalan kata benda.  Az menyederhanakan dan menormalkan nama cmdlet, sehingga semua cmdlet menggunakan 'Az' sebagai awalan kata benda cmdlet-nya. Contohnya:

```azurepowershell-interactive
Get-AzureRMVM
Get-AzureKeyVaultSecret
```

Telah berubah menjadi:

```azurepowershell-interactive
Get-AzVM
Get-AzKeyVaultSecret
```

Untuk mempermudah transisi ke nama cmdlet baru ini, Az memperkenalkan dua cmdlet baru, [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) dan [Disable-AzureRmAlias](/powershell/module/az.accounts/disable-azurermalias).  `Enable-AzureRmAlias` membuat alias untuk nama cmdlet lama di AzureRM yang memetakan ke nama cmdlet Az yang lebih baru. Menggunakan argumen `-Scope` dengan `Enable-AzureRmAlias` memungkinkan Anda untuk memilih di mana alias diaktifkan.

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

Saat Anda siap menonaktifkan alias, `Disable-AzureRmAlias` akan menghapus alias yang dibuat. Untuk detail selengkapnya, lihat [referensi Disable-AzureRmAlias](/powershell/module/az.accounts/disable-azurermalias).

> [!IMPORTANT]
> Saat menonaktifkan alias, pastikan bahwa alias dinonaktifkan untuk _semua_ cakupan yang memiliki alias aktif.

### <a name="module-name-changes"></a>Perubahan nama modul

Nama modul telah berubah dari `AzureRM.*` ke `Az.*`, kecuali untuk modul berikut:

| AzureRM module | Modul Az |
|----------------|-----------|
| Azure.Storage | Az.Storage |
| Azure.AnalysisServices | Az.AnalysisServices |
| AzureRM.Profile | Az.Accounts |
| AzureRM.Insights | Az.Monitor |
| AzureRM.DataFactories | Az.DataFactory |
| AzureRM.DataFactoryV2 | Az.DataFactory |
| AzureRM.RecoveryServices.Backup | Az.RecoveryServices |
| AzureRM.RecoveryServices.SiteRecovery | Az.RecoveryServices |
| AzureRM.Tags | Az.Resources |
| AzureRM.MachineLearningCompute | Az.MachineLearning |
| AzureRM.UsageAggregates | Az.Billing |
| AzureRM.Consumption | Az.Billing |

Perubahan dalam nama modul berarti bahwa setiap skrip yang menggunakan `#Requires` atau `Import-Module` untuk memuat modul tertentu harus diubah untuk menggunakan modul baru sebagai gantinya. Untuk modul yang akhiran cmdlet-nya tidak berubah, ini berarti meskipun nama modul telah berubah, akhiran yang menunjukkan ruang operasi _masih belum_.

#### <a name="migrating-requires-and-import-module-statements"></a>Memigrasi #Memerlukan dan Mengimpor Pernyataan Modul

Skrip yang menggunakan `#Requires` atau `Import-Module` untuk mendeklarasikan dependensi pada modul AzureRM harus diperbarui untuk menggunakan nama modul baru. Contohnya:

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

### <a name="migrating-fully-qualified-cmdlet-invocations"></a>Migrasi Pemanggilan Cmdlet yang Memenuhi Syarat

Skrip yang menggunakan pemanggilan cmdlet yang memenuhi syarat modul, seperti:

```azurepowershell-interactive
AzureRM.Compute\Get-AzureRmVM
```

Harus diubah untuk menggunakan modul dan nama cmdlet baru:

```azurepowershell-interactive
Az.Compute\Get-AzVM
```

### <a name="migrating-module-manifest-dependencies"></a>Memigrasi dependensi manifes modul

Modul yang menunjukkan dependensi pada modul AzureRM melalui file manifes modul (.psd1) harus memperbarui nama modul di bagian `RequiredModules`:

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

Alat untuk layanan ini tidak lagi didukung secara aktif.  Pelanggan disarankan untuk pindah ke layanan alternatif segera setelah sesuai.

### <a name="windows-powershell-51-and-net-472"></a>Windows PowerShell 5.1 and .NET 4.7.2

Menggunakan Az dengan PowerShell 5.1 untuk Windows memerlukan penginstalan .NET Framework 4.7.2. Menggunakan PowerShell Core 6.x atau yang lebih baru tidak memerlukan .NET Framework.

### <a name="temporary-removal-of-user-login-using-pscredential"></a>Penghapusan sementara masuk Pengguna menggunakan PSCredential

Karena perubahan alur autentikasi untuk .NET Standard, kami untuk sementara menghapus pengguna yang masuk melalui PSCredential. Kemampuan ini akan diperkenalkan kembali dalam rilis 1/15/2019 untuk PowerShell 5.1 untuk Windows. Ini dibahas secara detail dalam [masalah GitHub ini.](https://github.com/Azure/azure-powershell/issues/7430)

### <a name="default-device-code-login-instead-of-web-browser-prompt"></a>Masuk kode perangkat default sebagai ganti perintah browser web

Karena perubahan dalam alur autentikasi untuk .NET Standar, kami menggunakan masuk perangkat sebagai alur masuk default selama masuk interaktif. Masuk berbasis browser web akan diperkenalkan kembali untuk PowerShell 5.1 untuk Windows sebagai default dalam rilis 1/15/2019. Pada saat itu, pengguna akan dapat memilih masuk perangkat menggunakan parameter Beralih.

## <a name="module-breaking-changes"></a>Perubahan modul yang dapat menyebabkan gangguan

Bagian ini merinci perubahan spesifik yang dapat menyebabkan gangguan untuk modul dan cmdlet individual.

### <a name="azapimanagement-previously-azurermapimanagement"></a>Az.ApiManagement (previously AzureRM.ApiManagement)

- Menghapus cmdlet berikut: 
  - New-AzureRmApiManagementHostnameConfiguration
  - Set-AzureRmApiManagementHostnames
  - Update-AzureRmApiManagementDeployment
  - Import-AzureRmApiManagementHostnameCertificate
  - Gunakan cmdlet **Set-AzApiMenagement** untuk mengatur properti ini sebagai gantinya
- Menghapus properti berikut: 
  - Properti yang dihapus `PortalHostnameConfiguration`, `ProxyHostnameConfiguration`, `ManagementHostnameConfiguration`, dan `ScmHostnameConfiguration` pada jenis `PsApiManagementHostnameConfiguration` dari `PsApiManagementContext`. Sebagai gantinya gunakan `PortalCustomHostnameConfiguration`, `ProxyCustomHostnameConfiguration`, `ManagementCustomHostnameConfiguration`, dan `ScmCustomHostnameConfiguration` pada jenis `PsApiManagementCustomHostNameConfiguration`.
  - Menghapus properti `StaticIPs` dari PsApiManagementContext. Properti telah dibagi menjadi `PublicIPAddresses` dan `PrivateIPAddresses`.
  - Menghapus properti `Location` yang diperlukan dari cmdlet New-AzureApiManagementVirtualNetwork.

### <a name="azbilling-previously-azurermbilling-azurermconsumption-and-azurermusageaggregates"></a>Az.Billing (previously AzureRM.Billing, AzureRM.Consumption, and AzureRM.UsageAggregates)

- Parameter `InvoiceName` telah dihapus dari cmdlet `Get-AzConsumptionUsageDetail`.  Skrip perlu menggunakan parameter identitas lain untuk faktur.

### <a name="azcognitiveservices-previously-azurermcognitiveservices"></a>Az.CognitiveServices (previously AzureRM.CognitiveServices)

- Menghapus set parameter `GetSkusWithAccountParamSetName` dari cmdlet `Get-AzCognitiveServicesAccountSkus`  Anda harus mendapatkan Skus dengan Jenis Akun dan Lokasi, bukan menggunakan ResourceGroupName dan Nama Akun.

### <a name="azcompute-previously-azurermcompute"></a>Az.Compute (previously AzureRM.Compute)

- `IdentityIds` dihapus dari properti `Identity` di objek `PSVirtualMachine` dan `PSVirtualMachineScaleSet` Skrip tidak boleh lagi menggunakan nilai kolom ini untuk membuat keputusan pemrosesan.
- Jenis properti `InstanceView` objek `PSVirtualMachineScaleSetVM` diubah dari `VirtualMachineInstanceView` menjadi `VirtualMachineScaleSetVMInstanceView`
-               properti `AutoOSUpgradePolicy` dan `AutomaticOSUpgrade` dihapus dari properti `UpgradePolicy`
- Jenis properti `Sku` objek `PSSnapshotUpdate` diubah dari `DiskSku` menjadi `SnapshotSku`
- `VmScaleSetVMParameterSet` dihapus dari cmdlet `Add-AzVMDataDisk`, Anda tidak dapat lagi menambahkan disk data secara individual ke mesin virtual ScaleSet.

### <a name="azdatafactory-previously-azurermdatafactories-and-azurermdatafactoryv2"></a>Az.DataFactory (sebelumnya AzureRM.DataFactories dan AzureRM.DataFactoryV2)

- Parameter `GatewayName` telah menjadi wajib dalam cmdlet `New-AzDataFactoryEncryptValue`
- Menghapus cmdlet `New-AzDataFactoryGatewayKey`
- Menghapus parameter `LinkedServiceName` dari cmdlet `Get-AzDataFactoryV2ActivityRun`, Skrip tidak lagi menggunakan nilai bidang ini untuk membuat keputusan pemrosesan.

### <a name="azdatalakeanalytics-previously-azurermdatalakeanalytics"></a>Az.DataLakeAnalytics (previously AzureRM.DataLakeAnalytics)

- Menghapus cmdlet yang tidak digunakan lagi: `New-AzDataLakeAnalyticsCatalogSecret`, `Remove-AzDataLakeAnalyticsCatalogSecret`, dan `Set-AzDataLakeAnalyticsCatalogSecret`

### <a name="azdatalakestore-previously-azurermdatalakestore"></a>Az.DataLakeStore (previously AzureRM.DataLakeStore)

- Cmdlet berikut telah memiliki parameter `Encoding` yang diubah dari jenis `FileSystemCmdletProviderEncoding` menjadi `System.Text.Encoding`. Perubahan ini menghapus nilai pengodean `String` dan `Oem`. Semua nilai pengodean sebelumnya tetap ada.
  - New-AzureRmDataLakeStoreItem
  - Add-AzureRmDataLakeStoreItemContent
  - Get-AzureRmDataLakeStoreItemContent
- Menghapus alias properti `Tags` yang tidak digunakan lagi dari cmdlet `New-AzDataLakeStoreAccount` dan `Set-AzDataLakeStoreAccount`

  Skrip menggunakan
  ```azurepowershell-interactive
  New-AzureRMDataLakeStoreAccount -Tags @{TagName="TagValue"}
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  New-AzDataLakeStoreAccount -Tag @{TagName="TagValue"}
  ```

- Menghapus properti `Identity`, `EncryptionState`, `EncryptionProvisioningState`, `EncryptionConfig`, `FirewallState`, `FirewallRules`, `VirtualNetworkRules`, `TrustedIdProviderState`, `TrustedIdProviders`, `DefaultGroup`, `NewTier`, `CurrentTier`, `FirewallAllowAzureIps` yang tidak digunakan lagi dari objek `PSDataLakeStoreAccountBasic`.  Setiap skrip yang menggunakan `PSDatalakeStoreAccount` yang dikembalikan dari `Get-AzDataLakeStoreAccount` seharusnya tidak mereferensikan properti ini.

### <a name="azkeyvault-previously-azurermkeyvault"></a>Az.KeyVault (previously AzureRM.KeyVault)

- Properti `PurgeDisabled` telah dihapus dari objek `PSKeyVaultKeyAttributes`, `PSKeyVaultKeyIdentityItem`, dan `PSKeyVaultSecretAttributes` Skrip seharusnya tidak lagi merujuk properti ```PurgeDisabled``` untuk membuat keputusan pemrosesan.

### <a name="azmedia-previously-azurermmedia"></a>Az.Media (previously AzureRM.Media)

- Menghapus alias properti `Tags` yang tidak digunakan lagi dari cmdlet `New-AzMediaService` Skrip menggunakan
  ```azurepowershell-interactive
  New-AzureRMMediaService -Tags @{TagName="TagValue"}
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  New-AzMediaService -Tag @{TagName="TagValue"}
  ```

### <a name="azmonitor-previously-azurerminsights"></a>Az.Monitor (previously AzureRM.Insights)

- Menghapus parameter `Categories` dan `Timegrains` nama jamak sebagai ganti nama parameter tunggal dari cmdlet `Set-AzDiagnosticSetting` Skrip menggunakan
  ```azurepowershell-interactive
  Set-AzureRmDiagnosticSetting -Timegrains PT1M -Categories Category1, Category2
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  Set-AzDiagnosticSetting -Timegrain PT1M -Category Category1, Category2
  ```

### <a name="aznetwork-previously-azurermnetwork"></a>Az.Network (previously AzureRM.Network)

- Menghapus parameter `ResourceId` yang tidak digunakan lagi dari cmdlet `Get-AzServiceEndpointPolicyDefinition`
- Menghapus properti `EnableVmProtection` yang tidak digunakan lagi dari objek `PSVirtualNetwork`
- Menghapus cmdlet `Set-AzVirtualNetworkGatewayVpnClientConfig` yang tidak digunakan lagi

Skrip seharusnya tidak lagi membuat keputusan pemrosesan berdasarkan nilai-nilai di kolom ini.

### <a name="azoperationalinsights-previously-azurermoperationalinsights"></a>Az.OperationalInsights (previously AzureRM.OperationalInsights)

- Set parameter default untuk `Get-AzOperationalInsightsDataSource` dihapus, dan `ByWorkspaceNameByKind` menjadi set parameter default

  Skrip yang mencantumkan sumber data menggunakan
  ```azurepowershell-interactive
  Get-AzureRmOperationalInsightsDataSource
  ```

  Harus diubah untuk menentukan Jenis
  ```azurepowershell-interactive
  Get-AzOperationalInsightsDataSource -Kind AzureActivityLog
  ```

### <a name="azrecoveryservices-previously-azurermrecoveryservices-azurermrecoveryservicesbackup-and-azurermrecoveryservicessiterecovery"></a>Az.RecoveryServices (sebelumnya AzureRM.RecoveryServices, AzureRM.RecoveryServices.Backup, dan AzureRM.RecoveryServices.SiteRecovery)

- Menghapus parameter `Encryption` dari cmdlet `New/Set-AzRecoveryServicesAsrPolicy`
- Parameter `TargetStorageAccountName` kini wajib untuk pemulihan disk terkelola di cmdlet `Restore-AzRecoveryServicesBackupItem`
- Menghapus parameter `StorageAccountName` dan `StorageAccountResourceGroupName` dalam cmdlet `Restore-AzRecoveryServicesBackupItem`
- Menghapus parameter `Name` dalam cmdlet `Get-AzRecoveryServicesBackupContainer`

### <a name="azresources-previously-azurermresources"></a>Az.Resources (previously AzureRM.Resources)

- Menghapus parameter `Sku` dari cmdlet `New/Set-AzPolicyAssignment`
- Menghapus parameter `Password` dari cmdlet `New-AzADServicePrincipal` dan `New-AzADSpCredential` Kata sandi dibuat secara otomatis, skrip yang menyediakan kata sandinya:

  ```azurepowershell-interactive
  New-AzAdSpCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476 -Password $secPassword
  ```

  Harus diubah untuk mengambil kata sandi dari output:

  ```azurepowershell-interactive
  $credential = New-AzAdSpCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476
  $secPassword = $credential.Secret
  ```

### <a name="azservicefabric-previously-azurermservicefabric"></a>Az.ServiceFabric (previously AzureRM.ServiceFabric)

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

- Menghapus parameter `State` dan `ResourceId` dari cmdlet `Set-AzSqlDatabaseBackupLongTermRetentionPolicy`
- Menghapus cmdlet yang tidak digunakan lagi: `Get/Set-AzSqlServerBackupLongTermRetentionVault`, `Get/Start/Stop-AzSqlServerUpgrade`, `Get/Set-AzSqlDatabaseAuditingPolicy`, `Get/Set-AzSqlServerAuditingPolicy`, `Remove-AzSqlDatabaseAuditing`, `Remove-AzSqlServerAuditing`
- Menghapus parameter `Current` yang tidak digunakan lagi dari cmdlet `Get-AzSqlDatabaseBackupLongTermRetentionPolicy`
- Menghapus parameter `DatabaseName` yang tidak digunakan lagi dari cmdlet `Get-AzSqlServerServiceObjective`
- Menghapus parameter `PrivilegedLogin` yang tidak digunakan lagi dari cmdlet `Set-AzSqlDatabaseDataMaskingPolicy`

### <a name="azstorage-previously-azurestorage-and-azurermstorage"></a>Az.Storage (previously Azure.Storage and AzureRM.Storage)

- Untuk mendukung pembuatan konteks penyimpanan Oauth hanya dengan nama akun penyimpanan, kumpulan parameter default telah diubah menjadi `OAuthParameterSet`
  - Contoh: `$ctx = New-AzureStorageContext -StorageAccountName $accountName`
- Parameter `Location` telah menjadi wajib dalam cmdlet `Get-AzStorageUsage`
- Metode API Storage kini menggunakan Pola Asinkron Berbasis Tugas (TAP), bukan panggilan API sinkron. Contoh berikut menunjukkan perintah asinkron baru:

#### <a name="blob-snapshot"></a>Snapshot Blob

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

#### <a name="share-snapshot"></a>Berbagi Snapshot

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

#### <a name="undelete-soft-deleted-blob"></a>Membatalkan penghapusan blob yang dihapus sementara

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

#### <a name="set-blob-tier"></a>Mengatur tingkat blob

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

### <a name="azwebsites-previously-azurermwebsites"></a>Az.Websites (previously AzureRM.Websites)

- Menghapus properti yang tidak digunakan lagi dari objek `PSAppServicePlan`, `PSCertificate`, `PSCloningInfo`, dan `PSSite`
