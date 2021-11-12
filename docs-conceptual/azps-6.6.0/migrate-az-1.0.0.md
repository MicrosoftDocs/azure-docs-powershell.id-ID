---
title: Semua perubahan dari AzureRM ke Azure PowerShell Az 1.0.0
description: Panduan migrasi ini berisi daftar perubahan yang telah dibuat untuk Azure PowerShell di rilis Az versi 1.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 658e21f940f71c1aba9bd313062ba1e41435d437
ms.sourcegitcommit: b7ef209e489945ce397bbbba2c5f34fa6b2ca22e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429535"
---
# <a name="breaking-changes-for-az-100"></a>Memutus perubahan untuk Az 1.0.0

Dokumen ini menyediakan informasi mendetail tentang perubahan antara AzureRM 6.x dan modul Az baru, versi 1.x dan yang lebih baru. Daftar isi akan membantu memandu Anda melalui jalur migrasi lengkap, termasuk perubahan khusus modul yang mungkin memengaruhi skrip Anda.

Untuk saran umum tentang memulai migrasi dari AzureRM ke Az, lihat [Memulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).

> [!IMPORTANT]
> Ada perubahan antara Az 1.0.0 dan Az 2.0.0 juga. Setelah mengikuti panduan untuk memperbarui dari AzureRM ke Az, lihat perubahan terbaru [Az 2.0.0](migrate-az-2.0.0.md) untuk mengetahui jika Anda perlu membuat perubahan tambahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Perubahan umum yang tidak berubah](#general-breaking-changes)
  - [Perubahan prefiks kata benda cmdlet](#cmdlet-noun-prefix-changes)
  - [Perubahan nama modul](#module-name-changes)
  - [Modul yang dihapus](#removed-modules)
  - [Windows PowerShell 5.1 dan .NET 4.7.2](#windows-powershell-51-and-net-472)
  - [Penghapusan sementara pengguna masuk menggunakan PSCredential](#temporary-removal-of-user-login-using-pscredential)
  - [Kode perangkat default masuk, bukan perintah browser web](#default-device-code-login-instead-of-web-browser-prompt)
- [Perubahan pecah modul](#module-breaking-changes)
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

## <a name="general-breaking-changes"></a>Perubahan umum yang tidak berubah

Bagian ini menjelaskan perubahan umum yang menjadi bagian dari desain ulang modul Az.

### <a name="cmdlet-noun-prefix-changes"></a>Perubahan Prefiks Kata Benda Cmdlet

Dalam modul AzureRM, cmdlet menggunakan baik `AzureRM` atau `Azure` sebagai prefiks kata benda.  Az menyederhanakan dan menormalisasikan nama cmdlet, sehingga semua cmdlet menggunakan 'Az' sebagai prefiks kata benda cmdlet mereka. Misalnya:

```azurepowershell-interactive
Get-AzureRMVM
Get-AzureKeyVaultSecret
```

Telah berubah menjadi:

```azurepowershell-interactive
Get-AzVM
Get-AzKeyVaultSecret
```

Agar transisi ke nama cmdlet baru ini lebih sederhana, Az memperkenalkan dua cmdlet baru, [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) [dan Disable-AzureRmAlias.](/powershell/module/az.accounts/disable-azurermalias)  `Enable-AzureRmAlias` membuat alias untuk nama cmdlet yang lebih lama di AzureRM yang di map ke nama cmdlet Az yang lebih baru. Menggunakan `-Scope` argumen dengan `Enable-AzureRmAlias` memungkinkan Anda memilih di mana alias diaktifkan.

Misalnya, skrip berikut ini di AzureRM:

```azurepowershell-interactive
#Requires -Modules AzureRM.Storage
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

Dapat dijalankan dengan perubahan minimal `Enable-AzureRmAlias` menggunakan:

```azurepowershell-interactive
#Requires -Modules Az.Storage
Enable-AzureRmAlias -Scope Process
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

Menjalankan akan mengaktifkan alias untuk semua sesi PowerShell yang Anda buka, sehingga setelah menjalankan cmdlet ini, skrip seperti ini tidak perlu diubah `Enable-AzureRmAlias -Scope CurrentUser` sama sekali:

```azurepowershell-interactive
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

Untuk detail selengkapnya tentang penggunaan cmdlet alias, lihat referensi [Enable-AzureRmAlias.](/powershell/module/az.accounts/enable-azurermalias)

Ketika Anda siap untuk menonaktifkan alias, `Disable-AzureRmAlias` menghapus alias yang dibuat. Untuk detail selengkapnya, lihat [referensi Disable-AzureRmAlias](/powershell/module/az.accounts/disable-azurermalias).

> [!IMPORTANT]
> Ketika menonaktifkan alias, pastikan alias dinonaktifkan untuk _semua_ lingkup yang memiliki alias yang diaktifkan.

### <a name="module-name-changes"></a>Module Name Changes

Nama modul telah berubah dari `AzureRM.*` menjadi , kecuali modul berikut `Az.*` ini:

| Modul AzureRM | Modul Az |
|----------------|-----------|
| Azure. Storage | Az.Storage |
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

Perubahan dalam nama modul berarti bahwa skrip apa pun yang menggunakan atau memuat `#Requires` modul tertentu perlu diubah untuk menggunakan modul `Import-Module` baru. Untuk modul yang akhiran cmdlet belum berubah, hal ini berarti meskipun nama modul telah berubah, akhiran yang menunjukkan ruang operasi _belum_.

#### <a name="migrating-requires-and-import-module-statements"></a>Melakukan migrasi #Requires dan Import-Module Migrasi

Skrip yang menggunakan `#Requires` `Import-Module` atau mendeklarasikan dependensi pada modul AzureRM harus diperbarui untuk menggunakan nama modul baru. Misalnya:

```azurepowershell-interactive
#Requires -Module AzureRM.Compute
```

Harus diubah menjadi:

```azurepowershell-interactive
#Requires -Module Az.Compute
```

Untuk `Import-Module` :

```azurepowershell-interactive
Import-Module -Name AzureRM.Compute
```

Harus diubah menjadi:

```azurepowershell-interactive
Import-Module -Name Az.Compute
```

### <a name="migrating-fully-qualified-cmdlet-invocations"></a>Migrasi Fully-Qualified Cmdlet

Skrip yang menggunakan invokasi cmdlet yang memenuhi syarat modul, seperti:

```azurepowershell-interactive
AzureRM.Compute\Get-AzureRmVM
```

Harus diubah agar dapat menggunakan nama modul dan cmdlet baru:

```azurepowershell-interactive
Az.Compute\Get-AzVM
```

### <a name="migrating-module-manifest-dependencies"></a>Migrasi dependensi manifes modul

Modul yang menyatakan dependensi pada modul AzureRM melalui file manifes modul (.psd1) harus memperbarui nama modul di `RequiredModules` bagiannya:

```powershell
RequiredModules = @(@{ModuleName="AzureRM.Profile"; ModuleVersion="5.8.2"})
```

Harus diubah menjadi:

```powershell
RequiredModules = @(@{ModuleName="Az.Profile"; ModuleVersion="1.0.0"})
```

### <a name="removed-modules"></a>Modul yang dihapus

Modul berikut ini telah dihapus:

- `AzureRM.Backup`
- `AzureRM.Compute.ManagedService`
- `AzureRM.Scheduler`

Alat untuk layanan ini tidak lagi didukung secara aktif.  Pelanggan didorong untuk beralih ke layanan alternatif segera setelah memudahkan.

### <a name="windows-powershell-51-and-net-472"></a>Windows PowerShell 5.1 dan .NET 4.7.2

Menggunakan Az dengan PowerShell 5.1 untuk Windows memerlukan instalasi .NET Framework 4.7.2. Menggunakan PowerShell Core 6.x atau yang lebih baru tidak memerlukan .NET Framework.

### <a name="temporary-removal-of-user-login-using-pscredential"></a>Penghapusan sementara pengguna masuk menggunakan PSCredential

Karena perubahan dalam aliran autentikasi untuk .NET Standard, kami menghapus sementara pengguna masuk melalui PSCredential. Kemampuan ini akan diperkenalkan kembali dalam rilis 15/1/2019 untuk PowerShell 5.1 untuk Windows. Ini dibahas secara detail dalam [masalah GitHub ini.](https://github.com/Azure/azure-powershell/issues/7430)

### <a name="default-device-code-login-instead-of-web-browser-prompt"></a>Kode perangkat default masuk, bukan perintah browser web

Karena perubahan dalam aliran autentikasi untuk .NET Standard, kami menggunakan masuk perangkat sebagai alur masuk default selama masuk interaktif. Login berbasis browser web akan diperkenalkan kembali untuk PowerShell 5.1, Windows sebagai default dalam rilis 15/1/2019. Pada saat itu, pengguna akan dapat memilih perangkat masuk menggunakan parameter Alihkan.

## <a name="module-breaking-changes"></a>Perubahan pecah modul

Bagian ini menjelaskan perubahan khusus untuk modul dan cmdlet individual.

### <a name="azapimanagement-previously-azurermapimanagement"></a>Az.ApiManagement (sebelumnya AzureRM.ApiManagement)

- Hapus cmdlet berikut:
  - New-AzureRmApiManagementHostnameConfiguration
  - Set-AzureRmApiManagementHostnames
  - Update-AzureRmApiManagementDeployment
  - Import-AzureRmApiManagementHostnameCertificate
  - Gunakan cmdlet **Set-AzApiManagement** untuk mengatur properti ini sebagai gantinya
- Menghapus properti berikut ini:
  - Properti yang `PortalHostnameConfiguration` `ProxyHostnameConfiguration` dihapus, , `ManagementHostnameConfiguration` dan tipe `ScmHostnameConfiguration` dari `PsApiManagementHostnameConfiguration` `PsApiManagementContext` . Sebagai `PortalCustomHostnameConfiguration` gantinya `ProxyCustomHostnameConfiguration` gunakan , , dan dari tipe `ManagementCustomHostnameConfiguration` `ScmCustomHostnameConfiguration` `PsApiManagementCustomHostNameConfiguration` .
  - Properti yang `StaticIPs` dihapus dari PsApiManagementContext. Properti telah dipisahkan menjadi `PublicIPAddresses` dan `PrivateIPAddresses` .
  - Properti yang diperlukan `Location` telah dihapus New-AzureApiManagementVirtualNetwork cmdlet.

### <a name="azbilling-previously-azurermbilling-azurermconsumption-and-azurermusageaggregates"></a>Az.Billing (sebelumnya AzureRM.Billing, AzureRM.Consumption, dan AzureRM.UsageAggregates)

- Parameter `InvoiceName` dihapus dari `Get-AzConsumptionUsageDetail` cmdlet.  Skrip perlu menggunakan parameter identitas lain untuk faktur.

### <a name="azcognitiveservices-previously-azurermcognitiveservices"></a>Az.CognitiveServices (sebelumnya AzureRM.CognitiveServices)

- Kumpulan `GetSkusWithAccountParamSetName` parameter yang dihapus dari `Get-AzCognitiveServicesAccountSkus` cmdlet.  Anda harus mendapatkan Skus dengan Tipe dan Lokasi Akun, dan bukan menggunakan ResourceGroupName dan Nama Akun.

### <a name="azcompute-previously-azurermcompute"></a>Az.Compute (sebelumnya AzureRM.Compute)

- `IdentityIds` dihapus dari `Identity` properti dalam dan objek Skrip tidak boleh lagi menggunakan nilai bidang ini untuk membuat keputusan `PSVirtualMachine` `PSVirtualMachineScaleSet` pemrosesan.
- Tipe `InstanceView` properti objek diubah dari `PSVirtualMachineScaleSetVM` `VirtualMachineInstanceView` menjadi `VirtualMachineScaleSetVMInstanceView`
- `AutoOSUpgradePolicy` dan `AutomaticOSUpgrade` properti dihapus dari `UpgradePolicy` properti
- Tipe properti `Sku` dalam objek diubah dari `PSSnapshotUpdate` `DiskSku` menjadi `SnapshotSku`
- `VmScaleSetVMParameterSet` dihapus dari `Add-AzVMDataDisk` cmdlet, Anda tidak dapat lagi menambahkan disk data satu per satu ke ScaleSet VM.

### <a name="azdatafactory-previously-azurermdatafactories-and-azurermdatafactoryv2"></a>Az.DataFactory (sebelumnya AzureRM.DataFactories dan AzureRM.DataFactoryV2)

- Parameter `GatewayName` ini telah menjadi wajib di `New-AzDataFactoryEncryptValue` cmdlet
- Cmdlet `New-AzDataFactoryGatewayKey` yang dihapus
- Parameter `LinkedServiceName` yang dihapus dari skrip cmdlet tidak boleh menggunakan nilai bidang ini lagi untuk membuat keputusan `Get-AzDataFactoryV2ActivityRun` pemrosesan.

### <a name="azdatalakeanalytics-previously-azurermdatalakeanalytics"></a>Az.DataLakeAnalytics (sebelumnya AzureRM.DataLakeAnalytics)

- Cmdlets yang dihapus: `New-AzDataLakeAnalyticsCatalogSecret` , `Remove-AzDataLakeAnalyticsCatalogSecret` , dan `Set-AzDataLakeAnalyticsCatalogSecret`

### <a name="azdatalakestore-previously-azurermdatalakestore"></a>Az.DataLakeStore (sebelumnya AzureRM.DataLakeStore)

- Cmdlet berikut ini memiliki parameter `Encoding` yang berubah dari tipe menjadi `FileSystemCmdletProviderEncoding` `System.Text.Encoding` . Perubahan ini menghapus nilai pengodean `String` dan `Oem` . Semua nilai pengodean sebelumnya lainnya tetap ada.
  - New-AzureRmDataLakeStoreItem
  - Add-AzureRmDataLakeStoreItemContent
  - Get-AzureRmDataLakeStoreItemContent
- Menghapus alias properti `Tags` yang tidak berlaku lagi dari dan `New-AzDataLakeStoreAccount` `Set-AzDataLakeStoreAccount` cmdlet

  Skrip menggunakan
  ```azurepowershell-interactive
  New-AzureRMDataLakeStoreAccount -Tags @{TagName="TagValue"}
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  New-AzDataLakeStoreAccount -Tag @{TagName="TagValue"}
  ```

- Properti yang sudah tidak berlaku `Identity` lagi , , , , , , , `EncryptionState` , , `EncryptionProvisioningState` , , `EncryptionConfig` dari `FirewallState` `FirewallRules` `VirtualNetworkRules` `TrustedIdProviderState` `TrustedIdProviders` `DefaultGroup` `NewTier` `CurrentTier` `FirewallAllowAzureIps` `PSDataLakeStoreAccountBasic` objek.  Skrip apa pun yang menggunakan `PSDatalakeStoreAccount` hasil dari seharusnya tidak `Get-AzDataLakeStoreAccount` mereferensikan properti ini.

### <a name="azkeyvault-previously-azurermkeyvault"></a>Az.KeyVault (sebelumnya AzureRM.KeyVault)

- Properti `PurgeDisabled` dihapus dari Skrip , , dan objek seharusnya tidak lagi merujuk properti untuk membuat keputusan `PSKeyVaultKeyAttributes` `PSKeyVaultKeyIdentityItem` `PSKeyVaultSecretAttributes` ```PurgeDisabled``` pemrosesan.

### <a name="azmedia-previously-azurermmedia"></a>Az.Media (sebelumnya AzureRM.Media)

- Menghapus alias properti yang `Tags` sudah tidak berlaku dari skrip cmdlet `New-AzMediaService` menggunakan
  ```azurepowershell-interactive
  New-AzureRMMediaService -Tags @{TagName="TagValue"}
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  New-AzMediaService -Tag @{TagName="TagValue"}
  ```

### <a name="azmonitor-previously-azurerminsights"></a>Az.Monitor (sebelumnya AzureRM.Insights)

- Menghapus nama dan `Categories` `Timegrains` parameter bentuk jamak untuk mendukung nama parameter singular dari `Set-AzDiagnosticSetting` Skrip cmdlet menggunakan
  ```azurepowershell-interactive
  Set-AzureRmDiagnosticSetting -Timegrains PT1M -Categories Category1, Category2
  ```

  Harus diubah menjadi
  ```azurepowershell-interactive
  Set-AzDiagnosticSetting -Timegrain PT1M -Category Category1, Category2
  ```

### <a name="aznetwork-previously-azurermnetwork"></a>Az.Network (sebelumnya AzureRM.Network)

- Menghapus parameter yang sudah `ResourceId` tidak berlaku dari `Get-AzServiceEndpointPolicyDefinition` cmdlet
- Properti yang dihapus dari `EnableVmProtection` `PSVirtualNetwork` objek
- Cmdlet yang dihapus yang `Set-AzVirtualNetworkGatewayVpnClientConfig` tidak lagi dipakai

Skrip tidak boleh lagi membuat keputusan pemrosesan berdasarkan nilai bidang ini.

### <a name="azoperationalinsights-previously-azurermoperationalinsights"></a>Az.OperationalInsights (sebelumnya AzureRM.OperationalInsights)

- Kumpulan parameter default `Get-AzOperationalInsightsDataSource` untuk dihapus, `ByWorkspaceNameByKind` dan telah menjadi kumpulan parameter default

  Skrip yang mencantumkan sumber data menggunakan
  ```azurepowershell-interactive
  Get-AzureRmOperationalInsightsDataSource
  ```

  Harus diubah untuk menentukan Jenis
  ```azurepowershell-interactive
  Get-AzOperationalInsightsDataSource -Kind AzureActivityLog
  ```

### <a name="azrecoveryservices-previously-azurermrecoveryservices-azurermrecoveryservicesbackup-and-azurermrecoveryservicessiterecovery"></a>Az.RecoveryServices (sebelumnya AzureRM.RecoveryServices, AzureRM.RecoveryServices.Backup, dan AzureRM.RecoveryServices.SiteRecovery)

- Parameter `Encryption` yang dihapus dari `New/Set-AzRecoveryServicesAsrPolicy` cmdlet
- `TargetStorageAccountName` parameter sekarang wajib untuk pemulihan disk terkelola dalam `Restore-AzRecoveryServicesBackupItem` cmdlet
- Parameter `StorageAccountName` dan yang dihapus dalam `StorageAccountResourceGroupName` `Restore-AzRecoveryServicesBackupItem` cmdlet
- Parameter `Name` yang dihapus dalam `Get-AzRecoveryServicesBackupContainer` cmdlet

### <a name="azresources-previously-azurermresources"></a>Az.Resources (sebelumnya AzureRM.Resources)

- Parameter `Sku` yang dihapus dari `New/Set-AzPolicyAssignment` cmdlet
- Parameter `Password` yang dihapus dari dan kata sandi cmdlet secara otomatis `New-AzADServicePrincipal` `New-AzADSpCredential` dihasilkan, skrip yang menyediakan kata sandi:

  ```azurepowershell-interactive
  New-AzAdSpCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476 -Password $secPassword
  ```

  Harus diubah untuk mengambil kata sandi dari output:

  ```azurepowershell-interactive
  $credential = New-AzAdSpCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476
  $secPassword = $credential.Secret
  ```

### <a name="azservicefabric-previously-azurermservicefabric"></a>Az.ServiceFabric (sebelumnya AzureRM.ServiceFabric)

- Tipe pengembalian cmdlet berikut ini telah diubah:
  - Properti `ServiceTypeHealthPolicies` tipe `ApplicationHealthPolicy` telah dihapus.
  - Properti `ApplicationHealthPolicies` tipe `ClusterUpgradeDeltaHealthPolicy` telah dihapus.
  - Properti `OverrideUserUpgradePolicy` tipe `ClusterUpgradePolicy` telah dihapus.
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

- Parameter `State` dan yang dihapus dari `ResourceId` `Set-AzSqlDatabaseBackupLongTermRetentionPolicy` cmdlet
- Cmdlets yang dihapus: `Get/Set-AzSqlServerBackupLongTermRetentionVault` , `Get/Start/Stop-AzSqlServerUpgrade` , , , `Get/Set-AzSqlDatabaseAuditingPolicy` `Get/Set-AzSqlServerAuditingPolicy` `Remove-AzSqlDatabaseAuditing` , `Remove-AzSqlServerAuditing`
- Menghapus parameter yang sudah tidak berlaku `Current` dari `Get-AzSqlDatabaseBackupLongTermRetentionPolicy` cmdlet
- Menghapus parameter yang sudah tidak berlaku `DatabaseName` dari `Get-AzSqlServerServiceObjective` cmdlet
- Menghapus parameter yang sudah tidak berlaku `PrivilegedLogin` dari `Set-AzSqlDatabaseDataMaskingPolicy` cmdlet

### <a name="azstorage-previously-azurestorage-and-azurermstorage"></a>Az.Storage (sebelumnya Azure.Storage dan AzureRM.Storage)

- Untuk mendukung pembuatan konteks penyimpanan Oauth hanya dengan nama akun penyimpanan, kumpulan parameter default telah diubah menjadi `OAuthParameterSet`
  - Contoh: `$ctx = New-AzureStorageContext -StorageAccountName $accountName`
- Parameter `Location` ini telah menjadi wajib di `Get-AzStorageUsage` cmdlet
- Metode Storage API sekarang menggunakan Pola Asinkron Berbasis Tugas (TAP), bukan panggilan API sinkron. Contoh berikut memperlihatkan perintah asinkron baru:

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

#### <a name="set-blob-tier"></a>Set Blob Tier

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

- Properti yang sudah tidak berlaku dari `PSAppServicePlan` objek , , , `PSCertificate` `PSCloningInfo` dan `PSSite`
