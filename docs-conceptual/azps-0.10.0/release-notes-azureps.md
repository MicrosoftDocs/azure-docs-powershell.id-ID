---
title: Catatan rilis Azure PowerShell
description: Pelajari tentang semua pembaruan terbaru untuk modul Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/10/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: bcc219695687605e8a6b0c49762e374dc09d3f09
ms.sourcegitcommit: 2b90f2e68e4992e43f16a51f69e5581db189440b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/26/2022
ms.locfileid: "137778622"
---
# <a name="azure-powershell-release-notes"></a>Catatan rilis Azure PowerShell
## <a name="0100-preview---april-2020"></a>0.10.0-preview - April 2020
### <a name="general"></a>Umum
* Modul Az sekarang tersedia dalam pratinjau di Azure Stack Hub. Hal ini memungkinkan kompatibilitas lintas platform dengan Linux dan macOs. Azure Stack Hub sekarang mendukung inti PowerShell dengan modul Az, informasi lebih lanjut [di sini](/azure-stack/operator/powershell-install-az-module)
* Modul Az mendukung profil 2019-03-01-hybrid:
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
  - Az.Websites
* Tiga modul PowerShell baru untuk az yang bekerja dengan Azure Stack Hub telah diperkenalkan, yaitu Az.Databox, Az.IotHub, dan Az.EventHub
* Perintah tetap relatif sama dengan perubahan kecil, seperti mengubah AzureRM ke Az
* Link yang diperbarui ke dokumentasi PowerShell untuk Azure Stack Hub dapat ditemukan [di sini](/azure-stack/operator/powershell-install-az-module)

#### <a name="azaccounts"></a>Az.Accounts
* Meningkatkan dari ADAL ke MSAL


## <a name="370---march-2020"></a>3.7.0 - Maret 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki 'Get-AzTenant'/'Get-AzDefault'/'Set-AzDefault' yang mengeluarkan NullReferenceException saat tidak login [#10292]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter berikut ke cmdlet 'New-AzDiskConfig':
    - DiskIOPSReadOnly, DiskMBpsReadOnly, MaxSharesCount, GalleryImageReference
* Mengizinkan Properti Enkripsi ke parameter Target cmdlet 'New-AzGalleryImageVersion'.
* Memperbaiki masalah tempDisk untuk cmdlet 'Set-AzVmss' -Reimage dan 'Invoke-AzVMReimage'. [#11354]
* Menambahkan dukungan ke cmdlet di bawah ini untuk Ekstensi SAP baru
    - 'Set-AzVMAEMExtension'
    - 'Get-AzVMAEMExtension'
    - 'Remove-AzVMAEMExtension'
    - 'Update-AzVMAEMExtension'
* Memperbaiki kesalahan dalam contoh dokumen bantuan
* Menampilkan nilai string yang tepat untuk PowerState mesin virtual dalam format tabel.
* 'New-AzVmssConfig': memperbaiki serialisasi properti AutomaticRepairs saat SinglePlacementGroup dinonaktifkan. [#11257]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.8.0
* Menambahkan parameter opsional ke perintah 'Invoke-AzDataFactoryV2Pipeline' untuk mendukung eksekusi ulang

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan deskripsi perubahan yang berisiko untuk 'Export-AzDataLakeStoreItem' dan 'Import-AzDataLakeStoreItem'
* Menambahkan opsi pengodean Byte untuk 'New-AzDataLakeStoreItem', 'Add-AzDAtaLakeStoreItemContent', dan 'Get-AzDAtaLakeStoreItemContent'

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung penentuan versi TLS yang didukung minimal saat membuat kluster.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola pengaturan terdistribusi per perangkat. Cmdlet baru adalah:
    - 'Get-AzIotHubDistributedTracing'
    - 'Set-AzIotHubDistributedTracing'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan atribut perubahan berisiko ke 'New-AzKeyVault'

#### <a name="azmonitor"></a>Az.Monitor
* Memperbarui dokumentasi untuk 'New-AzScheduledQueryRuleLogMetricTrigger'

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk memungkinkan VirtualHubVnetConnections lintas penyewa
    - 'New-AzVirtualHubVnetConnection'
    - 'Update-AzVirtualHubVnetConnection'
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Menghapus dependensi SDK Manajemen Sql

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Meningkatkan pesan kesalahan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery menambahkan dukungan untuk melakukan perlindungan ulang dan memperbarui properti mesin virtual untuk Virtual Machines terenkripsi disk Azure.
* Menambahkan pemantauan DR properti VmwareToAzure Azure Site Recovery
* Azure Backup menambahkan dukungan untuk kebijakan percobaan kembali pada item yang gagal.
* Azure Backup Menambahkan dukungan untuk pengaturan pengecualian disk selama pencadangan dan pemulihan.
* Azure Backup Menambahkan Dukungan untuk Memulihkan Beberapa file/folder di AzureFileShare
* Azure Backup Menambahkan dukungan untuk dukungan Resourcegroup yang ditentukan Pengguna saat memperbarui Kebijakan IaasVM

#### <a name="azresources"></a>Az.Resources
* Memperbaiki 'Get-AzResource -ResourceGroupName -Name -ExpandProperties -ResourceType' agar menggunakan apiVersion sumber daya yang sebenarnya dan bukan apiVersion default [#11267]
* Menambahkan pengelogan correlationId untuk skenario kesalahan
* Perubahan dokumentasi kecil pada 'Get-AzResourceLock'. Menambahkan contoh.
* Memberi tanda escape pada kutipan tunggal dalam nilai parameter 'Get-AzADUser' [#11317]
* Menambahkan cmdlet baru untuk Skrip Penyebaran ('Get-AzDeploymentScript', 'Get-AzDeploymentScriptLog', 'Save-AzDeploymentScriptLog', 'Remove-AzDeploymentScript')

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter sekunder yang dapat dibaca ke 'Invoke-AzSqlDatabaseFailover'
* Menambahkan cmdlet 'Disable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menyimpan pangkat sensitivitas saat mengklasifikasikan kolom dalam database.

#### <a name="azsupport"></a>Az.Support
* Ketersediaan umum modul 'Az.Support'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk bekerja dengan Aturan Perutean Lalu Lintas aplikasi web melalui cmdlet baru di bawah ini
    - 'Get-AzWebAppTrafficRouting'
    - 'Update-AzWebAppTrafficRouting'
    - 'Add-AzWebAppTrafficRouting'
    - 'Remove-AzWebAppTrafficRouting'

## <a name="361---march-2020"></a>3.6.1 - Maret 2020
#### <a name="azaccounts"></a>Az.Accounts
* Membuka halaman survei Azure PowerShell di 'Kirim-Umpan Balik' [#11020]
* Menampilkan URL survei Azure PowerShell di 'Selesaikan-Kesalahan' [#11021]
* Menambahkan versi Az di UserAgent

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan dukungan untuk mengambil dan mengonfigurasi Domain Kustom pada Titik Akhir DeveloperPortal [#11007]
* 'Export-AzApiManagementApi' Menambahkan dukungan untuk mengunduh Definisi Api dalam format Json [#9987]
* 'Import-AzApiManagementApi' Menambahkan dukungan untuk mengimpor definisi OpenApi 3.0 dari dokumen Json
* 'New-AzApiManagementIdentityProvider' dan 'Set-AzApiManagementIdentityProvider' Menambahkan dukungan untuk mengonfigurasi 'Penyewa Masuk' untuk Penyedia AAD B2C [#9784]

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan referensi ke System.Buffers secara eksplisit di csproj dan psd1.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola perangkat di Iot Hub. Cmdlet baru adalah:
    - 'Add-AzIotHubDevice'
    - 'Get-AzIotHubDevice'
    - 'Remove-AzIotHubDevice'
    - 'Set-AzIotHubDevice'
* Menambahkan dukungan untuk mengelola modul pada perangkat Iot target di Iot Hub. Cmdlet baru adalah:
    - 'Add-AzIotHubModule'
    - 'Get-AzIotHubModule'
    - 'Remove-AzIotHubModule'
    - 'Set-AzIotHubModule'
* Menambahkan cmdlet untuk mendapatkan string koneksi perangkat IoT target di Iot Hub.
* Menambahkan cmdlet untuk mendapatkan string koneksi modul pada perangkat IoT target di Iot Hub.
* Menambahkan dukungan untuk mendapatkan/mengatur perangkat induk perangkat IoT. Cmdlet baru adalah:
    - 'Get-AzIotHubDeviceParent'
    - 'Set-AzIotHubDeviceParent'
* Menambahkan dukungan untuk mengelola hubungan perangkat induk-turunan.

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nilai output untuk 'Get-AzMetricDefinition' [#9714]

#### <a name="aznetwork"></a>Az.Network
* Memperbarui SDK Manajemen Sql.
* Memperbaiki masalah perbedaan penamaan di kelas PrivateLinkServiceConnectionState.
    - Memetakan bidang ActionsRequired ke ActionRequired.
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug referensi null di 'Get-AzRoleAssignment'
* Menandai sakelar '-Force' dan '-PassThru' sebagai opsional di 'Remove-AzADGroup' [#10849]
* Memperbaiki masalah 'MailNickname' tidak muncul di 'Remove-AzADGroup' [#11167]
* Memperbaiki masalah operasi pipa 'Remove-AzADGroup' tidak berfungsi [#11171]
* Memperbaiki bug referensi null di GetAzureRoleAssignmentCommand
* Menambahkan atribut perubahan berisiko untuk perubahan yang akan datang ke cmdlet kebijakan
* Memperbarui 'Get-AzResourceGroup' untuk melakukan pemfilteran tag grup sumber daya di sisi server
* Memperpanjang cmdlet Tag untuk menerima -ResourceId
    - Get-AzTag -ResourceId
    - New-AzTag -ResourceId
    - Remove-AzTag -ResourceId
* Menambahkan cmdlet Tag baru
    - Update-AzTag -ResourceId
* Membawa ScopedDeployment dari SDK 3.3.0

#### <a name="azsql"></a>Az.Sql
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Menambahkan dukungan pada konfigurasi cadangan Retensi Jangka Panjang untuk Database Terkelola
    - Mendapatkan/mengatur kebijakan LTR pada database terkelola
    - Mendapatkan pencadangan LTR berdasarkan database terkelola, instans terkelola, atau berdasarkan lokasi
    - Menghapus cadangan LTR
    - Memulihkan cadangan LTR untuk membuat database terkelola baru
* Menambahkan MinimalTlsVersion ke New-AzSqlServer dan Set-AzSqlServer
* Menambahkan MinimalTlsVersion ke New-AzSqlInstance dan Set-AzSqlInstance
* Mengubah SQL versi SDK untuk Az.Network

#### <a name="azstorage"></a>Az.Storage
* Mendukung AllowProtectedAppendWrite di ImmutabilityPolicy
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
* Menambahkan pesan peringatan perubahan berisiko untuk perubahan jenis AzureStorageTable di rilis mendatang
    - 'New-AzStorageTable'
    - 'Get-AzStorageTable'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan parameter Tag untuk 'New-AzAppServicePlan' dan 'Set-AzAppServicePlan'
* Menghentikan eksekusi cmdlet jika pengecualian dikeluarkan saat menambahkan domain kustom ke situs web
* Menambahkan dukungan untuk melakukan operasi untuk App Services yang tidak berada dalam grup sumber daya yang sama dengan Paket App Service
* Menerapkan pembatasan akses ke Aplikasi Web/Fungsi di grup sumber daya yang berbeda
* Memperbaiki masalah saat mengatur nama host kustom untuk WebAppSlots

## <a name="350---february-2020"></a>3.5.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama sebelumnya
* Mempebarui telemetri sisi klien.
* Az.IotHub menambahkan cmdlet untuk mendukung pengelolaan perangkat.
* Az.SqlVirtualMachine menambahkan cmdlet untuk Pendengar Grup Ketersediaan.

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan SubscriptionId, TenantId, dan waktu eksekusi ke dalam data telemetri sisi klien

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan ketik di Contoh 1 dalam dokumentasi referensi untuk 'New-AzAutomationSoftwareUpdateConfiguration'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui SDK ke 7.0
* Memperbarui pesan kesalahan saat isi respons server kosong

#### <a name="azcompute"></a>Az.Compute
* Mengizinkan nilai kosong untuk ProximityPlacementGroupId selama pembaruan

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan cmdlet untuk mendapatkan definisi aturan terkelola yang dapat digunakan di WAF

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola perangkat di Iot Hub. Cmdlet baru adalah:
    - 'Add-AzIotHubDevice'
    - 'Get-AzIotHubDevice'
    - 'Remove-AzIotHubDevice'
    - 'Set-AzIotHubDevice'

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki teks duplikat untuk Add-AzKeyVaultKey.md

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki deskripsi cmdlet Get-AzLog.
* Parameter baru yang disebut ActionGroupId ditambahkan ke perintah 'New-AzMetricAlertRuleV2'.
    - Pengguna dapat menyediakan ActionGroupId(string) atau ActionGorup(ActivityLogAlertActionGroup).

#### <a name="aznetwork"></a>Az.Network
* Menambahkan satu catatan parameter tambahan pada parameter '-EnableProxyProtocol' untuk cmdlet 'New-AzPrivateLinkService'.
* Memperbaiki contoh FilterData di Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Menambahkan contoh Pengambilan Paket untuk mengambil semua paket dalam dan luar di Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Mendukung Kebijakan Azure Firewall pada Firewall VNet
    - Tidak ada cmdlet baru yang ditambahkan. Melonggarkan pembatasan untuk kebijakan firewall pada firewall VNet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Dukungan untuk Restore-as-files pada SQL Database.

#### <a name="azresources"></a>Az.Resources
* Memfaktorkan ulang cmdlet penyebaran templat
    - Menambahkan cmdlet baru untuk mengelola penyebaran di grup manajemen: *-AzManagementGroupDeployment
    - Menambahkan cmdlet baru untuk mengelola penyebaran di cakupan penyewa: *-AzTenantDeployment
    - Memfaktorkan ulang cmdlet *-AzDeployment untuk bekerja secara khusus di cakupan langganan
    - Membuat alias *-AzSubscriptionDeployment untuk *-cmdlet AzDeployment
* Memperbaiki 'Update-AzADApplication' saat parameter 'AvailableToOtherTenants' tidak diatur
* Menghapus ApplicationObjectWithoutCredentialParameterSet untuk menghindari AmbiguousParameterSetException.
* Meregenerasi file bantuan

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk pemulihan titik waktu tertentu antar langganan di Instans Terkelola.
* Menambahkan dukungan untuk mengubah generasi perangkat keras Instans Terkelola Sql yang ada
* Memperbaiki contoh bantuan 'Update-AzSqlServerVulnerabilityAssessmentSetting': output parameter/properti - EmailAdmins

#### <a name="azsqlvirtualmachine"></a>Az.SqlVirtualMachine
* Menambahkan cmdlet untuk Pendengar Grup Ketersediaan

#### <a name="azstoragesync"></a>Az.StorageSync
* Memperbarui tataan karakter yang didukung di 'Invoke-AzStorageSyncCompatibilityCheck'.

## <a name="340---february-2020"></a>3.4.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama sebelumnya
* Az.CosmosDB versi awal 0.1.0 dirilis
* Dukungan Az.Network ConnectionMonitor V2 ditambahkan

#### <a name="azaccounts"></a>Az.Accounts
* Menonaktifkan penyimpanan otomatis konteks saat AzureRmContext.json tidak tersedia
* Memperbarui referensi ke Azure Powershell Common ke 1.3.5-preview

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Get-AzApiManagementApiSchema** Memperbaiki skema Open-Api yang terkait dengan API   https://github.com/Azure/azure-powershell/issues/10626
* **New-AzApiManagementProduct** _ dan _ *Set-AzApiManagementProduct**
  - Memperbaiki dokumentasi untuk https://github.com/Azure/azure-powershell/issues/10472
* **Set-AzApiManagementApi** Menambahkan contoh untuk menunjukkan cara memperbarui ServiceUrl menggunakan cmdlet

#### <a name="azcompute"></a>Az.Compute
* Membatasi jumlah status mesin virtual hingga 100 untuk menghindari pembatasan saat Get-AzVM -Status dilakukan tanpa nama mesin virtual.
* Menambahkan cmdlet Update-AzDiskEncryptionSet
* Menambahkan parameter EncryptionType dan DiskEncryptionSetId ke cmdlet berikut:
    - New-AzDiskUpdateConfig, New-AzSnapshotUpdateConfig
* Menambahkan parameter ColocationStatus ke cmdlet Get-AzProximityPlacementGroup.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.7.0

#### <a name="azdeploymentmanager"></a>Az.DeploymentManager
* Menambahkan operasi LIST untuk sumber daya
* Menambahkan kemampuan untuk melakukan operasi pada langkah-langkah Pemeriksaan Kesehatan

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki kesalahan dokumen New-AzHDInsightCluster.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan alias Nama ke atribut VaultName untuk membuat Remove-AzureKeyVault konsisten dengan New-AzureKeyVault.

#### <a name="aznetwork"></a>Az.Network
* Contoh baru ditambahkan ke Set-AzNetworkWatcherConfigFlowLog.md untuk menunjukkan skenario nonaktif Traffic Analitik Lalu Lintas.
* Menambahkan dukungan untuk menetapkan konfigurasi IP manajemen ke Azure Firewall - subnet khusus dan IP Publik yang akan digunakan firewall untuk lalu lintas manajemennya
    - Memperbarui cmdlet New-AzFirewall:
        - Menambahkan parameter -ManagementPublicIpAddress (tidak wajib) yang menerima objek Alamat IP Publik
        - Menambahkan metode SetManagementIpConfiguration pada objek firewall - memerlukan subnet dan alamat IP Publik sebagai input - nama subnet harus 'AzureFirewallManagementSubnet'
* Mengoreksi contoh Get-AzNetworkSecurityGroup untuk menampilkan contoh untuk NSG, bukan antarmuka jaringan.
* Memperbaiki kesalahan ketik dalam perintah New-AzVpnSite yang mencegah pelengkap id sumber daya menyelesaikan parameter.
* Menambahkan dukungan untuk Url Konfigurasi dalam Kumpulan Tindakan Aturan Penulisan Ulang di Application Gateway
    - Cmdlet baru ditambahkan:
        - New-AzApplicationGatewayRewriteRuleUrlConfiguration
    - Memperbarui cmdlet dengan parameter opsional - UrlConfiguration
        - New-AzApplicationGatewayRewriteRuleActionSet
* Menambahkan dukungan untuk sumber daya NetworkWatcher ConnectionMonitor versi 2

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Mendukung evaluasi kepatuhan sebelum menentukan sumber daya apa yang akan diremediasi
    - Menambahkan parameter '-ResourceDiscoverMode' ke Start-AzPolicyRemediation
* Menambahkan cmdlet Get-AzPolicyMetadata untuk mendapatkan sumber daya metadata kebijakan
* Memperbarui Get-AzPolicyState dan Get-AzPolicyStateSummary untuk API versi 2019-10-01

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk menghapus disk yang direplikasi.
* Azure Backup menambahkan dukungan untuk menambahkan tag saat membuat Vault Layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Menjadikan -Scope sebagai opsional di cmdlet *-AzPolicyAssignment dengan langganan default ke konteks
* Menambahkan contoh pembuatan ADServicePrincipal dengan kata sandi dan info masuk utama

#### <a name="azsql"></a>Az.Sql
Memperbaiki cmdlet New-AzSqlDatabaseSecondary untuk memeriksa keberadaan PartnerDatabaseName, bukan keberadaan DatabaseName.

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaturan Keytype Enkripsi Tabel/Antrean di Buat Akun Penyimpanan
    - New-AzStorageAccount
* Menampilkan RequestId saat StorageException tidak memiliki ExtendedErrorInformation
* Memperbaiki Contoh 6 cmdlet Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Az.Websites
* Set-AzWebapp dan Set-AzWebappSlot mendukung properti AlwaysOn, MinTls, dan FtpsState
* Memperbaiki masalah saat mengatur HttpsOnly bersama dengan mengubah AppservicePlan pada saat yang sama menggunakan Perintah Set-AzWebApp tunggal, sebelumnya mengatur ulang HttpsOnly ke nilai default

## <a name="330---january-2020"></a>3.3.0 - Januari 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAttestationServiceEndpointResourceId dan AzureAttestationServiceEndpointSuffix

#### <a name="azcdn"></a>Az.Cdn
* Menampilkan detail respons kesalahan di cmdlet New-AzCdnEndpoint

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki cmdlet Set-AzVMCustomScriptExtension untuk mesin virtual dengan disk OD terkelola yang tidak memiliki profil OS.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbaiki nama parameter yang digunakan oleh contoh New-AzContainerGroup

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Menambahkan cmdlet 'Get-AzDataBoxEdgeStorageContainer'
  - Mendapatkan Kontainer Penyimpanan Edge
* Menambahkan cmdlet 'New-AzDataBoxEdgeStorageContainer'
  - Membuat Kontainer Penyimpanan Edge baru
* Menambahkan cmdlet 'Remove-AzDataBoxEdgeStorageContainer'
  - Menghapus Kontainer Penyimpanan Edge
* Menambahkan cmdlet 'Invoke-AzDataBoxEdgeStorageContainer'
  - Memanggil tindakan untuk me-refresh data di Kontainer Penyimpanan Edge
* Menambahkan cmdlet 'Get-AzDataBoxEdgeStorageAccount'
  - Mendapatkan Akun Penyimpanan Edge
* Menambahkan cmdlet 'New-AzDataBoxEdgeStorageAccount'
  - Membuat Akun Penyimpanan Edge baru
* Menambahkan cmdlet 'Remove-AzDataBoxEdgeStorageAccount'
  - Menghapus Akun Penyimpanan Edge
* Memanggil cmdlet 'Invoke-AzDataBoxEdgeShare'
  - Memanggil tindakan untuk me-refresh data pada berbagi
* Menambahkan cmdlet 'Set-AzDataBoxEdgeStorageAccountCredential'
  - Mengatur info masuk akun penyimpanan az databoxedge

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan properti AutoUpdateETA, LatestVersion, PushedVersion, TaskQueueId, dan VersionStatus untuk cmd Get-AzDataFactoryV2IntegrationRuntime
* Memperbarui versi ADF .Net SDK ke 4.6.0
* Menambahkan parameter 'PublicIPs' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' guna mengaktifkan pembuatan Azure-SSIS IR dengan alamat IP publik statis.

#### <a name="azdevtestlabs"></a>Az.DevTestLabs
* Menghapus hyperlink rusak di Get-AzDtlAllowedVMSizesPolicy.md

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah 10634 : Memperbaiki referensi objek null untuk menghapus eventhubnamespace

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki kesalahan Invoke-AzHDInsightHiveJob.md.

#### <a name="azmachinelearning"></a>Az.MachineLearning
* Menghapus cmdlet di bawah ini karena MachineLearningCompute tidak tersedia lagi
  - Get-AzMlOpCluster
  - Get-AzMlOpClusterKey
  - New-AzMlOpCluster
  - Remove-AzMlOpCluster
  - Set-AzMlOpCluster
  - Test-AzMlOpClusterSystemServicesUpdateAvailability
  - Update-AzMlOpClusterSystemService

#### <a name="aznetwork"></a>Az.Network
* Meningkatkan dependensi Microsoft.Azure.Management.Sql dari 1.36-preview ke 1.37-preview

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery mengubah dukungan untuk mesin virtual disk terkelola yang dienkripsi saat tidak aktif dengan kunci yang dikelola pelanggan untuk penyedia Azure ke Azure.
* Azure Site Recovery mendukung untuk memasukkan enkripsi disk Set Id sebagai input opsional untuk mengaktifkan perlindungan Vmware ke Azure.
* Azure Site Recovery mendukung untuk memasukkan enkripsi disk Set Id sebagai input opsional di tingkat disk untuk mengaktifkan perlindungan Vmware ke Azure.
* Azure Site Recovery mendukung untuk memperbarui replikasi item yang dilindungi dengan set enkripsi disk Map for HyperV ke Azure.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki kesalahan dalam dokumen bantuan 'Remove-AzTag'.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki penilaian kerentanan dan mengatur fungsionalitas cmdlet dasar agar berfungsi pada master db untuk database azure dan membatasinya pada database sistem instans terkelola.
* Memperbaiki kesalahan saat membuat grup failover instans SQL Server

#### <a name="azsqlvirtualmachine"></a>Az.SqlVirtualMachine
* Menambahkan DR sebagai jenis Lisensi baru yang valid

#### <a name="azstorage"></a>Az.Storage
* Menambahkan pesan peringatan perubahan yang berisiko untuk perubahan Nilai DefaultAction dalam rilis mendatang
    - Update-AzStorageAccountNetworkRuleSet
* Mendukung Get waktu sinkronisasi terakhir akun Penyimpanan dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeGeoReplicationStats
    - Get-AzureRMStorageAccount

## <a name="320---december-2019"></a>3.2.0 - Desember 2019

### <a name="general"></a>Umum
* Memperbarui referensi di .psd1 guna menggunakan jalur relatif untuk semua modul

#### <a name="azaccounts"></a>Az.Accounts
* Mengatur UserAgent yang benar pada telemetri sisi klien untuk pratinjau Az 4.0
* Menampilkan pesan kesalahan yang ramah pengguna saat konteks null di pratinjau Az 4.0

#### <a name="azbatch"></a>Az.Batch
* Memperbaiki masalah [#10602](https://github.com/Azure/azure-powershell/issues/10602), ketika **New-AzBatchPool** tidak mengirim 'VirtualMachineConfiguration.ContainerConfiguration' atau 'VirtualMachineConfiguration.DataDisks' ke server dengan benar.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.5.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan dukungan pengecualian aturan terkelola WAF
* Menambahkan SocketAddr ke selesai otomatis

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Penanganan Pengecualian

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki nilai akses kesalahan yang berpotensi tidak diatur
* Manajemen Sertifikat Kriptografi Kurva Elips
    - Menambahkan dukungan untuk menentukan Kurva untuk Kebijakan Sertifikat

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan argumen opsional ke perintah Tambahkan Pengaturan Diagnostik. Argumen pengalihan yang, jika ada, menunjukkan bahwa ekspor ke Log Analytics harus ke skema tetap (alias khusus, jenis data)

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk IpGroups di Aplikasi AzureFirewall, Nat & Aturan Jaringan.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah ketika penyebaran templat gagal membaca parameter templat jika namanya bertentangan dengan beberapa nama parameter bawaan.
* Memperbarui cmdlet kebijakan untuk menggunakan api baru versi 2019-09-01 yang memperkenalkan dukungan pengelompokan dalam definisi set kebijakan.

#### <a name="azsql"></a>Az.Sql
* Meningkatkan pembuatan penyimpanan dalam pengaktifan otomatis Penilaian Kerentanan ke StorageV2

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan token SAS berbasis Blob/Identitas Kontainer dengan Konteks Penyimpanan berdasarkan autentikasi Oauth
    - New-AzStorageContainerSASToken
    - New-AzStorageBlobSASToken
* Mendukung pencabutan Kunci Delegasi Pengguna Akun Penyimpanan, sehingga semua token SAS Identitas dicabut
    - Revoke-AzStorageAccountUserDelegationKeys
* Meningkatkan ke Microsoft.Azure.Management.Storage 14.2.0, untuk mendukung API baru versi 2019-06-01.
* Dukungan QuotaGiB (Kuota Bersama di Gibibye) untuk nilai lebih dari 5120 di bidang Manajemen cmdlet Berbagi File dan menambahkan alias parameter 'Quota' ke parameter 'QuotaGiB'.
    - New-AzRmStorageShare
    - Update-AzRmStorageShare
* Menambahkan alias parameter 'QuotaGiB' ke parameter 'Quota'
    - Set-AzStorageShareQuota
* Memperbaiki masalah Set-AzStorageContainerAcl dapat menghapus Kebijakan Akses yang tersimpan
    - Set-AzStorageContainerAcl

## <a name="310---november-2019"></a>3.1.0 - November 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama sebelumnya
* Az.DataBoxEdge 1.0.0 dirilis
* Az.SqlVirtualMachine 1.0.0 dirilis

#### <a name="azcompute"></a>Az.Compute
* Fitur Pengaplikasian ulang mesin virtual
    - Menambahkan parameter Pengaplikasian ulang ke cmdlet Set-AzVM
* Fitur AutomaticRepairs Set Skala mesin virtual:
    - Menambahkan parameter EnableAutomaticRepair, AutomaticRepairGracePeriod, dan AutomaticRepairMaxInstanceRepairsPercent ke cmdlet berikut: New-AzVmssConfig Update-AzVmss
* Dukungan gambar galeri antar penyewa untuk New-AzVM
* Menambahkan 'Spot' ke pelengkap argumen parameter Prioritas di cmdlet New-AzVM, New-AzVMConfig, dan New-AzVmss
* Menambahkan parameter DiskIOPSReadWrite dan DiskMBpsReadWrite ke cmdlet Add-AzVmssDataDisk
* Mengubah parameter SourceImageId pada cmdlet New-AzGalleryImageVersion menjadi opsional
* Menambahkan parameter OSDiskImage dan DataDiskImage ke cmdlet New-AzGalleryImageVersion
* Menambahkan parameter HyperVGeneration ke cmdlet New-AzGalleryImageDefinition
* Menambahkan parameter SkipExtensionsOnOverprovisionedVMs ke cmdlet New-AzVmss, New-AzVmssConfig, dan Update-AzVmss

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Menambahkan cmdlet `Get-AzDataBoxEdgeOrder`
    - Mendapatkan Perintah
* Menambahkan cmdlet `New-AzDataBoxEdgeOrder`
    - Membuat Perintah baru
* Menambahkan cmdlet `Remove-AzDataBoxEdgeOrder`
    - Menghapus Perintah
* Perubahan pada cmdlet `New-AzDataBoxEdgeShare`
    - Sekarang membuat Berbagi Lokal
* Menambahkan cmdlet `Set-AzDataBoxEdgeRole`
    - Sekarang IotRole dapat dipetakan ke Berbagi
* Menambahkan cmdlet `Invoke-AzDataBoxEdgeDevice`
    - Memanggil pembaruan pemindaian, mengunduh pembaruan, memasang pembaruan pada perangkat
* Menambahkan cmdlet `Get-AzDataBoxEdgeTrigger`
    - Mendapatkan informasi tentang Pemicu
* Menambahkan cmdlet `New-AzDataBoxEdgeTrigger`
    - Membuat Pemicu baru
* Menambahkan cmdlet `Remove-AzDataBoxEdgeTrigger`
    - Menghapus Pemicu

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.4.0
* Menambahkan parameter 'ExpressCustomSetup' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan konfigurasi penyiapan dan komponen pihak ketiga tanpa skrip penyiapan khusus.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui dokumentasi Get-AzDataLakeStoreDeletedItem dan Restore-AzDataLakeStoreDeletedItem

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah 10301 : Memperbaiki format tanggal Token SAS

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan parameter MinimumTlsVersion ke Enable-AzFrontDoorCustomDomainHttps dan New-AzFrontDoorFrontendEndpointObject
* Menambahkan parameter HealthProbeMethod dan EnabledState ke New-AzFrontDoorHealthProbeSettingObject
* Menambahkan cmdlet baru guna membuat objek backendPoolsSettings untuk masuk ke pembuatan/pembaruan Front Door
    - New-AzFrontDoorBackendPoolsSettingObject

#### <a name="aznetwork"></a>Az.Network
* Mengubah contoh opsi FilterData 'Start-AzVirtualNetworkGatewayConnectionPacketCapture.md' dan 'Start-AzVirtualnetworkGatewayPacketCapture.md'.

#### <a name="azprivatedns"></a>Az.PrivateDns
* Memperbarui sdk .net PrivateDns ke versi 1.0.0

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery mendukung untuk memilih jenis disk saat mengaktifkan perlindungan.
* Perbaikan bug Azure Site Recovery untuk pengeditan tindakan rencana pemulihan.
* Azure Backup SQL Memulihkan dukungan untuk menerima MB aliran file.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'MinimumTlsVersion' di cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'. Selain itu, menambahkan 'MinimumTlsVersion' dalam output cmdlet 'Get-AzRedisCache'.
* Menambahkan validasi pada parameter '-Size' untuk cmdlet 'Set-AzRedisCache' dan 'New-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
- Memperbarui cmdlet kebijakan untuk menggunakan api baru versi 2019-06-01 yang memiliki properti EnforcementMode baru dalam penetapan kebijakan.
- Memperbarui contoh bantuan definisi kebijakan pembuatan
- Memperbaiki bug Remove-AZADServicePrincipal -ServicePrincipalName, yang mengeluarkan referensi null saat nama prinsipal layanan tidak ditemukan.
- Memperbaiki bug New-AZADServicePrincipal, yang mengeluarkan referensi null saat penyewa tidak memiliki langganan apa pun.
- Mengubah New-AzAdServicePrincipal untuk menambahkan info masuk hanya ke aplikasi terkait.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk database ReadReplicaCount.
* Memperbaiki Set-AzSqlDatabase saat redundansi zona tidak diatur

## <a name="300---november-2019"></a>3.0.0 - November 2019
### <a name="general"></a>Umum
* Az.PrivateDns 1.0.0 dirilis

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan pesan penghentian untuk alias 'Resolve-Error'.

#### <a name="azadvisor"></a>Az.Advisor
* Menambahkan kategori baru 'Operational Excellence' ke cmdlet Get-AzAdvisorRecommendation.

#### <a name="azbatch"></a>Az.Batch
* Mengganti nama `CoreQuota`di `BatchAccountContext` menjadi `DedicatedCoreQuota`. Ada juga `LowPriorityCoreQuota` baru.
  - Hal ini berdampak pada **Get-AzBatchAccount**.
* **New-AzBatchTask** parameter `-ResourceFile` sekarang mengambil koleksi objek `PSResourceFile`, yang dapat dibangun menggunakan cmdlet **New-AzBatchResourceFile** baru.
* Cmdlet **New-AzBatchResourceFile** baru untuk membantu membuat objek `PSResourceFile`. Objek ini dapat dipasok ke **New-AzBatchTask** pada parameter `-ResourceFile`.
  - Hal ini mendukung dua jenis file sumber daya baru selain cara `HttpUrl` yang ada:
    - File sumber daya berbasis `AutoStorageContainerName` mengunduh seluruh kontainer penyimpanan otomatis ke node Batch.
    - File sumber daya berbasis `StorageContainerUrl` mengunduh kontainer yang ditentukan dalam URL ke node Batch.
* Menghapus properti `ApplicationPackages``PSApplication` dimunculkan oleh **Get-AzBatchApplication**.
  - Paket spesifik di dalam aplikasi sekarang dapat diambil menggunakan **Get-AzBatchApplicationPackage**. Misalnya: `Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication`.
* Mengganti nama`ApplicationId` menjadi `ApplicationName`di **Get-AzBatchApplicationPackage**, **New-AzBatchApplicationPackage**, **Remove-AzBatchApplicationPackage**, **Get-AzBatchApplication**, **New-AzBatchApplication**, **Remove-AzBatchApplication**, dan **Set-AzBatchApplication**.
  - `ApplicationId` Sekarang adalah alias `ApplicationName`.
* Menambahkan properti `PSWindowsUserConfiguration` baru ke `PSUserAccount`.
* Mengganti nama `Version` menjadi `Name` di `PSApplicationPackage`.
* Mengganti nama `BlobSource` menjadi `HttpUrl` di `PSResourceFile`.
* Menghapus properti `OSDisk` dari `PSVirtualMachineConfiguration`.
* Menghapus **Set-AzBatchPoolOSVersion**. Operasi ini tidak lagi didukung.
* Menghapus `TargetOSVersion` dari `PSCloudServiceConfiguration`.
* Mengganti nama `CurrentOSVersion` menjadi `OSVersion` di `PSCloudServiceConfiguration`.
* Menghapus `DataEgressGiB` dan `DataIngressGiB` dari `PSPoolUsageMetrics`.
* Menghapus **Get-AzBatchNodeAgentSku** dan menggantinya dengan  **Get-AzBatchSupportedImage**.
  - **Get-AzBatchSupportedImage** memunculkan data yang sama dengan **Get-AzBatchNodeAgentSku** tetapi dalam format yang lebih ramah.
  - Gambar baru yang tidak diverifikasi juga sekarang dimunculkan. Informasi tambahan tentang `Capabilities` dan `BatchSupportEndOfLife` untuk setiap gambar juga disertakan.
* Menambahkan kemampuan untuk memasang sistem file jarak jauh pada setiap node kumpulan melalui parameter `MountConfiguration` baru **New-AzBatchPool**.
* Sekarang mendukung aturan keamanan jaringan yang memblokir akses jaringan ke kumpulan berdasarkan port sumber lalu lintas. Hal ini dilakukan melalui properti `SourcePortRanges` di `PSNetworkSecurityGroupRule`.
* Saat menjalankan kontainer, Batch sekarang mendukung pelaksanaan tugas di direktori kerja kontainer atau di direktori kerja tugas Batch. Hal ini dikendalikan oleh properti `WorkingDirectory` di `PSTaskContainerSettings`.
* Menambahkan kemampuan untuk menentukan koleksi IP publik di `PSNetworkConfiguration` melalui properti `PublicIPs` baru. Hal ini menjamin node di Kumpulan akan memiliki IP dari daftar IP yang disediakan pengguna.
* Ketika tidak ditentukan, nilai default `WaitForSuccess` di `PSSTartTask` sekarang adalah `$True` (sebelumnya `$False`).
* Ketika tidak ditentukan, nilai default `Scope` di `PSAutoUserSpecification` sekarang adalah `Pool` (sebelumnya `Task` di Windows dan `Pool` di Linux).

#### <a name="azcdn"></a>Az.Cdn
* Memperkenalkan UrlRewriteAction dan CacheKeyQueryStringAction ke RulesEngine.
* Memperbaiki beberapa bug seperti Input 'Selector' yang hilang di cmdlet New-AzDeliveryRuleCondition.

#### <a name="azcompute"></a>Az.Compute
* Fitur Set Enkripsi Disk
    - Cmdlet baru: New-AzDiskEncryptionSetConfig New-AzDiskEncryptionSet Get-AzDiskEncryptionSet Remove-AzDiskEncryptionSet
    - Parameter DiskEncryptionSetId ditambahkan ke cmdlet berikut: Set-AzImageOSDisk Set-AzVMOSDisk Set-AzVmssStorageProfile Add-AzImageDataDisk New-AzVMDataDisk Set-AzVMDataDisk Add-AzVMDataDisk Add-AzVmssDataDisk Add-AzVmssVMDataDisk
    - Parameter DiskEncryptionSetId dan EncryptionType ditambahkan ke cmdlet berikut:   New-AzDiskConfig   New-AzSnapshotConfig
* Menambahkan parameter PublicIPAddressVersion ke New-AzVmssIPConfig
* Memindahkan FileUris ekstensi skrip kustom dari pengaturan publik ke pengaturan yang dilindungi
* Menambahkan ScaleInPolicy ke cmdlet New-AzVmss, New-AzVmssConfig, dan Update-AzVmss
* Perubahan mencolok
    - Parameter UploadSizeInBytes digunakan, bukan DiskSizeGB, untuk New-AzDiskConfig saat CreateOption adalah Upload
    - PublishingProfile.Source.ManagedImage.Id diganti dengan StorageProfile.Source.Id di objek GalleryImageVersion

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.3.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui versi SDK ADLS (https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-123-alpha), menghadirkan perbaikan berikut
* Menghindari pembuangan pengecualian saat tidak dapat melakukan deserialisasi creationtime dari entri tempat sampah atau direktori.
* Mengekspos pengaturan per batas waktu permintaan di adlsclient
* Memperbaiki masalah melewati syncflag asli untuk pemulihan badoffset
* Memperbaiki EnumerateDirectory untuk mengambil token kelanjutan setelah respons diperiksa
* Memperbaiki Bug Concat

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbaiki kesalahan ketik lain-lain di seluruh modul

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki bug yang mengakibatkan pengguna mendapatkan kesalahan 'Bukan string Base-64 yang valid' saat menggunakan Get-AzHDInsightCluster untuk mendapatkan kluster dengan penyimpanan ADLSGen1.
* Menambahkan parameter bernama 'ApplicationId' ke tiga cmdlet Add-AzHDInsightClusterIdentity, New-AzHDInsightClusterConfig dan New-AzHDInsightCluster sehingga pelanggan dapat memberikan id aplikasi perwakilan layanan untuk mengakses Azure Data Lake.
* Mengubah Microsoft.Azure.Management.HDInsight dari 2.1.0 menjadi 5.1.0
* Menghapus lima cmdlet:
    - Get-AzHDInsightOMS
    - Enable-AzHDInsightOMS
    - Disable-AzHDInsightOMS
    - Grant-AzHDInsightRdpServicesAccess
    - Revoke-AzHDInsightRdpServicesAccess
* Menambahkan tiga cmdlet:
    - Get-AzHDInsightMonitoring menggantikan Get-AzHDInsightOMS.
    - Enable-AzHDInsightMonitoring menggantikan Enable-AzHDInsightOMS.
    - Disable-AzHDInsightMonitoring untuk menggantikan Disable-AzHDInsightOMS.
* Memperbaiki cmdlet Get-AzHDInsightProperties untuk mendukung mendapatkan informasi kemampuan dari lokasi tertentu.
* Menghapus set parameter ('Spark1', 'Spark2') dari Add-AzHDInsightConfigValue.
* Menambahkan contoh ke dokumen bantuan cmdlet Add-AzHDInsightSecurityProfile.
* Mengubah jenis output dari cmdlet berikut:
*  - Mengubah jenis output Get-AzHDInsightProperties dari CapabilitiesResponse menjadi AzureHDInsightCapabilities.
*  - Mengubah jenis output Remove-AzHDInsightCluster dari ClusterGetResponse menjadi bool.
*  - Mengubah jenis output Set-AzHDInsightGatewaySettings HttpConnectivitySettings menjadi GatewaySettings.
* Menambahkan beberapa kasus uji skenario.
* Menghapus beberapa alias: 'Add-AzHDInsightConfigValues', 'Get-AzHDInsightProperties'.

#### <a name="aziothub"></a>Az.IotHub
* Perubahan yang berisiko:
    - Cmdlet 'Add-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Parameter '__AllParameterSets' yang diatur untuk cmdlet 'Add-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Get-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Parameter '__AllParameterSets' yang diatur untuk cmdlet 'Get-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Properti 'OperationsMonitoringProperties' dari jenis 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubProperties' telah dihapus.
    - Properti 'OperationsMonitoringProperties' dari jenis 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubInputProperties' telah dihapus.
    - Cmdlet 'New-AzIotHubExportDevice' tidak lagi mendukung alias 'New-AzIotHubExportDevices'.
    - Cmdlet 'New-AzIotHubImportDevice' tidak lagi mendukung alias 'New-AzIotHubImportDevices'.
    - Cmdlet 'Remove-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Parameter '__AllParameterSets' yang diatur untuk cmdlet 'Remove-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Set-AzIotHub' tidak lagi mendukung parameter 'OperationsMonitoringProperties' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Parameter 'UpdateOperationsMonitoringProperties' yang diatur untuk cmdlet 'Set-AzIotHub' telah dihapus.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery mendukung untuk mengonfigurasi sumber daya jaringan seperti NSG, IP publik, dan load balancer internal untuk Azure ke Azure.
* Azure Site Recovery mendukung untuk menulis ke disk terkelola untuk vMWare ke Azure.
* Azure Site Recovery mendukung pengurangan NIC untuk vMWare ke Azure.
* Azure Site Recovery mendukung jaringan yang dipercepat untuk Azure ke Azure.
* Azure Site Recovery mendukung agen pembaruan otomatis untuk Azure ke Azure.
* Azure Site Recovery mendukung SSD Standar untuk Azure ke Azure.
* Azure Site Recovery mendukung Azure Disk Encryption dua sandi untuk Azure ke Azure.
* Azure Site Recovery Mendukung untuk melindungi disk yang baru ditambahkan untuk Azure ke Azure.
* Menambahkan fitur SoftDelete untuk mesin virtual dan menambahkan pengujian untuk softdelete

#### <a name="azresources"></a>Az.Resources
* Memperbarui perakitan dependensi Microsoft.Extensions.Caching.Memory dari 1.1.1 hingga 2.2

#### <a name="aznetwork"></a>Az.Network
* Mengubah semua cmdlet untuk PrivateEndpointConnection untuk mendukung penyedia layanan generik.
    - Memperbarui cmdlet:
        - Approve-AzPrivateEndpointConnection
        - Deny-AzPrivateEndpointConnection
        - Get-AzPrivateEndpointConnection
        - Remove-AzPrivateEndpointConnection
        - Set-AzPrivateEndpointConnection
* Menambahkan cmdlet baru untuk PrivateLinkResource dan juga mendukung penyedia layanan generik.
    - Cmdlet baru:
        - Get-AzPrivateLinkResource
* Menambahkan bidang dan parameter baru untuk fitur Proxy Protocol V2.
    - Menambahkan properti EnableProxyProtocol di PrivateLinkService
    - Menambahkan properti LinkIdentifier di PrivateEndpointConnection
    - Memperbarui New-AzPrivateLinkService untuk menambahkan parameter opsional baru EnableProxyProtocol.
* Memperbaiki deskripsi parameter yang salah dalam dokumentasi referensi 'New-AzApplicationGatewaySku'
* Cmdlet baru untuk mendukung kebijakan firewall azure
* Menambahkan dukungan untuk RouteTables sumber daya turunan virtualhub
    - Cmdlet baru ditambahkan:
        - Add-AzVirtualHubRoute
        - Add-AzVirtualHubRouteTable
        - Get-AzVirtualHubRouteTable
        - Remove-AzVirtualHubRouteTable
        - Set-AzVirtualHub
* Menambahkan dukungan untuk properti baru Sku dari VirtualHub dan VirtualWANType dari VirtualWan
    - Memperbarui cmdlet dengan parameter opsional:
        - New-AzVirtualHub : menambahkan parameter Sku
        - Update-AzVirtualHub : menambahkan parameter Sku
        - New-AzVirtualWan : menambahkan parameter VirtualWANType
        - Update-AzVirtualWan : menambahkan parameter VirtualWANType
* Menambahkan dukungan untuk properti EnableInternetSecurity untuk HubVnetConnection, VpnConnection, dan ExpressRouteConnection
    - Cmdlet baru ditambahkan:
        - Update-AzureRmVirtualHubVnetConnection
    - Memperbarui cmdlet dengan parameter opsional:
        - New-AzureRmVirtualHubVnetConnection : menambahkan parameter EnableInternetSecurity
        - New-AzureRmVpnConnection : menambahkan parameter EnableInternetSecurity
        - Update-AzureRmVpnConnection : menambahkan parameter EnableInternetSecurity
        - New-AzureRmExpressRouteConnection : menambahkan parameter EnableInternetSecurity
        - Set-AzureRmExpressRouteConnection : menambahkan parameter EnableInternetSecurity
* Menambahkan dukungan untuk Mengonfigurasi Kebijakan TopLevel WebApplicationFirewall
    - Cmdlet baru ditambahkan:
        - New-AzApplicationGatewayFirewallPolicySetting
        - New-AzApplicationGatewayFirewallPolicyExclusion
        - New-AzApplicationGatewayFirewallPolicyManagedRuleGroupOverride
        - New-AzApplicationGatewayFirewallPolicyManagedRuleOverride
        - New-AzApplicationGatewayFirewallPolicyManagedRule
        - New-AzApplicationGatewayFirewallPolicyManagedRuleSet
    - Memperbarui cmdlet dengan parameter opsional:
        - New-AzApplicationGatewayFirewallPolicy : menambahkan parameter PolicySetting, ManagedRule
* Menambahkan dukungan untuk operator Geo-Match di CustomRule
    - Menambahkan GeoMatch ke operator di FirewallCondition
* Menambahkan dukungan untuk kebijakan Firewall perListener dan perSite
    - Memperbarui cmdlet dengan parameter opsional:
        - New-AzApplicationGatewayHttpListener : menambahkan parameter FirewallPolicy, FirewallPolicyId
        - New-AzApplicationGatewayPathRuleConfig : menambahkan parameter FirewallPolicy, FirewallPolicyId
* Memperbaiki subnet yang diperlukan dengan nama AzureBastionSubnet di 'PSBastion' tidak peka huruf besar kecil
* Dukungan untuk FQDN Tujuan dalam Aturan Jaringan dan FQDN yang Diterjemahkan dalam Aturan NAT untuk Azure Firewall
* Menambahkan dukungan untuk RouteTables sumber daya tingkat atas dari IpGroup
    - Cmdlet baru ditambahkan:
        - Baru-AzIpGroup
        - Remove-AzIpGroup
        - Dapatkan-AzIpGroup
        - Atur-AzIpGroup

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menghapus cmdlet Add-AzServiceFabricApplicationCertificate karena skenario ini dicakup oleh Add-AzVmssSecret.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk memulihkan database yang dihilangkan pada Instans Terkelola.
* Dihentikan dari kode cmdlet audit lama.
* Menghapus alias yang tidak digunakan lagi:
* Get-AzSqlDatabaseIndexRecommendations (gunakan Get-AzSqlDatabaseIndexRecommendation sebagai gantinya)
* Get-AzSqlDatabaseRestorePoints (gunakan Get-AzSqlDatabaseRestorePoint sebagai gantinya)
* Menghapus cmdlet Get-AzSqlDatabaseSecureConnectionPolicy
* Menghapus alias untuk Penilaian Kerentanan Pengaturan cmdlet yang tidak digunakan lagi
* Cmdlet untuk Menghentikan Pengaturan Deteksi Ancaman Tingkat Lanjut
* Menambahkan cmdlet ke Nonaktifkan dan aktifkan rekomendasi sensitivitas pada kolom dalam database.

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaktifan berbagi File Besar saat membuat atau memperbarui akun Penyimpanan
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Saat close/get handel File, melewati pemeriksaan jalur input yang merupakan Direktori file atau File, untuk menghindari kegagalan dengan objek di status DeletePending
    -  Get-AzStorageFileHandle
    -  Close-AzStorageFileHandle

## <a name="280---october-2019"></a>2.8.0 - Oktober 2019
### <a name="general"></a>Umum
* Rilis Az.HealthcareApis 1.0.0

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui telemetri dan penulisan ulang url untuk modul yang dihasilkan, memperbaiki pengujian unit windows.

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Set-AzApiManagementApi** - Menambahkan dukungan untuk Memperbarui Api ke ApiVersionSet
    - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/10068

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki cmdlet New-AzureAutomationSoftwareUpdateConfiguration untuk parameter pengaturan reboot Linux.

#### <a name="azbatch"></a>Az.Batch
* **Get-AzBatchNodeAgentSku** tidak digunakan lagi dan akan digantikan oleh **Get-AzBatchSupportImage** di versi 2.0.0.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter Priority, EvictionPolicy, dan MaxPrice ke cmdlet New-AzVM dan New-AzVmss
* Memperbaiki pesan peringatan dan dokumen bantuan untuk cmdlet Add-AzVMAdditionalUnattendContent dan Add-AzVMSshPublicKey
* Memperbaiki pengecualian -skipVmBackup untuk mesin virtual Linux dengan disk terkelola untuk Set-AzVMDiskEncryptionExtension.
* Memperbaiki bug dalam pengaturan enkripsi pembaruan di Set-AzVMDiskEncryptionExtension, skenario dua sandi.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan perintah CRUD untuk aliran data ADF V2: Set-AzDataFactoryV2DataFlow, Remove-AzDataFactoryV2DataFlow, dan Get-AzDataFactoryV2DataFlow.
* Menambahkan perintah tindakan untuk debug Sesi aliran data ADF V2: Start-AzDataFactoryV2DataFlowDebugSession, Get-AzDataFactoryV2DataFlowDebugSession, Add-AzDataFactoryV2DataFlowDebugSessionPackage, Invoke-AzDataFactoryV2DataFlowDebugSessionCommand dan Stop-AzDataFactoryV2DataFlowDebugSession.
* Memperbarui versi ADF .Net SDK ke 4.2.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki validasi akun sehingga akun dengan '-' dapat diteruskan tanpa domain

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Memperbarui versi powershell ke 1.0.0
* Memperbarui versi SDK ke 1.0.2
* Pembaruan dalam pengujian untuk merujuk ke versi SDK baru
* Memperbarui struktur output dari berlapis menjadi rata.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan sumber perutean baru: DigitalTwinChangeEvents
* Perbaikan bug kecil: Get-AzIothub tidak memunculkan subscriptionId

#### <a name="azmonitor"></a>Az.Monitor
* Penerima grup tindakan baru ditambahkan untuk grup tindakan   -ItsmReceiver   -VoiceReceiver   -ArmRoleReceiver   -AzureFunctionReceiver   -LogicAppReceiver   -AutomationRunbookReceiver   -AzureAppPushReceiver
* Menggunakan skema peringatan umum yang diaktifkan untuk penerima. Hal ini tidak berlaku untuk SMS, pendorongan Aplikasi Azure, ITSM, dan penerima Voice
* Webhook sekarang mendukung autentikasi direktori aktif Azure .

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru Get-AzAvailableServiceAlias yang dapat dipanggil get alias yang dapat digunakan untuk Kebijakan Titik Akhir Layanan.
* Menambahkan dukungan untuk menambahkan pemilih lalu lintas ke Koneksi Gateway Virtual Network
    - Cmdlet baru ditambahkan:
        - New-AzureRmTrafficSelectorPolicy
    - Memperbarui cmdlet dengan parameter opsional -TrafficSelectorPolicies   -New-AzureRmVirtualNetworkGatewayConnection   -Set-AzureRmVirtualNetworkGatewayConnection
* Menambahkan dukungan untuk protokol ESP dan AH dalam konfigurasi aturan keamanan jaringan
    - Memperbarui cmdlet:
        - Tambahkan-AzNetworkSecurityRuleConfig
        - New-AzNetworkSecurityRuleConfig
        - Set-AzNetworkSecurityRuleConfig
* Meningkatkan penanganan pengecualian di cmdlet Cortex
* Generasi Baru dan SKU untuk VirtualNetworkGateways
  - Memperkenalkan Generasi baru untuk VirtualNetworkGateways.
  - Memperkenalkan SKU throughput tinggi baru untuk VirtualNetworkGateways.

#### <a name="azrediscache"></a>Az.RedisCache
* Memperbarui dokumentasi referensi 'Set-AzRedisCache' untuk menyertakan nilai yang hilang untuk parameter '-Size'

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk mengatur Administrator Active Directory pada Instans Terkelola

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan Pustaka Klien Penyimpanan ke 11.1.0
* Mencantumkan kontainer dengan API bidang Manajemen, akan mencantumkan dengan NextPageLink
    -  Get-AzRmStorageContainer
* Mencantumkan akun Penyimpanan dari langganan, akan mencantumkan dengan NextPageLink
    -  Dapatkan-AkunPenyimpananAz

#### <a name="azstoragesync"></a>Az.StorageSync
* Memperbaiki Masalah 9810 di Reset-AzStorageSyncServerCertificate.

#### <a name="azwebsites"></a>Az.Websites
* Set-AzWebApp memperbarui ASP aplikasi gagal

## <a name="270---september-2019"></a>2.7.0 - September 2019
#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbarui deskripsi parameter '-Format' dalam dokumentasi referensi 'Set-AzApiManagementPolicy'
* Menghapus referensi cmdlet 'Update-AzApiManagementDeployment' yang tidak digunakan lagi dari dokumentasi referensi. Menggunakan 'Set-AzApiManagement' sebagai gantinya.

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan ketik contoh dalam dokumentasi referensi untuk 'Register-AzAutomationDscNode'
* Menambahkan klarifikasi tentang pembatasan OS ke Register-AzAutomationDSCNode
* Memperbaiki pengecualian referensi Null cmdlet Start-AzAutomationRunbook untuk opsi -Wait.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter UploadSizeInBytes tp New-AzDiskConfig
* Menambahkan parameter Tambahan ke New-AzSnapshotConfig
* Menambahkan fitur mesin virtual prioritas rendah:
    - Parameter MaxPrice, EvictionPolicy, dan Priority ditambahkan ke New-AzVMConfig.
    - Parameter MaxPrice ditambahkan ke cmdlet New-AzVmssConfig, Update-AzVM, dan Update-AzVmss.
* Memperbaiki masalah referensi mesin virtual untuk cmdlet Get-AzAvailabilitySet saat mencantumkan semua set ketersediaan dalam langganan.
* Memperbaiki pengecualian null untuk Get-AzRemoteDesktopFile.
* Memperbaiki metode Pencarian VHD untuk posisi end-relative.
* Memperbaiki masalah UltraSSD untuk New-AzVM dan Update-AzVM.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan 3 perintah baru untuk ADF V2 - Add-AzDataFactoryV2TriggerSubscription, Remove-AzDataFactoryV2TriggerSubscription, and Get-AzDataFactoryV2TriggerSubscriptionStatus
* Memperbarui versi ADF .Net SDK ke 4.1.3

#### <a name="azhdinsight"></a>Az.HDInsight
* Memanggil perubahan yang berisiko

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk memanggil failover untuk IotHub ke wilayah pemulihan bencana yang dipasangkan secara geografis.
* Menambahkan dukungan untuk mengelola pengayaan pesan untuk IotHub. Cmdlet baru adalah:
    - Add-AzIotHubMessageEnrichment
    - Get-AzIotHubMessageEnrichment
    - Remove-AzIotHubMessageEnrichment
    - Set-AzIotHubMessageEnrichment

#### <a name="azmonitor"></a>Az.Monitor
* Menunjuk ke SDK Monitor terbaru, yaitu 0.24.1-preview
   - Menambahkan perubahan yang tidak berisiko pada cmdlet Metrik, yaitu enumerasi Unit mendukung beberapa nilai baru. Ini adalah cmdlet hanya baca, jadi tidak akan ada perubahan dalam input cmdlet.
   - Permintaan **ActionGroups** versi api sekarang **2019-06-01**, sebelumnya **2018-03-01**. Tes skenario telah diperbarui untuk mengakomodasi perubahan ini.
   - Konstruktor untuk kelas **EmailReceiver** dan **WebhookReceiver** menambahkan satu argumen wajib baru, yaitu nilai Boolean yang disebut **useCommonAlertSchema**. Saat ini, nilainya ditetapkan ke **false** untuk menyembunyikan perubahan yang berisiko ini dari cmdlet. **CATATAN**: perubahan ini bersifat sementara yang harus divalidasi oleh tim Peringatan.
   - Urutan argumen untuk konstruktor **Sumber** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua tes unit untuk diperbaiki: keduanya dikompilasi, tetapi gagal lulus uji.
   - Urutan argumen untuk konstruktor **AlertingAction** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua tes unit untuk diperbaiki: keduanya dikompilasi, tetapi gagal lulus uji.
* Mendukung kriteria Ambang Dinamis untuk peringatan metrik V2
    - New-AzMetricAlertRuleV2Criteria: sekarang juga menciptakan kriteria ambang batas dinamis
    - Add-AzMetricAlertRuleV2: sekarang juga menerima kriteria ambang dinamis
* Peningkatan cmdlet Aturan Kueri Terjadwal (SQR)
 - Cmdlets akan menerima paramater 'Location' dalam kedua format, baik lokasi (misalnya eastus) atau nama tampilan lokasi (misalnya US Timur)
 - Mengilustrasikan parameter 'Enabled' dalam file bantuan dengan benar
 - Menambahkan contoh untuk parameter opsional 'ActionGroup'
 - Meningkatkan file bantuan secara keseluruhan
* Memperbaiki bug dalam menentukan jenis cakupan untuk 'Set-AzActionRule'

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki contoh yang salah dalam dokumentasi referensi 'New-AzApplicationGateway'
* Menambahkan catatan dalam dokumentasi referensi 'Get-AzNetworkWatcherPacketCapture' terkait pengambilan semua properti untuk pengambilan paket
* Memperbaiki contoh dalam dokumentasi referensi 'Test-AzNetworkWatcherIPFlow' untuk menghitung NIC dengan benar
* Meningkatkan penguraian pengecualian cloud untuk menampilkan detail tambahan jika ada
* Meningkatkan penguraian pengecualian cloud untuk menangani jenis pengecualian SDK tambahan
* Memperbaiki pemetaan model Aturan Keamanan yang salah
* Menambahkan properti ke antarmuka jaringan untuk fitur ip privat
    - Menambahkan properti 'PrivateEndpoint' sebagai jenis PSResourceId ke PSNetworkInterface
    - Menambahkan properti 'PrivateLinkConnectionProperties' sebagai jenis PSIpConfigurationConnectivityInformation ke PSNetworkInterfaceIPConfiguration
    - Menambahkan kelas model baru PSIpConfigurationConnectivityInformation
* Menambahkan ApplicationRuleProtocolType 'mssql' baru untuk sumber daya Azure Firewall
* Dukungan MultiLink di Virtual WAN
    - Cmdlet baru
        - New-AzVpnSiteLink
        - New-AzVpnSiteLinkConnection
    - Memperbarui cmdlet:
        - New-VpnSite
        - Update-VpnSite
        - New-VpnConnection
        - Update-VpnConnection
* Memperbaiki dokumen pada beberapa contoh PowerShell untuk menggunakan cmdlet Az, bukan cmdlet AzureRM

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbarui Objek AzureVMpolicy dengan Atribut ProtectedItemsCount
* Menambahkan Tes untuk kebijakan mesin virtual dan Pemulihan Akun Penyimpanan Asli

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug ketika New-AzRoleAssignment tidak dapat dipanggil tanpa Cakupan parameter.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki kesalahan ketik dalam contoh untuk dokumentasi referensi 'Update-AzServiceFabricReliability'
* Menambahkan cmdlet baru untuk mengelola aplikasi dan layanan:
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
* Meningkatkan SDK Service Fabric ke versi 1.2.0 yang menggunakan penyedia sumber daya service fabric versi api 2019-03-01.

#### <a name="azsignalr"></a>Az.SignalR
* Menambahkan Pembaruan, Mulai Ulang, CheckNameAvailability, Cmdlet GetUsage

#### <a name="azsql"></a>Az.Sql
* Memperbarui contoh dalam dokumentasi referensi untuk 'Get-AzSqlElasticPool'
* Menambahkan contoh vCore untuk membuat kumpulan elastis (New-AzSqlElasticPool).
* Menghapus validasi EmailAddresses dan memeriksa bahwa EmailAdmins tidak salah jika EmailAddresses kosong di Set-AzSqlServerAdvancedThreatProtectionPolicy dan Set-AzSqlDatabaseAdvancedThreatProtectionPolicy
* Mengaktifkan penghapusan pengaturan audit server/database saat beberapa pengaturan diagnostik yang mengaktifkan kategori audit ada.
* Memperbaiki validasi alamat email di beberapa cmdlet Penilaian Kerentanan Sql (Update-AzSqlDatabaseVulnerabilityAssessmentSetting, Update-AzSqlServerVulnerabilityAssessmentSetting, Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting dan Update-AzSqlInstanceVulnerabilityAssessmentSetting).

#### <a name="azstorage"></a>Az.Storage
* Memperbarui contoh dalam dokumentasi referensi untuk 'Get-AzStorageAccountKey'
* Di pengunggahan/Pengunduhan File Azure, didukung untuk mempertahankan properti File SMB sumber (Atribut File, Waktu Pembuatan File, Waktu Penulisan File Terakhir) di file tujuan
    -  Set-AzStorageFileContent
    -  Get-AzStorageFileContent
* Memperbaiki pengunggahan blob blok dengan properti/metadate gagal pada ImmutabilityPolicy yang diaktifkan kontainer.
    -  Set-AzStorageBlobContent
* Mendukung pengelolaan berbagi File Azure dengan API bidang Manajemen
    -  New-AzRmStorageShare
    -  Get-AzRmStorageShare
    -  Update-AzRmStorageShare
    -  Remove-AzRmStorageShare

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki masalah ketika Tag aplikasi web dihapus saat memigrasikan Aplikasi ke ASPwhere baru Tag aplikasi web dihapus saat memigrasikan Aplikasi ke ASP baru
* Memperbaiki Publish-AzureWebapp untuk bekerja di Linux dan windows
* Memperbarui contoh dalam dokumentasi referensi 'Get-AzWebAppPublishingProfile'

## <a name="260---august-2019"></a>2.6.0 - Agustus 2019
#### <a name="general"></a>Umum
* Memperbaiki kesalahan ketik lain-lain di berbagai modul

#### <a name="azaccounts"></a>Az.Accounts
* Mendukung MSI yang ditetapkan pengguna di Autentikasi Azure Functions (#9479)

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah dengan output untuk 'Get-AzAks'
    * Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/9847

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/9351
    - Memperbarui versi nuget .net, yang tidak memberlakukan pembatasan pada productId, apiId, groupId, dan userId
* **Get-AzApiManagementProduct** - Menambahkan dukungan untuk mengkueri produk menggunakan Api.
  https://github.com/Azure/azure-powershell/issues/9482
* **New-AzApiManagementApiRevision** - Memperbaiki masalah ketika ApiRevisionDescription tidak diatur saat membuat revisi api baru https://github.com/Azure/azure-powershell/issues/9752
* Memperbaiki kesalahan ketik dalam model 'PsApiManagementOAuth2AuthrozationServer' menjadi 'PsApiManagementOAuth2AuthorizationServer'

#### <a name="azbatch"></a>Az.Batch
* Memperbaiki kesalahan ketik dalam pesan bantuan dan dokumentasi untuk mengkapitalisasi Windows

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki kesalahan ketik di CDN pembantu konversi modul

#### <a name="azcompute"></a>Az.Compute
* Menambahkan VmssId ke cmdlet New-AzVMConfig
* Menambahkan parameter TerminateScheduledEvents dan TerminateScheduledEventNotBeforeTimeoutInMinutes ke New-AzVmssConfig dan Update-AzVmss
* Menambahkan properti HyperVGeneration ke objek gambar mesin virtual
* Menambahkan fitur Host dan HostGroup
    - Cmdlet baru:   New-AzHostGroup   New-AzHost   Get-AzHostGroup   Get-AzHost   Remove-AzHostGroup   Remove-AzHost
    - Parameter HostId ditambahkan ke New-AzVMConfig dan New-AzVM
* Memperbarui contoh dalam dokumentasi 'Invoke-AzVMRunCommand' untuk menggunakan nama parameter yang benar
* Memperbarui deskripsi '-VolumeType' dalam dokumentasi referensi 'Set-AzVMDiskEncryptionExtension' dan 'Set-AzVmssDiskEncryptionExtension'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki kesalahan ketik untuk memanfaatkan dokumentasi 'Windows' di dokumentasi 'New-AzDataFactoryEncryptValue'
* Memperbarui versi ADF .Net SDK ke 4.1.2
* Menambahkan parameter 'DataProxyIntegrationRuntimeName', 'DataProxyStagingLinkedServiceName' dan 'DataProxyStagingPath' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan pengaturan Runtime Integrasi yang Dihost Sendiri sebagai proksi untuk Integration Runtime SSIS
* Memperbarui PSTriggerRun untuk menampilkan alur, pesan, dan properti yang dipicu, dan PSActivityRun untuk menampilkan jenis aktivitas

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki Get-DataLakeStoreDeletedItem untuk kesalahan atau pengecualian jarak jauh.

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah #9658 : Salah ketik parameter VirtualNteworkRule di Set-AzEventHubNetworkRuleSet
* Memperbaiki masalah #9558 : Set-AzEventHu0bNamespace menggunakan PATCH, bukan PUT
* menambahkan parameter EnableKafka ke cmdlet Set-AzEventHubNamespace
* Memperbaiki masalah #9786 : tidak dapat membuat aturan dengan hak Dengarkan saja

#### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* Memperbaiki kesalahan ketik dokumentasi di mana 'Azure' ditulis dalam huruf kecil

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam dokumentasi bantuan

#### <a name="aznetwork"></a>Az.Network
* Memperbarui New-AzPrivateLinkServiceIpConfig
    - Menghentikan parameter 'PublicIpAddress' karena parameter ini tidak pernah digunakan di sisi server.
    - Menambahkan satu parameter opsional 'Primary' yang menunjukkan konfigurasi ip saat ini adalah yang utama atau tidak.
* Meningkatkan penanganan pengecualian kesalahan permintaan dari SDK -Memperbaiki masalah pengecualian SDK sebelumnya yang tidak ditangani dengan benar sehingga mengakibatkan detail kesalahan utama tidak ditampilkan
* Menyesuaikan logika validasi untuk Awalan IP Ipv6 untuk memeriksa panjang prefiks IPv6 yang benar.
* Memperbarui Get-AzVirtualNetworkSubnetConfig: Menambahkan parameter yang diatur untuk mendapatkan id sumber daya subnet.
* Memperbarui Deskripsi parameter Lokasi untuk AzNetworkServiceTag

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbarui dokumentasi untuk 'New-AzOperationalInsightsLinuxSyslogDataSource'
    - Menambahkan contoh
    - Memperbarui deskripsi untuk parameter '-Name'
* Menambahkan contoh untuk New-AzOperationalInsightsWindowsEventDataSource
* Mengubah deskripsi parameter -Name untuk New-AzOperationalInsightsWindowsEventDataSource

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbarui 'Get-AzRecoveryServicesBackupJobDetail.md'

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk api baru versi 2019-05-10 untuk Microsoft.Resource
    - Menambahkan dukungan untuk 'copy.count = 0' untuk variabel, sumber daya, dan properti
    - Sumber daya dengan 'condition = false' atau 'copy.count = 0' akan dihapus dalam mode lengkap
* Menambahkan contoh menetapkan kebijakan di tingkat langganan untuk membantu dokumentasi

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki masalah #9658 : Salah ketik parameter VirtualNetworkRule di Set-AzServiceBusNetworkRuleSet
* Memperbaiki masalah #9786 : tidak dapat membuat aturan dengan hak Dengarkan saja
* Menambahkan perintah baru 'Test-AzServiceBusNameAvailability' untuk memeriksa ketersediaan nama untuk antrean dan topik

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki bug cmdlet jenis node tambahkan’:
    - Bug NullReferenceException ketika grup sumber daya memiliki vmss lain yang tidak terkait dengan kluster service fabric. Memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8681
    - Memperbaiki bug ketika cmdlet gagal jika virtualNetwork berada dalam grup sumber daya yang berbeda dengan kluster. memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8407
    - Menghentikan cmdlet Add-AzServiceFabricApplicationCertificate

#### <a name="azsql"></a>Az.Sql
* Memperbarui dokumentasi cmdlet Audit lama.

#### <a name="azstorage"></a>Az.Storage
* Memperbarui bantuan untuk Get/Close-AzStorageFileHandle, dengan menambahkan lebih banyak skenario ke contoh cmdlet dan memperbarui deskripsi parameter
* Mendukung StandardBlobTier di unggah blob dan salin blob
    -  Set-AzStorageBlobContent
    -  Start-AzStorageBlobCopy
* Mendukung Prioritas Rehidrasi dalam salin blob
    -  Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan klarifikasi di sekitar parameter -AppSettings di Set-AzWebApp dan Set-AzWebAppSlot

## <a name="250---july-2019"></a>2.5.0 - Juli 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Memperbaiki kesalahan ketik contoh dalam dokumentasi 'Remove-AzApplicationInsightsApiKey'

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan ketik dalam string sumber daya

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan dukungan NetworkRuleSet.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan properti yang hilang (ComputerName, OsName, OsVersion, dan HyperVGeneration) pada objek tampilan instans mesin virtual.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki kesalahan ketik dalam Remove-AzContainerRegistryReplication untuk parameter Replikasi
    - Informasi selengkapnya di sini https://github.com/Azure/azure-powershell/issues/9633

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.1.0
* Memperbaiki kesalahan ketik dalam dokumentasi untuk 'Get-AzDataFactoryV2PipelineRun'

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru yang ditambahkan untuk menghasilkan token SAS: New-AzEventHubAuthorizationRuleSASToken
* menambahkan pesan verifikasi dan kesalahan untuk hak otorisasi jika hanya 'Kelola' yang ditetapkan

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk menentukan Kebijakan KeySize for Certificate

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki Get-AzIntegrationAccountMap untuk mencantumkan semua jenis peta
    - Menambahkan parameter MapType baru untuk pemfilteran

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan dukungan untuk api versi 2019-06-01 (GA)

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk titik akhir privat dan layanan link privat
    - Cmdlet baru
        - Set-AzPrivateEndpoint
        - Set-AzPrivateLinkService
        - Approve-AzPrivateEndpointConnection
        - Deny-AzPrivateEndpointConnection
        - Get-AzPrivateEndpointConnection
        - Remove-AzPrivateEndpointConnection
        - Test-AzPrivateLinkServiceVisibility
        - Get-AzAutoApprovedPrivateLinkService
* Memperbarui perintah di bawah ini untuk fitur: PrivateEndpointNetworkPolicies/PrivateLinkServiceNetworkPolicies di Subnet di Virtualnetwork
    - Memperbarui New-AzVirtualNetworkSubnetConfig/Set-AzVirtualNetworkSubnetConfig/Add-AzVirtualNetworkSubnetConfig
        - Menambahkan parameter opsional -PrivateEndpointNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan pada titik akhir privat di subnet ini atau tidak.
        - Menambahkan parameter opsional -PrivateLinkServiceNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan pada layanan link privat di subnet ini atau tidak.
* Parameter cmdlet AzPrivateLinkService 'ServiceName' diganti namanya menjadi 'Name' dengan alias 'ServiceName' untuk kompatibilitas mundur
* Mengaktifkan protokol ICMP untuk konfigurasi aturan keamanan jaringan
    - Memperbarui cmdlet
        - Tambahkan-AzNetworkSecurityRuleConfig
        - New-AzNetworkSecurityRuleConfig
        - Set-AzNetworkSecurityRuleConfig
* Menambahkan ConnectionProtocolType (Ikev1/Ikev2) sebagai parameter yang dapat dikonfigurasi untuk New-AzVirtualNetworkGatewayConnection
* Menambahkan PrivateIpAddressVersion di LoadBalancerFrontendIpConfiguration
    - Memperbarui cmdlet:
        - New-AzLoadBalancerFrontendIpConfig
        - Add-AzLoadBalancerFrontendIpConfig
        - Set-AzLoadBalancerFrontendIpConfig
* Pembaruan perintah New-AzApplicationGatewayProbeConfig Application Gateway untuk mendukung port kustom di Probe
    - Memperbarui New-AzApplicationGatewayProbeConfig: Menambahkan Port parameter opsional yang digunakan untuk memeriksa server backend. Parameter ini berlaku untuk SKU Standard_V2 dan WAF_V2.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbarui versi default untuk pencarian yang disimpan menjadi 1.
* Memperbaiki penanganan regex null log kustom

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbarui 'Get-AzRecoveryServicesBackupJob.md'
* Memperbarui 'Get-AzRecoveryServicesBackupContainer.md'
* Memperbarui 'Get-AzRecoveryServicesVault.md'
* Memperbarui 'Wait-AzRecoveryServicesBackupJob.md'
* Memperbarui 'Set-AzRecoveryServicesVaultContext.md'
* Memperbarui 'Get-AzRecoveryServicesBackupItem.md'
* Memperbarui 'Get-AzRecoveryServicesBackupRecoveryPoint.md'
* Memperbarui 'Restore-AzRecoveryServicesBackupItem.md'
* Memperbarui panggilan layanan pada Kontainer Tidak Terdaftar untuk Berbagi File Azure
* Memperbarui 'Set-AzRecoveryServicesAsrAlertSetting.md'

#### <a name="azresources"></a>Az.Resources
- Menghapus cmdlet yang hilang yang dirujuk dalam dokumentasi 'New-AzResourceGroupDeployment'
- Memperbarui cmdlet kebijakan untuk menggunakan api baru versi 2019-01-01

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru yang ditambahkan untuk menghasilkan token SAS: New-AzServiceBusAuthorizationRuleSASToken
* menambahkan pesan verifikasi dan kesalahan untuk hak otorisasi jika hanya 'Manage' yang ditetapkan

#### <a name="azsql"></a>Az.Sql
* Memperbaiki contoh yang hilang untuk cmdlet Set-AzSqlDatabaseSecondary
* Memperbaiki pemindaian berulang pada Penilaian Kerentanan yang ditetapkan tanpa memberikan alamat email apa pun
* Memperbaiki kesalahan ketik kecil dalam pesan peringatan.

#### <a name="azstorage"></a>Az.Storage
* Memperbarui contoh dalam dokumentasi referensi pada 'Get-AzStorageAccount' untuk menggunakan nama parameter yang benar

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan cmdlet Invoke-AzStorageSyncChangeDetection.
* Memperbaiki Masalah 9551 untuk mematuhi TierFilesOlderThanDays

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug ketika beberapa properti SiteConfig tidak dimunculkan oleh Get-AzWebApp dan Set-AzWebApp
* Menambahkan parameter Lokasi baru ke Get-AzDeletedWebApp dan Restore-AzDeletedWebApp
* Memperbaiki bug dengan mengkloning slot aplikasi web menggunakan New-AzWebApp -IncludeSourceWebAppSlots

## <a name="240---july-2019"></a>2.4.0 - Juli 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan dukungan untuk cmdlet profil
* Menambahkan dukungan untuk lingkungan dan data plane di cmdlet yang dihasilkan
* Memperbaiki bug ketika titik akhir yang salah digunakan dalam beberapa kasus pada cmdlet data plane di Windows PowerShell

#### <a name="azadvisor"></a>Az.Advisor
* Rilis GA pada Az.Advisor
* Modul ini sekarang disertakan sebagai bagian dari modul `Az` roll-up

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8671
    - **Get-AzApiManagementSubscription**
        - Menambahkan dukungan untuk mengkueri langganan oleh Pengguna dan Produk
        - Menambahkan dukungan untuk kueri menggunakan Cakupan '/', '/apis', '/apis/echo-api'
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/9307 dan https://github.com/Azure/azure-powershell/issues/8432
    - **Import-AzApiManagementApi**
        - Menambahkan dukungan untuk menentukan 'ApiVersion' dan 'ApiVersionSetId' saat mengimpor Apis

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug cmdlet Set-AzAutomationConnectionFieldValue untuk menangani nilai string.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HyperVGeneration ke New-AzImageConfig

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui output aktivitas get yang berjalan, get alur yang berjalan, dan get pemicu yang menjalankan cmdlet ADF untuk mendukung alur Select-Object.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbaiki kesalahan ketik dalam dokumentasi 'New-AzEventGridSubscription'

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk meregenerasi kunci kebijakan otorisasi

#### <a name="aznetwork"></a>Az.Network
* Menambahkan 'RoutingPreference' ke tag ip publik
* Meningkatkan contoh untuk dokumentasi referensi 'Get-AzNetworkServiceTag'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi null di Get-AzPolicyState
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/9446

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbaiki model sumber data CustomLog yang dimunculkan dalam Get-AzOperationalInsightsDataSource

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki perintah get-policy untuk IaaSVMs

#### <a name="azresources"></a>Az.Resources
   - Memperbaiki teks bantuan untuk Parameter Get-AzPolicyState -Top
   - Menambahkan dukungan penomoran sisi klien untuk Get-AzPolicyAlias
   - Menambahkan parameter baru untuk Set-AzPolicyAssignment, -PolicyParameters dan -PolicyParametersObject
   - Beberapa dokumen dan contoh pembaruan untuk cmdlet Policy

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki masalah #4938 - New-AzureRmServiceBusQueue memunculkan BadRequest saat mengatur MaxSizeInMegabytes

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet Grup Failover Instans dari rilis pratinjau ke rilis publik
* Mendukung Audit Azure SQL Server\Database dengan cmdlet baru.
    - Set-AzSqlServerAudit
    - Get-AzSqlServerAudit
    - Remove-AzSqlServerAudit
    - Set-AzSqlDatabaseAudit
    - Get-AzSqlDatabaseAudit
    - Remove-AzSqlDatabaseAudit
* Menghapus batasan email dari pengaturan Penilaian Kerentanan

#### <a name="azstorage"></a>Az.Storage
* Mengubah 2 parameter '-IndexDocument' dan '-ErrorDocument404Path' dari wajib menjadi opsional dalam cmdlet:
    -  Enable-AzStorageStaticWebsite
* Memperbarui bantuan Get-AzStorageBlobContent dengan menambahkan contoh
* Menampilkan informasi kesalahan lainnya saat cmdlet gagal dengan StorageException
* Mendukung pembuatan atau pembaruan akun Penyimpanan dengan Autentikasi DS AAD Azure Files
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Mendukung pencantuman atau penutupan handel file berbagi file, direktori file, atau file
    - Get-AzStorageFileHandle
    - Close-AzStorageFileHandle

#### <a name="azstoragesync"></a>Az.StorageSync
* Modul ini sekarang disertakan sebagai bagian dari modul `Az` roll-up

## <a name="232---june-2019"></a>2.3.2 - Juni 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki bug ketika URL yang salah digunakan dalam beberapa kasus untuk panggilan Functions
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8983
* Memperbaiki Masalah alias dari AzureRM ke cmdlet Az
  - Set-AzureRmVMBootDiagnostics -> Set-AzVMBootDiagnostic
  - Export-AzureRMLogAnalyticThrottledRequests -> Export-AzLogAnalyticThrottledRequest

#### <a name="azcompute"></a>Az.Compute
* Set parameter sederhana New-AzVm dan New-AzVmss sekarang menerima parameter 'ProximityPlacementGroup'.
* Memperbaiki kesalahan ketik dalam dokumentasi referensi 'New-AzVM'

#### <a name="azdns"></a>Az.Dns
* Memperbaiki kesalahan ketik dalam contoh bantuan 'Set-AzDnsZone'.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui penggunaan versi API 06-01-2019.
* Cmdlet baru:
    - New-AzureRmEventGridDomain
        - Membuat Domain Azure Event Grid baru.
    - Get-AzureRmEventGridDomain
        - Mendapatkan detail Domain Event Grid, atau mendapatkan daftar semua Domain Event Grid dalam langganan Azure saat ini.
    - Remove-AzureRmEventGridDomain
        - Menghapus Domain Azure Event Grid.
    - New-AzureRmEventGridDomainKey
        - Meregenerasi kunci akses bersama untuk Domain Azure Event Grid.
    - Get-AzureRmEventGridDomainKey
        - Mendapatkan kunci akses bersama yang digunakan untuk menerbitkan peristiwa ke Domain Event Grid.
    - New-AzureRmEventGridDomainTopic:
        - Membuat Topik Domain Azure Event Grid baru.
    - Get-AzureRmEventGridDomainTopic
        - Mendapatkan detail Topik Domain Event Grid, atau mendapatkan daftar semua Topik Domain Event Grid di bawah Domain Event Grid tertentu di Azure saat ini
    - Remove-AzureRmEventGridDomainTopic:
        - Menghapus Topik Domain Azure Event Grid yang ada.
* Memperbarui cmdlet:
    - New-AzureRmEventGridSubscription/Update-AzureRmEventGridSubscription:
        - Menambahkan parameter wajib baru untuk mendukung penyaluran untuk Domain Event Grid baru dan Topik Domain Event Grid untuk memungkinkan pembuatan langganan peristiwa baru di bawah sumber daya ini.
        - Menambahkan parameter wajib baru untuk menentukan nama Domain Event Grid baru dan/atau nama Topik Domain Event Grid untuk memungkinkan pembuatan langganan peristiwa baru di bawah sumber daya ini.
        - Menambahkan set Parameter baru untuk domain dan topik domain untuk memungkinkan penggunaan kembali parameter yang ada (misalnya, EndPointType, SubjectBeginsWith, dll).
        - Menambahkan parameter opsional baru untuk menentukan:
            - Masa kedaluwarsa langganan peristiwa,
            - Parameter pemfilteran tingkat lanjut.
        - Menambahkan enum baru untuk servicebusqueue sebagai tujuan.
        - Melarang penggunaan 'All' dalam opsi -IncludedEventType dan menggantinya dengan
    - Get-AzEventGridTopic, Get-AzEventGridDomain, Get-AzEventGridDomainTopic, Get-AzEventGridSubscription:
        - Menambahkan parameter opsional baru (Top, ODataQuery dan NextLink) untuk mendukung hasil penomoran dan penyaringan.
    - Remove-AzureRmEventGridSubscription
        - Menambahkan parameter wajib baru untuk mendukung penyaluran untuk Domain Event Grid dan Topik Domain Event Grid untuk memungkinkan menghapus langganan peristiwa yang ada di bawah sumber daya ini.
        - Menambahkan parameter wajib baru untuk menentukan nama Domain Event Grid dan/atau nama Topik Domain Event Grid untuk memungkinkan menghapus langganan peristiwa yang ada di bawah sumber daya ini.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* New-AzFrontDoorWafMatchConditionObject
    - Menambahkan dukungan transformasi dan nilai lengkap otomatis operator baru (RegEx)
* New-AzFrontDoorWafManagedRuleObject
    - Menambahkan nilai lengkap otomatis baru

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk Sumber Daya Gateway Virtual Network
    - Cmdlet baru
        - Get-AzVirtualNetworkGatewayVpnClientConnectionHealth
* Menambahkan AvailablePrivateEndpointType
    - Cmdlet baru
        - Get-AzAvailablePrivateEndpointType
* Menambahkan PrivatePrivateLinkService
    - Cmdlet baru
        - Get-AzPrivateLinkService
        - New-AzPrivateLinkService
        - Remove-AzPrivateLinkService
        - New-AzPrivateLinkServiceIpConfig
        - Set-AzPrivateEndpointConnection
* Menambahkan PrivateEndpoint
    - Cmdlet baru
        - Get-AzPrivateEndpoint
        - New-AzPrivateEndpoint
        - Remove-AzPrivateEndpoint
        - New-AzPrivateLinkServiceConnection
* Memperbarui perintah fitur di bawah ini: Gunakan bendera UseLocalAzureIpAddress di VpnConnection
    - Memperbarui New-AzVpnConnection: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
    - Memperbarui Set-AzVpnConnection: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
* Menambahkan peeredConnections bidang baca saja di peering ExpressRoute.
* Menambahkan bidang baca saja GlobalReachEnabled di ExpressRoute.
* Menambahkan atribut perubahan yang berisiko untuk memanggil penghentian bidang AllowGlobalReach di model ExpressRouteCircuit
* Memperbaiki Masalah Kesalahan 8756 menggunakan TargetListenerID dengan cmdlet AzApplicationGatewayRedirectConfiguration
* Memperbaiki bug di New-AzApplicationGatewayPathRuleConfig yang mencegah kumpulan aturan penulisan ulang diterapkan.
* Memperbaiki tampilan VirtualNetworkTaps di NetworkInterfaceIpConfiguration
* Memperbaiki cmdlet Get Cortex untuk mencantumkan semua bagian
* Memperbaiki pembuatan referensi VirtualHub untuk ExpressRouteGateways, VpnGateway
* Menambahkan dukungan untuk Zona Ketersediaan di AzureFirewall dan NatGateway
* Menambahkan cmdlet Get-AzNetworkServiceTag
* Menambahkan dukungan untuk beberapa alamat IP publik untuk Azure Firewall
    - Memperbarui cmdlet New-AzFirewall:
        - Menambahkan parameter -PublicIpAddress yang menerima satu atau beberapa objek Alamat IP Publik
        - Menambahkan parameter -VirtualNetwork yang menerima objek Virtual Network
        - Menambahkan metode AddPublicIpAddress dan RemovePublicIpAddress pada objek firewall - metode ini menerima objek Alamat IP Publik sebagai input
        - Parameter yang tidak digunakan lagi -PublicIpName dan -VirtualNetworkName
* Memperbarui perintah fitur di bawah ini: Atur opsi autentikasi AAD VpnClient ke sumber daya gateway virtual.
    - Memperbarui New-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi autentikasi AAD VpnClient di Gateway.
    - Memperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi autentikasi AAD VpnClient di Gateway.
    - Memperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter sakelar opsional RemoveAadAuthentication untuk menghapus opsi autentikasi AAD VpnClient dari Gateway.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Mengaktifkan tingkat harga **pergb2018** dalam perintah 'New-AzureRmOperationalInsightsWorkspace'

#### <a name="azresources"></a>Az.Resources
* Mendukung opsi Ekspor Templat tambahan
    - Menambahkan parameter '-SkipResourceNameParameterization' ke Export-AzResourceGroup
    - Menambahkan parameter '-SkipAllParameterization' ke Export-AzResourceGroup
    - Menambahkan parameter '-Resource' ke Export-AzResourceGroup untuk pemfilteran sumber daya yang diekspor

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki penambahan sertifikat ByExistingKeyVault agar tidak mendapatkan thumbprint yang salah dalam beberapa kasus

#### <a name="azsql"></a>Az.Sql
* Memperbaiki akhiran titik akhir penyimpanan Perlindungan Ancaman Tingkat Lanjut
* Memperbaiki Advanced Data Security yang mengaktifkan penggantian kebijakan Perlindungan Ancaman Tingkat Lanjut
* Cmdlet baru untuk Management.Sql yang memungkinkan pelanggan menambahkan kunci TDE dan mengatur pelindung TDE untuk instans terkelola
   - Add-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceKeyVaultKey
   - Remove-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceTransparentDataEncryptionProtector
   - Set-AzSqlInstanceTransparentDataEncryptionProtector

#### <a name="azstorage"></a>Az.Storage
* Mendukung FileStorage Kind dan Premium_ZRS SkuName saat membuat akun Penyimpanan
    - New-AzStorageAccount
* Deskripsi yang diklarifikasi tentang cmdlet ketetapan blob
    -  Remove-AzRmStorageContainerImmutabilityPolicy

#### <a name="azwebsites"></a>Az.Websites
* Mengoptimalkan Get-AzWebAppCertificate untuk memfilter berdasarkan grup sumber daya di server, bukan klien
* Menambahkan parameter sakelar -UseDisasterRecovery ke Get-AzWebAppSnapshot

## <a name="220---june-2019"></a>2.2.0 - Juni 2019
#### <a name="azcdn"></a>Az.Cdn
* Memperbarui cmdlet untuk mendukung fitur rulesEngine berdasarkan API versi 2019-04-15.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter `NoWait` yang memulai operasi dan segera memunculkannya, sebelum operasi selesai.
    - Memperbarui cmdlet:   Export-AzLogAnalyticRequestRateByInterval   Export-AzLogAnalyticThrottledRequest   Remove-AzVM   Remove-AzVMAccessExtension   Remove-AzVMAEMExtension   Remove-AzVMChefExtension   Remove-AzVMCustomScriptExtension   Remove-AzVMDiagnosticsExtension   Remove-AzVMDiskEncryptionExtension   Remove-AzVMDscExtension   Remove-AzVMSqlServerExtension   Restart-AzVM   Set-AzVM   Set-AzVMAccessExtension   Set-AzVMADDomainExtension   Set-AzVMAEMExtension   Set-AzVMBginfoExtension   Set-AzVMChefExtension   Set-AzVMCustomScriptExtension   Set-AzVMDiagnosticsExtension   Set-AzVMDscExtension   Set-AzVMExtension   Start-AzVM   Stop-AzVM   Update-AzVM

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki #9231 - Get-AzEventHubNamespace tidak memunculkan tag
* Memperbaiki #9230 - Get-AzEventHubNamespace memunculkan ResourceGroup, bukan ResourceGroupName

#### <a name="aznetwork"></a>Az.Network
* Memperbarui ResourceId dan InputObject untuk Gateway Nat
    - Menambahkan alias untuk ResourceId dan InputObject

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi Null di Get-AzPolicyEvent

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Retensi minimum kebijakan IaaSVM dalam beberapa hari berubah menjadi 7, sebelumnya 1

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki masalah #9182 - Get-AzServiceBusNamespace memunculkan ResourceGroup, bukan ResourceGroupName

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki kesalahan ketik dalam pesan kesalahan untuk 'Update-AzServiceFabricReliability'
* Memperbaiki karakter yang hilang di cmdline Service Fabric

#### <a name="azsql"></a>Az.Sql
* Menambahkan Parameter DnsZonePartner untuk cmdlet New-AzureSqlInstance guna mendukung AutoDr pada Instans Terkelola.
* Menghentikan cmdlet Get-AzSqlDatabaseSecureConnectionPolicy
* Mengganti nama cmdlet Deteksi Ancaman menjadi Perlindungan Ancaman Tingkat Lanjut
* Parameter New-AzSqlInstance -StorageSizeInGB dan -LicenseType sekarang bersifat opsional.

#### <a name="azwebsites"></a>Az.Websites
* memperbaiki masalah saat menggunakan Set-AzWebApp dan Set-AzWebAppSlot dengan properti -WebApp yang menghapus tag

## <a name="210---may-2019"></a>2.1.0 - Mei 2019
#### <a name="azapimanagement"></a>Az.ApiManagement
* Membuat Cmdlet baru untuk mengelola diagnostik di Cakupan global dan API
    - **Get-AzApiManagementDiagnostic** - Mendapatkan diagnostik yang dikonfigurasi Cakupan global atau api
    - **New-AzApiManagementDiagnostic** - Membuat diagnostik baru di cakupan global atau Cakupan api
    - **New-AzApiManagementHttpMessageDiagnostic** - Membuat pengaturan diagnostik tempat Header mencatat dan ukuran Byte Body
    - **New-AzApiManagementPipelineDiagnosticSetting** - Membuat pengaturan Diagnostik untuk pesan HTTP masuk/keluar ke Gateway.
    - **New-AzApiManagementSamplingSetting** - Membuat Pengaturan Pengambilan Sampel untuk permintaan/respons untuk diagnostik
    - **Remove-AzApiManagementDiagnostic** - Menghapus entitas diagnostik di cakupan global atau api
    - **Set-AzApiManagementDiagnostic** - Memperbarui Entitas diagnostik di cakupan global atau api
* Membuat Cmdlet baru untuk mengelola Cache di layanan ApiManagement
    - **Get-AzApiManagementCache** - Mendapatkan detail Cache yang ditentukan oleh pengidentifikasi atau semua cache
    - **New-AzApiManagementCache** - Membuat Cache atau Cache 'default' baru di 'region' azure tertentu
    - **Remove-AzApiManagementCache** - Menghapus cache
    - **Update-AzApiManagementCache** - Memperbarui cache
* Membuat Cmdlet baru untuk mengelola Skema API
    - **New-AzApiManagementSchema** - Membuat skema baru untuk API
    - **Get-AzApiManagementSchema** - Mendapatkan skema yang dikonfigurasi dalam API
    - **Remove-AzApiManagementSchema** - Menghapus skema yang dikonfigurasi dalam API
    - **Set-AzApiManagementSchema** - Memperbarui skema yang dikonfigurasi dalam API
* Membuat Cmdlet baru untuk membuat Token Pengguna.
    - **New-AzApiManagementUserToken** - Membuat Token Pengguna baru yang berlaku selama 8 jam secara default. Token untuk pengguna 'GIT' dapat dihasilkan menggunakan cmdlet ini./
* Membuat cmdlet baru untuk mengambil Status Jaringan
    - **Get-AzApiManagementNetworkStatus** - Mendapatkan konektivitas status jaringan sumber daya tempat layanan API Management bergantung. Hal ini berguna saat menyebarkan layanan ApiManagement ke Virtual Network dan valid apakah ada dependensi yang rusak.
* Memperbarui cmdlet **New-AzApiManagement** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk SKU 'Consumption' baru
    - Menambahkan dukungan untuk mengaktifkan bendera 'EnableClientCertificate' untuk SKU 'Consumption'
    - Cmdlet baru **New-AzApiManagementSslSetting** memungkinkan konfigurasi pengaturan 'TLS/SSL' pada 'Backend' dan 'Frontend'. Hal ini juga dapat digunakan untuk mengkonfigurasi 'Cipher' seperti '3DES' dan 'ServerProtocols' seperti 'Http2' pada 'Frontend' dari layanan ApiManagement.
    - Menambahkan dukungan untuk mengonfigurasi nama host 'DeveloperPortal' pada layanan ApiManagement.
* Memperbarui cmdlets **Get-AzApiManagementSsoToken** untuk mengambil objek 'PsApiManagement' sebagai input
* Memperbarui cmdlet untuk menampilkan Pesan Kesalahan sebaris
     > PS D:\github\azure-powershell> Set-AzApiManagementPolicy -Context -PolicyFilePath C:\wrongpolicy.xml -ApiId httpbin Set-AzApiManagementPolicy : Kode Kesalahan: ValidationError Pesan Kesalahan: Satu atau beberapa bidang berisi nilai yang salah: Detail Kesalahan: [Code=ValidationError, Message=Kesalahan di elemen 'log-to-eventhub' pada baris 3, kolom 10: Pencatat tidak ditemukan, Target=log-to-eventhub]
* Memperbarui cmdlet **Export-AzApiManagementApi** untuk mengekspor API dalam format 'OpenApi 3.0'
* Memperbarui cmdlet **Import-AzApiManagementApi**
    - Untuk mengimpor Api dari spesifikasi dokumen 'OpenApi 3.0'
    - Untuk mengambil alih properti 'PsApiManagementSchema' yang ditentukan dalam dokumen apa pun ('Swagger', 'Wadl', 'Wsdl', 'OpenApi').
    - Untuk mengambil alih properti 'ServiceUrl' yang ditentukan dalam dokumen apa pun.
* Memperbarui cmdlet **Get-AzApiManagementPolicy** untuk mengembalikan kebijakan dalam 'format' non-Xml yang lolos menggunakan 'rawxml'
* Memperbarui cmdlet **Set-AzApiManagementPolicy** untuk menerima kebijakan dalam 'format' Non-Xml lolos menggunakan 'rawxml' dan Xml lolos menggunakan 'xml'
* Memperbarui cmdlet **New-AzApiManagementApi**
    - Untuk mengonfigurasi API dengan server otorisasi 'OpenId'.
    - Untuk membuat API di 'ApiVersionSet'
    - Untuk mengkloning API menggunakan 'SourceApiId' dan 'SourceApiRevision'.
    - Kemampuan untuk mengonfigurasi 'SubscriptionRequired' di cakupan Api.
* Memperbarui cmdlet **Set-AzApiManagementApi**
    - Untuk mengonfigurasi API dengan server otorisasi 'OpenId'.
    - Untuk memperbarui API menjadi 'ApiVersionSet'
    - Kemampuan untuk mengonfigurasi 'SubscriptionRequired' di cakupan Api.
* Memperbarui cmdlet **New-AzApiManagementRevision**
    - Untuk mengkloning (salin tag, produk, operasi, dan kebijakan) revisi yang ada menggunakan 'SourceApiRevision'. Revisi baru mengasumsikan 'ApiId' dari induk.
    - Untuk menyediakan 'ApiRevisionDescription'
    - Untuk mengambil alih 'ServiceUrl' saat mengkloning API.
* Memperbarui cmdlet **New-AzApiManagementIdentityProvider**
    - Untuk mengonfigurasi 'AAD' atau 'AADB2C' dengan 'Authority'
    - Untuk menyiapkan 'SignupPolicy', 'SigninPolicy', 'ProfileEditingPolicy' dan 'PasswordResetPolicy'
* Memperbarui cmdlet **New-AzApiManagementSubscription**
    - Untuk menjelaskan SubscriptonModel baru menggunakan 'Scope' dan 'UserId'
    - Untuk menjelaskan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Menambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Memperbarui cmdlet **Set-AzApiManagementSubscription**
    - Untuk menjelaskan SubscriptonModel baru menggunakan 'Scope' dan 'UserId'
    - Untuk menjelaskan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Menambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Memperbarui cmdlet berikut untuk menerima 'ResourceId' sebagai input
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
* Memperbarui Get-AzAutomationJobOutputRecord untuk menangani nilai JSON dan catatan Teks.
    - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/7977
    - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8600
* Mengubah perilaku bagi Start-AzAutomationDscCompilationJob untuk memulai pekerjaan bukan menunggu hingga selesai.
    * Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8347
* Memperbaiki Get-AzAutomationDscNode saat menggunakan -Name memunculkan semua node. Sekarang memunculkan node yang cocok saja.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter ProtectFromScaleIn dan ProtectFromScaleSetAction ke cmdlet Update-AzVmssVM.
* New-AzVM yang diatur sekarang menggunakan lokasi yang tersedia secara default jika 'US Timur' tidak didukung

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui sdk ADLS untuk menggunakan httpclient, mengintegrasikan pengujian dataplane dengan azure framework

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam contoh bantuan

#### <a name="aznetwork"></a>Az.Network
* Menambahkan bendera DisableBgpRoutePropagation ke output Tabel Rute yang Efektif
    - Memperbarui cmdlet:
        - Get-AzEffectiveRouteTable
* Memperbaiki tanda hubung ganda dalam dokumentasi New-AzApplicationGatewayTrustedRootCertificate

#### <a name="azresources"></a>Az.Resources
* Menambahkan cmdlet baru Get-AzureRmDenyAssignment untuk mengambil tugas penolakan

#### <a name="azsql"></a>Az.Sql
* Mengganti nama cmdlet Perlindungan Ancaman Tingkat Lanjut menjadi Advanced Data Security dan mengaktifkan Penilaian Kerentanan secara default

## <a name="200---may-2019"></a>2.0.0 - Mei 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Pustaka Autentikasi untuk memperbaiki masalah ADFS dengan autentikasi nama pengguna/kata sandi

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Hanya menampilkan pengelakan Bing untuk Layanan Pencarian Bing.
* Memperbaiki kesalahan saat gagal membuat akun.

#### <a name="azcompute"></a>Az.Compute
* Fitur grup penempatan kedekatan.
    - Cmdlet baru berikut ditambahkan: New-AzProximityPlacementGroup Get-AzProximityPlacementGroup Remove-AzProximityPlacementGroup
    - Parameter baru, ProximityPlacementGroupId, ditambahkan ke cmdlet berikut:   New-AzAvailabilitySet   New-AzVMConfig   New-AzVmssConfig
* Parameter StorageAccountType ditambahkan ke New-AzGalleryImageVersion.
* TargetRegion of New-AzGalleryImageVersion dapat berisi StorageAccountType.
* Parameter sakelar SkipShutdown ditambahkan ke Stop-AzVM dan Stop-AzVmss
* Perubahan mencolok
    - Set-AzVMBootDiagnostics diubah menjadi Set-AzVMBootDiagnostic.
    - Export-AzLogAnalyticThrottledRequests diubah menjadi Export-AzLogAnalyticThrottledRequests.

#### <a name="azdeploymentmanager"></a>Az.DeploymentManager
* Rilis cmdlet Manajer Penyebaran Azure pertama yang tersedia secara umum

#### <a name="azdns"></a>Az.Dns
* Delegasi NameServer DNS Otomatis
    - Membuat cmdlet zona DNS yang menerima nama zona induk sebagai parameter opsional tambahan.
    - Menambahkan catatan NS di zona induk untuk zona turunan yang baru dibuat.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Rilis Cmdlet Azure FrontDoor Pertama yang Tersedia Secara Umum
* Mengganti nama cmdlet WAF untuk menyertakan 'Waf'
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
* Menambahkan cmdlet baru Set-AzHDInsightGatewayCredential untuk menggantikan Grant-AzHDInsightHttpServicesAccess
* Memperbarui cmdlet Get-AzHDInsightJobOutput untuk membedakan peran pembaca dan peran operator hdinsight:
    - Pengguna dengan peran pembaca perlu menentukan parameter 'DefaultStorageAccountKey' secara eksplisit, jika tidak terjadi kesalahan.
    - Pengguna dengan peran operator hdinsight tidak akan terpengaruh.

#### <a name="azmonitor"></a>Az.Monitor
* Cmdlet baru untuk SQR API (Aturan Kueri Terjadwal)
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
    - Informasi [lebih lanjut](/rest/api/monitor/scheduledqueryrules) tentang SQR API
    - Memperbarui Az.Monitor.md untuk menyertakan cmdlet pada aturan peringatan berbasis metrik GenV2 (non klasik)

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk Sumber Daya Gateway Nat
    - Cmdlet baru
        - New-AzNatGateway
        - Get-AzNatGateway
        - Set-AzNatGateway
        - Remove-AzNatGateway
   - Memperbarui cmdlet
        - New-AzureVirtualNetworkSubnetConfigCommand
        - Add-AzureVirtualNetworkSubnetConfigCommand
* Memperbarui perintah di bawah ini untuk fitur: Rute kustom diatur/dihapus di Gateway Brooklyn.
    - Memperbarui New-AzVirtualNetworkGateway: Menambahkan parameter opsional -CustomRoute untuk mengatur awalan alamat sebagai rute kustom yang akan ditetapkan di Gateway.
    - Memperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter opsional -CustomRoute untuk mengatur awalan alamat sebagai rute kustom untuk diatur di Gateway.

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Mendukung untuk mengkueri detail evaluasi kebijakan.
    - Menambahkan parameter '-Expand' ke Get-AzPolicyState. Mendukung '-Expand PolicyEvaluationDetails'.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Mendukung antar langganan Azure ke pemulihan situs Azure.
* Menandai perubahan berisiko yang akan datang untuk Azure Site Recovery.
* Memperbaiki rencana tindakan akhir pemulihan Azure Site Recovery.
* Memperbaiki pemetaan jaringan Pembaruan Azure Site Recovery untuk Azure ke Azure.
* Memperbaiki arah perlindungan pembaruan Azure Site Recovery untuk Azure ke Azure pada disk terkelola.
* Perubahan kecil lainnya.

#### <a name="azrelay"></a>Az.Relay
* Memperbaiki kesalahan ketik dalam pesan yang diterima pelanggan

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru untuk NetworkRuleSet pada Namespace layanan

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan ke Pustaka Klien Penyimpanan 10.0.1 (namespace layanan semua objek dari SDK ini berubah dari 'Microsoft.WindowsAzure.Storage. *' menjadi 'Microsoft.Azure. Storage.* ')
* Meningkatkan ke Microsoft.Azure.Management.Storage 11.0.0, untuk mendukung API baru versi 2019-04-01.
* Akun Penyimpanan Kind default di Buat perubahan akun Penyimpanan dari 'Storage' menjadi 'StorageV2'
    - New-AzStorageAccount
* Mengubah output cmdlet akun Penyimpanan Sku.Name diratakan dengan input SkuName dengan menambahkan '-', seperti perubahan 'StandardLRS' menjadi 'Standard_LRS'
    - New-AzStorageAccount
    - Dapatkan-AkunPenyimpananAz
    - Set-AzStorageAccount

#### <a name="azwebsites"></a>Az.Websites
* Properti 'Kind' sekarang akan ditetapkan untuk objek PSSite yang dimunculkan oleh Get-AzWebApp
* Get-AzWebApp*Metrics dan Get-AzAppServicePlanMetrics ditandai sebagai tidak digunakan lagi

## <a name="180---april-2019"></a>1.8.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama sebelumnya
* Ketersediaan umum modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, silakan kunjungi: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan resourcename: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: cmdlet baru untuk Assembly Akun Integrasi dan Konfigurasi Batch

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Uninstall-AzureRm untuk menghapus modul dengan benar di Mac

#### <a name="azbatch"></a>Az.Batch
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="azcdn"></a>Az.Cdn
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah dengan penginstalan AEM jika id sumber daya disk memiliki kumpulan sumber daya huruf kecil di id sumber daya
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan SsisProperties jika NodeCount tidak null untuk runtime integrasi terkelola.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui teks bantuan untuk titik akhir guna menunjukkan bahwa sumber daya harus dibuat sebelum menggunakan cmdlet langganan peristiwa buat/perbarui.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru untuk NetworkRuleSet pada Namespace layanan

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azmachinelearning"></a>Az.MachineLearning
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="azmedia"></a>Az.Media
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan nama jamak yang tidak digunakan lagi.

#### <a name="azmonitor"></a>Az.Monitor
  * Cmdlet baru untuk aturan peringatan berbasis metrik GenV2 (non klasik)
      - New-AzMetricAlertRuleV2DimensionSelection
      - New-AzMetricAlertRuleV2Criteria
      - Remove-AzMetricAlertRuleV2
      - Get-AzMetricAlertRuleV2
      - Add-AzMetricAlertRuleV2
  * Memperbarui SDK Monitor ke versi 0.22.0-preview

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="aznotificationhubs"></a>Az.NotificationHubs
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.
* Memperbarui format tabel untuk SQL di mesin virtual azure
* Menambahkan metode alternatif untuk mengambil lokasi di AzureFileShare
* Memperbarui ScheduleRunDays di objek SchedulePolicy berdasarkan zona waktu

#### <a name="azrediscache"></a>Az.RedisCache
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azsql"></a>Az.Sql
* Mengganti dependensi pada SDK Monitor dengan kode umum
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.
* Menyempurnakan proses pada klasifikasi beberapa kolom.
* Menyertakan properti sku (nama sku, keluarga, kapasitas) sebagai respons dari Get-AzSqlServerServiceObjective dan format sebagai tabel secara default.
* Kemampuan untuk Get-AzSqlServerServiceObjective berdasarkan lokasi tanpa memerlukan server yang sudah ada sebelumnya di wilayah tersebut.
* Mendukung parameter zona waktu dalam pembuatan Instans Terkelola.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azwebsites"></a>Az.Websites
* memperbaiki Set-AzWebApp dan Set-AzWebAppSlot agar tidak menghapus tag pada eksekusi
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal dan menghentikan penggunaan nama jamak.
* Memperbarui SDK WebSites.
* Menghapus properti AdminSiteName dari PSAppServicePlan.

## <a name="170---april-2019"></a>1.7.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama sebelumnya
* Ketersediaan umum modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, silakan kunjungi: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan resourcename: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: cmdlet baru untuk Assembly Akun Integrasi dan Konfigurasi Batch

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAnalysisServicesEndpointResourceId

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Menggunakan ServiceClient dalam cmdlet dataplane dan menghapus logika autentikasi asli
* Membuat Add-AzureASAccount sebagai pembungkus Connect-AzAccount untuk menghindari perubahan yang berisiko

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug cmdlet New-AzAutomationSoftwareUpdateConfiguration untuk Inklusi. Sekarang parameter IncludedKbNumber dan IncludedPackageNameMask akan berfungsi.
* Memperbaiki bug untuk grup dinamis manajemen pembaruan otomatisasi azure

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HyperVGeneration ke New-AzDiskConfig dan New-AzSnapshotConfig
* Mengizinkan pembuatan mesin virtual dengan gambar galeri dari penyewa lain.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbaiki masalah di parameter -Command New-AzContainerGroup yang menambahkan argumen kosong berikutnya

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 3.0.2
* Memperbarui Set-AzDataFactoryV2 cmdlet dengan parameter tambahan untuk pengaturan terkait RepoConfiguration.

#### <a name="azresources"></a>Az.Resources
* Meningkatkan penanganan penyedia untuk parameter 'Get-AzResource' saat menyediakan parameter '-ResourceId' atau '-ResourceGroupName', '-Name' dan '-ResourceType'
* Meningkatkan penanganan kesalahan untuk 'Test-AzDeployment' dan 'Test-AzResourceGroupDeployment'
    - Menangani kesalahan yang dikeluarkan di luar validasi penyebaran dan menyertakannya ke dalam output perintah sebagai gantinya
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/6856
* Menambahkan parameter sakelar '-IgnoreDynamicParameters' ke kumpulan cmdlet penyebaran untuk melewati permintaan dalam skenario skrip dan pekerjaan
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/6856

#### <a name="azsql"></a>Az.Sql
* Mendukung Klasifikasi Data Database.

#### <a name="azstorage"></a>Az.Storage
* Melaporkan kesalahan detail saat membuat konteks Penyimpanan dengan parameter -UseConnectedAccount, tetapi tanpa login akun Azure
    - New-AzStorageContext
* Mendukung Pengelolaan Properti Layanan Blob dari akun Penyimpanan tertentu dengan API bidang Manajemen
    - Update-AzStorageBlobServiceProperty
    - Get-AzStorageBlobServiceProperty
    - Enable-AzStorageBlobDeleteRetentionPolicy
    - Disable-AzStorageBlobDeleteRetentionPolicy
* -AsJob mendukung Blob dan pengunggahan file dan pengunduhan cmdlet
    - Get-AzStorageBlobContent
    - Set-AzStorageBlobContent
    - Get-AzStorageFileContent
    - Set-AzStorageFileContent

## <a name="160---march-2019"></a>1.6.0 - Maret 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis utama sebelumnya
* Ketersediaan umum modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, silakan kunjungi: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan resourcename: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: cmdlet baru untuk Assembly Akun Integrasi dan Konfigurasi Batch

#### <a name="azautomation"></a>Az.Automation
* Otomatisasi Azure memperbarui perubahan manajemen untuk mendukung fitur baru berikut:
    * Pengelompokan dinamis
    * Skrip Pra-Posting
    * Pengaturan penghidupan ulang

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah pada resolusi jalur di Get-AzVmBootDiagnosticsData
* Memperbarui pustaka klien Azure Compute ke 25.0.0.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan kartubebas ke cmdlet KeyVault

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan Inteligensi Ancaman untuk Azure Firewall
* Menambahkan sumber daya tingkat atas Kebijakan Firewall Application Gateway dan Aturan Kustom

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan SnapshotRetentionInDays dalam kebijakan mesin virtual Azure untuk mendukung RP Instan
* Menambahkan dukungan alur untuk kontainer yang tidak terdaftar

#### <a name="azresources"></a>Az.Resources
* Memperbarui dukungan kartubebas untuk Get-AzResource dan Get-AzResourceGroup
* Memperbarui info masuk yang digunakan saat melakukan panggilan umum ke ARM

#### <a name="azsql"></a>Az.Sql
* mengubah param cmdlet Deteksi Ancaman (ExcludeDetectionType) dari DetectionType ke string[] untuk menjadikannya sebagai bukti di masa mendatang ketika DetectionTypes baru ditambahkan dan juga untuk mendukung pelengkapan otomatis.

#### <a name="azstorage"></a>Az.Storage
* Mendukung Kebijakan Manajemen Get/Set/Remove pada akun Penyimpanan
    - Atur-AzStorageAccountManagementPolicy
    - Get-AzStorageAccountManagementPolicy
    - Hapus-AzStorageAccountManagementPolicy
    - Tambahkan-AzstorageAccountManagementPolicyaction
    - Baru-AzStorageAccountManagementPolicyFilter
    - Baru-AzStorageAccountManagementPolicyRule

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug templat ARM yang memutus kloning semua slot menggunakan 'New-AzWebApp -IncludeSourceWebAppSlots'

## <a name="150---march-2019"></a>1.5.0 - Maret 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan perintah 'Register-AzModule' untuk mendukung cmdlet yang dihasilkan AutoRest
* Memperbarui contoh untuk Connect-AzAccount

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah saat menerima jadwal bulanan tertentu di beberapa cmdlet Azure Automation
* Memperbaiki Get-AzAutomationDscNode yang memunculkan hanya 20 node teratas. Sekarang memunculkan semua node

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet Powershell baru untuk Mengaktifkan/Menonaktifkan Https Domain Kustom dan menghentikan penggunaan yang lama

#### <a name="azcompute"></a>Az.Compute
* Menambahkan dukungan kartubebas ke cmdlet Get

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 3.0.1

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki ListWorkflows yang hanya mengambil halaman pertama hasil

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan kartubebas ke cmdlet Network

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan server Sql di dukungan mesin virtual Azure
* Pembaruan SDK
* Menghapus cek masuk VMappContainer Get-ProtectableItem
* Menambahkan Name dan ServerName sebagai parameter untuk Get-ProtectableItem

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter `-TemplateObject` ke cmdlet penyebaran
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/2933
* Memperbaiki masalah saat menyalurkan hasil `Get-AzResource` ke `Set-AzResource`
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8240
* Memperbaiki masalah dengan perubahan jenis data JSON saat menjalankan `Set-AzResource`
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/7930

#### <a name="azsql"></a>Az.Sql
* Memperbarui AuditEndpointsCommunicator.
    - Memperbaiki perilaku kasus tepi saat membuat pengaturan diagnostik baru.

#### <a name="azstorage"></a>Az.Storage
* Mendukung BlockBlobStorage Kind saat membuat akun Penyimpanan      - New-AzStorageAccount

## <a name="140---february-2019"></a>1.4.0 - Februari 2019
#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Menghentikan penggunaan cmdlet AddAzureASAccount

#### <a name="azautomation"></a>Az.Automation
* Memperbarui bantuan untuk Import-AzAutomationDscNodeConfiguration
* Menambahkan validasi nama konfigurasi ke cmdlet Import-AzAutomationDscConfiguration
* Meningkatkan penanganan kesalahan untuk cmdlet Import-AzAutomationDscConfiguration

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan CustomSubdomainName sebagai parameter opsional baru untuk New-AzCognitiveServicesAccount yang digunakan untuk menentukan subdomain pada sumber daya.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah set parameter ID
* Memperbarui Get-AzVMExtension untuk mencantumkan semua ekstensi yang dipasang jika parameter Name tidak disediakan
* Menambahkan parameter Tag dan ResourceId ke cmdlet Update-AzImage
* Get-AzVmssVM tanpa ID instans dan dengan InstanceView dapat mencantumkan mesin virtual VMSS dengan tampilan instans.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan cmdlet untuk enumerasi dan pemulihan item ADL yang terhapus

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan properti boolean baru SkipEmptyArchives untuk Melewati Arsip Kosong di kelas CaptureDescription Eventhub

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki penandaan di Set-AzKeyVaultSecret

#### <a name="azlogicapp"></a>Az.LogicApp
* Menambahkan sku Dasar untuk Akun Integrasi
* Menambahkan XSLT 2.0, XSLT 3.0 dan Jenis Peta Dinamis
* Cmdlet baru untuk Assembly Akun Integrasi
    - Get-AzIntegrationAccountAssembly
    - New-AzIntegrationAccountAssembly
    - Remove-AzIntegrationAccountAssembly
    - Set-AzIntegrationAccountAssembly
* Cmdlet baru untuk Konfigurasi Batch Akun Integrasi
    - Get-AzIntegrationAccountBatchConfiguration
    - New-AzIntegrationAccountBatchConfiguration
    - Remove-AzIntegrationAccountBatchConfiguration
    - Set-AzIntegrationAccountBatchConfiguration
* Memperbarui SDK Aplikasi Logika ke versi 4.1.0

#### <a name="azmonitor"></a>Az.Monitor
* Memperbarui bantuan untuk Get-AzMetric

#### <a name="aznetwork"></a>Az.Network
* Memperbarui contoh bantuan untuk Add-AzApplicationGatewayCustomError

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Dukungan tambahan untuk sumber data New dan Get ApplicationInsights.
    - Menambahkan jenis 'ApplicationInsights' baru untuk mendukung Get spesifik dan Get semua sumber data ApplicationInsights untuk ruang kerja tertentu.
    - Menambahkan cmdlet New-AzOperationalInsightsApplicationInsightsDataSource untuk membuat sumber data dengan parameter sumber daya Application-Insights yang diberikan: Id langganan, resourceGroupName, dan name.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8166
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8235
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6219
* Memperbaiki bug yang mencegah pembuatan KeyCredentials berulang

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk tingkat DB Hyperscale SQL
* Memperbaiki bug ketika pemulihan bisa gagal karena pengaturan properti yang tidak perlu dalam permintaan pemulihan

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki contoh pada Get-AzWebAppSlotMetrics

## <a name="130---february-2019"></a>1.3.0 - Februari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui ke versi terbaru ClientRuntime

#### <a name="azanalysisservices"></a>Az.AnalysisServices
Ketersediaan umum untuk modul Az.AnalysisServices.

#### <a name="azcompute"></a>Az.Compute
* Ekstensi AEM: Menambahkan dukungan untuk disk UltraSSD dan P60,P70 dan P80
* Memperbarui deskripsi bantuan untuk Set-AzVMBootDiagnostics
* Memperbarui deskripsi dan contoh bantuan untuk Update-AzImage

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
Ketersediaan umum untuk modul Az.RecoveryServices.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki penandaan untuk grup sumber daya
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8166
* Memperbaiki masalah ketika `Get-AzureRmRoleAssignment` tidak mematuhi -ErrorAction
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8235

#### <a name="azsql"></a>Az.Sql
* Menambahkan Get/Set AzSqlDatabaseBackupShortTermRetentionPolicy
* Memperbaiki masalah ketika tidak masuk ke akun Azure akan mengakibatkan pengecualian nullref saat menjalankan cmdlet SQL
* Memperbaiki pengecualian ref null di Get-AzSqlCapability

## <a name="121---january-2019"></a>1.2.1 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Merilis dengan versi Autentikasi yang benar

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Merilis dengan dependensi Autentikasi yang diperbarui

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Merilis dengan dependensi Autentikasi yang diperbarui

## <a name="120---january-2019"></a>1.2.0 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Memperbarui URL bantuan online yang salah
* Menambahkan pesan peringatan di PS Core untuk Uninstall-AzureRm

#### <a name="azaks"></a>Az.Aks
* Memperbarui URL bantuan online yang salah

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk runbook Python 2
* Memperbarui URL bantuan online yang salah

#### <a name="azcdn"></a>Az.Cdn
* Memperbarui URL bantuan online yang salah

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet Invoke-AzVMReimage
* Menambahkan parameter TempDisk ke Set-AzVmss
* Memperbaiki pesan peringatan New-AzVM

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbarui URL bantuan online yang salah

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 3.0.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki masalah titik akhir ADLS saat menggunakan MSI
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/7462
* Memperbarui URL bantuan online yang salah

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan format Pengodean ke cmdlet Add-IotHubRoutingEndpoint.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbarui URL bantuan online yang salah

#### <a name="aznetwork"></a>Az.Network
* Memperbarui URL bantuan online yang salah

#### <a name="azresources"></a>Az.Resources
* Memperbaiki contoh yang salah dalam dokumentasi referensi 'New-AzADAppCredential' dan 'New-AzADSpCredential'
* Memperbaiki masalah ketika jalur untuk parameter '-TemplateFile' tidak diselesaikan sebelum menjalankan cmdlet penyebaran grup sumber daya
* Az.Resources: Memperbaiki dokumentasi untuk nilai default New-AzureRmPolicyDefinition -Mode
* Az.Resources: Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/7522
* Az.Resources: Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/5747
* Memperbaiki masalah pemformatan dengan objek 'PSResourceGroupDeployment'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/2123

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memutar kembali ketika sertifikat ditambahkan ke model VMSS tetapi pengecualian diberikan untuk memperbaiki bug: https://github.com/Azure/service-fabric-issues/issues/932
* Memperbaiki beberapa pesan kesalahan.
* Memperbaiki pembuatan kluster dengan templat ARM default untuk New-AzServiceFabriCluster yang tidak berfungsi dengan migrasi ke Az.
* Memperbaiki penambahan sertifikat kluster/aplikasi untuk ditambahkan hanya ke VM Scale Sets yang sesuai kluster dengan memeriksa id kluster di ekstensi.

#### <a name="azsignalr"></a>Az.SignalR
* Memperbarui URL bantuan online yang salah

#### <a name="azsql"></a>Az.Sql
* Memperbarui URL bantuan online yang salah
* Memperbarui deskripsi parameter untuk parameter LicenseType dengan nilai yang memungkinkan
* Memperbaiki pembaruan identitas instans terkelola yang tidak berfungsi ketika identitas tersebut satu-satunya properti yang diperbarui
* Mendukung kolase kustom pada instans terkelola

#### <a name="azstorage"></a>Az.Storage
* Memperbarui URL bantuan online yang salah
* Memberikan pesan kesalahan detail saat melakukan get/set Logging/Metric klasik di Akun Penyimpanan Premium, karena Akun Premium Storage tidak mendukung Logging/Metric klasik.
    - Get/Set-AzStorageServiceLoggingProperty
    - Get/Set-AzStorageServiceMetricsProperty

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Memperbarui URL bantuan online yang salah

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui URL bantuan online yang salah
* Memperbaiki 'New-AzWebAppSSLBinding' untuk mengunggah sertifikat ke resourcegroup+location yang benar jika aplikasi dihosting di ASE.
* Memperbaiki 'New-AzWebAppSSLBinding' agar tidak menimpa tag saat mengikat sertifikat SSL ke aplikasi

## <a name="110---january-2019"></a>1.1.0 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Cakupan 'Local' ke Enable-AzureRmAlias

#### <a name="azcompute"></a>Az.Compute
* Name sekarang bersifat opsional dalam parameter ID yang ditetapkan untuk Restart/Start/Stop/Remove/Set-AzVM dan Save-AzVMImage
* Memperbarui deskripsi ID dalam file bantuan
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui versi sdk dataplane ke 1.1.14 untuk perbaikan SDK.
    - Memperbaiki penanganan acesstime negatif dan waktu modifikasi untuk getfilestatus dan liststatus, Memperbaiki token pembatalan asinkron

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui penggunaan versi API 01-01-2019.
* Memperbarui cmdlet berikut untuk mendukung skenario baru dalam versi API 2019-01-01
    - New-AzureRmEventGridSubscription: Menambahkan parameter opsional baru untuk menentukan:
        - Waktu Hidup Peristiwa,
        - Jumlah maksimum upaya pengiriman untuk peristiwa tersebut,
        - Titik akhir surat gagal.
    - Update-AzureRmEventGridSubscription: Menambahkan parameter opsional baru untuk menentukan:
        - Waktu Hidup Peristiwa,
        - Jumlah maksimum upaya pengiriman untuk peristiwa tersebut,
        - Titik akhir surat gagal.
* Menambahkan nilai enum baru (yaitu, storageQueue dan hybridConnection) untuk opsi EndpointType dalam cmdlet New-AzureRmEventGridSubscription dan Update-AzureRmEventGridSubscription.
* Menampilkan pesan peringatan jika pembuatan atau pembaruan langganan peristiwa diharapkan melibatkan tindakan manual dari pengguna.

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui SDK IotHub ke versi terbaru

#### <a name="azlogicapp"></a>Az.LogicApp
* Get-AzLogicApp mencantumkan semua tanpa Name yang ditentukan

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah set parameter saat menyediakan parameter '-ODataQuery' dan '-ResourceId' untuk 'Get-AzResource'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/7875
* Memperbaiki penanganan parameter -Custom di New/Set-AzPolicyDefinition
* Memperbaiki kesalahan ketik dalam dokumentasi New-AzDeployment
* Mewajibkan parameter '-MailNickname' untuk 'New-AzADUser'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8220

#### <a name="azsignalr"></a>Az.SignalR
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

#### <a name="azsql"></a>Az.Sql
* Mengonversi dependensi klien manajemen Penyimpanan ke implementasi SDK umum.

#### <a name="azstorage"></a>Az.Storage
* Mengatur StorageAccountName pada konteks Penyimpanan sebagai Nama Akun Penyimpanan yang sebenarnya, saat dibuat dengan Sas Token, OAuth, atau Anonim
    - New-AzStorageContext
* Membuat Token Sas Objek Snapshot Blob dengan parameter '-FullUri', memperbaiki Uri yang dimunculkan menjadi snapshot Uri
    - New-AzStorageBlobSASToken

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug penguraian tanggal di 'Get-AzDeletedWebApp'
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

## <a name="100---december-2018"></a>1.0.0 - Desember 2018
### <a name="general"></a>Umum

- Ketersediaan Umum Modul Az
- Bantuan online untuk setiap modul
- Untuk detail selengkapnya dan peta strategi, lihat [Halaman Pengumuman Az](https://aka.ms/azps-announce)
- Lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk informasi tentang migrasi dari AzureRM

### <a name="azaccounts"></a>Az.Accounts
- Berubah dari Az.Profile
- Memperbaiki format tabel untuk jenis profil dan konteks

### <a name="azapimanagement"></a>Az.ApiManagement
- Memperbaiki #7002
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azbatch"></a>Az.Batch
- Menambahkan kemampuan untuk melihat versi Agen Node Azure Batch yang berjalan di masing-masing mesin virtual dalam kumpulan, melalui properti `NodeAgentInformation` baru di `PSComputeNode`.
- Default `Caching` untuk `PSDataDisk` sekarang `ReadWrite`, bukan `None`.
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azbilling"></a>Az.Billing
- Menggabungkan Penagihan, Konsumsi, dan cmdlet UsageAggregates, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azcognitivservices"></a>Az.CognitivServices
- Menambahkan pelengkap untuk SkuName dan Typem yang tersedia di New-AzureRmCognitiveServicesAccount operasi
- Menghapus set parameter GetSkusWithAccountParamSetName dari Get-AzCognitiveServicesAccountSkus

### <a name="azcontainerinstance"></a>Az.ContainerInstance
- Menambahkan dukungan ManagedIdentity

### <a name="azdatalakeanalytics"></a>Az.DataLakeAnalytics
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azdatalakestore"></a>Az.DataLakeStore
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azmonitor"></a>Az.Monitor
- Mengganti nama Az.Insights menjadi Az.Monitor dan perubahan berisiko kecil lainnya, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azkeyvault"></a>Az.KeyVault
- Menghapus properti 'PurgeDisabled' yang tidak digunakan lagi dari jenis output

### <a name="azmachinelearning"></a>Az.MachineLearning
- Menyertakan cmdlet dari modul Az.MachineLearningCompute

### <a name="azmedia"></a>Az.Media
- Menghapus alias -Tags yang tidak digunakan lagi dari New-AzMediaService

### <a name="aznetwork"></a>Az.Network
Menambahkan dukungan untuk mengonfigurasi RewriteRuleSets di Application Gateway
    - Cmdlet baru ditambahkan:
        - Add-AzureRmApplicationGatewayRewriteRuleSet
        - Get-AzureRmApplicationGatewayRewriteRuleSet
        - New-AzureRmApplicationGatewayRewriteRuleSet
        - Remove-AzureRmApplicationGatewayRewriteRuleSet
        - Set-AzureRmApplicationGatewayRewriteRuleSet
        - New-AzureRmApplicationGatewayRewriteRule
        - New-AzureRmApplicationGatewayRewriteRuleActionSet
        - New-AzureRmApplicationGatewayRewriteRuleHeaderConfiguration
    - Memperbarui cmdlet dengan parameter opsional -RewriteRuleSet
        - New-AzureRmApplicationGateway
        - New-AzureRmApplicationGatewayRequestRoutingRule
        - Add-AzureRmApplicationGatewayRequestRoutingRule
        - New-AzureRmApplicationGatewayPathRuleConfig
        - Add-AzureRmApplicationGatewayUrlPathMapConfig
        - New-AzureRmApplicationGatewayUrlPathMapConfig Menambahkan Dukungan KeyVault ke Application Gateway menggunakan Identity.
    - Memperbarui cmdlet dengan parameter opsional -KeyVaultSecretId, -KeyVaultSecret
        - Add-AzApplicationGatewaySslCertificate
        - New-AzApplicationGatewaySslCertificate
        - Set-AzApplicationGatewaySslCertificate
    - Memperbarui cmdlet New-AzApplicationGateway dengan parameter opsional -UserAssignedIdentity
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azoperationalinsights"></a>Az.OperationalInsights
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azprofile"></a>Az.Profile
- Mengubah nama modul menjadi Az.Accounts

### <a name="azrecoveryservices"></a>Az.RecoveryServices
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azresources"></a>Az.Resources
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azservicefabric"></a>Az.ServiceFabric
- Mendukung Penentuan sertifikat berdasarkan nama umum dan thumbprint
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azsignalr"></a>Az.SIgnalR
- Ketersediaan Umum untuk cmdlet PowerShell pada SIgnalR

### <a name="azsql"></a>Az.Sql
- Menambahkan jenis deteksi Data_Exfiltration dan Unsafe_Action baru ke cmdlet Deteksi Ancaman
- Memperbarui contoh dokumentasi untuk cmdlet Audit Sql
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azstorage"></a>Az.Storage
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azwebsites"></a>Az.Websites
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

## <a name="070---december-2018"></a>0.7.0 - Desember 2018

### <a name="general"></a>Umum

* Perubahan kecil untuk transisi AzureRM ke Az mendatang

### <a name="azcompute"></a>Az.Compute

* Menambahkan dukungan untuk UltraSSD dan Gambar Galeri dalam set param sederhana untuk cmdlet `New-AzVm(ss)`.

### <a name="azdatalakestore"></a>Az.DataLakeStore

* Memperbaiki garis miring di belakang domain akun adls

### <a name="azfrontdoor"></a>Az.FrontDoor

* Memperbaiki beberapa hyperlink rusak
    - Memperbaiki link ke artikel cmdlet New-AzureRmFrontDoorHealthProbeSettingObject dalam artikel New-AzureRmFrontDoor dan Set-AzureRmFrontDoor.
    - Memperbaiki link ke artikel cmdlet New-AzureRmFrontDoorRuleGroupOverrideObject dalam artikel New-AzureRmFrontDoorManagedRuleObject.

### <a name="azrecoveryservices"></a>Az.RecoveryServices

* Menambahkan validasi sisi klien untuk operasi pemulihan Berbagi File Azure.
* Menjadikan storageAccountName dan storageAccountResourceGroupName sebagai opsional untuk pemulihan afs.

### <a name="azresources"></a>Az.Resources

* Memperbaiki https://github.com/Azure/azure-powershell/issues/7679
    - Memperbarui Get-AzureRmRoleAssignment untuk menggunakan cakupan langganan jika disediakan saat meminta administrator klasik.

### <a name="azsql"></a>Az.Sql

* Perubahan kecil untuk transisi AzureRM ke Az mendatang
* Memperbaiki masalah dengan menggunakan Get-AzureRmSqlDatabaseVulnerabilityAssessment dengan inti DotNet
* Mengubah dokumentasi pesan bantuan yang terkait dengan cmdlet Audit SQL.

### <a name="azstorage"></a>Az.Storage

* Menambahkan -EnableHierarchicalNamespace ke New-AzureRmStorageAccount
* Memperbaiki masalah bahwa cmdlet Copy File tidak dapat menggunakan kembali konteks sumber di tujuan saat tidak memasukkan -DestContext
    - Start-AzureStorageFileCopy
* Mendukung konfigurasi Situs Web Statis
    - Enable-AzureStorageStaticWebsite
    - Disable-AzureStorageStaticWebsite

### <a name="azwebsites"></a>Az.Websites

* Set-AzureRmWebApp dan Set-AzureRmWebAppSlot
    - Parameter baru (-AzureStoragePath) ditambahkan untuk menentukan jalur Azure Storage yang akan dipasang di aplikasi kontainer Windows dan Linux. Menggunakan output cmdlet baru New-AzureRmWebAppAzureStoragePath sebagai parameter untuk mengatur jalur Azure Storage.

## <a name="061---november-2018"></a>0.6.1 - November 2018

### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbarui dependensi untuk masalah pemetaan jenis

### <a name="azautomation"></a>Az.Automation
* Cmdlet Azure Automation berbasis Swagger
* Menambahkan cmdlet Update Management
* Menambahkan cmdlet Source Control
* Menambahkan cmdlet Remove-AzureRmAutomationHybridWorkerGroup
* Memperbaiki perintah Node Pendaftaran DSC

### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah identitas untuk identitas SystemAssigned
* Memperbarui dependensi untuk masalah pemetaan jenis

### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbarui dependensi untuk masalah pemetaan jenis

### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* memperbarui deskripsi contoh untuk cmdlet marketplace

### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet New-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayCustomError, Get-AzureRmApplicationGatewayCustomError, Set-AzureRmApplicationGatewayCustomError, Remove-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayHttpListenerCustomError, Get-AzureRmApplicationGatewayHttpListenerCustomError, Set-AzureRmApplicationGatewayHttpListenerCustomError, Remove-AzureRmApplicationGatewayHttpListenerCustomError
* Menambahkan ICMP kembali ke Protokol Jaringan AzureFirewall yang didukung
* Memperbarui cmdlet Test-AzureRmNetworkWatcherConnectivity, menambahkan validasi pada id tujuan, alamat, dan port.
* Memperbaiki masalah penggunaan memori di peta VirtualNetwork

### <a name="azrecoveryservicesbackup"></a>Az.RecoveryServices.Backup
* Memperbaiki perubahan kebijakan untuk berbagi file yang dilindungi.
* Mengonversi zona waktu kebijakan menjadi huruf besar.

### <a name="azrecoveryservicessiterecovery"></a>Az.RecoveryServices.SiteRecovery
* Memperbaiki contoh di New-AzureRmRecoveryServicesAsrProtectableItem
* Memperbarui dependensi untuk masalah pemetaan jenis

### <a name="azrelay"></a>Az.Relay
* Menambahkan Parameter opsional -KeyValue ke cmdlet New-AzureRmRelayKey, yang memungkinkan pengguna untuk menyediakan KeyValue.

### <a name="azresources"></a>Az.Resources
* Memperbarui dokumentasi bantuan untuk parameter terkait identitas sumber daya di `New-AzureRmPolicyAssignment` dan `Set-AzureRmPolicyAssignment`
* Menambahkan contoh untuk New-AzureRmPolicyDefinition yang menggunakan -Metadata
* Melakukan perbaikan agar memungkinkan pelestarian kasus di kunci Tag di NetStandard: #7678 #7703

### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan pesan penghentian untuk perubahan berisiko yang akan datang

### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet baru untuk operasi CRUD pada Instans Terkelola Database Azure Sql dan Database Terkelola Azure Sql
    - Get-AzureRmSqlInstance
    - New-AzureRmSqlInstance
    - Set-AzureRmSqlInstance
    - Remove-AzureRmSqlInstance
    - Get-AzureRmSqlInstanceDatabase
    - New-AzureRmSqlInstanceDatabase
    - Restore-AzureRmSqlInstanceDatabase
    - Remove-AzureRmSqlInstanceDatabase
* Mengaktifkan Manajemen Kebijakan Audit yang Diperpanjang di server atau database.
    - Parameter baru (PredicateExpression) ditambahkan untuk mengaktifkan pemfilteran log audit.
    - Cmdlet dimodifikasi untuk menggunakan klien SQL, bukan klien Legacy.
    - Set-AzureRmSqlServerAuditing.
    - Get-AzureRmSqlServerAuditing.
    - Set-AzureRmSqlDatabaseAuditing.
    - Get-AzureRmSqlDatabaseAuditing.
* Memperbaiki masalah saat menggunakan Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings dengan kumpulan parameter nama akun penyimpanan

## <a name="050---november-2018"></a>0.5.0 - November 2018
#### <a name="general"></a>Umum
* Menambahkan kPelengkap Sumber Daya ke banyak cmdlet inti - hal ini memungkinkan Anda untuk menandai nama sumber daya yang ada saat memanggil cmdlet secara interaktif

#### <a name="azprofile"></a>Az.Profile
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime
* Mengganti nama param TenantId di cmdlet Connect-AzAccount ke Penyewa dan menambahkan alias untuk TenantId
* Memperbarui deskripsi TenantId untuk Connect-AzAccount
* Memperbaiki pesan kesalahan untuk login yang gagal saat menyediakan domain penyewa
    - https://github.com/Azure/azure-powershell/issues/6936
* Memperbaiki masalah dengan nama konteks yang berbenturan untuk akun tanpa langganan di penyewa
    - https://github.com/Azure/azure-powershell/issues/7453
* Memperbaiki masalah titik akhir DataLake saat menggunakan MSI
    - https://github.com/Azure/azure-powershell/issues/7462
* Memperbaiki masalah ketika 'Disconnect-AzAccount' dikeluarkan jika tidak terhubung
    - https://github.com/Azure/azure-powershell/issues/7167

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan operasi Get-AzCognitiveServicesAccountSkus.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet Add-AzVmssVMDataDisk dan Remove-AzVmssVMDataDisk
* Get-AzVMImage menunjukkan AutomaticOSUpgradeProperties
* Memperbaiki nilai opsi SetAzVMChefExtension -BootstrapOptions dan -JsonAttribute yang tidak diatur dalam format json.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui paket DataLake ke 1.1.10.
* Menambahkan Konkurensi default ke operasi multialur.

#### <a name="azinsights"></a>Az.Insights
* Memperbaiki masalah #7267 (Area skala otomatis)
    - Masalah pembuatan aturan skala otomatis baru yang tidak mengatur parameter yang dienumerasi dengan benar (akan selalu diatur ke nilai default).
* Memperbaiki masalah #7513 [Insights] Set-AzDiagnosticSetting memerlukan spesifikasi kategori eksplisit selama pembuatan pengaturan
    - Sekarang cmdlet tidak memerlukan indikasi eksplisit pada kategori agar aktif selama pembuatan, yaitu berfungsi saat didokumentasikan

#### <a name="aznetwork"></a>Az.Network
* Mengubah PeeringType menjadi parameter wajib untuk cmdlet berikut: -
    - Get-AzExpressRouteCircuitRouteTable
    - Get-AzExpressRouteCircuitARPTable
    - Get-AzExpressRouteCircuitRouteTableSummary
    - Get-AzExpressRouteCrossConnectionArpTable
    - Get-AzExpressRouteCrossConnectionRouteTable
    - Get-AzExpressRouteCrossConnectionRouteTableSummary

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan cmdlet remediasi kebijakan

#### <a name="azresources"></a>Az.Resources
* Memperbaiki https://github.com/Azure/azure-powershell/issues/7402
    - Mengizinkan daftar sumber daya menggunakan parameter '-ResourceId' untuk 'Get-AzResource'

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan properti baca-saja MigrationState ke PSServiceBusMigrationConfigurationAttributes yang akan membantu mengetahui status Migrasi.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki penambahan sertifikat ke Linux Vmss.
* Memperbaiki 'Add-AzServiceFabricClusterCertificate'
    - Menggunakan thumbprint yang benar dari sertifikat baru (Azure/service-fabric-issues#932).
    - Menampilkan pengecualian dengan benar (Azure/service-fabric-issues#1054).
* Memperbaiki 'Update-AzServiceFabricDurability' untuk memperbarui konfigurasi kluster sebelum memulai operasi Vmss CreateOrUpdate.

## <a name="040---october-2018"></a>0.4.0 - Oktober 2018
#### <a name="azprofile"></a>Az.Profile
* Memperbaiki masalah Get-AzSubscription di CloudShell
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azcompute"></a>Az.Compute
* Menambahkan ukuran baru ke daftar yang memungkinkan ukuran mesin virtual untuk mengaktifkan jaringan yang dipercepat saat menggunakan set param sederhana untuk 'New-AzVm'
* Menambahkan pelengkap argumen ResourceName ke semua cmdlet.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan dukungan untuk Aturan Virtual Network
    - Get-AzDataLakeStoreVirtualNetworkRule: Mendapat atau Mencantumkan aturan jaringan virtual Azure Data Lake Store.
    - Add-AzDataLakeStoreVirtualNetworkRule: Menambahkan aturan jaringan virtual ke akun Data Lake Store yang ditentukan.
    - Set-AzDataLakeStoreVirtualNetworkRule: Mengubah aturan jaringan virtual yang ditentukan di akun Data Lake Store yang ditentukan.
    - Remove-AzDataLakeStoreVirtualNetworkRule: Menghapus aturan jaringan virtual Azure Data Lake Store.

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet Test-AzNetworkWatcherConnectivity, meneruskan nilai protokol ke backend.
* Menambahkan pelengkap argumen ResourceName ke semua cmdlet.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah ketika Get-AzRoleDefinition memberikan pengecualian yang tidak dapat dipahami (ketika profil default tidak memiliki langganan di dalamnya dan tidak ada cakupan yang ditentukan) dengan menambahkan pengecualian yang berarti dalam skenario. Juga mengatur param default ke 'RoleDefinitionNameParameterSet'.

## <a name="030---october-2018"></a>0.3.0 - Oktober 2018
#### <a name="azurestorage"></a>Azure.Storage
* Memperbaiki Copy Blob/File yang tidak menyalin metadata saat tujuan mengalami masalah metadata
    - Start-AzureStorageBlobCopy
    - Start-AzureStorageFileCopy
* Mendukung get penggunaan sumber daya Penyimpanan dari lokasi tertentu, dan menambahkan pesan peringatan karena get penggunaan sumber daya Penyimpanan global sudah usang.
    - Get-AzStorageUsage

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung Get-AzCognitiveServicesAccountSkus tanpa akun yang ada.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki `<rg>` Get-AzVM -ResourceGroupName untuk memunculkan lebih dari 50 hasil jika diperlukan
* Menambahkan contoh 'SimpleParameterSet' ke bantuan cmdlet New-AzVmss.
* Memperbaiki kesalahan ketik di pesan progres Azure Disk Encryption

#### <a name="azdatafactoryv2"></a>Az.DataFactoryV2
* Memperbarui versi SDK .Net ADF ke 2.3.0.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan fungsionalitas NetworkProfile. cmdlet baru ditambahkan
    - Get-AzNetworkProfile
    - New-AzNetworkProfile
    - Remove-AzNetworkProfile
    - Set-AzNetworkProfile
    - New-AzContainerNicConfig
    - New-AzContainerNicConfigIpConfig
* Menambahkan link asosiasi layanan pada Model Subnet
* Menambahkan cmdlet New-AzVirtualNetworkTap, Get-AzVirtualNetworkTap, Set-AzVirtualNetworkTap, Remove-AzVirtualNetworkTap
* Menambahkan cmdlet Set-AzNEtworkInterfaceTapConfig, Get-AzNEtworkInterfaceTapConfig, Remove-AzNEtworkInterfaceTapConfig

#### <a name="azrediscache"></a>Az.RedisCache
* Mengizinkan string apa pun sebagai parameter Size seterusnya. Menambahkan P5 di popup PSArgumentCompleter

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter -Mode yang hilang ke Set-AzPolicyDefinition
* Memperbaiki bug commandlet Get-AzProviderOperation untuk operasi dengan Asal yang berisi Pengguna

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah ketika beberapa cmdlet cadangan tidak akan mengenali langganan azure saat ini

#### <a name="azwebsites"></a>Az.Websites
* Cmdlet baru Get-AzWebAppContainerContinuousDeploymentUrl - Mendapatkan URL Webhook Penyebaran Berkelanjutan Kontainer
* Cmdlet baru New-AzWebAppContainerPSSession dan Enter-WebAppContainerPSSession - Memulai sesi jarak jauh PowerShell ke dalam aplikasi kontainer windows

## <a name="020---september-2018"></a>0.2.0 - September 2018
 Rilis Awal