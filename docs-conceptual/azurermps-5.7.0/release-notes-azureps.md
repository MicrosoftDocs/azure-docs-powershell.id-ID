---
title: Log Perubahan Azure PowerShell
description: Ini adalah sejarah perubahan yang dibuat untuk Azure PowerShell dalam rilis terbaru.
ms.devlang: powershell
ms.topic: conceptual
ms.workload: ''
ms.date: 2/20/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: a5fe155159f4e170872b80a982099b3fb5366751
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427395"
---
# <a name="azure-powershell-release-notes"></a>Catatan rilis Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Ini adalah daftar perubahan yang dibuat untuk Azure PowerShell dalam rilis ini.

---

## <a name="azure-powershell-570"></a>Azure PowerShell 5.7.0

Penginstal Azure PowerShell 5.7.0: [tautan](https://github.com/Azure/azure-powershell/releases/download/v5.7.0-April2018/azure-powershell.5.7.0.msi)

Modul Galeri Cmdlet ARM: [tautan](https://www.powershellgallery.com/packages/AzureRM/5.7.0)

Untuk menginstal `AzureRM` dari Galeri PowerShell, jalankan perintah berikut:

```powershell-interactive
Install-Module -Name AzureRM -Repository PSGallery -Force
```

Untuk memperbarui `AzureRM` dari versi lama, jalankan perintah berikut:

```powershell-interactive
Update-Module -Name AzureRM
```

### <a name="changes-since-last-release"></a>Perubahan Sejak Rilis Terakhir

#### <a name="general"></a>Umum
* Diperbarui ke versi terbaru Azure ClientRuntime

#### <a name="azurestorage"></a>Azure.Storage
* Memperbaiki masalah kegagalan dalam mengunggah cmdlet Blob dan mengunggah cmdlet file pada komputer yang mendukung kebijakan FIPS
    - Set-AzureStorageBlobContent
    - Set-AzureStorageFileContent

#### <a name="azurermbilling"></a>AzureRM.Billing
* Cmdlet Baru Get-AzureRmEnrollmentAccount
  - cmdlet untuk mengambil akun pendaftaran

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Integrasikan dengan SDK Manajemen Cognitive Services versi 4.0.0.
* Tambahkan operasi Get-AzureRmCognitiveServicesAccountUsage.

#### <a name="azurermcompute"></a>AzureRM.Compute
* `Get-AzureRmVmssDiskEncryptionStatus` mendukung status enkripsi di tingkat disk data
* `Get-AzureRmVmssVmDiskEncryptionStatus` mendukung status enkripsi di tingkat disk data
* Memperbarui Zona Ketangguhan
* Zona ketersediaan dukungan 'New-AzureRmVm' dan 'New-AzureRmVmss' (set parameter sederhana).

#### <a name="azurermcontainerregistry"></a>AzureRM.ContainerRegistry
* Memisahkan ketergantungan pada Commands.Resources.Rest dan ARM/Storage SDK.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Menambahkan fungsionalitas debug
* Memperbarui SDK dataplane ADLS ke versi 1.1.2
* Export-AzureRmDataLakeStoreItem - Parameter yang tidak digunakan lagi PerFileThreadCount, ConcurrentFileCount dan memperkenalkan parameter Konkurensi
* Import-AzureRMDataLakeStoreItem - Parameter yang tidak digunakan lagi PerFileThreadCount, ConcurrentFileCount dan memperkenalkan parameter Konkurensi
* Get-AzureRMDataLakeStoreItemContent - Memperbaiki perilaku tail untuk konten yang lebih besar dari 4MB
* Set-AzureRMDataLakeStoreItemExpiry - Memperkenalkan set parameter baru SetRelativeExpiry untuk mengatur waktu kedaluwarsa relatif
* Remove-AzureRmDataLakeStoreItem - Membersihkan parameter yang tidak digunakan lagi.

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Memperbaiki AlternameName di New-AzureRmEventHubGeoDRConfiguration

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Cmdlet yang diperbarui untuk menyertakan skenario penyaluran
* Menambahkan pesan penghentian untuk rilis perubahan yang berisiko selanjutnya

#### <a name="azurermnetwork"></a>AzureRM.Network
* Memperbaiki pesan kesalahan dengan cmdlet Jaringan

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan 'properti' di CorrelationFilter Aturan untuk mendukung customproperties
* memperbarui bantuan New-AzureRmServiceBusGeoDRConfiguration dan memperbaiki output cmdlet Aturan
* Memperbaiki properti pengalihan otomatis dalam cmdlet New-AzureRmServiceBusQueue dan New-AzureRmServiceBusSubscription

#### <a name="azurermsql"></a>AzureRM.Sql
* Menambahkan cmdlet baru 'Stop-AzureRmSqlElasticPoolActivity' untuk mendukung pembatalan operasi asinkron pada kumpulan elastis
* Memperbarui respons untuk cmdlet Get-AzureRmSqlDatabaseActivity dan Get-AzureRmSqlElasticPoolActivity guna memberikan lebih banyak informasi dalam respons

Perubahan sejak rilis terakhir: https://github.com/Azure/azure-powershell/compare/v5.6.0-March2018...v5.7.0-April2018

## <a name="560---march-2018"></a>5.6.0 - Maret 2018

#### <a name="general"></a>Umum
* Memperbaiki masalah terkait Grup Sumber Daya Default di CloudShell
* Memperbaiki masalah di mana skrip startup yang salah dijalankan selama impor modul

#### <a name="azurermprofile"></a>AzureRM.Profile
* Mengaktifkan autentikasi MSI dalam skenario yang tidak didukung
* Menambahkan dukungan untuk Identitas Layanan Terkelola yang ditentukan pengguna

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Memperbaiki masalah dengan menghapus skrip di build

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Memperbaiki masalah dengan menghapus skrip di build

#### <a name="azurermcompute"></a>AzureRM.Compute
* 'New-AzureRmVM' dan 'New-AzureRmVMSS' mendukung disk data.
* 'New-AzureRmVM' dan 'New-AzureRmVMSS' mendukung gambar kustom berdasarkan nama atau id.
* Fitur analitik log
    - Menambahkan cmdlet 'Export-AzureRmLogAnalyticRequestRateByInterval'
    - Menambahkan cmdlet 'Export-AzureRmLogAnalyticThrottledRequests'

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Memperbaiki masalah set parameter untuk registri kontainer dan pemasangan volume file azure

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui ADF .Net SDK ke pratinjau versi 0.6.0 yang berisi perubahan berikut:
    - Menambahkan Aktivitas AzureDatabricks LinkedService dan DatabricksNotebook baru
    - Menambahkan properti headNodeSize dan dataNodeSize di HDInsightOnDemand LinkedService
    - Menambahkan LinkedService, Dataset, CopySource untuk SalesforceMarketingCloud
    - Menambahkan dukungan untuk SecureOutput di semua aktivitas
    - Menambahkan properti BatchCount baru pada aktivitas ForEach yang mengontrol berapa banyak aktivitas bersamaan yang harus dijalankan
    - Menambahkan Aktivitas Filter baru
    - Menambahkan dukungan Parameter Layanan Tertaut

#### <a name="azurermdns"></a>AzureRM.Dns
* Dukungan untuk Zona DNS Privat (Pratinjau Publik)
    - Menambahkan kemampuan untuk membuat zona DNS yang hanya terlihat oleh jaringan virtual terkait

#### <a name="azurermnetwork"></a>AzureRM.Network
* Memperbarui jenis model untuk kompatibilitas dengan cmdlet DNS.

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Perubahan untuk ASR Azure ke Azure Site Recovery (cmdlet saat ini mendukung operasi untuk Enterprise ke Enterprise, Enterprise ke Azure, HyperV ke Azure, VMware ke Azure)
    - New-AzureRmRecoveryServicesAsrProtectionContainer
    - New-AzureRmRecoveryServicesAsrAzureToAzureDiskReplicationConfig
    - Remove-AzureRmRecoveryServicesAsrProtectionContainer
    - Update-AzureRmRecoveryServicesAsrProtectionDirection

#### <a name="azurermstorage"></a>AzureRM.Storage
* Parameter berikut kedaluwarsa di cmdlet Akun Penyimpanan baru dan yang telat diatur: EnableEncryptionService dan DisableEncryptionService, karena Enkripsi saat Istirahat diaktifkan secara default dan tidak dapat dinonaktifkan.
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Memperbaiki bantuan untuk Remove-AzureRmWebAppSlot

## <a name="550---march-2018"></a>5.5.0 - Maret 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbaiki masalah terkait pengimporan alias
* Muat Newtonsoft.Json versi 10.0.3 bersamaan dengan versi 6.0.8

#### <a name="azurestorage"></a>Azure.Storage
* Mendukung fitur Penghapusan Sementara
    - Enable-AzureStorageDeleteRetentionPolicy
    - Disable-AzureStorageDeleteRetentionPolicy
    - Get-AzureStorageBlob

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Memperbaiki masalah terkait pengimporan alias
* Tambahkan dukungan fitur firewall dan penabahan kueri, serta dukungan versi api 01-08-2017.

#### <a name="azurermautomation"></a>AzureRM.Automation
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Perbarui notice.txt dan pesan pemberitahuan.

#### <a name="azurermcompute"></a>AzureRM.Compute
* 'New-AzureRmVMSS' mencetak string koneksi dalam mode verbose.
* 'New-AzureRmVmss' mendukung alamat IP publik, aturan penyeimbangan beban, aturan NAT masuk.
* Fitur WriteAccelerator
    - Menambahkan parameter switch WriteAccelerator ke cmdlet berikut: Set-AzureRmVMOSDisk Set-AzureRmVMDataDisk Add-AzureRmVMDataDisk Add-AzureRmVmssDataDisk
    - Menambahkan parameter switch OsDiskWriteAccelerator ke cmdlet berikut:     Set-AzureRmVmssStorageProfile.
    - Menambahkan parameter Boolean OsDiskWriteAccelerator ke cmdlet berikut:     Update-AzureRmVM     Update-AzureRmVmss

#### <a name="azurermdatafactories"></a>AzureRM.DataFactories
* Memperbaiki masalah enkripsi info masuk yang tidak menyebabkan kesalahan berarti untuk beberapa operasi enkripsi
* Aktifkan runtime integrasi untuk dibagikan di seluruh pabrik data

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Tambahkan parameter "SetupScriptContainerSasUri" dan "Edition" untuk cmd "Set-AzureRmDataFactoryV2IntegrationRuntime" guna mengaktifkan pengaturan khusus dan fungsionalitas pemilihan edisi
* Memperbaiki masalah enkripsi info masuk yang tidak menyebabkan kesalahan berarti untuk beberapa operasi enkripsi.
* Aktifkan runtime integrasi untuk dibagikan di seluruh pabrik data

#### <a name="azurermhdinsight"></a>AzureRM.HDInsight
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Contoh tetap untuk Set-AzureRmKeyVaultAccessPolicy

#### <a name="azurermnetwork"></a>AzureRM.Network
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermrecoveryservices"></a>AzureRM.RecoveryServices
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah terkait pengimporan alias

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan properti EnableBatchedOperations ke Antrean
* Menambahkan properti DeadLetteringOnFilterEvaluationExceptions ke Langganan

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Refresh cmdlet Service Fabric
  - Templat ARM yang diperbarui
  - Operasi yang gagal tidak lagi di-rollback
  - Add-AzureRmServiceFabricNodeType
    - VM default untuk disk terkelola
    - Subnet VMSS yang ada digunakan
    - Semua operasi bersifat idempoten
  - Remove-AzureRmServiceFabricNodeType menghapus jenis VMSS dan/atau node cluster yang dibuat sebagian
  - Memperbaiki output objek PSCluster untuk jenis properti kompleks

#### <a name="azurermsql"></a>AzureRM.Sql
* Memperbaiki masalah terkait pengimporan alias
* Respons Get-AzureRmSqlServer, New-AzureRmSqlServer, dan Remove-AzureRmSqlServer sekarang menyertakan properti FullyQualifiedDomainName.

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Memperbaiki masalah terkait pengimporan alias
* New-AzureRMWebApp - menambahkan set parameter untuk pembuatan WebApp yang disederhanakan, dengan dukungan repositori git lokal.

## <a name="540---february-2018"></a>5.4.0 - Februari 2018
#### <a name="azurermautomation"></a>AzureRM.Automation
* Menambahkan alias dari New-AzureRmAutomationModule ke Import-AzureRmAutomationModule

#### <a name="azurermcompute"></a>AzureRM.Compute
* Perbaiki masalah ErrorAction untuk beberapa cmdlet Get.

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Terapkan SDK Instans Kontainer Azure 01-02-2018
    - Mendukung Label Nama DNS

#### <a name="azurermdevtestlabs"></a>AzureRM.DevTestLabs
* Memperbaiki semua cmdlet GET yang sebelumnya tidak berfungsi.

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Memperbaiki bug dalam bantuan Get-AzureRmEventHubGeoDRConfiguration

#### <a name="azurermnetwork"></a>AzureRM.Network
* Menambahkan cmdlet untuk membuat monitor koneksi baru
    - New-AzureRmNetworkWatcherConnectionMonitor
* Menambahkan cmdlet untuk memperbarui monitor koneksi
    - Set-AzureRmNetworkWatcherConnectionMonitor
* Menambahkan cmdlet untuk mendapatkan monitor koneksi atau daftar monitor koneksi
    - Get-AzureRmNetworkWatcherConnectionMonitor
* Menambahkan cmdlet ke monitor koneksi kueri
    - Get-AzureRmNetworkWatcherConnectionMonitorReport
* Menambahkan cmdlet untuk memulai monitor koneksi
    - Start-AzureRmNetworkWatcherConnectionMonitor
* Menambahkan cmdlet untuk menghentikan monitor koneksi
    - Stop-AzureRmNetworkWatcherConnectionMonitor
* Menambahkan cmdlet untuk menghapus monitor koneksi
    - Remove-AzureRmNetworkWatcherConnectionMonitor
* Memperbarui dokumentasi Set-AzureRmApplicationGatewayBackendAddressPool untuk menghapus contoh yang tidak digunakan lagi
* Menambahkan bendera EnableHttp2 ke Application Gateway
    - Memperbarui New-AzureRmApplicationGateway: Menambahkan parameter opsional -EnableHttp2
* Menambahkan Tag Ip ke PublicIpAddress
    - Memperbarui New-AzureRmPublicIpAddress: Menambahkan Tag Ip
    - New-AzureRmPublicIpTag untuk menambahkan Iptag
* Menambahkan properti DisableBgpRoutePropagation di RouteTable dan effectiveRoute.

#### <a name="azurermresources"></a>AzureRM.Resources
* Register-AzureRmProviderFeature: Menambahkan contoh yang hilang di dokumen
* Register-AzureRmResourceProvider: Menambahkan contoh yang hilang di dokumen

#### <a name="azurermstorage"></a>AzureRM.Storage
* Parameter berikut kedaluwarsa di cmdlet Akun Penyimpanan baru dan yang telat diatur: EnableEncryptionService dan DisableEncryptionService, karena Enkripsi saat Istirahat diaktifkan secara default dan tidak dapat dinonaktifkan.
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount


## <a name="530---february-2018"></a>5.3.0 - Februari 2018
### <a name="azurermprofile"></a>AzureRM.Profile
* Menambahkan peringatan penghentian untuk PowerShell 3 dan 4
* `Add-AzureRmAccount` telah diganti namanya menjadi `Connect-AzureRmAccount`; alias telah ditambahkan untuk nama cmdlet lama, dan alias lainnya (`Login-AzAccount` dan `Login-AzureRmAccount`) telah dialihkan ke nama cmdlet baru.
* `Remove-AzureRmAccount` telah diganti namanya menjadi `Disconnect-AzureRmAccount`; alias telah ditambahkan untuk nama cmdlet lama, dan alias lainnya (`Logout-AzAccount` dan `Logout-AzureRmAccount`) telah dialihkan ke nama cmdlet baru.
* Memperbaiki String Sumber Daya untuk menggunakan `Connect-AzureRmAccount` bukan `Login-AzureRmAccount`
* `Add-AzureRmEnvironment` dan `Set-AzureRmEnvironment`
  - Menambahkan `-AzureOperationalInsightsEndpoint` dan `-AzureOperationalInsightsEndpointResourceId` sebagai parameter untuk digunakan dengan RP data plane OperationalInsights.

### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Memperbaiki penggunaan `Login-AzureRmAccount` untuk menggunakan`Connect-AzureRmAccount`

### <a name="azurermcompute"></a>AzureRM.Compute
* Menambahkan parameter `-AvailabilitySetName` ke set parameter yang disederhanakan dari `New-AzureRmVM`.
* Memperbaiki penggunaan `Login-AzureRmAccount` untuk menggunakan`Connect-AzureRmAccount`
* Dukungan identitas yang ditetapkan pengguna untuk kumpulan skala VM dan VM
    - Parameter `-IdentityType` dan `-IdentityId` ditambahkan ke `New-AzureRmVMConfig`, `New-AzureRmVmssConfig`, `Update-AzureRmVM` dan `Update-AzureRmVmss`
* Menambahkan parameter `-EnableIPForwarding` ke `Add-AzureRmVmssNetworkInterfaceConfig`
* Menambahkan parameter `-Priority` ke `New-AzureRmVmssConfig`

### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Memperbaiki penggunaan `Login-AzureRmAccount` untuk menggunakan`Connect-AzureRmAccount`

### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Memperbaiki penggunaan `Login-AzureRmAccount` untuk menggunakan`Connect-AzureRmAccount`
* Memperbaiki pesan kesalahan `Test-AzureRmDataLakeStoreAccount` saat menjalankan cmdlet ini tanpa harus masuk dengan `Login-AzureRmAccount`

### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Diperbarui untuk menggunakan versi API 01-01-2018.

### <a name="azurermeventhub"></a>AzureRM.EventHub

* Tambahkan perintah baru di bawah untuk operasi Pemulihan Bencana Geo.
  - Membuat Alias baru (konfigurasi Pemulihan Bencana):
    - `New-AzureRmEventHubGeoDRConfiguration`
  - Ambil Alias (konfigurasi Pemulihan Bencana) :
    - `Get-AzureRmEventHubGeoDRConfiguration`
  - Menonaktifkan Pemulihan Bencana dan menghentikan replikasi perubahan dari namespace primer ke sekunder
    - `Set-AzureRmEventHubGeoDRConfigurationBreakPair`
  - Meminta failover Pemulihan Bencana dan mengonfigurasi ulang alias untuk mengarah ke namespace sekunder
    - `Set-AzureRmEventHubGeoDRConfigurationFailOver`
  - Menghapus Alias(konfigurasi Pemulihan Bencana)
    - `Remove-AzureRmEventHubGeoDRConfiguration`
* Tambahkan perintah baru di bawah untuk memeriksa Nama Namespace dan Nama Konfigurasi GeoDr - Ketersediaan alias.
  - Periksa Ketersediaan nama Namespace atau nama Alias (Konfigurasi Pemulihan Bencana):
    - `Test-AzureRmEventHubName`

### <a name="azurerminsights"></a>AzureRM.Insights
* Memperbaiki penggunaan `Login-AzureRmAccount` untuk menggunakan`Connect-AzureRmAccount`

### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbaiki penggunaan `Login-AzureRmAccount` untuk menggunakan`Connect-AzureRmAccount`

### <a name="azurermnetwork"></a>AzureRM.Network
* Memperbaiki pesan yang menimpa 'Apakah Anda yakin ingin overwriteresource'

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Menambahkan dukungan untuk kueri API V2 melalui `Invoke-AzureRmOperationalInsightsQuery`. Lihat [https://dev.loganalytics.io/](https://dev.loganalytics.io/) untuk info selengkapnya tentang API baru.

### <a name="azurermresources"></a>AzureRM.Resources
* `Get-AzureRmADServicePrincipal`: Menghapus`-ServicePrincipalName` dari set parameter Kosong default karena redundan dengan set parameter SPN

### <a name="azurermservicebus"></a>AzureRM.ServiceBus

* Menambahkan perbaikan fungsionalitas untuk `Remove-AzureRmServiceBusRule` dan `Get-AzureRmServiceBusKey`
* Menambahkan commandlet baru di bawah ini untuk operasi Pemulihan Bencana Geo.
  - Membuat Alias baru (konfigurasi Pemulihan Bencana):
    - `New-AzureRmServiceBusDRConfigurations`
  - Ambil Alias (konfigurasi Pemulihan Bencana) :
    - `Get-AzureRmServiceBusDRConfigurations`
  - Menonaktifkan Pemulihan Bencana dan menghentikan replikasi perubahan dari namespace primer ke sekunder
    - `Set-AzureRmServiceBusDRConfigurationsBreakPairing`
  - Meminta failover Pemulihan Bencana dan mengonfigurasi ulang alias untuk mengarah ke namespace sekunder
    - `Set-AzureRmServiceBusDRConfigurationsFailOver`
  - Menghapus Alias(konfigurasi Pemulihan Bencana)
    - `Remove-AzureRmServiceBusDRConfigurations`
* Memperbarui commandlet `Test-AzureRmServiceBusName` untuk mendukung Pemulihan Bencana Geo - Operasi ketersediaan pemeriksaan nama alias.
  - Periksa Ketersediaan nama Namespace atau nama Alias (Konfigurasi Pemulihan Bencana):
    - `Test-AzureRmServiceBusName`

### <a name="azurermusageaggregates"></a>AzureRM.UsageAggregates
* Memperbaiki penggunaan `Login-AzureRmAccount` untuk menggunakan`Connect-AzureRmAccount`

## <a name="520---january-2018"></a>5.2.0 - Januari 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Add-AzureRmAccount
  * Menambahkan -masuk MSI untuk autentikasi menggunakan info masuk Identitas Layanan Terkelola dari VM/Layanan saat ini
  * Memperbaiki Autentikasi KeyVault saat masuk dengan token akses yang disediakan pengguna

#### <a name="azurestorage"></a>Azure.Storage
* Menambahkan cmdlet untuk mendapatkan dan mengatur properti layanan Penyimpanan
    - Get-AzureStorageServiceProperty
    - Update-AzureStorageServiceProperty

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmApiManagementProperty, Set-AzureRmApiManagementProperty, dan New-AzureRmApiManagement

#### <a name="azurermapplicationinsights"></a>AzureRM.ApplicationInsights
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermautomation"></a>AzureRM.Automation
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag Set-AzureRmAutomationRunbook

#### <a name="azurermbackup"></a>AzureRM.Backup
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermbatch"></a>AzureRM.Batch
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmCdnEndpoint dan New-AzureRmCdnProfile

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Integrasikan dengan SDK Manajemen Cognitive Services versi 3.0.0.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Menambahkan set parameter sederhana ke New-AzureRmVmss, yang dapat membuat Set Skala Mesin Virtual dan semua sumber daya yang diperlukan menggunakan default cerdas
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmVm dan Update-AzureRmVm
* Memperbaiki cmdlet Get-AzureRmComputeResourceSku saat Zone disertakan dalam pembatasan.
* Perbarui skema konfigurasi Agen Diagnostik untuk dukungan sink Azure Monitor.

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermcontainerregistry"></a>AzureRM.ContainerRegistry
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermdatafactories"></a>AzureRM.DataFactories
* Mengaktifkan dukungan Azure Key Vault untuk semua layanan tertaut penyimpanan data
* Menambahkan properti jenis lisensi untuk runtime integrasi Azure SSIS
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmDataFactory

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Mengaktifkan dukungan Azure Key Vault untuk semua layanan tertaut penyimpanan data
* Menambahkan properti jenis lisensi untuk runtime integrasi Azure SSIS
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tambahkan parameter "LicenseType" untuk cmd "Set-AzureRmDataFactoryV2IntegrationRuntime" guna mengaktifkan fungsionalitas AHUB

#### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmDataLakeAnalyticsAccount dan Set-AzureRmDataLakeAnalyticsAccount

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmDataLakeStoreAccount dan Set-AzureRmDataLakeStoreAccount

#### <a name="azurermdevtestlabs"></a>AzureRM.DevTestLabs
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermdns"></a>AzureRM.Dns
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Tambahkan cmdlet baru berikut:
  - Update-AzureRmEventGridSubscription
    - Perbarui properti langganan peristiwa Event Grid.
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermhdinsight"></a>AzureRM.HDInsight
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurerminsights"></a>AzureRM.Insights
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermiothub"></a>AzureRM.IotHub
* Menambahkan dukungan Sertifikat untuk cmdlet IoTHub
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tambahkan-Dukungan AsJob untuk cmdlet KeyVault yang sudah berjalan lama. Memungkinkan cmdlet yang dipilih untuk berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
  * Cmdlet yang terpengaruh adalah: Remove-AzureRmKeyVault
* Memperbaiki bug di Set-AzureRmKeyVaultAccessPolicy di mana filter AAD mengatur SPN ke UPN yang disediakan, bukan mengatur UPN
  - Lihat masalah berikut untuk informasi lebih lanjut: https://github.com/Azure/azure-powershell/issues/5201

#### <a name="azurermlogicapp"></a>AzureRM.LogicApp
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermmachinelearning"></a>AzureRM.MachineLearning
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag Update-AzureRmMlCommitmentPlan

#### <a name="azurermmachinelearningcompute"></a>AzureRM.MachineLearningCompute
* Menambahkan parameter IncludeAllResources ke cmdlet Remove-AzureRmMlOpCluster
  - Menggunakan parameter switch ini akan menghapus semua sumber daya yang dibuat dengan kluster awalnya
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermmedia"></a>AzureRM.Media
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag Set-AzureRmMediaService dan New-AzureRmMediaService

#### <a name="azurermnetwork"></a>AzureRM.Network
* Menambahkan -Dukungan AsJob untuk cmdlet Jaringan yang sudah berjalan lama. Memungkinkan cmdlet yang dipilih untuk berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermnotificationhubs"></a>AzureRM.NotificationHubs
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmNotificationHubsNamespace dan Set-AzureRmNotificationHubsNamespace

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -New-AzureRmOperationalInsightsSavedSearch, Set-AzureRmOperationalInsightsSavedSearch, New-AzureRmOperationalInsightsWorkspace, dan Set-AzureRmOperationalInsightsWorkspace

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermrecoveryservices"></a>AzureRM.RecoveryServices
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Menambahkan -opsi UseOriginalStorageAccount ke cmdlet Restore-AzureRmRecoveryServicesBackupItem.
  - Mengaktifkan bendera ini menghasilkan pemulihan disk ke akun penyimpanan aslinya yang memungkinkan pengguna untuk mempertahankan konfigurasi VM yang dipulihkan semirip mungkin dengan VM asli.
  - Tindakan tersebut juga membantu dalam meningkatkan performa operasi pemulihan.

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Menambahkan  3 cmdlet baru untuk aturan firewall
* Menambahkan  3 cmdlet baru untuk replikasi geo
* Menambahkan dukungan untuk zona dan tag
* Jadikan ResourceGroup sebagai opsional bila memungkinkan.

#### <a name="azurermrelay"></a>AzureRM.Relay
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermresources"></a>AzureRM.Resources
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Menambahkan -Dukungan AsJob untuk cmdlet Sumber Daya yang sudah berjalan lama. Memungkinkan cmdlet yang dipilih untuk berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
* Menambahkan alias dari Get-AzureRmProviderOperation ke Get-AzureRmResourceProviderAction agar sesuai dengan konvensi penamaan

#### <a name="azurermscheduler"></a>AzureRM.Scheduler
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermservermanagement"></a>AzureRM.ServerManagement
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Tag-yang tidak digunakan mendukung -Tag New-AzureRmServerManagementNode dan New-AzureRmServerManagementGateway

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermsiterecovery"></a>AzureRM.SiteRecovery
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermsql"></a>AzureRM.Sql
* Memperbarui deskripsi parameter perintah Audit
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Menambahkan parameter -AsJob ke cmdlet yang sudah berjalan lama
* Parameter DatabaseName -yang tidak digunakan dalam Get-AzureRmSqlServiceObjective

#### <a name="azurermstorage"></a>AzureRM.Storage
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Memperbaiki masalah referensi null dalam menjalankan cmdlet New-AzureRMStorageAccount dengan parameter -EnableEncryptionService yang Tidak ada
* Menambahkan -Dukungan AsJob untuk cmdlet Storage yang sudah berjalan lama. Memungkinkan cmdlet yang dipilih untuk berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
    - Cmdlet yang terpengaruh adalah New-, Remove-, Add-, dan Update- untuk Akun Storage dan Aturan Jaringan Akun Storage.

#### <a name="azurermstreamanalytics"></a>AzureRM.StreamAnalytics
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Menambahkan Pelengkap Lokasi ke parameter -Lokasi memungkinkan penyelesaian tab melalui Lokasi yang valid
* Menambahkan Pelengkap ResourceGroup ke parameter -ResourceGroup memungkinkan penyelesaian tab melalui grup sumber daya dalam langganan saat ini
* Menambahkan -Dukungan AsJob untuk cmdlet Situs Web yang sudah berjalan lama. Memungkinkan cmdlet yang dipilih untuk berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
     - Cmdlet yang terpengaruh adalah New-, Remove-, Add-, dan Set- untuk WebApps, AppServicePlan dan Slot

## <a name="2017128-version-511"></a>2017.12.8 Versi 5.1.1
* AnalysisServices
  - Ubah validasi set lokasi menjadi pencarian dinamis sehingga semua cloud didukung.
* Automation
  - Memperbarui ke Import-AzureRMAutomationRunbook
    - Dukungan sekarang disediakan untuk runbook Python2
* Batch
  - Memperbaiki bug di mana operasi akun tanpa grup sumber daya gagal mendeteksi grup sumber daya secara otomatis
* Compute
  - Get-AzureRmComputeResourceSku menunjukkan informasi zona.
  - Memperbaiki Disable-AzureRmVmssDiskEncryption untuk memperbaiki masalah https://github.com/Azure/azure-powershell/issues/5038
  - Menambahkan -Dukungan AsJob untuk cmdlet Compute yang sudah berjalan lama. Memungkinkan cmdlet yang dipilih untuk berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
    - Cmdlet yang terpengaruh meliputi: cmdlet New-, Update-, Set-, Remove-, Start-, Restart-, Stop untuk Virtual Machines dan Virtual Machine Scale Sets
    - Menambahkan set parameter sederhana ke New-AzureRmVM, yang membuat Mesin Virtual dan semua sumber daya yang diperlukan menggunakan default cerdas
* ContainerInstance
  - Menerapkan SDK Instans Kontainer Azure 01-10-2017
    - Mendukung kontainer run-to-completion
    - Mendukung pemasangan volume File Azure
    - Mendukung pembukaan beberapa port untuk IP publik
* ContainerRegistry
  - Cmdlet baru untuk replikasi geo dan webhook
    - Get/New/Remove-AzureRmContainerRegistryReplication
    - Get/New/Remove/Test/Update-AzureRmContainerRegistryWebhook
* DataFactories
    - Fungsionalitas enkripsi info masuk sekarang berfungsi terhadap "Akses Jarak Jauh" yang diaktifkan (Over Network) dan "Akses Jarak Jauh" yang dinonaktifkan (KomputerLokal).
* DataFactoryV2
  - Menambahkan dua cmdlet baru: Update-AzureRmDataFactoryV2 dan Stop-AzureRmDataFactoryV2PipelineRun
* DataLakeAnalytics
  - Menambahkan parameter yang disebut ScriptParameter ke Submit-AzureRmDataLakeAnalyticsJob
    - Informasi terperinci tentang ScriptParameter dapat ditemukan menggunakan Get-Help di Submit-AzureRmDataLakeAnalyticsJob
  - Untuk New-AzureRmDataLakeAnalyticsAccount, mengubah parameter MaxDegreeOfParallelism menjadi MaxAnalyticsUnits
    - Menambahkan alias untuk parameter MaxAnalyticsUnits: MaxDegreeOfParallelism
  - Untuk New-AzureRmDataLakeAnalyticsComputePolicy, mengubah parameter MaxDegreeOfParallelismPerJob menjadi MaxAnalyticsUnitsPerJob
    - Menambahkan alias untuk parameter MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
  - Untuk Set-AzureRmDataLakeAnalyticsAccount, mengubah parameter MaxDegreeOfParallelism menjadi MaxAnalyticsUnits
    - Menambahkan alias untuk parameter MaxAnalyticsUnits: MaxDegreeOfParallelism
  - Untuk Submit-AzureRmDataLakeAnalyticsJob, mengubah parameter DegreeOfParallelism menjadi AnalyticsUnits
    - Menambahkan alias untuk parameter AnalyticsUnits: DegreeOfParallelism
  - Untuk Update-AzureRmDataLakeAnalyticsComputePolicy, mengubah parameter MaxDegreeOfParallelismPerJob menjadi MaxAnalyticsUnitsPerJob
    - Menambahkan alias untuk parameter MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
* MachineLearningCompute
  - Menambahkan Set-AzureRmMlOpCluster
    - Memperbarui jumlah agen kluster atau konfigurasi SSL
  - Properti orkestrator bersifat opsional
    - Layanan akan membuat perwakilan layanan jika tidak disediakan, sehingga properti orkestrator sekarang bersifat opsional
* PowerBIEmbedded
  - Menambahkan dukungan untuk cmdlet Kapasitas Power BI Embedded
  - Cmdlet baru Get-AzureRmPowerBIEmbeddedCapacity - Mendapatkan detail Kapasitas yang Tersematkan dalam PowerBI.
  - Cmdlet baru New-AzureRmPowerBIEmbeddedCapacity - Menciptakan Kapasitas yang Tersematkan dalam PowerBI baru
  - Cmdlet baru Remove-AzureRmPowerBIEmbeddedCapacity - Menghapus instans Kapasitas yang Tersematkan dalam PowerBI
  - Cmdlet baru Resume-AzureRmPowerBIEmbeddedCapacity - Melanjutkan instans Kapasitas yang Tersematkan dalam PowerBI
  - Cmdlet baru Suspend-AzureRmPowerBIEmbeddedCapacity - Menangguhkan instans Kapasitas yang Tersematkan dalam PowerBI
  - Cmdlet baru Test-AzureRmPowerBIEmbeddedCapacity - Menguji keberadaan instans Kapasitas yang Tersematkan dalam PowerBI
  - Cmdlet baru Update-AzureRmPowerBIEmbeddedCapacity - Memodifikasi instans Kapasitas yang Tersematkan dalam PowerBI
* Profil
  - Memperbarui USGovernmentActiveDirectoryEndpoint menjadi https://login.microsoftonline.us/
    - Untuk informasi selengkapnya tentang pemetaan titik akhir Azure Government, lihat [Pemetaan titik akhir](/azure/azure-government/documentation-government-developer-guide#endpoint-mapping)
    - Menambahkan -Dukungan AsJob untuk cmdlet, memungkinkan cmdlet yang dipilih untuk dijalankan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan
    - Menambahkan parameter -AsJob ke cmdlet Get-AzureRmSubscription
* RecoveryServices.Backup
  - Bug tetap - Get-AzureRmRecoveryServicesBackupItem harus melakukan perbandingan kasus yang tidak sensitif terhadap filter nama kontainer.
  - Bug tetap - AzureVmItem sekarang memiliki properti yang menunjukkan terakhir kali operasi pencadangan terjadi - LastBackupTime.
* Sumber
  - Memperbaiki masalah di mana Get-AzureRMRoleAssignment akan menghasilkan tugas tanpa nama roledefiniton untuk peran khusus
    - Pengguna sekarang dapat menggunakan Get-AzureRMRoleAssignment dengan tugas yang memiliki nama roledefinition terlepas dari jenis perannya
  - Memperbaiki masalah di mana Set-AzureRMRoleRoleDefinition digunakan untuk melempar kesalahan RD tidak ditemukan saat ada cakupan baru di assignablescopes
    - Pengguna sekarang dapat menggunakan Set-AzureRMRoleRoleDefinition dengan cakupan yang dapat ditetapkan termasuk cakupan baru terlepas dari posisi cakupan
  - Izinkan cakupan berakhir dengan "/"
    - Pengguna sekarang dapat menggunakan commandlet RoleDefinition dan RoleAssignment dengan cakupan yang diakhiri dengan "/", konsisten dengan API dan CLI
  - Mengizinkan pengguna membuat RoleAssignment menggunakan bendera delegasi
    - Pengguna sekarang dapat menggunakan New-AzureRMRoleAssignment dengan opsi penambahan bendera delegasi
  - Memperbaiki RoleAssignment Dapat menghormati parameter cakupan
  - Menambahkan alias untuk ServicePrincipalName di Commandlet New-AzureRmRoleAssignment
    - Pengguna sekarang dapat menggunakan ApplicationId, bukan ServicePrincipalName saat menggunakan commandlet New-AzureRmRoleAssignment
* SiteRecovery
  - Tambahkan peringatan penghentian untuk semua cmdlet di modul ini dalam persiapan untuk rilis perubahan yang berisiko berikutnya.
    - Silakan lihat panduan perubahan yang berisiko selanjutnya untuk informasi lebih lanjut tentang cara memigrasikan cmdlet Anda dari AzureRM.
* Sql
  - Menambahkan kemampuan untuk mengganti nama database menggunakan Set-AzureRmSqlDatabase
  - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/4974
    - Memberikan nilai AUDIT_CHANGED_GROUP yang tidak valid untuk mengaudit cmdlet tidak lagi menimbulkan kesalahan dan akan dihapus dalam rilis mendatang.
  - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/5046
    - Parameter AuditAction dalam mengaudit cmdlet tidak lagi diabaikan
  - Memperbaiki masalah di Cmdlet Audit saat StorageKeyType 'Sekunder' disediakan
    - Saat mengatur audit blob, kunci akun penyimpanan utama digunakan sebagai ganti kunci sekunder saat memberikan nilai 'Sekunder' untuk parameter StorageKeyType.
  - Mengubah kata-kata untuk pesan konfirmasi dari Set-AzureRmSqlServerTransparentDataEncryptionProtector
* Azure (RDFE)
    - Menghapus semua Cmdles RemoteApp
* Azure.Storage
    - Meningkatkan ke Pustaka Klien Azure Storage 8.6.0 dan Pustaka DataMovement Azure Storage 0.6.5

## <a name="20171110-version-501"></a>2017.11.10 Versi 5.0.1
* Memperbaiki masalah pemuatan perakitan yang menyebabkan beberapa cmdlet gagal saat melakukan eksekusi dalam modul berikut:
  - AzureRM.ApiManagement
  - AzureRM.Backup
  - AzureRM.Batch
  - AzureRM.Compute
  - AzureRM.DataFactories
  - AzureRM.HDInsight
  - AzureRM.KeyVault
  - AzureRM.RecoveryServices
  - AzureRM.RecoveryServices.Backup
  - AzureRM.RecoveryServices.SiteRecovery
  - AzureRM.RedisCache
  - AzureRM.SiteRecovery
  - AzureRM.Sql
  - AzureRM.Storage
  - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>2017.11.8 - Versi 5.0.0
* CATATAN: Ini adalah rilis perubahan yang berisiko. Silakan lihat panduan migrasi (https://aka.ms/azps-migration-guide) untuk daftar lengkap perubahan berisiko yang diperkenalkan.
* Semua cmdlet di AzureRM sekarang mendukung bantuan online
  - Jalankan Get-Help dengan parameter -Online untuk membuka bantuan online di browser Internet default Anda
* AnalysisServices
  * Perintah Synchronize-AzureAsInstance tetap berfungsi dengan ASAzure REST API baru untuk sinkronisasi
* ApiManagement
  * Silakan lihat panduan migrasi untuk perubahan berisiko yang dibuat pada ApiManagement rilis ini
  * Memperbarui Cmdlet Get-AzureRmApiManagementUser untuk memperbaiki masalah https://github.com/Azure/azure-powershell/issues/4510
  * Memperbarui Cmdlet New-AzureRmApiManagementApi untuk membuat Api dengan Jalur Kosong https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
  * Menambahkan perintah untuk mendapatkan/membuat/menghapus sumber daya insight aplikasi
    - Get-AzureRmApplicationInsights
    - New-AzureRmApplicationInsights
    - Remove-AzureRmApplicationInsights
  * Menambahkan perintah untuk mendapatkan/memperbarui harga/batas harian sumber daya insight aplikasi
    - Get-AzureRmApplicationInsights -IncludeDailyCap
    - Set-AzureRmApplicationInsightsPricingPlan
    - Set-AzureRmApplicationInsightsDailyCap
  * Menambahkan perintah untuk mendapatkan/membuat/memperbarui/menghapus ekspor berkelanjutan sumber daya insight aplikasi
    - Get-AzureRmApplicationInsightsContinuousExport
    - Set-AzureRmApplicationInsightsContinuousExport
    - New-AzureRmApplicationInsightsContinuousExport
    - Remove-AzureRmApplicationInsightsContinuousExport
  * Menambahkan perintah untuk mendapatkan/membuat/menghapus kunci api sumber daya insight aplikasi
    - Get-AzureRmApplicationInsightsApiKey
    - New-AzureRmApplicationInsightsApiKey
    - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
  * Tambahkan parameter baru ke `New-AzureRmBatchAccount`.
    - `PoolAllocationMode`: Mode alokasi yang digunakan untuk membuat kumpulan di akun Batch. Untuk membuat akun Batch yang mengalokasikan node kumpulan dalam langganan pengguna, atur ini ke `UserSubscription`.
    - `KeyVaultId`: ID sumber daya brankas kunci Azure yang terkait dengan akun Batch.
    - `KeyVaultUrl`: URL brankas kunci Azure yang terkait dengan akun Batch.
  * Parameter yang diperbarui ke `New-AzureBatchTask`.
    - Hapus switch `RunElevated`. Parameter `UserIdentity` telah ditambahkan untuk menggantikan `RunElevated`, dan perilaku yang setara dapat dicapai dengan membangun `PSUserIdentity` seperti yang ditunjukkan di bawah ini:
      - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
      - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
    - Menambahkan parameter `AuthenticationTokenSettings`. Parameter ini memungkinkan Anda untuk meminta layanan Batch memberikan token autentikasi ke tugas saat berjalan, menghindari kebutuhan untuk meneruskan kunci akun Batch ke tugas untuk mengeluarkan permintaan ke layanan Batch.
    - Tambahkan parameter `ContainerSettings`.
      - Parameter ini memungkinkan Anda untuk meminta layanan Batch menjalankan tugas di dalam kontainer.
    - Tambahkan parameter `OutputFiles`.
      - Parameter ini memungkinkan Anda untuk mengonfigurasi tugas guna mengunggah file ke Azure Storage setelah selesai.
  * Parameter yang diperbarui ke `New-AzureBatchPool`.
    - Tambahkan parameter `UserAccounts`.
      - Parameter ini menentukan akun pengguna yang dibuat pada setiap node di kumpulan.
    - Tambahkan `TargetLowPriorityComputeNodes` dan ganti nama `TargetDedicated` menjadi `TargetDedicatedComputeNodes`.
      - Alias `TargetDedicated` dibuat untuk parameter `TargetDedicatedComputeNodes`.
    - Tambahkan parameter `NetworkConfiguration`.
      - Parameter ini memungkinkan Anda untuk mengonfigurasi pengaturan jaringan kumpulan.
  * Parameter yang diperbarui ke `New-AzureBatchCertificate`.
    - Sekarang parameter `Password` adalah `SecureString`.
  * Parameter yang diperbarui ke `New-AzureBatchComputeNodeUser`.
    - Sekarang parameter `Password` adalah `SecureString`.
  * Parameter yang diperbarui ke `Set-AzureBatchComputeNodeUser`.
    - Sekarang parameter `Password` adalah `SecureString`.
  * Mengganti nama parameter `Name` menjadi `Path` pada `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent`, dan `Remove-AzureBatchNodeFile`.
    - Alias `Name` dibuat untuk parameter `Path`.
  * Perubahan pada objek
    - Silakan lihat log perubahan Batch untuk daftar lengkap
  * Tambahkan dukungan untuk autentikasi berbasis Azure Active Directory.
    - Untuk menggunakan autentikasi Azure Active Directory, ambil objek `BatchAccountContext` menggunakan cmdlet `Get-AzureRmBatchAccount`, dan suplai `BatchAccountContext` ini ke parameter `-BatchContext` cmdlet layanan Batch. Autentikasi Azure Active Directory wajib untuk akun dengan `PoolAllocationMode = UserSubscription`.
    - Untuk akun yang sudah ada atau untuk akun baru yang dibuat dengan `PoolAllocationMode = BatchService`, Anda dapat terus menggunakan autentikasi kunci bersama dengan mengambil objek `BatchAccountContext` menggunakan cmdlet `Get-AzureRmBatchAccoutKeys`.
* Compute
  * Perintah Ekstensi Azure Disk Encryption
    - Parameter Baru untuk 'Set-AzureRmVmDiskEncryptionExtension': '-EncryptFormatAll' mengenkripsi format disk data
    - Parameter Baru untuk 'Set-AzureRmVmDiskEncryptionExtension': '-ExtensionPublisherName' dan '-ExtensionType' memungkinkan beralih ke versi ekstensi lainnya
    - Parameter Baru untuk 'Disable-AzureRmVmDiskEncryption': '-ExtensionPublisherName' dan '-ExtensionType' memungkinkan beralih ke versi ekstensi lainnya
    - Parameter Baru untuk 'Get-AzureRmVmDiskEncryptionStatus': '-ExtensionPublisherName' dan '-ExtensionType' memungkinkan beralih ke versi ekstensi lainnya
* DataLakeAnalytics
  * Silakan lihat panduan migrasi untuk perubahan berisiko yang dibuat pada DataLakeAnalytics rilis ini
  * Mengubah salah satu dari dua OutputTypes Get-AzureRmDataLakeAnalyticsAccount
    - Mencantumkan \<DataLakeAnalyticsAccount> ke Daftar\<PSDataLakeAnalyticsAccountBasic>
    - Properti PSDataLakeAnalyticsAccountBasic adalah subset ketat properti DataLakeAnalyticsAccount
    - Properti tambahan yang ada di DataLakeAnalyticsAccount tidak dikembalikan oleh layanan.  Oleh karena itu, perubahan ini berfungsi untuk mencerminkan propeti ini secara akurat. Properti tambahan ini masih ada di PSDataLakeAnalyticsAccountBasic, tetapi ditandai sebagai Tidak digunakan.
  * Mengubah salah satu dari dua OutputTypes Get-AzureRmDataLakeAnalyticsJob
    - Mencantumkan \<JobInformation> ke Daftar\<PSJobInformationBasic>
    - Properti PSJobInformationBasic adalah subset ketat dari properti JobInformation
    - Properti tambahan yang ada di JobInformation tidak dikembalikan oleh layanan.  Oleh karena itu, perubahan ini berfungsi untuk mencerminkan propeti ini secara akurat. Properti tambahan ini masih ada di PSJobInformationBasic, tetapi ditandai sebagai Tidak digunakan.
* DataLakeStore
  * Silakan lihat panduan migrasi untuk perubahan berisiko yang dibuat pada DataLakeStore rilis ini
  * Mengubah salah satu dari dua OutputTypes Get-AzureRmDataLakeStoreAccount
    - Mencantumkan \<PSDataLakeStoreAccount> ke Daftar\<PSDataLakeStoreAccountBasic>
    - Properti PSDataLakeStoreAccountBasic merupakan subset ketat dari properti PSDataLakeStoreAccount
    - Properti tambahan yang ada di PSDataLakeStoreAccount tidak dikembalikan oleh layanan.  Oleh karena itu, perubahan ini berfungsi untuk mencerminkan propeti ini secara akurat. Properti tambahan ini masih ada di PSDataLakeStoreAccountBasic, tetapi ditandai sebagai Tidak digunakan.
* Dns
  * Dukungan untuk jenis rekaman CAA di Azure DNS
    - Mendukung semua operasi pada jenis rekaman CAA
* EventHub
  * Silakan lihat panduan migrasi untuk perubahan berisiko yang dibuat pada EventHub rilis ini
* Wawasan
  * Silakan lihat panduan migrasi untuk perubahan berisiko yang dibuat pada Insights rilis ini
* Jaringan
  * Silakan lihat panduan migrasi untuk perubahan berisiko yang dibuat pada Jaringan rilis ini
  * Menambahkan cmdlet ke daftar penyedia layanan internet yang tersedia untuk wilayah Azure tertentu
    - Get-AzureRmNetworkWatcherReachabilityProvidersList
  * Menambahkan cmdlet guna mendapatkan skor latensi relatif untuk penyedia layanan internet dari lokasi tertentu ke wilayah Azure
    - Get-AzureRmNetworkWatcherReachabilityReport
* Profil
  - Set-AzureRmDefault
    - Gunakan cmdlet ini untuk mengatur grup sumber daya default.  Ini akan membuat parameter -ResourceGroup bersifat opsional untuk beberapa cmdlet, dan akan menggunakan default ketika grup sumber daya tidak ditentukan
    - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
    - Jika grup sumber daya yang ditentukan ada di langganan, grup sumber daya ini akan diatur ke default.  Sebaliknya, grup sumber daya akan dibuat dan kemudian diatur ke default.
  - Get-AzureRmDefault
    - Gunakan cmdlet ini untuk mendapatkan grup sumber daya default saat ini (dan default lainnya di masa mendatang).
    - ```Get-AzureRmDefault -ResourceGroup```
  - Clear-AzureRmDefault
    - Gunakan cmdlet ini untuk menghapus grup sumber daya default saat ini
    - ```Clear-AzureRmDefault -ResourceGroup```
  - Add-AzureRmEnvironment dan Set-AzureRmEnvironment
    - Tambahkan parameter BatchAudience, yang memungkinkan Anda menentukan audiens Azure Batch Active Directory untuk digunakan saat memperoleh token autentikasi untuk layanan Batch.
* RecoveryServices.Backup
  * Tambahkan cmdlet untuk melakukan pemulihan file instan.
    - Get-AzureRmRecoveryServicesBackupRPMountScript
    - Disable-AzureRmRecoveryServicesBackupRPMountScript
  * Memperbarui versi RecoveryServices.Backup SDK ke yang terbaru
  * Pengujian yang diperbarui untuk beban kerja Azure VM hingga semua penyiapan yang diperlukan untuk uji coba dilakukan oleh pengujian itu sendiri.
  * Memperbaiki https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
  * Perubahan untuk ASR VMware ke Azure Site Recovery (cmdlet saat ini mendukung operasi untuk Enterprise ke Enterprise, Enterprise ke Azure, HyperV ke Azure)
    - New-AzureRmRecoveryServicesAsrPolicy
    - New-AzureRmRecoveryServicesAsrProtectedItem
    - Update-AzureRmRecoveryServicesAsrPolicy
    - Update-AzureRmRecoveryServicesAsrProtectionDirection
  * Menambahkan dukungan ke brankas berbasis AAD
  * Menambahkan cmdlet untuk mengelola sumber daya VCenter
    - Get-AzureRmRecoveryServicesAsrVCenter
    - New-AzureRmRecoveryServicesAsrVCenter
    - Remove-AzureRmRecoveryServicesAsrVCenter
    - Update-AzureRmRecoveryServicesAsrVCenter
  * Menambahkan cmdlet lainnya
    - Get-AzureRmRecoveryServicesAsrAlertSetting
    - Get-AzureRmRecoveryServicesAsrEvent
    - New-AzureRmRecoveryServicesAsrProtectableItem
    - Set-AzureRmRecoveryServicesAsrAlertSetting
    - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
    - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
    - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
    - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
  - Silakan lihat panduan migrasi untuk perubahan berisiko yang dibuat pada ServiceBus rilis ini
* Sql
  * Menambahkan dukungan untuk mendaftarkan dan membatalkan operasi pembaruan asinkron pada database
    - memperbarui cmdlet yang ada Get-AzureRmSqlDatabaseActivity untuk mengembalikan status operasi updateslo DB.
    - tambahkan cmdlet baru Stop-AzureRmSqlDatabaseActivity untuk membatalkan operasi pembaruan asinkron pada database.
  * Menambahkan dukungan untuk Redundansi Zona untuk database dan kumpulan elastis
    - Menambahkan parameter switch ZoneRedundant ke New-AzureRmSqlDatabase
    - Menambahkan parameter switch ZoneRedundant ke Set-AzureRmSqlDatabase
    - Menambahkan parameter switch ZoneRedundant ke New-AzureRmSqlElasticPool
    - Menambahkan parameter switch ZoneRedundant ke Set-AzureRmSqlElasticPool
  * Menambahkan dukungan untuk Alias DNS Server
    - Menambahkan cmdlet Get-AzureRmSqlServerDnsAlias yang mendapat alias dns server berdasarkan server dan nama alias atau daftar alias dns server untuk Azure SQL Server.
    - Menambahkan cmdlet New-AzureRmSqlServerDnsAlias yang membuat alias dns server baru untuk server Azure SQL tertentu
    - Menambahkan Set-AzurermSqlServerDnsAlias cmlet yang memungkinkan pembaruan Azure SQL Server yang ditunjukkan oleh alias dns server
    - Menambahkan cmdlet Remove-AzureRmSqlServerDnsAlias yang menghapus alias dns server untuk Azure SQL Server
* Azure.Storage
  * Tingkatkan ke Pustaka Klien Azure Storage 8.5.0 dan Pustaka DataMovement Azure Storage 0.6.3
  * Menambahkan Fitur Dukungan Snapshot Berbagi File
    - Menambahkan parameter 'SnapshotTime' ke Get-AzureStorageShare
    - Menambahkan parameter 'IncludeAllSnapshot' ke Remove-AzureStorageShare
