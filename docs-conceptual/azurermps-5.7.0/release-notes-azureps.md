---
title: Azure PowerShell Log Perubahan
description: Ini adalah riwayat perubahan yang dibuat untuk Azure PowerShell dalam rilis terbaru.
ms.devlang: powershell
ms.topic: conceptual
ms.workload: ''
ms.date: 2/20/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: a5fe155159f4e170872b80a982099b3fb5366751
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427395"
---
# <a name="azure-powershell-release-notes"></a>Azure PowerShell Catatan rilis

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Ini adalah daftar perubahan yang dibuat untuk Azure PowerShell dalam rilis ini.

---

## <a name="azure-powershell-570"></a>Azure PowerShell 5.7.0

Azure PowerShell Penginstal 5.7.0: [](https://github.com/Azure/azure-powershell/releases/download/v5.7.0-April2018/azure-powershell.5.7.0.msi)

Modul Galeri untuk Cmdlet ARM: [tautan](https://www.powershellgallery.com/packages/AzureRM/5.7.0)

Untuk menginstal `AzureRM` dari Galeri PowerShell, jalankan perintah berikut:

```powershell-interactive
Install-Module -Name AzureRM -Repository PSGallery -Force
```

Untuk memperbarui dari versi `AzureRM` lama, jalankan perintah berikut:

```powershell-interactive
Update-Module -Name AzureRM
```

### <a name="changes-since-last-release"></a>Perubahan sejak rilis terakhir

#### <a name="general"></a>Umum
* Diperbarui ke versi terbaru Azure ClientRuntime

#### <a name="azurestorage"></a>Azure. Storage
* Memperbaiki masalah yang mengunggah cmdlet Blob dan pengunggahan File yang gagal pada komputer yang mengaktifkan kebijakan FIPS
    - Set-AzureStorageBlobContent
    - Set-AzureStorageFileContent

#### <a name="azurermbilling"></a>AzureRM.Billing
* Perintah Cmdlet Get-AzureRmEnrollmentAccount
  - cmdlet untuk mendapatkan akun pendaftaran

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Terintegrasi dengan SDK Manajemen Layanan Kognitif versi 4.0.0.
* Menambahkan Get-AzureRmCognitiveServicesAccountUsage operasi.

#### <a name="azurermcompute"></a>AzureRM.Compute
* `Get-AzureRmVmssDiskEncryptionStatus` mendukung status enkripsi pada tingkat disk data
* `Get-AzureRmVmssVmDiskEncryptionStatus` mendukung status enkripsi pada tingkat disk data
* Pembaruan untuk Resilien Zona
* 'New-AzureRmVm' dan 'New-AzureRmVmss' (simple parameter set) mendukung zona ketersediaan.

#### <a name="azurermcontainerregistry"></a>AzureRM.ContainerRegistry
* Memisahkan ketergantungan pada Perintah.Sumber Daya.Rest dan ARM/Storage SDKs.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Menambahkan fungsionalitas debug
* Memperbarui versi SDK dataplane ADLS ke 1.1.2
* Export-AzureRmDataLakeStoreItem - Parameter yang sudah tidak berlaku PerFileThreadCount, ConcurrentFileCount dan memperkenalkan parameter Concurrency
* Import-AzureRMDataLakeStoreItem - Deprecated parametersPerFileThreadCount, ConcurrentFileCount dan memperkenalkan parameter Concurrency
* Get-AzureRMDataLakeStoreItemContent - Memperbaiki perilaku arah untuk konten yang lebih besar dari 4MB
* Set-AzureRMDataLakeStoreItemExpiry - Memperkenalkan kumpulan parameter baru SetRelativeExpiry untuk mengatur waktu kedaluwarsa relatif
* Remove-AzureRmDataLakeStoreItem - Parameter yang sudah tidak berlaku Clean.

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Memperbaiki AlternameName di New-AzureRmEventHubGeoDRConfiguration

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Cmdlet yang diperbarui untuk menyertakan skenario pemipaan
* Tambahkan pesan penghentian untuk rilis perubahan yang akan datang

#### <a name="azurermnetwork"></a>AzureRM.Network
* Memperbaiki pesan kesalahan dengan cmdlet Jaringan

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan 'properti' di CorrelationFilter of Rules untuk mendukung properti kustom
* pembaruan New-AzureRmServiceBusGeoDRConfiguration bantuan dan output cmdlet Aturan tetap
* Memperbaiki properti penerusan otomatis dalam New-AzureRmServiceBusQueue dan New-AzureRmServiceBusSubscription cmdlet

#### <a name="azurermsql"></a>AzureRM.Sql
* Tambahkan cmdlet baru 'Stop-AzureRmSqlElasticPoolActivity' untuk mendukung pembatalan operasi asinkron pada pool elastis
* Memperbarui respons untuk cmdlet Get-AzureRmSqlDatabaseActivity dan Get-AzureRmSqlElasticPoolActivity untuk mencerminkan informasi selengkapnya dalam respons

Perubahan sejak rilis terakhir: https://github.com/Azure/azure-powershell/compare/v5.6.0-March2018...v5.7.0-April2018

## <a name="560---march-2018"></a>5.6.0 - Maret 2018

#### <a name="general"></a>Umum
* Memperbaiki masalah dengan Grup Sumber Daya Default di CloudShell
* Memperbaiki masalah ketika skrip mulai yang salah dijalankan selama impor modul

#### <a name="azurermprofile"></a>AzureRM.Profile
* Mengaktifkan autentikasi MSI dalam skenario yang tidak didukung
* Tambahkan dukungan untuk Identitas Layanan Terkelola yang ditentukan pengguna

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Memperbaiki masalah membersihkan skrip dalam build

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Memperbaiki masalah membersihkan skrip dalam build

#### <a name="azurermcompute"></a>AzureRM.Compute
* 'New-AzureRmVM' dan 'New-AzureRmVMSS' mendukung disk data.
* 'New-AzureRmVM' dan 'New-AzureRmVMSS' mendukung gambar kustom berdasarkan nama atau berdasarkan id.
* Fitur analitik log
    - Cmdlet 'Export-AzureRmLogAnalyticRequestRateByInterval' ditambahkan
    - Cmdlet 'Export-AzureRmLogAnalyticThrottledRequests' ditambahkan

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Memperbaiki masalah kumpulan parameter untuk registri wadah dan volume file azure

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui ADF .Net SDK ke versi 0.6.0-preview yang berisi perubahan berikut ini:
    - Menambahkan Aktivitas AzureDatabricks LinkedService dan DatabricksNotebook baru
    - Properti headNodeSize dan dataNodeSize yang ditambahkan di HDInsightOnDemand LinkedService
    - Added LinkedService, Dataset, CopySource for SalesforceMarketingCloud
    - Menambahkan dukungan untuk SecureOutput di semua aktivitas
    - Menambahkan properti BatchCount baru pada aktivitas ForEach yang mengontrol berapa banyak aktivitas serentak yang akan dijalankan
    - Menambahkan Aktivitas Filter baru
    - Dukungan Parameter Layanan Tertaut yang ditambahkan

#### <a name="azurermdns"></a>AzureRM.Dns
* Dukungan untuk Zona DNS Privat (Pratinjau Publik)
    - Menambahkan kemampuan untuk membuat zona DNS yang hanya terlihat oleh jaringan virtual yang terkait

#### <a name="azurermnetwork"></a>AzureRM.Network
* Memperbarui tipe model untuk kompatibilitas dengan cmdlet DNS.

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Perubahan ASR Azure pada Pemulihan Situs Azure (cmdlet saat ini mendukung operasi Enterprise ke Enterprise, Enterprise ke Azure, HyperV ke Azure, VMware ke Azure)
    - New-AzureRmRecoveryServicesAsrProtectionContainer
    - New-AzureRmRecoveryServicesAsrAzureToAzureDiskReplicationConfig
    - Remove-AzureRmRecoveryServicesAsrProtectionContainer
    - Update-AzureRmRecoveryServicesAsrProtectionDirection

#### <a name="azurermstorage"></a>AzureRM. Storage
* Parameter berikut ini tak t aktif di cmdlet baru dan setel Akun Storage: EnableEncryptionService dan DisableEncryptionService, karena Enkripsi saat ini diaktifkan secara default dan tidak bisa dinonaktifkan.
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Memperbaiki bantuan untuk Remove-AzureRmWebAppSlot

## <a name="550---march-2018"></a>5.5.0 - Maret 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbaiki masalah ketika mengimpor alias
* Memuat versi 10.0.3 Newtonsoft.Json berdampingan dengan versi 6.0.8

#### <a name="azurestorage"></a>Azure. Storage
* Fitur Soft-Delete dukungan
    - Enable-AzureStorageDeleteRetentionPolicy
    - Disable-AzureStorageDeleteRetentionPolicy
    - Get-AzureStorageBlob

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Memperbaiki masalah ketika mengimpor alias
* Tambahkan dukungan fitur firewall dan skala kueri, serta dukungan versi api 2017-08-01.

#### <a name="azurermautomation"></a>AzureRM.Automation
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Perbarui notice.txt pemberitahuan dan pemberitahuan Anda.

#### <a name="azurermcompute"></a>AzureRM.Compute
* 'New-AzureRmVMSS' mencetak string koneksi dalam mode verbose.
* 'New-AzureRmVmss' mendukung alamat IP publik, aturan keseimbangan muat, aturan NAT masuk.
* Fitur WriteAccelerator
    - Menambahkan parameter sakelar WriteAccelerator ke cmdlet berikut: Set-AzureRmVMOSDisk Set-AzureRmVMDataDisk Add-AzureRmVMDataDisk Add-AzureRmVmssDataDisk
    - Ditambahkan OsDiskWriteAccelerator mengganti parameter ke cmdlet berikut: Set-AzureRmVmssStorageProfile.
    - Menambahkan parameter Boolean OsDiskWriteAccelerator ke cmdlet berikut: Update-AzureRmVM Update-AzureRmVmss

#### <a name="azurermdatafactories"></a>AzureRM.DataFactories
* Memperbaiki masalah enkripsi kredensial yang menyebabkan tidak ada kesalahan bermakna untuk beberapa operasi enkripsi
* Mengaktifkan runtime integrasi untuk dibagikan di seluruh pabrik data

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Tambahkan parameter "SetupScriptContainerSasUri" dan "Edition" untuk cmd "Set-AzureRmDataFactoryV2IntegrationRuntime" untuk mengaktifkan fungsionalitas pemilihan penyetelan dan edisi kustom
* Perbaiki masalah enkripsi kredensial yang menyebabkan tidak ada kesalahan bermakna untuk beberapa operasi enkripsi.
* Mengaktifkan runtime integrasi untuk dibagikan di seluruh pabrik data

#### <a name="azurermhdinsight"></a>AzureRM.HDInsight
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Contoh tetap untuk Set-AzureRmKeyVaultAccessPolicy

#### <a name="azurermnetwork"></a>AzureRM.Network
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermrecoveryservices"></a>AzureRM.RecoveryServices
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah ketika mengimpor alias

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan properti EnableBatchedOperations ke Queue
* Menambahkan properti DeadLetteringOnFilterEvaluationExceptions ke Langganan

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* refresh cmdlet Service Fabric
  - Templat ARM yang diperbarui
  - Gagalkan operasi tidak lagi mengembalikan
  - Add-AzureRmServiceFabricNodeType
    - VM default untuk disk yang dikelola
    - Subnet VMSS yang sudah ada yang digunakan
    - Semua operasi idempok
  - Remove-AzureRmServiceFabricNodeType membersihkan VMSS dan/atau tipe node kluster yang dibuat sebagian
  - Output tetap objek PSCluster untuk tipe properti kompleks

#### <a name="azurermsql"></a>AzureRM.Sql
* Memperbaiki masalah ketika mengimpor alias
* Get-AzureRmSqlServer, New-AzureRmSqlServer, Remove-AzureRmSqlServer anda kini menyertakan properti FullyQualifiedDomainName.

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Memperbaiki masalah ketika mengimpor alias
* New-AzureRMWebApp - kumpulan parameter yang ditambahkan untuk pembuatan WebApp yang disederhanakan, dengan dukungan penyimpanan git lokal.

## <a name="540---february-2018"></a>5.4.0 - Februari 2018
#### <a name="azurermautomation"></a>AzureRM.Automation
* Alias yang ditambahkan New-AzureRmAutomationModule ke Import-AzureRmAutomationModule

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki Masalahction Kesalahan untuk beberapa Get cmdlets.

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Menerapkan Azure Container Instance SDK 2018-02-01
    - Label nama DNS dukungan

#### <a name="azurermdevtestlabs"></a>AzureRM.DevTestLabs
* Memperbaiki semua cmdlet GET yang sebelumnya tidak berfungsi.

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Memperbaiki bug dalam Get-AzureRmEventHubGeoDRConfiguration bantuan

#### <a name="azurermnetwork"></a>AzureRM.Network
* Cmdlet yang ditambahkan untuk membuat monitor koneksi baru
    - New-AzureRmNetworkWatcherConnectionMonitor
* Cmdlet yang ditambahkan untuk memperbarui monitor koneksi
    - Set-AzureRmNetworkWatcherConnectionMonitor
* Cmdlet yang ditambahkan untuk mendapatkan daftar monitor koneksi atau monitor koneksi
    - Get-AzureRmNetworkWatcherConnectionMonitor
* Cmdlet ditambahkan ke monitor koneksi kueri
    - Get-AzureRmNetworkWatcherConnectionMonitorReport
* Cmdlet yang ditambahkan untuk memulai monitor koneksi
    - Start-AzureRmNetworkWatcherConnectionMonitor
* Cmdlet yang ditambahkan untuk menghentikan monitor koneksi
    - Stop-AzureRmNetworkWatcherConnectionMonitor
* Cmdlet yang ditambahkan untuk menghapus monitor koneksi
    - Remove-AzureRmNetworkWatcherConnectionMonitor
* Dokumentasi Set-AzureRmApplicationGatewayBackendAddressPool diperbarui untuk menghapus contoh yang sudah tidak berlaku
* Ditambahkan aktifkanhttp2 bendera ke Gateway Aplikasi
    - Updated New-AzureRmApplicationGateway: Added optional parameter -EnableHttp2
* Menambahkan IpTag ke PublicIpAddress
    - Updated New-AzureRmPublicIpAddress: Added IpTags
    - New-AzureRmPublicIpTag menambahkan Iptag
* Tambahkan properti DisableBgpRoutePropagation dalam RouteTable dan effectiveRoute.

#### <a name="azurermresources"></a>AzureRM.Resources
* Register-AzureRmProviderFeature: Menambahkan contoh yang hilang dalam dokumen
* Register-AzureRmResourceProvider: Contoh hilang yang ditambahkan di dokumen

#### <a name="azurermstorage"></a>AzureRM. Storage
* Parameter berikut ini tak t aktif di cmdlet baru dan setel akun Storage baru: EnableEncryptionService dan DisableEncryptionService, karena Enkripsi di Rest diaktifkan secara default dan tidak bisa dinonaktifkan.
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount


## <a name="530---february-2018"></a>5.3.0 - Februari 2018
### <a name="azurermprofile"></a>AzureRM.Profile
* Peringatan penghentian yang ditambahkan untuk PowerShell 3 dan 4
* `Add-AzureRmAccount` telah diganti namanya sebagai ; alias telah ditambahkan untuk nama cmdlet lama, dan alias lain ( dan `Connect-AzureRmAccount` ) telah dialihkan ke nama cmdlet `Login-AzAccount` `Login-AzureRmAccount` baru.
* `Remove-AzureRmAccount` telah diganti namanya sebagai ; alias telah ditambahkan untuk nama cmdlet lama, dan alias lain ( dan `Disconnect-AzureRmAccount` ) telah dialihkan ke nama cmdlet `Logout-AzAccount` `Logout-AzureRmAccount` baru.
* String Sumber Daya yang diperbaiki untuk `Connect-AzureRmAccount` digunakan sebagai ganti `Login-AzureRmAccount`
* `Add-AzureRmEnvironment` dan `Set-AzureRmEnvironment`
  - Ditambahkan `-AzureOperationalInsightsEndpoint` dan sebagai parameter untuk digunakan dengan bidang data `-AzureOperationalInsightsEndpointResourceId` OperationalInsights RP.

### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Penggunaan penggunaan yang `Login-AzureRmAccount` diperbaiki `Connect-AzureRmAccount`

### <a name="azurermcompute"></a>AzureRM.Compute
* Parameter `-AvailabilitySetName` yang ditambahkan ke parameterset yang disederhanakan dari `New-AzureRmVM` .
* Penggunaan penggunaan yang `Login-AzureRmAccount` diperbaiki `Connect-AzureRmAccount`
* Dukungan identitas yang ditetapkan pengguna untuk kumpulan skala VM dan VM
    - `-IdentityType` dan `-IdentityId` parameter ditambahkan ke , , `New-AzureRmVMConfig` `New-AzureRmVmssConfig` `Update-AzureRmVM` dan `Update-AzureRmVmss`
* Parameter `-EnableIPForwarding` yang ditambahkan ke `Add-AzureRmVmssNetworkInterfaceConfig`
* Parameter `-Priority` yang ditambahkan ke `New-AzureRmVmssConfig`

### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Penggunaan penggunaan yang `Login-AzureRmAccount` diperbaiki `Connect-AzureRmAccount`

### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Penggunaan penggunaan yang `Login-AzureRmAccount` diperbaiki `Connect-AzureRmAccount`
* Memperbaiki pesan kesalahan ketika `Test-AzureRmDataLakeStoreAccount` menjalankan cmdlet ini tanpa harus masuk dengan `Login-AzureRmAccount`

### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Diperbarui untuk menggunakan versi API 2018-01-01.

### <a name="azurermeventhub"></a>AzureRM.EventHub

* Ditambahkan di bawah perintah baru untuk operasi Pemulihan Bencana Geo.
  - Membuat Alias baru (Konfigurasi Pemulihan Bencana):
    - `New-AzureRmEventHubGeoDRConfiguration`
  - Ambil Alias (Konfigurasi Pemulihan Bencana) :
    - `Get-AzureRmEventHubGeoDRConfiguration`
  - Menonaktifkan Pemulihan Bencana dan berhenti mengggentikan perubahan dari ruang nama utama ke sekunder
    - `Set-AzureRmEventHubGeoDRConfigurationBreakPair`
  - Faktur failover Pemulihan Bencana dan konfigurasi ulang alias agar mengarah ke ruang nama sekunder
    - `Set-AzureRmEventHubGeoDRConfigurationFailOver`
  - Menghapus Alias(Konfigurasi Pemulihan Bencana)
    - `Remove-AzureRmEventHubGeoDRConfiguration`
* Ditambahkan di bawah perintah baru untuk memeriksa Nama Ruang Nama dan Nama Konfigurasi GeoDr - Ketersediaan alias.
  - Periksa nama Ketersediaan Nama ruang nama atau Alias(Konfigurasi Pemulihan Bencana)::
    - `Test-AzureRmEventHubName`

### <a name="azurerminsights"></a>AzureRM. Insights
* Penggunaan penggunaan yang `Login-AzureRmAccount` diperbaiki `Connect-AzureRmAccount`

### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Penggunaan penggunaan yang `Login-AzureRmAccount` diperbaiki `Connect-AzureRmAccount`

### <a name="azurermnetwork"></a>AzureRM.Network
* Perbaiki pesan menimpa 'Are you sure you want to overwriteresource'

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Menambahkan dukungan untuk membuat kueri API V2 melalui `Invoke-AzureRmOperationalInsightsQuery` . Lihat [https://dev.loganalytics.io/](https://dev.loganalytics.io/) informasi selengkapnya tentang API baru.

### <a name="azurermresources"></a>AzureRM.Resources
* `Get-AzureRmADServicePrincipal`: Dihapus `-ServicePrincipalName` dari kumpulan parameter Kosong default yang diatur karena berlebihan dengan kumpulan parameter SPN

### <a name="azurermservicebus"></a>AzureRM.ServiceBus

* Perbaikan fungsionalitas yang ditambahkan `Remove-AzureRmServiceBusRule` untuk dan `Get-AzureRmServiceBusKey`
* Ditambahkan di bawah commandlet baru untuk operasi Pemulihan Bencana Geo.
  - Membuat Alias baru (Konfigurasi Pemulihan Bencana):
    - `New-AzureRmServiceBusDRConfigurations`
  - Ambil Alias (Konfigurasi Pemulihan Bencana) :
    - `Get-AzureRmServiceBusDRConfigurations`
  - Menonaktifkan Pemulihan Bencana dan berhenti mengggentikan perubahan dari ruang nama utama ke sekunder
    - `Set-AzureRmServiceBusDRConfigurationsBreakPairing`
  - Faktur failover Pemulihan Bencana dan konfigurasi ulang alias agar mengarah ke ruang nama sekunder
    - `Set-AzureRmServiceBusDRConfigurationsFailOver`
  - Menghapus Alias(Konfigurasi Pemulihan Bencana)
    - `Remove-AzureRmServiceBusDRConfigurations`
* Commandlet `Test-AzureRmServiceBusName` yang diperbarui untuk mendukung Pemulihan Geo Disaster - Operasi ketersediaan pemeriksaan nama alias.
  - Periksa nama Ketersediaan Nama ruang nama atau Alias(Konfigurasi Pemulihan Bencana)::
    - `Test-AzureRmServiceBusName`

### <a name="azurermusageaggregates"></a>AzureRM.UsageAggregates
* Penggunaan penggunaan yang `Login-AzureRmAccount` diperbaiki `Connect-AzureRmAccount`

## <a name="520---january-2018"></a>5.2.0 - Januari 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Add-AzureRmAccount
  * Masuk -MSI untuk authenticationg menggunakan kredensial Identitas Layanan Terkelola VM / Layanan saat ini
  * Perbaikan Autentikasi KeyVault ketika masuk dengan token akses yang diberikan pengguna

#### <a name="azurestorage"></a>Azure. Storage
* Menambahkan cmdlet untuk mendapatkan dan Storage properti layanan
    - Get-AzureStorageServiceProperty
    - Update-AzureStorageServiceProperty

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Usang -Tag untuk mendukung -Tag untuk New-AzureRmApiManagementProperty, Set-AzureRmApiManagementProperty, dan New-AzureRmApiManagement

#### <a name="azurermapplicationinsights"></a>AzureRM.ApplicationInsights
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermautomation"></a>AzureRM.Automation
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t Set-AzureRmAutomationRunbook

#### <a name="azurermbackup"></a>AzureRM.Backup
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermbatch"></a>AzureRM.Batch
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t New-AzureRmCdnEndpoint digunakan untuk mendukung -Tag New-AzureRmCdnEndpoint dan New-AzureRmCdnProfile

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Terintegrasi dengan SDK Manajemen Layanan Kognitif versi 3.0.0.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Menambahkan kumpulan parameter yang disederhanakan ke AzureRmVms Baru, yang membuat Kumpulan Skala Mesin Virtual dan semua sumber daya yang diperlukan menggunakan default cerdas
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t New-AzureRmVm digunakan untuk mendukung -Tag New-AzureRmVm dan Update-AzureRmVm
* Perbaikan Get-AzureRmComputeResourceSku cmdlet ketika Zone disertakan dalam batasan.
* Skema konfigurasi Agen Diagnostik yang diperbarui untuk dukungan sink Monitor Azure.

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermcontainerregistry"></a>AzureRM.ContainerRegistry
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermdatafactories"></a>AzureRM.DataFactories
* Dukungan Azure Key Vault yang diaktifkan untuk semua layanan tertaut penyimpanan data
* Properti tipe lisensi yang ditambahkan untuk runtime integrasi Azure SSIS
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t New-AzureRmDataFactory

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Dukungan Azure Key Vault yang diaktifkan untuk semua layanan tertaut penyimpanan data
* Properti tipe lisensi yang ditambahkan untuk runtime integrasi Azure SSIS
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tambahkan parameter "LicenseType" untuk cmd "Set-AzureRmDataFactoryV2IntegrationRuntime" untuk mengaktifkan fungsionalitas AHUB

#### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t New-AzureRmDataLakeAnalyticsAccount digunakan untuk mendukung -Tag Set-AzureRmDataLakeAnalyticsAccount

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t New-AzureRmDataLakeStoreAccount digunakan untuk mendukung -Tag Set-AzureRmDataLakeStoreAccount

#### <a name="azurermdevtestlabs"></a>AzureRM.DevTestLabs
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermdns"></a>AzureRM.Dns
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Menambahkan cmdlet baru berikut:
  - Update-AzureRmEventGridSubscription
    - Perbarui properti langganan acara Kisi Acara.
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermhdinsight"></a>AzureRM.HDInsight
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurerminsights"></a>AzureRM. Insights
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermiothub"></a>AzureRM.IotHub
* Menambahkan dukungan Sertifikat untuk cmdlet IoTHub
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Menambahkan dukungan -AsJob untuk cmdlet KeyVault yang berjalan dalam waktu lama. Memperbolehkan cmdlet yang dipilih berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
  * Cmdlet yang terpengaruh adalah: Remove-AzureRmKeyVault
* Perbaikan bug Set-AzureRmKeyVaultAccessPolicy filter AAD mengatur SPN ke UPN yang disediakan, bukan menyetel UPN
  - Lihat masalah berikut ini untuk informasi selengkapnya: https://github.com/Azure/azure-powershell/issues/5201

#### <a name="azurermlogicapp"></a>AzureRM.LogicApp
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermmachinelearning"></a>AzureRM.MachineLearning
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t Update-AzureRmMlCommitmentPlan

#### <a name="azurermmachinelearningcompute"></a>AzureRM.MachineLearningCompute
* Menambahkan parameter IncludeAllResources ke Remove-AzureRmMlOpCluster cmdlet
  - Menggunakan parameter sakelar ini akan menghapus semua sumber daya yang dibuat dengan kluster awal
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermmedia"></a>AzureRM.Media
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t Set-AzureRmMediaService digunakan untuk mendukung -Tag New-AzureRmMediaService

#### <a name="azurermnetwork"></a>AzureRM.Network
* Menambahkan dukungan -AsJob untuk cmdlet Jaringan yang berjalan dalam waktu lama. Memperbolehkan cmdlet yang dipilih berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermnotificationhubs"></a>AzureRM.NotificationHubs
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t New-AzureRmNotificationHubsNamespace digunakan untuk mendukung -Tag Set-AzureRmNotificationHubsNamespace

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags mendukung -Tag untuk New-AzureRmOperationalInsightsSavedSearch, Set-AzureRmOperationalInsightsSavedSearch, New-AzureRmOperationalInsightsWorkspace, dan Set-AzureRmOperationalInsightsWorkspace

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermrecoveryservices"></a>AzureRM.RecoveryServices
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Ditambahkan opsi -UseOriginalStorageAccount ke cmdlet Restore-AzureRmRecoveryServicesBackupItem baru.
  - Mengaktifkan bendera ini mengembalikan disk ke akun penyimpanan asli mereka yang memungkinkan pengguna untuk mempertahankan konfigurasi VM yang dipulihkan sedekup mungkin dengan VM asli.
  - Hal ini juga membantu meningkatkan kinerja operasi pemulihan.

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Menambahkan 3 cmdlet baru untuk aturan firewall
* Menambahkan 3 cmdlet baru untuk replikasi geo
* Dukungan tambahan untuk zona dan tag
* Make ResourceGroup sebagai opsional bila memungkinkan.

#### <a name="azurermrelay"></a>AzureRM.Relay
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermresources"></a>AzureRM.Resources
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Menambahkan dukungan -AsJob untuk cmdlet Sumber Daya yang berjalan dalam waktu lama. Memperbolehkan cmdlet yang dipilih berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
* Alias yang ditambahkan Get-AzureRmProviderOperation ke Get-AzureRmResourceProviderAction sesuai dengan konvensi penamaan

#### <a name="azurermscheduler"></a>AzureRM.Scheduler
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermservermanagement"></a>AzureRM.ServerManagement
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Tag tak t New-AzureRmServerManagementNode digunakan untuk mendukung -Tag New-AzureRmServerManagementGateway

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermsiterecovery"></a>AzureRM.SiteRecovery
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermsql"></a>AzureRM.Sql
* Memperbarui deskripsi parameter perintah Audit
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Menambahkan parameter -AsJob ke cmdlet yang berjalan lama
* Parameter -DatabaseName yang tak t Get-AzureRmSqlServiceObjective

#### <a name="azurermstorage"></a>AzureRM. Storage
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Memperbaiki masalah referensi null ketika menjalankan perintah cmdlet New-AzureRMStorageAccount parameter -EnableEncryptionService None
* Menambahkan dukungan -AsJob untuk cmdlet Storage yang berjalan lama. Memperbolehkan cmdlet yang dipilih berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
    - Cmdlet yang terpengaruh adalah New-, Remove-, Add-, dan Update- untuk Akun Storage baru Storage Aturan Jaringan Akun.

#### <a name="azurermstreamanalytics"></a>AzureRM.StreamAnalytics
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Menambahkan Location Completer ke parameter -Location yang memungkinkan penyelesaian tab melalui Lokasi yang valid
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Menambahkan dukungan -AsJob untuk cmdlet Situs Web yang berjalan dalam waktu lama. Memperbolehkan cmdlet yang dipilih berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
     - Cmdlet yang terpengaruh adalah New-, Remove-, Add-, dan Set- for WebApps, AppServicePlan dan Slots

## <a name="2017128-version-511"></a>2017.12.8 Versi 5.1.1
* AnalysisServices
  - Ubah validasi kumpulan lokasi menjadi pencarian dinamis agar semua awan didukung.
* Otomatisasi
  - Perbarui ke Import-AzureRMAutomationRunbook
    - Dukungan kini disediakan untuk runbooks Python2
* Kumpulan
  - Perbaikan bug operasi akun tanpa grup sumber daya yang gagal mendeteksi grup sumber daya secara otomatis
* Hitung
  - Get-AzureRmComputeResourceSku menampilkan informasi zona.
  - Perbarui Disable-AzureRmVmssDiskEncryption untuk memperbaiki masalah https://github.com/Azure/azure-powershell/issues/5038
  - Menambahkan dukungan -AsJob untuk cmdlet Perhitungan yang berjalan dalam waktu lama. Memperbolehkan cmdlet yang dipilih berjalan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan.
    - Cmdlet yang terpengaruh meliputi: New-, Update-, Set-, Remove-, Start-, Restart-, Stop- cmdlet untuk Mesin Virtual dan Kumpulan Skala Mesin Virtual
    - Menambahkan kumpulan parameter yang disederhanakan ke New-AzureRmVM, yang membuat Komputer Virtual dan semua sumber daya yang diperlukan menggunakan default cerdas
* ContainerInstance
  - Menerapkan Azure Container Instance SDK 2017-10-01
    - Wadah dukungan run-to-completion
    - Mendukung dudukan volume File Azure
    - Dukungan untuk membuka beberapa port untuk IP publik
* ContainerRegistry
  - Cmdlet baru untuk replikasi geo dan webhook
    - Dapatkan/Baru/Hapus-AzureRmContainerRegistryReplication
    - Dapatkan/Baru/Hapus/Uji/Update-AzureRmContainerRegistryWebhook
* DataFactories
    - Fungsionalitas enkripsi kredensial sekarang berfungsi dengan "Akses Jarak Jauh" yang diaktifkan (Melalui Jaringan) dan "Akses Jarak Jauh" dinonaktifkan (Komputer Lokal).
* DataFactoryV2
  - Menambahkan dua cmdlet baru: Update-AzureRmDataFactoryV2 dan Stop-AzureRmDataFactoryV2PipelineRun
* DataLakeAnalytics
  - Menambahkan parameter yang disebut ScriptParameter ke Submit-AzureRmDataLakeAnalyticsJob
    - Informasi mendetail tentang ScriptParameter dapat ditemukan menggunakan Get-Help di Submit-AzureRmDataLakeAnalyticsJob
  - Untuk New-AzureRmDataLakeAnalyticsAccount, ubah parameter MaxDegreeOfParallelism menjadi MaxAnalyticsUnits
    - Menambahkan alias untuk parameter MaxAnalyticsUnits: MaxDegreeOfParallelism
  - Untuk New-AzureRmDataLakeAnalyticsComputePolicy, ubah parameter MaxDegreeOfParallelismPerJob menjadi MaxAnalyticsUnitsPerJob
    - Menambahkan alias untuk parameter MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
  - Untuk Set-AzureRmDataLakeAnalyticsAccount, ubah parameter MaxDegreeOfParallelism menjadi MaxAnalyticsUnits
    - Menambahkan alias untuk parameter MaxAnalyticsUnits: MaxDegreeOfParallelism
  - Untuk Submit-AzureRmDataLakeAnalyticsJob, ubah parameter DegreeOfParallelism menjadi AnalyticsUnits
    - Menambahkan alias untuk parameter AnalyticsUnits: DegreeOfParallelism
  - Untuk Update-AzureRmDataLakeAnalyticsComputePolicy, ubah parameter MaxDegreeOfParallelismPerJob menjadi MaxAnalyticsUnitsPerJob
    - Menambahkan alias untuk parameter MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
* MachineLearningCompute
  - Menambahkan Set-AzureRmMlOpCluster
    - Memperbarui jumlah agen kluster atau konfigurasi SSL
  - Properti Orchestrator bersifat opsional
    - Layanan akan membuat prinsipal layanan jika tidak disediakan, sehingga properti pengelola sekarang bersifat opsional
* PowerBIEmbedded
  - Menambahkan dukungan untuk Power BI Embedded cmdlet Kapasitas Baru
  - Cmdlet Baru Get-AzureRmPowerBIEmbeddedCapacity - Mendapatkan detail Kapasitas yang Disematkan PowerBI.
  - Perintah Cmdlet New-AzureRmPowerBIEmbeddedCapacity - Membuat Kapasitas Tersemat PowerBI baru
  - Perintah Cmdlet Remove-AzureRmPowerBIEmbeddedCapacity - Menghapus instans Kapasitas Yang Disematkan PowerBI
  - Perintah Cmdlet Resume-AzureRmPowerBIEmbeddedCapacity - Melanjutkan contoh Kapasitas yang Disematkan PowerBI
  - Perintah Cmdlet Suspend-AzureRmPowerBIEmbeddedCapacity - Menangguhkan instans Kapasitas Yang Disematkan PowerBI
  - Cmdlet Baru Test-AzureRmPowerBIEmbeddedCapacity - Menguji keberadaan instans Kapasitas Yang Disematkan PowerBI
  - Perintah Cmdlet Update-AzureRmPowerBIEmbeddedCapacity - Memodifikasi instans Kapasitas Yang Disematkan PowerBI
* Profil
  - USGovernmentActiveDirectoryEndpoint menjadi https://login.microsoftonline.us/
    - Untuk informasi selengkapnya tentang pemetaan titik akhir Azure Government, lihat [Pemetaan titik akhir](/azure/azure-government/documentation-government-developer-guide#endpoint-mapping)
    - Menambahkan dukungan -AsJob untuk cmdlet, memungkinkan cmdlet yang dipilih untuk dijalankan di latar belakang dan mengembalikan pekerjaan untuk melacak dan mengontrol kemajuan
    - Menambahkan parameter -AsJob ke Get-AzureRmSubscription cmdlet
* RecoveryServices.Backup
  - Fixed bug - Get-AzureRmRecoveryServicesBackupItem do case insensitive comparison for container name filter.
  - Memperbaiki bug - AzureVmItem kini memiliki properti yang memperlihatkan waktu terakhir operasi pencadangan terjadi - LastBackupTime.
* Sumber daya
  - Memperbaiki masalah Get-AzureRMRoleAssignment penetapan peran tanpa nama roledefiniton untuk peran kustom
    - Pengguna kini dapat Get-AzureRMRoleAssignment tugas yang memiliki nama perandefinis tanpa melihat tipe peran
  - Memperbaiki masalah Set-AzureRMRoleRoleDefinition yang digunakan untuk menetapkan kesalahan RD yang tidak ditemukan ketika ada lingkup baru dalam assignablescopes
    - Pengguna kini Set-AzureRMRoleRoleDefinition dengan lingkup yang dapat ditetapkan termasuk lingkup baru terlepas dari posisi lingkup
  - Perbolehkan lingkup berakhir dengan "/"
    - Pengguna kini dapat menggunakan perintah RoleDefinition dan RoleAssignment dengan lingkup berakhiran "/" ,konsisten dengan API dan CLI
  - Memperbolehkan pengguna membuat Penetapan Peran menggunakan bendera delegasi
    - Pengguna kini dapat New-AzureRMRoleAssignment pesan dengan opsi menambahkan bendera delegasi
  - Fix RoleAssignment menetapkan parameter untuk menghormati parameter lingkup
  - Menambahkan alias untuk ServicePrincipalName di New-AzureRmRoleAssignment Commandlet
    - Pengguna kini dapat menggunakan ApplicationId dan bukan ServicePrincipalName ketika menggunakan commandlet New-AzureRmRoleAssignment
* Pemulihan Situs
  - Tambahkan peringatan penghentian untuk semua cmdlet dalam modul ini sebagai persiapan untuk rilis perubahan berikutnya.
    - Silakan lihat panduan perubahan terbaru yang akan datang untuk informasi selengkapnya tentang cara memigrasi cmdlet dari AzureRM.
* Sql
  - Kemampuan menambahkan nama database menggunakan Set-AzureRmSqlDatabase
  - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/4974
    - Penyediaan nilai AUDIT_CHANGED_GROUP tidak valid untuk cmdlet pengauditan tidak lagi memberikan kesalahan dan akan dihapus di rilis mendatang.
  - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/5046
    - Parameter auditAction dalam cmdlet pengauditan tidak lagi diabaikan
  - Memperbaiki masalah dalam Cmdlet Pengauditan ketika StorageKeyType 'Sekunder' disediakan
    - Ketika mengatur pengauditan blob, kunci akun penyimpanan utama digunakan, bukan kunci sekunder ketika menyediakan nilai 'Sekunder' untuk parameter StorageKeyType.
  - Mengubah kata-kata untuk pesan konfirmasi dari Set-AzureRmSqlServerTransparentDataEncryptionProtector
* Azure (RDFE)
    - Menghapus semua Cmdapp RemoteApp
* Azure. Storage
    - Mutakhirkan ke Azure Storage Client Library 8.6.0 dan Azure Storage DataMovement Library 0.6.5

## <a name="20171110-version-501"></a>2017.11.10 Versi 5.0.1
* Perbaikan masalah pemuatan perakitan yang menyebabkan beberapa cmdlet gagal saat menjalankan modul berikut:
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
  - AzureRM. Storage
  - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>2017.11.8 - Versi 5.0.0
* CATATAN: Rilis ini merupakan rilis perubahan yang tidak dapat diubah. Silakan lihat panduan migrasi ( https://aka.ms/azps-migration-guide) untuk daftar lengkap perubahan yang diperkenalkan.
* Semua cmdlet di AzureRM kini mendukung bantuan online
  - Menjalankan Get-Help dengan parameter -Online untuk membuka bantuan online di browser internet default Anda
* AnalysisServices
  * Memperbaiki Synchronize-AzureAsInstance agar berfungsi dengan API REST AsAzure yang baru untuk sinkronisasi
* ApiManagement
  * Silakan lihat panduan migrasi untuk memutus perubahan yang dibuat pada ApiManagement rilis ini
  * Perintah Cmdlet Get-AzureRmApiManagementUser untuk memperbaiki masalah https://github.com/Azure/azure-powershell/issues/4510
  * Perintah Cmdlet New-AzureRmApiManagementApi membuat Api dengan Jalur Kosong https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
  * Menambahkan perintah untuk mendapatkan/membuat/menghapus sumber daya wawasan aplikasi
    - Get-AzureRmApplicationInsights
    - New-AzureRmApplicationInsights
    - Remove-AzureRmApplicationInsights
  * Menambahkan perintah untuk mendapatkan/memperbarui harga/jumlah sumber daya wawasan aplikasi harian
    - Get-AzureRmApplicationInsights -IncludeDailyCap
    - Set-AzureRmApplicationInsightsPricingPlan
    - Set-AzureRmApplicationInsightsDailyCap
  * Menambahkan perintah untuk mendapatkan/membuat/memperbarui/menghapus ekspor berkelanjutan dari sumber daya wawasan aplikasi
    - Get-AzureRmApplicationInsightsContinuousExport
    - Set-AzureRmApplicationInsightsContinuousExport
    - New-AzureRmApplicationInsightsContinuousExport
    - Remove-AzureRmApplicationInsightsContinuousExport
  * Tambahkan perintah untuk mendapatkan/membuat/menghapus tombol api dari wawasan aplikasi
    - Get-AzureRmApplicationInsightsApiKey
    - New-AzureRmApplicationInsightsApiKey
    - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
  * Menambahkan parameter baru ke `New-AzureRmBatchAccount` .
    - `PoolAllocationMode`: Mode alokasi untuk digunakan membuat kolam renang di akun Kumpulan. Untuk membuat akun Batch yang mengalokasikan simpul kumpulan dalam langganan pengguna, atur ke `UserSubscription` .
    - `KeyVaultId`: ID sumber daya vault kunci Azure yang terkait dengan akun Batch.
    - `KeyVaultUrl`: URL penyimpanan kunci Azure yang terkait dengan akun Kumpulan.
  * Parameter yang diperbarui menjadi `New-AzureBatchTask` .
    - Menghapus `RunElevated` sakelar. Parameter telah ditambahkan untuk menggantikan , dan perilaku yang setara dapat dicapai dengan membangun `UserIdentity` `RunElevated` seperti yang diperlihatkan di bawah `PSUserIdentity` ini:
      - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
      - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
    - Menambahkan `AuthenticationTokenSettings` parameter. Parameter ini memungkinkan Anda untuk meminta layanan Batch menyediakan token autentikasi untuk tugas ketika dijalankan, menghindari perlunya memberikan kunci akun Batch ke tugas untuk masalah permintaan ke layanan Batch.
    - Menambahkan `ContainerSettings` parameter.
      - Parameter ini memungkinkan Anda untuk meminta layanan Batch menjalankan tugas di dalam wadah.
    - Menambahkan `OutputFiles` parameter.
      - Parameter ini memungkinkan Anda mengonfigurasi tugas untuk mengunggah file Azure Storage setelah selesai.
  * Parameter yang diperbarui menjadi `New-AzureBatchPool` .
    - Menambahkan `UserAccounts` parameter.
      - Parameter ini menentukan akun pengguna yang dibuat pada setiap simpul dalam pool.
    - Ditambahkan `TargetLowPriorityComputeNodes` dan diganti `TargetDedicated` namanya menjadi `TargetDedicatedComputeNodes` .
      - Alias `TargetDedicated` dibuat untuk `TargetDedicatedComputeNodes` parameter.
    - Menambahkan `NetworkConfiguration` parameter.
      - Parameter ini memungkinkan Anda untuk mengonfigurasi pengaturan jaringan kolam renang.
  * Parameter yang diperbarui menjadi `New-AzureBatchCertificate` .
    - Parameter `Password` sekarang adalah `SecureString` .
  * Parameter yang diperbarui menjadi `New-AzureBatchComputeNodeUser` .
    - Parameter `Password` sekarang adalah `SecureString` .
  * Parameter yang diperbarui menjadi `Set-AzureBatchComputeNodeUser` .
    - Parameter `Password` sekarang adalah `SecureString` .
  * Mengganti nama `Name` parameter menjadi pada , , dan `Path` `Get-AzureBatchNodeFile` `Get-AzureBatchNodeFileContent` `Remove-AzureBatchNodeFile` .
    - Alias `Name` dibuat untuk `Path` parameter.
  * Perubahan pada objek
    - Silakan lihat log Perubahan kumpulan untuk daftar lengkap
  * Dukungan tambahan untuk Azure Active Directory berbasis autentikasi.
    - Untuk menggunakan Azure Active Directory autentikasi, `BatchAccountContext` ambil objek menggunakan `Get-AzureRmBatchAccount` cmdlet, dan `BatchAccountContext` memasoknya ke parameter cmdlet layanan `-BatchContext` Batch. Azure Active Directory autentikasi wajib untuk akun dengan `PoolAllocationMode = UserSubscription` .
    - Untuk akun yang sudah ada atau akun baru yang dibuat dengan , Anda dapat terus menggunakan autentikasi kunci bersama dengan `PoolAllocationMode = BatchService` `BatchAccountContext` mengambil objek menggunakan `Get-AzureRmBatchAccoutKeys` cmdlet.
* Hitung
  * Perintah Ekstensi Enkripsi Disk Azure
    - Parameter Baru untuk 'Set-AzureRmVmDiskEncryptionExtension': '-EncryptFormatAll' mengenkripsi disk data
    - Parameter Baru untuk 'Set-AzureRmVmDiskEncryptionExtension': '-ExtensionPublisherName' dan '-ExtensionType' memungkinkan peralihan ke versi ekstensi lain
    - Parameter Baru untuk 'Disable-AzureRmVmDiskEncryption': '-ExtensionPublisherName' dan '-ExtensionType' memungkinkan pengalihan ke versi ekstensi lain
    - Parameter Baru untuk 'Get-AzureRmVmDiskEncryptionStatus': '-ExtensionPublisherName' dan '-ExtensionType' memungkinkan pengalihan ke versi ekstensi lain
* DataLakeAnalytics
  * Silakan lihat panduan migrasi untuk mengetahui perubahan yang terjadi pada DataLakeAnalytics pada rilis ini
  * Mengubah salah satu dari dua Tipe Output dari Get-AzureRmDataLakeAnalyticsAccount
    - Daftar \<DataLakeAnalyticsAccount> ke Daftar\<PSDataLakeAnalyticsAccountBasic>
    - Properti PSDataLakeAnalyticsAccountBasic adalah subset langsung dari properti DataLakeAnalyticsAccount
    - Properti tambahan yang ada di DataLakeAnalyticsAccount tidak dikembalikan oleh layanan.  Oleh karena itu, perubahan ini harus mencerminkan hal ini secara akurat. Properti tambahan ini masih ada di PSDataLakeAnalyticsAccountBasic, tetapi ditandai sebagai Obsolete.
  * Mengubah salah satu dari dua Tipe Output dari Get-AzureRmDataLakeAnalyticsJob
    - Daftar \<JobInformation> ke Daftar\<PSJobInformationBasic>
    - Properti DARI PSJobInformationBasic adalah subset ketat dari properti JobInformation
    - Properti tambahan yang ada di JobInformation tidak dikembalikan oleh layanan.  Oleh karena itu, perubahan ini harus mencerminkan hal ini secara akurat. Properti tambahan ini masih di PSJobInformationBasic, namun properti ini ditandai sebagai Obsolete.
* DataLakeStore
  * Silakan lihat panduan migrasi untuk mengetahui perubahan yang terjadi pada DataLakeStore rilis ini
  * Mengubah salah satu dari dua Tipe Output dari Get-AzureRmDataLakeStoreAccount
    - Daftar \<PSDataLakeStoreAccount> ke Daftar\<PSDataLakeStoreAccountBasic>
    - Properti PSDataLakeStoreAccountBasic adalah subset langsung dari properti PSDataLakeStoreAccount
    - Properti tambahan yang ada di PSDataLakeStoreAccount tidak dikembalikan oleh layanan.  Oleh karena itu, perubahan ini harus mencerminkan hal ini secara akurat. Properti tambahan ini masih ada di PSDataLakeStoreAccountBasic, tetapi ditandai sebagai Sudah Tidak Tbasi.
* Dns
  * Dukungan untuk tipe catatan CAA di Azure DNS
    - Mendukung semua operasi pada tipe rekaman CAA
* EventHub
  * Silakan lihat panduan migrasi untuk perubahan yang terjadi pada EventHub rilis ini
* Insights
  * Silakan lihat panduan migrasi untuk mengetahui perubahan yang dibuat pada Insights rilis ini
* Jaringan
  * Silakan lihat panduan migrasi untuk mengetahui perubahan yang dibuat pada Jaringan rilis ini
  * Menambahkan cmdlet ke daftar penyedia layanan internet yang tersedia untuk kawasan Azure yang ditentukan
    - Get-AzureRmNetworkWatcherReachabilityProvidersList
  * Cmdlet ditambahkan untuk mendapatkan skor latensi relatif bagi penyedia layanan internet dari lokasi tertentu ke kawasan Azure
    - Get-AzureRmNetworkWatcherReachabilityReport
* Profil
  - Set-AzureRmDefault
    - Gunakan cmdlet ini untuk mengatur grup sumber daya default.  Langkah ini akan membuat parameter -ResourceGroup bersifat opsional untuk beberapa cmdlet, dan akan menggunakan default saat grup sumber daya tidak ditentukan
    - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
    - Jika grup sumber daya yang ditentukan ada dalam langganan, grup sumber daya ini akan diatur ke default.  Jika tidak, grup sumber daya akan dibuat dan diatur ke default.
  - Get-AzureRmDefault
    - Gunakan cmdlet ini untuk mendapatkan grup sumber daya default saat ini (dan default lainnya di masa mendatang).
    - ```Get-AzureRmDefault -ResourceGroup```
  - Clear-AzureRmDefault
    - Gunakan cmdlet ini untuk menghapus grup sumber daya default saat ini
    - ```Clear-AzureRmDefault -ResourceGroup```
  - Add-AzureRmEnvironment dan Set-AzureRmEnvironment
    - Tambahkan parameter BatchAudience, yang memungkinkan Anda menentukan audiens Azure Batch Active Directory untuk digunakan saat mendapatkan token autentikasi untuk layanan Batch.
* RecoveryServices.Backup
  * Cmdlet yang ditambahkan untuk melakukan pemulihan file instan.
    - Get-AzureRmRecoveryServicesBackupRPMountScript
    - Disable-AzureRmRecoveryServicesBackupRPMountScript
  * Updated RecoveryServices.Backup SDK version to the latest
  * Memperbarui uji untuk beban kerja Azure VM sehingga, semua penyiapan yang diperlukan untuk menjalankan uji dilakukan dengan sendirinya oleh uji tersebut.
  * Perbaikan https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
  * Perubahan untuk VMware ASR pada Pemulihan Situs Azure (cmdlet saat ini mendukung operasi Untuk Perusahaan ke Perusahaan, Perusahaan ke Azure, HyperV untuk Azure)
    - New-AzureRmRecoveryServicesAsrPolicy
    - New-AzureRmRecoveryServicesAsrProtectedItem
    - Update-AzureRmRecoveryServicesAsrPolicy
    - Update-AzureRmRecoveryServicesAsrProtectionDirection
  * Dukungan tambahan AAD berbasis vault
  * Menambahkan cmdlet untuk mengelola sumber daya VCenter
    - Get-AzureRmRecoveryServicesAsrVCenter
    - New-AzureRmRecoveryServicesAsrVCenter
    - Remove-AzureRmRecoveryServicesAsrVCenter
    - Update-AzureRmRecoveryServicesAsrVCenter
  * Menambahkan cmdlet lain
    - Get-AzureRmRecoveryServicesAsrAlertSetting
    - Get-AzureRmRecoveryServicesAsrEvent
    - New-AzureRmRecoveryServicesAsrProtectableItem
    - Set-AzureRmRecoveryServicesAsrAlertSetting
    - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
    - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
    - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
    - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
  - Silakan lihat panduan migrasi untuk mengetahui perubahan yang terjadi pada ServiceBus rilis ini
* Sql
  * Menambahkan dukungan untuk daftar dan membatalkan operasi tombol pembaruan asinkron pada database
    - cmdlet pembaruan yang sudah Get-AzureRmSqlDatabaseActivity untuk mengembalikan status operasi perangkat pembaruan DB.
    - tambahkan cmdlet Stop-AzureRmSqlDatabaseActivity untuk membatalkan operasi pembaruan asinkron pada database.
  * Menambahkan dukungan untuk Kelebihan Kelebihan Zona untuk database dan kolam renang elastis
    - Menambahkan parameter sakelar ZoneRedundant New-AzureRmSqlDatabase
    - Menambahkan parameter sakelar ZoneRedundant Set-AzureRmSqlDatabase
    - Menambahkan parameter sakelar ZoneRedundant New-AzureRmSqlElasticPool
    - Menambahkan parameter sakelar ZoneRedundant Set-AzureRmSqlElasticPool
  * Menambahkan dukungan untuk Alias DNS Server
    - Menambahkan Get-AzureRmSqlServerDnsAlias cmdlet yang mendapatkan alias dns server berdasarkan nama server dan alias, atau daftar alias dns server untuk Azure Sql Server.
    - Menambahkan New-AzureRmSqlServerDnsAlias cmdlet yang membuat alias dns server baru untuk server Azure Sql tertentu
    - Menambahkan Set-AzurermSqlServerDnsAlias cmlet yang memungkinkan pembaruan Azure Sql Server ke alias dns server yang menunjuk
    - Menambahkan Remove-AzureRmSqlServerDnsAlias cmdlet yang menghapus alias dns server untuk Azure Sql Server
* Azure. Storage
  * Mutakhirkan ke Azure Storage Client Library 8.5.0 dan Azure Storage DataMovement Library 0.6.3
  * Fitur Dukungan Snapshot Tambahkan Berbagi File
    - Menambahkan parameter 'SnapshotTime' ke Get-AzureStorageShare
    - Menambahkan parameter 'IncludeAllSnapshot' untuk Remove-AzureStorageShare
