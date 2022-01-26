---
title: Azure PowerShell rilis
description: Pelajari tentang semua pembaruan terkini untuk Azure PowerShell baru.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/10/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: bcc219695687605e8a6b0c49762e374dc09d3f09
ms.sourcegitcommit: 2b90f2e68e4992e43f16a51f69e5581db189440b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/26/2022
ms.locfileid: "137778622"
---
# <a name="azure-powershell-release-notes"></a>Azure PowerShell rilis
## <a name="0100-preview---april-2020"></a>0.10.0-preview - April 2020
### <a name="general"></a>Umum
* Modul Az kini tersedia dalam pratinjau di Azure Stack Hub. Hal ini memungkinkan kompatibilitas lintas platform dengan Linux dan macOS. Azure Stack Hub kini mendukung inti PowerShell dengan modul Az, informasi selengkapnya di [sini](/azure-stack/operator/powershell-install-az-module)
* Profil dukungan modul Az 2019-03-01-hybrid:
  - Az.Billing
  - Az.Compute
  - Az.DataBoxEdge
  - Az.EventHub
  - Az.IotHub
  - Az.KeyVault
  - Az.Monitor
  - Az.Network
  - Az.Resources
  - Az.Storage
  - Situs Web Az.
* Tiga modul PowerShell baru untuk az telah diperkenalkan yang berfungsi dengan Azure Stack Hub, yaitu Az.Databox, Az.IotHub, dan Az.EventHub
* Perintah tetap relatif sama, dengan sedikit perubahan seperti mengubah AzureRM menjadi Az
* Tautan yang diperbarui ke dokumentasi PowerShell untuk Azure Stack Hub dapat ditemukan di [sini](/azure-stack/operator/powershell-install-az-module)

#### <a name="azaccounts"></a>Az.Accounts
* Memutakhirkan dari ADAL ke MSAL


## <a name="370---march-2020"></a>3.7.0 - Maret 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki 'Get-AzTenant'/'Get-AzDefault'/'Set-AzDefault' mengembalikan NullReferenceException ketika tidak masuk [#10292]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter berikut ke cmdlet 'New-AzDiskConfig':
    - DiskIOPSReadOnly, DiskMBpsReadOnly, MaxSharesCount, GalleryImageReference
* Properti Enkripsi yang diperbolehkan ke parameter Target dari cmdlet 'New-AzGalleryImageVersion'.
* Memperbaiki masalah tempDisk untuk cmdlet 'Set-AzVmss' -Reimage dan 'Invoke-AzVMReimage'. [#11354]
* Dukungan tambahan ke cmdlet di bawah ini untuk Ekstensi SAP baru
    - 'Set-AzVMAEMExtension'
    - 'Get-AzVMAEMExtension'
    - 'Remove-AzVMAEMExtension'
    - 'Update-AzVMAEMExtension'
* Memperbaiki kesalahan dalam contoh dokumen bantuan
* Memperlihatkan nilai string yang tepat untuk VM PowerState dalam format tabel.
* 'New-AzVmssConfig': diperbaiki serialisasi properti AutomaticRepairs saat SinglePlacementGroup dinonaktifkan. [#11257]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 4.8.0
* Menambahkan parameter opsional untuk perintah 'Invoke-AzDataFactoryV2Pipeline' untuk mendukung jalan ulang

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Penambahan deskripsi perubahan terbaru untuk 'Ekspor-AzDataLakeStoreItem' dan 'Import-AzDataLakeStoreItem'
* Opsi tambahan pengodean Byte untuk 'New-AzDataLakeStoreItem', 'Add-AzDAtaLakeStoreItemContent', dan 'Get-AzDAtaLakeStoreItemContent'

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung menentukan versi TLS minimal yang didukung saat membuat kluster.

#### <a name="aziothub"></a>Az.IotHub
* Dukungan tambahan untuk mengelola pengaturan terdistribusi per perangkat. Cmdlet Baru adalah:
    - 'Get-AziotHubDistributedTracing'
    - 'Set-AziotHubDistributedTracing'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan atribut perubahan pecah ke 'New-AzKeyVault'

#### <a name="azmonitor"></a>Az.Monitor
* Dokumentasi yang diperbarui untuk 'New-AzScheduledQueryRuleLogMetricTrigger'

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui untuk memperbolehkan VirtualHubVnetConnections lintas penyewa
    - 'New-AzVirtualHubVnetConnection'
    - 'Update-AzVirtualHubVnetConnection'
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Dependensi SDK Manajemen Sql yang dihapus

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Pesan kesalahan yang ditingkatkan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Pemulihan Situs Azure menambahkan dukungan untuk melakukan proteksi ulang dan pembaruan properti vm untuk Komputer Virtual terenkripsi disk Azure.
* Ditambahkan pemantauan DR Pemulihan Situs Azure VmwareToAzure
* Azure Backup menambahkan dukungan untuk mencoba pembaruan kebijakan untuk item yang gagal.
* Cadangan Azure Dukungan tambahan untuk pengaturan pengecualian disk selama pencadangan dan pemulihan.
* Azure Backup Added Support for Restoring Multiple files/folders in AzureFileShare
* Dukungan Azure Backup Ditambahkan untuk dukungan Grup Sumber Daya yang ditentukan pengguna saat memperbarui Kebijakan IaasVM

#### <a name="azresources"></a>Az.Resources
* Memperbaiki 'Get-AzResource -ResourceGroupName -Name -ExpandProperties -ResourceType' untuk menggunakan apiVersion sumber daya aktual dan bukan apiVersion default [#11267]
* Menambahkan pembuatan log ID korelasi untuk skenario kesalahan
* Dokumentasi kecil berubah menjadi 'Get-AzResourceLock'. Contoh yang ditambahkan.
* Kutip tunggal yang di escape dalam nilai parameter 'Get-AzADUser' [#11317]
* Menambahkan cmdlet baru untuk Skrip Penyebaran ('Get-AzDeploymentScript', 'Get-AzDeploymentScriptLog', 'Save-AzDeploymentScriptLog', 'Remove-AzDeploymentScript')

#### <a name="azsql"></a>az.sql
* Menambahkan parameter sekunder yang dapat dibaca ke 'Invoke-AzSqlDatabaseFailover'
* Cmdlet ditambahkan 'Disable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Peringkat sensitivitas yang disimpan saat mengklasifikasikan kolom dalam database.

#### <a name="azsupport"></a>Az.Support
* Ketersediaan umum modul 'Az.Support'

#### <a name="azwebsites"></a>Situs Web Az.
* Menambahkan dukungan untuk bekerja dengan Aturan Perutean Lalu Lintas webapp melalui cmdlet baru
    - 'Get-AzWebAppTrafficRouting'
    - 'Update-AzWebAppTrafficRouting'
    - 'Add-AzWebAppTrafficRouting'
    - 'Remove-AzWebAppTrafficRouting'

## <a name="361---march-2020"></a>3.6.1 - Maret 2020
#### <a name="azaccounts"></a>Az.Accounts
* Buka Azure PowerShell survei anda dalam 'Kirim-Umpan Balik' [#11020]
* Menampilkan Azure PowerShell URL survei dalam 'Atasi-Kesalahan' [#11021]
* Versi Az yang ditambahkan di UserAgent

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan dukungan untuk mengambil dan mengonfigurasi Domain Kustom di Titik Akhir DeveloperPortal [#11007]
* 'Export-AzApiManagementApi' Dukungan tambahan untuk mengunduh Definisi Api dalam format Json [#9987]
* 'Import-AzApiManagementApi' Dukungan tambahan untuk mengimpor definisi OpenApi 3.0 dari dokumen Json
* 'New-AzApiManagementIdentityProvider' dan 'Set-AzApiManagementIdentityProvider' Dukungan tambahan untuk mengonfigurasi 'Penyewa Masuk' untuk AAD Penyedia B2C [#9784]

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan referensi ke System.Buffers secara eksplisit di csproj dan psd1.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola perangkat di Hub Iot. Cmdlet Baru adalah:
    - 'Add-AziotHubDevice'
    - 'Get-AziotHubDevice'
    - 'Remove-AziotHubDevice'
    - 'Set-AziotHubDevice'
* Dukungan tambahan untuk mengelola modul di perangkat target di Hub Iot. Cmdlet Baru adalah:
    - 'Add-AziotHubModule'
    - 'Get-AziotHubModule'
    - 'Remove-AziotHubModule'
    - 'Set-AziotHubModule'
* Cmdlet tambahan untuk mendapatkan string koneksi perangkat IoT target dalam Iot Hub.
* Cmdlet tambahan untuk mendapatkan string koneksi modul pada perangkat IoT target dalam Iot Hub.
* Menambahkan dukungan untuk mendapatkan/mengatur perangkat induk dari perangkat IoT. Cmdlet Baru adalah:
    - 'Get-AziotHubDeviceParent'
    - 'Set-AziotHubDeviceParent'
* Dukungan tambahan untuk mengelola hubungan orang tua dan anak perangkat.

#### <a name="azmonitor"></a>Az.Monitor
* Nilai output tetap untuk 'Get-AzMetricDefinition' [#9714]

#### <a name="aznetwork"></a>Az.Network
* SDK Manajemen Sql yang diperbarui.
* Memperbaiki masalah perbedaan penamaan dalam kelas PrivateLinkServiceConnectionState.
    - Memetakan Tindakan bidangRequired ke ActionRequired.
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'

#### <a name="azresources"></a>Az.Resources
* Diperbaiki untuk bug referensi null dalam 'Get-AzRoleAssignment'
* Tanda alih '-Paksa' dan '-PassThru' opsional dalam 'Remove-AzADGroup' [#10849]
* Memperbaiki masalah yang 'MailNickname' tidak muncul kembali di 'Remove-AzADGroup' [#11167]
* Memperbaiki masalah operasi pipa 'Hapus-AzADGroup' tidak berfungsi [#11171]
* Perbaikan untuk bug referensi null dalam GetAzureRoleAssignmentCommand
* Menambahkan atribut perubahan yang pecah untuk perubahan yang akan datang ke cmdlet kebijakan
* Memperbarui 'Get-AzResourceGroup' untuk menjalankan pemfilteran tag grup sumber daya di sisi server
* Cmdlet Extended Tag untuk menerima -ResourceId
    - Get-AzTag -ResourceId
    - New-AzTag -ResourceId
    - Remove-AzTag -ResourceId
* Cmdlet Tag baru yang ditambahkan
    - Update-AzTag -ResourceId
* Brought ScopedDeployment dari SDK 3.3.0

#### <a name="azsql"></a>az.sql
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Menambahkan dukungan untuk konfigurasi pencadangan Penyimpanan Jangka Panjang untuk Database Terkelola
    - Mendapatkan/Mengatur kebijakan LTR di database terkelola
    - Mendapatkan cadangan LTR dengan database terkelola, instans terkelola, atau menurut lokasi
    - Menghapus cadangan LTR
    - Memulihkan cadangan LTR untuk membuat database terkelola baru
* Menambahkan MinimalTlsVersion ke New-AzSqlServer dan Set-AzSqlServer
* Menambahkan MinimalTlsVersion ke New-AzSqlInstance dan Set-AzSqlInstance
* Benturan SQL SDK untuk Az.Network

#### <a name="azstorage"></a>Az.Storage
* Supported AllowProtectedAppendWrite in ImmutabilityPolicy
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
* Pesan peringatan perubahan yang ditambahkan untuk perubahan tipe AzureStorageTable dalam rilis mendatang
    - 'New-AzStorageTable'
    - 'Get-AzStorageTable'

#### <a name="azwebsites"></a>Situs Web Az.
* Menambahkan parameter Tag untuk 'New-AzAppServicePlan' dan 'Set-AzAppServicePlan'
* Menghentikan eksekusi cmdlet jika pengecualian dilakukan saat menambahkan domain kustom ke situs web
* Dukungan tambahan untuk menjalankan operasi untuk Layanan Aplikasi tidak berada dalam grup sumber daya yang sama dengan Paket Layanan Aplikasi
* Pembatasan akses yang diterapkan untuk WebApp/Function di grup sumber daya yang berbeda
* Memperbaiki masalah dalam mengatur nama host kustom untuk WebAppSlots

## <a name="350---february-2020"></a>3.5.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama terakhir
* Telemetri sisi klien yang diperbarui.
* Az.IotHub menambahkan cmdlet untuk mendukung pengelolaan perangkat.
* Az.SqlVirtualMachine menambahkan cmdlet untuk Pendengar Grup Ketersediaan.

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Id SubscriptionId, TenantId, dan waktu eksekusi ke data telemetri sisi klien

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan ketik di Contoh 1 dalam dokumentasi referensi untuk 'New-AzAutomationSoftwareUpdateConfiguration'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* SDK yang diperbarui ke 7.0
* Pesan kesalahan yang ditingkatkan ketika respons server isi kosong

#### <a name="azcompute"></a>Az.Compute
* Nilai kosong yang diperbolehkan untuk ProximityPlacementGroupId selama pembaruan

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Cmdlet ditambahkan untuk mendapatkan definisi aturan terkelola yang dapat digunakan di WAF

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola perangkat di Hub Iot. Cmdlet Baru adalah:
    - 'Add-AziotHubDevice'
    - 'Get-AziotHubDevice'
    - 'Remove-AziotHubDevice'
    - 'Set-AziotHubDevice'

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki teks duplikat untuk Add-AzKeyVaultKey.md

#### <a name="azmonitor"></a>Az.Monitor
* Deskripsi tetap tentang cmdlet Get-AzLog baru.
* Parameter baru yang disebut ActionGroupId ditambahkan ke perintah 'New-AzMetricAlertRuleV2'.
    - Pengguna dapat menyediakan ActionGroupId(string) atau ActionGorup(ActivityLogAlertActionGroup).

#### <a name="aznetwork"></a>Az.Network
* Menambahkan satu catatan parameter tambahan untuk parameter '-EnableProxyProtocol' untuk cmdlet 'New-AzPrivateLinkService'.
* Memperbaiki contoh FilterData di Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Contoh Penangkapan Paket ditambahkan untuk merekam semua paket dalam dan luar Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Kebijakan Azure Firewall yang Didukung di VNet Firewalls
    - Tidak ada cmdlet baru yang ditambahkan. Relaxing the restriction for firewall policy on VNet firewalls

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Dukungan untuk Pemulihan file untuk SQL Database.

#### <a name="azresources"></a>Az.Resources
* Cmdlet penyebaran templat refactored
    - Menambahkan cmdlet baru untuk mengelola penyebaran di grup manajemen: *-AzManagementGroupDeployment
    - Menambahkan cmdlet baru untuk mengelola penyebaran dalam lingkup penyewa: *-AzTenantDeployment
    - Cmdlet Refactored *-AzDeployment untuk bekerja secara khusus pada lingkup langganan
    - Alias yang dibuat *-AzSubscriptionDeployment untuk *-AzDeployment cmdlets
* Fixed 'Update-AzADApplication' when parameter 'AvailableToOtherTenants' is not set
* Menghapus ApplicationObjectWithoutCredentialParameterSet untuk menghindari AmbiguousParameterSetException.
* File bantuan yang digenerasi

#### <a name="azsql"></a>az.sql
* Menambahkan dukungan untuk titik langganan silang dalam pemulihan waktu pada Instans Terkelola.
* Menambahkan dukungan untuk mengubah generasi perangkat keras Sql Managed Instance yang sudah ada
* Memperbaiki contoh bantuan 'Update-AzSqlServerVulnerabilityAssessmentSetting': parameter/output properti - EmailAdmins

#### <a name="azsqlvirtualmachine"></a>az.sqlVirtualMachine
* Cmdlet yang ditambahkan untuk Pendengar Grup Ketersediaan

#### <a name="azstoragesync"></a>Az.StorageSync
* Kumpulan karakter yang didukung yang diperbarui di 'Invoke-AzStorageSyncCompatibilityCheck'.

## <a name="340---february-2020"></a>3.4.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama terakhir
* Az.CosmosDB versi awal 0.1.0 dirilis
* Dukungan Az.Network ConnectionMonitor V2 ditambahkan

#### <a name="azaccounts"></a>Az.Accounts
* Menonaktifkan penyimpanan otomatis konteks ketika AzureRmContext.json tidak tersedia
* Memperbarui referensi ke Azure Powershell Common ke pratinjau 1.3.5

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Get-AzApiManagementApiSchema** Memperbaiki Open-Api Schema yang terkait dengan API   https://github.com/Azure/azure-powershell/issues/10626
* **New-AzApiManagementProduct** _ and _ *Set-AzApiManagementProduct**
  - Perbaiki dokumentasi untuk https://github.com/Azure/azure-powershell/issues/10472
* **Set-AzApiManagementApi** Contoh tambahan untuk memperlihatkan cara memperbarui ServiceUrl menggunakan cmdlet

#### <a name="azcompute"></a>Az.Compute
* Batasi jumlah status VM menjadi 100 agar terhindar dari pembatasan saat Get-AzVM -Status dijalankan tanpa nama VM.
* Menambahkan Update-AzDiskEncryptionSet cmdlet
* Tambahkan parameter EncryptionType dan DiskEncryptionSetId ke cmdlet berikut:
    - New-AzDiskUpdateConfig, New-AzSnapshotUpdateConfig
* Tambahkan parameter ColocationStatus Get-AzProximityPlacementGroup cmdlet.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.7.0

#### <a name="azdeploymentmanager"></a>az.deploymentmanager
* Menambahkan operasi LIST untuk sumber daya
* Menambahkan kemampuan untuk menjalankan operasi pada langkah-langkah Pemeriksaan Kesehatan

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki kesalahan dokumen New-AzHDInsightCluster.

#### <a name="azkeyvault"></a>Az.KeyVault
* Tambahkan alias Nama ke atribut VaultName agar Remove-AzureKeyVault konsisten dengan New-AzureKeyVault.

#### <a name="aznetwork"></a>Az.Network
* Contoh baru yang ditambahkan Set-AzNetworkWatcherConfigFlowLog.md menunjukkan skenario Analitik Lalu Lintas yang dinonaktifkan.
* Tambahkan dukungan untuk menetapkan konfigurasi IP manajemen ke Azure Firewall - subnet khusus dan IP Publik yang akan digunakan firewall untuk lalu lintas manajemennya
    - Cmdlet New-AzFirewall diperbarui:
        - Parameter yang ditambahkan -ManagementPublicIpAddress (tidak wajib) yang menerima objek Alamat IP Publik
        - Metode yang ditambahkan SetManagementIpConfiguration pada objek firewall - memerlukan subnet dan alamat IP Publik sebagai input - nama subnet harus 'AzureFirewallManagementSubnet'
* Contoh Get-AzNetworkSecurityGroup yang diperbaiki agar memperlihatkan contoh untuk NSG, bukan antarmuka jaringan.
* Memperbaiki kesalahan ketik New-AzVpnSite perintah yang mencegah selesainya id sumber daya menyelesaikan parameter.
* Menambahkan dukungan untuk Konfiugrasi URL dalam Kumpulan Tindakan Tulis Ulang Aturan di Gateway Aplikasi
    - Cmdlet baru ditambahkan:
        - New-AzApplicationGatewayRewriteRuleUrlConfiguration
    - Cmdlet yang diperbarui dengan parameter opsional - UrlConfiguration
        - New-AzApplicationGatewayRewriteRuleActionSet
* Menambahkan suppport untuk NetworkWatcher ConnectionMonitor versi 2 sumber daya

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Mendukung evaluasi kepatuhan sebelum menentukan sumber daya yang perlu diperbaiki
    - Menambahkan parameter '-ResourceDiscoverMode' ke Start-AzPolicyRemediation
* Menambahkan Get-AzPolicyMetadata cmdlet untuk mendapatkan sumber daya metadata kebijakan
* Memperbarui Get-AzPolicyState dan Get-AzPolicyStateSummary untuk API versi 2019-10-01

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk menghapus disk yang direplikasi.
* Azure Backup menambahkan dukungan untuk menambahkan tag saat membuat Vault Layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Buat -Scope opsional dalam cmdlet *-AzPolicyAssignment dengan default untuk langganan konteks
* Tambahkan contoh pembuatan ADServicePrincipal dengan kata sandi dan kredensial kunci

#### <a name="azsql"></a>az.sql
Perbaiki New-AzSqlDatabaseSecondary cmdlet untuk memeriksa keberadaan PartnerDatabaseName dan bukan keberadaan DatabaseName.

#### <a name="azstorage"></a>Az.Storage
* Kumpulan dukungan yang diatur dalam Enkripsi Keytype Tabel/Antrean dalam Storage Ini
    - New-AzStorageAccount
* Memperlihatkan RequestId saat StorageException tidak memiliki ExtendedErrorInformation
* Memperbaiki perintah cmdlet Contoh 6 Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Situs Web Az.
* Set-AzWebapp dan Set-AzWebappSlot mendukung properti AlwaysOn, MinTls, dan FtpsState
* Memperbaiki masalah ketika mengatur HttpsOnly bersama dengan mengubah AppservicePlan secara bersamaan menggunakan Perintah Set-AzWebApp tunggal, mengatur ulang HttpsOnly ke nilai default

## <a name="330---january-2020"></a>3.3.0 - Januari 2020
#### <a name="azaccounts"></a>Az.Accounts
* Pembaruan Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAttestationServiceEndpointResourceId dan AzureAttestationServiceEndpointUpdatefix

#### <a name="azcdn"></a>Az.Cdn
* Menampilkan detail respons kesalahan New-AzCdnEndpoint cmdlet

#### <a name="azcompute"></a>Az.Compute
* Perbaiki Set-AzVMCustomScriptExtension cmdlet untuk VM dengan disk OD terkelola yang tidak memiliki profil OS.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Nama parameter tetap yang digunakan oleh contoh New-AzContainerGroup

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Cmdlet tambahan 'Get-AzDataBoxEdgeStorageContainer'
  - Dapatkan Wadah Storage Edge
* Cmdlet tambahan 'New-AzDataBoxEdgeStorageContainer'
  - Buat Wadah Edge Edge baru
* Cmdlet tambahan 'Remove-AzDataBoxEdgeStorageContainer'
  - Menghapus Wadah Storage Edge
* Cmdlet yang ditambahkan 'Invoke-AzDataBoxEdgeStorageContainer'
  - Tindakan invoke untuk melakukan refresh data di Edge Storage Container
* Cmdlet tambahan 'Get-AzDataBoxEdgeStorageAccount'
  - Dapatkan Akun Storage Edge
* Menambahkan cmdlet 'New-AzDataBoxEdgeStorageAccount'
  - Buat Akun Storage Edge baru
* Cmdlet tambahan 'Remove-AzDataBoxEdgeStorageAccount'
  - Menghapus Akun Storage Edge
* Invoke cmdlet 'Invoke-AzDataBoxEdgeShare'
  - Menjalankan tindakan untuk merefresh data saat berbagi
* Cmdlet ditambahkan 'Set-AzDataBoxEdgeStorageAccountCredential'
  - Mengatur kredensial akun penyimpanan az databoxedge

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan properti AutoUpdateETA, LatestVersion, PushedVersion, TaskQueueId, dan VersionStatus untuk Get-AzDataFactoryV2IntegrationRuntime cmd
* Memperbarui versi .Net SDK ADF ke versi 4.6.0
* Tambahkan parameter 'PublicIPs' untuk 'Set-AzureRmDataFactoryV2IntegrationRuntime' cmd untuk mengaktifkan buat Azure-SSIS IR dengan alamat IP publik statis.

#### <a name="azdevtestlabs"></a>Az.DevTestLabs
* Menghapus tautan yang rusak di Get-AzDtlAllowedVMSizesPolicy.md

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan untuk masalah 10634 : Memperbaiki referensi Objek null untuk menghapus eventhubnamespace

#### <a name="azhdinsight"></a>Az.HDInsight
* Perbaiki Invoke-AzHDInsightHiveJob.md kesalahan.

#### <a name="azmachinelearning"></a>Az.MachineLearning
* Dihapus di bawah cmdlet karena MachineLearningCompute tidak tersedia lagi
  - Get-AzMlOpCluster
  - Get-AzMlOpClusterKey
  - New-AzMlOpCluster
  - Remove-AzMlOpCluster
  - Set-AzMlOpCluster
  - Test-AzMlOpClusterSystemServicesUpdateAvailability
  - Update-AzMlOpClusterSystemService

#### <a name="aznetwork"></a>Az.Network
* Memutakhirkan dependensi Microsoft.Azure.Management.Sql dari pratinjau 1.36 ke pratinjau 1.37

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan perubahan Pemulihan Situs Azure untuk disk terkelola vms encrypted at rest dengan kunci terkelola pelanggan bagi Azure ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk memasukkan enkripsi disk Atur Id sebagai input opsional pada mengaktifkan proteksi untuk Vmware ke Azure.
* Dukungan Pemulihan Situs Azure untuk memasukkan enkripsi disk Atur Id sebagai input opsional pada tingkat disk untuk mengaktifkan proteksi vmware ke Azure.
* Dukungan Pemulihan Situs Azure untuk memperbarui item replikasi yang dilindungi dengan enkripsi disk yang diatur Peta untuk HyperV ke Azure.

#### <a name="azresources"></a>Az.Resources
* Perbaiki kesalahan dalam dokumen bantuan dari 'Remove-AzTag'.

#### <a name="azsql"></a>az.sql
* Perbaiki penilaian kerentanan yang mengatur fungsionalitas cmdlet baseline agar berfungsi di master db untuk database Azure dan membatasinya pada database sistem instans terkelola.
* Memperbaiki kesalahan saat membuat SQL grup failover contoh

#### <a name="azsqlvirtualmachine"></a>az.sqlVirtualMachine
* Tambahkan DR sebagai tipe Lisensi baru yang valid

#### <a name="azstorage"></a>Az.Storage
* Pesan peringatan tambahkan perubahan untuk perubahan DefaultAction Value dalam rilis yang akan datang
    - Update-AzStorageAccountNetworkRuleSet
* Dukungan Dapatkan waktu sinkronisasi terakhir akun Storage dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeGeoReplicationStats
    - Get-AzureRMStorageAccount

## <a name="320---december-2019"></a>3.2.0 - Desember 2019

### <a name="general"></a>Umum
* Referensi pembaruan dalam .psd1 untuk menggunakan jalur relatif untuk semua modul

#### <a name="azaccounts"></a>Az.Accounts
* Mengatur UserAgent yang benar untuk telemetri pihak klien untuk pratinjau Az 4.0
* Menampilkan pesan kesalahan yang ramah pengguna saat konteks null di az 4.0 pratinjau

#### <a name="azbatch"></a>Az.Batch
* Perbaiki masalah [#10602,](https://github.com/Azure/azure-powershell/issues/10602)ketika **New-AzBatchPool** tidak mengirimkan 'VirtualMachineConfiguration.ContainerConfiguration' atau 'VirtualMachineConfiguration.DataDisks' ke server.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.5.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Dukungan pengecualian aturan terkelola WAF yang ditambahkan
* Menambahkan SocketAddr ke lengkapi-otomatis

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Penanganan Pengecualian

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki nilai pengaksesan kesalahan yang berpotensi tidak diatur
* Pengelolaan Sertifikat Kriptografi Kurva Elliptic
    - Ditambahkan dukungan untuk menentukan Kurva untuk Kebijakan Sertifikat

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan argumen opsional ke perintah tambahkan Pengaturan Diagnostik. Argumen sakelar yang jika ada menunjukkan bahwa ekspor ke Analitik Log harus ke skema tetap (alias khusus, tipe data)

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk IpGroup di AzureFirewall Application,Nat & Network Rules.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah penyebaran templat yang gagal membaca parameter templat jika namanya berkonflik dengan beberapa nama parameter bawaan.
* Cmdlet kebijakan yang diperbarui untuk menggunakan api versi 2019-09-01 yang memperkenalkan dukungan kelompok di dalam definisi kumpulan kebijakan.

#### <a name="azsql"></a>az.sql
* Peningkatan pembuatan penyimpanan di Penilaian Kerentanan otomatis diaktifkan ke StorageV2

#### <a name="azstorage"></a>Az.Storage
* Dukungan menghasilkan token SAS berbasis Idenitas Blob/Constainer dengan Storage Konteks berdasarkan autentikasi Oauth
    - New-AzStorageContainerSASToken
    - New-AzStorageBlobSASToken
* Dukungan mencabut Storage Delegasi Pengguna Akun, sehingga semua token SAS Idenity dicabut
    - Revoke-AzStorageAccountUserDelegationKeys
* Mutakhirkan ke Microsoft.Azure.Management. Storage 14.2.0, untuk mendukung API versi baru 2019-06-01.
* Dukungan QuotaGiB (Share Quota in Gibibye) untuk nilai lebih dari 5120 dalam bidang Manajemen dari cmdlet Berbagi File dan menambahkan alias parameter 'Quota' ke parameter 'QuotaGiB'.
    - New-AzRmStorageShare
    - Update-AzRmStorageShare
* Menambahkan alias parameter 'QuotaGiB' ke parameter 'Quota'
    - Set-AzStorageShareQuota
* Memperbaiki masalah yang Set-AzStorageContainerAcl membersihkan Kebijakan Akses yang disimpan
    - Set-AzStorageContainerAcl

## <a name="310---november-2019"></a>3.1.0 - November 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama terakhir
* Az.DataBoxEdge 1.0.0 dirilis
* Az.SqlVirtualMachine 1.0.0 dirilis

#### <a name="azcompute"></a>Az.Compute
* Fitur Reapply VM
    - Menambahkan menerapkan kembali parameter Set-AzVM cmdlet
* Fitur Atur Balasan Otomatis Vm Scale Set:
    - Tambahkan parameter EnableAutomaticRepair, AutomaticRepairGracePeriod, dan AutomaticRepairMaxInstanceRepairsPercent ke cmdlet berikut: New-AzVmssConfig Update-AzVmss
* Dukungan gambar galeri penyewa silang untuk New-AzVM
* Menambahkan 'Titik' ke selesai argumen parameter Prioritas dalam cmdlet New-AzVM, New-AzVMConfig New-AzVmss baru
* Menambahkan parameter DiskIOPSReadWrite dan DiskMBpsReadWrite Add-AzVmssDataDisk cmdlet
* Ubah parameter SourceImageId dari cmdlet New-AzGalleryImageVersion ke opsional
* Menambahkan PARAMETER OSDiskImage dan DataDiskImage New-AzGalleryImageVersion cmdlet
* Menambahkan parameter HyperVGeneration New-AzGalleryImageDefinition cmdlet
* Menambahkan parameter SkipExtensionsOnOverprovisionedVMs ke cmdlet New-AzVmss, New-AzVmssConfig Update-AzVmss baru

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Cmdlet yang ditambahkan `Get-AzDataBoxEdgeOrder`
    - Dapatkan Pesanan
* Cmdlet yang ditambahkan `New-AzDataBoxEdgeOrder`
    - Buat Pesanan baru
* Cmdlet yang ditambahkan `Remove-AzDataBoxEdgeOrder`
    - Hapus Urutan
* Ubah dalam cmdlet `New-AzDataBoxEdgeShare`
    - Kini, buat Berbagi Lokal
* Cmdlet yang ditambahkan `Set-AzDataBoxEdgeRole`
    - Sekarang PeranRol bisa dipetakan ke Bagikan
* Cmdlet yang ditambahkan `Invoke-AzDataBoxEdgeDevice`
    - Menggunakan pembaruan pemindaian, mengunduh pembaruan, menginstal pembaruan pada perangkat
* Cmdlet yang ditambahkan `Get-AzDataBoxEdgeTrigger`
    - Mendapatkan informasi tentang Pemicu
* Cmdlet yang ditambahkan `New-AzDataBoxEdgeTrigger`
    - Membuat Pemicu baru
* Cmdlet yang ditambahkan `Remove-AzDataBoxEdgeTrigger`
    - Hapus Pemicu

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.4.0
* Tambahkan parameter 'ExpressCustomSetup' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan konfigurasi penyiapan dan komponen pihak ke-3 tanpa skrip penyiapan kustom.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Dokumentasi pembaruan Get-AzDataLakeStoreDeletedItem dan Restore-AzDataLakeStoreDeletedItem

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan untuk masalah 10301 : Memperbaiki format tanggal Token SAS

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan parameter MinimumTlsVersion ke Enable-AzFrontDoorCustomDomainHttps dan New-AzFrontDoorFrontendEndpointObject
* Menambahkan parameter HealthProbeMethod dan EnabledState New-AzFrontDoorHealthProbeSettingObject
* Menambahkan cmdlet baru untuk membuat backendPoolsSettings objec untuk memasukkan pembuatan/pembaruan Pintu Depan
    - New-AzFrontDoorBackendPoolsSettingObject

#### <a name="aznetwork"></a>Az.Network
* Mengubah contoh opsi FilterData 'Start-AzVirtualNetworkGatewayConnectionPacketCapture.md' dan 'Start-AzVirtualnetworkGatewayPacketCapture.md' FilterData.

#### <a name="azprivatedns"></a>Az.PrivateDns
* Memperbarui PrivateDns .net sdk ke versi 1.0.0

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk memilih tipe disk untuk mengaktifkan proteksi.
* Perbaikan bug Pemulihan Situs Azure untuk pengeditan tindakan rencana pemulihan.
* Azure Backup SQL Pulihkan untuk menerima DBs filestream.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'MinimumTlsVersion' dalam cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'. Selain itu, ditambahkan 'MinimumTlsVersion' dalam output cmdlet 'Get-AzRedisCache'.
* Validasi tambahan pada parameter '-Size' untuk cmdlet 'Set-AzRedisCache' dan 'New-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
- Cmdlet kebijakan yang diperbarui untuk menggunakan versi api baru 2019-06-01 yang memiliki properti EnforcementMode baru dalam penetapan kebijakan.
- Contoh bantuan pembuatan definisi kebijakan yang diperbarui
- Perbaiki bug Remove-AZADServicePrincipal -ServicePrincipalName, memberikan referensi null saat nama prinsipal layanan tidak ditemukan.
- Memperbaiki bug New-AZADServicePrincipal, memberikan referensi null saat penyewa tidak memiliki langganan apa pun.
- Ubah New-AzAdServicePrincipal menambahkan kredensial ke aplikasi terkait saja.

#### <a name="azsql"></a>az.sql
* Menambahkan dukungan untuk database ReadReplicaCount.
* Perbaikan Set-AzSqlDatabase ketika kelebihan zona tidak diatur

## <a name="300---november-2019"></a>3.0.0 - November 2019
### <a name="general"></a>Umum
* Az.PrivateDns 1.0.0 released

#### <a name="azaccounts"></a>Az.Accounts
* Tambahkan pesan penghentian untuk alias 'Atasi Kesalahan'.

#### <a name="azadvisor"></a>Az.Advisor
* Menambahkan kategori baru 'Operasi Operasi' ke Get-AzAdvisorRecommendation cmdlet.

#### <a name="azbatch"></a>Az.Batch
* Diganti `CoreQuota` namanya `BatchAccountContext` menjadi `DedicatedCoreQuota` . Ada juga yang `LowPriorityCoreQuota` baru.
  - Hal ini memengaruhi **Get-AzBatchAccount**.
* **New-AzBatchTask** `-ResourceFile` parameter sekarang mengambil kumpulan `PSResourceFile` objek, yang bisa dibuat menggunakan cmdlet **New-AzBatchResourceFile** baru.
* Cmdlet **New-AzBatchResourceFile** baru untuk membantu membuat `PSResourceFile` objek. Ini bisa disediakan untuk **New-AzBatchTask** pada `-ResourceFile` parameter.
  - Ini mendukung dua jenis file sumber daya baru selain cara yang sudah `HttpUrl` ada:
    - `AutoStorageContainerName` file sumber daya berbasis mengunduh seluruh wadah penyimpanan otomatis ke node Batch.
    - `StorageContainerUrl` file sumber daya berbasis mengunduh wadah yang ditentukan dalam URL ke node Batch.
* Properti `ApplicationPackages` yang dihapus dari yang dikembalikan oleh `PSApplication` **Get-AzBatchApplication**.
  - Paket tertentu di dalam aplikasi sekarang bisa diambil menggunakan **Get-AzBatchApplicationPackage**. Misalnya: `Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication` .
* Diubah namanya menjadi `ApplicationId` `ApplicationName` di **Get-AzBatchApplicationPackage**, **New-AzBatchApplicationPackage**, **Remove-AzBatchApplicationPackage**, **Get-AzBatchApplication**, **New-AzBatchApplication**, **Remove-AzBatchApplication**, dan **Set-AzBatchApplication**.
  - `ApplicationId` sekarang adalah alias `ApplicationName` dari .
* Menambahkan properti `PSWindowsUserConfiguration` baru ke `PSUserAccount` .
* Diubah `Version` namanya `Name` menjadi pada `PSApplicationPackage` .
* Diubah `BlobSource` namanya `HttpUrl` menjadi pada `PSResourceFile` .
* Properti `OSDisk` yang dihapus dari `PSVirtualMachineConfiguration` .
* Removed **Set-AzBatchPoolOSVersion**. Operasi ini tidak lagi didukung.
* Dihapus `TargetOSVersion` dari `PSCloudServiceConfiguration` .
* Diubah `CurrentOSVersion` namanya `OSVersion` menjadi pada `PSCloudServiceConfiguration` .
* Dihapus `DataEgressGiB` dan `DataIngressGiB` dari `PSPoolUsageMetrics` .
* Menghapus **Get-AzBatchNodeAgentSku** dan menggantinya dengan  **Get-AzBatchSupportedImage**.
  - **Get-AzBatchSupportedImage** mengembalikan data yang sama seperti **Get-AzBatchNodeAgentSku** tetapi dalam format yang lebih mudah dikenal.
  - Gambar baru yang tidak diverifikasi kini juga dikembalikan. Informasi tambahan tentang `Capabilities` dan untuk setiap gambar juga `BatchSupportEndOfLife` disertakan.
* Menambahkan kemampuan untuk memasang sistem file jarak jauh pada setiap simpul pool melalui `MountConfiguration` parameter baru **New-AzBatchPool**.
* Sekarang mendukung aturan keamanan jaringan yang memblokir akses jaringan ke pool berdasarkan port sumber lalu lintas. Ini dilakukan melalui `SourcePortRanges` properti di `PSNetworkSecurityGroupRule` .
* Ketika menjalankan wadah, Kumpulan kini mendukung eksekusi tugas dalam direktori kerja wadah atau direktori kerja tugas Kumpulan. Ini dikontrol oleh properti `WorkingDirectory` pada `PSTaskContainerSettings` .
* Kemampuan tambahan untuk menentukan kumpulan IP publik melalui `PSNetworkConfiguration` properti `PublicIPs` baru. Ini menjamin node di Pool akan memiliki IP dari daftar pengguna yang disediakan IP.
* Ketika tidak ditentukan, nilai default `WaitForSuccess` dari `PSSTartTask` pada sekarang `$True` (adalah `$False` ).
* Ketika tidak ditentukan, nilai default `Scope` dari on `PSAutoUserSpecification` sekarang `Pool` (berada pada Windows dan di `Task` `Pool` Linux).

#### <a name="azcdn"></a>Az.Cdn
* Memperkenalkan UrlRewriteAction dan CacheKeyQueryStringAction ke RulesEngine.
* Memperbaiki beberapa bug seperti Input 'Pemilih' yang hilang New-AzDeliveryRuleCondition cmdlet.

#### <a name="azcompute"></a>Az.Compute
* Fitur Kumpulan Enkripsi Disk
    - Cmdlet baru: New-AzDiskEncryptionSetConfig New-AzDiskEncryptionSet Get-AzDiskEncryptionSet Remove-AzDiskEncryptionSet
    - Parameter DiskEncryptionSetId ditambahkan ke cmdlet berikut: Set-AzImageOSDisk Set-AzVMOSDisk Set-AzVmssStorageProfile Add-AzImageDataDisk New-AzVMDataDisk Set-AzVMDataDisk Add-AzVMDataDisk Add-AzVmssDataDisk Add-AzVmssVMDataDisk
    - Parameter DiskEncryptionSetId dan EncryptionType ditambahkan ke cmdlet berikut: New-AzDiskConfig New-AzSnapshotConfig
* Menambahkan parameter PublicIPAddressVersion ke New-AzVmssIPConfig
* Pindahkan FileUris ekstensi skrip kustom dari pengaturan publik ke pengaturan terproteksi
* Menambahkan ScaleInPolicy ke cmdlet New-AzVmss, New-AzVmssConfig Update-AzVmss baru
* Memutus perubahan
    - Parameter UploadSizeInBytes digunakan sebagai ganti DiskSizeGB untuk New-AzDiskConfig saat CreateOption Upload
    - PublishingProfile.Source.ManagedImage.Id diganti dengan gambar StorageProfile.Source.Id dalam objek GalleryImageVersion

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.3.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbarui versi ADLS SDK ( https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-123-alpha) , membawa perbaikan berikut ini
* Hindari memberikan pengecualian saat tidak dapat deserialisasi saat pembuatan entri direktori atau sampah.
* Mengekspos pengaturan per waktu habis permintaan di klien iklan
* Perbaikan menyampaikan bendera sinkronisasi asli untuk pemulihan badoffset
* Perbaiki EnumerateDirectory untuk mengambil token kelanjutan setelah respons dicentang
* Memperbaiki Bug Concat

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbaiki kesalahan ketik lain di seluruh modul

#### <a name="azhdinsight"></a>Az.HDInsight
* Perbaikan bug yang akan dapatkan kesalahan 'Bukan string Basis-64 yang valid' ketika menggunakan Get-AzHDInsightCluster untuk mendapatkan kluster dengan penyimpanan ADLSGen1.
* Tambahkan parameter bernama 'ApplicationId' ke tiga cmdlet Add-AzHDInsightClusterIdentity, New-AzHDInsightClusterConfig dan New-AzHDInsightCluster sehingga pelanggan dapat menyediakan id aplikasi prinsipal layanan untuk mengakses Azure Data Lake.
* Mengubah Microsoft.Azure.Management.HDInsight dari 2.1.0 menjadi 5.1.0
* Menghapus lima cmdlet:
    - Get-AzHDInsightOMS
    - Enable-AzHDInsightOMS
    - Disable-AzHDInsightOMS
    - Grant-AzHDInsightRdpServicesAccess
    - Revoke-AzHDInsightRdpServicesAccess
* Menambahkan tiga cmdlet:
    - Get-AzHDInsightMonitoring mengganti Get-AzHDInsightOMS.
    - Enable-AzHDInsightMonitoring mengganti Enable-AzHDInsightOMS.
    - Disable-AzHDInsightMonitoring mengganti Disable-AzHDInsightOMS.
* Fixed cmdlet Get-AzHDInsightProperties to support get capabilities information from a specific location.
* Removed parameter sets('Spark1', 'Spark2') from Add-AzHDInsightConfigValue.
* Tambahkan contoh ke dokumen bantuan cmdlet Add-AzHDInsightSecurityProfile.
* Tipe output yang diubah dari cmdlet berikut:
*  - Mengubah tipe output dari Get-AzHDInsightProperties CapabilitiesResponse menjadi AzureHDInsightCapabilities.
*  - Mengubah tipe output tipe Remove-AzHDInsightCluster ClusterGetResponse menjadi bool.
*  - Mengubah tipe output dari Set-AzHDInsightGatewaySettings HttpConnectivitySettings menjadi GatewaySettings.
* Menambahkan beberapa kasus uji skenario.
* Hapus beberapa alias: 'Add-AzHDInsightConfigValues', 'Get-AzHDInsightProperties'.

#### <a name="aziothub"></a>Az.IotHub
* Memutus perubahan:
    - Cmdlet 'Add-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter '__AllParameterSets' untuk cmdlet 'Add-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Get-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter '__AllParameterSets' untuk cmdlet 'Get-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Properti 'OperationsMonitoringProperties' dari tipe 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubProperties' telah dihapus.
    - 'OperationsMonitoringProperties' properti dari tipe 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubInputProperties' telah dihapus.
    - Cmdlet 'New-AzIotHubExportDevice' tidak lagi mendukung alias 'New-AzIotHubExportDevices'.
    - Cmdlet 'New-AzIotHubImportDevice' tidak lagi mendukung alias 'New-AzIotHubImportDevices'.
    - Cmdlet 'Remove-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter '__AllParameterSets' untuk cmdlet 'Remove-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Set-AzIotHub' tidak lagi mendukung parameter 'OperationsMonitoringProperties' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter 'UpdateOperationsMonitoringProperties' untuk cmdlet 'Set-AzIotHub' telah dihapus.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk mengonfigurasi sumber daya jaringan seperti NSG, IP publik, dan penyeimbang muat internal bagi Azure untuk Azure.
* Dukungan Pemulihan Situs Azure untuk menulis ke disk terkelola vMWare ke Azure.
* Dukungan Pemulihan Situs Azure untuk pengurangan NIC untuk vMWare ke Azure.
* Dukungan Pemulihan Situs Azure untuk mempercepat jaringan bagi Azure ke Azure.
* Dukungan Pemulihan Situs Azure untuk agen pembaruan otomatis bagi Azure ke Azure.
* Dukungan Pemulihan Situs Azure untuk SSD Standar untuk Azure ke Azure.
* Dukungan Pemulihan Situs Azure untuk Enkripsi Disk Azure dua pass untuk Azure ke Azure.
* Dukungan Pemulihan Situs Azure untuk melindungi disk yang baru saja ditambahkan bagi Azure ke Azure.
* Menambahkan fitur SoftDelete untuk VM dan menambahkan uji untuk softdelete

#### <a name="azresources"></a>Az.Resources
* Perbarui dependensi perakitan Microsoft.Extensions.Caching.Memory dari 1.1.1 hingga 2.2

#### <a name="aznetwork"></a>Az.Network
* Ubah semua cmdlet untuk PrivateEndpointConnection untuk mendukung penyedia layanan generik.
    - Cmdlet yang diperbarui:
        - Approve-AzPrivateEndpointConnection
        - Deny-AzPrivateEndpointConnection
        - Get-AzPrivateEndpointConnection
        - Remove-AzPrivateEndpointConnection
        - Set-AzPrivateEndpointConnection
* Tambahkan cmdlet baru untuk PrivateLinkResource dan juga mendukung penyedia layanan generik.
    - Cmdlet baru:
        - Get-AzPrivateLinkResource
* Tambahkan bidang dan parameter baru untuk fitur Protokol Proksi V2.
    - Tambahkan properti EnableProxyProtocol di PrivateLinkService
    - Add property LinkIdentifier in PrivateEndpointConnection
    - Diperbarui New-AzPrivateLinkService menambahkan parameter opsional baru EnableProxyProtocol.
* Memperbaiki deskripsi parameter yang salah dalam dokumentasi referensi 'New-AzApplicationGatewaySku'
* Cmdlet baru untuk mendukung kebijakan firewall Azure
* Menambahkan dukungan untuk RouteTables sumber daya anak VirtualHub
    - Cmdlet baru ditambahkan:
        - Add-AzVirtualHubRoute
        - Add-AzVirtualHubRouteTable
        - Get-AzVirtualHubRouteTable
        - Remove-AzVirtualHubRouteTable
        - Set-AzVirtualHub
* Menambahkan dukungan untuk properti baru Sku VirtualHub dan VirtualWANType dari VirtualWan
    - Cmdlet yang diperbarui dengan parameter opsional:
        - New-AzVirtualHub : Sku parameter yang ditambahkan
        - Update-AzVirtualHub : Sku parameter yang ditambahkan
        - New-AzVirtualWan : parameter tambahan VirtualWANType
        - Update-AzVirtualWan : parameter tambahan VirtualWANType
* Tambahkan dukungan untuk properti EnableInternetSecurity untuk HubVnetConnection, VpnConnection, dan ExpressRouteConnection
    - Cmdlet baru ditambahkan:
        - Update-AzureRmVirtualHubVnetConnection
    - Cmdlet yang diperbarui dengan parameter opsional:
        - New-AzureRmVirtualHubVnetConnection : parameter tambahan EnableInternetSecurity
        - New-AzureRmVpnConnection : parameter tambahan EnableInternetSecurity
        - Update-AzureRmVpnConnection : parameter tambahan EnableInternetSecurity
        - New-AzureRmExpressRouteConnection : parameter tambahan EnableInternetSecurity
        - Set-AzureRmExpressRouteConnection : parameter tambahan EnableInternetSecurity
* Menambahkan dukungan untuk Mengonfigurasi Kebijakan TopLevel WebApplicationFirewall
    - Cmdlet baru ditambahkan:
        - New-AzApplicationGatewayFirewallPolicySetting
        - New-AzApplicationGatewayFirewallPolicyExclusion
        - New-AzApplicationGatewayFirewallPolicyManagedRuleGroupOverride
        - New-AzApplicationGatewayFirewallPolicyManagedRuleOverride
        - New-AzApplicationGatewayFirewallPolicyManagedRule
        - New-AzApplicationGatewayFirewallPolicyManagedRuleSet
    - Cmdlet yang diperbarui dengan parameter opsional:
        - New-AzApplicationGatewayFirewallPolicy : added parameter PolicySetting, ManagedRule
* Menambahkan dukungan untuk Geo-Match operator di CustomRule
    - Menambahkan GeoMatch ke operator di FirewallCondition
* Menambahkan dukungan untuk pendengar dan kebijakan firewall perSitus
    - Cmdlet yang diperbarui dengan parameter opsional:
        - New-AzApplicationGatewayHttpListener : parameter tambahan FirewallPolicy, FirewallPolicyId
        - New-AzApplicationGatewayPathRuleConfig : parameter tambahan FirewallPolicy, FirewallPolicyId
* Fix required subnet with name AzureBastionSubnet in 'PSBastion' can be case insensitive
* Dukungan untuk FQDN Tujuan dalam Aturan Jaringan dan FQDN yang Diterjemahkan dalam Aturan NAT untuk Azure Firewall
* Menambahkan dukungan untuk Sumber daya Tingkat Atas RouteTables IpGroup
    - Cmdlet baru ditambahkan:
        - New-AzIpGroup
        - Remove-AzIpGroup
        - Get-AzIpGroup
        - Set-AzIpGroup

#### <a name="azservicefabric"></a>az.servicefabric
* Hapus Add-AzServiceFabricApplicationCertificate cmdlet karena skenario ini dibahas oleh Add-AzVmssSecret.

#### <a name="azsql"></a>az.sql
* Menambahkan dukungan untuk pemulihan database yang dijatuhkan pada Instans Terkelola.
* Dikemukakan dari cmdlet pengauditan lama kode.
* Alias yang dihapus:
* Get-AzSqlDatabaseIndexRecommendations (gunakan Get-AzSqlDatabaseIndexRecommendation)
* Get-AzSqlDatabaseRestorePoints (gunakan Get-AzSqlDatabaseRestorePoint)
* Hapus Get-AzSqlDatabaseSecureConnectionPolicy cmdlet
* Menghapus alias untuk cmdlet Penilaian Kerentanan yang tidak Pengaturan di tempat
* Hapus cmdlet Advanced Threat Detection Pengaturan baru
* Menambahkan cmdlet ke Menonaktifkan dan mengaktifkan rekomendasi sensitivitas pada kolom dalam database.

#### <a name="azstorage"></a>Az.Storage
* Dukungan untuk mengaktifkan berbagi File Besar ketika membuat atau memperbarui Storage anda
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Ketika menutup/mendapatkan gagang File, lewati periksa jalur inputnya adalah Direktori file atau File, untuk menghindari kegagalan dengan objek di status DeletePending
    -  Get-AzStorageFileHandle
    -  Close-AzStorageFileHandle

## <a name="280---october-2019"></a>2.8.0 - Oktober 2019
### <a name="general"></a>Umum
* Rilis Az.HealthcareApis 1.0.0

#### <a name="azaccounts"></a>Az.Accounts
* Perbarui telemetri dan penulisan ulang URL untuk modul yang dihasilkan, perbaiki tes unit windows.

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Set-AzApiManagementApi** - Dukungan tambahan untuk Memperbarui Api ke Dalam ApiVersionSet
    - Perbaikan masalah https://github.com/Azure/azure-powershell/issues/10068

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki New-AzureAutomationSoftwareUpdateConfiguration cmdlet untuk parameter pengaturan mulai ulang Linux.

#### <a name="azbatch"></a>Az.Batch
* **Get-AzBatchNodeAgentSku** sudah tidak berlaku dan akan diganti oleh **Get-AzBatchSupportImage** di versi 2.0.0.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter Priority, CmdletPolicy, dan MaxPrice New-AzVM dan New-AzVmss cmdlets
* Memperbaiki pesan peringatan dan dokumen bantuan Add-AzVMAdditionalUnattendContent dan Add-AzVMSshPublicKey cmdlet
* Perbaiki pengecualian -skipVmBackup untuk Linux VM dengan disk terkelola untuk Set-AzVMDiskEncryptionExtension.
* Memperbaiki bug dalam pengaturan enkripsi pembaruan dalam skenario Set-AzVMDiskEncryptionExtension, dua pass.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan perintah CRUD untuk aliran data ADF V2: Set-AzDataFactoryV2DataFlow, Remove-AzDataFactoryV2DataFlow, dan Get-AzDataFactoryV2DataFlow.
* Menambahkan perintah tindakan untuk Sesi debug aliran data ADF V2: Start-AzDataFactoryV2DataFlowDe debugSession, Get-AzDataFactoryV2DataFlowDeflowSession, Add-AzDataFactoryV2DataFlowDeflowSessionPackage, Invoke-AzDataFactoryV2DataFlowDebugSessionCommand dan Stop-AzDataFactoryV2DataFlowDeflowSession.
* Memperbarui versi .Net SDK ADF ke versi 4.2.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbaiki validasi akun sehingga akun dengan '-' dapat lolos tanpa domain

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Memperbarui versi powershell ke 1.0.0
* Memperbarui versi SDK ke 1.0.2
* Perbarui dalam uji untuk merujuk ke versi SDK baru
* Memperbarui struktur output dari bertumpuk menjadi diratakan.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan sumber perutean baru: DigitalTwinChangeEvents
* Perbaikan bug minor: Get-AzIothub akan mengembalikan SubscriptionId

#### <a name="azmonitor"></a>Az.Monitor
* Penerima grup tindakan baru ditambahkan untuk grup tindakan -ItsmReceiver -VoiceReceiver -ArmRoleReceiver -AzureFunctionReceiver -LogicAppReceiver -AutomationRunbookReceiver -AzureAppPushReceiver
* Gunakan skema pemberitahuan umum yang diaktifkan untuk penerima. Hal ini tidak berlaku untuk pelanggan SMS, Azure App push , ITSM, dan Voice
* Webhooks kini mendukung autentikasi Azure active directory.

#### <a name="aznetwork"></a>Az.Network
* Tambahkan cmdlet Get-AzAvailableServiceAlias cmdlet baru yang bisa disebut untuk mendapatkan alias yang bisa digunakan untuk Kebijakan Titik Akhir Layanan.
* Menambahkan dukungan untuk menambahkan pemilih lalu lintas ke Virtual Network Gateway Connections
    - Cmdlet baru ditambahkan:
        - New-AzureRmTrafficSelectorPolicy
    - Cmdlet yang diperbarui dengan parameter opsional -TrafficSelectorPolicies -New-AzureRmVirtualNetworkGatewayConnection -Set-AzureRmVirtualNetworkGatewayConnection
* Menambahkan dukungan untuk protokol ESP dan AH dalam konfigurasi aturan keamanan jaringan
    - Cmdlet yang diperbarui:
        - Add-AzNetworkSecurityRuleConfig
        - New-AzNetworkSecurityRuleConfig
        - Set-AzNetworkSecurityRuleConfig
* Meningkatkan penanganan pengecualian dalam cmdlet Cortex
* Generasi Baru dan SKU untuk VirtualNetworkGateway
  - Memperkenalkan Generasi baru untuk VirtualNetworkGateway.
  - Memperkenalkan SKU throughput tinggi yang baru untuk VirtualNetworkGateway.

#### <a name="azrediscache"></a>Az.RedisCache
* Memperbarui dokumentasi referensi 'Set-AzRedisCache' agar menyertakan nilai yang hilang untuk parameter '-Size'

#### <a name="azsql"></a>az.sql
* Add support for setting Active Directory Administrator on Managed Instance

#### <a name="azstorage"></a>Az.Storage
* Memutakhirkan Storage Klien ke 11.1.0
* Wadah daftar dengan API bidang Manajemen, akan di list dengan NextPageLink
    -  Get-AzRmStorageContainer
* Daftar Storage dari langganan, akan di list dengan NextPageLink
    -  Get-AzStorageAccount

#### <a name="azstoragesync"></a>Az.StorageSync
* Perbaiki Masalah 9810 di Reset-AzStorageSyncServerCertificate.

#### <a name="azwebsites"></a>Situs Web Az.
* Set-AzWebApp memperbarui ASP dari aplikasi gagal

## <a name="270---september-2019"></a>2.7.0 - September 2019
#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbarui deskripsi parameter '-Format' dalam dokumentasi referensi 'Set-AzApiManagementPolicy'
* Menghapus referensi cmdlet 'Update-AzApiManagementDeployment' dari dokumentasi referensi. Gunakan 'Set-AzApiManagement' sebagai gantinya.

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki contoh kesalahan ketik dalam dokumentasi referensi untuk 'Register-AzAutomationDscNode'
* Penjelasan tambahan tentang pembatasan OS untuk Register-AzAutomationDSCNode
* Perbaikan Start-AzAutomationRunbook cmdlet Null pengecualian untuk opsi -Wait.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter UploadSizeInBytes parameter tp New-AzDiskConfig
* Menambahkan parameter Penambahan ke New-AzSnapshotConfig
* Menambahkan fitur mesin virtual berprioritas rendah:
    - MaxPrice, parameter Parameter Layanan Dan Prioritas ditambahkan ke New-AzVMConfig.
    - Parameter MaxPrice ditambahkan ke New-AzVmssConfig, Update-AzVM dan Update-AzVmss cmdlet.
* Perbaiki masalah referensi VM Get-AzAvailabilitySet cmdlet ketika cmdlet tersebut mencantumkan semua kumpulan ketersediaan dalam langganan.
* Perbaiki pengecualian null untuk Get-AzRemoteDesktopFile.
* Perbaiki metode VHD Mencari posisi relatif akhir.
* Perbaiki masalah UltraSSD untuk New-AzVM dan Update-AzVM.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan 3 perintah baru untuk ADF V2 - Add-AzDataFactoryV2TriggerSubscription, Remove-AzDataFactoryV2TriggerSubscription, Get-AzDataFactoryV2TriggerSubscriptionStatus
* Memperbarui versi .Net SDK ADF ke 4.1.3

#### <a name="azhdinsight"></a>Az.HDInsight
* Membuat panggilan keluar dari perubahan

#### <a name="aziothub"></a>Az.IotHub
* Tambahkan dukungan untuk membuka failover untuk IotHub ke kawasan pemulihan bencana yang sudah dipasangkan geo.
* Tambahkan dukungan untuk mengelola pengayaan pesan untuk IotHub. Cmdlet baru adalah:
    - Add-AzIotHubMessageEnrichment
    - Get-AzIotHubMessageEnrichment
    - Remove-AzIotHubMessageEnrichment
    - Set-AzIotHubMessageEnrichment

#### <a name="azmonitor"></a>Az.Monitor
* Menunjuk ke MONITOR SDK terbaru, misalnya 0.24.1-preview
   - Menambahkan perubahan non-pengetikan pada cmdlet Metrik, yaitu enumerasi Unit mendukung beberapa nilai baru. Ini adalah cmdlet baca-saja, jadi tidak ada perubahan dalam input cmdlet.
   - Versi api permintaan **ActionGroups** kini adalah **2019-06-01,** sebelum 01-03-2018.  Tes skenario telah diperbarui untuk mengakomodasi perubahan ini.
   - Constructors untuk kelas **EmailReceiver** dan **WebhookReceiver** menambahkan satu argumen wajib baru, yaitu nilai Boolean yang disebut **useCommonAlertSchema**. Saat ini, nilai diperbaiki **ke false** untuk menyembunyikan perubahan pecah ini dari cmdlet. **CATATAN**: ini adalah perubahan sementara yang harus divalidasi oleh tim Pemberitahuan.
   - Urutan argumen untuk konstruktif dari kelas **Sumber** (terkait dengan kelas **ScheduledQueryRuleSource)** diubah dari SDK sebelumnya. Perubahan ini memerlukan dua uji unit untuk diperbaiki: disusun, tetapi gagal lolos tes.
   - Urutan argumen untuk konstruksi kelas **AlertingAction** (terkait dengan kelas **ScheduledQueryRuleSource)** diubah dari SDK sebelumnya. Perubahan ini memerlukan dua uji unit untuk diperbaiki: disusun, tetapi gagal lolos tes.
* Mendukung kriteria Ambang Dinamis untuk metrik pemberitahuan V2
    - New-AzMetricAlertRuleV2Criteria: kini kriteria ambang batas dinamis juga
    - Add-AzMetricAlertRuleV2: kini juga menerima kriteria ambang batas dinamis
* Penyempurnaan dalam cmdlet Aturan Kueri Terjadwal (SQR)
 - Cmdlet akan menerima paramater 'Lokasi' dalam kedua format, baik lokasi (misalnya eastus) atau nama tampilan lokasi (misalnya AS Timur)
 - Ilustrasi parameter 'Diaktifkan' dalam file bantuan dengan benar
 - Menambahkan contoh untuk parameter opsional 'ActionGroup'
 - Keseluruhan file bantuan yang ditingkatkan
* Memperbaiki bug dalam menentukan tipe lingkup untuk 'Set-AzActionRule'

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki contoh yang salah dalam dokumentasi referensi 'New-AzApplicationGateway'
* Tambahkan catatan di dokumentasi referensi 'Get-AzNetworkWatcherPacketCapture' tentang mengambil semua properti untuk penangkapan paket
* Memperbaiki contoh dalam dokumentasi referensi 'Test-AzNetworkWatcherIPFlow' untuk menghitung NICs dengan benar
* Menyempurnakan penguraian pengecualian cloud untuk menampilkan detail tambahan jika ada
* Menyempurnakan penguraian pengecualian awan untuk menangani tipe pengecualian SDK tambahan
* Memperbaiki pemetaan model Aturan Keamanan yang tidak benar
* Properti yang ditambahkan ke antarmuka jaringan untuk fitur ip privat
    - Properti ditambahkan 'PrivateEndpoint' sebagai tipe PSResourceId ke PSNetworkInterface
    - Properti tambahan 'PrivateLinkConnectionProperties' sebagai tipe PSIpConfigurationConnectivityInformation menjadi PSNetworkInterfaceIPConfiguration
    - Menambahkan kelas model baru PSIpConfigurationConnectivityInformation
* Menambahkan baru ApplicationRuleProtocolType 'mssql' untuk sumber daya Azure Firewall
* Dukungan MultiLink di Virtual WAN
    - Cmdlet baru
        - New-AzVpnSiteLink
        - New-AzVpnSiteLinkConnection
    - Cmdlet yang diperbarui:
        - New-VpnSite
        - Update-VpnSite
        - New-VpnConnection
        - Update-VpnConnection
* Memperbaiki dokumen untuk beberapa contoh PowerShell agar menggunakan cmdlet Az, bukan cmdlet AzureRM

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbarui Objek AzureVMpolicy dengan Atribut ProtectedItemsCount
* Uji tambahan untuk kebijakan VM dan Pemulihan Storage Asli

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug New-AzRoleAssignment parameter yang tidak dapat disebut tanpa Lingkup parameter.

#### <a name="azservicefabric"></a>az.servicefabric
* Memperbaiki kesalahan ketik dalam contoh untuk dokumentasi referensi 'Update-AzServiceFabricReliability'
* Menambahkan cmdlet baru untuk mengelola penghubungan dan layanan:
    - New-AzServiceFabricApplication
    - New-AzServiceFabricApplicationType
    - New-AzServiceFabricApplicationTypeVersion
    - New-AzServiceFabricService
    - Update-AzServiceFabricApplication
    - Get-AzServiceFabricApplication
    - Get-AzServiceFabricApplicationType
    - Get-AzServiceFabricApplicationTypeVersion
    - Get-AzServiceFabricService
    - Remove-AzServiceFabricApplication
    - Remove-AzServiceFabricApplicationType
    - Remove-AzServiceFabricApplicationTypeVersion
    - Remove-AzServiceFabricServic
* Upgraded Service Fabric SDK to version 1.2.0 which uses service fabric resource provider api-version 2019-03-01.

#### <a name="azsignalr"></a>az.signalr
* Tambahkan Pembaruan, Mulai Ulang, CheckNameAvailability, Cmdlet GetUsage

#### <a name="azsql"></a>az.sql
* Contoh pembaruan dalam dokumentasi referensi untuk 'Get-AzSqlElasticPool'
* Menambahkan contoh vCore untuk membuat kolam elastis (New-AzSqlElasticPool).
* Hapus validasi EmailAddresses dan periksa bahwa EmailAdmins tidak false dalam kasus EmailAddresses kosong di bagian Set-AzSqlServerAdvancedThreatProtectionPolicy dan Set-AzSqlDatabaseAdvancedThreatProtectionPolicy
* Penghapusan pengaturan pengauditan server/database yang diaktifkan ketika terdapat beberapa pengaturan diagnostik yang mengaktifkan kategori audit.
* Perbaiki validasi alamat email dalam beberapa cmdlet Penilaian Kerentanan Sql (Update-AzSqlDatabaseVulnerabilityAssessmentSetting, Update-AzSqlServerVulnerabilityAssessmentSetting, Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting, dan Update-AzSqlInstanceVulnerabilityAssessmentSetting).

#### <a name="azstorage"></a>Az.Storage
* Contoh yang diperbarui dalam dokumentasi referensi untuk 'Get-AzStorageAccountKey'
* Di Azure File Azure Unggah/Downalod, dukungan layanan properti File SMB sumber (File Attributtes, Waktu Pembuatan File, Waktu Penulisan Terakhir File) di file tujuan
    -  Set-AzStorageFileContent
    -  Get-AzStorageFileContent
* Perbaiki Upload dengan properti/metadate gagal pada wadah yang mengaktifkan ImmutabilityPolicy.
    -  Set-AzStorageBlobContent
* Dukungan mengelola berbagi File Azure dengan API bidang Manajemen
    -  New-AzRmStorageShare
    -  Get-AzRmStorageShare
    -  Update-AzRmStorageShare
    -  Remove-AzRmStorageShare

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki masalah Tag aplikasi web yang terhapus ketika melakukan migrasi Aplikasi ke Tag aspwhere webapp yang baru dihapus ketika melakukan migrasi Aplikasi ke ASP baru
* Memperbaiki masalah Publish-AzureWebapp berfungsi di Linux dan windows
* Contoh pembaruan dalam dokumentasi referensi 'Get-AzWebAppPublishingProfile'

## <a name="260---august-2019"></a>2.6.0 - Agustus 2019
#### <a name="general"></a>Umum
* Memperbaiki kesalahan ketik lain di seluruh modul

#### <a name="azaccounts"></a>Az.Accounts
* Mendukung MSI yang ditetapkan pengguna di Azure Functiosn Authentication (#9479)

#### <a name="azaks"></a>Az.Aks
* Perbaiki masalah dengan output untuk 'Get-AzAks'
    * Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/9847

#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbaikan masalah https://github.com/Azure/azure-powershell/issues/9351
    - Perbarui versi .net nuget, yang tidak memberlakukan pembatasan pada productId, apiId, groupId dan userId
* **Get-AzApiManagementProduct** - Dukungan tambahan untuk membuat kueri produk menggunakan Api.
  https://github.com/Azure/azure-powershell/issues/9482
* **New-AzApiManagementApiRevision** - Perbaikan untuk masalah ketika ApiRevisionDescription tidak diatur saat membuat revisi api baru https://github.com/Azure/azure-powershell/issues/9752
* Memperbaiki kesalahan ketik dalam model 'PsApiManagementOAuth2AuthrozationServer' menjadi 'PsApiManagementOAuth2AuthorizationServer'

#### <a name="azbatch"></a>Az.Batch
* Memperbaiki kesalahan ketik dalam pesan bantuan dan dokumentasi untuk kapitalkan Windows

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki kesalahan ketik di CDN bantuan konversi modul

#### <a name="azcompute"></a>Az.Compute
* Tambahkan VmssId ke New-AzVMConfig cmdlet
* Tambahkan parameter TerminateScheduledEvents dan TerminateScheduledEventNotBeforeTimeoutInMinutes untuk New-AzVmssConfig dan Update-AzVmss
* Menambahkan properti HyperVGeneration ke objek gambar VM
* Menambahkan fitur Host dan Grup Host
    - Cmdlet baru: New-AzHostGroup New-AzHost Get-AzHostGroup Get-AzHost Remove-AzHostGroup Remove-AzHost
    - Parameter HostId ditambahkan ke New-AzVMConfig dan New-AzVM
* Contoh pembaruan dalam dokumentasi 'Invoke-AzVMRunCommand' untuk menggunakan nama parameter yang benar
* Perbarui deskripsi '-VolumeType' dalam dokumentasi referensi 'Set-AzVMDiskEncryptionExtension' dan 'Set-AzVmssDiskEncryptionExtension'

#### <a name="azdatafactory"></a>Az.DataFactory
* Perbaiki kesalahan ketik untuk kapitalkan 'Windows' dalam dokumentasi 'New-AzDataFactoryEncryptValue'
* Memperbarui versi .Net SDK ADF ke 4.1.2
* Tambahkan parameter 'DataProxyIntegrationRuntimeName', 'DataProxyStagingLinkedServiceName' dan 'DataProxyStagingPath' untuk 'Set-AzureRmDataFactoryV2IntegrationRuntime' cmd untuk mengaktifkan konfigurasi Self-Hosted Integration Runtime sebagai proksi untuk SSIS Integration Runtime
* PSTriggerRun yang diperbarui untuk memperlihatkan saluran, pesan dan properti yang dipicu, serta PSActivityRun untuk memperlihatkan tipe aktivitas

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbaiki kesalahan yang terjadi Get-DataLakeStoreDeletedItem kesalahan atau pengecualian jarak jauh.

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan masalah #9658 : Kesalahan Ketik parameter VirtualNteworkRule di Set-AzEventHubNetworkRuleSet
* Perbaikan untuk masalah #9558 : Set-AzEventHubNamespace menggunakan PATCH sebagai ganti PUT
* menambahkan parameter EnableKafka ke Set-AzEventHubNamespace cmdlet
* Perbaikan untuk masalah #9786 : tidak dapat membuat aturan dengan hak Dengarkan saja

#### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* Memperbaiki kesalahan pengetikan dokumentasi ketika semua huruf kecil 'Azure'

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam dokumentasi bantuan

#### <a name="aznetwork"></a>Az.Network
* Pembaruan New-AzPrivateLinkServiceIpConfig
    - Usangkan paramster 'PublicIpAddress' karena ini tidak pernah digunakan di sisi server.
    - Ditambahkan satu parameter opsional 'Utama' yang mengindikasikan konfigurasi ip saat ini adalah konfigurasi utama satu atau tidak.
* Penanganan pengecualian kesalahan permintaan yang ditingkatkan dari SDK -Memperbaiki masalah yang sebelumnya pengecualian SDK tidak ditangani dengan benar sehingga menghasilkan detail kesalahan utama tidak ditampilkan
* Logika validasi yang disesuaikan untuk Prefiks IP Ipv6 untuk memeriksa panjang prefiks IPv6 yang benar.
* Diperbarui Get-AzVirtualNetworkSubnetConfig: Parameter yang ditambahkan diatur untuk masuk menurut id sumber daya subnet.
* Deskripsi parameter Lokasi yang diperbarui untuk AzNetworkServiceTag

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Updated documentation for 'New-AzOperationalInsightsLinuxSyslogDataSource'
    - Contoh yang ditambahkan
    - Deskripsi yang diperbarui untuk parameter '-Nama'
* Menambahkan contoh untuk New-AzOperationalInsightsWindowsEventDataSource
* Mengubah deskripsi parameter -Name untuk New-AzOperationalInsightsWindowsEventDataSource

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbarui 'Get-AzRecoveryServicesBackupJobDetail.md'

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk api baru versi 2019-05-10 untuk Microsoft.Resource
    - Tambahkan dukungan untuk 'copy.count = 0' untuk variabel, sumber daya, dan properti
    - Sumber daya dengan 'kondisi = false' atau 'copy.count = 0' akan dihapus dalam mode lengkap
* Tambahkan contoh menetapkan kebijakan di tingkat langganan untuk membantu dokumen

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaikan masalah #9658 : Kesalahan Ketik parameter VirtualNetworkRule di Set-AzServiceBusNetworkRuleSet
* Perbaikan untuk masalah #9786 : tidak dapat membuat aturan dengan hak Dengarkan saja
* Menambahkan perintah baru 'Test-AzServiceBusNameAvailability' untuk memeriksa ketersediaan nama untuk antrean dan topik

#### <a name="azservicefabric"></a>az.servicefabric
* Memperbaiki bug cmdlet tipe node:
    - Bug NullReferenceException ketika grup sumber daya memiliki vmss lain yang tidak terkait dengan kluster kain layanan. Masalah perbaikan: https://github.com/Azure/azure-powershell/issues/8681
    - Fix bug where cmdlet failed if virtualNetwork was in a different resource group that the cluster. masalah perbaikan: https://github.com/Azure/azure-powershell/issues/8407
    - Penghentian Add-AzServiceFabricApplicationCertificate cmdlet

#### <a name="azsql"></a>az.sql
* Dokumentasi pembaruan cmdlet Pengauditan lama.

#### <a name="azstorage"></a>Az.Storage
* Bantuan pembaruan untuk Get/Close-AzStorageFileHandle, dengan menambahkan lebih banyak skenario pada contoh cmdlet dan memperbarui deskripsi parameter
* Dukungan StandardBlobTier diunggah blob dan salin blob
    -  Set-AzStorageBlobContent
    -  Start-AzStorageBlobCopy
* Mendukung Prioritas Rehydrate dalam salin blob
    -  Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Situs Web Az.
* Tambahkan klarifikasi di sekitar parameter -AppSettings Set-AzWebApp dan Set-AzWebAppSlot

## <a name="250---july-2019"></a>2.5.0 - Juli 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Memperbaiki contoh kesalahan ketik dalam dokumentasi 'Remove-AzApplicationInsightsApiKey'

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan ketik dalam string sumber daya

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan dukungan NetworkRuleSet.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan properti yang hilang (ComputerName, OsName, OsVersion dan HyperVGeneration) dari objek tampilan instans VM.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki kesalahan ketik Remove-AzContainerRegistryReplication untuk Parameter replikasi
    - Informasi selengkapnya di sini https://github.com/Azure/azure-powershell/issues/9633

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 4.1.0
* Perbaiki kesalahan ketik dalam dokumentasi untuk 'Get-AzDataFactoryV2PipelineRun'

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmmdlet baru untuk menghasilkan token SAS : New-AzEventHubAuthorizationRuleSASToken
* ditambahkan verifikasi dan pesan kesalahan untuk hak otorisasi jika hanya 'Kelola' yang ditetapkan

#### <a name="azkeyvault"></a>Az.KeyVault
* Ditambahkan dukungan untuk menentukan KeySize untuk Kebijakan Sertifikat

#### <a name="azlogicapp"></a>Az.LogicApp
* Perbaikan untuk Get-AzIntegrationAccountMap mencantumkan semua tipe peta
    - Menambahkan parameter MapType baru untuk pemfilteran

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan dukungan untuk api versi 2019-06-01 (GA)

#### <a name="aznetwork"></a>Az.Network
* Tambahkan dukungan untuk layanan titik akhir privat dan tautan privat
    - Cmdlet baru
        - Set-AzPrivateEndpoint
        - Set-AzPrivateLinkService
        - Approve-AzPrivateEndpointConnection
        - Deny-AzPrivateEndpointConnection
        - Get-AzPrivateEndpointConnection
        - Remove-AzPrivateEndpointConnection
        - Test-AzPrivateLinkServiceVisibility
        - Get-AzAutoApprovedPrivateLinkService
* Diperbarui di bawah perintah untuk fitur: PrivateEndpointNetworkPolicies/PrivateLinkServiceNetworkPolicies bendera pada Subnet di Virtualnetwork
    - Updated New-AzVirtualNetworkSubnetConfig/Set-AzVirtualNetworkSubnetConfig/Add-AzVirtualNetworkSubnetConfig
        - Menambahkan parameter opsional -PrivateEndpointNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan pada titik akhir privat dalam subnet ini.
        - Menambahkan parameter opsional -PrivateLinkServiceNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan kebijakan jaringan pada layanan link privat dalam subnet ini.
* Parameter cmdlet AzPrivateLinkService 'ServiceName' telah diganti namanya menjadi 'Name' dengan alias 'ServiceName' untuk kompatibilitas mundur
* Mengaktifkan protokol ICMP untuk konfigurasi aturan keamanan jaringan
    - Cmdlet yang diperbarui
        - Add-AzNetworkSecurityRuleConfig
        - New-AzNetworkSecurityRuleConfig
        - Set-AzNetworkSecurityRuleConfig
* Menambahkan ConnectionProtocolType (Ikev1/Ikev2) sebagai parameter yang dapat New-AzVirtualNetworkGatewayConnection
* Add PrivateIpAddressVersion in LoadBalancerFrontendIpConfiguration
    - Cmdlet yang diperbarui:
        - New-AzLoadBalancerFrontendIpConfig
        - Add-AzLoadBalancerFrontendIpConfig
        - Set-AzLoadBalancerFrontendIpConfig
* Pembaruan perintah New-AzApplicationGatewayProbeConfig Gateway Aplikasi untuk mendukung port kustom di Default
    - Updated New-AzApplicationGatewayProbeConfig: Added optional parameter Port which is used for probing backend server. Parameter ini berlaku untuk Standard_V2 dan WAF_V2 SKU.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Versi default yang diperbarui untuk pencarian yang disimpan menjadi 1.
* Memperbaiki penanganan regex null log kustom

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbarui 'Get-AzRecoveryServicesBackupJob.md'
* Perbarui 'Get-AzRecoveryServicesBackupContainer.md'
* Perbarui 'Get-AzRecoveryServicesVault.md'
* Perbarui 'Wait-AzRecoveryServicesBackupJob.md'
* Perbarui 'Set-AzRecoveryServicesVaultContext.md'
* Perbarui 'Get-AzRecoveryServicesBackupItem.md'
* Perbarui 'Get-AzRecoveryServicesBackupRecoveryPoint.md'
* Perbarui 'Restore-AzRecoveryServicesBackupItem.md'
* Pembaruan panggilan layanan untuk Wadah Pendaftaran untuk Berbagi File Azure
* Perbarui 'Set-AzRecoveryServicesAsrAlertSetting.md'

#### <a name="azresources"></a>Az.Resources
- Hapus cmdlet yang hilang yang direferensikan dalam dokumentasi 'New-AzResourceGroupDeployment'
- Cmdlet kebijakan yang diperbarui untuk menggunakan versi api baru 2019-01-01

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmmdlet baru untuk menghasilkan token SAS : New-AzServiceBusAuthorizationRuleSASToken
* ditambahkan verifikasi dan pesan kesalahan untuk hak otorisasi jika hanya 'Kelola' yang ditetapkan

#### <a name="azsql"></a>az.sql
* Memperbaiki contoh yang hilang Set-AzSqlDatabaseSecondary cmdlet
* Memperbaiki pemindaian berulang Penilaian Kerentanan tanpa menyediakan alamat email apa pun
* Memperbaiki sedikit kesalahan ketik dalam pesan yang warin.

#### <a name="azstorage"></a>Az.Storage
* Contoh pembaruan dalam dokumentasi referensi untuk 'Get-AzStorageAccount' menggunakan nama parameter yang benar

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan Invoke-AzStorageSyncChangeDetection cmdlet.
* Fix Issue 9551 for honoring TierFilesOlderTermal

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki bug di mana beberapa properti SiteConfig tidak dikembalikan oleh Get-AzWebApp dan Set-AzWebApp
* Menambahkan parameter Lokasi baru ke Get-AzDeletedWebApp dan Restore-AzDeletedWebApp
* Memperbaiki bug dengan slot aplikasi web yang mengksumsi menggunakan New-AzWebApp -IncludeSourceWebAppSlots

## <a name="240---july-2019"></a>2.4.0 - Juli 2019
#### <a name="azaccounts"></a>Az.Accounts
* Tambahkan dukungan untuk cmdlet profil
* Menambahkan dukungan untuk lingkungan dan paket data dalam cmdlet yang dihasilkan
* Memperbaiki bug ketika titik akhir yang salah digunakan dalam beberapa kasus untuk cmdlet pesawat data Windows PowerShell

#### <a name="azadvisor"></a>Az.Advisor
* Rilis GA dari Az.Advisor
* Modul ini kini disertakan sebagai bagian dari modul `Az` peluncuran

#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbaikan masalah https://github.com/Azure/azure-powershell/issues/8671
    - **Get-AzApiManagementSubscription**
        - Menambahkan dukungan untuk membuat kueri langganan menurut Pengguna dan Produk
        - Menambahkan dukungan untuk membuat kueri menggunakan Lingkup '/', '/apis', '/apis/echo-api'
* Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/9307 dan https://github.com/Azure/azure-powershell/issues/8432
    - **Import-AzApiManagementApi**
        - Ditambahkan dukungan untuk menentukan 'ApiVersion' dan 'ApiVersionSetId' saat mengimpor Api

#### <a name="azautomation"></a>Az.Automation
* Perbaikan Set-AzAutomationConnectionFieldValue cmdlet untuk menangani nilai string.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HyperVGeneration ke New-AzImageConfig

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui output untuk menjalankan aktivitas, menjalankan pipeline, dan mendapatkan pemicu menjalankan cmdlet ADF untuk mendukung Select-Object pipa.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbaiki kesalahan ketik dalam dokumentasi 'New-AzEventGridSubscription'

#### <a name="aziothub"></a>Az.IotHub
* Tambahkan dukungan untuk meregenerasi kunci kebijakan otorisasi.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan 'RoutingPreference' ke tag ip publik
* Meningkatkan contoh untuk dokumentasi referensi 'Get-AzNetworkServiceTag'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi null di Get-AzPolicyState
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/9446

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Model sumber data CustomLog yang dikembalikan di Get-AzOperationalInsightsDataSource

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaikan untuk perintah get-policy untuk IaaSVMs

#### <a name="azresources"></a>Az.Resources
   - Memperbaiki teks bantuan untuk Get-AzPolicyState -Parameter teratas
   - Add client-side paging support for Get-AzPolicyAlias
   - Menambahkan parameter baru untuk Set-AzPolicyAssignment, -PolicyParameters dan -PolicyParametersObject
   - Beberapa dokumen dan contoh pembaruan untuk cmdlet Kebijakan

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaikan untuk masalah #4938 - New-AzureRmServiceBusQueue mengembalikan BadRequest saat mengatur MaxSizeInMegabytes

#### <a name="azsql"></a>az.sql
* Tambahkan cmdlet Grup Failover Instance dari rilis pratinjau ke rilis publik
* Mendukung Pengauditan Azure SQL Server\Database dengan cmdlet baru.
    - Set-AzSqlServerAudit
    - Get-AzSqlServerAudit
    - Remove-AzSqlServerAudit
    - Set-AzSqlDatabaseAudit
    - Get-AzSqlDatabaseAudit
    - Remove-AzSqlDatabaseAudit
* Hapus batasan email dari pengaturan Penilaian Kerentanan

#### <a name="azstorage"></a>Az.Storage
* Ubah 2 parameter '-IndexDocument' dan '-ErrorDocument404Path' dari yang diperlukan ke opsional dalam cmdlet:
    -  Enable-AzStorageStaticWebsite
* Memperbarui bantuan Get-AzStorageBlobContent Anda dengan menambahkan contoh
* Memperlihatkan informasi kesalahan lainnya ketika cmdlet gagal dengan StorageException
* Dukungan untuk membuat atau memperbarui Storage dengan Autentikasi DS Azure AAD
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Daftar dukungan atau tutup gagang file berbagi file, direktori file, atau file
    - Get-AzStorageFileHandle
    - Close-AzStorageFileHandle

#### <a name="azstoragesync"></a>Az.StorageSync
* Modul ini kini disertakan sebagai bagian dari modul `Az` peluncuran

## <a name="232---june-2019"></a>2.3.2 - Juni 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki bug URL yang tidak benar yang digunakan dalam beberapa kasus untuk panggilan Fungsi
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8983
* Perbaiki Masalah dengan alias dari AzureRM ke cmdlet Az
  - Set-AzureRmVMBootDiagnostics -> Set-AzVMBootDiagnostic
  - Export-AzureRMLogAnalyticThrottledRequests -> Export-AzLogAnalyticThrottledRequest

#### <a name="azcompute"></a>Az.Compute
* New-AzVm dan New-AzVmss parameter sederhana sekarang menerima parameter 'ProximityPlacementGroup'.
* Memperbaiki kesalahan ketik dalam dokumentasi referensi 'New-AzVM'

#### <a name="azdns"></a>Az.Dns
* Memperbaiki kesalahan ketik dalam contoh bantuan 'Set-AzDnsZone'.

#### <a name="azeventgrid"></a>Az.EventGrid
* Diperbarui untuk menggunakan versi API 2019-06-01.
* Cmdlet baru:
    - New-AzureRmEventGridDomain
        - Membuat Domain Kisi Acara Azure yang baru.
    - Get-AzureRmEventGridDomain
        - Mendapatkan detail Domain Kisi Acara, atau mendapatkan daftar semua Domain Kisi Acara di langganan Azure saat ini.
    - Remove-AzureRmEventGridDomain
        - Menghapus Domain Kisi Acara Azure.
    - New-AzureRmEventGridDomainKey
        - Meregenerasi kunci akses bersama untuk Domain Kisi Acara Azure.
    - Get-AzureRmEventGridDomainKey
        - Dapatkan kunci akses bersama yang digunakan untuk menerbitkan acara ke Domain Kisi Acara.
    - New-AzureRmEventGridDomainTopic:
        - Membuat Topik Domain Kisi Acara Azure yang baru.
    - Get-AzureRmEventGridDomainTopic
        - Mendapatkan detail Topik Domain Kisi Acara, atau mendapatkan daftar semua Topik Domain Kisi Acara di bawah Domain Kisi Acara tertentu di Azure saat ini
    - Remove-AzureRmEventGridDomainTopic:
        - Menghapus Topik Domain Kisi Acara Azure yang sudah ada.
* Cmdlet yang diperbarui:
    - New-AzureRmEventGridSubscription/Update-AzureRmEventGridSubscription:
        - Tambahkan parameter wajib baru untuk mendukung pemipaan bagi Domain Kisi Kejadian yang baru dan Topik Domain Kisi Acara untuk memungkinkan pembuatan langganan acara baru di bawah sumber daya ini.
        - Tambahkan parameter wajib baru untuk menentukan nama Domain Kisi Acara yang baru dan/atau nama Topik Domain Kisi Acara untuk memungkinkan membuat langganan acara baru di bawah sumber daya ini.
        - Tambahkan kumpulan Parameter baru untuk domain dan topik domain untuk memungkinkan penggunaan kembali parameter yang sudah ada (misalnya EndPointType, SubjectBeginsWith, dll).
        - Tambahkan parameter opsional baru untuk menentukan:
            - Tanggal kedaluwarsa langganan acara,
            - Parameter pemfilteran tingkat lanjut.
        - Tambahkan enum baru untuk servicebusqueue sebagai tujuan.
        - Tidak melarang penggunaan opsi 'Semua' di -IncludedEventType dan menggantinya dengan
    - Get-AzEventGridTopic, Get-AzEventGridDomain, Get-AzEventGridDomainTopic, Get-AzEventGridSubscription:
        - Tambahkan parameter opsional baru (Top, ODataQuery dan NextLink) untuk mendukung penomoran dan pemfilteran hasil.
    - Remove-AzureRmEventGridSubscription
        - Tambahkan parameter wajib baru untuk mendukung pemipaan untuk Topik Domain Kisi Acara dan Domain Kisi Kejadian untuk memungkinkan menghapus langganan acara yang sudah ada di bawah sumber daya ini.
        - Tambahkan parameter wajib baru untuk menentukan nama Domain Kisi Kejadian dan/atau nama Topik Domain Kisi Acara untuk memungkinkan menghapus langganan acara yang sudah ada di bawah sumber daya ini.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* New-AzFrontDoorWafMatchConditionObject
    - Menambahkan dukungan transformasi dan nilai lengkapi otomatis operator baru (RegEx)
* New-AzFrontDoorWafManagedRuleObject
    - Menambahkan nilai lengkapi otomatis baru

#### <a name="aznetwork"></a>Az.Network
* Tambahkan dukungan untuk Sumber Daya Gateway Jaringan Virtual
    - Cmdlet baru
        - Get-AzVirtualNetworkGatewayVpnClientConnectionHealth
* Tambahkan AvailablePrivateEndpointType
    - Cmdlet baru
        - Get-AzAvailablePrivateEndpointType
* Menambahkan PrivatePrivateLinkService
    - Cmdlet baru
        - Get-AzPrivateLinkService
        - New-AzPrivateLinkService
        - Remove-AzPrivateLinkService
        - New-AzPrivateLinkServiceIpConfig
        - Set-AzPrivateEndpointConnection
* Tambahkan PrivateEndpoint
    - Cmdlet baru
        - Get-AzPrivateEndpoint
        - New-AzPrivateEndpoint
        - Remove-AzPrivateEndpoint
        - New-AzPrivateLinkServiceConnection
* Perintah yang diperbarui di bawah ini untuk fitur: UseLocalAzureIpAddress bendera pada VpnConnection
    - Diperbarui New-AzVpnConnection: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip Azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
    - Pembaruan Set-AzVpnConnection: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip Azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
* Menambahkan bidang baca saja PeeredConnections di peering ExpressRoute.
* Bidang baca saja GlobalReachEnabled di ExpressRoute.
* Added breaking change attribute to call out deprecation of AllowGlobalReach field in ExpressRouteCircuit model
* Memperbaiki Kesalahan Masalah 8756 menggunakan TARGETListenerID dengan cmdlet AzApplicationGatewayRedirectConfiguration
* Perbaikan bug New-AzApplicationGatewayPathRuleConfig kumpulan aturan tulis ulang tidak dapat diatur.
* Memperbaiki tampilan VirtualNetworkTaps di NetworkInterfaceIpConfiguration
* Fixed Cortex Get cmdlets for list all part
* Memperbaiki pembuatan referensi VirtualHub untuk ExpressRouteGateway, VpnGateway
* Menambahkan dukungan untuk Zona Ketersediaan di AzureFirewall dan NatGateway
* Perintah cmdlet Get-AzNetworkServiceTag
* Menambahkan dukungan untuk beberapa alamat IP publik untuk Azure Firewall
    - Cmdlet New-AzFirewall yang diperbarui:
        - Parameter tambahan -PublicIpAddress yang menerima satu atau beberapa objek Alamat IP Publik
        - Parameter yang ditambahkan -VirtualNetwork yang menerima objek Jaringan Virtual
        - Metode yang ditambahkan AddPublicIpAddress dan RemovePublicIpAddress pada objek firewall - langkah-langkah ini menerima objek Alamat IP Publik sebagai input
        - Parameter yang sudah tidak berlaku -PublicIpName dan -VirtualNetworkName
* Diperbarui di bawah perintah untuk fitur: Atur Opsi AAD autentikasi ke Sumber daya gateway jaringan virtual.
    - Diperbarui New-AzVirtualNetworkGateway: Added optional parameters AadTenantUri,AadAudienceId,AadIssuerUri to set VpnClient AAD authentication options on Gateway.
    - Updated Set-AzVirtualNetworkGateway: Added optional parameter AadTenantUri,AadAudienceId,AadIssuerUri to set VpnClient AAD authentication options on Gateway.
    - Updated Set-AzVirtualNetworkGateway: Added optional switch parameter RemoveAadAuthentication to remove VpnClient AAD authentication options from Gateway.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Perintah **Aktifkan tingkatan harga pergb2018** dalam perintah 'New-AzureRmOperationalInsightsWorkspace'

#### <a name="azresources"></a>Az.Resources
* Dukungan untuk opsi Ekspor Templat tambahan
    - Menambahkan parameter '-SkipResourceNameParameterization' untuk Export-AzResourceGroup
    - Menambahkan parameter '-SkipAllParameterization' untuk Export-AzResourceGroup
    - Tambahkan parameter '-Sumber Daya' untuk Export-AzResourceGroup pemfilteran sumber daya yang diekspor

#### <a name="azservicefabric"></a>az.servicefabric
* Memperbaiki penambahan sertifikat MenurutExistingKeyVault yang salah dicetak dalam beberapa kasus

#### <a name="azsql"></a>az.sql
* Memperbaiki akhiran titik akhir penyimpanan Advanced Threat Protection
* Fix Advanced Data Security enable overrides Advanced Threat Protection policy
* Cmdlet Baru untuk Manajemen.Sql untuk mengizinkan pelanggan menambahkan kunci TDE dan mengatur instans terkelola TDE
   - Add-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceKeyVaultKey
   - Remove-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceTransparentDataEncryptionProtector
   - Set-AzSqlInstanceTransparentDataEncryptionProtector

#### <a name="azstorage"></a>Az.Storage
* Dukungan FileStorage dan SkuName dukungan Premium_ZRS saat membuat Storage saya
    - New-AzStorageAccount
* Deskripsi dijelaskan cmdlet blob immutability
    -  Remove-AzRmStorageContainerImmutabilityPolicy

#### <a name="azwebsites"></a>Situs Web Az.
* Mengoptimalkan Get-AzWebAppCertificate Anda memfilter menurut grup sumber daya di server, bukan klien
* Menambahkan -UseDisasterRecovery beralih parameter Get-AzWebAppSnapshot

## <a name="220---june-2019"></a>2.2.0 - Juni 2019
#### <a name="azcdn"></a>Az.Cdn
* Cmdlet yang diperbarui untuk mendukung fitur rulesEngine berdasarkan API versi 2019-04-15.

#### <a name="azcompute"></a>Az.Compute
* Parameter `NoWait` tambahan yang memulai operasi dan segera mengembalikannya, sebelum operasi selesai.
    - Cmdlet yang diperbarui: Export-AzLogAnalyticRequestRateByInterval Export-AzLogAnalyticThrottledRequest Remove-AzVM Remove-AzVMAccessExtension Remove-AzVMAEMExtension Remove-AzVMChefExtension Remove-AzVMCustomScriptExtension Remove-AzVMDiagnosticsExtension Remove-AzVMDiskEncryptionExtension Remove-AzVMDscExtension Remove-AzVMSqlServerExtension Restart-AzVM Set-AzVM Set-AzVMAccessExtension Set-AzVMADDomainExtension Set-AzVMAEMExtension Set-AzVMBginfoExtension Set-AzVMChefExtension Set-AzVMCustomScriptExtension Set-AzVMDiagnosticsExtension Set-AzVMDscExtension Set-AzVMExtension Start-AzVM Stop-AzVM Update-AzVM

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan untuk #9231 - Get-AzEventHubNamespace tidak mengembalikan tag
* Perbaikan untuk #9230 - Get-AzEventHubNamespace mengembalikan ResourceGroup dan bukan ResourceGroupName

#### <a name="aznetwork"></a>Az.Network
* Memperbarui ResourceId dan InputObject untuk Gateway Nat
    - Menambahkan alias untuk ResourceId dan InputObject

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi Null di Get-AzPolicyEvent

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Kebijakan IaaSVM penyimpanan minimum dalam hari berubah menjadi 7 dari 1

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaikan untuk masalah #9182 - Get-AzServiceBusNamespace mengembalikan ResourceGroup dan bukan ResourceGroupName

#### <a name="azservicefabric"></a>az.servicefabric
* Memperbaiki kesalahan ketik dalam pesan kesalahan untuk 'Update-AzServiceFabricReliability'
* Memperbaiki karakter yang hilang di Service Fabric cmd

#### <a name="azsql"></a>az.sql
* Tambahkan Parameter DnsZonePartner New-AzureSqlInstance cmdlet untuk mendukung AutoDr untuk Instans yang Dikelola.
* Perintah penghentian Get-AzSqlDatabaseSecureConnectionPolicy cmdlet
* Ganti Nama cmdlet Deteksi Ancaman menjadi Advanced Threat Protection
* New-AzSqlInstance parameter -StorageSizeInGB dan -LicenseType kini bersifat opsional.

#### <a name="azwebsites"></a>Situs Web Az.
* memperbaiki masalah ketika menggunakan Set-AzWebApp dan Set-AzWebAppSlot dengan properti -WebApp menghapus tag

## <a name="210---may-2019"></a>2.1.0 - Mei 2019
#### <a name="azapimanagement"></a>Az.ApiManagement
* Cmdlet baru yang dibuat untuk mengelola diagnostik di global dan Lingkup API
    - **Get-AzApiManagementDiagnostic** - Dapatkan diagnostik yang dikonfigurasi global atau Lingkup api
    - **New-AzApiManagementDiagnostic** - Membuat diagnostik baru di lingkup global atau Lingkup api
    - **New-AzApiManagementHttpMessageDiagnostic** - Membuat pengaturan diagnostik yang digunakan header untuk log dan ukuran Body Bytes
    - **New-AzApiManagementPipelineDiagnosticSetting** - Buat pengaturan Diagnostik untuk pesan HTTP masuk/keluar ke Gateway.
    - **New-AzApiManagementSamplingSetting** - Membuat Pengaturan Sampling untuk permintaan/respons untuk diagnostik
    - **Remove-AzApiManagementDiagnostic** - Menghapus entitas diagnostik di global atau lingkup api
    - **Set-AzApiManagementDiagnostic** - Memperbarui Entitas diagnostik di global atau lingkup api
* Membuat Cmdlets baru untuk mengelola Singgahan dalam layanan ApiManagement
    - **Get-AzApiManagementCache** - Dapatkan detail Cache yang ditentukan berdasarkan pengidentifikasi atau semua cache
    - **New-AzApiManagementCache** - Membuat Singgahan atau Singgahan 'default' baru di 'kawasan' azure tertentu
    - **Remove-AzApiManagementCache** - Menghapus cache
    - **Update-AzApiManagementCache** - Memperbarui singgahan
* Cmdlet baru yang dibuat untuk mengelola Skema API
    - **New-AzApiManagementSchema** - Buat Skema baru untuk API
    - **Get-AzApiManagementSchema** - Dapatkan skema yang dikonfigurasi dalam API
    - **Remove-AzApiManagementSchema** - Menghapus skema yang dikonfigurasi di API
    - **Set-AzApiManagementSchema** - Perbarui skema yang dikonfigurasi dalam API
* Cmdlet baru yang dibuat untuk menghasilkan Token Pengguna.
    - **New-AzApiManagementUserToken** - Buat Token Pengguna baru yang valid selama 8 jam secara default. Token untuk pengguna 'GIT' dapat dihasilkan menggunakan cmdlet ini./
* Membuat cmdlet baru untuk mengambil Status Jaringan
    - **Get-AzApiManagementNetworkStatus** - Dapatkan Konektivitas status jaringan dari sumber daya yang bergantung pada layanan Manajemen API. Ini berguna saat menggunakan layanan ApiManagement ke dalam Jaringan Virtual dan validing apakah salah satu dependensi rusak.
* Cmdlet **New-AzApiManagement yang diperbarui** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk SKU 'Pemakaian' baru
    - Menambahkan dukungan untuk mengaktifkan bendera 'EnableClientCertificate' untuk SKU 'Konsumsi'
    - Cmdlet baru **New-AzApiManagementSsslSetting** memungkinkan konfigurasi pengaturan 'TLS/SSL' pada 'Backend' dan 'Frontend'. Opsi ini juga dapat digunakan untuk mengonfigurasi 'Ciphers' seperti '3DES' dan 'ServerProtocols' seperti 'Http2' di 'Frontend' dari layanan ApiManagement.
    - Menambahkan dukungan untuk mengonfigurasi nama host 'DeveloperPortal' di layanan ApiManagement.
* Cmdlet yang diperbarui **Get-AzApiManagementSsoToken** untuk mengambil objek 'PsApiManagement' sebagai input
* Memperbarui cmdlet untuk menampilkan pesan kesalahan sebaris
     > PS D:\github\azure-powershell> Set-AzApiManagementPolicy -Context -PolicyFilePath C:\wrongpolicy.xml -ApiId httpbin Set-AzApiManagementPolicy : Kode Kesalahan: Pesan Kesalahan ValidationError: Satu atau beberapa bidang berisi nilai yang salah: Detail Kesalahan: [Code=ValidationError, Message=Error in element 'log-to-eventhub' on line 3, column 10: Logger tidak ditemukan, Target=log-to-eventhub]
* Pembaruan cmdlet **Export-AzApiManagementApi** untuk mengekspor API dalam format 'OpenApi 3.0'
* Pembaruan cmdlet **Import-AzApiManagementApi**
    - Untuk mengimpor Api dari spesifikasi dokumen 'OpenApi 3.0'
    - Untuk menimpa properti 'PsApiManagementSchema' yang ditentukan dalam setiap dokumen ('Swagger', 'Wadl', 'Wsdl', 'OpenApi').
    - Untuk mengesampingkan properti 'ServiceUrl' yang ditentukan dalam setiap dokumen.
* Cmdlet yang **diperbarui Get-AzApiManagementPolicy** untuk mengembalikan kebijakan dalam 'format' non-Xml yang di escape menggunakan 'rawxml'
* Pembaruan cmdlet **Set-AzApiManagementPolicy** untuk menerima kebijakan dalam 'format' non-Xml yang di escape menggunakan 'rawxml' dan Xml di escape menggunakan 'xml'
* Cmdlet **New-AzApiManagementApi yang diperbarui**
    - Untuk mengonfigurasi API dengan server otorisasi 'OpenId'.
    - Untuk membuat API di 'ApiVersionSet'
    - Untuk kloning API menggunakan 'SourceApiId' dan 'SourceApiRevision'.
    - Kemampuan untuk mengonfigurasi 'Langganan Diminta' di lingkup Api.
* Cmdlet **Set-AzApiManagementApi diperbarui**
    - Untuk mengonfigurasi API dengan server otorisasi 'OpenId'.
    - Untuk memperbarui API menjadi 'ApiVersionSet'
    - Kemampuan untuk mengonfigurasi 'Langganan Diminta' di lingkup Api.
* Cmdlet **New-AzApiManagementRevision** yang diperbarui
    - Untuk kloning (menyalin tag, produk, operasi, dan kebijakan) revisi yang ada menggunakan 'SourceApiRevision'. Revisi baru mengasumsikan 'ApiId' dari induk.
    - Untuk menyediakan 'ApiRevisionDescription'
    - Untuk menimpa 'ServiceUrl' saat mengk cloning API.
* Updated cmdlet **New-AzApiManagementIdentityProvider**
    - Untuk mengonfigurasi 'AAD' atau 'AADB2C' dengan 'Otoritas'
    - Untuk menyiapkan 'SignupPolicy', 'SigninPolicy', 'ProfileEditingPolicy' dan 'PasswordResetPolicy'
* Cmdlet **New-AzApiManagementSubscription yang diperbarui**
    - Untuk membuat akun untuk SubskripModel baru menggunakan 'Lingkup' dan 'UserId'
    - Untuk mempertimbangkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Tambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Cmdlet **Set-AzApiManagementSubscription yang diperbarui**
    - Untuk membuat akun untuk SubskripModel baru menggunakan 'Lingkup' dan 'UserId'
    - Untuk mempertimbangkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Tambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Cmdlets berikut diperbarui untuk menerima 'ResourceId' sebagai input
    - 'New-AzApiManagementContext'
        > New-AzApiManagementContext -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso
    - 'Get-AzApiManagementApiRelease'
        > Get-AzApiManagementApiRelease -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso/apis/echo-api/releases/releaseId
    - 'Get-AzApiManagementApiVersionSet'
        > Get-AzApiManagementApiVersionSet -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/constoso/apiversionsets/pathversionset
    - 'Get-AzApiManagementAuthorizationServer'
    - 'Get-AzApiManagementBackend'
        > Get-AzApiManagementBackend -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso/backends/servicefabric
    - 'Get-AzApiManagementCertificate'
    - 'Remove-AzApiManagementApiVersionSet'
    - 'Remove-AzApiManagementSubscription'

#### <a name="azautomation"></a>Az.Automation
* Diperbarui Get-AzAutomationJobOutputRecord menangani nilai catatan JSON dan Teks.
    - Perbaikan masalah https://github.com/Azure/azure-powershell/issues/7977
    - Perbaikan masalah https://github.com/Azure/azure-powershell/issues/8600
* Perilaku yang diubah Start-AzAutomationDscCompilationJob Anda baru saja memulai pekerjaan dan bukan menunggu penyelesaiannya.
    * Perbaikan masalah https://github.com/Azure/azure-powershell/issues/8347
* Perbaikan untuk Get-AzAutomationDscNode ketika menggunakan -Name mengembalikan semua simpul. Sekarang node yang cocok saja mengembalikannya.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter ProtectFromScaleIn dan ProtectFromScaleSetAction Update-AzVmssVM cmdlet.
* New-AzVM parameter wimple sekarang menggunakan secara default lokasi yang tersedia jika 'AS Timur' tidak didukung

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui ADLS sdk untuk menggunakan httpclient, mengintegrasikan pengujian dataplane dengan azure framework

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam contoh bantuan

#### <a name="aznetwork"></a>Az.Network
* Menambahkan bendera DisableBgpRoutePropagation ke output Tabel Rute Efektif
    - Cmdlet yang diperbarui:
        - Get-AzEffectiveRouteTable
* Memperbaiki tanda hubung ganda New-AzApplicationGatewayTrustedRootCertificate dokumentasi

#### <a name="azresources"></a>Az.Resources
* Menambahkan cmdlet Get-AzureRmDenyAssignment cmdlet baru untuk mengambil penetapan penolakan

#### <a name="azsql"></a>az.sql
* Ganti Nama cmdlet Advanced Threat Protection ke Keamanan Data Tingkat Lanjut dan aktifkan Penilaian Kerentanan secara default

## <a name="200---may-2019"></a>2.0.0 - Mei 2019
#### <a name="azaccounts"></a>Az.Accounts
* Perbarui Pustaka Autentikasi untuk memperbaiki masalah ADFS dengan username/password auth

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Hanya menampilkan Bing sanggahan untuk Bing Pencarian Layanan.
* Meningkatkan kesalahan ketika membuat akun gagal.

#### <a name="azcompute"></a>Az.Compute
* Fitur grup penempatan kedekatan.
    - Cmdlet baru berikut ini ditambahkan: New-AzProximityPlacementGroup Get-AzProximityPlacementGroup Remove-AzProximityPlacementGroup
    - Parameter baru, ProximityPlacementGroupId, ditambahkan ke cmdlet berikut: New-AzAvailabilitySet New-AzVMConfig New-AzVmssConfig
* Parameter StorageAccountType ditambahkan ke New-AzGalleryImageVersion.
* Wilayah Target New-AzGalleryImageVersion memuat StorageAccountType.
* Parameter sakelar SkipSdown ditambahkan ke Stop-AzVM dan Stop-AzVmss
* Memutus perubahan
    - Set-AzVMBootDiagnostics diubah menjadi Set-AzVMBootDiagnostic.
    - Export-AzLogAnalyticThrottledRequests diubah menjadi Export-AzLogAnalyticThrottledRequests.

#### <a name="azdeploymentmanager"></a>az.deploymentmanager
* Rilis cmdlet Azure Deployment Manager pertama yang Tersedia Secara Umum

#### <a name="azdns"></a>Az.Dns
* Delegasi NameServer DNS otomatis
    - Buat cmdlet zona DNS menerima nama zona induk sebagai parameter opsional tambahan.
    - Menambahkan catatan NS di zona induk untuk zona anak yang baru dibuat.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Rilis Cmdlet Azure FrontDoor pertama yang Tersedia Secara Umum
* Ganti nama cmdlet WAF untuk menyertakan 'Waf'
    - `Get-AzFrontDoorFireWallPolicy --> Get-AzFrontDoorWafPolicy`
    - `New-AzFrontDoorCustomRuleObject --> New-AzFrontDoorWafCustomRuleObject`
    - `New-AzFrontDoorFireWallPolicy --> New-AzFrontDoorWafPolicy`
    - `New-AzFrontDoorManagedRuleObject --> New-AzFrontDoorWafManagedRuleObject`
    - `New-AzFrontDoorManagedRuleOverrideObject --> New-AzFrontDoorWafManagedRuleOverrideObject`
    - `New-AzFrontDoorMatchConditionObject --> New-AzFrontDoorWafMatchConditionObject`
    - `New-AzFrontDoorRuleGroupOverrideObject --> New-AzFrontDoorWafRuleGroupOverrideObject`
    - `Remove-AzFrontDoorFireWallPolicy --> Remove-AzFrontDoorWafPolicy`
    - `Update-AzFrontDoorFireWallPolicy --> Update-AzFrontDoorWafPolicy`
#### <a name="azhdinsight"></a>Az.HDInsight
* Menghapus dua cmdlet:
    - Grant-AzHDInsightHttpServicesAccess
    - Revoke-AzHDInsightHttpServicesAccess
* Menambahkan cmdlet baru Set-AzHDInsightGatewayCredential menggantikan Grant-AzHDInsightHttpServicesAccess
* Perbarui cmdlet Get-AzHDInsightJobOutput untuk membedakan peran pembaca dan peran operator hdinsight:
    - Pengguna dengan peran pembaca perlu menentukan parameter 'DefaultStorageAccountKey' secara eksplisit, jika tidak kesalahan terjadi.
    - Pengguna dengan peran operator hdinsight tidak akan terpengaruh.

#### <a name="azmonitor"></a>Az.Monitor
* Cmdlet baru untuk API SQR (Aturan Kueri Terjadwal)
    - New-AzScheduledQueryRuleAlertingAction
    - New-AzScheduledQueryRuleAznsActionGroup
    - New-AzScheduledQueryRuleLogMetricTrigger
    - New-AzScheduledQueryRuleSchedule
    - New-AzScheduledQueryRuleSource
    - New-AzScheduledQueryRuleTriggerCondition
    - New-AzScheduledQueryRule
    - Get-AzScheduledQueryRule
    - Set-AzScheduledQueryRule
    - Update-AzScheduledQueryRule
    - Remove-AzScheduledQueryRule
    - [Informasi](/rest/api/monitor/scheduledqueryrules) selengkapnya tentang API SQR
    - Diperbarui Az.Monitor.md menyertakan cmdlet untuk aturan pemberitahuan berbasis metrik GenV2 (non klasik)

#### <a name="aznetwork"></a>Az.Network
* Tambahkan dukungan untuk Sumber Daya Gateway Nat
    - Cmdlet baru
        - New-AzNatGateway
        - Get-AzNatGateway
        - Set-AzNatGateway
        - Remove-AzNatGateway
   - Cmdlet yang diperbarui
        - New-AzureVirtualNetworkSubnetConfigCommand
        - Add-AzureVirtualNetworkSubnetConfigCommand
* Diperbarui di bawah perintah untuk fitur: Rute kustom yang diatur/dihapus di Gateway Gateway.
    - Diperbarui New-AzVirtualNetworkGateway: Menambahkan parameter opsional -CustomRoute untuk mengatur prefiks alamat sebagai rute kustom untuk diatur di Gateway.
    - Updated Set-AzVirtualNetworkGateway: Added optional parameter -CustomRoute to set the address prefixes as custom routes to set on Gateway.

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Dukungan untuk detail evaluasi kebijakan kueri.
    - Tambahkan parameter '-Expand' ke Get-AzPolicyState. Mendukung '-Perluas PolicyEvaluationDetails'.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan untuk Azure langganan silang untuk pemulihan situs Azure.
* Menandai perubahan terbaru yang akan datang untuk Pemulihan Situs Azure.
* Perbaikan untuk rencana tindakan akhir paket pemulihan Situs Azure.
* Perbaikan untuk pemetaan jaringan Pembaruan Pemulihan Situs Azure untuk Azure ke Azure.
* Perbaikan untuk arah perlindungan pembaruan Pemulihan Situs Azure bagi Azure bagi disk terkelola di Azure.
* Perbaikan minor lainnya.

#### <a name="azrelay"></a>Az.Relay
* Memperbaiki kesalahan ketik dalam pesan yang diterima pelanggan

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru untuk NetworkRuleSet of Namespace

#### <a name="azstorage"></a>Az.Storage
* Mutakhirkan ke Storage Client Library 10.0.1 (kumpulan nama semua objek dari perubahan SDK ini dari 'Microsoft.WindowsAzure.Storage. *' ke 'Microsoft.Azure. Storage.*')
* Mutakhirkan ke Microsoft.Azure.Management. Storage 11.0.0, untuk mendukung API versi baru 2019-04-01.
* Tipe akun Storage default dalam Membuat Storage berubah dari 'Storage' menjadi 'StorageV2'
    - New-AzStorageAccount
* Ubah output cmdlet Storage akun Sku.Name diratakan dengan SkuName input dengan menambahkan '-', seperti 'StandardLRS' berubah menjadi 'Standard_LRS'
    - New-AzStorageAccount
    - Get-AzStorageAccount
    - Set-AzStorageAccount

#### <a name="azwebsites"></a>Situs Web Az.
* Properti 'Kind' sekarang akan diatur untuk objek PSSite yang dikembalikan oleh Get-AzWebApp
* Get-AzWebApp*Metrics and Get-AzAppServicePlanMetrics marked deprecated

## <a name="180---april-2019"></a>1.8.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama terakhir
* Ketersediaan umum `Az` modul
* Untuk informasi selengkapnya tentang modul `Az` ini, silakan kunjungi: https://aka.ms/azps-announce
* Added Location, ResourceGroup, and ResourceName completers: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan wildcard untuk Mendapatkan cmdlet untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi untuk Windows PowerShell 5.1 saja
* Menambahkan dukungan untuk runbooks Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Kumpulan Akun Integrasi dan Konfigurasi Kumpulan

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Uninstall-AzureRm menghapus modul dengan benar di Mac

#### <a name="azbatch"></a>Az.Batch
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azcdn"></a>Az.Cdn
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah penginstalan AEM jika id sumber daya disk memiliki grup sumber daya huruf kecil dalam id sumber daya
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.
* Perbaiki dokumentasi untuk wildcard

#### <a name="azdatafactory"></a>Az.DataFactory
* Tambahkan SsisProperties jika NodeCount tidak null untuk runtime integrasi terkelola.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui teks bantuan untuk titik akhir agar menunjukkan bahwa sumber daya harus dibuat sebelum menggunakan cmdlet buat/perbarui langganan acara.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru untuk NetworkRuleSet of Namespace

#### <a name="azhdinsight"></a>Az.HDInsight
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="aziothub"></a>Az.IotHub
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azkeyvault"></a>Az.KeyVault
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.
* Perbaiki dokumentasi untuk wildcard

#### <a name="azmachinelearning"></a>Az.MachineLearning
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azmedia"></a>Az.Media
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azmonitor"></a>Az.Monitor
  * Cmdlet baru untuk aturan pemberitahuan berbasis metrik GenV2 (non klasik)
      - New-AzMetricAlertRuleV2DimensionSelection
      - New-AzMetricAlertRuleV2Criteria
      - Remove-AzMetricAlertRuleV2
      - Get-AzMetricAlertRuleV2
      - Add-AzMetricAlertRuleV2
  * Memperbarui Monitor SDK ke versi 0.22.0-preview

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.
* Perbaiki dokumentasi untuk wildcard

#### <a name="aznotificationhubs"></a>Az.NotificationHubs
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.
* Format tabel yang diperbarui SQL di Azure VM
* Metode alternatif yang ditambahkan untuk mengambil lokasi di AzureFileShare
* Updated ScheduleRunDays in SchedulePolicy object according to timezone

#### <a name="azrediscache"></a>Az.RedisCache
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.

#### <a name="azresources"></a>Az.Resources
* Perbaiki dokumentasi untuk wildcard

#### <a name="azsql"></a>az.sql
* Mengganti dependensi pada Monitor SDK dengan kode umum
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.
* Proses klasifikasi beberapa kolom yang disempurnakan.
* Sertakan properti sku (nama sku, keluarga, kapasitas) sebagai respons dari Get-AzSqlServerServiceObjective dan format sebagai tabel secara default.
* Kemampuan untuk Get-AzSqlServerServiceObjective lokasi tanpa membutuhkan server yang sudah ada di kawasan tersebut.
* Dukungan untuk parameter zona waktu dalam pembuatan Instans Terkelola.
* Perbaiki dokumentasi untuk wildcard

#### <a name="azwebsites"></a>Situs Web Az.
* memperbaiki Set-AzWebApp dan Set-AzWebAppSlot untuk tidak menghapus tag pada eksekusi
* Cmdlet yang diperbarui dengan kata benda jamak menjadi singular, dan nama jamak yang tidak lagi dipakai.
* Memperbarui SDK Situs Web.
* Menghapus properti AdminSiteName dari PSAppServicePlan.

## <a name="170---april-2019"></a>1.7.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama terakhir
* Ketersediaan umum `Az` modul
* Untuk informasi selengkapnya tentang modul `Az` ini, silakan kunjungi: https://aka.ms/azps-announce
* Added Location, ResourceGroup, and ResourceName completers: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan wildcard untuk Mendapatkan cmdlet untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi untuk Windows PowerShell 5.1 saja
* Menambahkan dukungan untuk runbooks Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Kumpulan Akun Integrasi dan Konfigurasi Kumpulan

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAnalysisServicesEndpointResourceId

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Menggunakan ServiceClient dalam cmdlet dataplane dan menghapus logika autentikasi asli
* Membuat Add-AzureASAccount menjadi pembungkus Connect-AzAccount untuk menghindari perubahan yang belum bisa diubah

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki New-AzAutomationSoftwareUpdateConfiguration cmdlet untuk Penyertaan. Sekarang parameter IncludedKbNumber dan IncludedPackageNameMask akan berfungsi.
* Perbaikan bug untuk grup dinamis manajemen pembaruan otomatisasi Azure

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HyperVGeneration ke New-AzDiskConfig dan New-AzSnapshotConfig
* Izinkan pembuatan VM dengan gambar vm dari penyewa lain.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbaiki masalah dalam parameter -Command parameter New-AzContainerGroup yang menambahkan argumen kosong akhir

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 3.0.2
* Diperbarui Set-AzDataFactoryV2 cmdlet dengan parameter tambahan untuk RepoConfiguration related settings.

#### <a name="azresources"></a>Az.Resources
* Meningkatkan penanganan penyedia untuk 'Get-AzResource' saat menyediakan parameter '-ResourceId' atau '-ResourceGroupName', '-Name' dan '-ResourceType'
* Meningkatkan penanganan kesalahan untuk 'Test-AzDeployment' dan 'Test-AzResourceGroupDeployment'
    - Menangani kesalahan yang dihasilkan di luar validasi penyebaran dan menyertakannya dalam output perintah sebagai gantinya
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/6856
* Menambahkan parameter sakelar '-IgnoreDynamicParameters' untuk mengatur cmdlet penyebaran untuk melewati perintah dalam skrip dan skenario pekerjaan
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/6856

#### <a name="azsql"></a>az.sql
* Mendukung Klasifikasi Data Database.

#### <a name="azstorage"></a>Az.Storage
* Kesalahan detail laporan ketika membuat Storage konteks dengan parameter -UseConnectedAccount, tetapi tanpa masuk ke akun Azure
    - New-AzStorageContext
* Dukungan Kelola Properti Layanan Blob dari akun Storage dengan API bidang Manajemen
    - Update-AzStorageBlobServiceProperty
    - Get-AzStorageBlobServiceProperty
    - Enable-AzStorageBlobDeleteRetentionPolicy
    - Disable-AzStorageBlobDeleteRetentionPolicy
* Dukungan -AsJob untuk cmdlet unggah dan unduh file Blob
    - Get-AzStorageBlobContent
    - Set-AzStorageBlobContent
    - Get-AzStorageFileContent
    - Set-AzStorageFileContent

## <a name="160---march-2019"></a>1.6.0 - Maret 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama terakhir
* Ketersediaan umum `Az` modul
* Untuk informasi selengkapnya tentang modul `Az` ini, silakan kunjungi: https://aka.ms/azps-announce
* Added Location, ResourceGroup, and ResourceName completers: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan wildcard untuk Mendapatkan cmdlet untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi untuk Windows PowerShell 5.1 saja
* Menambahkan dukungan untuk runbooks Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Kumpulan Akun Integrasi dan Konfigurasi Kumpulan

#### <a name="azautomation"></a>Az.Automation
* Perubahan manajemen pembaruan otomatisasi Azure untuk mendukung fitur baru berikut ini:
    * Mengelompokkan dinamis
    * Skrip Pra-Posting
    * Pengaturan Reboot

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah dengan resolusi jalur di Get-AzVmBootDiagnosticsData
* Perbarui Hitung pustaka klien ke 25.0.0.

#### <a name="azkeyvault"></a>Az.KeyVault
* Dukungan wildcard yang ditambahkan ke cmdlet KeyVault

#### <a name="aznetwork"></a>Az.Network
* Tambahkan dukungan Kecerdasan Ancaman untuk Azure Firewall
* Menambahkan Sumber daya tingkat atas Kebijakan Gateway Aplikasi dan Aturan Kustom

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan SnapshotRetentionInDays dalam kebijakan Azure VM untuk mendukung Instant RP
* Dukungan pipa yang ditambahkan untuk wadah unregister

#### <a name="azresources"></a>Az.Resources
* Memperbarui dukungan wildcard untuk Get-AzResource dan Get-AzResourceGroup
* Kredensial pembaruan yang digunakan saat membuat panggilan umum ke ARM

#### <a name="azsql"></a>az.sql
* mengubah cmdlet param (ExcludeDetectionType) deteksi ancaman dari DetectionType menjadi string[] untuk membuatnya bukti di masa mendatang ketika DetectionTypes baru ditambahkan dan untuk mendukung lengkapiotomatis juga.

#### <a name="azstorage"></a>Az.Storage
* Dukungan Dapatkan/Atur/Hapus Kebijakan Manajemen pada Storage Anda
    - Set-AzStorageAccountManagementPolicy
    - Get-AzStorageAccountManagementPolicy
    - Remove-AzStorageAccountManagementPolicy
    - Add-AzStorageAccountManagementPolicyAction
    - New-AzStorageAccountManagementPolicyFilter
    - New-AzStorageAccountManagementPolicyRule

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki bug templat ARM yang merusak semua slot menggunakan 'New-AzWebApp -IncludeSourceWebAppSlots'

## <a name="150---march-2019"></a>1.5.0 - Maret 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan perintah 'Register-AzModule' untuk mendukung cmdlet yang dihasilkan Auto Cmdlets
* Memperbarui contoh untuk Connect-AzAccount

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah saat pengangkut ulang jadwal bulanan tertentu dalam beberapa cmdlet Azure Automation
* Perbaiki Get-AzAutomationDscNode hanya mengembalikan 20 node teratas. Sekarang node mengembalikan semua

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet Powershell baru untuk Aktifkan/Nonaktifkan Domain Kustom Https dan menghapus yang lama

#### <a name="azcompute"></a>Az.Compute
* Menambahkan dukungan wildcard ke Cmdlet Get

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 3.0.1

#### <a name="azlogicapp"></a>Az.LogicApp
* Fix for ListWorkflows only retrieving the first page of results

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan wildcard ke cmdlet Jaringan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan server Sql dalam dukungan Azure VM
* SDK Update
* Check in VMappContainer yang dihapus Get-ProtectableItem
* Menambahkan Nama dan Nama Server sebagai parameter untuk Get-ProtectableItem

#### <a name="azresources"></a>Az.Resources
* Menambahkan `-TemplateObject` parameter ke cmdlet penyebaran
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/2933
* Perbaiki masalah saat pemipaan hasil `Get-AzResource` ke `Set-AzResource`
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8240
* Memperbaiki masalah terkait perubahan tipe data JSON ketika dijalankan `Set-AzResource`
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/7930

#### <a name="azsql"></a>az.sql
* Memperbarui AuditIngEndpointsCommunicator.
    - Memperbaiki perilaku kasus tepi saat membuat pengaturan diagnostik baru.

#### <a name="azstorage"></a>Az.Storage
* BlockBlobStorage Jenis Dukungan saat Storage saya - New-AzStorageAccount

## <a name="140---february-2019"></a>1.4.0 - Februari 2019
#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Cmdlet AddAzureASAccount yang sudah tidak berlaku

#### <a name="azautomation"></a>Az.Automation
* Bantuan pembaruan untuk Import-AzAutomationDscNodeConfiguration
* Menambahkan validasi nama konfigurasi Import-AzAutomationDscConfiguration cmdlet
* Penanganan kesalahan yang ditingkatkan Import-AzAutomationDscConfiguration cmdlet

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Added CustomSubdomainName as a new optional parameter for New-AzCognitiveServicesAccount which is used to specify subdomain for the resource.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah dengan kumpulan parameter ID
* Perbarui Get-AzVMExtension untuk mencantumkan semua ekstensi yang terinstal jika parameter Nama tidak disediakan
* Menambahkan parameter Tag dan ResourceId Update-AzImage cmdlet
* Get-AzVmssVM tanpa ID instans dan dengan InstanceView dapat mencantumkan VMSS VMSS dengan tampilan instans.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan cmdlet untuk item terhapus ADL menghitung dan memulihkan

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan properti boolean baru SkipEmptyArchives untuk Melewati Arsip Kosong dalam kelas CaptureDescription Eventhub

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki pemberian tag di Set-AzKeyVaultSecret

#### <a name="azlogicapp"></a>Az.LogicApp
* Add in Basic sku for Integration Accounts
* Tambahkan di XSLT 2.0, XSLT 3.0 dan Tipe Peta Air
* Cmdlet baru untuk Assemblies Akun Integrasi
    - Get-AzIntegrationAccountAssembly
    - New-AzIntegrationAccountAssembly
    - Remove-AzIntegrationAccountAssembly
    - Set-AzIntegrationAccountAssembly
* Cmdlet baru untuk Konfigurasi Kumpulan Akun Integrasi
    - Get-AzIntegrationAccountBatchConfiguration
    - New-AzIntegrationAccountBatchConfiguration
    - Remove-AzIntegrationAccountBatchConfiguration
    - Set-AzIntegrationAccountBatchConfiguration
* Perbarui SDK Aplikasi Logika ke versi 4.1.0

#### <a name="azmonitor"></a>Az.Monitor
* Bantuan pembaruan untuk Get-AzMetric

#### <a name="aznetwork"></a>Az.Network
* Memperbarui contoh bantuan untuk Add-AzApplicationGatewayCustomError

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Dukungan tambahan untuk sumber data Baru dan Get ApplicationInsights.
    - Menambahkan jenis 'ApplicationInsights' baru untuk mendukung Dapatkan sumber data Khusus dan Dapatkan semua ApplicationInsights untuk ruang kerja tertentu.
    - Ditambahkan New-AzOperationalInsightsApplicationInsightsDataSource cmdlet untuk membuat sumber data dengan parameter sumber Application-Insights tambahan: Id langganan, resourceGroupName dan nama.

#### <a name="azresources"></a>Az.Resources
* Perbaikan masalah https://github.com/Azure/azure-powershell/issues/8166
* Perbaikan masalah https://github.com/Azure/azure-powershell/issues/8235
* Perbaikan masalah https://github.com/Azure/azure-powershell/issues/6219
* Memperbaiki bug yang mencegah pengulangan pembuatan KeyCredentials

#### <a name="azsql"></a>az.sql
* Menambahkan dukungan untuk SQL db hyperscale tier
* Perbaikan bug yang menyebabkan pemulihan gagal karena pengaturan properti yang tidak diperlukan dalam permintaan pemulihan

#### <a name="azwebsites"></a>Situs Web Az.
* Contoh yang benar Get-AzWebAppSlotMetrics

## <a name="130---february-2019"></a>1.3.0 - Februari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Perbarui ke versi terbaru ClientRuntime

#### <a name="azanalysisservices"></a>Az.AnalysisServices
Ketersediaan umum untuk modul Az.AnalysisServices.

#### <a name="azcompute"></a>Az.Compute
* Ekstensi AEM: Tambahkan dukungan untuk disk UltraSSD dan P60,P70 dan P80
* Memperbarui deskripsi bantuan untuk Set-AzVMBootDiagnostics
* Memperbarui deskripsi bantuan dan contoh untuk Update-AzImage

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
Ketersediaan umum untuk modul Az.RecoveryServices.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki penandaan tag untuk grup sumber daya
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8166
* Memperbaiki masalah `Get-AzureRmRoleAssignment` yang tidak menghargai -ErrorAction
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8235

#### <a name="azsql"></a>az.sql
* Tambahkan Dapatkan/Set AzSqlDatabaseBackupShortTermRetentionPolicy
* Memperbaiki masalah ketika tidak masuk ke akun Azure akan menghasilkan pengecualian nullref saat menjalankan cmdlet SQL cmdlets
* Pengecualian ref null tetap di Get-AzSqlCapability

## <a name="121---january-2019"></a>1.2.1 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Rilis dengan versi Autentikasi yang benar

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Rilis dengan dependensi Autentikasi yang diperbarui

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Rilis dengan dependensi Autentikasi yang diperbarui

## <a name="120---january-2019"></a>1.2.0 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi untuk Windows PowerShell 5.1 saja
* Memperbarui URL bantuan online yang tidak benar
* Tambahkan pesan peringatan di PS Core untuk Uninstall-AzureRm

#### <a name="azaks"></a>Az.Aks
* Memperbarui URL bantuan online yang tidak benar

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk runbooks Python 2
* Memperbarui URL bantuan online yang tidak benar

#### <a name="azcdn"></a>Az.Cdn
* Memperbarui URL bantuan online yang tidak benar

#### <a name="azcompute"></a>Az.Compute
* Tambahkan Invoke-AzVMReimage cmdlet
* Menambahkan parameter TempDisk ke Set-AzVmss
* Memperbaiki pesan peringatan tentang New-AzVM

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbarui URL bantuan online yang tidak benar

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 3.0.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki masalah titik akhir ADLS ketika menggunakan MSI
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/7462
* Memperbarui URL bantuan online yang tidak benar

#### <a name="aziothub"></a>Az.IotHub
* Tambahkan format Pengodean Add-IotHubRoutingEndpoint cmdlet.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbarui URL bantuan online yang tidak benar

#### <a name="aznetwork"></a>Az.Network
* Memperbarui URL bantuan online yang tidak benar

#### <a name="azresources"></a>Az.Resources
* Memperbaiki contoh yang salah dalam dokumentasi referensi 'New-AzADAppCredential' dan 'New-AzADSpCredential'
* Memperbaiki masalah parameter '-TemplateFile' jalur yang tidak diatasi sebelum menjalankan cmdlet penyebaran grup sumber daya
* Az.Resources: Dokumentasi yang benar untuk New-AzureRmPolicyDefinition default -Mode
* Az.Resources: Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/7522
* Az.Resources: Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/5747
* Memperbaiki masalah pemformatan dengan objek 'PSResourceGroupDeployment'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/2123

#### <a name="azservicefabric"></a>az.servicefabric
* Kembali saat sertifikat ditambahkan ke model VMSS, tetapi pengecualian dilakukan untuk memperbaiki bug: https://github.com/Azure/service-fabric-issues/issues/932
* Memperbaiki beberapa pesan kesalahan.
* Perbaiki kluster dengan templat ARM default untuk New-AzServiceFabriCluster yang tidak berfungsi dengan migrasi ke Az.
* Perbaiki penambahan sertifikat kluster/aplikasi agar hanya ditambahkan ke Kumpulan Skala VM yang sesuai dengan kluster dengan memeriksa id kluster dalam ekstensi.

#### <a name="azsignalr"></a>az.signalr
* Memperbarui URL bantuan online yang tidak benar

#### <a name="azsql"></a>az.sql
* Memperbarui URL bantuan online yang tidak benar
* Deskripsi parameter yang diperbarui untuk parameter LicenseType dengan nilai yang mungkin
* Perbaikan untuk memperbarui identitas instans terkelola tidak berfungsi jika merupakan satu-satunya properti yang diperbarui
* Dukungan untuk kolaborasi kustom pada instans terkelola

#### <a name="azstorage"></a>Az.Storage
* Memperbarui URL bantuan online yang tidak benar
* Berikan pesan kesalahan detail ketika mendapatkan/mengatur Pembuatan Log/Metrik klasik Premium Storage Metrik, karena Premium Storage Bukan Pembuatan Log/Metrik klasik.
    - Get/Set-AzStorageServiceLoggingProperty
    - Get/Set-AzStorageServiceMetricsProperty

#### <a name="aztrafficmanager"></a>az.trafficmanager
* Memperbarui URL bantuan online yang tidak benar

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbarui URL bantuan online yang tidak benar
* Memperbaiki 'New-AzWebAppSSLBinding' untuk mengunggah sertifikat ke resourcegroup+location yang benar jika aplikasi dihosting di ASE.
* Memperbaiki 'New-AzWebAppSSLBinding' untuk tidak menimpa tag saat mengikat sertifikat SSL ke sebuah aplikasi

## <a name="110---january-2019"></a>1.1.0 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Lingkup 'Lokal' ke Enable-AzureRmAlias

#### <a name="azcompute"></a>Az.Compute
* Nama sekarang opsional dalam parameter ID diatur untuk Mulai Ulang/Mulai/Hentikan/Hapus/Set-AzVM dan Save-AzVMImage
* Memperbarui deskripsi ID dalam file bantuan
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbarui versi sdk dataplane ke 1.1.14 untuk perbaikan SDK.
    - Memperbaiki penanganan waktu akses negatif dan waktu modifikasi untuk getfilestatus dan liststatus, Perbaiki token pembatalan async

#### <a name="azeventgrid"></a>Az.EventGrid
* Diperbarui untuk menggunakan versi API 2019-01-01.
* Perbarui cmdlet berikut untuk mendukung skenario baru dalam versi API 2019-01-01
    - New-AzureRmEventGridSubscription: Tambahkan parameter opsional baru untuk menentukan:
        - Waktu acara-untuk-Langsung,
        - Jumlah maksimum upaya pengiriman untuk peristiwa tersebut,
        - Titik akhir huruf maut.
    - Update-AzureRmEventGridSubscription: Tambahkan parameter opsional baru untuk menentukan:
        - Waktu acara-untuk-Langsung,
        - Jumlah maksimum upaya pengiriman untuk peristiwa tersebut,
        - Titik akhir huruf maut.
* Tambahkan nilai enum baru (namely, storageQueue dan hybridConnection) untuk opsi EndpointType dalam New-AzureRmEventGridSubscription Update-AzureRmEventGridSubscription cmdlets.
* Perlihatkan pesan peringatan jika membuat atau memperbarui langganan acara diharapkan untuk mengharuskan tindakan manual dari pengguna.

#### <a name="aziothub"></a>Az.IotHub
* Diperbarui ke versi terbaru IotHub SDK

#### <a name="azlogicapp"></a>Az.LogicApp
* Get-AzLogicApp mencantumkan semua tanpa Nama yang ditentukan

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah pengaturan parameter saat menyediakan parameter '-ODataQuery' dan '-ResourceId' untuk 'Get-AzResource'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/7875
* Memperbaiki penanganan parameter -Custom dalam New/Set-AzPolicyDefinition
* Memperbaiki kesalahan ketik New-AzDeployment dokumentasi
* Buat parameter '-MailNickname' wajib untuk 'New-AzADUser'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8220

#### <a name="azsignalr"></a>az.signalr
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

#### <a name="azsql"></a>az.sql
* Mengonversi dependensi Storage manajemen klien menjadi implementasi SDK umum.

#### <a name="azstorage"></a>Az.Storage
* Mengatur StorageAccountName Storage konteks sebagai nama Storage asli, saat dibuat dengan Sas Token, OAuth atau Anonim
    - New-AzStorageContext
* Buat Sas Token Dari Objek Snapshot Blob dengan parameter '-FullUri', perbaiki Uri yang dikembalikan menjadi tangkapan layar Uri
    - New-AzStorageBlobSASToken

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki bug penguraian tanggal dalam 'Get-AzDeletedWebApp'
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

## <a name="100---december-2018"></a>1.0.0 - Desember 2018
### <a name="general"></a>Umum

- Ketersediaan Umum Az Module
- Bantuan online untuk setiap modul
- Untuk detail dan peta strategi selengkapnya, lihat halaman [Pengumuman Az](https://aka.ms/azps-announce)
- Lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk informasi tentang melakukan migrasi dari AzureRM

### <a name="azaccounts"></a>Az.Accounts
- Diubah dari Az.Profile
- Memperbaiki format tabel untuk profil dan tipe konteks

### <a name="azapimanagement"></a>Az.ApiManagement
- Perbaikan untuk #7002
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azbatch"></a>Az.Batch
- Menambahkan kemampuan untuk melihat versi Agen Node Azure Batch yang dijalankan pada setiap VM dalam kumpulan, melalui properti `NodeAgentInformation` baru pada `PSComputeNode` .
- Default `Caching` untuk `PSDataDisk` sekarang, bukan `ReadWrite` `None` .
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azbilling"></a>Az.Billing
- Menggabungkan cmdlet Tagihan, Pemakaian, dan PenggunaanAggregates, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azcognitivservices"></a>Az.CognitivServices
- Menambahkan completer untuk SkuName dan Typem yang tersedia New-AzureRmCognitiveServicesAccount operasi
- Kumpulan parameter GetSkusWithAccountParamSetName yang dihapus dari Get-AzCognitiveServicesAccountSkus

### <a name="azcontainerinstance"></a>Az.ContainerInstance
- Dukungan ManagedIdentity yang ditambahkan

### <a name="azdatalakeanalytics"></a>Az.DataLakeAnalytics
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azdatalakestore"></a>Az.DataLakeStore
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azmonitor"></a>Az.Monitor
- Diubah namanya az.Insights menjadi Az.Monitor dan perubahan minor lainnya, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azkeyvault"></a>Az.KeyVault
- Menghapus properti 'PurgeDisabled' yang sudah tidak berlaku dari tipe output

### <a name="azmachinelearning"></a>Az.MachineLearning
- Menyertakan cmdlet dari modul Az.MachineLearningCompute

### <a name="azmedia"></a>Az.Media
- Hapus alias -Tag yang tidak lagi dipakai New-AzMediaService

### <a name="aznetwork"></a>Az.Network
Menambahkan dukungan untuk mengonfigurasi RewriteRuleSets di Gateway Aplikasi
    - Cmdlet baru ditambahkan:
        - Add-AzureRmApplicationGatewayRewriteRuleSet
        - Get-AzureRmApplicationGatewayRewriteRuleSet
        - New-AzureRmApplicationGatewayRewriteRuleSet
        - Remove-AzureRmApplicationGatewayRewriteRuleSet
        - Set-AzureRmApplicationGatewayRewriteRuleSet
        - New-AzureRmApplicationGatewayRewriteRule
        - New-AzureRmApplicationGatewayRewriteRuleActionSet
        - New-AzureRmApplicationGatewayRewriteRuleHeaderConfiguration
    - Cmdlet yang diperbarui dengan parameter opsional -RewriteRuleSet
        - New-AzureRmApplicationGateway
        - New-AzureRmApplicationGatewayRequestRoutingRule
        - Add-AzureRmApplicationGatewayRequestRoutingRule
        - New-AzureRmApplicationGatewayPathRuleConfig
        - Add-AzureRmApplicationGatewayUrlPathMapConfig
        - New-AzureRmApplicationGatewayUrlPathMapConfig Menambahkan Dukungan KeyVault ke Gateway Aplikasi menggunakan Identitas.
    - Cmdlet diperbarui dengan parameter optonal -KeyVaultSecretId, -KeyVaultSecret
        - Add-AzApplicationGatewaySslCertificate
        - New-AzApplicationGatewaySslCertificate
        - Set-AzApplicationGatewaySslCertificate
    - New-AzApplicationGateway cmdlet diperbarui dengan parameter opsional -UserAssignedIdentity
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azoperationalinsights"></a>Az.OperationalInsights
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azprofile"></a>Az.Profile
- Nama modul yang diubah menjadi Az.Accounts

### <a name="azrecoveryservices"></a>Az.RecoveryServices
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azresources"></a>Az.Resources
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azservicefabric"></a>az.servicefabric
- Mendukung sertifikat berspasi berdasarkan nama umum dan thumbprint
- Mengetahui perubahan terbaru, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azsignalr"></a>az.signalr
- Ketersediaan Umum untuk cmdlet PowerShell untuk SIgnalR

### <a name="azsql"></a>az.sql
- Menambahkan fitur Data_Exfiltration dan Unsafe_Action deteksi baru ke cmdlet Threat Detection
- Contoh dokumentasi yang diperbarui untuk cmdlet Pengauditan Sql
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azstorage"></a>Az.Storage
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azwebsites"></a>Situs Web Az.
- Perubahan minor yang tidak sama, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

## <a name="070---december-2018"></a>0.7.0 - Desember 2018

### <a name="general"></a>Umum

* Perubahan minor untuk transisi AzureRM ke Az yang akan datang

### <a name="azcompute"></a>Az.Compute

* Tambahkan dukungan untuk UltraSSD dan Gambar Galeri dalam set param sederhana `New-AzVm(ss)` untuk cmdlet.

### <a name="azdatalakestore"></a>Az.DataLakeStore

* Memperbaiki garis miring di akhir domain akun adls

### <a name="azfrontdoor"></a>Az.FrontDoor

* Memperbaiki beberapa tautan yang rusak
    - Dalam artikel New-AzureRmFrontDoor dan Set-AzureRmFrontDoor, perbaiki tautan ke artikel cmdlet New-AzureRmFrontDoorHealthProbeSettingObject cmdlet.
    - Dalam artikel New-AzureRmFrontDoorManagedRuleObject ini, memperbaiki tautan ke New-AzureRmFrontDoorRuleGroupOverrideObject cmdlet.

### <a name="azrecoveryservices"></a>Az.RecoveryServices

* Menambahkan validasi sisi klien untuk operasi pemulihan Berbagi File Azure.
* Made storageAccountName and storageAccountResourceGroupName opsional untuk pemulihan afs.

### <a name="azresources"></a>Az.Resources

* Perbaikan untuk https://github.com/Azure/azure-powershell/issues/7679
    - Perbarui Get-AzureRmRoleAssignment untuk menggunakan lingkup langganan jika tersedia saat meminta administrator klasik.

### <a name="azsql"></a>az.sql

* Perubahan minor untuk transisi AzureRM ke Az yang akan datang
* Memperbaiki masalah penggunaan Get-AzureRmSqlDatabaseVulnerabilityAssessment dengan inti DotNet
* Modified documentation of help messages related to SQL Auditing cmdlets.

### <a name="azstorage"></a>Az.Storage

* Tambahkan -EnableHierarchicalNamespace untuk New-AzureRmStorageAccount
* Perbaiki masalah cmdlet Salin File tidak dapat menggunakan kembali konteks sumber di tujuan ketika tidak memasukkan -DestContext
    - Start-AzureStorageFileCopy
* Mendukung konfigurasi Situs Web Statis
    - Enable-AzureStorageStaticWebsite
    - Disable-AzureStorageStaticWebsite

### <a name="azwebsites"></a>Situs Web Az.

* Set-AzureRmWebApp dan Set-AzureRmWebAppSlot
    - Parameter baru (-AzureStoragePath) ditambahkan untuk menentukan jalur Azure Storage akan terpasang dalam aplikasi wadah Windows Linux dan Windows. Gunakan output cmdlet baru yang New-AzureRmWebAppAzureStoragePath sebagai parameter untuk mengatur jalur Azure Storage.

## <a name="061---november-2018"></a>0.6.1 - November 2018

### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azautomation"></a>Az.Automation
* Cmdlet Otomatisasi Azure berbasis Swagger
* Cmdlet Manajemen Pembaruan tambahan
* Cmdlet Kontrol Sumber Ditambahkan
* Cmdlet Remove-AzureRmAutomationHybridWorkerGroup ditambahkan
* Memperbaiki perintah Node Register DSC

### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah identitas untuk Identitas SystemAssigned
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* perbarui deskripsi contoh untuk cmdlet marketplace

### <a name="aznetwork"></a>Az.Network
* Ditambahkan cmdlet New-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayCustomError, Get-AzureRmApplicationGatewayCustomError, Set-AzureRmApplicationGatewayCustomError, Remove-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayhttpListenerCustomError, Get-AzureRmApplicationGatewayhttpListenerCustomError, Set-AzureRmApplicationGatewayHttpListenerCustomError, Remove-AzureRmApplicationGatewayHttpListenerCustomError
* Menambahkan icMP kembali ke AzureFirewall Network Protocols yang didukung
* Perbarui cmdlet Test-AzureRmNetworkWatcherConnectivity, tambahkan validasi pada id tujuan, alamat dan port.
* Memperbaiki masalah penggunaan memori di Peta jaringan Virtual

### <a name="azrecoveryservicesbackup"></a>Az.RecoveryServices.Backup
* Perbaikan untuk mengubah kebijakan untuk berbagi file yang diproteksi.
* Zona waktu kebijakan yang dikonversi menjadi huruf besar.

### <a name="azrecoveryservicessiterecovery"></a>Az.RecoveryServices.SiteRecovery
* Contoh yang diperbaiki dalam New-AzureRmRecoveryServicesAsrProtectableItem
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azrelay"></a>Az.Relay
* Added optional Parameter -KeyValue to New-AzureRmRelayKey cmdlet, which enables user to provide KeyValue.

### <a name="azresources"></a>Az.Resources
* Memperbarui dokumentasi bantuan untuk parameter terkait identitas sumber daya `New-AzureRmPolicyAssignment` di dan `Set-AzureRmPolicyAssignment`
* Menambahkan contoh untuk New-AzureRmPolicyDefinition yang menggunakan -Metadata
* Perbaikan untuk memungkinkan mempertahankan huruf dalam tombol Tag di NetStandard: #7678 #7703

### <a name="azservicefabric"></a>az.servicefabric
* Tambahkan pesan penghentian untuk perubahan yang akan datang

### <a name="azsql"></a>az.sql
* Menambahkan cmdlet baru untuk operasi CRUD di Azure Sql Database Managed Instance dan Database Azure Sql Managed
    - Get-AzureRmSqlInstance
    - New-AzureRmSqlInstance
    - Set-AzureRmSqlInstance
    - Remove-AzureRmSqlInstance
    - Get-AzureRmSqlInstanceDatabase
    - New-AzureRmSqlInstanceDatabase
    - Restore-AzureRmSqlInstanceDatabase
    - Remove-AzureRmSqlInstanceDatabase
* Manajemen Kebijakan Audit Diperluas yang Diaktifkan di server atau database.
    - Parameter baru (PredicateExpression) ditambahkan untuk mengaktifkan pemfilteran log audit.
    - Cmdlet telah diubah untuk menggunakan klien SQL, bukan klien Warisan.
    - Set-AzureRmSqlServerAuditing.
    - Get-AzureRmSqlServerAuditing.
    - Set-AzureRmSqlDatabaseAuditing.
    - Get-AzureRmSqlDatabaseAuditing.
* Memperbaiki masalah penggunaan Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings dengan kumpulan parameter nama akun penyimpanan

## <a name="050---november-2018"></a>0.5.0 - November 2018
#### <a name="general"></a>Umum
* Penambahan Selesai Sumber Daya ke banyak cmdlet inti, semuanya memungkinkan Anda untuk menemukan nama sumber daya yang ada saat cmdlet menggunakan cmdlet secara interaktif

#### <a name="azprofile"></a>Az.Profile
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime
* Ganti nama Id Tenant di cmdlet Connect-AzAccount ke Tenant dan tambahkan alias untuk TenantId
* Deskripsi TenantId yang diperbarui untuk Connect-AzAccount
* Pesan kesalahan perbaikan gagal masuk saat menyediakan domain penyewa
    - https://github.com/Azure/azure-powershell/issues/6936
* Perbaiki masalah terkait nama konteks yang bentrok untuk akun tanpa langganan dalam penyewa
    - https://github.com/Azure/azure-powershell/issues/7453
* Memperbaiki masalah titik akhir DataLake saat menggunakan MSI
    - https://github.com/Azure/azure-powershell/issues/7462
* Memperbaiki masalah ketika 'Disconnect-AzAccount' akan muncul jika tidak tersambung
    - https://github.com/Azure/azure-powershell/issues/7167

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan Get-AzCognitiveServicesAccountSkus otomatis.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan Add-AzVmssVMDataDisk cmdlet Remove-AzVmssVMDataDisk dan add-in
* Get-AzVMImage memperlihatkan AutomaticOSUpgradeProperties
* Memperbaiki nilai opsi SetAzVMChefExtension -BootstrapOptions dan -JsonAttribute tidak diatur dalam format json.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbarui paket DataLake ke 1.1.10.
* Tambahkan Konkurensi default ke operasi multithreaded.

#### <a name="azinsights"></a>Az.Insights
* Memperbaiki masalah #7267 (area Skala Otomatis)
    - Masalah dengan pembuatan aturan skala otomatis baru yang tidak mengatur parameter yang dienumerasi dengan benar (akan selalu mengaturnya ke nilai default).
* Memperbaiki masalah #7513 [Insights] Set-AzDiagnosticSetting memerlukan spesifikasi kategori eksplisit selama pembuatan pengaturan
    - Sekarang cmdlet tidak mengharuskan indikasi kategori eksplisit untuk mengaktifkan selama pembuatan, misalnya saat kategori itu berfungsi sebagaimana didokumentasikan

#### <a name="aznetwork"></a>Az.Network
* Changed PeeringType to be a mandatory parameter for the following cmdlets:-
    - Get-AzExpressRouteCircuitRouteTable
    - Get-AzExpressRouteCircuitARPTable
    - Get-AzExpressRouteCircuitRouteTableSummary
    - Get-AzExpressRouteCrossConnectionArpTable
    - Get-AzExpressRouteCrossConnectionRouteTable
    - Get-AzExpressRouteCrossConnectionRouteTableSummary

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Cmdlet perbaikan kebijakan yang ditambahkan

#### <a name="azresources"></a>Az.Resources
* Perbaikan untuk https://github.com/Azure/azure-powershell/issues/7402
    - Perbolehkan daftar sumber daya menggunakan parameter '-ResourceId' untuk 'Get-AzResource'

#### <a name="azservicebus"></a>Az.ServiceBus
* Added MigrationState read-only property to PSServiceBusMigrationConfigurationAttributes which will help to know the Migration state.

#### <a name="azservicefabric"></a>az.servicefabric
* Perbaiki penambahan sertifikat untuk Vms Linux.
* Memperbaiki 'Add-AzServiceFabricClusterCertificate'
    - Menggunakan thumbprint yang benar dari sertifikat baru (Azure/service-fabric-issues#932).
    - Display exception correctly (Azure/service-fabric-issues#1054).
* Perbaiki 'Update-AzServiceFabricDurability' untuk memperbarui konfigurasi kluster sebelum memulai operasi Vmss CreateOrUpdate.

## <a name="040---october-2018"></a>0.4.0 - Oktober 2018
#### <a name="azprofile"></a>Az.Profile
* Memperbaiki masalah terkait Get-AzSubscription di CloudShell
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azcompute"></a>Az.Compute
* Menambahkan ukuran baru pada daftar ukuran VM yang diizinkan ketika jaringan yang dipercepat akan diaktifkan ketika menggunakan kumpulan param sederhana untuk 'New-AzVm'
* Penambahan selesai argumen ResourceName ke semua cmdlet.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan dukungan untuk Aturan Jaringan Virtual
    - Get-AzDataLakeStoreVirtualNetworkRule: Mendapatkan atau Mencantumkan aturan jaringan virtual Azure Data Lake Store.
    - Add-AzDataLakeStoreVirtualNetworkRule: Menambahkan aturan jaringan virtual ke akun Data Lake Store yang ditentukan.
    - Set-AzDataLakeStoreVirtualNetworkRule: Mengubah aturan jaringan virtual tertentu di akun Data Lake Store yang ditentukan.
    - Remove-AzDataLakeStoreVirtualNetworkRule: Menghapus aturan jaringan virtual Azure Data Lake Store.

#### <a name="aznetwork"></a>Az.Network
* Perbarui cmdlet Test-AzNetworkWatcherConnectivity, berikan nilai protokol ke backend.
* Penambahan selesai argumen ResourceName ke semua cmdlet.

#### <a name="azresources"></a>Az.Resources
* Fix isssue where Get-AzRoleDefinition throws an unintelligible exception (when the default profile has no subscription in it and no scope is specified) by adding a meaningful exception in the scenario. Juga setel param default ke 'RoleDefinitionNameParameterSet'.

## <a name="030---october-2018"></a>0.3.0 - Oktober 2018
#### <a name="azurestorage"></a>Azure. Storage
* Perbaiki Salin Blob/File tidak akan menyalin metadata ketika tujuan memiliki masalah metadata
    - Start-AzureStorageBlobCopy
    - Start-AzureStorageFileCopy
* Dukungan mendapatkan Storage sumber daya lokasi tertentu, dan menambahkan pesan peringatan untuk mendapatkan penggunaan sumber Storage global sudah tak t fungsi.
    - Get-AzStorageUsage

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Dukungan Get-AzCognitiveServicesAccountSkus tanpa akun yang sudah ada.

#### <a name="azcompute"></a>Az.Compute
* Perbaiki Get-AzVM -ResourceGroupName `<rg>` untuk mengembalikan lebih dari 50 hasil jika diperlukan
* Menambahkan contoh 'SimpleParameterSet' untuk New-AzVmss cmdlet.
* Memperbaiki kesalahan ketik dalam pesan kemajuan Enkripsi Disk Azure

#### <a name="azdatafactoryv2"></a>Az.DataFactoryV2
* Memperbarui versi .Net SDK ADF ke 2.3.0.

#### <a name="aznetwork"></a>Az.Network
* Fungsionalitas NetworkProfile yang ditambahkan. cmdlet baru ditambahkan
    - Get-AzNetworkProfile
    - New-AzNetworkProfile
    - Remove-AzNetworkProfile
    - Set-AzNetworkProfile
    - New-AzContainerNicConfig
    - New-AzContainerNicConfigIpConfig
* Tautan asosiasi layanan yang ditambahkan pada Model Subnet
* Menambahkan cmdlet New-AzVirtualNetworkTap, Get-AzVirtualNetworkTap, Set-AzVirtualNetworkTap, Remove-AzVirtualNetworkTap
* Added cmdlet Set-AzNEtworkInterfaceTapConfig, Get-AzNEtworkInterfaceTapConfig, Remove-AzNEtworkInterfaceTapConfig

#### <a name="azrediscache"></a>Az.RedisCache
* Perbolehkan string apa pun sebagai parameter Ukuran ke depan. Tambahkan P5 di popup PSA argumentmentCompleter

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter -Mode hilang ke Set-AzPolicyDefinition
* Memperbaiki Get-AzProviderOperation commandlet untuk operasi dengan Origin yang berisi Pengguna

#### <a name="azsql"></a>az.sql
* Memperbaiki masalah ketika beberapa cmdlet cadangan tidak mengenali langganan Azure saat ini

#### <a name="azwebsites"></a>Situs Web Az.
* Perintah Cmdlet Get-AzWebAppContainerContinuousDeploymentUrl - Mendapatkan URL Container Continuous Deployment Webhook
* Cmdlet Baru New-AzWebAppContainerPSSession dan Enter-WebAppContainerPSSession - Memulai sesi jarak jauh PowerShell ke aplikasi wadah windows

## <a name="020---september-2018"></a>0.2.0 - September 2018
 Rilis Awal