---
description: Pelajari semua pembaruan terbaru untuk modul Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 05/24/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Catatan rilis Azure PowerShell
ms.openlocfilehash: 1e84aecd4e3977518d1a6c1d84eeb2f9cdd4266c
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146607269"
---
# <a name="azure-powershell-release-notes"></a>Catatan rilis Azure PowerShell
## <a name="800---may-2022"></a>8.0.0 - Mei 2022
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan fitur pratinjau yang memungkinkan pengguna mengontrol konfigurasi berikut dengan menggunakan 'Get-AzConfig', 'Update-AzConfig' dan 'Clear-AzConfig':
    - 'DefaultSubscriptionForLogin': Nama langganan atau GUID. Mengatur konteks default untuk Azure PowerShell saat masuk tanpa menentukan langganan.
    - 'DisplayBreakingChangeWarning': Mengontrol apakah pesan peringatan untuk melanggar perubahan ditampilkan atau ditekan.
    - 'EnableDataCollection': Saat diaktifkan, Azure PowerShell cmdlet mengirim data telemetri ke Microsoft untuk meningkatkan pengalaman pelanggan.
* System.Reflection.DispatchProxy yang ditingkatkan pada Windows PowerShell [#17856]
* Azure.Identity yang ditingkatkan ke 1.6.0 dan Azure.Core ke 1.24.0

#### <a name="azaks"></a>Az.Aks
* Menghapus alias ini:
  * 'Get-AzAks'
  * 'New-AzAks'
  * 'Set-AzAks'
  * 'Remove-AzAks'

#### <a name="azapimanagement"></a>Az.ApiManagement
* [Melanggar perubahan] Mengganti parameter 'Sampel' dengan 'Contoh' di 'New-AzApiManagementOperation' dan 'Set-AzApiManagementOperation'
* ApiM .Net SDK yang diperbarui ke versi 8.0.0 / Api Versi 2021-08-01

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Versi API yang ditingkatkan untuk komponen ApplicationInsights ke 2020-02-02
* Komponen berbasis ruang kerja Log Analytics yang didukung oleh 'New-AzApplicationInsights' dan 'Update-AzApplicationInsights'

#### <a name="azcdn"></a>Az.Cdn
* Versi API yang ditingkatkan ke 2021-06-01
* Cmdlet yang tidak digunakan lagi dihapus
  - Disable-AzCdnCustomDomain
  - Enable-AzCdnCustomDomain
  - Get-AzCdnEdgeNodes
  - Get-AzCdnProfileSsoUrl
  - New-AzCdnDeliveryPolicy
  - Set-AzFrontDoorCdnSecret
* Menambahkan cmdlet baru
  - Clear-AzFrontDoorCdnEndpointContent
  - Get-AzFrontDoorCdnEndpointResourceUsage
  - Get-AzFrontDoorCdnOriginGroupResourceUsage
  - Get-AzFrontDoorCdnProfileResourceUsage
  - Get-AzFrontDoorCdnRuleSetResourceUsage
  - Test-AzFrontDoorCdnEndpointCustomDomain
  - Test-AzFrontDoorCdnEndpointNameAvailability
  - Test-AzFrontDoorCdnProfileHostNameAvailability
  - Update-AzFrontDoorCdnCustomDomainValidationToken
  - Update-AzFrontDoorCdnRule
* Cmdlet Set berganti nama menjadi Cmdlet Pembaruan
* Menambahkan akhiran 'Objek' ke cmdlet pembuatan objek memori

#### <a name="azcompute"></a>Az.Compute
* Logika internal cmdlet 'New-AzVm' yang diedit untuk menggunakan nilai 'PlatformFaultDomain' di objek 'PSVirtualMachine' yang diteruskan ke objek tersebut di komputer virtual baru.
* Menambahkan cmdlet baru bernama 'Restart-AzHost' untuk memulai ulang host khusus.
* Menambahkan parameter '-DataAccessAuthMode' ke cmdlet berikut:
    - 'New-AzDiskConfig'
    - 'New-AzDiskUpdateConfig'
    - 'New-AzSnapshotConfig'
    - 'New-AzSnapshotUpdateConfig'
* Menambahkan parameter '-Architecture' ke cmdlet berikut:
    - 'New-AzDiskConfig'
    - 'New-AzDiskUpdateConfig'
    - 'New-AzSnapshotConfig'
    - 'New-AzSnapshotUpdateConfig'
    - 'New-AzGalleryImageDefinition'
* Menambahkan parameter '-InstanceView' ke 'Get-AzRestorePoint'
* Menambahkan parameter '-ScriptString' ke 'Invoke-AzvmRunCommand' dan 'Invoke-AzvmssRunCommand'
* Menambahkan parameter '-ScaleInPolicyForceDeletion' ke 'Update-Azvmss'

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Jenis parameter yang diperbarui dari bool ke bool? untuk 'Update-AzContainerRegistryRepository' [#17857]
    - 'ReadEnabled'
    - 'ListEnabled'
    - 'WriteEnabled'
    - 'DeleteEnabled'

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan dukungan untuk membuat kontainer dengan Kebijakan Enkripsi Klien. Versi Kebijakan Enkripsi Klien yang didukung saat ini adalah 1.

#### <a name="azdatafactory"></a>Az.DataFactory
* Versi ADF .Net SDK yang diperbarui ke 6.1.0
* Memperbaiki Set-AzDataFactoryV2 -InputObject tidak benar dengan Parameter PublicNetworkAccess

#### <a name="azeventhub"></a>Az.EventHub
* Membuat 'IPRule' dan 'VirtualNetworkRule' opsional di 'Set-AzEventHubNetworkRuleSet'.
* Properti MSI lama yang tidak digunakan lagi di 'Set-AzEventHubNamespace' dan 'New-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Memperbaiki masalah yang New-AzFunctionApp cmdlet harus menulis pesan peringatan saat mengatur nilai default untuk parameter yang tidak disediakan.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Modul yang dimigrasikan ke basis kode yang dihasilkan.
* Cmdlet yang ditambahkan:
    - Baru/Dapatkan/Perbarui/Hapus-AzHealthcareApisService
    - Baru/Dapatkan/Perbarui/Hapus-AzHealthcareApisWorkspace
    - Baru/Dapatkan/Perbarui/Hapus-AzHealthcareFhirService
    - Baru/Dapatkan/Perbarui/Hapus-AzHealthcareDicomService
    - Baru/Dapatkan/Perbarui/Remove-AzHealthcareIoTConnector
    - Baru/Dapatkan/Hapus-AzHealthcareIotConnectorFhirDestination
    - Get-AzHealthcareFhirDestination

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan 'Putar' ke dalam daftar izin ke kunci [#17970]

#### <a name="azmanagedserviceidentity"></a>Az.ManagedServiceIdentity
* Ketersediaan umum 'Az.ManagedServiceIdentity'

#### <a name="aznetwork"></a>Az.Network
* Didukung 'Microsoft.Network/privateLinkServices' di 'Get-AzPrivateEndpointConnection' [#16984].
* Pesan ramah yang disediakan jika jenis sumber daya tidak didukung untuk fitur koneksi titik akhir privat [#17091].
* Menambahkan 'DisableIPsecProtection' ke 'Virtual Network Gateway'.
* Menambahkan cmdlet baru untuk membuat/mengelola objek otorisasi untuk ExpressRoutePort:
    - 'Add-AzExpressRoutePortAuthorization'
    - 'Get-AzExpressRoutePortAuthorization'
    - 'Remove-AzExpressRoutePortAuthorization'
* Menambahkan parameter opsi 'AuthorizationKey' ke cmdlet 'New-AzExpressRouteCircuit' untuk memungkinkan pembuatan Sirkuit ExpressRoute pada ExpressRoutePort dengan pemilik yang berbeda.
* Perbaiki bug yang tidak dapat menampilkan CustomIpPrefix di PublicIpPrefix.
* Cmdlet yang diperbarui untuk menambahkan properti baru 'HubRoutingPreference' di VirtualHub dan mengatur properti 'PreferredRoutingGateway' tidak digunakan lagi.
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Menambahkan parameter opsional 'AuxiliaryMode' ke cmdlet 'New-AzNetworkInterface' untuk mengaktifkan antarmuka jaringan ini saat Sirius diaktifkan. Nilai yang diizinkan adalah None(default) dan MaxConnections.
* Perubahan fitur multipool: Cmdlet yang diperbarui untuk menambahkan properti opsional baru: objek 'ConfigurationPolicyGroups' untuk mengaitkan grup kebijakan.
    - 'Update-AzVpnServerConfiguration'
    - 'New-AzVpnServerConfiguration'
* Perubahan fitur multipool: Cmdlet yang diperbarui untuk menambahkan properti opsional baru: objek 'P2SConnectionConfiguration' untuk menentukan beberapa konfigurasi Koneksi.
    - 'Update-AzP2sVpnGateway'
    - 'New-AzP2sVpnGateway'
* Perubahan fitur multipool: Menambahkan cmdlet baru untuk mendukung CRUD grup kebijakan Konfigurasi untuk VpnServerConfiguration.
    - 'Get-AzVpnServerConfigurationPolicyGroup'
    - 'New-AzVpnServerConfigurationPolicyGroup'
    - 'Update-AzVpnServerConfigurationPolicyGroup'
    - 'Remove-AzVpnServerConfigurationPolicyGroup'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan dukungan untuk otorisasi Multi-pengguna menggunakan Resource Guard untuk vault layanan pemulihan.
* Menambahkan dukungan untuk pemulihan lintas langganan untuk vault layanan pemulihan, akun penyimpanan yang dimodifikasi untuk diambil dari langganan target.

#### <a name="azresources"></a>Az.Resources
* Menambahkan cmdlet untuk kredensial identitas federasi aplikasi
    - 'Get-AzADAppFederatedIdentityCredential'
    - 'New-AzADAppFederatedIdentityCredential'
    - 'Remove-AzADAppFederatedIdentityCredential'
    - 'Update-AzADAppFederatedIdentityCredential'
* Cmdlet 'Get-AzLocation' yang ditingkatkan dan direvisi:
    - Peningkatan 'subscriptionClient' untuk 'Get-AzLocation'. Mengubah apiVersion-nya dari 2016-01-01 menjadi 2021-01-01. [#18002]
    - Menambahkan semua atribut info lokasi untuk 'Get-AzLocation', termasuk 'pairedRegion' dan sebagainya. [#18045] [#17536]
    - Dukungan ExtendedLocations oleh 'Get-AzLocation' [#18046]
* Menambahkan cmdlet berikut agar tetap seimbang dengan versi API 2021-04-01:
    - 'New-AzHierarchySetting'
    - 'Get-AzHierarchySetting'
    - 'Update-AzHierarchySetting'
    - 'Remove-AzHierarchySetting'
    - 'Get-AzManagementGroupSubscription'
    - 'Get-AzSubscriptionUnderManagementGroup'
    - 'Start-AzTenantBackfill'
    - 'Get-AzTenantBackfillStatus'
    - 'Get-AzManagementGroupNameAvailability'
    - 'Get-AzEntity'
* [Melanggar Perubahan] Mengganti nama properti `isSyncedFromOnPremis` menjadi `isSyncedFromOnPremise` selaras dengan spesifikasi API

#### <a name="azsecurity"></a>Az.Security
* Menambahkan cmdlet baru: 'Get-AzSecuritySolution'
* Menambahkan Aturan Supresi Pemberitahuan ke cmdlet: 'Get-AlertsSuppressionRule' 'Remove-AlertsSuppressionRule' 'Set-AlertsSuppressionRule' 'New-AzAlertsSuppressionRuleScope'

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki kesalahan ketik seperangkat aturan jaringan lain-lain di seluruh modul.
* Tambahkan 'TrustedServiceAccessEnabled' ke 'Set-AzServiceBusNetworkRuleSet'

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet baru 'Get-AzSqlInstanceEndpointCertificate'
* Menambahkan parameter 'HighAvailabilityReplicaCount' ke 'New-AzSqlElasticPool' dan 'Set-AzSqlElasticPool'

#### <a name="azstorage"></a>Az.Storage
* Didukung menghasilkan token Sas untuk DataLakeGen2
    -  'New-AzDataLakeGen2SasToken'
* Menampilkan token OAuth hanya dalam log debug dalam build debug
    -  'New-AzStorageContext'
* Didukung mengembalikan lebih banyak properti file saat mencantumkan file Azure
    -  'Get-AzStorageFile'

#### <a name="azsynapse"></a>Az.Synapse
* Menambahkan dukungan untuk Synapse Link untuk Azure Sql Database
    - Menambahkan cmdlet 'Get-AzSynapseLinkConnection'
    - Menambahkan cmdlet 'Get-AzSynapseLinkConnectionDetailedStatus'
    - Menambahkan cmdlet 'Set-AzSynapseLinkConnection'
    - Menambahkan cmdlet 'Remove-AzSynapseLinkConnection'
    - Menambahkan cmdlet 'Start-AzSynapseLinkConnection'
    - Menambahkan cmdlet 'Stop-AzSynapseLinkConnection'
    - Menambahkan cmdlet 'Set-AzSynapseLinkConnectionLinkTable'
    - Menambahkan cmdlet 'Get-AzSynapseLinkConnectionLinkTable'
    - Menambahkan cmdlet 'Get-AzSynapseLinkConnectionLinkTableStatus'
    - Menambahkan cmdlet 'Update-AzSynapseLinkConnectionLandingZoneCredential'
* Atur 'UploadedTimestamp' saat menambahkan paket ke kumpulan spark dengan 'Update-AzSynapseSparkPool'

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'Get-AzWebApp' dan 'Get-AzWebAppSlot' untuk mengekspos properti 'VirtualNetworkSubnetId' [#18042]

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @bb-froggy, Memperbaiki tautan mati ke Gambaran Umum DCR (#17998)
* Darryl van der Peijl (@DarrylvanderPeijl), Mengubah lokal ke lokal (#17974)
* Hiroshi Yoshioka (@hyoshioka0128), Kesalahan Ketik "Github Actions"→"GitHub Actions" (#18160)
* @misbamustaqim, Menambahkan DisableIPsecProtection check(bool) ke gateway Virtual Network (#18029)
* Scott Tang (@scottwtang), Perbarui dokumentasi untuk cmdlet Get-AzApiManagementSubscription (#18027)
* @SnehaSudhirG, Perbarui Get-AzAutomationScheduledRunbook.md (#18059)

## <a name="750---april-2022"></a>7.5.0 - April 2022
#### <a name="azaccounts"></a>Az.Accounts
* Microsoft.Rest.ClientRuntime yang ditingkatkan ke 2.3.24

#### <a name="azaks"></a>Az.Aks
* Memperbarui deskripsi 'Force' di 'Invoke-AzAksRunCommand' [#17756]
* Memperbaiki masalah bahwa 'identitas' tidak dapat disalurkan ke dalam 'Set-AzAksCluster' [#17376]

#### <a name="azapimanagement"></a>Az.ApiManagement
Menambahkan pesan peringatan untuk perubahan yang melanggar mendatang.

#### <a name="azbatch"></a>Az.Batch
* Az.Batch yang diperbarui untuk menggunakan SDK 'Microsoft.Azure.Batch' versi 15.3.0
  - Tambahkan kemampuan untuk menetapkan identitas terkelola yang ditetapkan pengguna ke 'PSCloudPool'. Identitas ini akan tersedia pada setiap simpul di kumpulan, dan dapat digunakan untuk mengakses berbagai sumber daya.
  - Menambahkan properti 'IdentityReference' ke model berikut untuk mendukung akses sumber daya melalui identitas terkelola:
    - 'PSAzureBlobFileSystemConfiguration'
    - 'PSOutputFileBlobContainerDestination'
    - 'PSContainerRegistry'
    - 'PSResourceFile'
    - 'PSUploadBatchServiceLogsConfiguration'
  - Menambahkan properti 'ekstensi' baru ke 'PSVirtualMachineConfiguration' di 'PSCloudPool' untuk menentukan ekstensi komputer virtual untuk simpul
  - Menambahkan kemampuan untuk menentukan zona ketersediaan menggunakan properti baru 'NodePlacementConfiguration' di 'VirtualMachineConfiguration'
  - Menambahkan properti 'OSDisk' baru ke 'VirtualMachineConfiguration', yang berisi pengaturan untuk disk sistem operasi Komputer Virtual.
    - Properti 'Penempatan' pada 'PSDiffDiskSettings' menentukan penempatan disk ephemeral untuk disk sistem operasi untuk semua VM di kumpulan. Mengaturnya ke 'CacheDisk' akan menyimpan disk OS sementara pada cache VM.
  - Menambahkan properti 'MaxParallelTasks' di 'PSCloudJob' untuk mengontrol tugas maksimum yang diizinkan per pekerjaan (default ke -1, yang berarti tidak terbatas).
  - Menambahkan properti 'VirtualMachineInfo' pada 'PSComputeNode' yang berisi informasi tentang status komputer virtual saat ini, termasuk versi gambar marketplace yang tepat yang digunakan VM.
  - Menambahkan properti 'RecurrenceInterval' ke 'PSSchedule' untuk mengontrol interval antara waktu mulai dua pekerjaan berturut-turut di bawah jadwal pekerjaan.
  - Menambahkan perintah 'Get-AzBatchComputeNodeExtension' baru, yang mendapatkan ekstensi tertentu berdasarkan nama, atau daftar semua ekstensi, untuk simpul komputasi tertentu.
* SDK Az.Batch'Microsoft.Azure.Management.Batch' versi 14.0.0 yang diperbarui.
  - Menambahkan perintah 'Get-AzBatchSupportedVirtualMachineSku' baru, yang mendapatkan daftar ukuran VM Komputer Virtual yang didukung Batch yang tersedia di lokasi tertentu.
  - Menambahkan perintah 'Get-AzBatchTaskSlotCount' baru, yang mendapatkan jumlah slot tugas yang diperlukan oleh pekerjaan tertentu.
  - 'MaxTasksPerComputeNode' telah diganti namanya menjadi 'TaskSlotsPerNode', agar sesuai dengan perubahan fungsionalitas.
    - 'MaxTasksPerComputeNode' akan tetap sebagai alias tetapi akan dihapus dalam pembaruan mendatang.

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan pesan perubahan yang melanggar untuk semua cmdlet dalam modul Az.CDN

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* PowerShell CognitiveServices yang diperbarui untuk menggunakan versi 2022-03-01.
* Menambahkan cmdlet 'Get-AzCognitiveServicesAccountModel'.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-ImageReferenceId' ke cmdlet berikut: 'New-AzVm', 'New-AzVmConfig', 'New-AzVmss', 'Set-AzVmssStorageProfile'
* Menambahkan fungsionalitas untuk referensi gambar lintas penyewa untuk pembuatan VM, VMSS, Disk Terkelola, dan Versi Gambar Galeri.
* 'New-AzGallery' dapat mengambil parameter '-Permission' untuk mengatur properti sharingProfile-nya.
* 'Update-AzGallery' dapat memperbarui sharingProfile.
* 'Get-AzGallery' dapat mengambil parameter '-Expand' untuk tampilan sumber daya yang diperluas.
* Parameter baru diatur untuk cmdlet berikut untuk mendukung berbagi langsung Shared Image Gallery
    - Get-AzGallery
    - Get-AzGalleryImageDefinition
    - Get-AzGalleryImageVersion
* Updates dan penyempurnaan 'Add-AzVhd'
    - Menambahkan parameter '-DiskHyperVGeneration' dan '-DiskOsType' ke set parameter DirectUploadToManagedDisk untuk diunggah ke pengaturan disk terkelola yang lebih kuat.
    - Memperbarui fungsi output kemajuan sehingga berfungsi dengan file VHD dengan karakter '&' dalam namanya.
    - Diperbarui sehingga mengunggah file VHD berukuran dinamis dikonversi ke ukuran tetap selama pengunggahan.
    - Memperbaiki bug dalam mengunggah disk yang berbeda.
    - Hapus file VHD yang dikonversi/diubah ukurannya secara otomatis setelah diunggah.
    - Memperbaiki bug yang menunjukkan parameter '-ResourceGroupName' sebagai opsional ketika benar-benar wajib.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Volume direktori kosong dan volume rahasia yang didukung untuk membuat grup kontainer [#17410]

#### <a name="azdatafactory"></a>Az.DataFactory
* Versi ADF .Net SDK yang diperbarui ke 6.0.0

#### <a name="azeventhub"></a>Az.EventHub
* Menghentikan penggunaan bidang terkait MSI yang lebih lama di New-AzEventHubNamespace dan Set-AzEventHubNamespace

#### <a name="azkeyvault"></a>Az.KeyVault
* Didukung untuk mendapatkan angka acak dari HSM terkelola oleh 'Get-AzKeyVaultRandomNumber'
* Melewati validasi status koneksi langganan untuk Az.KeyVault.Extension [#17712]
* Mengaktifkan pengaturan akses jaringan publik

#### <a name="azkusto"></a>Az.Kusto
* Sumber daya skrip sebaris yang didukung (pembuatan skrip dengan konten alih-alih token sas)
* Menambahkan dukungan identitas terkelola ke EventGrid
* Menambahkan databaseRouting (Tunggal/Multi) ke semua koneksi data
* Menambahkan PublicIPType ke kluster

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki 'ArgumentNullException' di 'Add-AzureRmRouteConfig' saat 'RouteTable.Routes' null.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan dukungan untuk beberapa pencadangan per hari (per jam) Kebijakan yang ditingkatkan untuk workloadType AzureVM.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki tanda kutip redundan dalam daftar penomoran halaman [#17667]
* Menambahkan cmdlet 'Update-AzADGroup' [#17514]
* Versi API yang diperbarui menjadi beta untuk cmdlet terkait anggota grup untuk memungkinkan perwakilan layanan ditambahkan, mendapatkan, dan menghapus dari grup [#16698]
* Menambahkan parameter '-OwnedApplication' untuk 'Get-AzADApplication' untuk mendapatkan aplikasi yang dimiliki oleh pengguna saat ini
* Menambahkan parameter '-Web' untuk 'Update-AzADApplication' [#16750]

#### <a name="azsecurity"></a>Az.Security
* Menambahkan cmdlet baru untuk API Automations keamanan

#### <a name="azstackhci"></a>Az.StackHCI
* Aturan firewall yang diperbarui untuk jaringan Pengesahan untuk memblokir semua lalu lintas lainnya
* Kluster yang diperbarui untuk mengabaikan jaringan Pengesahan

#### <a name="azstorage"></a>Az.Storage
* DaysAfterLastTierChangeGreaterThan yang Didukung dalam Kebijakan Manajemen
    -  'Add-AzStorageAccountManagementPolicyAction'
* Memperbaiki masalah yang mungkin gagal mengunggah blob di Linux [#17743]
    -  'Set-AzStorageBlobContent'
* AllowPermanentDelete yang didukung saat mengaktifkan penghapusan sementara blob
    - 'Enable-AzStorageBlobDeleteRetentionPolicy'
* Menambahkan pesan peringatan perubahan berisiko untuk perubahan berisiko cmdlet yang akan datang
    - 'Get-AzStorageFile'

#### <a name="azsynapse"></a>Az.Synapse
* Menambahkan dukungan untuk autentikasi khusus Synapse Azure Active Directory (Azure AD)
    - Menambahkan cmdlet 'Get-AzSynapseActiveDirectoryOnlyAuthentication'
    - Menambahkan cmdlet 'Enable-AzSynapseActiveDirectoryOnlyAuthentication'
    - Menambahkan cmdlet 'Disable-AzSynapseActiveDirectoryOnlyAuthentication'

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'New-AzWebAppContainerPSSession' dengan Atribut CmdletDeprecation [#16646]
* Memperbarui 'Restore-AzDeletedWebApp' untuk memperbaiki masalah yang mencegah cmdlet bekerja pada host dengan lokal adalah sesuatu yang berbeda dari 'en-US'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Aleksandar Nikolić (@alexandair), Perbaiki properti UniqueName dalam contoh (#17826)
* @enevoj, Masalah penyajian markup? (#17732)
* @jeremytanyz, Perbarui Set-AzStorageFileContent.md (#17805)
* Martin Bentancour (@mbentancour), Memperbaiki masalah DateTime memulihkan aplikasi web yang dihapus (#16308)
* Preben Huybrechts (@pregress), Lakukan pemeriksaan null sebelum mengaksesnya (#16552)
* Ryan Buckman (@ryan-buckman), perbarui contoh 1 deskripsi perintah agar sesuai dengan arg ApiRevision dalam sampel kode (#17741)

## <a name="740---april-2022"></a>7.4.0 - April 2022
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan 'SshCredentialFactory' untuk mendukung mendapatkan kredensial ssh vm dari msal.
* Memperbaiki bug cmdlet gagal ketika -DefaultProfile diatur ke konteks masuk perwakilan layanan. [#16617]
* Memperbaiki masalah bahwa otorisasi tidak berfungsi di lingkungan Dogfood

#### <a name="azappconfiguration"></a>Az.AppConfiguration
* Menambahkan parameter 'PublicNetworkAccess' di 'New-AzAppConfigurationStore' dan 'Update-AzAppConfigurationStore'

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan peringatan perubahan yang melanggar untuk Az.ApplicationInsights 2.0.0 mendatang

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan pesan perubahan yang melanggar untuk rilis perubahan yang melanggar versi 2.0.0 yang akan datang

#### <a name="azcompute"></a>Az.Compute
* Memperbarui 'New-AzVM' untuk membuat akun penyimpanan baru untuk diagnostik boot jika tidak ada. Ini akan mencegah cmdlet menggunakan akun penyimpanan acak di langganan saat ini untuk digunakan untuk diagnostik boot.
* Menambahkan parameter string 'AutomaticRepairAction' ke cmdlet 'New-AzVmssConfig' dan 'Update-AzVmss'.
* Memperbarui 'Get-AzVm' untuk menyertakan kumpulan parameter 'GetVirtualMachineById'.
* Mengedit dokumentasi untuk cmdlet 'Set-AzVMADDomainExtension' untuk memastikan contohnya akurat.
* Deskripsi dan contoh yang disempurnakan untuk pembuatan disk.
* Menambahkan parameter baru ke 'New-AzRestorePoint' dan 'New-AzRestorePointCollection' untuk menyalin Titik Pemulihan dan Kumpulan Titik Pemulihan.
* Menambahkan Parameter 'Zone' dan 'PlacementGroupId' ke 'Repair-AzVmssServiceFabricUpdateDomain'.
* Logika 'New-AzVmss' yang diedit untuk memeriksa properti null dengan lebih baik saat parameter 'OrchestrationMode' digunakan.

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan dukungan untuk manajemen sumber daya kunci enkripsi klien yang diperlukan untuk CosmosDB Client-Side Encryption dengan menambahkan dukungan untuk membuat, memperbarui dan mengambil kunci enkripsi klien dengan cmdlet berikut: 'Get-AzCosmosDbClientEncryptionKey', 'New-AzCosmosDbClientEncryptionKey' dan 'Update-AzCosmosDbClientEncryptionKey'

#### <a name="azdatafactory"></a>Az.DataFactory
* Versi ADF .Net SDK yang diperbarui ke 5.4.0

#### <a name="azfunctions"></a>Az.Functions
* Definisi tumpukan PowerShell 7.2 yang diekspos untuk pembuatan aplikasi fungsi hanya di Functions V4

#### <a name="azhdinsight"></a>Az.HDInsight
Rilis ini memigrasikan Microsoft.Azure. Graph SDK ke MicrosoftGraph SDK.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk terus mengunjungi 'NextPageLink' saat mencantumkan brankas kunci dari ARM API

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk mengambil status pengambilan paket bahkan ketika status penyediaan pengambilan paket gagal
    - 'Get-AzNetworkWatcherPacketCapture'
* Menambahkan dukungan untuk menerima sumber daya Vnet, Subnet, dan NIC sebagai TargetResourceId untuk cmdlet berikut
    - 'Set-AzNetworkWatcherFlowLog'
    - 'New-AzNetworkWatcherFlowLog'

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Menghapus validasi kapasitas di cmdlet kluster baru dan memperbarui karena validasi ada di sisi server.
* Pesan kesalahan yang diperluas pada kelas dasar untuk informasi yang diperluas.
* Perbaikan bug - mencegah pengecualian saat menggunakan cmdlet StorageInsight.
* Perbaikan bug - saat memperbarui kluster, SKU diatur meskipun tidak ada nilai yang diteruskan.

#### <a name="azpostgresql"></a>Az.PostgreSql
* Menambahkan parameter PublicNetworkAccess untuk cmdlet terkait server tunggal PostgreSQL [#17263]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan dukungan untuk pencadangan VM Tepercaya dan Kebijakan yang ditingkatkan untuk WorkloadType AzureVM.
* Menambahkan dukungan untuk menonaktifkan fitur keamanan cadangan hibrid di cmdlet 'Set-AzRecoveryServicesVaultProperty'. Fitur ini dapat diaktifkan kembali dengan mengatur bendera 'DisableHybridBackupSecurityFeature' ke False.

#### <a name="azresources"></a>Az.Resources
* Dihapus '-ApplicationId' dari 'New-AzADServicePrincipal' 'SimpleParameterSet' [#17256]
* Menambahkan cmdlet 'New-AzResourceManagementPrivateLink', dan cmdlet 'New-AzPrivateLinkAssociation'
* Menambahkan cmdlet terkait otorisasi:
    - 'Get-AzRoleAssignmentSchedule'
    - 'Get-AzRoleAssignmentScheduleInstance'
    - 'Get-AzRoleAssignmentScheduleRequest'
    - 'Get-AzRoleEligibilitySchedule'
    - 'Get-AzRoleEligibilityScheduleInstance'
    - 'Get-AzRoleEligibilityScheduleRequest'
    - 'Get-AzRoleEligibleChildResource'
    - 'Get-AzRoleManagementPolicy'
    - 'Get-AzRoleManagementPolicyAssignment'
    - 'New-AzRoleAssignmentScheduleRequest'
    - 'New-AzRoleEligibilityScheduleRequest'
    - 'New-AzRoleManagementPolicyAssignment'
    - 'Remove-AzRoleManagementPolicy'
    - 'Remove-AzRoleManagementPolicyAssignment'
    - 'Stop-AzRoleAssignmentScheduleRequest'
    - 'Stop-AzRoleEligibilityScheduleRequest'
    - 'Update-AzRoleManagementPolicy'
* Menambahkan 'Get-AzResourceManagementPrivateLink', 'Remove-AzResourceManagementPrivateLink', cmdlet 'Get-AzResourceManagementPrivateLinkAssociation' dan 'Remove-AzResourceManagementPrivateLinkAssociation'

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki 'New-AzServiceBusAuthorizationRuleSASToken' menampilkan token yang tidak valid. [#12975]

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan dukungan untuk gambar VM Ubuntu 20.04.
    - Ini memungkinkan operasi kluster dengan gambar VM Ubuntu 20.04 menggunakan AZ powershell.

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter 'ServicePrincipalType' ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* [Melanggar perubahan] Dihapus 'Get-AzSqlDatabaseTransparentDataEncryptionActivity'
* Menambahkan properti 'CurrentBackupStorageRedundancy' dan 'RequestedBackupStorageRedundancy' dalam output perintah CRUD Instans Terkelola
* Menambahkan properti opsional 'Tag' ke 'Restore-AzSqlDatabase'
* Menambahkan cmdlet baru untuk mengelola Sertifikat Kepercayaan Server
    - 'New-AzSqlInstanceServerTrustCertificate'
    - 'Get-AzSqlInstanceServerTrustCertificate'
    - 'Remove-AzSqlInstanceServerTrustCertificate'
* Menambahkan cmdlet baru untuk mengelola Managed Instance Link
    - 'New-AzSqlInstanceLink'
    - 'Get-AzSqlInstanceLink'
    - 'Remove-AzSqlInstanceLink'
    - 'Set-AzSqlInstanceLink'
* Menambahkan dukungan untuk operasi pemulihan lintas penyewa dan lintas langganan DataWarehouse ke cmdlet 'Restore-AzSqlDatabase'

#### <a name="azstorage"></a>Az.Storage
* Contoh yang diperbarui dalam dokumentasi referensi untuk 'Close-AzStorageFileHandle'
* Didukung untuk membuat konteks penyimpanan dengan blob, antrean, file, titik akhir layanan tabel yang disesuaikan
    - 'New-AzStorageContext'
* Memperbaiki kegagalan blob salin pada akun Premium Storage, atau namespace hierarkis yang diaktifkan akun
    -  'Copy-AzStorageBlob'
* Didukung membuat token SAS akun, token SAS kontainer, token SAS blob dengan EncryptionScope
    -  'New-AzStorageAccountSASToken'
    -  'New-AzStorageContainerSASToken'
    -  'New-AzStorageBlobSASToken'
* Salinan blob asinkron yang didukung berjalan pada versi API baru
    -  'Start-AzStorageBlobCopy'
* Memperbaiki contoh IpRule dalam bantuan
    -  'Add-AzStorageAccountNetworkRule'
    -  'Remove-AzStorageAccountNetworkRule'
    -  'Update-AzStorageAccountNetworkRuleSet'

#### <a name="azsynapse"></a>Az.Synapse
* Azure.Analytics.Synapse.Artifacts yang ditingkatkan ke 1.0.0-preview.14
* Memperbaiki masalah bahwa cmdlet berikut hanya memperlihatkan 100 entri
    - Cmdlet 'Get-AzSynapseRoleAssignment'
    - Cmdlet 'Get-AzSynapsePipelineRun'
    - Cmdlet 'Get-AzSynapseTriggerRun'
    - Cmdlet 'Get-AzSynapseActivityRun'
* Memperbaiki masalah bahwa seharusnya ada pesan kesalahan saat menghapus alur dependensi

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Set-AzWebAppSlot' untuk mendukung pembaruan versi MinTlsVersion [#17663]
* Memperbaiki 'Set-AzAppServicePlan' untuk menyimpan Tag yang ada saat menambahkan Tag baru
* Memperbaiki 'Set-AzWebApp','Set-AzWebAppSlot', 'Get-AzWebApp' dan 'Get-AzWebAppSlot' untuk mengekspos properti 'VnetRouteAllEnabled' di 'SiteConfig' [#15663]
* Memperbaiki 'Set-AzWebApp', 'Set-AzWebAppSlot', 'Get-AzWebApp' dan 'Get-AzWebAppSlot' untuk mengekspos properti 'HealthCheckPath' di 'SiteConfig' [#16325]
* Memperbaiki masalah konversi DateTime yang disebabkan oleh budaya [#17253]
* Menambahkan dukungan untuk fitur pekerjaan web [#661]
    - Get-AzWebAppContinuousWebJob
    - Get-AzWebAppSlotContinuousWebJob
    - Get-AzWebAppSlotTriggeredWebJob
    - Get-AzWebAppSlotTriggeredWebJobHistory
    - Get-AzWebAppSlotWebJob
    - Get-AzWebAppTriggeredWebJob
    - Get-AzWebAppTriggeredWebJobHistory
    - Get-AzWebAppWebJob
    - Remove-AzWebAppContinuousWebJob
    - Remove-AzWebAppSlotContinuousWebJob
    - Remove-AzWebAppSlotTriggeredWebJob
    - Remove-AzWebAppTriggeredWebJob
    - Start-AzWebAppContinuousWebJob
    - Start-AzWebAppSlotContinuousWebJob
    - Start-AzWebAppSlotTriggeredWebJob
    - Start-AzWebAppTriggeredWebJob
    - Stop-AzWebAppContinuousWebJob
    - Stop-AzWebAppSlotContinuousWebJob

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Axel B. Andersen (@Agazoth)
  * Memperbarui Get-AzADUser.md (#17549)
  * Menambahkan contoh baru (#17535)
* @davidslamb, Perbaiki token SAS yang tidak valid dari New-AzServiceBusAuthorizationRuleSASToken (#17349)
* elle (@elle24), Update Get-AzApplicationGatewayRequestRoutingRule.md (#17405)
* @enevoj, Perbarui Get-AzDataCollectionRule.md (#17586)
* Felipe Guth de Freitas Bergstrom (@guthbergstrom), Update New-AzDatabricksWorkspace.md (#17472)
* @k0rtina, Perbarui Set-AzConsumptionBudget.md (#17355)
* Kanika Gupta (@kangupt), Menambahkan contoh untuk New-AzVM
* Evgeniy Chuvikov (@snofe), Update Update-AzCosmosDBSqlDatabaseThroughput.md

## <a name="732---march-2022"></a>7.3.2 - Maret 2022
#### <a name="azaccounts"></a>Az.Accounts
* Mengubah kerangka kerja target AuthenticationAssemblyLoadContext ke netcoreapp2.1 [#17428]

#### <a name="azcompute"></a>Az.Compute
* Fitur New-AzVM yang diperbarui untuk parameter 'vCPUsAvailable' dan 'vCPUsPerCore'. Cmdlet tidak akan mencoba menggunakan fitur 'VMCustomizationPreview' baru jika pengguna tidak memiliki akses ke fitur tersebut. [#17370]

## <a name="730---march-2022"></a>7.3.0 - Maret 2022
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah bahwa otorisasi tidak berfungsi di lingkungan yang disesuaikan [#17157]
* Mengaktifkan Lanjutkan Evaluasi Akses untuk MSGraph
* Pesan kesalahan yang disempurnakan saat login diblokir oleh AAD
* Pesan kesalahan yang disempurnakan ketika autentikasi ulang senyap gagal
* Loaded System.Private.ServiceModel and System.ServiceModel.Primitives on Windows PowerShell [#17087]

#### <a name="azaks"></a>Az.Aks
* Memperbarui pesan peringatan perubahan yang melanggar [#16805]

#### <a name="azcloudservice"></a>Az.CloudService
* Memperbaiki masalah 'Get-AzCloudServiceNetworkInterface' dan 'Get-AzCloudServicePublicIPAddress'.

#### <a name="azcompute"></a>Az.Compute
* Referensi paket Compute .NET SDK yang ditingkatkan ke versi 52.0.0
* Cmdlet 'New-AzSshKey' yang diperbarui untuk menulis jalur file ke kunci yang dihasilkan ke aliran Peringatan alih-alih konsol.
* Menambahkan parameter bilangan bulat 'vCPUsAvailable' dan 'vCPUsPerCore' ke cmdlet 'New-AzVm', 'New-AzVmConfig', dan 'Update-AzVm'.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbaiki Bug Identitas di ImageRegistryCredential

#### <a name="azdatabricks"></a>Az.Databricks
* Versi API yang ditingkatkan ke pratinjau 2021-04-01

#### <a name="azdatafactory"></a>Az.DataFactory
* Versi ADF .Net SDK yang diperbarui ke 5.2.0

#### <a name="azdatashare"></a>Az.DataShare
* Menambahkan pesan peringatan perubahan yang melanggar karena memperbarui versi API.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan properti MSI ke New-AzEventHubNamespace dan Set-AzEventHubNamespace. Menambahkan New-AzEventHubEncryptionConfig.

#### <a name="azkeyvault"></a>Az.KeyVault
* 'New-AzKeyVaultManagedHsm': didukung yang menentukan berapa lama hsm terkelola yang dihapus dipertahankan oleh 'SoftDeleteRetentionInDays' dan mengaktifkan perlindungan penghapusan menyeluruh oleh 'EnablePurgeProtection'
* 'Update-AzKeyVaultManagedHsm': didukung mengaktifkan perlindungan penghapusan menyeluruh oleh 'EnablePurgeProtection'
* 'Get-AzKeyVaultManagedHsm': Didukung mendapatkan atau mencantumkan HSM terkelola yang dihapus
* 'Remove-AzKeyVaultManagedHsm': Didukung pembersihan HSM terkelola yang dihapus tertentu

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki masalah di mana pengguna tidak dapat mengabaikan pesan peringatan dengan benar setelah mengatur variabel lingkungan [#17013]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan properti baru 'SqlSetting' untuk cmdlet Kebijakan Azure Firewall
    - 'Get-AzFirewallPolicy'
    - 'New-AzFirewallPolicy'
    - 'Set-AzFirewallPolicy'
* Menambahkan baru untuk membuat objek 'SqlSetting' baru untuk membuat Kebijakan Azure Firewall
    - 'New-AzFirewallPolicySqlSetting'
* Menambahkan cmdlet baru untuk mendukung kueri Load Balancer daftar pemetaan port aturan nat masuk untuk alamat backend
    - 'Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping'
    - Cmdlet yang juga diperbarui untuk mendukung konfigurasi aturan nat masuk V2
        - 'New-AzLoadBalancerInboundNatRuleConfig'
        - 'Set-AzLoadBalancerInboundNatRuleConfig'
        - 'Add-AzLoadBalancerInboundNatRuleConfig'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup menambahkan dukungan untuk pengalaman 'Buat komputer virtual baru' dan 'Ganti komputer virtual yang ada' untuk VM Terkelola dalam cmdlet Restore-AzRecoveryServicesBackupItem. Untuk melakukan pemulihan VM ke AlternateLocation, gunakan parameter TargetVMName, TargetVNetName, TargetVNetResourceGroup, TargetSubnetName. Untuk melakukan pemulihan ke VM di OriginalLocation, jangan berikan parameter TargetResourceGroupName dan RestoreAsUnmanagedDisks, lihat contoh untuk detail selengkapnya.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki format kunci keycredential, dari base64url ke byte [#17131]
* Memperbaiki tambahkan kredensial kunci menimpa kredensial yang ada [#17088]
* Set parameter yang dihapus tidak dapat dicapai untuk 'New-AzADSericePrincipal'
* Ditandai 'ObjectType' sebagai 'Unknown' jika objek tidak ditemukan atau akun saat ini tidak memiliki hak istimewa yang cukup untuk mendapatkan tipe objek untuk penetapan peran [#16981]
* Diperbaiki bahwa 'Get-AzRoleAssignment' menunjukkan RoleDefinitionName kosong untuk peran kustom saat tidak menentukan cakupan [#16991]
* Menyatukan 'RoleDefinitionId' yang dikembalikan di PSRoleAssignment ke GUID [#16991]

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan properti identitas dan enkripsi ke New-AzServiceBusNamespace dan Set-AzServiceBusNamespace.
* Menambahkan New-AzServiceBusEncryptionConfig

#### <a name="azstorage"></a>Az.Storage
* Blob unduhan yang didukung dari akun disk terkelola dengan Sas Uri dan token pembawa
    -  'Get-AzStorageBlobContent'
* Akun penyimpanan buat/tingkatkan yang didukung dengan ActiveDirectorySamAccountName dan ActiveDirectoryAccountType
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'

#### <a name="azstoragesync"></a>Az.StorageSync
* Fitur Azure AD yang dimigrasikan di Az.StorageSync ke MSGraph API. Cmdlet akan memanggil MSGraph API sesuai dengan parameter input: New-AzStorageSyncCloudEndpoint
* Mengubah kumpulan parameter default Invoke-AzStorageSyncChangeDetection untuk menggunakan deteksi berbagi penuh

#### <a name="azsynapse"></a>Az.Synapse
* Memperbarui 'Update-AzSynapseSparkPool' untuk mendukung parameter baru [-ForceApplySetting]

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Aleksandar Nikolić (@alexandair)
  * Perbaiki parameter StayProvisioned (#17070)
  * Memperbaiki kesalahan ketik (#17069)
* Joel Greijer (@greijer), Mengklarifikasi kasus khusus pada TemplateParameterUri (#17004)
* Aman Sharma (@HarvestingClouds), Menambahkan Jenis Beban Kerja ke poin agar sesuai dengan nilai yang diterima (#17041)
* @hsrivast, Hsrivastava/breaking change msg (#16985)
* Chris (@isjwuk), Update New-AzAutomationUpdateManagementAzureQuery.md (#16365)
* @MSakssharm, Mengembalikan kesalahan jika izin pengguna yang tidak mencukuum ada untuk GetAgentRegistrationInfo (#16965)
* Emanuel Palm (@PalmEmanuel), New-AzSshKey harus masuk ke aliran Peringatan alih-alih konsol (#16988)
* Pavel Safonov (@PSafonov), Memperbaiki kesalahan ketik dalam deskripsi parameter ManagedResourceGroupName (#17039)
* Michael Arnwine (@vsmike), Update New-AzApplicationGatewayRewriteRuleSet.md Description Text salah (#17102)

## <a name="721---february-2022"></a>7.2.1 - Februari 2022
#### <a name="azresources"></a>Az.Resources
* Diperbaiki `New-AzADServicePrincipal` tidak berfungsi [#17054] [#17040]

## <a name="720---february-2022"></a>7.2.0 - Februari 2022
#### <a name="azaccounts"></a>Az.Accounts
* Menghapus assembly warisan System.Private.ServiceModel dan System.ServiceModel.Primitives [#16063]

#### <a name="azaks"></a>Az.Aks
* Memperbaiki kesalahan pengetikan di 'New-AzAksCluster' [#16733]

#### <a name="azcompute"></a>Az.Compute
* Menghapus properti ProvisioningDetails dari objek PSRestorePoint.
* Memperbarui cmdlet 'Set-AzVmExtension' untuk menampilkan parameter '-Name' dan '-Location' dengan benar sebagai wajib.
* Mengedit contoh kedua 'New-AzVmssConfig' sehingga berhasil berjalan dengan mengubah input Tag ke format yang benar.
* Menambahkan parameter 'Hibernate' ke cmdlet 'Stop-AzVm'.
* Menambahkan parameter 'HibernationEnabled' ke cmdlet 'New-AzVm', 'New-AzVmConfig', dan 'Update-AzVm'.
* Menambahkan parameter 'EnableHotpatching' ke cmdlet 'Set-AzVmssOSProfile'.
* Menambahkan parameter 'ForceDeletion' ke Remove-AzVM dan Remove-AzVMSS.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 5.1.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan akses jaringan publik ke cmdlet set 'Set-AzEventHubNetworkRuleSet'
* Menambahkan 'New-AzEventHubSchemaGroup', 'Remove-AzEventHubSchemaGroup' dan 'Get-AzEventHubSchemaGroup' di PS eventhubs.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Cmdlet HealthcareApis akan meningkatkan versi API yang dapat memperkenalkan perubahan mencolok. Harap hubungi kami untuk informasi selengkapnya.

#### <a name="azkeyvault"></a>Az.KeyVault
* Meningkatkan pesan kesalahan Az.KeyVault.Extension [#16798]
* Menambahkan kebijakan akses default untuk kunci Key Vault sebagai 'All but purge'
* KeyOps yang diserap dari parameter saat mengimpor kunci dari sertifikat pada HSM terkelola [#16773]
* Memperbaiki bug saat memperbarui operasi kunci pada HSM terkelola [#16774]
* Memperbaiki masalah saat mengimpor sertifikat tanpa kata sandi [#16742]

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Menambahkan logika untuk mencegah pengecualian saat menggunakan cmdlet 'StorageInsight'.

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan dukungan untuk properti remediasi baru yang memungkinkan remediasi lebih banyak sumber daya dengan kontrol yang lebih baik atas tingkat remediasi dan penanganan kesalahan
* Menambahkan dukungan untuk mengambil set hasil yang sangat besar menggunakan panggilan API yang dipaginasi secara internal untuk perintah status kebijakan dan peristiwa kebijakan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Mengembalikan batas cadangan konfigurasi per kebijakan untuk VM dari 1000 menjadi 100. Batas ini sebelumnya dilonggarkan, tetapi karena portal Microsoft Azure memiliki batas 100 VM per kebijakan, kami mengembalikan batas ini.
* Menambahkan dukungan untuk beberapa cadangan per hari untuk FileShares.
* Memisahkan beberapa alur CRR dan non-CRR berdasarkan pembaruan SDK.
* Menambahkan parameter EdgeZone ke cmdlet 'New-AzRecoveryServicesAsrRecoveryPlan' Layanan pemulihan situs Azure

#### <a name="azresources"></a>Az.Resources
* Menambahkan properti 'onPremisesLastSyncDateTime', 'onPremisesSyncEnabled' ke objek 'Pengguna' [#16892]
* Menambahkan properti tambahan saat membuat permintaan untuk 'New-AzADServicePrincipal' dan 'Update-AzADServicePrincipal' [#16847] [#16841]
* Memperbaiki 'DisplayName' dan 'ApplicationId' untuk 'New-AzADAppCredential' [#16764]
* Memungkinkan pengaturan ulang kata sandi untuk 'Update-AzADUser' [#16869]
* Memperbarui nama parameter 'EnableAccount' menjadi 'AccountEnabled', dan menambahkan alias 'EnableAccount' untuk 'Update-AzADUser' [#16753] [#16795]
* Memperbaiki 'Set-AzPolicyAssignment' tidak menghapus 'notScope' apabila kosong [#15828]

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan dukungan untuk Mengaktifkan atau Menonaktifkan Akses Jaringan Publik sebagai parameter opsional 'PublicNetworkAccess' ke 'Set-AzServiceBusNetworkRuleSet'
* Memperbaiki 'Set-AzServiceBusNamespace' dengan Tag

#### <a name="azsql"></a>Az.Sql
* Penghentian cmdlet Get-AzSqlDatabaseTransparentDataEncryptionActivity
* Memperbaiki cmdlet untuk Admin Azure Active Directory 'AzureSqlServerActiveDirectoryAdministratorAdapter' dan 'AzureSqlInstanceActiveDirectoryAdministratorAdapter' bermigrasi dari 'AzureEnvironment.Endpoint.AzureEnvironment.Endpoint.Graph' ke 'AzureEnvironment.ExtendedEndpoint.MicrosoftGraphUrl'

#### <a name="azstackhci"></a>Az.StackHCI
* Menambahkan cmdlet dukungan untuk Dukungan Jarak Jauh
    - Cmdlet baru - Install-AzStackHCIRemoteSupport, Remove-AzStackHCIRemoteSupport, Enable-AzStackHCIRemoteSupport, Disable-AzStackHCIRemoteSupport, Get-AzStackHCIRemoteSupportAccess,Get-AzStackHCIRemoteSupportSessionHistory

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah bahwa nomor output di konsol saat memperbarui/menyalin blob terkadang [#16783]
    -  'Set-AzStorageBlobContent'
    -  'Copy-AzStorageBlob'
* Memperbarui file bantuan, menambahkan lebih banyak deskripsi untuk salinan blob asinkron.
    -  'Start-AzStorageBlobCopy'

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Menambahkan dua parameter opsional baru 'MinChildEndpointsIPv4' dan 'MinChildEndpointsIPv6' untuk titik akhir berlapis

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'New-AzAppServicePlan' untuk membuat paket layanan aplikasi dengan id lingkungan host #16094

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @adriancuadrado, Perbarui New-AzADServicePrincipal.md (#16896)
* Alan (@AlanFlorance), Update Get-AzDataLakeGen2ChildItem.md (#16292)
* @geologyrocks, Header duplikat (#16876)
* Hiroshi Yoshioka (@hyoshioka0128), Kesalahan Ketik "Azure CosmosDB"→"Azure Cosmos DB" (#16561)
* Jean-Paul Smit (@jeanpaulsmit), Opsi -Force tidak di dokumentasikan dan tidak diterima sebagai parameter (#16910)
* Kamil Konderak (@kamilkonderak), Deskripsi tetap untuk parameter NodeOsDiskSize (#16716)
* Muralidhar Ranganathan (@rmuralidhar), Mitigasi Get-AzKeyVaultSecret: Parameter AsPlainText Tidak Valid (#16730)
* Ørjan Landgraff (@theorjan), contoh PS yang lebih baik (#16748)
* @ahbleite, Opsi sakelar tidak diperbarui untuk mencerminkan nilai ParameterSetName baru, oleh karena itu $id selalu null. (#16818)

## <a name="710---january-2022"></a>7.1.0 - Januari 2022
#### <a name="azaccounts"></a>Az.Accounts
* Menyalin 'ServicePrincipalSecret' dan 'CertificatePassword' dari profil bawaan Az.Accounts ke profil yang ditetapkan pelanggan. [#16617]
* Memperbarui pesan bantuan dan penurunan harga bantuan untuk parameter 'Tenant' cmdlet 'Set-AzContext'. [#16515]
* Memperbaiki masalah bahwa Azure PowerShell tidak berfungsi dalam alur kerja. [#16408]
* Memperbaiki Versi Api ganda di URI dari permintaan dasar yang dikeluarkan oleh 'Invoke-AzRestMethod'. [#16615]

#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan 'load balancer' dan 'api server access' di 'New-AzAksCluster' dan 'Set-AzAksCluster'. [#16575]

#### <a name="azautomation"></a>Az.Automation
* 'New-AzAutomationSchedule' memungkinkan penentuan StartTime dengan offset.
*  Memperbaiki bug: memperbarui 'Set-AzAutomationModule' untuk menggunakan panggilan PUT saat memperbarui modul dengan versi tertentu   [#12552]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui PowerShell untuk menggunakan versi 2021-10-01.
* Menambahkan cmdlet CommitmentTier dan CommitmentPlan.
* Menambahkan cmdlet Deployment.
* Menambahkan cmdlet 'New-AzCognitiveServicesObject' untuk menghasilkan objek CommitmentPlan/Deployment.

#### <a name="azcompute"></a>Az.Compute
* Memperbarui parameter 'UserData' dalam cmdlet VM dan VMSS untuk menyalurkan berdasarkan Nama Properti untuk memastikan skenario penyaluran terjadi dengan benar.
* Mengubah cmdlet 'New-AzVM' saat menggunakan SimpleParameterSet untuk tidak membuat 'PublicIPAddress' saat nama 'PublicIPAddress' tidak disediakan.
* Menambahkan parameter 'PlatformFaultDomain' ke cmdlet: 'New-AzVM' dan 'New-AzVMConfig'
* Menambahkan parameter '-Feature' untuk 'New-AzGalleryImageDefinition'
* Menambahkan parameter string 'DiffDiskPlacement' ke cmdlet 'Set-AzVmOSDisk' dan 'Set-AzVmssStorageProfile'.

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Mengekspos BackupPolicyMigrationState sebagai bagian dari respons Get-AzCosmosDBAccount.
  - Ini menampilkan status kondisi migrasi kebijakan cadangan ketika akun sedang dikonversi dari mode cadangan berkala menjadi berkelanjutan.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 5.0.0

#### <a name="azfunctions"></a>Az.Functions
* Menghapus pratinjau dari tumpukan PowerShell 7.0 di Linux

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan Cmdlet: 'Invoke-AzKeyVaultKeyRotation', 'Get-AzKeyVaultKeyRotationPolicy' dan 'Set-AzKeyVaultKeyRotationPolicy'

#### <a name="azmysql"></a>Az.MySql
* Ketersediaan umum Az.MySql

#### <a name="aznetwork"></a>Az.Network
* Menggunakan perbandingan tidak peka huruf besar atau kecil untuk ResourceId (Set/New-NetworkWatcherFlowLog)
* Menambahkan properti baru 'ApplicationSecurityGroup', 'IpConfiguration' dan 'CustomNetworkInterfaceName' untuk cmdlet Titik Akhir Privat
    - 'Get-AzPrivateEndpoint'
    - 'New-AzPrivateEndpoint'
* Menambahkan cmdlet baru untuk membuat objek 'IpConfiguration' baru untuk membangun Titik Akhir Privat
    - 'New-AzPrivateEndpointIpConfiguration'
* Menambahkan OrdinalIgnoreCase untuk perbandingan string jenis 'ResourceIdentifier' untuk cmdlet FlowLog
* Memperbaiki kesalahan pengetikan dalam pesan kesalahan 'InvalidWorkspaceResourceId'

#### <a name="azpostgresql"></a>Az.PostgreSql
* Ketersediaan umum Az.PostgreSql

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'IdentityType' dan 'UserAssignedIdentity' di cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'.
    - Ini digunakan untuk menetapkan dan memodifikasi Identitas Azure Cache for Redis.

#### <a name="azresourcemover"></a>Az.ResourceMover
* Menambahkan dukungan untuk Tag di azure resource mover
* Menambahkan dukungan untuk SystemData di azure resource mover
* Merilis api-version 2021-08-01

#### <a name="azresources"></a>Az.Resources
* Memperbaiki alias yang salah untuk 'Get-AzADSpCredential' [#16592]
* Memperbaiki parameter 'ServicePrincipalName' dan 'InputObject' untuk 'Update-AzADServicePrincipal' [#16620]
* Memperbaiki contoh untuk 'New-AzADAppCredential' [#16682]
* Menambahkan parameter 'Web' untuk 'New-AzADApplication' [#16659]
* Menambahkan teks rahasia sebagai respons dari 'New-AzADApplication' dan 'New-AzADServicePrincipal' [#16659]
* Mendeserialisasi 'Value' di 'DeploymentVariable' sebagai array objek jika jenisnya adalah Array [#16523]
* Memperbaiki penggunaan 'SignInName' di 'New-AzRoleAssignment' [#16627]
* Memformat format output 'DeploymentVariable'
* Menghapus filter operasi 'isUser' dari Cmdlet GetAzureProviderOperation

#### <a name="azsignalr"></a>Az.SignalR
* Memperbaiki bug cmdlet 'Update-AzSignalR' yang mengatur ulang status sumber daya secara tidak sengaja.

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter 'ZoneRedundant' ke 'New-AzSqlDatabaseCopy', 'New-AzSqlDatabaseSecondary' dan 'Restore-AzSqlDatabase' untuk mengaktifkan salinan redundan zona, dukungan geo sekunder dan PITR untuk database hyperscale

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki kegagalan blob salin sinkronisasi dengan nama blob tujuan panjang [#16628]
    -  'Copy-AzStorageBlob'
* Konteks penyimpanan oauth AAD yang didukung dalam cmdlet tabel penyimpanan.
    - `Get-AzStorageCORSRule`
    - `Get-AzStorageServiceLoggingProperty`
    - `Get-AzStorageServiceMetricsProperty`
    - `Get-AzStorageServiceProperty`
    - `Get-AzStorageTable`
    - `Get-AzStorageTableStoredAccessPolicy`
    - `New-AzStorageTable`
    - `New-AzStorageTableSASToken`
    - `New-AzStorageTableStoredAccessPolicy`
    - `Remove-AzStorageCORSRule`
    - `Remove-AzStorageTableStoredAccessPolicy`
    - `Set-AzStorageCORSRule`
    - `Set-AzStorageServiceLoggingProperty`
    - `Set-AzStorageServiceMetricsProperty`
    - `Set-AzStorageServiceProperty`
    - `Set-AzStorageTable`
    - `Set-AzStorageTableStoredAccessPolicy`

#### <a name="azsynapse"></a>Az.Synapse
* Ketersediaan umum Az.Synapse
* Memigrasikan fitur Microsoft Azure AD pada Az.Synapse ke MSGraph API. Cmdlet di bawah ini memanggil MSGraph API berdasarkan parameter input:
    - Cmdlet 'New-AzSynapseRoleAssignment'
    - Cmdlet 'Get-AzSynapseRoleAssignment'
    - Cmdlet 'Remove-AzSynapseRoleAssignment'
    - Cmdlet 'Set-AzSynapseSqlActiveDirectoryAdministrator'
* Menambahkan nilai default untuk parameter perintah [-AutoPauseDelayInMinute] 'New-AzSynapseSparkpool' dan 'Update-AzSynapseSparkpool'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @adishiritwick, Memperbarui Set-AzAutomationModule untuk menggunakan panggilan PUT saat memperbarui modul dengan versi tertentu (#16505)
* @anuraj, Memperbarui New-AzWebAppCertificate (#16634)
* @BrajaMS, Memperbarui perintah contoh dengan param NodeType (#16670)
* @geologyrocks, Kesalahan pengetikan principal (sebelumnya princial) (#16699)
* Hen Itzhaki (@HenItzhaki), Menambahkan lebih banyak contoh (#16424)
* Chris (@isjwuk), Peningkatan pemformatan (#15826)
* Jaromir Kaspar (@jaromirk), Menambahkan contoh untuk info masuk kata sandi (#16600 )
* Martin Falkus (@mfalkus), Memperbaiki kesalahan pengetikan pada dokumen Memperbarui Az-Tags di mana "Repalces" ditentukan alih-alih "Replaces" (#16541)
* Radoslav Gatev (@RadoslavGatev), [Az.Accounts] Memperbaiki Versi Api ganda di Uri dari permintaan yang dikeluarkan oleh Invoke-AzRestMethod (#16616)
* @Skuldo, Perbaikan kesalahan pengetikan (#16585)
* Sujit Singh (@sujitks), Memperbarui Set-AzApplicationGatewayFirewallPolicy.md (#16583)
* @trudolf-msft, contoh baru 4/penanganan masalah ( #16437)

## <a name="700---december-2021"></a>7.0.0 - Desember 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menghapus 'ServicePrincipalSecret' dan 'CertificatePassword' di 'PSAzureRmAccount' [#15427]
* Menambahkan parameter opsional 'MicrosoftGraphAccessToken' ke 'Connect-AzAccount'
* Menambahkan parameter opsional 'MicrosoftGraphEndpointResourceId', 'MicrosoftGraphUrl' ke 'Add-AzEnvironment' dan 'Set-AzEnvironment'
* Menambahkan properti '-AccountId' ke set parameter 'UserWithSubscriptionId' 'Connect-AzAccount' yang memungkinkan nama pengguna dipilih di awal untuk proses masuk interaktif
* Menambahkan '-Uri' dan '-ResourceId' ke 'Invoke-AzRestMethod'
* Menambahkan pelengkap otomatis Lingkungan ke cmdlet berikut: Connect-AzAccount, Get-AzEnvironment, Set-AzEnvironment, dan Remove-AzEnvironment [#15991]
* Menambahkan nama dan versi modul ke string User-Agent [#16291]

#### <a name="azadvisor"></a>Az.Advisor
* Memperbaiki masalah bahwa 'Az.Advisor.psd1' tidak ditandatangani [#16226]

#### <a name="azaks"></a>Az.Aks
* [Perubahan Mencolok] Memperbarui alias parameter dan jenis output dari 'Get-AzAksVersion'
* Menambahkan 'Invoke-AzAksRunCommand' untuk mendukung eksekusi perintah shell (dengan kubectl, helm) pada kluster aks. [#16104]
* Menambahkan dukungan 'EnableNodePublicIp' dan 'NodePublicIPPrefixID' untuk 'New-AzAksCluster' dan 'New-AzAksNodePool'. [#15656]
* Memigrasikan logika pembuatan perwakilan layanan di 'New-AzAksCluster' dari 'Azure Active Directory Graph' ke 'Microsoft Graph'.
* Memperbaiki masalah 'Set-AzAksCluster' tidak dapat meningkatkan kluster saat versi kumpulan node tidak cocok dengan versi kluster. [#14583]
* Menambahkan 'ResourceGroupName' di 'PSKubernetesCluster'. [#15802]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan fungsi WebTest. Berikut merupakan cmdlet baru
    * 'Get-AzApplicationInsightsWebTest'
    * 'New-AzApplicationInsightsWebTest'
    * 'New-AzApplicationInsightsWebTestGeolocationObject'
    * 'New-AzApplicationInsightsWebTestHeaderFieldObject'
    * 'Remove-AzApplicationInsightsWebTest'
    * 'Update-AzApplicationInsightsWebTestTag'

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki contoh dalam dokumen referensi untuk 'Remove-AzAutomationHybridWorkerGroup'
* Memperbarui 'Set-AzAutomationModule' untuk menggunakan panggilan PUT saat memperbarui modul dengan versi tertentu [#12552]

#### <a name="azcloudservice"></a>Az.CloudService
* Ketersediaan umum modul 'Az.CloudService'

#### <a name="azcompute"></a>Az.Compute
* Berisi pembaruan untuk cmdlet powershell berikut
    - 'SetAzVmssDiskEncryptionExtension': Menambahkan parameter ekstensi untuk cmdlet agar berfungsi dengan ekstensi pengujian dan parameter 'EncryptFormatAll' untuk Virtual Machine Scale Sets
    - 'GetAzVmssVMDiskEncryptionStatus': Memodifikasi fungsionalitas cmdlet untuk menampilkan status enkripsi disk data Virtual Machine Scale Sets dengan benar
    - 'SetAzDiskEncryptionExtension'     : Memperbaiki bug pada cmdlet dalam skenario migrasi dari enkripsi 2pass ke 1pass
* Menambahkan 'Add-AzVhd' untuk mengonversi VHD menggunakan Hyper-V
* Menambahkan parameter 'UserData' ke cmdlet VM dan VMSS
* Menambahkan parameter string 'PublicNetworkAccess' ke cmdlet DiskConfig dan SnapshotConfig
* Menambahkan parameter boolean 'AcceleratedNetwork' ke cmdlet DiskConfig dan SnapshotConfig
* Menambahkan properti 'CompletionPercent' ke model PSSnapshot sehingga terlihat oleh pengguna.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Meningkatkan versi API ke 2021-09-01
  - [Perubahan Mencolok] Mengubah jenis parameter 'LogAnalyticWorkspaceResourceId' di 'New-AzContainerGroup' dari Hashtable menjadi String
  - [Perubahan Mencolok] Menghapus parameter 'NetworkProfileId' di 'New-AzContainerGroup', menambahkan 'SubnetId' sebagai alternatifnya
  - [Perubahan Mencolok] Menghapus parameter 'ReadinessProbeHttpGetHttpHeadersName' dan 'ReadinessProbeHttpGetHttpHeadersValue' di 'New-AzContainerInstanceObject', menambahkan 'ReadinessProbeHttpGetHttpHeader' sebagai alternatifnya
  - [Perubahan Mencolok] Menghapus parameter 'LivenessProbeHttpGetHttpHeadersName' dan 'LivenessProbeHttpGetHttpHeadersValue' di 'New-AzContainerInstanceObject', menambahkan 'LivenessProbeHttpGetHttpHeader' sebagai alternatif
  - Menambahkan 'Zone' di 'New-AzContainerGroup', 'AcrIdentity' di 'New-AzContainerGroupImageRegistryCredentialObject'
  - Mengubah 'Username' di 'New-AzContainerGroupImageRegistryCredentialObject' dari wajib menjadi opsional
* Untuk 'Invoke-AzContainerInstanceCommand'
    - [Perubahan Mencolok] Menampilkan hasil eksekusi perintah sebagai output cmdlet dengan menyambungkan websocket di backend [#15754]
    - Menambahkan '-PassThru' untuk mendapatkan hasil eksekusi terakhir saat perintah berhasil
    - Mengubah 'TerminalSizeCol' dan 'TerminalSizeRow' dari wajib menjadi opsional, mengatur nilai defaultnya berdasarkan ukuran jendela PowerShell saat ini
* Menambahkan 'Restart-AzContainerGroup', 'Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint' dan 'New-AzContainerInstanceHttpHeaderObject'

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperbaiki saat peringatan mengenai nilai AnalyticalStorageSchemaType ditampilkan saat tidak ada nilai yang diberikan.
* Menambahkan dukungan untuk Cassandra yang dikelola.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.28.0

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah 'New-AzEventHubKey' selalu menghasilkan kunci utama baru, bukan kunci sekunder sejak versi 1.9.0 [#16362]

#### <a name="azfunctions"></a>Az.Functions
* [Perubahan Mencolok] 'Update-AzFunctionAppPlan' meminta konfirmasi [#16490]
* [Perubahan Mencolok] 'Remove-AzFunctionApp' tidak menghapus ASP jika itu merupakan aplikasi terakhir dalam paket [#16487]
* [Perubahan Mencolok] Mengatur 'FunctionsVersion' ke 4 untuk pembuatan FunctionApp [#16426]
* [Perubahan Mencolok] 'Update-AzFunctionApp' meminta konfirmasi [#14442]
* Memperbaiki kesalahan pembuatan fungsi dengan 'New-AzFunctionApp' di PowerShell 5.1 [#15430]
* Mendukung SKU akun penyimpanan 'Standard_GZRS' [#14633]

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan dua parameter '-Zone' dan '-PrivateLinkConfiguration' ke cmdlet 'New-AzHDInsightCluster'
  - Menambahkan parameter '-Zone' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung pembuatan kluster dengan fitur zona ketersediaan
  - Menambahkan parameter '-PrivateLinkConfiguration' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung penambahan konfigurasi link privat saat membuat kluster dengan fitur link privat.
* Menambahkan cmdlet New-AzHDInsightIPConfiguration untuk membuat objek konfigurasi ip dalam memori.
* Menambahkan cmdlet New-AzHDInsightPrivateLinkConfiguration untuk membuat objek konfigurasi link privat dalam memori.
* Memperbaiki jenis output di dokumen bantuan cmdlet Set-AzHDInsightClusterDiskEncryptionKey dari 'Microsoft.Azure.Management.HDInsight.Models.Cluster' ke 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster' agar tetap konsisten dengan jenis sebenarnya dari objek yang dikembalikan.
* Perubahan mencolok:
  - Mengubah jenis parameter 'OSType' dari 'Microsoft.Azure.Management.HDInsight.Models.OSType' menjadi 'System.string' dalam cmdlet 'New-AzHDInsightCluster'.
  - Mengubah jenis parameter 'ClusterTier' dari 'Microsoft.Azure.Management.HDInsight.Models.ClusterTier' menjadi 'System.string' dalam cmdlet 'New-AzHDInsightCluster' dan 'New-AzHDInsightClusterConfig'.
  - Mengubah jenis properti 'VmSizes' pada kelas 'AzureHDInsightCapabilities' dari `IDictionary<string, AzureHDInsightVmSizesCapability>` menjadi `IList<string>`.
  - Mengubah jenis properti 'AssignedIdentity' pada kelas 'AzureHDInsightCluster' dari 'Microsoft.Azure.Management.HDInsight.Models.ClusterIdentity' menjadi 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightClusterIdentity'.

#### <a name="azkeyvault"></a>Az.KeyVault
* [Perubahan Mencolok] Mengubah nama properti jenis 'PSKeyVaultPermission' untuk mengikuti pola Azure RBAC.
* Memigrasikan AAD Graph API ke MSGraph API.
* Menambahkan pesan ke 'Set-AzKeyVaultAccessPolicy' yang menyatakan bahwa untuk parameter Izin, menggunakan opsi 'Semua' tidak akan menyertakan izin 'Pembersihan'.

#### <a name="azmanagedservices"></a>Az.ManagedServices
* [Perubahan Mencolok] Memperbarui versi API ke pratinjau 2020-02-01

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan properti baru EventName, Category, ResourceProviderName, OperationName, Status, SubStatus dengan jenis string sebagai output untuk perintah Get-AzLog [#15833]
* Mendukung penerima hub peristiwa dalam grup tindakan [#16348]
* Menambahkan set parameter default 'GetByResourceGroup' untuk perintah 'Get-AzAlertRule' [#16356]

#### <a name="aznetwork"></a>Az.Network
* Perbaikan bug pada PSAzureFirewallPolicyThreatIntelWhitelist untuk FirewallPolicy
* Menambahkan parameter opsional '-IsSecuritySite' ke cmdlet berikut:
    - 'New-AzVpnSite'
* Menambahkan dukungan untuk Variabel Pencocokan baru pada Pengecualian WAF
* Melakuka onboarding Enkripsi Virtual Network ke Cmdlet Virtual Network
* Menambahkan dukungan untuk parameter rentang port NAT dalam sumber daya aturan VPN NAT
    - 'New-AzVpnGatewayNatRule.md'
    - 'Update-AzVpnGatewayNatRule.md'
    - 'New-AzVirtualNetworkGatewayNatRule.md'
    - 'Update-AzVirtualNetworkGatewayNatRule.md'
* Menambahkan cmdlet baru untuk mendukung Pengecualian Per Aturan untuk WAF Application Gateway
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet'
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup'
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRule'
    - Selain itu, memperbarui cmdlet untuk menambahkan properti untuk mengonfigurasi ExclusionManagedRuleSet dalam Pengecualian
        - 'New-AzApplicationGatewayFirewallPolicyExclusion'
* Perbaikan Bug di cmdlet Sertifikat Klien Tepercaya Application Gateway untuk memuat seluruh rantai sertifikat dari file.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperluas DataSourceType dengan nilai 'Query', 'Alerts' untuk cmdlet LinkedStorageAccount
* [Perubahan Mencolok] mengganti nama 'StorageAccountId' menjadi 'StorageAccountIds'
  - 'New-AzOperationalInsightsLinkedStorageAccount'
* [Perubahan Mencolok] Mengembalikan 'PSSavedSearch' alih-alih 'HttpStatusCode' melalui 'New-AzOperationalInsightsComputerGroup'
* [Perubahan Mencolok] Mengembalikan 'PSCluster' alih-alih 'PSLinkedService' melalui 'Update-AzOperationalInsightsCluster'
* Memperluas Sku dengan nilai 'capacityreservation', 'lacluster' untuk Ruang Kerja
* Menambahkan properti baru:'SkuCapacity', 'ForceCmkForQuery', 'DisableLocalAuth' untuk Ruang Kerja
* Menambahkan properti baru: 'DailyQuotaGb'on'Set-AzOperationalInsightsWorkspace'
* Menambahkan properti baru: 'ETag', 'Tag' untuk cmdlet StorageInsight
* Menambahkan properti baru 'StorageAccountResourceId' ke cmdlet:
  - 'Set-AzOperationalInsightsStorageInsight'
* Menambahkan atribut SupportsShouldProcess ke cmdlet:
  - 'Set-AzOperationalInsightsStorageInsight'
* Menambahkan cmdlet baru untuk mendukung Table, DataExport, WorkspaceShareKey, PurgeWorkspace, dan AvailableServiceTier
* Menambahkan properti 'Error' dalam hasil 'Invoke-AzOperationalInsightsQuery' untuk mengambil kesalahan parsial saat menjalankan kueri [#16378]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup memperbarui set validasi untuk BackupManagementType yang didukung pada cmdlet 'Get-AzRecoveryServicesBackupItem', 'Get-AzRecoveryServicesBackupContainer', Get-AzRecoveryServicesBackupJob.
* Azure Backup menambahkan dukungan untuk SAPHanaDatabase cmdlet untuk 'Disable-AzRecoveryServicesBackupProtection', 'Unregister-AzRecoveryServicesBackupContainer', 'Get-AzRecoveryServicesBackupItem', 'Get-AzRecoveryServicesBackupContainer'.
* Perubahan Mencolok: Perintah 'Get-AzRecoveryServicesBackupJob', 'Get-AzRecoveryServicesBackupContainer' dan 'Get-AzRecoveryServicesBackupItem' hanya akan mendukung 'BackupManagementType MAB' alih-alih 'MARS'.
* Dukungan Azure Site Recovery untuk reservasi kapasitas untuk Azure ke penyedia Azure.

#### <a name="azresources"></a>Az.Resources
* Menambahkan cmdlet 'Get-AzProviderPreviewFeature', 'Register-AzProviderPreviewFeature' dan 'Unregister-AzProviderPreviewFeature'.
* Memperbaiki bug saat menjalankan Get-AzPolicyAlias dengan nilai kosong parameter NamespaceMatch [#16370]
* [Perubahan Mencolok] Memigrasikan dari AAD Graph ke Microsoft Graph
* [Perubahan Mencolok] Mengubah 'Id' yang dikembalikan di PSDenyAssignment dari string GUID menjadi ID yang memenuhi syarat
* Memungkinkan parameter 'Id' pada 'Get-AzDenyAssignment' untuk menerima ID yang memenuhi syarat
* Menambahkan cmdlet baru 'Publish-AzBicepModule' untuk menerbitkan modul Bicep
* Menambahkan pesan penghentian untuk parameter 'AssignIdentity' di cmdlet '*-AzPolicyAssignment'.
* Menambahkan dukungan untuk identitas terkelola yang ditetapkan pengguna dalam penetapan kebijakan dengan menambahkan parameter 'IdentityType' dan 'IdentityId' ke cmdlet '*-AzPolicyAssignment'.
* Memperbarui cmdlet kebijakan untuk menggunakan api baru versi 2021-06-01 yang memperkenalkan dukungan untuk identitas terkelola yang ditetapkan pengguna dalam penetapan kebijakan.
* Mempersempit izin API saat mendapatkan informasi mengenai objek direktori aktif untuk *-AzRoleAssignment [#16054]

#### <a name="azsql"></a>Az.Sql
* Memperbaiki pemfilteran kartubebas FirewallRuleName di 'Get-AzSqlServerFirewallRule' [#16199]
* Memindahkan AAD SQL Server dan SQL Instance dari ActiveDirectoryClient ke MicrosoftGraphClient

#### <a name="azstackhci"></a>Az.StackHCI
* Mempromosikan Az.StackHCI ke GA

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki kegagalan 'Get-AzStorageContainerStoredAccessPolicy' saat izin null [#15644]
* Mendukung pembuatan token Sas atau token Sas akun layanan blob dengan izin i
    -  'New-AzStorageBlobSASToken'
    -  'New-AzStorageContainerSASToken'
    -  'New-AzStorageAccountSASToken'
* Memperbaiki pembuatan token SAS kontainer yang gagal dari kebijakan akses tanpa waktu kedaluwarsa, dan mengatur waktu kedaluwarsa token SAS [#16266]
    -  'New-AzStorageContainerSASToken'
* Menghapus parameter -Name dari Get-AzRmStorageShare ShareResourceIdParameterSet
    - 'Get-AzRmStorageShare'
* Mendukung pembuatan atau migrasi kontainer untuk mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.
    -  'New-AzRmStorageContainer'
    -  'Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration'
* Mendukung pengaturan/penghapusan kebijakan kekekalan pada blob Storage.
    -  'Set-AzStorageBlobImmutabilityPolicy'
    -  'Remove-AzStorageBlobImmutabilityPolicy'
* Mendukung pengaktifan/penonaktifan penangguhan hukum pada blob Storage.
    -  'Set-AzStorageBlobLegalHold'
* Mendukung pembuatan akun penyimpanan dengan dukungan kekekalan tingkat akun dengan penerapan versi, dan membuat/memperbarui akun penyimpanan dengan kebijakan kekekalan tingkat akun.
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui Microsoft.Azure.Management.Websites SDK ke 3.1.2

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Hiroshi Yoshioka (@hyoshioka0128), Memperbaiki kesalahan ketik "Azure CosmosDB"→"Azure Cosmos DB" (#16470)
* Chris (@isjwuk), Update New-AzAutomationSourceControl.md (#16366)
* Julian Hüppauff (@jhueppauff), [API Management] Referensi variabel tetap (#16525)
* @toswedlu, [CosmosDB] Mengubah pesan peringatan untuk AnalyticalStorageSchemaType (#15723)

## <a name="660---november-2021"></a>6.6.0 - November 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan versi baru klien layanan AAD menggunakan API Microsoft Graph

#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan untuk parameter baru 'NetworkPolicy', 'PodCidr', 'ServiceCidr', 'DnsServiceIP', 'DockerBridgeCidr', 'NodePoolLabel', 'AksCustomHeader di 'New-AzAksCluster'. [#13795]
* Menambahkan peringatan tentang perubahan migrasi berisiko yang akan datang ke Microsoft Graph.
* Menambahkan dukungan untuk mengubah jumlah node dalam kumpulan node. [#12379]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbaiki bug di cmdlet 'Get-AzApiManagementTenantGitAccess'.

#### <a name="azbatch"></a>Az.Batch
* Menghapus 'System.Text.Encodings.Web.dll' assembly [#16062]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet untuk menambahkan properti VMGalleryApplication ke mesin virtual/VMSS
    - New-AzVmGalleryApplication
    - New-AzVmssGalleryApplication
    - Add-AzVmGalleryApplication
    - Add-AzVmssGalleryApplication
    - Remove-AzVmGalleryApplication
    - Remove-AzVmssGalleryApplication
* Menambahkan dukungan untuk pengaturan proksi dan debug untuk Ekstensi mesin virtual untuk SAP (AEM)
* Memperbarui New-AzGalleryImageVersion untuk mengambil properti 'Enkripsi' dengan benar dari parameter '-TargetRegion'.
* Memperbarui Set-AzVmBootDiagnostic ke akun penyimpanan terkelola default jika tidak disediakan.
* Mengedit perilaku default New-AzVmss saat 'OrchestrationMode' diatur ke Fleksibel.
    - Menghapus Kumpulan NAT.
    - Menghapus UpgradePolicy. Melemparkan kesalahan jika disediakan.
    - SinglePlacementGroup pasti salah. Melempar kesalahan jika benar.
    - Versi API Profil Jaringan adalah 01-11-2020 atau yang lebih baru.
    - Properti Utama Konfigurasi IP Profil Jaringan diatur ke true.

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan Get-AzCosmosDBMongoDBBackupInformation untuk mengambil informasi pencadangan terbaru bagi MongoDB.
* Memperbarui New-AzCosmosDBAccount, Update-AzCosmosDBAccount untuk menerima BackupStorageRedundancy
* Memperkenalkan Get-AzCosmosDBLocation untuk mencantumkan Akun Azure CosmosDB dan properti lokasinya.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan PublicNetworkAccess ke Perintah Update_AzDataFactoryV2
* Memperbarui versi SDK .Net ADF ke 4.26.0

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Meningkatkan versi api ke 12-07-2021.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan dukungan untuk sku dan namespace Premium serta parameter pengalihan opsional 'DisableLocalAuth' ke 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Mengatur konfigurasi situs netFrameworkVersion hanya untuk aplikasi V4 Windows
* Mengaktifkan aplikasi fungsi untuk tumpukan Functions V4 [#15919]

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui SDK Manajemen IoT Hub ke versi 4.1.0 (versi-api 10-07-2021)

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan pesan peringatan tentang perubahan berisiko yang akan datang ke 'New-AzKeyVaultRoleDefinition' dan 'Get-AzKeyVaultRoleDefinition'.
    - Untuk mematuhi sintaks 'New-AzRoleDefinition' dan 'Get-AzRoleDefinition' kita akan mengganti nama beberapa properti model 'PSKeyVaultPermission', yang mungkin mempengaruhi dua cmdlet ini.
* Menambahkan peringatan tentang perubahan migrasi berisiko yang akan datang ke Microsoft Graph.

#### <a name="azmigrate"></a>Az.Migrate
* Menambahkan pemeriksaan untuk alamat IP yang tidak valid

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbaiki bug di 'Set-AzOperationalInsightsLinkedService: ketika layanan tertaut tidak ada, lakukan buat(perbarui) alih-alih gagal'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup memperbaiki masalah terkait StorageConfig
* Azure Backup menambahkan NodesList dan AutoProtectionPolicy ke Cmdlet Get-AzRecoveryServicesBackupProtectableItem.
* Azure Backup memperbaiki GetItemsForContainerParamSet guna mendukung pengambilan item cadangan MAB.
* Azure Backup memperbaiki Get-AzRecoveryServicesBackupContainer guna mendukung MAB BackupManagementType, bukan MARS.
* Menambahkan peringatan perubahan yang berisiko: perintah 'Get-AzRecoveryServicesBackupJob', 'Get-AzRecoveryServicesBackupContainer' dan 'Get-AzRecoveryServicesBackupProtectableItem' hanya akan mendukung perintah 'MAB BackupManagementType' alih-alih alias 'MARS', perubahan akan berlaku dari rilis mendatang.
* Menambahkan dukungan untuk jenis disk ZRS guna replikasi Azure ke Azure.
* Menambahkan informasi Zona ketersediaan dalam respons item terproteksi yang direplikasi untuk replikasi Azure ke Azure.

#### <a name="azrediscache"></a>Az.RedisCache
* Membuat contoh baru dalam dokumentasi 'New-AzRedisCache' dan 'Set-AzRedisCache'.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug terkait exitcode Bicep [#16055]
* Menambahkan peringatan perubahan yang berisiko untuk cmdlet AAD
* Menambahkan properti 'UIFormDefinition' ke Template Spec Versions, 'Export-AzTemplateSpec' sekarang akan menyertakan UIFormDefinition Template Spec Version (jika ada) sebagai bagian dari ekspor.
* Menambahkan penangkap kesalahan untuk pembuatan penetapan peran yang gagal saat membuat Perwakilan Layanan
* Peningkatan performa untuk Get-AzPolicyAlias saat -NamespaceMatch cocok dengan satu namespace RP

#### <a name="azsecurity"></a>Az.Security
* Memperbarui referensi paket SDK .NET Keamanan ke versi 3.0.0

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan dukungan untuk ZoneRedundant dan parameter pengalihan opsional 'DisableLocalAuth' ke 'New-AzServiceBusNamespace' dan 'Set-AzServiceBusNamespace'

#### <a name="azsignalr"></a>Az.SignalR
* Menambahkan cmdlet Web PubSub
  - 'New-AzWebPubSub'
  - 'Get-AzWebPubSub'
  - 'Update-AzWebPubSub'
  - 'Restart-AzWebPubSub'
  - 'Remove-AzWebPubSub'
  - 'New-AzWebPubSubHub'
  - 'Get-AzWebPubSubHub'
  - 'Remove-AzWebPubSubHub'
  - 'New-AzWebPubSubKey'
  - 'Get-AzWebPubSubKey'
  - 'Get-AzWebPubSubSku'
  - 'Get-AzWebPubSubUsage'
  - 'Test-AzWebPubSubNameAvailability'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* bgomezangulo (@beagam), Memperbarui Resume-AzNetAppFilesReplication.md (#16040)
* Jim McCormick (@eimajtrebor), Memperbaiki kesalahan ketik (#16091)
* Lampson Nguyen (@lampson), Memperbarui Get-AzDataShare.md (#16015)
* @MaxMeng1985, Memperbarui Get-AzSynapseSqlPoolRestorePoint.md (#16138)
* Reggie Gibson (@regedit32), New-AzBotService: Memperbaiki konversi AppSecret ke teks biasa di Windows PowerShell (#16160)
* Mötz Jensen (@Splaxi), detail BusinessIdentities tidak cocok dengan implementasi saat ini (#16141)


## <a name="650---october-2021"></a>6.5.0 - Oktober 2021
#### <a name="azaccounts"></a>Az.Accounts
* Didukung mendapatkan token akses untuk Microsoft Graph.
* Menambahkan AuthorizeRequestDelegate untuk memungkinkan modul layanan menyesuaikan audiens token.
* Menggunakan [AssemblyLoadContext](/dotnet/api/system.runtime.loader.assemblyloadcontext) untuk menyelesaikan masalah konflik assembly di PowerShell.
* Memperbarui Azure.Core dari 1.16.0 ke 1.19.0.

#### <a name="azattestation"></a>Az.Attestation
* Ketersediaan umum modul 'Az.Attestation'

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki pengecualian referensi nol dan kesalahan ketik di cmdlet 'New-AzFrontDoorCdnRule'

#### <a name="azcompute"></a>Az.Compute
* Memperbarui referensi paket SDK .NET Komputasi ke versi 49.1.0
* Memperbaiki bug di 'Get-AzVM' yang menyebabkan output status daya salah.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan argumen DataFlowEnableQuickReuse untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' guna mengaktifkan penggunaan kembali kluster dengan cepat dalam aktivitas alur berikutnya.
* Memperbarui versi SDK .Net ADF ke 4.25.0
* Menambahkan argumen VNetInjectionMethod untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' guna mendukung injeksi jaringan virtual ekspres Integration Runtime Azure-SSIS.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memungkinkan pembuatan tindakan mesin aturan tanpa RouteConfigurationOverride untuk 'New-AzFrontDoorRulesEngineActionObject'.
* Memperbaiki masalah parameter DynamicCompression yang diabaikan dari 'New-AzFrontDoorRulesEngineActionObject'.

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung definisi peran kustom pada HSM terkelola:
    - Buat melalui 'New-AzKeyVaultRoleDefinition',
    - Hapus melalui 'Remove-AzKeyVaultRoleDefinition',
    - Filter semua peran kustom melalui 'Get-AzKeyVaultRoleDefinition -Custom'.
* Mendukung Enkripsi/Dekripsi/Bungkus/Membuka bungkus menggunakan kunci [#15679]
* Mengaktifkan pengelolaan sumber daya di langganan lain tanpa mengalihkan konteks dengan menambahkan `-Subscription <String>`.

#### <a name="azmaintenance"></a>Az.Maintenance
* Menambahkan dukungan pemeliharaan patch Tamu.

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk Sku, parameter ScaleUnits dari sumber daya BastionHost.
    - 'New-AzBastion'
    - 'Set-AzBastion'
* Onboard Azure Resource Manager ke Cmdlets Umum Private Link
* Memperbarui cmdlet untuk menambahkan properti guna mengaktifkan/menonaktifkan BgpRouteTranslationForNat untuk VpnGateway.
    - 'New-AzVpnGateway'
    - 'Update-AzVpnGateway'
* Memperbarui cmdlet untuk menambahkan properti guna menonaktifkan InternetSecurity untuk P2SVpnGateway.
    - 'New-AzP2sVpnGateway'
* Menambahkan cmdlet baru untuk sumber daya turunan HubBgpConnection dari VirtualHub.
    - 'Get-AzVirtualHubBgpConnection'
    - 'New-AzVirtualHubBgpConnection'
    - 'Update-AzVirtualHubBgpConnection'
    - 'Remove-AzVirtualHubBgpConnection'
* Onboard Azure HDInsight ke Cmdlets Umum Private Link

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaikan bug Azure Site Recovery untuk VMware ke Azure Reprotect, Memperbarui kebijakan, dan Menonaktifkan skenario.
* Azure Backup menambahkan dukungan untuk USERAssigned MSI di RecoveryServices Vault.

#### <a name="azresources"></a>Az.Resources
* Menambahkan pesan kesalahan yang lebih jelas untuk kasus di mana TemplateUri tidak menerima file bisep.
* Memperbaiki kesalahan ketik terkait deskripsi perubahan yang berisiko ManagementGroups [#15819].
* Memperbaiki masalah kapitalisasi tag sumber daya - kapitalisasi tag sumber daya tidak dipertahankan.
* Diperbarui ke Microsoft.Azure.Management.Authorization 2.13.0-pratinjau.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki 'Get-AzSqlDatabaseImportExportStatus' untuk melaporkan kesalahan yang dihadapi

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan Azure.Storage.Blobs ke 12.10.0
* Meningkatkan Azure.Storage.Files.Shares ke 12.8.0
* Meningkatkan Azure.Storage.Files.DataLake ke 12.8.0
* Meningkatkan Azure.Storage.Antrean ke 12.8.0
* Mendukung akun penyimpanan peningkatan untuk mengaktifkan HierarchicalNamespace
    -  'Invoke-AzStorageAccountHierarchicalNamespaceUpgrade'
    -  'Stop-AzStorageAccountHierarchicalNamespaceUpgrade'
* Mendukung AccessTierInferred, Tag dalam skema kebijakan inventaris blob
    - 'New-AzStorageBlobInventoryPolicyRule'
* Mendukung buat/perbarui akun penyimpanan dengan PublicNetworkAccess diaktifkan/dinonaktifkan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung buat/perbarui kontainer blob penyimpanan dengan RootSquash
    - 'New-AzRmStorageContainer'
    - 'Update-AzRmStorageContainer'
* Mendukung AllowProtectedAppendWriteSemua dalam Kebijakan Kekebalan kontainer yang ditetapkan, dan menambahkan kontainer LegalHold
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
    - 'Add-AzRmStorageContainerLegalHold'

#### <a name="azstoragesync"></a>Az.StorageSync
* Memperbaiki bug di mana tidak semua properti objek PSSyncSessionStatus dan PSSyncActivityStatus sedang diisi dengan benar.
* Hal ini memengaruhi cmdlet 'Get-AzStorageSyncServerEndpoint' saat mencoba mengakses properti output berikut:
    - SyncStatus.UploadStatus
    - SyncStatus.DownloadStatus
    - SyncStatus.UploadActivity
    - SyncStatus.DownloadActivity

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'Import-AzWebAppKeyVaultCertificate1' untuk mengatur nama default dengan kombinasi nama keyvault dan nama sertifikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @DSakura207, Menggunakan instans PowerState terakhir pada Status untuk status daya (#15941)
* Yannic Graber (@grabery), Mengodekan ulang Example2 (#15808)
* @joelmforsyth, Memperbaiki contoh multi-regional (#15918)
* Adam Coffman (@SysAdminforCoffee), Memperbarui Set-AzNetworkInterfaceIpConfig.md (#15846)
* Michael Howard (@x509cert), Menulis ulang kalimat untuk memperjelas bahwa versi kunci tertentu harus disediakan (# 15886)

## <a name="640---september-2021"></a>6.4.0 - September 2021
#### <a name="azaccounts"></a>Az.Accounts
* Mengoreksi URL ke Portal Microsoft Azure dalam hasil 'Get-AzEnvironment' dan 'Get-AzContext'. [#15429]
* Membuat perubahan infrastruktur untuk mendukung pengambilalihan langganan default melalui parameter `-SubscriptionId <String>`.
    - [Az.Aks](/powershell/module/az.aks/get-azakscluster) adalah modul pertama yang mendukungnya.

#### <a name="azaks"></a>Az.Aks
* Membuat `-Subscription <String>` tersedia di semua cmdlet Aks. Anda dapat mengelola sumber daya Aks di langganan lain tanpa mengalihkan konteksnya.

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan cmdlet 'Sync-AzApiManagementKeyVaultSecret' baru.
* Menambahkan cmdlet 'New-AzApiManagementKeyVaultObject' baru.
* Menambahkan parameter [-useFromLocation] opsional baru ke cmdlet 'Get-ApiManagementCache' 'New-ApiManagementCache''Update-ApiManagementCache'.
* Memperbarui cmdlet **New-AzApiManagement** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk SKU 'Terisolasi' baru
    - Menambahkan dukungan untuk mengelola Zona Ketersediaan menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
    - Menambahkan dukungan untuk mengelola Versi Api minimum untuk memungkinkan Sarana Kontrol menggunakan properti 'MinimalControlPlaneApiVersion'.
* Memperbarui cmdlet **New-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk mengelola Zona Ketersediaan menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
* Memperbarui cmdlet **Add-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk mengelola Zona Ketersediaan menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
* Memperbarui cmdlet **Update-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk mengelola Zona Ketersediaan menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
* Memperbarui cmdlet **New-AzApiManagementCustomHostnameConfiguration** untuk mengelola Konfigurasi Nama Host Kustom
    - Menambahkan dukungan untuk menentukan 'IdentityClientId' guna menyediakan ClientId yang Ditetapkan Pengguna Identitas Terkelola untuk digunakan dengan KeyVault

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug: Menutup handel file input di Import-AzAutomationRunbook

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah parameter wajib di cmdlet 'Get-AzCdnEndpointResourceUsage'

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter baru '-LinuxConfigurationPatchMode', '-WindowsConfigurationPatchMode', dan '-LinuxConfigurationProvisionVMAgent' ke 'Set-AzVmssOSProfile'
* Menambahkan parameter baru '-SshKeyName' dan '-GenerateSshKey' ke 'New-AzVM' untuk membuat mesin virtual dengan SSH
* Memperbaiki bug di 'Add-AzVHD' di Linux yang menyebabkan unggahan gagal untuk URI tujuan tertentu
* Menambahkan cmdlet baru untuk Titik Pemulihan dan Koleksi Titik Pemulihan:
    - 'New-AzRestorePoint'
    - 'New-AzRestorePointCollection'
    - 'Get-AzRestorePoint'
    - 'Get-AzRestorePointCollection'
    - 'Update-AzRestorePointCollection'
    - 'Remove-AzRestorePoint'
    - 'Remove-AzRestorePointCollection'
* Menambahkan parameter baru '-EnableSpotRestore' dan '-SpotRestoreTimeout' ke 'New-AzVMSSConfig' untuk mengaktifkan Kebijakan Pemulihan Spot
* Menambahkan cmdlet baru: 'Update-AzCapacityReservationGroup' dan 'Update-AzCapacityReservation'

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperbaiki bug tempat pemulihan akun database yang dihapus gagal.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan argumen subnetId untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' guna mendukung RBAC memeriksa injeksi VNet terhadap ID sumber daya subnet alih-alih ID sumber daya VNet.
* Menambahkan cmdlet 'Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint' untuk menyediakan daftar dependensi jaringan keluar untuk runtime integrasi SSIS di Azure Data Factory yang bergabung dengan jaringan virtual.
* Menambahkan PublicNetworkAccess ke Data Factory.
* Memperbarui versi SDK .Net ADF ke 4.23.0

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung penambahkan kunci EC di brankas kunci [#15699]

#### <a name="azmigrate"></a>Az.Migrate
* Mendukung UUID disk duplikat pada disk sumber.
* Mendukung subnet di VNet yang sama untuk AVSet.
* Mendukung runAsAccount yang mengambil beberapa Vcenter di situs yang sama.

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk menambahkan properti 'Subnet' untuk kumpulan alamat backend penyeimbang beban berbasis IP.
    - 'New-AzLoadBalancerBackendAddressConfig'
* Memperbarui Cmdlet untuk menambahkan properti 'TunnelInterface' untuk operasi terkait kumpulan backend.
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan multi appliance Azure Site Recovery untuk skenario pemulihan bencana VMware ke Azure menggunakan RCM sebagai sarana kontrol.
* Azure Backup memperbaiki masalah targetPhysicalPath dengan SQL CRR
* Azure Backup memperbaiki perlindungan yang nonaktifkan untuk beban kerja SQL
* Azure Backup menyelesaikan bug dalam mengatur properti CMK di rilis terbaru
* Azure Backup menghapus karakter khusus dari teks bantuan perintah register-azrecoveryservicesbackupcontainer

#### <a name="azresources"></a>Az.Resources
* Menggunakan JsonExtensions untuk membuat serialisasi objek JSON deserialize guna memastikan penggunaan pengaturan serialisasi kustom [#15552]
* Menambahkan dukungan untuk jenis perubahan 'Unsupported' dan 'NoEffect' ke penyebaran cmdlet What-If.

#### <a name="azsecurityinsights"></a>Az.SecurityInsights
* Diperbarui ke parameter 'Get-AzSentinelIncident'
    - Menambahkan '-Filter' untuk mendukung filter OData
    - Menambahkan '-OrderBy' untuk mendukung pemesanan OData
    - Menambahkan '-Max' untuk mendukung pengambilan lebih dari default 1000 insiden.

#### <a name="azsql"></a>Az.Sql
* Mengubah implementasi yang mendasari 'Get-AzSqlDatabase' untuk mendukung respons yang dipaginasi dari server
* Menambahkan parameter 'ZoneRedundant' ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance' guna mengaktifkan pembuatan dan pembaruan zona - instans redundan.
* Menambahkan bidang ZoneRedundant ke model instans terkelola sehingga menampilkan informasi tentang zona - redundansi misalnya yang ditampilkan oleh 'Get-AzSqlInstance'.
* Memperpanjang enum AuditActionGroups dalam server & audit database. Menambahkan DBCC_GROUP, DATABASE_OWNERSHIP_CHANGE_GROUP dan DATABASE_CHANGE_GROUP.
* Menambahkan bendera 'AsJob' ke 'Remove-AzSqlInstance'
* Menambahkan parameter 'SubnetId' ke 'Set-AzSqlInstance' untuk mendukung SLO pembaruan lintas-subnet
* Ditingkatkan ke versi SDK terbaru

#### <a name="azstorage"></a>Az.Storage
* Mendukung untuk mendapatkan/mengatur tag blob pada blob tertentu
    -  'Get-AzStorageBlobTag'
    -  'Set-AzStorageBlobTag'
* Mendukung pembuatan blob tujuan dengan tag blob tertentu saat mengunggah/menyalin Blob
    -  'Set-AzStorageBlobContent'
    -  'Start-AzStorageBlobCopy'
* Mendukung blob daftar di seluruh kontainer dengan ekspresi sql filter tag blob
    -  'Get-AzStorageBlobByTag'
* Mendukung blob daftar di dalam kontainer dan menyertakan Tag Blob
    -  'Get-AzStorageBlob'
* Mendukung operasi blob dengan kondisi tag blob, dan menggagalkan cmdlet saat kondisi tag blob tidak cocok
    -  'Get-AzStorageBlob'
    -  'Get-AzStorageBlobContent'
    -  'Get-AzStorageBlobTag'
    -  'Remove-AzStorageBlob'
    -  'Set-AzStorageBlobContent'
    -  'Set-AzStorageBlobTag'
    -  'Start-AzStorageBlobCopy'
    -  'Stop-AzStorageBlobCopy'
* Menghasilkan token sas blob dengan versi API baru
    -  'New-AzStorageBlobSASToken'
    -  'New-AzStorageContainerSASToken'
    -  'New-AzStorageAccountSASToken'
* Memperbaiki kegagalan penyalinan blob dengan info masuk OAuth saat klien dan server memiliki perbedaan waktu [#15644]
    -  'Copy-AzStorageBlob'
* Memperbaiki penghapusan item Data Lake Gen2 yang gagal dengan token SAS baca saja
    -  'Remove-AzDataLakeGen2Item'
* Merevisi tujuan cek masuk yang ada yang memindahkan item Data Lake Gen2
    -  'Move-AzDataLakeGen2Item'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan set parameter ke 'Invoke-AzStorageSyncChangeDetection'
    - Dapat memanggil cmdlet tanpa parameter -DirectoryPath dan -Path untuk memicu deteksi perubahan pada seluruh berbagi file
* Menambahkan dukungan untuk pengunggahan otoritatif sebagai bagian dari New-AzStorageSyncServerEndpoint.
* Menambahkan informasi status enumerasi perubahan cloud di objek Titik Akhir Cloud.
* Memperbarui objek Titik Akhir Server dengan berbagai properti kesehatan
* Menambahkan properti 'ServerName' di Titik Akhir Server dan objek Server Terdaftar untuk mendukung menampilkan FQDN server saat ini.

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Set-AzWebApp' untuk menampilkan pesan peringatan yang valid saat gagal menambahkan -Hostname #9316
* Memperbaiki 'Get-AzWebApp' untuk menampilkan CustomDomainVerificationId dalam respons. #9316

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Sears (@asears)
  * Memperbaiki ejaan accountname (#15779)
  * Memperbaiki Ejaan, contoh (#15780)
* @cawrites, Memperbarui New-AzDataMigrationService.md (#15646)
* @harpaul-gill, Menambahkan dukungan untuk paginasi di Database Get Sql (#15772)
* @jeepingben, Membuat nama mutex yang aman untuk Linux (memperbaiki #15653) (#15666)
* @LosManos, Dokumen: Parameter diabaikan saat mencantumkan rahasia ( #15788 )
* Mats Estensen (@matsest), dokumen: menambahkan contoh untuk Update-AzSubscription (#15748)
* Mauricio Arroyo (@mauricio-msft), memperbaiki kesalahan ketik dalam contoh cmdlet (#15719 )

## <a name="630---august-2021"></a>6.3.0 - Agustus 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menonaktifkan penyimpanan otomatis konteks saat persistensi cache token gagal di Windows dan macOS
* Menambahkan versi PowerShell ke dalam rekaman telemetri
* Meningkatkan Microsoft.ApplicationInsights dari 2.4.0 ke 2.12.0
* Memperbarui Azure.Core ke 1.16.0

#### <a name="azaks"></a>Az.Aks
* Menambahkan 'Start-AzAksCluster', 'Stop-AzAksCluster', 'Get-AzAksUpgradeProfile', dan 'Get-AzAksNodePoolUpgradeProfile'. [#14194]
* Menambahkan properti 'IdentityProfile' dalam output 'Get-AzAksCluster'. [#12546]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* [Perubahan yang Berisiko] Mengubah jenis PSCognitiveServicesAccount.Identity.Type dari IdentityType menjadi ResourceIdentityType.
* [Perubahan yang Berisiko] Mengubah jenis PSCognitiveServicesAccount.Sku.Tier dari SkuTier menjadi string.
* [Perubahan yang Berisiko] Menghapus ActionRequired dari PrivateLinkServiceConnectionState.
* Memperbarui PowerShell untuk menggunakan versi 30-04-2021.
* Menambahkan cmdlet 'Undo-AzCognitiveServicesAccountRemoval'.
* Menambahkan parameter '-RestrictOutboundNetworkAccess', '-AllowedFqdnList', '-DisableLocalAuth', '-KeyVaultIdentityClientId', '-IdentityType', '-UserAssignedIdentityId' ke 'New-AzureCognitiveServicesAccount' dan 'Set-AzureCognitiveServicesAccount'.
* Menambahkan parameter '-InRemovedState', '-Location' ke 'Remove-AzureCognitiveServicesAccount' dan 'Get-AzureCognitiveServicesAccount'.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki peringatan di cmdlet 'New-AzVM' yang menyatakan sku mesin virtual sedang default bahkan jika ukuran sku disediakan oleh pengguna. Sekarang hanya terjadi ketika pengguna tidak memberikan ukuran sku.
* Mengedit cmdlet 'Set-AzVmOperatingSystem' untuk tidak lagi menimpa nilai EnableAutomaticUpdates yang ada pada mesin virtual yang diteruskan jika ada.
* Memperbarui modul Komputasi untuk menggunakan SDK .Net versi terbaru 48.0.0.
* Menambahkan cmdlet baru untuk Fitur Reservasi Kapasitas:
    - 'New-AzCapacityReservationGroup'
    - 'Remove-AzCapacityReservationGroup'
    - 'Get-AzCapacityReservationGroup'
    - 'New-AzCapacityReservation'
    - 'Remove-AzCapacityReservation'
    - 'Get-AzCapacityReservation'
* Menambahkan parameter baru '-CapacityReservationGroupId' ke cmdlet berikut:
    - 'New-AzVm'
    - 'New-AzVmConfig'
    - 'New-AzVmss'
    - 'New-AzVmssConfig'
    - 'Update-AzVm'
    - 'Update-AzVmss'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.21.0

#### <a name="azmigrate"></a>Az.Migrate
* Menambahkan jenis lisensi SQL Server.
* Menambahkan fitur CRN.
* Menambahkan fitur tag sumber daya.
* Diperbarui ke versi api 10-02-2021.

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan kembali parameter 'ResourceGroupName' untuk set parameter 'Add-AzAutoscaleSetting' 'AddAzureRmAutoscaleSettingUpdateParamGroup' dan menjadikannya opsional [#15491]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Arsip untuk brankas V1.
* Menambahkan ProtectedItemsCount di Get-AzRecoveryServicesBackupProtectionPolicy.
* Perbaikan bug pemulihan situs Azure untuk azure ke azure dalam properti pembaruan mesin virtual.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'RedisVersion' di 'New-AzRedisCache' dan 'Set-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug terkait 'PSResource' di mana beberapa konstruktor meninggalkan properti 'SubscriptionId' tanpa ditetapkan/null.  [#10783]
* Menambahkan dukungan untuk membuat dan memperbarui Spesifikasi Templat dalam file Bicep [#15313]
* Menambahkan parameter '-ProceedIfNoChange' ke penyebaran yang membuat cmdlet.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki model Aplikasi Klasik dan Terkelola (Aplikasi, Kluster, Layanan) dengan memperbarui konstruktor untuk mengambil semua properti baru
    - Ini memecahkan masalah terkait alur di mana menyalurkan hasil langsung dari panggilan cmdlet Get ke dalam dan panggilan Update atau Set menghapus beberapa properti yang sengaja diatur
    - Memperbarui file uji yang sesuai untuk mencakup kasus-kasus yang disebutkan di atas

#### <a name="azsql"></a>Az.Sql
* Memperbaiki logika identitas di 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Mendukung Waktu Akses Terakhir Blob
    -  'Enable-AzStorageBlobLastAccessTimeTracking'
    -  'Disable-AzStorageBlobLastAccessTimeTracking'
    -  'Add-AzStorageAccountManagementPolicyAction'
* Membuat 'Get-AzDataLakeGen2ChildItem' mencantumkan semua item datalake gen2 secara default, alih-alih membutuhkan pengguna untuk mencantumkan potongan demi potongan.
* Memperbaiki masalah BlobProperties kosong saat menggunakan sas tanpa awalan '?' [#15460]
* Memperbaiki kegagalan menyalin blob kecil secara sinkron [#15548]
    - 'Copy-AzStorageBlob'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Add-AzWebAppAccessRestrictionRule' yang gagal ketika pengguna tidak memiliki izin untuk mendapatkan daftar Tag Layanan #15316 dan #14862

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Borys Generalov (@bgener), Memperbarui Get-AzPolicyState.md (#15455)
* Dean Mock (@deanmock), Memperbarui New-AzAutomationSchedule.md (#15371)
* John Bevan (@JohnLBevan), #10783 - Perbaikan untuk Get-AzResource yang menampilkan PSResource dengan SubscriptionId null (#15106)
* Michael Mejias Sanchez (@mikemej), Pembaruan - Memperbarui penyebaran (VNET eksternal) (#15391)
* @mjsharma, Menambahkan catatan untuk perintah alternatif (#15360)
* Ked Mardemootoo (@nocticdr), Memperbaiki beberapa kesalahan ketik untuk kejelasan tambahan (#15428)
* Pascal Berger (@pascalberger), Memperbaiki nama parameter dalam contoh Sync-AzVirtualNetworkPeering (#15493)
* @rcabr, Memperbaiki dokumen di Get-AzStorageContainer ( #15476 )
* AAron (@S-AA-RON), Memperbarui New-AzNetworkSecurityGroup.md (#15512)
* 坂本ポテコ (@sakamoto-poteko), Memperbarui New-AzVMConfig.md (#15376)
* @Shawn-Yuen, Memperbarui Remove-AzDataLakeGen2Item.md (#15388)

## <a name="621---july-2021"></a>6.2.1 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki kesalahan akses ketika subscripiton tidak memiliki properti 'Tag' [#15425].

## <a name="620---july-2021"></a>6.2.0 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Tag, AuthorizationSource ke PSAzureSusbscripiton dan menambahkan TenantType, DefaultDomain, TenantBrandingLogoUrl, CountryCode ke PSAzureTenant [#15220]
* Meningkatkan klien langganan ke 01-01-2021 [#15220]
* Menghapus pemeriksaan mode Interaktif di pustaka umum
* Menambahkan titik akhir OperationalInsights ke lingkungan AzureChinaCloud [#15305]
* Mencetak log default modul yang dibuat otomatis ke aliran verbose

#### <a name="azaks"></a>Az.Aks
* Menambahkan parameter 'AvailabilityZone' untuk 'New-AzAksNodePool'. [#14505]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan properti hanya baca 'ConnectionString' dan 'ApplicationId' ke komponen applicationinsights

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-OrchestrationMode' ke 'New-AzVmss' dan 'New-AzVmssConfig'
* Memperbarui cmdlet berikut agar berfungsi saat sumber daya menggunakan sumber gambar jarak jauh menggunakan AKS atau Shared Image Gallery.
    - 'Update-AzVm'
    - 'Update-AzVmss'
    - 'Update-AzGalleryImageVersion'
* Menambahkan parameter '-EnableCrossZoneUpgrade' dan '-PrioritizeUnhealthyInstance' ke 'Set-AzVmssRollingUpgradePolicy'
* Menambahkan parameter 'AssessmentMode' ke cmdlet 'Set-AzVMOperatingSystem'.
* Memperbaiki bug di 'Add-AzVmssNetworkInterfaceConfiguration'
* Memperbaiki IOPS dan pemeriksaan throughput di 'Test-AzVMAEMExtension'
* Menambahkan cmdlet baru untuk versi API DiskRP 01-12-2020
    - New-AzDiskPurchasePlanConfig
    - Set-AzDiskSecurityProfile
* Mengubah Cmdlet untuk versi API DiskRP 01-12-2020
    - New-AzDiskConfig
    - New-AzSnapshotConfig
    - New-AzSnapshotUpdateConfig
    - New-AzDiskUpdateConfig
    - New-AzDiskEncryptionSetConfig
    - Update-AzDiskEncryptionSet

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Rilis ini memperkenalkan cmdlet untuk fitur Pencadangan Berkelanjutan (Pemulihan titik waktu tertentu):
  - Memperkenalkan dukungan untuk membuat akun dengan kebijakan pencadangan mode berkelanjutan.
  - Memperkenalkan dukungan untuk Pemulihan titik waktu tertentu untuk akun dengan kebijakan pencadangan mode berkelanjutan.
  - Memperkenalkan dukungan untuk memperbarui interval pencadangan dan retensi pencadangan untuk akun dengan kebijakan pencadangan mode berkala.
  - Memperkenalkan dukungan untuk mencantumkan sumber daya yang dapat dipulihkan dalam akun database langsung.
  - Memperkenalkan dukungan untuk menentukan jenis skema penyimpanan analitis pada pembuatan/pembaruan akun.
  - Cmdlet berikut ditambahkan:
    - Restore-AzCosmosDBAccount, New-AzCosmosDBDatabaseToRestore, Get-AzCosmosDBRestorableDatabaseAccount,
    - Get-AzCosmosDBSqlRestorableDatabase, Get-AzCosmosDBSqlRestorableContainer, Get-AzCosmosDBSqlRestorableResource,
    - Get-AzCosmosDBMongoDBRestorableDatabase, Get-AzCosmosDBMongoDBRestorableCollection, Get-AzCosmosDBMongoDBRestorableResource.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan Enkripsi Kunci yang Dikelola Pelanggan ke DataFactory

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dua pengaturan aplikasi tambahan (WEBSITE_CONTENTSHARE dan WEBSITE_CONTENTAZUREFILECONNECTIONSTRING) untuk aplikasi Konsumsi Linux. [15124]
* Memperbaiki bug terkait New-AzFunctionApp saat dibuat di Azure Gov. [13379]
* Menambahkan cmdlet Az.Functions yang dibutuhkan untuk mendukung pembuatan dan penyalinan pengaturan aplikasi dengan nilai kosong. [14511]

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug referensi null untuk 'Get-AzMetric' saat 'ResultType' diatur ke 'Metadata'
* Memperbaiki bug untuk 'Add-AzAutoscaleSetting' tidak dapat menyalurkan hasil dari 'Get-AzAutoscaleSetting' [#13861]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan alamat ip publik sebagai parameter opsional untuk membuat server rute
    - 'New-AzRouteServer'
* Memperbarui cmdlet untuk mengaktifkan spesifikasi zona tepi
    - 'New-AzPublicIpPrefix'
    - 'New-AzLoadBalancer'
    - 'New-AzPrivateLinkService'
    - 'New-AzPrivateEndpoint'
* Menambahkan dukungan untuk menampilkan lokasi jaringan virtual yang diperluas di konsol
    - 'New-AzVirtualNetwork'
    - 'Get-AzVirtualNetwork'
* Menambahkan dukungan untuk menampilkan lokasi alamat IP publik yang diperluas di konsol
    - 'New-AzPublicIpAddress'
    - 'Get-AzPublicIpAddress'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki AutoProtection AG SQL yang Nonaktif.

#### <a name="azsecurity"></a>Az.Security
* Ketersediaan umum modul Az.Security
* Mengubah nama Get-AzRegulatoryComplainceAssessment menjadi Get-AzRegulatoryComplianceAssessment untuk memperbaiki kesalahan ketik

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter 'RestrictOutboundNetworkAccess' ke cmdlet berikut
    - 'New-AzSqlServer'
    - 'Set-AzSqlServer'
* Menambahkan cmdlet baru untuk operasi CRUD pada FQDN yang Diizinkan dari aturan Firewall Keluar 'Get-AzSqlServerOutboundFirewallRule' 'New-AzSqlServerOutboundFirewallRule' 'Remove-AzSqlServerOutboundFirewallRule'
* Memperbaiki logika identitas untuk SystemAssigned, identitas UserAssigned untuk New-AzSqlServer, New-AzSqlInstance
* Memperbarui cmdlet untuk mendapatkan dan memperbarui frekuensi cadangan diferensial database SQL 'Get-AzSqlDatabaseBackupShortTermRetentionPolicy' 'Set-AzSqlDatabaseBackupShortTermRetentionPolicy'
* Memperbaiki masalah PUT Parsial untuk Azure Policy di 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Mendukung aktifkan/nonaktifkan penghapusan sementara kontainer Blob
    -  'Enable-AzStorageContainerDeleteRetentionPolicy'
    -  'Disable-AzStorageContainerDeleteRetentionPolicy'
* Mendukung daftar kontainer Blob yang dihapus
    -  'Get-AzRmStorageContainer'
    -  'Get-AzStorageContainer'
* Mendukung pemulihan kontainer Blob yang dihapus
    -  'Restore-AzStorageContainer'
* Mendukung pengaturan SMB aman di properti layanan File
    - 'Update-AzStorageFileServiceProperty'
* Mendukung pembuatan akun dengan EnableNfsV3
    - 'New-AzStorageAccount'
* Mendukung memasukkan lebih banyak parameter penyalinan blob dari alur [#15301]
    -  'Start-AzStorageBlobCopy'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Import-AzWebAppKeyVaultCertificate' untuk mendukung ServerFarmId [#15091]
* Memperbaiki 'Menambahkan parameter opsional untuk menghapus atau menyimpan paket Appservice saat WebApp terakhir dihapus dari paket'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Mikey Bronowski (@MikeyBronowski)
  * Memperbarui Get-AzSynapseTriggerRun.md ( #15231 )
  * Memperbarui Get-AzSynapsePipelineRun.md dengan menambahkan lebih banyak contoh yang mencakup lebih banyak skenario (#15232)
* @mjsharma, Menambahkan catatan untuk perintah alternatif (#15359)
* @tomswedlund, Menambahkan dukungan untuk mengatur jenis skema penyimpanan analitis pada pembuatan/pembaruan akun untuk CosmosDB (#15362)
* @ylabade, Memperbaiki nama parameter aplikasi web dalam contoh ( #15291 )


## <a name="610---june-2021"></a>6.1.0 - Juni 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan cmdlet 'Open-AzSurveyLink'
* Mendukung file sertifikat sebagai parameter input Connect-AzAccount

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah 'Set-AzAks' akan gagal di Automation Runbook. [#15006]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Memperbaiki masalah 'ResourcegroupName' terlewatkan saat mengeksekusi di bawah cmdlet dengan parameter 'InputObject' [#14848]
  * 'Get-AzApplicationInsightsLinkedStorageAccount'
  * 'New-AzApplicationInsightsLinkedStorageAccount'
  * 'Update-AzApplicationInsightsLinkedStorageAccount'
  * 'Remove-AzApplicationInsightsLinkedStorageAccount'

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah profil yang hilang di cmdlet 'Remove-AzCdnProfile'

#### <a name="azcompute"></a>Az.Compute
* Memperbarui modul Komputasi untuk menggunakan SDK .Net versi terbaru 47.0.0.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Menghapus tampilan info masuk berbagi file [#15224]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.19.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan fungsionalitas untuk menerima input dari alur untuk 'Get-AzEventHub' dari 'Get-AzEventHubNamespace'.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung fitur monitor azure baru di HDInsight:
    - Menambahkan cmdlet 'Get-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mendapatkan status Azure Monitor dari kluster HDInsight.
    - Menambahkan cmdlet 'Enable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mengaktifkan Azure Monitor di kluster HDInsight.
    - Menambahkan cmdlet 'Disable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan menonaktifkan Azure Monitor di kluster HDInsight.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menghapus item daftar duplikat di 'Get-AzKeyVault' [#15164]
* Menambahkan tag 'SecretManagement' ke modul 'Az.KeyVault' [#15173]

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk server rute demi cara yang lebih stabil untuk menambahkan konfigurasi IP.
* Menambahkan dukungan untuk mendapatkan satu sumber daya tautan privat.
* Menambahkan deskripsi lebih rinci tentang GroupId di 'New-AzPrivateLinkServiceConnection'
* Memperbarui cmdlet untuk mengaktifkan pengaturan PrivateRange di AzureFirewallPolicy.
    - 'New-AzFirewallPolicy'
    - 'Set-AzFirewallPolicy'
* Memperbarui cmdlet untuk menambahkan NatRules di VirtualNetworkGateway dan BgpRouteTranslationForNat.
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'
* Memperbarui cmdlet untuk menambahkan EngressNatRules dan EgressNatRules di Koneksi VirtualNetworkGateway.
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Memperbarui cmdlet untuk mengaktifkan pengaturan FlowTimeout di VirtualNetwork.
    - 'New-AzVirtualNetwork'
* Menambahkan cmdlet untuk Mendapatkan/Membuat/Memperbarui/Menghapus VirtualNetworkGatewayNatRules.
    - 'New-AzVirtualNetworkGatewayNatRule'
    - 'Update-AzVirtualNetworkGatewayNatRule'
    - 'Get-AzVirtualNetworkGatewayNatRule'
    - 'Remove-AzVirtualNetworkGatewayNatRule'
* Menambahkan cmdlet baru untuk Sinkronisasi di VirtualNetworkPeering
    - 'Sync-AzVirtualNetworkPeering'
* Memperbarui cmdlet untuk menambahkan properti baru dan mendefinisikan ulang properti yang ada di VirtualNetworkPeering
    - 'Add-AzVirtualNetworkPeering'
    - 'Get-AzVirtualNetworkPeering'
* Memperbarui cmdlet untuk mengaktifkan pengaturan PreferredRoutingGateway di VirtualHub.
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Memperbarui cmdlet untuk mengekspos dua properti baca-saja sertifikat klien.
    - 'Get-AzApplicationGatewayTrustedClientCertificate'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan pemindahan DS lintas penyewa.
* Menghapus batasan untuk mengambil titik pemulihan hanya untuk rentang waktu 30 hari.
* Mengaktifkan CRR untuk wilayah baru.

#### <a name="azresources"></a>Az.Resources
* Memungkinkan untuk memberi nama penyebaran saat menguji penyebaran [#11497]

#### <a name="azsignalr"></a>Az.SignalR
* Mengubah menjadi parameter 'Allow' dan 'Deny' cmdlet 'Update-AzSignalRNetworkAcl':
    - Menerima 'Trace' sebagai nilai yang valid.
    - Diterima '@()' sebagai koleksi kosong untuk menghapus daftar.
* Mendukung 'ResourceGroupCompleter' dan 'ResourceNameCompleter' dalam cmdlet yang berlaku.
* Tidak menggunakan lagi properti 'HostNamePrefix' dari jenis output 'PSSignalRResource' cmdlet berikut:
    - 'Get-AzSignalR'
    - 'New-AzSignalR'
    - 'Update-AzSignalR'

#### <a name="azsql"></a>Az.Sql
* Menambahkan opsi untuk mendukung versi singkat id konfigurasi pemeliharaan untuk Instans Terkelola di cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Menambahkan HighAvailabilityReplicaCount ke 'New-AzSqlDatabaseSecondary'
* Menambahkan Hanya Properti AAD dan Administrator Eksternal ke AzSqlServer dan AzSqlInstance
    - Menambahkan opsi untuk menentukan cmdlet '-ExternalAdminName', '-ExternalAdminSid', '-EnableActiveDirectoryOnlyAuthentication' di cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
    - Menambahkan opsi untuk memperluas informasi administrator eksternal menggunakan cmdlet '-ExpandActiveDirectoryAdministrator' di 'Get-AzSqlServer' dan 'Get-AzSqlInstance'
* Memperbaiki 'Set-AzSqlDatabase' agar tidak lagi secara default mengatur ReadScale ke Nonaktif saat tidak ditentukan
* Memperbaiki 'Set-AzSqlServer' dan 'Set-AzSqlInstance' untuk PUT parsial hanya dengan properti identitas dan null
* Menambahkan parameter yang terkait dengan UMI di cmdlet 'New-AzSqlServer', 'New-AzSqlInstance', 'Set-AzSqlServer' dan 'Set-AzSqlInstance'.
* Menambahkan parameter -AutoRotationEnabled ke cmdlet berikut:
    - 'Set-AzSqlServerTransparentDataEncryptionProtector'
    - 'Get-AzSqlServerTransparentDataEncryptionProtector'
    - 'Set-AzSqlInstanceTransparentDataEncryptionProtector'
    - 'Get-AzSqlInstanceTransparentDataEncryptionProtector'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan berbagi file dengan NFS/SMB enabledEnabledProtocol dan RootSquash, serta pembaruan berbagi dengan RootSquash
    - 'New-AzRmStorageShare'
    - 'Update-AzRmStorageShare'
* Mendukung pengaktifan Smb Multichannel pada layanan File
    -  'Update-AzStorageFileServiceProperty'
* Memperbaiki masalah penyalinan di dalam akun yang sama berdasarkan sumber akses menggunakan info masuk anonim, saat menyalin Blob di dalam akun yang sama dengan info masuk Oauth
* Menghapus StorageFileDataSmbShareOwner dari set nilai parameter DefaultSharePermission dalam membuat/memperbarui akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki masalah yang mencegah penghapusan aturan berdasarkan nama dan pengenal unik di 'Remove-AzWebAppAccessRestrictionRule'
* Memperbaiki masalah yang secara default mengatur Grup Ketersediaan AlwaysOn ke false di 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andy Roberts (@andyr8939), Menghapus variabel TimeGrain yang tidak digunakan dari contoh (#15062)
* Ashley Roll (@AshleyRoll), Menghapus Write-Host yang membocorkan info masuk berbagi file (#15225)
* Kailash Mandal (@KaishM), Memperbarui New-AzPublicIpAddress.md (#15040)
* Olivier Miossec (@omiossec), Memperbarui Get-AzExpressRouteCircuitRouteTable.md (#15054)
* Scott (@S-T-S), Memperbarui Set-AzNetworkInterface.md (#15112)
* @sohaibMSFT, Contoh AutoScale Application Gateway (#15071)
* @Srihsu, Memperbarui Split-AzReservation.md (#15049)
* @srozemuller, kesalahan ketik dalam contoh parameter resourcegroup ( #15146 )


## <a name="600---may-2021"></a>6.0.0 - Mei 2021
Az 6.0.0 (Az.Accounts 2.3.0) hanya didukung pada Windows PowerShell 5.1, PowerShell 7.0 versi 7.0.6 atau lebih tinggi dan PowerShell 7.1 versi 7.1.3 atau yang lebih tinggi, terbuka https://aka.ms/install-powershell untuk mempelajari cara meningkatkan. Untuk informasi lebih lanjut, buka https://aka.ms/azpslifecycle.

#### <a name="azaccounts"></a>Az.Accounts
* Meningkatkan Azure.Identity ke 1.4 dan MSAL ke 4.30.1
* Menghapus parameter usang 'ManagedServiceHostName', 'ManagedServicePort' dan 'ManagedServiceSecret' dari cmdlet 'Koneksi-AzAccount', variabel lingkungan 'MSI_ENDPOINT' dan 'MSI_SECRET' dapat digunakan sebagai gantinya
* Menyesuaikan format tampilan PSAzureRmAccount untuk menyembunyikan rahasia perwakilan layanan [#14208]
* Menambahkan parameter opsional 'AuthScope' ke 'Koneksi-AzAccount' untuk mendukung autentikasi fitur data plane yang ditingkatkan
* Mengatur waktu coba lagi menurut variabel lingkungan [#14748]
* Mendukung autentikasi pengeluar sertifikat nama subjek

#### <a name="azcompute"></a>Az.Compute
* Menambahkan 'Invoke-AzVmInstallPatch' untuk mendukung penginstalan patch di mesin virtual menggunakan PowerShell.
* Memperbarui modul Komputasi untuk menggunakan SDK .Net versi terbaru 46.0.0.
* Menambahkan parameter opsional '-EdgeZone' ke cmdlet berikut:
    - 'Get-AzVMImage
    - 'Get-AzVMImageOffer'
    - 'Get-AzVMImageSku'
    - 'New-AzDiskConfig'
    - 'New-AzImageConfig'
    - 'New-AzSnapshotConfig'
    - 'New-AzVM'
    - 'New-AzVmssConfig'
    - 'New-AzVMSS'

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Menambahkan cmdlet baru: 'Start-AzContainerGroup', 'Stop-AzContainerGroup' [#10773], 'Invoke-AzContainerInstanceCommand' [#7648], 'Update-AzContainerGroup', 'Add-AzContainerInstanceOutput', 'Get-AzContainerInstanceCachedImage', 'Get-AzContainerInstanceCapability', 'Get-AzContainerInstanceUsage', 'New-AzContainerGroupImageRegistryCredentialObject', 'New-AzContainerGroupPortObject', 'New-AzContainerGroupVolumeObject', 'New-AzContainerInstanceEnvironmentVariableObject', 'New-AzContainerInstanceInitDefinitionObject', 'New-AzContainerInstanceObject', 'New-AzContainerInstancePortObject', dan 'New-AzContainerInstanceVolumeMountObject'
* Mendukung parameter Analitik Log di 'New-AzContainerGroup' [#11117]
* Menambahkan dukungan untuk menentukan profil jaringan dan nama Azure File Share di 'New-AzContainerGroup' [#9993] [#12218]
* Menambahkan dukungan untuk menentukan variabel lingkungan sebagai SecureValue [#10110] [#10640]

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki masalah nama pengguna dan kata sandi di 'Import-AzContainerRegistryImage' [#14971]
* Memperbaiki operasi data plane (repositori, tag, manifes) gagal melintasi registri dalam satu sesi Powershell [#14849]

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan dukungan untuk RBAC data plane Sql, yang memungkinkan pembuatan, pembaruan, penghapusan, dan pengambilan Definisi Peran dan Penetapan Peran
  - Cmdlet berikut ditambahkan:
    - Get-AzCosmosDBSqlRoleDefinition, Get-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlRoleDefinition, New-AzCosmosDBSqlRoleAssignment,
    - Remove-AzCosmosDBSqlRoleDefinition, Remove-AzCosmosDBSqlRoleAssignment,
    - Update-AzCosmosDBSqlRoleDefinition, Update-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlPermission

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Meningkatkan versi api ke 01-02-2021-pratinjau.

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dukungan dalam pembuatan aplikasi fungsi untuk aplikasi fungsi Python 3.9 dan Node 14
* Menghapus dukungan dalam pembuatan aplikasi fungsi untuk aplikasi fungsi V2, Python 3.6, Node 8, dan Node 10
* Memperbarui parameter IdentityID dari string ke array string di Update-AzFunctionApp. Hal ini konsisten dengan New-AzFunctionApp yang memiliki parameter yang sama sebagai array string
* Memperbarui FullyQualifiedErrorId untuk versi Functions yang tidak valid dari FunctionsVersionIsInvalid ke FunctionsVersionNotSupported
* Saat membuat aplikasi fungsi Node.js, jika tidak ada versi runtime yang ditentukan, versi runtime default diatur ke 14, bukan 12

#### <a name="azkeyvault"></a>Az.KeyVault
* Menyediakan ukuran kunci untuk kunci RSA [#14819]

#### <a name="azkusto"></a>Az.Kusto
* Mengubah versi API ke stabil 01-01-2021

#### <a name="azmaintenance"></a>Az.Maintenance
* Mengubah versi API ke stabil 01-05-2021

#### <a name="azmigrate"></a>Az.Migrate
* Memperbaiki masalah di Initialize-AzMigrateReplicationInfrastructure.ps1

#### <a name="aznetwork"></a>Az.Network
* Memperbarui validasi untuk memungkinkan melewati nilai nol untuk parameter saDataSizeKilobytes
    - 'New-AzureRmIpsecPolicy'
* Menambahkan parameter opsional '-EdgeZone' ke cmdlet berikut:
    - 'New-AzNetworkInterface'
    - 'New-AzPublicIpAddress'
    - 'New-AzVirtualNetwork'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki masalah keamanan terkait pemulihan SQL, ini adalah perubahan berisiko yang diperlukan. TargetContainer menjadi wajib untuk Pemulihan Lokasi Alternatif.
* Menghapus alias cmdlet Set-AzRecoveryServicesBackupProperties, Set-AzRecoveryServicesBackupProperty didukung.
* Menghapus alias cmdlet Get-AzRecoveryServicesBackupJobDetails, Get-AzRecoveryServicesBackupJobDetail didukung.
* Menambahkan dukungan untuk pemindahan DS lintas langganan.
* Dukungan Azure Site Recovery untuk skenario pemulihan bencana VMware ke Azure menggunakan RCM sebagai sarana kontrol.

#### <a name="azresources"></a>Az.Resources
* Mengubah '-IdentifierUris' di 'New-AzADApplication' menjadi parameter opsional
* Menghapus 'DisplayName' ADApplication yang dibuat oleh 'New-AzADServicePrincipal'
* Memperbarui SDK ke 3.13.1-pratinjau untuk menggunakan versi API TemplateSpecs GA
* Menambahkan 'AdditionalProperties' ke PSADUser dan PSADGroup [#14568]
* Mendukung 'CustomKeyIdentifier' di 'New-AzADAppCredential' dan 'Get-AzADAppCredential' [#11457], [#13723]
* Mengubah 'MainTemplate' untuk ditampilkan oleh pemformat default untuk Versi Spesifikasi Templat

#### <a name="azsecurityinsights"></a>Az.SecurityInsights
* Rilis GA untuk `Az.SecurityInsights`

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menghapus perintah sertifikat kluster yang tidak digunakan lagi:
    - 'Add-AzServiceFabricClusterCertificate'
    - 'Remove-AzServiceFabricClusterCertificate'
* Mengubah model PSManagedService untuk menghindari penggunaan parameter properti langsung dari sdk.
* Menghapus parameter usang untuk cmdlet terkelola:
    - 'ReverseProxyEndpointPort'
    - 'InstanceCloseDelayDuration'
    - 'ServiceDnsName'
    - 'InstanceCloseDelayDuration'
    - 'DropSourceReplicaOnMove'
* Memperbaiki 'Update-AzServiceFabricReliability' untuk memperbarui dengan benar jumlah instans mesin virtual dari jenis node utama pada sumber daya kluster.

#### <a name="azsql"></a>Az.Sql
* Memperbarui dokumentasi 'Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline' untuk menyertakan contoh array terdefinisi dari array dengan satu array dalam.
* Menambahkan cmdlet 'Copy-AzSqlDatabaseLongTermRetentionBackup'
    - Menyalin cadangan LTR ke server yang berbeda
* Menambahkan cmdlet 'Update-AzSqlDatabaseLongTermRetentionBackup'
    - Memperbarui nilai Redundansi Penyimpanan Cadangan untuk cadangan LTR
* Menambahkan CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy ke 'Get-AzSqlDatabase', 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlDatabaseSecondary', 'Set-AzSqlDatabaseSecondary', 'New-AzSqlDatabaseCopy'
    - Mengubah nilai BackupStorageRedundancy menjadi CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy untuk mencerminkan nilai saat ini dan apa yang telah diminta jika perubahan dilakukan

#### <a name="azstorage"></a>Az.Storage
* Mendukung snapshot berbagi file
    - 'New-AzRmStorageShare'
    - 'Get-AzRmStorageShare'
    - 'Remove-AzRmStorageShare'
* Mendukung menghapus berbagi file dengan snapshotnya (disewakan dan tidak disewakan), secara default menghapus berbagi file akan gagal saat berbagi memiliki snapshot
    - 'Remove-AzRmStorageShare'
* Mendukung untuk Mengatur/Mendapatkan/Menghapus kebijakan inventaris blob
    - 'New-AzStorageBlobInventoryPolicyRule'
    - 'Set-AzStorageBlobInventoryPolicy'
    - 'Get-AzStorageBlobInventoryPolicy'
    - 'Remove-AzStorageBlobInventoryPolicy'
* Mendukung DefaultSharePermission dalam membuat/memperbarui akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung AllowCrossTenantReplication dalam membuat/memperbarui akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung pengaturan Kebijakan Replikasi Objek dengan SourceAccount/DestinationAccount sebagai Id sumber daya Akun penyimpanan
    - 'Set-AzStorageObjectReplicationPolicy'
* Mendukung pengaturan SasExpirationPeriod sebagai TimeSpan.Zero
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount
* Memastikan nama akun yang benar digunakan saat membuat info masuk akun
    - 'New-AzStorageContext'

#### <a name="azstoragesync"></a>Az.StorageSync
* Tidak menggunakan lagi 'Invoke-AzStorageSyncFileRecall'
    - Pelanggan seharusnya menggunakan 'Invoke-StorageSyncFileRecall', cmdlet yang dikirim dengan agen Azure File Sync.
* Menghapus fitur transfer data offline di 'New-AzStorageSyncServerEndpoint'.

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Mengubah versi API ke 01-04-2017-pratinjau
* Menambahkan dukungan Kluster StreamAnalytics

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'Set-AzAppServicePlan' untuk menyimpan Tag yang ada saat menambahkan Tag baru
* Memperbaiki 'Set-AzWebApp' untuk mengatur AppSettings
* memperbarui 'Set-AzWebAppSlot' untuk mengatur FtpsState
* Menambahkan dukungan untuk StaticSites.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @corichte, Memperbarui New-AzVirutalNetworkGatewayConnection Ex 1 (#14858)
* Hiroshi Yoshioka (@hyoshioka0128)
  * Kesalahan ketik "Azure SQL database"→"Azure SQL Database" (#14883)
  * Kesalahan ketik "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14891)
  * Kesalahan ketik "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14892)
  * Kesalahan ketik "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14902)
  * Kesalahan ketik "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14901)
  * Kesalahan ketik "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14900)
  * Kesalahan ketik "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14898)
  * Kesalahan ketik "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14899)
* Jay Zelos (@jzelos), Memperbarui contoh 3 untuk menggunakan parameter yang benar (#14852)
* @StevePantol, Memperbarui New-AzVMwarePrivateCloud.md (#14996)


## <a name="590---may-2021"></a>5.9.0 - Mei 2021
#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan 'AcrNameToAttach' di 'Set-AzAksCluster'. [#14692]
* Menambahkan dukungan 'AcrNameToDetach' di 'Set-AzAksCluster'. [#14693]
* Menambahkan 'Set-AzAksClusterCredential' untuk mereset ServicePrincipal dari kluster AKS yang ada.

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk Identitas yang Ditetapkan Pengguna dan bendera PublicNetworkAccess

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung SKU Standar/Premium AFD baru

#### <a name="azcompute"></a>Az.Compute
* Memperbarui cmdlet 'Set-AzVMDiskEncryptionExtension' untuk mendukung migrasi ekstensi Azure Disk Encryption dari dua langkah (versi dengan parameter input AAD) ke satu langkah (versi tanpa parameter input AAD).
    - Menambahkan parameter pengalihan '-Migrasi' untuk memicu alur kerja migrasi.
    - Menambahkan parameter pengalihan '-MigrationRecovery' untuk memicu alur kerja pemulihan untuk mesin virtual yang mengalami kegagalan setelah migrasi dari Azure Disk Encryption dua langkah.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan Identitas yang Ditetapkan Pengguna ke Data Factory.
* Memperbarui versi SDK .Net ADF ke 4.18.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memungkinkan parameter SecretVersion Enable-AzFrontDoorCustomDomainhttps menjadi opsional untuk mendukung rotasi otomatis bawa-sertifikat-Anda-sendiri

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -IncludeVersions' saat versi saat ini dinonaktifkan [#14740]
* Menampilkan kode kesalahan dan pesan saat memperbarui rahasia yang dibersihkan [#14800]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk Multiple IP per NIC untuk penyedia Azure ke Azure.
* Dukungan Azure Site Recovery untuk SqlServerLicenseType untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk Set ketersediaan untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk TargetVmSize untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk ResourceTagging untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk Set Skala Mesin Virtual untuk penyedia Azure ke Azure.
* Menambahkan dukungan untuk memulihkan mesin virtual disk yang tidak dikelola sebagai disk terkelola.

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter 'ObjectType' untuk 'New-AzRoleAssignment'

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Meningkatkan perintah Kluster Terkelola untuk menggunakan SDK Kluster Terkelola Service Fabric versi 1.0.0 yang menggunakan penyedia sumber daya service fabric versi-api 01-05-2021.
* 'New-AzServiceFabricManagedCluster' menambahkan parameter UpgradeCadence dan ZonalResiliency.
* 'New-AzServiceFabricManagedNodeType' menambahkan parameter DiskType, VmUserAssignedIdentity, IsStateless, dan MultiplePlacementGroup.
* 'New-AzServiceFabricManagedClusterService' dan 'Set-AzServiceFabricManagedClusterService' memberi tanda parameter untuk penghentian: InstanceCloseDelayDuration, DropSourceReplicaOnMove, dan ServiceDnsName. Mereka tidak didukung.

#### <a name="azresourcemover"></a>Az.ResourceMover
* Ketersediaan umum modul 'Az.ResourceMover'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan/pembaruan akun penyimpanan dengan KeyExpirationPeriod dan SasExpirationPeriod
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung pembuatan/pembaruan akun penyimpanan dengan enkripsi keyvault dan keyvault akses dengan identitas yang ditetapkan pengguna
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung EdgeZone dalam pembuatan akun penyimpanan
    - 'New-AzStorageAccount'
* Memperbaiki masalah menghapus blob yang tidak dapat diubah akan meminta pesan yang salah.
    - 'Remove-azStorageAccount'
* Memungkinkan pembaruan properti KeyVault Akun Penyimpanan dengan membersihkan Keyversion guna mengaktifkan rotasi otomatis kunci [#14769]
    - 'Set-AzStorageAccount'
* Menambahkan pesan peringatan perubahan berisiko untuk perubahan berisiko cmdlet yang akan datang
    - 'Remove-AzRmStorageShare'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Thomas Lee (@doctordns), Memperbarui Get-AzEnvironment.md (#14704)
* Fabian (@FullByte), Contoh dengan parameter yang salah (salah ketik) (#14743)
* @gradinDotCom, Memperbarui Get-AzNetworkWatcherNextHop.md (#14813)
* Dr Greg Low (@greglow-sdu), Memperbarui Get-AzSqlServerDnsAlias.md (#14737)
* Prateek Singh (@PrateekKumarSingh)
  * memperbaiki kesalahan ketik (#14779)
  * memperbaiki kesalahan ketik (#14773)
* Remco Eissing (@remcoeissing)
  * Memperbaiki kesalahan ketik di Restore-AzApiManagement (#14770)
  * Contoh 2 untuk menggunakan New-AzPolicyExemption (#14716)
* @sharma224
  * Perubahan identitas pengguna (#14803)
  * Mendukung kunci yang dikelola Pelanggan (#14680)
* Yannick Dils (@yannickdils), Memperbarui Penjelasan lokasi (#14719)


## <a name="580---april-2021"></a>5.8.0 - April 2021
#### <a name="azaccounts"></a>Az.Accounts
* Fallback ke konteks valid pertama jika kunci konteks default saat ini adalah 'Default' yang tidak valid

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk Enkripsi Kunci Terkelola Pelanggan dengan Identitas yang Ditetapkan Sistem
* Memperbaiki masalah yang menonaktifkan jadwal penyebaran pembaruan jika jadwal dibuat ulang dengan nama yang sama

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki bug saat 1 disk data dilampirkan ke VMSS untuk Remove-AzVmssDataDisk [#13368]
* Menambahkan cmdlet baru untuk mendukung cmdlet terkait TrustedLaunch:
    - 'Set-AzVmSecurityProfile'
    - 'Set-AzVmUefi'
    - 'Set-AzVmssSecurityProfile'
    - 'Set-AzVmssUefi'
* Mengedit nilai default untuk parameter Ukuran dalam cmdlet New-AzVM dari Standard_DS1_v2 menjadi Standard_D2s_v3.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki bug di 'Get-AzContainerRegistryManifest' yang menunjukkan nama gambar yang salah

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung untuk mendapatkan vmsize default dari backend jika pelanggan tidak menyediakan parameter terkait: '-WorkerNodeSize', '-HeadNodeSize', '-ZookeeperNodeSize', '-EdgeNodeSize', '-KafkaManagementNodeSize'.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Menambahkan dukungan untuk Acr LoginServers

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -AsPlainText' jika rahasia tidak ditemukan [#14645]

#### <a name="azmigrate"></a>Az.Migrate
* Nullref Bug diperbaiki di server yang ditemukan dan menginisialisasi commandlets infrastruktur replikasi.

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan cmdlet untuk mendapatkan kategori pengaturan diagnostik untuk langganan
    - 'Get-AzSubscriptionDiagnosticSettingCategory'
* Mendukung operasi pengaturan diagnostik langganan dengan parameter baru: SubscriptionId
    - 'Get-AzDiagnosticSetting'
    - 'New-AzDiagnosticSetting'
    - 'Remove-AzDiagnosticSetting'
* Mendukung parameter 'AutoMitigate' dalam properti aturan pemberitahuan metrik. Bendera menunjukkan apakah peringatan harus diselesaikan secara otomatis atau tidak.

#### <a name="azresources"></a>Az.Resources
* Menambahkan peringatan perubahan berisiko yang akan datang di bawah cmdlet, karena nilai parameter 'IdentifierUris' akan memerlukan domain terverifikasi.
  - 'New-AzADApplication'
  - 'Update-AzADApplication'
  - 'New-AzADServicePrincipal'
  - 'Update-AzADServicePrincipal'
* Mengabaikan pesan peringatan Bicep dalam aliran kesalahan jika exitcode sama dengan nol.

#### <a name="azsql"></a>Az.Sql
* Menambahkan peringatan perubahan berisiko output cmdlet ke berikut ini:
    - 'New-AzSqlDatabase'
    - 'Get-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
    - 'Remove-AzSqlDatabase'
    - 'New-AzSqlDatabaseSecondary'
    - 'Remove-AzSqlDatabaseSecondary'
    - 'Get-AzSqlDatabaseReplicationLink'
    - 'New-AzSqlDatabaseCopy'
    - 'Set-AzSqlDatabaseSecondary'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki penyalinan blob gagal dengan konteks sumber sebagai Oauth [#14662]
    -  'Start-AzStorageBlobCopy'

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Menambahkan pesan peringatan perubahan berisiko yang akan datang ke semua cmdlet karena perubahan parameter yang akan datang.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrei Zhukouski (@BurgerZ), Memperbaiki kesalahan ketik (#14575)
* Mark Allison (@markallisongit), Memperbarui Invoke-AzSqlInstanceFailover.md (#14603)


## <a name="570---march-2021"></a>5.7.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki pesan peringatan yang salah di Windows PowerShell [#14556]
* Mengatur variabel Azure Environment 'AzureKeyVaultServiceEndpointResourceId' sesuai dengan nilai 'AzureKeyVaultDnsSuffix' saat menemukan lingkungan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah untuk memulai runbook Python3 dengan parameter

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.15.0

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki 'New-AzServiceBusAuthorizationRuleSASToken' menampilkan token yang tidak valid. [#12975]

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui model dan SDK Manajemen IoT Hub ke versi 3.0.0 (versi-api 01-03-2020)

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung desain API baru yang akan datang untuk 'Export-AzKeyVaultSecurityDomain'
* Memperbaiki beberapa kesalahan ketik dalam pesan cmdlet [#14341]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk menggantikan nama produk lama 'perute virtual' dengan nama baru 'server rute' di masa depan.
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - Menambahkan peringatan atribut penghentian ke cmdlet lama.
* Memperbarui 'set-azExpressRouteGateway' untuk memungkinkan parameter -MinScaleUnits tanpa menentukan -MaxScaleUnits
* Memperbarui cmdlet untuk mengaktifkan pengaturan VpnLinkConnectionMode di VpnSiteLinkConnections.
    - 'New-AzVpnSiteLinkConnection'
    - 'Update-AzVpnConnection'
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Tautan Situs VPN.
    - 'Get-VpnSiteLinkConnectionIkeSa'
* Menambahkan cmdlet baru untuk mereset Koneksi Gateway Virtual Network.
    - 'Reset-AzVirtualNetworkGatewayConnection'
* Menambahkan cmdlet baru untuk mereset Koneksi Tautan Situs Vpn.
    - 'Reset-VpnSiteLinkConnection'
* Memperbarui cmdlet untuk mengaktifkan pengaturan parameter opsional -TrafficSelectorPolicies
    - 'New-AzVpnConnection'
    - 'Update-AzVpnConnection'
* Memperbaiki bug untuk memperbarui vpnServerConfiguration.
* Menambahkan scenarioTest untuk VWAN multi-otorisasi p2s.
* Menambahkan dukungan fitur multi-otorisasi untuk VNG
    - 'Get-AzVpnClientConfiguration'
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Pemulihan Lintas Zonal untuk mesin virtual terkelola.

#### <a name="azredisenterprisecache"></a>Az.RedisEnterpriseCache
* Versi GA dari Az.RedisEnterpriseCache

#### <a name="azresources"></a>Az.Resources
* Mengarahkan pesan bisep ke aliran verbose
* Menghapus logika menyalin file templat Bicep ke folder temp.
* Menambahkan dukungan jenis sumber daya pembebasan kebijakan
* Memperbaiki fungsi What-If saat menggunakan parameter '-QueryString'.
* Menormalisasi '-QueryString' yang dimulai dengan '?' untuk skenario yang melibatkan parameter dinamis.

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki 'New-AzServiceBusAuthorizationRuleSASToken' menampilkan token yang tidak valid. [#12975]

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan parameter 'VMImagePublisher', 'VMImageOffer', 'VMImageSku', 'VMImageVersion' ke 'Add-AzServiceFabricNodeType' untuk memfasilitasi pembuatan gambar OS alternatif yang mudah untuk jenis node baru.
* Menambahkan parameter 'IsPrimaryNodeType' ke 'Add-AzServiceFabricNodeType' untuk dapat membuat jenis node utama tambahan, untuk tujuan transisi jenis node utama ke yang lain dalam kasus migrasi OS.
* 'Add-AzServiceFabricNodeType' sekarang menyalin ekstensi LinuxDiagnostic dengan benar. Ia sebelumnya tidak berfungsi untuk Linux.
* 'Add-AzServiceFabricNodeType' sekarang menyalin pemetaan port NAT masuk penyeimbang beban RDP/SSH dengan benar ke jenis node baru.
* Menambahkan templat untuk 'UbuntuServer1804' untuk membuat kluster Ubuntu 18.04 menggunakan 'New-AzServiceFabricCluster'.
* 'Remove-AzServiceFabricNodeType' salah memblokir jenis node ketahanan Perunggu untuk penghapusan, dan ini telah diperbarui untuk hanya memblokir ketika tingkat ketahanan Perunggu berbeda antara jenis node SF dan pengaturan VMSS.
* Menambahkan cmdlet 'Update-AzServiceFabricVmImage' untuk memperbarui jenis paket runtime SF yang dikirimkan. Ini harus diubah saat bermigrasi dari Ubuntu 16 ke 18.
* Menambahkan cmdlet 'Update-AzServiceFabricNodeType' untuk memperbarui properti jenis node kluster. Untuk saat ini, ini hanya digunakan untuk memperbarui apakah jenis node utamanya melalui parameter bool '-IsPrimaryNodeType False'.
* 'Update-AzServiceFabricReliability' sekarang dapat memperbarui tingkat keandalan ketika kluster memiliki lebih dari satu jenis node utama. Untuk melakukan ini, nama jenis node disediakan melalui parameter -NodeType baru.
* Menambahkan cmdlet baru untuk aplikasi terkelola:
    - 'New-AzServiceFabricManagedClusterApplication'
    - 'Get-AzServiceFabricManagedClusterApplication'
    - 'Set-AzServiceFabricManagedClusterApplication'
    - 'Remove-AzServiceFabricManagedClusterApplication'
    - 'New-AzServiceFabricManagedClusterApplicationType'
    - 'Get-AzServiceFabricManagedClusterApplicationType'
    - 'Set-AzServiceFabricManagedClusterApplicationType'
    - 'Remove-AzServiceFabricManagedClusterApplicationType'
    - 'New-AzServiceFabricManagedClusterApplicationTypeVersion'
    - 'Get-AzServiceFabricManagedClusterApplicationTypeVersion'
    - 'Set-AzServiceFabricManagedClusterApplicationTypeVersion'
    - 'Remove-AzServiceFabricManagedClusterApplicationTypeVersion'
    - 'New-AzServiceFabricManagedClusterService'
    - 'Get-AzServiceFabricManagedClusterService'
    - 'Set-AzServiceFabricManagedClusterService'
    - 'Remove-AzServiceFabricManagedClusterService'
* Meningkatkan perintah Kluster Terkelola untuk menggunakan SDK Kluster Terkelola Service Fabric versi 1.0.0-beta.1 yang menggunakan penyedia sumber daya service fabric versi-api 01-01-2021-pratinjau.

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet 'New-AzSqlServerTrustGroup'
* Menambahkan cmdlet 'Remove-AzSqlServerTrustGroup'
* Menambahkan cmdlet 'Get-AzSqlServerTrustGroup'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah mencantumkan akun dari grup sumber daya tidak mau menggunakan nextlink
    - 'Get-AzStorageAccount'
* Mendukung ChangeFeedRetentionInDays saat Mengaktifkan ChangeFeed di Blob service
    - 'Update-AzStorageBlobServiceProperty'

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'Add-AzWebAppAccessRestrictionRule' untuk memungkinkan semua Tag Layanan yang didukung dan memvalidasi terhadap API Tag Layanan.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Freddie Sackur (@fsackur), Memperbaiki token SAS yang tidak valid dari New-AzServiceBusAuthorizationRuleSASToken dan New-AzEventHubAuthorizationRuleSASToken (#14535)
* Serafín Martín (@infoTrainingym), Parameter tidak diketahui (#14515)
* João Carlos Ferra de Almeida (@Jalmeida1994), Memperbarui Get-AzAksNodePool.md (#14503)
* Liam Barnett (@liambarnett), Memperbaiki 3 kesalahan ketik dalam dokumen (#14335)
* @sbojjawar-Msft, Memperbarui Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline.md (#14432)
* Yannick Dils (@yannickdils), Menghapus grup sumber daya dari get-azloadbalancer ini menghasilkan pembaruan wilayah/zona. (#14417)


## <a name="560---march-2021"></a>5.6.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Meningkatkan Azure.Identity untuk memperbaiki masalah Connect-AzAccount gagal saat info masuk ADFS digunakan [#13560]

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah string tidak dapat diserialisasi dengan benar. [#14215]
* Menambahkan Dukungan untuk Jenis Runbook Python3

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EnableHotpatching' ke cmdlet 'Set-AzVMOperatingSystem' untuk mesin Windows.
* Menambahkan parameter '-PatchMode' ke set parameter Linux di cmdlet 'Set-AzVMOperatingSystem'.
* [Perubahan yang Berisiko] Perubahan yang berisiko untuk pengguna dalam pratinjau publik untuk fitur Patching Tamu Mesin Virtual.
    - Menghapus properti 'RebootStatus' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Menghapus properti 'StartedBy' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Mengganti nama properti 'Kbid' menjadi 'KbId' di objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineSoftwarePatchProperties'.
    - Mengganti nama properti 'patches' menjadi 'availablePatches' di objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineAssessPatchesResult'.
    - Mengganti nama objek 'Microsoft.Azure.Management.Compute.Models.SoftwareUpdateRebootBehavior' menjadi 'Microsoft.Azure.Management.Compute.Models.VMGuestPatchRebootBehavior'.
    - Mengganti nama objek 'Microsoft.Azure.Management.Compute.Models.InGuestPatchMode' menjadi 'Microsoft.Azure.Management.Compute.Models.WindowsVMGuestPatchMode'.
* [Perubahan yang Berisiko] Menghapus semua cmdlet 'ContainerService'. API Layanan Kontainer tidak digunakan lagi pada Januari 2020.
    - 'Add-AzContainerServiceAgentPoolProfile'
    - 'Get-AzContainerService'
    - 'New-AzContainerService'
    - 'New-AzContainerServiceConfig'
    - 'Remove-AzContainerService'
    - 'Remove-AzContainerServiceAgentPoolProfile'
    - 'Update-AzContainerService'

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki autentikasi untuk `Connect-AzContainerRegistry`

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan NetworkAclBypass dan NetworkAclBypassResourceIds untuk cmdlet Akun Database.
* Memperkenalkan parameter ServerVersion ke Update-AzCosmosDBAccount.
* Memperkenalkan BackupInterval dan BackupRetention untuk cmdlet Akun Database

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.14.0

#### <a name="azmigrate"></a>Az.Migrate
* Az.Migrate GA
* Memasukkan Initialize-AzMigrateReplicationInfrastructure sebagai cmdlet dalam modul Az.Migrate, dari skrip eksternal yang dijalankan saat ini.
* Membuat beberapa parameter New-AzMigrateServerReplication, New-AzMigrateDiskMapping tidak sensitif huruf besar atau kecil.
* Menambahkan dukungan untuk perubahan appliance skala, untuk menangani kunci V3 baru.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan pemeriksaan null untuk akun penyimpanan target di pemulihan FileShare.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk penyebaran sumber daya Azure dalam bahasa Bicep
* Memperbaiki masalah terkait penyebaran TemplateSpec di 'New-AzTenantDeployment' dan 'New-AzManagementGroupDeployment'
* Menambahkan dukungan untuk parameter '-QueryString' di cmdlet 'Test-Az*Deployments'
* Memperbaiki masalah terkait parameter dinamis saat 'New-Az*Deployments' digunakan dengan '-QueryString'
* Menambahkan dukungan untuk parameter '-TemplateParameterObject' saat menggunakan parameter '-TemplateSpecId' di cmdlet 'New-Az*Deployments'
* Memperbaiki pesan kesalahan yang tidak akurat yang diterima saat mencoba menyebarkan spesifikasi templat yang tidak ada

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan ke Microsoft.Azure.Management.Storage 19.0.0, untuk mendukung API versi baru 01-01-2021.
* Mendukung aturan akses sumber daya di NetworkRuleSet
    - 'Update-AzStorageAccountNetworkRuleSet'
    - 'Add-AzStorageAccountNetworkRule'
    - 'Remove-AzStorageAccountNetworkRule'
* Mendukung versi Blob dan Menambahkan jenis Blob dalam Kebijakan Manajemen
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyFilter'
    - 'Set-AzStorageAccountManagementPolicy'
* Mendukung pembuatan/pembaruan akun dengan AllowSharedKeyAccess
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung pembuatan Cakupan Enkripsi dengan RequireInfrastructureEncryption
    - 'New-AzStorageEncryptionScope'
* Mendukung penyalinan blob blok secara sinkron, dengan cakupan enkripsi
    - 'Copy-AzStorageBlob'
* Memperbaiki masalah Get-AzStorageBlobContent menggunakan char pemisah direktori yang salah di Linux dan MacOS [#14234]

#### <a name="azwebsites"></a>Az.Websites
* Memperkenalkan opsi untuk memberikan batas waktu kustom untuk 'Publish-AzWebApp'
* Menambahkan dukungan untuk Lingkungan App Service
    - 'New-AzAppServiceEnvironment'
    - 'Remove-AzAppServiceEnvironment'
    - 'Get-AzAppServiceEnvironment'
    - 'New-AzAppServiceEnvironmentInboundServices'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @alunmj, Ejaan kecil, perubahan pemformatan (#14155)
* @chakra146, Memperbarui Add-AzLoadBalancerInboundNatPoolConfig.md (#14231)
* Martin Ehrnst (@ehrnst), Memperbaiki kesalahan ketik di cmdlet (#14112)
* Jan David Narkiewicz (@jdnark)
  * Contoh yang digunakan New-AzAks yaitu cmdlet warisan dan alias untuk New-AzAksCluster. Mengubah contoh untuk menggunakan New-AzAksCluster yang merupakan cmdlet yang ditargetkan halaman dokumentasi ini. (#14088)
  * Jenis fox: mengubah SshKeyVaule menjadi SshKeyValue (#14087)
* Ivan Kulezic (@kukislav), Menambahkan contoh konfigurasi pemeliharaan mi sql (#14216)
* @webguynj, Memperbarui Set-AzNetworkSecurityRuleConfig.md (#14176)
* Yannick Dils (@yannickdils), Menambahkan cmdline tambahan ke contoh yang menerapkan perubahan pada penyeimbang beban (#14185)


## <a name="550---february-2021"></a>5.5.0 - Februari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Melacak kode CloudError dalam pengecualian
* Mengangkat peristiwa 'ContextCleared' ketika 'Clear-AzContext' dieksekusi

#### <a name="azaks"></a>Az.Aks
* Menyempurnakan pesan kesalahan dari kegagalan cmdlet.
* Meningkatkan penanganan pengecualian untuk menggunakan pengecualian terkait Azure PowerShell.
* Memperbaiki masalah yang tidak dapat digunakan pengguna sebagai perwakilan layanan yang disediakan untuk membuat kluster Kubernetes. [#13938]

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah pemrosesan 'PSCustomObject' dan 'Array'.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EnableAutomaticUpgrade' ke 'Set-AzVmExtension' dan 'Add-AzVmssExtension'.
* Menghapus parameter FilterExpression dari dokumentasi cmdlet 'Get-AzVMImage'.
* Menambahkan pesan penghentian ke cmdlet ContainerService:
    - 'Add-AzureRmContainerServiceAgentPoolProfileCommand'
    - 'Get-AzContainerService'
    - 'New-AzContainerService'
    - 'New-AzContainerServiceConfig'
    - 'Remove-AzContainerService'
    - 'Remove-AzContainerServiceAgentPoolProfile'
    - 'Update-AzContainerService'
* Menambahkan parameter '-BurstingEnabled' ke 'New-AzDiskConfig' dan 'New-AzDiskUpdateConfig'
* Menambahkan parameter '-GroupByApplicationId' dan '-GroupByUserAgent' ke cmdlet 'Export-AzLogAnalyticThrottledRequest' dan 'Export-AzLogAnalyticRequestRateByInterval'.
* Menambahkan set parameter 'VMParameterSet' ke cmdlet 'Get-AzVMExtension'. Menambahkan parameter baru '-VM' ke set parameter ini.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Menambahkan cmdlet ke operasi repositori, manifes, dan tag yang didukung:
    - 'Get-AzContainerRegistryRepository'
    - 'Update-AzContainerRegistryRepository'
    - 'Remove-AzContainerRegistryRepository'
    - 'Get-AzContainerRegistryManifest'
    - 'Update-AzContainerRegistryManifest'
    - 'Remove-AzContainerRegistryManifest'
    - 'Get-AzContainerRegistryTag'
    - 'Update-AzContainerRegistryTag'
    - 'Remove-AzContainerRegistryTag'

#### <a name="azdatabricks"></a>Az.Databricks
Mendukung -EnableNoPublicIP saat membuat ruang kerja Databricks

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan FrontDoorId ke properti
* Menambahkan Pengecualian JSON dan dukungan RequestBodyCheck ke aturan terkelola

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan parameter baru '-EnableComputeIsolation' dan '-ComputeIsolationHostSku' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur isolasi komputasi
* Menambahkan properti 'ComputeIsolationProperties' dan 'ConnectivityEndpoints' di kelas AzureHDInsightCluster.

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung penentuan jenis kunci dan nama kurva saat mengimpor kunci melalui file BYOK

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk menggantikan nama produk lama 'perute virtual' dengan nama baru 'server rute' di masa depan.
    - 'New-AzRouteServer'
    - 'Get-AzRouteServer'
    - 'Remove-AzRouteServer'
    - 'Update-AzRouteServer'
    - 'Get-AzRouteServerPeer'
    - 'Add-AzRouteServerPeer'
    - 'Update-AzRouteServerPeer'
    - 'Remove-AzRouteServerPeer'
    - Menambahkan peringatan atribut penghentian ke cmdlet lama.
* Perbaikan bug di ExpressRouteLink MacSecConfig. Menambahkan properti baru 'SciState' ke 'PSExpressRouteLinkMacSecConfig'
* Memperbarui daftar format dan tampilan tabel format untuk Get-AzVirtualNetworkGatewayConnectionIkeSa

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menarik perubahan yang dilakukan di powershell yang meningkatkan batas baris permintaan. Menghapus pernyataan yang salah tentang mendukung paginasi

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memodifikasi batas validasi kebijakan sesuai layanan cadangan.
* Menambahkan Redundansi Zona untuk Brankas Layanan Pemulihan.
* Dukungan Azure Site Recovery untuk grup penempatan Kedekatan untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk Zona Ketersediaan untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk UseManagedDisk untuk penyedia HyperV ke Azure

#### <a name="azresources"></a>Az.Resources
* Menghapus jenis prinsipal pada New-AzRoleAssignment dan Set-AzRoleAssignment karena pemetaan saat ini memutus skenario tertentu

#### <a name="azsql"></a>Az.Sql
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlElasticPool' dan 'Set-AzSqlElasticPool'
* Memperbaiki regresi di 'Set-AzSqlServerAudit' saat argumen PredicateExpression disediakan

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaturan RoutingPreference dalam pembuatan/pembaruan Akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Meningkatkan Azure.Storage.Blobs ke 12.8.0
* Meningkatkan Azure.Storage.Files.Shares ke 12.6.0
* Meningkatkan Azure.Storage.Files.DataLake ke 12.6.0

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk Mengimpor sertifikat brankas kunci ke WebApp.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Memperbarui Set-AzEventHub.md (#13921)
* Christoph Bergmeister [MVP] (@bergmeister), Set-AzDataLakeGen2AclRecursive.md - Memperbaiki kesalahan ketik (directiry -> directory) (#14082)
* Alexander Schmidt (@devdeer-alex), Memperbaiki hyperlink rusak ke pedoman kontribusi (#14009)
* @JiangYuchun, Memperbarui Get-AzApplicationGatewayAuthenticationCertificate.md (#13972)
* Sebastian Olsen (@Spacebjorn), Mengoreksi contoh perintah (#13901)


## <a name="540---january-2021"></a>5.4.0 - Januari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menampilkan id permintaan klien yang benar pada pesan debug [#13745]
* Menambahkan jenis pengecualian Azure PowerShell umum
* Mendukung API penyimpanan 01-06-2019

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah di mana deskripsi tidak diisi untuk jadwal manajemen pembaruan

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Ketersediaan umum modul 'Az.CosmosDB'
* Membatasi cmdlet New-AzCosmosDBAccount untuk melakukan panggilan pembaruan ke Akun Database yang ada.
* Memperkenalkan AnalyticalStorageTTL di SqlContainer.

#### <a name="aziothub"></a>Az.IotHub
* Memperbaiki regresi mengenai pembuatan token SAS

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki masalah dalam modul Manajemen Rahasia

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki masalah 'Get-AzLogicAppTriggerHistory' dan 'Get-AzLogicAppRunAction' hanya mengambil halaman pertama hasil [#9141]

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan cmdlet untuk aturan pengumpulan data:
    - 'Get-AzDataCollectionRule'
    - 'New-AzDataCollectionRule'
    - 'Set-AzDataCollectionRule'
    - 'Update-AzDataCollectionRule'
    - 'Remove-AzDataCollectionRule'
* Menambahkan cmdlet untuk asosiasi aturan pengumpulan data
    - 'Get-AzDataCollectionRuleAssociation'
    - 'New-AzDataCollectionRuleAssociation'
    - 'Remove-AzDataCollectionRuleAssociation'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk CRUD VpnGatewayNATRule.
    - 'New-AzAzVpnGatewayNatRule'
    - 'Update-AzAzVpnGatewayNatRule'
    - 'Get-AzAzVpnGatewayNatRule'
    - 'Remove-AzAzVpnGatewayNatRule'
* Memperbarui cmdlet untuk mengatur NATRule pada sumber daya VpnGateway dan mengaitkannya dengan sumber daya VpnSiteLinkConnection.
    - 'New-AzVpnGateway'
    - 'Update-AzVpnGateway'
    - 'New-AzVpnSiteLinkConnection'
* Memperbarui cmdlet untuk mengaktifkan pengaturan ConnectionMode pada Koneksi Gateway Virtual Network.
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Memperbarui cmdlet 'New-AzFirewallPolicyApplicationRule':
    - Menambahkan parameter TargetUrl
    - Menambahkan parameter TerminateTLS
* Menambahkan cmdlet baru untuk Fitur Premium Azure Firewall
    - 'New-AzFirewallPolicyIntrusionDetection'
    - 'New-AzFirewallPolicyIntrusionDetectionBypassTraffic'
    - 'New-AzFirewallPolicyIntrusionDetectionSignatureOverride'
* Menambahkan cmdlet New-AzFirewallPolicy:
    - Menambahkan parameter -SkuTier
    - Menambahkan parameter -Identitas
    - Menambahkan parameter -UserAssignedIdentityId
    - Menambahkan parameter -IntrusionDetection
    - Menambahkan parameter -TransportSecurityName
    - Menambahkan parameter -TransportSecurityKeyVaultSecretId
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Gateway Virtual Network.
    - 'Get-AzVirtualNetworkGatewayConnectionIkeSa'
* Menambahkan beberapa dukungan Autentikasi untuk p2sVpnGateway
    - Memperbarui New-AzVpnServerConfiguration dan Update-AzVpnServerConfiguration untuk memungkinkan beberapa parameter autentikasi diatur.
* Memperbarui cmdlet 'New-AzVpnGateway' dan 'New-AzP2sVpnGateway':
    - Menambahkan parameter EnableRoutingPreferenceInternetFlag

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan fitur Pemulihan Lintas Wilayah.
* Memblokir untuk mendapatkan konfigurasi beban kerja saat item target merupakan grup ketersediaan.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk parameter -QueryString di cmdlet New-Az*Deployments

#### <a name="azsql"></a>Az.Sql
* Membuat cmdlet 'Start-AzSqlInstanceDatabaseLogReplay' sinkron, menambahkan bendera -AsJob

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki ContinuationToken yang tidak pernah null saat mencantumkan blob dengan -IncludeVersion
    - 'Get-AzStorageBlob'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk sertifikat Terkelola App Service
    - 'New-AzWebAppCertificate'
    - 'Remove-AzWebAppCertificate'
* Memperbaiki masalah yang menyebabkan Kata Sandi Docker dihapus dari appsetting di 'Set-AzWebApp' dan 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Ivan Akcheurov (@ivanakcheurov), Memperbarui Set-AzSecurityWorkspaceSetting.md (#13877)
* @javiermarasco, Memperbarui contoh (#13837)
* @jhaprakash26, Memperbarui Set-AzVirtualNetwork.md ( #13857)
* Michael Holmes (@MichaelHolmesWP), Memperbarui New-AzStorageTableStoredAccessPolicy.md (#13871)
* Michael James (@mikejwhat), Memungkinkan Get-AzLogicAppTriggerHistory dan Get-AzLogicAppRunAction untuk menampilkan lebih dari 30 hasil (#13846)
* @Willem-J-an, memperbaiki bug yang menyebabkan Kata Sandi Docker dihapus dari appsettings di Set-AzWebApp(Slot) (#13866)


## <a name="530---december-2020"></a>5.3.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah proksi Http tidak dihormati di Windows PowerShell [#13647]
* Meningkatkan log debug dari operasi yang berjalan lama di modul yang dihasilkan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah parameter 'Start-AzAutomationRunbook' tidak dapat mengonversi string terbungkus PSObject ke string JSON [#13240]
* Memperbaiki pelengkap lokasi untuk cmdlet New-AzAutomationUpdateManagementAzureQuery

#### <a name="azcompute"></a>Az.Compute
* Parameter baru 'VM' dalam set parameter baru 'VMParameterSet' ditambahkan ke cmdlet 'Get-AzVMDscExtensionStatus' dan 'Get-AzVMDscExtension'.
* Cmdlet 'New-AzSnapshot' yang diedit untuk memeriksa rekam jepret yang ada dengan nama yang sama dalam grup sumber daya yang sama.
    - Melemparkan kesalahan jika ada rekam jepret duplikat.

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki masalah yang dapat menyebabkan 'New-AzDatabricksVNetPeering' kembali sebelum sepenuhnya disediakan (https://github.com/Azure/autorest.powershell/issues/610)

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki perintah 'Invoke-AzDataFactoryV2Pipeline' untuk masalah SupportsShouldProcess

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan properti StartVMOnConnect ke hostpool.

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan properti: Fqdn dan EffectiveDiskEncryptionKeyUrl di kelas AzureHDInsightHostInfo.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan parameter baru '-AsPlainText' ke 'Get-AzKeyVaultSecret' untuk langsung menampilkan rahasia dalam teks biasa [#13630]
* Mendukung pemulihan selektif kunci dari pencadangan penuh HSM terkelola [#13526]
* Memperbaiki beberapa masalah kecil [#13583] [#13584]
* Menambahkan objek ditampilkan yang hilang dari 'Get-Secret' dalam modul SecretManagement
* Memperbaiki masalah yang dapat menyebabkan brankas dibuat tanpa kebijakan akses default [#13687]

#### <a name="azkusto"></a>Az.Kusto
* Memperbarui versi API ke 18-09-2020.

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki masalah dalam menghapus cmdlet koneksi dan peering untuk skenario ExpressRouteCircuit
    - 'Remove-AzExpressRouteCircuitPeeringConfig' dan 'Remove-AzExpressRouteCircuitConnectionConfig'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan dukungan untuk menampilkan hasil terpaginasi untuk Get-AzPolicyState

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Mengaktifkan fitur softdelete untuk SQL.
* Memperbaiki pemulihan AG SQL dan menghapus pemeriksaan nama kontainer.
* Mengubah format nama kontainer untuk item cadangan Azure Files.
* Menambahkan dukungan fitur CMK untuk brankas layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah pengecualian NullRef di 'New-AzureManagedApplication' dan 'Set-AzureManagedApplication'.
* Memperbarui SDK Azure Resource Manager SDK untuk menggunakan DeploymentScripts GA versi-api terbaru: 01-10-2020.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki 'Add-AzServiceFabricNodeType'. Menambahkan jenis node ke kluster service fabric sebelum membuat set skala mesin virtual.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki deskripsi parameter untuk perintah 'InstanceFailoverGroup'.
* Memperbarui logika di mana schemaName, tableName, dan columnName sedang diekstraksi dari id perintah Klasifikasi Data SQL.
* Memperbaiki bidang StatusMessage dan Status di 'Get-AzSqlDatabaseImportExportStatus' agar sesuai dengan dokumentasi
* Menambahkan cmdlet audit operasi dukungan Microsoft (DevOps): Get-AzSqlServerMSSupportAudit, Set-AzSqlServerMSSupportAudit, Remove-AzSqlServerMSSupportAudit

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan/pembaruan/pendapatan/pencantuman EnkripsiSkop Akun penyimpanan
    - 'New-AzStorageEncryptionScope'
    - 'Update-AzStorageEncryptionScope'
    - 'Get-AzStorageEncryptionScope'
* Mendukung pembuatan kontainer dan mengunggah blob dengan pengaturan Cakupan Enkripsi
    - 'New-AzRmStorageContainer'
    - 'New-AzStorageContainer'
    - 'Set-AzStorageBlobContent'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andreas Wolter (@AndreasWolter), menghapus bahasa pemasaran, filter contoh yang lebih baik (#13671)
* Tidjani Belmansour (@BelRarr), Memperbarui Get-AzBillingInvoice.md (#13634)
* David Klempfner (@DavidKlempfner)
  * Memperbaiki kesalahan ejaan ( #13677 )
  * Memperbarui PSMetricNoDetails.cs (#13676)
* @kilobyte97, perbaikan bug untuk menghapus cmdlet untuk menghapus konfigurasi ( #13655 )
* @kongou-ae, Memperbarui Set-AzFirewall.md (#13727)
* @MasterKuat, Memperbaiki swap antara judul dan kode dalam dokumentasi (#13666)
* NickT (@nukeulis), Memperbarui Set-AzContext.md (#13702)
* @PaulHCode, Memperbarui Start-AzJitNetworkAccessPolicy.md - Memperbaiki Contoh untuk menampilkan cmdlet yang tepat yang ditunjukkan (#13713)
* Ryan Borstelmann (@ryanborMSFT), Menghapus ID Langganan (#13715)
* Shashikant Shakya (@shshakya), Memperbarui Set-AzSqlDatabase.md (#13674)
* Sebastian Olsen (@Spacebjorn), Memperbarui Get-AzRecoveryServicesBackupItem.md (#13719)

## <a name="520---december-2020"></a>5.2.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Berhasil mengurai waktu ExpiresOn dari token mentah jika tidak bisa mendapatkan dari pustaka yang mendasarinya
* Meningkatkan pesan peringatan jika autentikasi Interaktif tidak tersedia

#### <a name="azapimanagement"></a>Az.ApiManagement
* [Perubahan yang berisiko] 'New-AzApiManagementProduct' secara default tidak memiliki batas langganan.

#### <a name="azcompute"></a>Az.Compute
* Mengedit Get-AzVm untuk memfilter berdasarkan '-Nama' sebelum memeriksa pembatasan karena terlalu banyak sumber daya.
* Cmdlet baru 'Start-AzVmssRollingExtensionUpgrade'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Mendukung parameter 'Name' untuk dan nilai dari input alur untuk 'Get-AzContainerRegistryUsage' [#13605]
* Memperbaiki pengecualian untuk 'Koneksi-AzContainerRegistry'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.13.0

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Menambahkan dukungan untuk kunci yang dikelola pelanggan

#### <a name="aziothub"></a>Az.IotHub
* Memperbaiki masalah token SAS.

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung 'all' sebagai opsi saat mengatur kebijakan akses brankas kunci
* Mendukung versi baru modul SecretManagement [#13366]
* Mendukung ByteArray, String, PSCredential dan Hashtable untuk 'SecretValue' di SecretManagementModule [#12190]
* [Perubahan yang berisiko] mendesain ulang permukaan API cmdlet yang terkait dengan HSM terkelola.

#### <a name="azmonitor"></a>Az.Monitor
* Mengubah parameter 'Rule' 'New-AzAutoscaleProfile' untuk menerima daftar kosong. [#12903]
* Menambahkan cmdlet baru untuk mendukung pembuatan pengaturan diagnostik yang lebih fleksibel:
    * 'Get-AzDiagnosticSettingCategory'
    * 'New-AzDiagnosticSetting'
    * 'New-AzDiagnosticDetailSetting'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Membuat teks bantuan dan perubahan nama set parameter ke cmdlet 'Restore-AzRecoveryServicesBackupItem'.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan parameter '-Tag' ke 'Set-AzTemplateSpec' dan 'New-AzTemplateSpec'
* Menambahkan dukungan tampilan Tag ke pemformat default untuk Spesifikasi Templat

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan contoh untuk 'Set-AzServiceFabricSetting' dengan param settingsSectionDescription
* Memperbarui cmdlet terkait aplikasi untuk memanggil bahwa dukungan hanya untuk sumber daya yang disebarkan ARM
* Menandai cmdlet cert kluster penghentian 'Add-AzureRmServiceFabricClusterCertificate' dan 'Remove-AzureRmServiceFabricClusterCertificate'

#### <a name="azsql"></a>Az.Sql
* Menambahkan SecondaryType ke berikut ini:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
    - 'New-AzSqlDatabaseSecondary'
* Menambahkan HighAvailabilityReplicaCount ke berikut ini:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
* Membuat ReadReplicaCount alias HighAvailabilityReplicaCount pada berikut ini:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengunggahan ukuran Azure File hingga 4 TiB
    - 'Set-AzStorageFileContent'
* Meningkatkan Azure.Storage.Blobs ke 12.7.0
* Meningkatkan Azure.Storage.Files.Shares ke 12.5.0
* Meningkatkan Azure.Storage.Files.DataLake ke 12.5.0

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan Fitur kebijakan peningkatan sinkronisasi dengan kebijakan unduhan dan mode cache lokal

#### <a name="azwebsites"></a>Az.Websites
* Mencegah aturan pembatasan akses duplikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Dawson (@dawsonar802), Memperbarui Get-AzKeyVaultCertificate.md - Mendapatkan sertifikat dan Menyimpannya sebagai bagian pfx untuk bekerja dengan Inti PowerShell (#13557)
* @iviark, Pembaruan BYOK Powershell API Kesehatan (#13518)
* John Duckmanton (@johnduckmanton), Mengoreksi ejaan dari TagPatchOperation (#13508)
* Michael James (@mikejwhat)
  * Membantu Merapikan Get-AzLogicAppRunHistory (#13513)
* Richard de Zwart (@mountain65)
  * Memperbarui Update-AzAppConfigurationStore.md ( #13485 )
  * Memperbarui New-AzCosmosDBAccount.md (#13490)
* @SteppingRazor, New-AzApiManagementProduct: Mengubah nilai default parameter SubscriptionsLimit menjadi Tidak Ada (#13457)
* Steve Burkett (@SteveBurkettNZ), Memperbaiki Kesalahan ketik untuk parameter WorkspaceResourceId dalam contoh (#13589 )

## <a name="510---november-2020"></a>5.1.0 - November 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah yang mungkin tidak dihormati TenantId jika menggunakan 'Koneksi-AzAccount -DeviceCode'[#13477]
* Menambahkan cmdlet baru 'Get-AzAccessToken'
* Memperbaiki masalah kesalahan terjadi jika jalur profil pengguna tidak dapat diakses
* Memperbaiki masalah yang menyebabkan kesalahan Write-Object selama Connect-AzAccount [#13419]
* Menambahkan parameter 'ContainerRegistryEndpointSuffix' ke: 'Add-AzEnvironment', 'Set-AzEnvironment'
* Mendukung gangguan proses masuk dengan menekan <kbd>CTRL</kbd>+<kbd>C</kbd>
* Memperbaiki masalah yang menyebabkan 'Koneksi-AzAccount -KeyVaultAccessToken' tidak berfungsi [#13127]
* Memperbaiki referensi null dan metode tidak sensitif huruf besar atau kecil di 'Invoke-AzRestMethod'

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah pengguna tidak dapat menggunakan perwakilan layanan untuk membuat kluster Kubernetes baru. [#13012]

#### <a name="azappconfiguration"></a>Az.AppConfiguration
* Ketersediaan umum modul 'Az.AppConfiguration'

#### <a name="azdatafactory"></a>Az.DataFactory
* Meningkatkan pesan kesalahan dari perintah 'New-AzDataFactoryV2LinkedServiceEncryptedCredential'

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui SDK dataplane ADLS ke 1.2.4-alpha. Perubahan: https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-124-alpha

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan cmdlet Paket MSIX baru dan cmdlet Aplikasi yang diperbarui.

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki perintah kluster untuk kluster EventHub tanpa tag
* Memperbarui teks bantuan untuk PartnerNamespace perintah AzEventHubGeoDRConfiguration

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan parameter 'ResourceProviderConnection' dan 'PrivateLink' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur link privat dan relay keluar
* Menambahkan parameter 'AmbariDatabase' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur database Ambari kustom
* Menambahkan nilai terima 'AmbariDatabase' ke parameter 'MetastoreType' cmdlet 'Add-AzHDInsightMetastore'

#### <a name="aziothub"></a>Az.IotHub
* Memungkinkan tag di IoT Hub membuat cmdlet.

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung pembaruan tag brankas kunci

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki terkait Get-AzLogicAppRunHistory yang hanya mengambil halaman pertama hasil

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet di bawah ini
    - 'New-AzLoadBalancerFrontendIpConfigCommand', 'Set-AzLoadBalancerFrontendIpConfigCommand', 'Add-AzLoadBalancerFrontendIpConfigCommand':
        - Menambahkan properti PublicIpAddressPrefix
        - Menambahkan properti PublicIpAddressPrefixId
* Menambahkan properti baru ke cmdlet berikut untuk memungkinkan penyeimbangan beban global
    - 'New-AzLoadBalancer':
        - Menambahkan properti Tingkat Sku
    - 'New-AzPuplicIpAddress':
        - Menambahkan properti Tingkat Sku
    - 'New-AzPublicIpPrefix':
        - Menambahkan properti Tingkat Sku
    - 'New-AzLoadBalancerBackendAddressConfig':
        - Menambahkan properti LoadBalancerFrontendIPConfigurationId
* Memperbarui perencanaan untuk menghentikan peringatan untuk cmdlet berikut -'New-AzVirtualHubRoute' -'New-AzVirtualHubRouteTable' -'Add-AzVirtualHubRoute' -'Add-AzVirtualHubRouteTable' -'Get-AzVirtualHubRouteTable' -'Remove-AzVirtualHubRouteTable'
* Menambahkan perencanaan untuk menghentikan peringatan pada argumen 'RouteTable' untuk cmdlet berikut -'New-AzVirtualHub' -'Set-AzVirtualHub' -'Update-AzVirtualHub'
* Membuat argumen '-MinScaleUnits' dan '-MaxScaleUnits' opsional di 'Set-AzExpressRouteGateway'
* Menambahkan cmdlet baru untuk mendukung Autentikasi Timbal Balik dan Profil SSL di Application Gateway
    - 'Get-AzApplicationGatewayClientAuthConfiguration'
    - 'New-AzApplicationGatewayClientAuthConfiguration'
    - 'Remove-AzApplicationGatewayClientAuthConfiguration'
    - 'Set-AzApplicationGatewayClientAuthConfiguration'
    - 'Add-AzApplicationGatewayTrustedClientCertificate'
    - 'Get-AzApplicationGatewayTrustedClientCertificate'
    - 'New-AzApplicationGatewayTrustedClientCertificate'
    - 'Remove-AzApplicationGatewayTrustedClientCertificate'
    - 'Set-AzApplicationGatewayTrustedClientCertificate'
    - 'Add-AzApplicationGatewaySslProfile'
    - 'Get-AzApplicationGatewaySslProfile'
    - 'New-AzApplicationGatewaySslProfile'
    - 'Remove-AzApplicationGatewaySslProfile'
    - 'Set-AzApplicationGatewaySslProfile'
    - 'Get-AzApplicationGatewaySslProfilePolicy'
    - 'Remove-AzApplicationGatewaySslProfilePolicy'
    - 'Set-AzApplicationGatewaySslProfilePolicy'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menentukan BackupTime kebijakan dalam format UTC.
* Memodifikasi peringatan perubahan yang berisiko di cmdlet Get-AzRecoveryServicesBackupJobDetails.
* Memperbarui teks bantuan skrip sampel untuk cmdlet Set-AzRecoveryServicesBackupProtectionPolicy.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah di mana What-If menunjukkan dua cakupan grup sumber daya dengan huruf besar atau kecil yang berbeda
* Memperbarui 'Export-AzResourceGroup' untuk menggunakan SDK.
* Menambahkan info budaya untuk mengurai metode

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah di mana Set-AzSqlDatabaseAudit tidak mendukung database Hyperscale dan edisi database tidak dapat ditentukan
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Memperbaiki bug di GetAzureSqlDatabaseReplicationLink.cs tempat parameter PartnerServerName sedang diperiksa berdasarkan nilai, bukan kunci

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk fitur pembatasan akses baru: ServiceTag, multi-ip dan http-header

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* John Q. Martin (@johnmart82), Menambahkan informasi prasyarat firewall (#13385)
* Manikandan Duraisamy (@madurais-msft), Mengoreksi argumen PublicSubnetName (#13417)
* @mahortas, Pembaruan untuk nilai parameter -HostNames ( #13349)
* @MariachiForHire, menambahkan nilai TrafficAnalyticsInterval yang didukung (#13304)
* Michael James (@mikejwhat), Memungkinkan Get-AzLogicAppRunHistory untuk menampilkan lebih dari 30 entri (#13393)
* Shashikant Shakya (@shshakya), Memperbarui Restore-AzSqlInstanceDatabase.md (#13404)

## <a name="500---october-2020"></a>5.0.0 - Oktober 2020
#### <a name="azaccounts"></a>Az.Accounts
* [Perubahan yang Berisiko] Menghapus 'Get-AzProfile' dan 'Select-AzProfile'
* Mengganti Pustaka Autentikasi Direktori Azure dengan Pustaka Autentikasi Microsoft (MSAL)

#### <a name="azaks"></a>Az.Aks
* [Perubahan yang Berisiko] Menghapus alias parameter 'ClientIdAndSecret' di 'New-AzAksCluster' dan 'Set-AzAksCluster'.
* [Perubahan yang Berisiko] Mengubah nilai default 'NodeVmSetType' di 'New-AzAksCluster' dari 'AvailabilitySet' menjadi 'VirtualMachineScaleSets'.
* [Perubahan yang Berisiko] Mengubah nilai default 'NetworkPlugin' di 'New-AzAksCluster' dari 'None' menjadi 'azure'.
* [Perubahan yang Berisiko] Menghapus parameter 'NodeOsType' di 'New-AzAksCluster' karena hanya mendukung satu nilai Linux.

#### <a name="azbilling"></a>Az.Billing
* Menambahkan cmdlet 'Get-AzBillingAccount'
* Menambahkan cmdlet 'Get-AzBillingProfile'
* Menambahkan cmdlet 'Get-AzInvoiceSection'
* Menambahkan parameter baru di cmdlet 'Get-AzBillingInvoice'
* Menghapus properti DownloadUrlExpiry, Type, BillingPeriodNames dari respons cmdlet Get-AzBillingInvoice

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung fungsionalitas tautan privat dan multi-asal

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui SDK ke 7.4.0-pratinjau.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-VmssId' ke 'New-AzVm'
* Menambahkan parameter 'PlatformFaultDomainCount' ke cmdlet 'New-AzVmss'.
* Cmdlet baru 'Get-AzDiskEncryptionSetAssociatedResource'
* Menambahkan parameter opsional 'Tier' dan 'LogicalSectorSize' ke cmdlet New-AzDiskConfig.
* Menambahkan parameter opsional 'Tier', 'MaxSharesCount', 'DiskIOPSReadOnly', dan 'DiskMBpsReadOnly' ke cmdlet 'New-AzDiskUpdateConfig'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* [Perubahan yang Berisiko] Memperbarui versi API ke 01-05-2019
* [Perubahan yang Berisiko] Menghapus SKU 'Classic' dan parameter 'StorageAccountName' dari 'New-AzContainerRegistry'
* Menambahkan cmdlet baru: 'Koneksi-AzContainerRegistry', 'Import-AzContainerRegistry', 'Get-AzContainerRegistryUsage', 'New-AzContainerRegistryNetworkRule', 'Set-AzContainerRegistryNetworkRule'
* Menambahkan parameter baru 'NetworkRuleSet' ke 'Update-AzContainerRegistry'

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki bug yang dapat menyebabkan pembaruan ruang kerja databricks tanpa kegagalan `-EncryptionKeyVersion`.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.12.0
* Memperbarui versi SDK klien enkripsi ADF ke 4.14.7587.7
* Menambahkan perintah 'Stop-AzDataFactoryV2TriggerRun' dan 'Invoke-AzDataFactoryV2TriggerRun'

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Memerlukan properti Lokasi untuk membuat objek lengan tingkat atas.
        * Membuat `ApplicationGroupType` yang diperlukan untuk `New-AzWvdApplicationGroup`.
        * Membuat `HostPoolArmPath` yang diperlukan untuk `New-AzWvdApplicationGroup`.
        * Menambahkan `PreferredAppGroupType` untuk `New-AzWvdHostPool`.

#### <a name="azfunctions"></a>Az.Functions
* [Perubahan yang Berisiko] Menghapus parameter pengalih 'IncludeSlot' dari semua kecuali satu set parameter 'Get-AzFunctionApp'. Cmdlet sekarang mendukung pengambilan slot penyebaran dalam hasil saat '-IncludeSlot' ditentukan.
* Memperbarui 'New-AzFunctionApp':
  - Memperbaiki -DisableApplicationInsights sehingga tidak ada proyek wawasan aplikasi yang dibuat saat opsi ini ditentukan. [#12728]
  - [Perubahan yang Berisiko] Menghapus dukungan untuk membuat aplikasi fungsi PowerShell 6.2.
  - [Perubahan yang Berisiko] Mengubah versi runtime default di Functions versi 3 pada Windows untuk aplikasi fungsi PowerShell dari 6.2 menjadi 7.0 saat parameter RuntimeVersion tidak ditentukan.
  - [Perubahan yang Berisiko] Mengubah versi runtime default di Functions versi 3 di Windows dan Aplikasi fungsi Linux untuk Node dari 10 menjadi 12 saat parameter RuntimeVersion tidak ditentukan.
  - [Perubahan yang Berisiko] Mengubah versi runtime default di Functions versi 3 di Linux untuk aplikasi fungsi Python dari 3.7 menjadi 3.8 saat parameter RuntimeVersion tidak ditentukan.

#### <a name="azhdinsight"></a>Az.HDInsight
 * Untuk cmdlet New-AzHDInsightCluster:
     - Mengganti parameter 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
     - Mengganti parameter 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
     - Mengganti parameter 'DefaultStorageAccountType' dengan 'StorageAccountType'
     - Menghapus parameter 'PublicNetworkAccessType'
     - Menghapus parameter 'OutboundPublicNetworkAccessType'
     - Menambahkan parameter baru: 'StorageFileSystem' dan 'StorageAccountManagedIdentity' untuk mendukung ADLSGen2
     - Menambahkan parameter baru 'EnableIDBroker' untuk Mendukung BROKER ID HDInsight
     - Menambahkan parameter baru: 'KafkaClientGroupId', 'KafkaClientGroupName' dan 'KafkaManagementNodeSize' untuk mendukung Kafka Rest Proxy
 * Untuk cmdlet New-AzHDInsightClusterConfig:
     - Mengganti parameter 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
     - Mengganti parameter 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
     - Mengganti parameter 'DefaultStorageAccountType' dengan 'StorageAccountType'
     - Menghapus parameter 'PublicNetworkAccessType'
     - Menghapus parameter 'OutboundPublicNetworkAccessType'
* Untuk cmdlet Set-AzHDInsightDefaultStorage:
    - Mengganti parameter 'StorageAccountName' dengan 'StorageAccountResourceId'
* Untuk cmdlet Add-AzHDInsightSecurityProfile:
    - Mengganti parameter 'Domain' dengan 'DomainResourceId'
    - Menghapus persyaratan wajib untuk parameter 'OrganizationalUnitDN'

#### <a name="azkeyvault"></a>Az.KeyVault
* [Perubahan yang Berisiko] Tidak menggunakan lagi parameter DisableSoftDelete di 'New-AzKeyVault' dan EnableSoftDelete di 'Update-AzKeyVault'
* [Perubahan yang Berisiko] Menghapus atribut SecretValueText untuk menghindari menampilkan SecretValue secara langsung [#12266]
* Mendukung jenis sumber daya baru: HSM terkelola
    - CRUD dari cmdlet dan HSM terkelola untuk mengoperasikan kunci pada HSM terkelola
    - Pencadangan/pemulihan HSM penuh, pembuatan kunci AES, pencadangan/pemulihan domain keamanan, RBAC

#### <a name="azmanagedservices"></a>Az.ManagedServices
* [Perubahan yang Berisiko] Memperbarui konvensi penamaan parameter dan contoh terkait

#### <a name="aznetwork"></a>Az.Network
* [Perubahan yang Berisiko] Menghapus Parameter 'HostedSubnet' dan menambahkan 'Subnet' sebagai gantinya
* Menambahkan cmdlet baru untuk Rute Serekan Perute Virtual
    - 'Get-AzVirtualRouterPeerLearnedRoute'
    - 'Get-AzVirtualRouterPeerAdvertisedRoute'
* Memperbarui cmdlet New-AzFirewall:
    - Menambahkan parameter '-SkuTier'
    - Menambahkan parameter '-SkuName' dan menjadikan Sku sebagai Alias untuk ini
    - Menghapus parameter '-Sku'
* [Perubahan yang Berisiko] Membuat argumen 'Connectionlink' wajib di 'Start-AzVpnConnectionPacketCapture' dan 'Stop-AzVpnConnectionPacketCapture'
* [Perubahan yang Berisiko] Memperbarui 'New-AzNetworkWatcherConnectionMonitorEndPointObject' untuk menghapus parameter '-Filter'
* [Perubahan yang Berisiko] Mengganti cmdlet 'New-AzNetworkWatcherConnectionMonitorEndpointFilterItemObject' dengan cmdlet 'New-AzNetworkWatcherConnectionMonitorEndpointScopeItemObject'
* Memperbarui cmdlet 'New-AzNetworkWatcherConnectionMonitorEndPointObject':
    - Menambahkan parameter '-Tipe'
    - Menambahkan parameter '-CoverageLevel'
    - Menambahkan parameter '-Scope'
* Memperbarui cmdlet 'New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject' dengan parameter baru '-DestinationPortBehavior'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Pemulihan Beban Kerja untuk izin kontributor.
* Menambahkan set parameter dan validasi baru untuk cmdlet Restore-AzRecoveryServicesBackupItem.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug penguraian
* Memperbarui cmdlet What-If templat ARM untuk menghapus pesan pratinjau dari hasil
* Memperbaiki masalah di mana cmdlet penyebaran templat crash jika '-WhatIf' diatur pada cakupan yang lebih tinggi [#13038]
* Memperbaiki masalah di mana cmdlet penyebaran templat tidak mempertahankan huruf besar atau kecil untuk parameter templat
* Menambahkan versi API default untuk digunakan di cmdlet 'Export-AzResourceGroup'
* Menambahkan cmdlet untuk Spesifikasi Templat ('Get-AzTemplateSpec', 'Set-AzTemplateSpec', 'New-AzTemplateSpec', 'Remove-azTemplateSpec', 'Export-AzTemplateSpec')
* Menambahkan dukungan untuk menyebarkan Spesifikasi Templat menggunakan cmdlet penyebaran yang ada (melalui parameter -TemplateSpecId baru)
* Memperbarui 'Get-AzResourceGroupDeploymentOperation' untuk menggunakan SDK.
* Menghapus parameter '-ApiVersion' dari cmdlet '*-AzDeployment'.

#### <a name="azsql"></a>Az.Sql
* Menambahkan DiffBackupIntervalInHours ke 'Set-AzSqlDatabaseBackupShortTermRetentionPolicy'
* Memperbaiki masalah di mana New-AzSqlDatabaseExport gagal jika networkIsolation tidak ditentukan [#13097]
* Memperbaiki masalah di mana New-AzSqlDatabaseExport dan New-AzSqlDatabaseImport tidak menampilkan OperationStatusLink di objek hasil [#13097]
* Memperbarui URL Wilayah Berpasangan Azure dalam Peringatan Redundansi Penyimpanan Cadangan

#### <a name="azstorage"></a>Az.Storage
* Menghapus properti usang RestorePolicy.LastEnabledTime
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Get-AzStorageBlobServiceProperty'
    - 'Update-AzStorageBlobServiceProperty'
* Mengubah Jenis HariAfterModificationGreaterThan dari int ke int?
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyRule'
* Mendukung pembuatan/pembaruan dengan tingkat penyimpanan
    - 'New-AzRmStorageShare'
    - 'Update-AzRmStorageShare'
* Mendukung pengaturan/pembaruan/penghapusan Acl secara berulang pada item Datalake Gen2
    -  'Set-AzDataLakeGen2AclRecursive'
    -  'Update-AzDataLakeGen2AclRecursive'
    -  'Remove-AzDataLakeGen2AclRecursive'
* Mendukung kebijakan akses Kontainer dengan izin baru x,t
    -  'New-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Mengubah output dapatkan/atur cmdlet kebijakan akses Kontainer, dengan mengubah jenis Izin properti turunan dari enum ke String
    -  'Get-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Memperbaiki masalah skrip contoh set kebijakan manajemen dengan json
    -  'Set-AzStorageAccountManagementPolicy'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk tingkat harga Premium V3
* Memperbarui SDK WebSites ke 3.1.0

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Memperbarui Get-AzDelegation.md (#13176)
* @dineshreddy007, Mendapatkan Peran Aplikasi yang ditetapkan dengan benar jika terjadi pendaftaran Stack HCI menggunakan token WAC. (#13249)
* @kongou-ae, Memperbarui New-AzOffice365PolicyProperty.md (#13217)
* Lohith Chowdary Chilukuri (@Lochiluk), Memperbarui Set-AzApplicationGateway.md (#13150)
* Matthew Burleigh (@mburleigh)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen ( #13203 )
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen ( #13190 )
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen ( #13189 )
  * menambahkan tautan ke cmdlet yang direferensikan ( #13137 )
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen ( #13204 )
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen ( #13205 )


## <a name="480---october-2020"></a>4.8.0 - Oktober 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah penguraian DateTime di pustaka umum [#13045]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan cmdlet 'New-AzCognitiveServicesAccountApiProperty'.
* Mendukung parameter 'ApiProperty' untuk 'New-AzCognitiveServicesAccount' dan 'Set-AzCognitiveServicesAccount'

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah di 'Update-ASRRecoveryPlan' dengan mengisi FailoverTypes
* Menambahkan parameter opsional '-Top' dan '-OrderBy' ke cmdlet 'Get-AzVmImage'.

#### <a name="azdatabricks"></a>Az.Databricks
* Ketersediaan umum modul 'Az.Databricks'
* Menambahkan dukungan untuk peering jaringan virtual

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki kesalahan ketik dalam pesan output

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter pengalihan opsional 'TrustedServiceAccessEnabled' ke cmdlet 'Set-AzEventHubNetworkRuleSet'

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan pesan peringatan untuk berencana menghentikan parameter 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType'
* Menambahkan pesan peringatan untuk berencana mengganti parameter 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
* Menambahkan pesan peringatan untuk berencana mengganti parameter 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
* Menambahkan pesan peringatan untuk berencana mengganti parameter 'DefaultStorageAccountType' dengan 'StorageAccountType'
* Menambahkan pesan peringatan untuk berencana mengganti parameter 'DefaultStorageContainer' dengan 'StorageContainer'
* Menambahkan pesan peringatan untuk berencana mengganti parameter 'DefaultStorageRootPath' dengan 'StorageRootPath'

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui sdk perangkat.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memberikan tanggal terperinci untuk menghapus properti SecretValueText

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Memperbarui peringatan perubahan yang berisiko pada cmdlet definisi dan penetapan layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug yang pesan peringatannya tidak dapat ditekan. [#12889]
* Mendukung parameter 'SkipMetricValidation' dalam kriteria aturan peringatan. Memungkinkan pembuatan aturan peringatan pada metrik kustom yang belum dipancarkan, dengan menyebabkan validasi metrik dilewati.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan Kebijakan Office365 ke Sumber Daya VPNSite
    - 'New-AzO365PolicyProperty'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan validasi nama kontainer untuk pencadangan beban kerja.

#### <a name="azrediscache"></a>Az.RedisCache
* Membuat cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache' tidak gagal karena masalah izin terkait pendaftaran Microsoft.Cache RP

#### <a name="azsql"></a>Az.Sql
* Menambahkan BackupStorageRedundancy ke berikut ini:
    - 'Restore-AzureRmSqlDatabase'
    - 'New-AzSqlDatabaseCopy'
    - 'New-AzSqlDatabaseSecondary'
* Menghapus sensitivitas huruf besar atau kecil untuk parameter BackupStorageRedundancy untuk semua referensi DB SQL
* Memperbarui nama pesan peringatan BackupStorageRedundancy

#### <a name="azstorage"></a>Az.Storage
* Mendukung mengaktifkan/menonaktifkan/mendapatkan properti penghapusan sementara berbagi pada file Layanan Akun penyimpanan
    - 'Update-AzStorageFileServiceProperty'
    - 'Get-AzStorageFileServiceProperty'
* Mendukung daftar berbagi file termasuk Akun penyimpanan yang dihapus, dan Mendapatkan penggunaan berbagi file tunggal
    - 'Get-AzRmStorageShare'
* Mendukung pemulihan berbagi file yang terhapus:
    - 'Restore-AzRmStorageShare'
* Mengubah cmdlet untuk memodifikasi properti layanan blob, tidak akan mendapatkan properti asli dari server, tetapi hanya mengatur properti yang dimodifikasi ke server.
    - 'Enable-AzStorageBlobDeleteRetentionPolicy'
    - 'Disable-AzStorageBlobDeleteRetentionPolicy'
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Update-AzStorageBlobServiceProperty'
* Memperbaiki masalah bantuan untuk parameter New-AzStorageAccount nilai default -Kind [#12189]
* Memperbaiki masalah dengan menambahkan contoh untuk menunjukkan cara mengatur ContentType yang benar di pengunggahan blob [#12989]

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @felickz, Mengklarifikasi pelepasan karakter khusus dalam Subjek (#13028)
* Martin Zurita (@Gorgoras), Mengoreksi beberapa kesalahan ketik dalam pesan. (#12999)
* @kingsleyAzure
  * Menambahkan uri hsm terkelola dalam pencocokan regex (#12912)
  * Menambahkan dukungan HSM Terkelola untuk SQL (#13073)
* @MasterKuat, Memperbaiki keluhan pada database sistem instans terkelola untuk penilaian kerentanan (#12971)


## <a name="470---september-2020"></a>4.7.0 - September 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memformat pesan perubahan berisiko yang akan datang
* Memperbarui Azure.Core ke 1.4.1

#### <a name="azaks"></a>Az.Aks
* Menambahkan logika validasi parameter sisi klien untuk 'New-AzAksCluster', 'Set-AzAksCluster' dan 'New-AzAksNodePool'. [#12372]
* Menambahkan dukungan untuk add-on di 'New-AzAksCluster'. [#11239]
* Menambahkan cmdlet 'Enable-AzAksAddOn' dan 'Disable-AzAksAddOn' untuk add-on. [#11239]
* Menambahkan parameter 'GenerateSshKey' untuk 'New-AzAksCluster'. [#12371]
* Memperbarui versi api ke 01-06-2020.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menunjukkan persyaratan hukum tambahan untuk API tertentu.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-EncryptionType' ke 'New-AzVmDiskEncryptionSetConfig'
* Cmdlet baru untuk jenis sumber daya baru: DiskAccess 'Get-AzDiskAccess', 'New-AzDiskAccess', 'Get-AzDiskAccess'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzSnapshotConfig'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzDiskConfig'
* Menambahkan properti 'PatchStatus' ke Tampilan Instans VirtualMachine
* Menambahkan properti 'VMHealth' ke tampilan instans mesin virtual, yang merupakan objek yang ditampilkan saat 'Get-AzVm' dipanggil dengan '-Status'
* Menambahkan bidang 'AssignedHost' ke tampilan instans 'Get-AzVM' dan 'Get-AzVmss'. Bidang ini menunjukkan id sumber daya instans mesin virtual
* Menambahkan parameter opsional '-SupportAutomaticPlacement' ke 'New-AzHostGroup'
* Menambahkan parameter '-HostGroupId' ke 'New-AzVm' dan 'New-AzVmss'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.11.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet Kluster baru - 'New-AzEventHubCluster', 'Set-AzEventHubCluster', 'Get-AzEventHubCluster', 'Remove-AzEventHubCluster', 'Get-AzEventHubClustersAvailableRegions'.
* Memperbaiki masalah #10722 : Perbaikan untuk hanya menetapkan 'Listen' ke hak AuthorizationRule.

#### <a name="azfunctions"></a>Az.Functions
* Menghapus kemampuan untuk membuat Functions v2 di wilayah yang tidak mendukungnya.
* Tidak menggunakan lagi Powershell 6.2. Menambahkan peringatan saat pengguna membuat aplikasi fungsi PowerShell 6.2 yang menyarankan mereka untuk membuat aplikasi fungsi PowerShell 7.0 sebagai gantinya.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan konfigurasi Skala Otomatis
    - Menambahkan parameter baru 'AutoscaleConfiguration' ke cmdlet 'New-AzHDInsightCluster'
* Mendukung pengoperasian konfigurasi Skala Otomatis kluster
    - Menambahkan cmdlet baru 'Get-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'Set-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'Remove-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleScheduleCondition'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk otorisasi RBAC [#10557]
* Menyempurnakan penanganan kesalahan di 'Set-AzKeyVaultAccessPolicy' [#4007]

#### <a name="azkusto"></a>Az.Kusto
* Ketersediaan umum modul 'Az.Kusto'

#### <a name="aznetwork"></a>Az.Network
* [Perubahan yang Berisiko] Memperbarui cmdlet di bawah ini untuk menyelaraskan perute virtual sumber daya dan hub virtual
    - 'New-AzVirtualRouter':
        - Menambahkan parameter -HostedSubnet untuk mendukung sumber daya turunan konfigurasi IP
        - menghapus -HostedGateway dan -HostedGatewayId
    - 'Get-AzVirtualRouter':
        - Menambahkan set parameter tingkat langganan
    - 'Remove-AzVirtualRouter'
    - 'Add-AzVirtualRouterPeer'
    - 'Get-AzVirtualRouterPeer'
    - 'Remove-AzVirtualRouterPeer'
* Menambahkan cmdlet baru untuk Port Rute Ekspres Azure
    - 'New-AzExpressRoutePortLOA'
* Menambahkan properti RemoteBgpCommunities ke Sumber Daya Peering VirtualNetwork
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress', dan 'New-AzPublicIpPrefix'.
* Menambahkan VpnGatewayIpConfigurations ke output 'Get-AzVpnGateway'
* Memperbaiki bug untuk 'Set-AzApplicationGatewaySslCertificate' [#9488]
* Menambahkan parameter 'AllowActiveFTP' ke 'AzureFirewall'
* Memperbarui perintah fitur di bawah ini: Mengaktifkan pengaturan/penghapusan keamanan internet di VirtualWan P2SVpnGateway.
- Memperbarui 'New-AzP2sVpnGateway': Menambahkan parameter pengalihan opsional 'EnableInternetSecurityFlag' bagi pelanggan untuk mengatur true guna mengaktifkan keamanan internet di P2SVpnGateway, yang akan diterapkan untuk klien Titik ke situs.
- Memperbarui 'Update-AzP2sVpnGateway': Menambahkan parameter pengalihan opsional 'EnableInternetSecurityFlag' atau 'DisableInternetSecurityFlag' bagi pelanggan untuk mengatur true/false guna mengaktifkan/menonaktifkan keamanan internet di P2SVpnGateway, yang akan diterapkan untuk klien Titik ke situs.
* Menambahkan cmdlet baru 'Reset-AzP2sVpnGateway' bagi pelanggan untuk mengatur ulang/me-reboot VirtualWan P2SVpnGateway mereka guna pemecahan masalah.
* Menambahkan cmdlet baru 'Reset-AzVpnGateway' bagi pelanggan untuk mengatur ulang/me-reboot VirtualWan VpnGateway mereka guna pemecahan masalah.
* Memperbarui 'Set-azVirtualNetworkSubnetConfig'
    - Mengatur properti Tabel Rute dan NSG subnet ke null jika secara eksplisit diatur dalam parameter [#1548][#9718]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Status Hapus untuk Item Cadangan beban kerja.

#### <a name="azresources"></a>Az.Resources
* Menambahkan pemeriksaan kehilangan untuk Set-AzRoleAssignment
* Menambahkan atribut perubahan yang berisiko ke parameter 'SubscriptionId' dari 'Get-AzResourceGroupDeploymentOperation'
* Memperbarui cmdlet What-If templat ARM untuk menampilkan perubahan sumber daya 'Ignore' terakhir
* Memperbaiki masalah serialisasi parameter array dan aman untuk cmdlet penyebaran [#12773]

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan cmdlet baru untuk kluster terkelola dan jenis simpul:
    - 'New-AzServiceFabricManagedCluster'
    - 'Get-AzServiceFabricManagedCluster'
    - 'Set-AzServiceFabricManagedCluster'
    - 'Remove-AzServiceFabricManagedCluster'
    - 'Add-AzServiceFabricManagedClusterClientCertificate'
    - 'Remove-AzServiceFabricManagedClusterClientCertificate'
    - 'New-AzServiceFabricManagedNodeType'
    - 'Get-AzServiceFabricManagedNodeType'
    - 'Set-AzServiceFabricManagedNodeType'
    - 'Remove-AzServiceFabricManagedNodeType'
    - 'Add-AzServiceFabricManagedNodeTypeVMExtension'
    - 'Add-AzServiceFabricManagedNodeTypeVMSecret'
    - 'Remove-AzServiceFabricManagedNodeTypeVMExtension'
    - 'Restart-AzServiceFabricManagedNodeTyp'
* Meningkatkan SDK Service Fabric ke versi 1.2.0 yang menggunakan penyedia sumber daya service fabric versi-api 01-03-2020 untuk model saat ini dan 01-01-2020-pratinjau untuk kluster terkelola.

#### <a name="azsql"></a>Az.Sql
* Menambahkan BackupStorageRedundancy ke 'New-AzSqlInstance' dan 'Get-AzSqlInstance'
* Menambahkan cmdlet 'Get-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menambahkan cmdlet 'Enable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menambahkan parameter Force ke 'New-AzSqlInstance'
* Menambahkan cmdlet untuk layanan Replay Log Database Terkelola
    - 'Start-AzSqlInstanceDatabaseLogReplay'
    - 'Get-AzSqlInstanceDatabaseLogReplay'
    - 'Complete-AzSqlInstanceDatabaseLogReplay'
    - 'Stop-AzSqlInstanceDatabaseLogReplay'
* Menambahkan cmdlet 'Get-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Menambahkan cmdlet 'Enable-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Menambahkan cmdlet 'Disable-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Memperbarui cmdlet 'New-AzSqlDatabaseImport' dan 'New-AzSqlDatabaseExport' untuk mendukung fungsionalitas isolasi jaringan
* Menambahkan cmdlet 'New-AzSqlDatabaseImportExisting'
* Memperbarui cmdlet Database untuk mendukung spesifikasi jenis penyimpanan cadangan
* Menambahkan parameter Force ke 'New-AzSqlDatabase'
* Menambahkan peringatan untuk konfigurasi BackupStorageRedundancy di wilayah tertentu di 'New-AzSqlDatabase'
* Memperbarui cmdlet ActiveDirectoryOnlyAuthentication untuk server dan instans untuk menyertakan ResourceId dan InputObject

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki pengunggahan blob yang gagal dengan meningkatkan ke Microsoft.Azure.Storage.DataMovement 2.0.0 [#12220]
* Mendukung Pemulihan Titik Waktu Tertentu
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'New-AzStorageBlobRangeToRestore'
    - 'Restore-AzStorageBlobRange'
* Mendukung untuk mendapatkan status pemulihan blob Akun penyimpanan dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeBlobRestoreStatus
    - 'Get-AzureRMStorageAccount'
* Menambahkan pesan peringatan perubahan yang berisiko untuk perubahan output cmdlet yang akan datang
    - 'Get-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyRule'
* Meningkatkan SDK Microsoft.Azure.Cosmos.Table ke 1.0.8

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Thomas Van Laere (@ThomVanL), Menambahkan Dockerfile-alpine-3.10 (#12911)
* Lohith Chowdary Chilukuri (@Lochiluk), Memperbarui Remove-AzNetworkInterfaceIpConfig.md (#12807)
* Roberth Strand (@roberthstrand), Get-AzResourceGroup - Contoh baru, dan pembersihan (#12828)
* Ravi Mishra (@inmishrar), memperbarui tumpukan runtime Azure Web App ke DOTNETCORE (#12833)
* @jack-education, Memperbarui Set-AzVirtualNetworkSubnetConfig untuk memungkinkan NSG dan Tabel Rute dihapus dari subnet (#12351)
* @hagop-globanet, Memperbarui Add-AzApplicationGatewayCustomError.md (#12784)
* Joshua Van Daalen (@greenSacrifice)
  * Memperbarui ejaan Properti ke Properti (#12821)
  * Memperbarui contoh New-AzResourceLock.md (#12806)
* Eragon Riddle (@eragonriddle), Mengoreksi nama bidang parameter dalam contoh (#12825)
* @rossifumax, Memperbaiki kesalahan ketik di New-AzConfigurationAssignment.md (#12701)


## <a name="461---august-2020"></a>4.6.1 - Agustus 2020
#### <a name="azcompute"></a>Az.Compute
* Melakukan patch parameter '-EncryptionAtHost' di 'New-AzVm' untuk menghapus nilai default false [#12776]

## <a name="460---august-2020"></a>4.6.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memuat semua lingkungan cloud publik saat titik akhir penemuan tidak menampilkan AzureCloud default atau lingkungan publik lainnya [#12633]
* Mengekspos SubscriptionPolicies di 'Get-AzSubscription' [#12551]

#### <a name="azautomation"></a>Az.Automation
* Menambahkan parameter '-RunOn' ke 'Set-AzAutomationWebhook' untuk menentukan Grup Pekerja Hibrid

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EncryptionAtHost' ke 'New-AzVm', 'New-AzVmss', 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVM', dan 'Update-AzVmss'
* Menambahkan 'SecurityProfile' ke objek hasil 'Get-AzVM' dan 'Get-AzVmss'
* Menambahkan pengalih '-InstanceView' sebagai parameter opsional ke 'Get-AzHostGroup'
* Menambahkan cmdlet baru 'Invoke-AzVmPatchAssessment'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan properti yang hilang ke kelas PSPipelineRun.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan fitur enkripsi di host.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan pesan peringatan untuk perencanaan menonaktifkan penghapusan sementara
* Menambahkan pesan peringatan untuk perencanaan menghapus atribut SecretValueText

#### <a name="azmaintenance"></a>Az.Maintenance
* Menambahkan bidang terkait jadwal opsional ke 'New-AzMaintenanceConfiguration'
* Menambahkan cmdlet baru untuk 'Get-AzMaintenancePublicConfiguration'

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan peringatan perubahan yang berisiko pada cmdlet definisi dan penetapan layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperluas parameter yang diatur dalam 'Set-AzDiagnosticSetting' untuk pemisahan pengaktifan Metrik dan Log [#12482]
* Memperbaiki bug untuk 'Add-AzMetricAlertRuleV2' saat mendapatkan peringatan metrik dari alur

#### <a name="azresources"></a>Az.Resources
* Memperbarui respons 'Get-AzPolicyAlias' untuk menyertakan informasi yang menunjukkan apakah alias tersebut dapat dimodifikasi oleh Azure Policy.
* Membuat cmdlet baru 'Set-AzRoleAssignment'
* Menambahkan 'Get-AzDeploymentManagementGroupWhatIfResult' untuk mendapatkan hasil What-If templat ARM di cakupan Grup manajemen
* Menambahkan cmdlet baru 'Get-AzTenantWhatIfResult' untuk mendapatkan hasil What-If templat ARM di cakupan penyewa
* Mengambil alih '-WhatIf' dan '-Confirm' untuk 'New-AzManagementGroupDeployment' dan 'New-AzTenantDeployment' untuk menggunakan hasil What-If templat ARM
* Memperbaiki perilaku '-WhatIf' dan '-Confirm' untuk cmdlet penyebaran baru sehingga mereka mematuhi False dan
* Memperbaiki kesalahan serialisasi untuk '-TemplateObject' dan 'TemplateParameterObject' [#1528] [#6292]
* Menambahkan atribut perubahan yang berisiko ke 'Get-AzResourceGroupDeploymentOperation' untuk perubahan jenis output yang akan datang

#### <a name="azsignalr"></a>Az.SignalR
* Memperbaiki kesalahan file bantuan 'Restart-AzSignalR' dan 'Update-AzSignalR'
* Menambahkan cmdlets 'Update-AzSignalRNetworkAcl', 'Set-AzSignalRUpstream'

#### <a name="azstorage"></a>Az.Storage
* Mendukung akselerasi kueri blob
    -  'Get-AzStorageBlobQueryResult'
    -  'New-AzStorageBlobQueryConfig'
* Memperbarui file bantuan, menambahkan lebih banyak deskripsi, dan memperbaiki kesalahan ketik
    -  'Start-AzStorageBlobCopy'
    -  'Get-AzDataLakeGen2Item'
* Memperbaiki kegagalan pengunduhan blob saat sub direktori terkait tidak ada [#12592]
    -  'Get-AzStorageBlobContent'
* Mendukung untuk Mengatur/Mendapatkan/Menghapus Kebijakan Replikasi Objek di Akun penyimpanan
    - 'New-AzStorageObjectReplicationPolicyRule'
    - 'Set-AzStorageObjectReplicationPolicy'
    - 'Get-AzStorageObjectReplicationPolicy'
    - 'Remove-AzStorageObjectReplicationPolicy'
* Mendukung pengaktifan/penonaktifan ChangeFeed di Layanan Blob Akun penyimpanan
    - 'Update-AzStorageBlobServiceProperty'

## <a name="450---august-2020"></a>4.5.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui 'Connect-AzAccount' untuk menerima parameter 'MaxContextPopulation' [#9865]
* Memperbarui versi SubscriptionClient ke 01-06-2019 dan menampilkan domain penyewa [#9838]
* Mendukung informasi penyewa rumah dan penyewa manageBy langganan
* Mengoreksi nama modul, info versi dalam data telemetri
* Menyesuaikan SqlDatabaseDnsSuffix dan ServiceManagementUrl jika titik akhir metadata lingkungan menampilkan nilai yang tidak kompatibel

#### <a name="azaks"></a>Az.Aks
* Menghapus 'ClientIdAndSecret' ke 'ServicePrincipalIdAndSecret' dan menetapkan 'ClientIdAndSecret' sebagai alias [#12381].
* Menghapus 'Get-AzAks'/'New-AzAks'/'Remove-AzAks'/'Set-AzAks' ke 'Get-AzAksCluster'/'New-AzAksCluster'/'Remove-AzAksCluster'/'Set-AzAksCluster' dan menetapkan yang asli sebagai alias [#12373].

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan cmdlet 'Add-AzApiManagementApiToGateway' baru.
* Menambahkan cmdlet 'Get-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'Get-AzApiManagementGatewayHostnameConfiguration' baru.
* Menambahkan cmdlet 'Get-AzApiManagementGatewayKey' baru.
* Menambahkan cmdlet 'New-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'New-AzApiManagementGatewayHostnameConfiguration' baru.
* Menambahkan cmdlet 'New-AzApiManagementResourceLocationObject' baru.
* Menambahkan cmdlet 'Remove-AzApiManagementApiFromGateway' baru.
* Menambahkan cmdlet 'Remove-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'Remove-AzApiManagementGatewayHostnameConfiguration' baru.
* Menambahkan cmdlet 'Update-AzApiManagementGateway' baru.
* Menambahkan parameter [-GatewayId] opsional baru ke cmdlet 'Get-AzApiManagementApi'.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menggunakan 'Deny' secara khusus sebagai tindakan default NetworkRules.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbaiki masalah di mana pengecualian sedang dilemparkan ketika Enum.Parse mencoba memaksa nilai null ke nilai enum yang Diaktifkan atau Dinonaktifkan [#12344]

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan enkripsi dalam fitur transit.
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightCluster'
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightClusterConfig'
* Mendukung pembuatan kluster dengan fitur link privat:
    - Menambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightCluster'
    - Tambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightClusterConfig'
* Menampilkan informasi jaringan virtual saat memanggil 'New-AzHDInsightCluster' atau 'Get-AzHDInsightCluster'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Menambahkan perubahan yang tidak berisiko: Fungsi PeerAddressType untuk Peering Privat di 'Remove-AzExpressRouteCircutPeeringConfig'.
* Perubahan kode untuk mengabaikan huruf besar atau kecil untuk parameter AddressPrefixType dan PeerAddressType.
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress', dan 'New-AzPublicIpPrefix'.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Menambahkan opsi '-ForceDelete' untuk 'Remove-AzOperationalInsightsworkspace'
* Menambahkan cmdlet baru 'Get-AzOperationalInsightsDeletedWorkspace'
* Menambahkan cmdlet baru 'Restore-AzOperationalInsightsWorkspace'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Meningkatkan pengalaman penemuan item/kontainer Azure Backup.

#### <a name="azresources"></a>Az.Resources
* Menambahkan properti 'Condition', 'ConditionVersion' dan 'Description' ke 'New-AzRoleAssignment'
    - Ini termasuk semua perubahan yang relevan pada model data

#### <a name="azsql"></a>Az.Sql
* Memperbaiki potensi kesalahan ketidak sensitifan huruf besar atau kecil nama server di 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Memperbaiki nama database yang salah ditampilkan pada kesalahan database yang ada di 'New-AzSqlDatabaseSecondary'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan token Sas blob/kontainer dengan izin baru x,t
    -  'New-AzStorageBlobSASToken'
    -  'New-AzStorageContainerSASToken'
* Mendukung pembuatan Token Sas akun dengan izin baru x,t,f
    -  'New-AzStorageAccountSASToken'
* Mendukung untuk mendapatkan penggunaan berbagi file tunggal
    - 'Get-AzRmStorageShare'

## <a name="440---july-2020"></a>4.4.0 - Juli 2020
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan cmdlet baru 'Invoke-AzRestMethod'
* Memperbaiki masalah yang dapat menyebabkan kesalahan autentikasi dalam skenario multi-proses seperti menjalankan beberapa cmdlet Azure PowerShell menggunakan 'Start-Job' [#9448]

#### <a name="azaks"></a>Az.Aks
* Memperbaiki bug 'Get-AzAks' tidak mendapatkan semua kluster [#12296]

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Menghapus referensi proyek ke Autentikasi

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah string dengan char escape tidak dapat diubah menjadi objek json.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan peringatan saat menggunakan 'New-AzVmss' tanpa versi gambar 'latest'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan parameter global ke Data Factory.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui untuk menggunakan versi API 01-06-2020.
* Menambahkan fitur baru:
    - Pemetaan input
    - Skema Pengiriman Peristiwa
    - Private Link
    - Skema V10 Peristiwa Cloud
    - Topik Bus Layanan Sebagai Tujuan
    - Fungsi Azure Sebagai Tujuan
    - Pembuatan Batch WebHook
    - Webhook aman (dukungan AAD)
    - IpFiltering
* Memperbarui cmdlet:
    - 'New-AzEventGridSubscription'/'Update-AzEventGridSubscription':
        - Menambahkan parameter opsional baru untuk mendukung batch webhook.
        - Menambahkan parameter opsional baru untuk mendukung webhook aman menggunakan AAD.
        - Menambahkan enum baru untuk parameter EndpointType untuk mendukung fungsi azure dan topik bus layanan sebagai tujuan baru.
        - Menambahkan parameter opsional baru untuk skema pengiriman.
    - 'New-AzEventGridTopic'/'Update-AzEventGridTopic' dan 'New-AzEventGridDomain'/'Update-AzEventGridDomain':
        - Menambahkan parameter opsional baru untuk mendukung IpFiltering.
    - 'New-AzEventGridTopic'/'New-AzEventGridDomain':
        - Menambahkan parameter opsional baru untuk mendukung Pemetaan input.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbarui modul untuk menggunakan API 01-05-2020
* Menambahkan dukungan link Privat untuk sumber daya Storage, Keyvault, dan Web App Service

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan penyimpanan ADLSGen1/2 di cloud nasional.

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug untuk 'Get-AzDiagnosticSetting' saat metrik atau log null [#12272]

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki swap parameter dalam koneksi HubVnet VWan
* Menambahkan cmdlet baru untuk Situs Appliance Virtual Jaringan Azure
    - 'Get-AzVirtualApplianceSite'
    - 'New-AzVirtualApplianceSite'
    - 'Remove-AzVirtualApplianceSite'
    - 'Update-AzVirtualApplianceSite'
    - 'New-AzOffice365PolicyProperty'
* Menambahkan cmdlet baru untuk Appliance Virtual Jaringan Azure
    - 'Get-AzNetworkVirtualAppliance'
    - 'New-AzNetworkVirtualAppliance'
    - 'Remove-AzNetworkVirtualAppliance'
    - 'Update-AzNetworkVirtualAppliance'
    - 'Get-AzNetworkVirtualApplianceSku'
    - 'New-AzVirtualApplianceSkuProperty'
* Onboard Application Gateway ke Cmdlet Umum Private Link
* Onboard StorageSync ke Cmdlet Umum Private Link
* Onboard SignalR ke Cmdlet Umum Private Link

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menghapus referensi proyek ke Autentikasi
* Cmdlet yang disetel Azure Backup membantu teks menjadi lebih akurat.
* Azure Backup menambahkan dukungan untuk mengambil pekerjaan agen MAB menggunakan cmdlet 'Get-AzRecoveryServicesBackupJob'.

#### <a name="azresources"></a>Az.Resources
* Memperbarui 'Save-AzResourceGroupDeploymentTemplate' untuk menggunakan SDK.
* Menambahkan cmdlet 'Unregister-AzResourceProvider'.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk Perwakilan layanan dan pengguna tamu di cmdlet Set-AzSqlInstanceActiveDirectoryAdministrator'
* Memperbaiki bug di cmdlet Klasifikasi Data.'
* Menambahkan dukungan untuk failover Azure SQL Managed Instance: 'Invoke-AzSqlInstanceFailover'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah UserAgent tidak ditambahkan untuk beberapa cmdlet data plane.
* Mendukung pembuatan/pembaruan Akun penyimpanan dengan MinimumTlsVersion dan AllowBlobPublicAccess
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung pengaktifan/penonaktifan penerapan versi di Layanan Blob Akun penyimpanan
    - 'Update-AzStorageBlobServiceProperty'
* Mendukung daftar blob dengan versi blob
    - 'Get-AzStorageBlob'
* Mendukung untuk mendapatkan/menghapus snapshot blob tunggal atau versi blob
    - 'Get-AzStorageBlob'
    - 'Remove-AzStorageBlob'
* Mendukung alur dari objek blob yang dihasilkan dari Azure. Storage.Blob V12
    - 'Get-AzStorageBlobContent'
    - 'New-AzStorageBlobSASToken'
    - 'Remove-AzStorageBlob'
    - 'Set-AzStorageBlobContent'
    - 'Start-AzStorageBlobCopy'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan versi baru SDK StorageSync yang menargetkan ApiVersion 01-03-2020
* Menambahkan cmdlet Layanan Sinkronisasi Pembaruan Penyimpanan
    - 'Set-AzStorageSyncService'
* Menambahkan IncomingTrafficPolicy dan PrivateEndpointConnections ke cmdlet StorageSyncService.

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk melakukan operasi untuk Slot yang tidak berada dalam grup sumber daya yang sama dengan Paket App Service

## <a name="430---june-2020"></a>4.3.0 - Juni 2020
#### <a name="azaccounts"></a>Az.Accounts
* Mendukung penemuan pengaturan lingkungan secara default dan menambahkan lingkungan melalui 'Add-AzEnvironment'
* Memperbarui rakitan yang dimuat sebelumnya [#12024], [#11976]
* Memperbarui assembly Inti Azure
* Memperbaiki masalah yang dapat menyebabkan 'Koneksi-AzAccount' gagal dalam eksekusi multi-rangkaian [#11201]

#### <a name="azaks"></a>Az.Aks
* Mengganti penggunaan [API AccessProfile](/rest/api/aks/managedclusters/getaccessprofile) lama dengan memanggil ke API [ListClusterAdmin](/rest/api/aks/managedclusters/listclusteradmincredentials) dan [ListClusterUser](/rest/api/aks/managedclusters/listclusterusercredentials)

#### <a name="azbatch"></a>Az.Batch
* Memperbarui Az.Batch untuk menggunakan versi SDK 'Microsoft.Azure.Management.Batch' ke 11.0.0
* Menambahkan kemampuan untuk menetapkan Identitas BatchAccount di cmdlet 'New-AzBatchAccount'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung penampilan kemampuan akun.
* Mendukung pemodifikasian PublicNetworkAccess.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter SimulateEviction ke cmdlet Set-AzVM dan Set-AzVmssVM.
* Menambahkan 'Premium_LRS' ke daftar lengkap argumen parameter StorageAccountType untuk New-AzGalleryImageVersion cmdlet.
* Menambahkan Substatus ke VMCustomScriptExtension [#11297]
* Menambahkan 'Delete' ke pelengkap argumen parameter EvictionPolicy untuk cmdlet New-AzVM dan New-AzVMConfig.
* Memperbaiki nama Ekstensi mesin virtual baru untuk SAP

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.9.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter Identitas Terkelola ke cmdlet 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dukungan untuk membuat aplikasi fungsi PowerShell 7.0 dan Java 11

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung daftar host dan memulai ulang host tertentu dari kluster HDInsight.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Memperbarui versi SDK ke 1.1.0
* Menambahkan dukungan untuk pengaturan Ekspor dan Identitas Terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki parameter objek input untuk 'Set-AzActivityLogAlert'
* Memperbaiki parameter 'InputObject' untuk 'Set-AzActionGroup' [#10868]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Menambahkan cmdlet baru untuk FirewallPolicy Azure
    - 'New-AzFirewallPolicyDnsSetting'
    - Dukungan untuk FQDN Tujuan dalam Aturan Jaringan untuk Kebijakan Firewall
* Menambahkan dukungan untuk operasi kumpulan alamat backend
    - 'New-AzLoadBalancerBackendAddressConfig'
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'
    - 'Remove-AzLoadBalancerBackendAddressPool'
    - 'Get-AzLoadBalancerBackendAddressPool'
* Menambahkan validasi nama untuk 'New-AzIpGroup'
* Menambahkan cmdlet baru untuk FirewallPolicy Azure
    - 'New-AzFirewallPolicyThreatIntelWhitelist'
* Memperbarui perintah di bawah ini untuk fitur: Server dns kustom atur/hapus di P2SVpnGateway VirtualWan.
    - Memperbarui New-AzP2sVpnGateway: Menambahkan parameter opsional '-CustomDnsServer' bagi pelanggan untuk menentukan server dns mereka untuk diatur di P2SVpnGateway, yang dapat digunakan oleh klien Titik ke situs.
    - Memperbarui Update-AzP2sVpnGateway: Menambahkan parameter opsional '-CustomDnsServer' bagi pelanggan untuk menentukan server dns mereka untuk diatur di P2SVpnGateway, yang dapat digunakan oleh klien Titik ke situs.
* Memperbarui 'Update-AzVpnGateway'
    - Menambahkan parameter opsional '-BgpPeeringAddress' bagi pelanggan untuk menentukan bgps kustom mereka untuk diatur di VpnGateway.
* Menambahkan cmdlet baru untuk mendukung reset status perutean sumber daya VirtualHub:
    - 'Reset-AzHubRouter'
* Memperbarui hal-hal di bawah ini berdasarkan perubahan swagger baru-baru ini untuk Kebijakan Firewall
    - Mengubah nama untuk RuleGroup, RuleCollectionGroup, dan RuleType
    - Menambahkan dukungan untuk Koleksi Aturan NAT Kebijakan Firewall untuk mendukung beberapa Kumpulan Aturan NAT
* [Perubahan yang Berisiko] Menambahkan parameter wajib 'SourceIpGroup' untuk 'New-AzFirewallPolicyApplicationRule' dan 'New-AzFirewallPolicyNetworkRule'.
* [Perubahan yang Berisiko] Memperbaiki 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' menjadi wajib.
* [Perubahan yang Berisiko] Memperbaiki 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' menjadi wajib.
* [Perubahan yang Berisiko] Menghapus parameter wajib: 'TranslatedAddress', 'TranslatedPort' untuk 'New-AzFirewallPolicyNatRuleCollection'.
* Menambahkan cmdlet baru untuk mendukung PrivateLink Pada Application Gateway
    - 'New-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Get-AzApplicationGatewayPrivateLinkConfiguration'
    - 'New-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Set-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Remove-AzApplicationGatewayPrivateLinkConfiguration'
    - 'New-AzApplicationGatewayPrivateLinkIpConfiguration'
* Menambahkan cmdlet baru untuk sumber daya turunan HubRouteTables dari VirtualHub.
    - 'New-AzVHubRoute'
    - 'New-AzVHubRouteTable'
    - 'Get-AzVHubRouteTable'
    - 'Update-AzVHubRouteTable'
    - 'Remove-AzVHubRouteTable'
* Memperbarui cmdlet yang ada untuk mendukung parameter input RoutingConfiguration opsional untuk perutean kustom di VirtualWan.
    - 'New-AzExpressRouteConnection'
    - 'Set-AzExpressRouteConnection'
    - 'New-AzVirtualHubVnetConnection'
    - 'Update-AzVirtualHubVnetConnection'
    - 'New-AzVpnConnection'
    - 'Update-AzVpnConnection'
    - 'New-AzP2sVpnGateway'
    - 'Update-AzP2sVpnGateway'

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbaiki bug PSWorkspace tidak menerapkan IOperationalInsightsWorkspace [#12135]
* Menambahkan 'pergb2018' ke set parameter nilai yang valid 'Sku' di 'Set-AzOperationalInsightsWorkspace'
* Menambahkan alias 'FunctionParameters' untuk parameter 'FunctionParameter' ke
    - 'New-AzOperationalInsightsSavedSearch'
    - 'Set-AzOperationalInsightsSavedSearch'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup menambahkan dukungan untuk mengambil item MAB.
* Azure Site Recovery mendukung jenis disk 'StandardSSD_LRS'

#### <a name="azresources"></a>Az.Resources
* Menambahkan 'UsageLocation', 'GivenName', 'Surname', 'AccountEnabled', 'MailNickname', 'Mail' di 'PSADUser' [#10526] [#10497]
* Memperbaiki masalah '-Mail' tidak berfungsi di 'Get-AzADUser' [#11981]
* Menambahkan parameter '-ExcludeChangeType' ke 'Get-AzDeploymentWhatIfResult' dan 'Get-AzResourceGroupDeploymentWhatIfResult'
* Menambahkan parameter '-WhatIfExcludeChangeType' ke 'New-AzDeployment' dan 'New-AzResourceGroupDeployment'
* Memperbarui cmdlet 'Test-Az*Deployment' untuk menampilkan pesan kesalahan yang lebih baik
* Memperbaiki pesan bantuan untuk parameter '-Nama' dari pembuatan penyebaran dan cmdlet What-If

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk perwakilan layanan untuk Set cmdlet Admin Azure Active Directory SQL Server
* Memperbaiki masalah sinkronisasi dalam cmdlet Klasifikasi Data.
* Mendukung pencarian pengguna melalui email di 'Set-AzSqlServerActiveDirectoryAdministrator' [#12192]

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan Akun penyimpanan dengan RequireInfrastructureEncryption
    -  'New-AzStorageAccount'
* Memindahkan logika pemuatan Azure.Core ke Az.Accounts

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan perlindungan untuk menghapus aplikasi web yang dibuat jika pemulihan gagal di 'Restore-AzDeletedWebApp'
* Menambahkan 'SourceWebApp.Location' untuk 'New-AzWebApp' dan 'New-AzWebAppSlot'
* Memperbaiki bug yang mencegah perubahan pengaturan Kontainer di 'Set-AzWebApp' dan 'Set-AzWebAppSlot'
* Memperbaiki bug untuk mendapatkan SiteConfig saat -Name tidak diberikan untuk Get-AzWebApp
* Menambahkan dukungan untuk membuat ASP untuk Aplikasi Linux
* Menambahkan pengecualian untuk klon di seluruh grup sumber daya

## <a name="420---june-2020"></a>4.2.0 - Juni 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah yang dapat menyebabkan Az melewati log di pekerjaan Azure Automation atau PowerShell [#11492]

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Memperbarui versi assembly dari cmdlet data plane

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbarui versi assembly dari cmdlet manajemen layanan

#### <a name="azbilling"></a>Az.Billing
* Memperbarui versi assembly dari cmdlet konsumsi

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung kontrol PrivateEndpoint dan PublicNetworkAccess.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi assembly dari cmdlet V2 pabrik data

#### <a name="azdatashare"></a>Az.DataShare
* Ketersediaan umum modul ''Az.DataShare''

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Ketersediaan umum modul ''Az.DesktopVirtualization''

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Meningkatkan SDK ke 0.21.0
* Menambahkan parameter opsional ke
    - 'New-AzOperationalInsightsSavedSearch'
    - 'Set-AzOperationalInsightsSavedSearch'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Mengoreksi contoh 3 untuk 'Start-AzPolicyComplianceScan'

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Memperbarui versi assembly dari cmdlet PowerBI

#### <a name="azprivatedns"></a>Az.PrivateDns
* Mengoreksi pemformatan string output verbose untuk Remove-AzPrivateDnsRecordSet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk membuat rencana pemulihan untuk replikasi zona ke zona dari input xml.
* Memperbarui versi assembly dari cmdlet SiteRecovery dan Backup

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter Tail ke cmdlet Get-AzDeploymentScriptLog dan Save-AzDeploymentScriptLog
* Memformat properti Output dan menampilkannya pada output cmdlet Get-AzDeploymentScript
* Mengganti nama parameter -DeploymentScriptInputObject menjadi -DeploymentScriptObject
* Memperbaiki nama file/target yang hilang di pesan cmdlet.
* Memperbarui versi assembly dari pengelola sumber daya dan cmdlet tag

#### <a name="azsql"></a>Az.Sql
* Menambahkan UsePrivateLinkConnection ke 'New-AzSqlSyncGroup', 'Update-AzSqlSyncGroup', 'New-AzSqlSyncMember', dan 'Update-AzSqlSyncMember'
* Menambahkan SyncMemberAzureDatabaseResourceId ke 'New-AzSqlSyncMember' dan 'Update-AzSqlSyncMember'
* Menambahkan dukungan pencarian pengguna Tamu ke Set cmdlet Admin Azure Active Directory SQL Server

#### <a name="azstorage"></a>Az.Storage
* Memperbarui versi assembly dari cmdlet data plane

## <a name="410---may-2020"></a>4.1.0 - Mei 2020
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Mendukung versi PowerShell: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7
* Ketersediaan umum Az.Functions
* Az.ApiManagement, Az.Batch, Az.Compute, Az.KeyVault, Az.Monitor, Az.Network, Az.OperationalInsights, Az.Resources, dan Az.Storage memiliki rilis besar

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui 'Add-AzEnvironment' dan 'Set-AzEnvironment' untuk menerima parameter 'AzureSynapseAnalyticsEndpointResourceId' dan 'AzureSynapseAnalyticsEndpointSuffix'
* Menambahkan assembly terkait Azure.Core ke Az.Accounts, mendukung platform PowerShell mencakup Windows PowerShell 5.1, PowerShell Core 6.2.4, PowerShell 7+

#### <a name="azaks"></a>Az.Aks
* Meningkatkan versi API ke 01-10-2019
* Mendukung untuk membuat AKS menggunakan kontainer Windows
* Menyediakan cmdlet baru: 'New-AzAksNodePool', 'Update-AzAksNodePool', 'Remove-AzAksNodePool', 'Get-AzAksNodePool', 'Install-AzAksKubectl', 'Get-AzAksVersion'

#### <a name="azapimanagement"></a>Az.ApiManagement
* Parameter 'New-AzApiManagement' dan 'Set-AzApiManagement': [-AssignIdentity] berganti nama menjadi [-SystemAssignedIdentity]
* 'New-AzApiManagement' dan 'Set-AzApiManagement': Parameter baru ditambahkan: [`-UserAssignedIdentity <String[]>`]
* 'Get-AzApiManagementProperty': berganti nama menjadi 'Get-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'New-AzApiManagementProperty': berganti nama menjadi 'New-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'Set-AzApiManagementProperty': berganti nama menjadi 'Set-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'Remove-AzApiManagementProperty': berganti nama menjadi 'Remove-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* Menambahkan cmdlet 'Get-AzApiManagementAuthorizationServerClientSecret' baru dan 'Get-AzApiManagementAuthorizationServer' tidak akan menampilkan rahasia klien lagi.
* Menambahkan cmdlet 'Get-AzApiManagementNamedValueSecretValue' baru dan 'Get-AzApiManagementNamedValue' tidak akan menampilkan nilai rahasia.
* Menambahkan cmdlet 'Get-AzApiManagementOpenIdConnectProviderClientSecret' baru dan cmdlet 'Get-AzApiManagementOpenIdConnectProvider' tidak akan menampilkan rahasia klien lagi.
* Menambahkan cmdlet 'Get-AzApiManagementSubscriptionKey' baru dan 'Get-AzApiManagementSubscription' tidak akan menampilkan kunci berlangganan lagi.
* Menambahkan cmdlet 'Get-AzApiManagementTenantAccessSecret' baru dan 'Get-AzApiManagementTenantAccess' tidak akan menampilkan kunci lagi.
* Menambahkan cmdlet 'Get-AzApiManagementTenantGitAccessSecret' baru dan 'Get-AzApiManagementTenantGitAccess' tidak akan menampilkan kunci lagi.

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan parameter: 'RetentionInDays' 'PublicNetworkAccessForIngestion' 'PublicNetworkAccessForQuery' untuk 'New-AzApplicationInsights'
* Membuat cmdlet 'Update-AzApplicationInsights'
* Membuat cmdlet untuk Akun Penyimpanan Tertaut

#### <a name="azbatch"></a>Az.Batch
* Memperbarui Az.Batch untuk menggunakan SDK 'Microsoft.Azure.Batch' versi 13.0.0 dan SDK 'Microsoft.Azure.Management.Batch' versi 9.0.0.
* Menambahkan kemampuan untuk memilih jenis sertifikat yang ditambahkan menggunakan parameter '-CertificateKind' baru ke 'New-AzBatchCertificate'.
* Menghapus properti 'ApplicationPackages' dari 'PSApplication' yang sebelumnya selalu ''.
  - Paket spesifik di dalam aplikasi sekarang dapat diambil menggunakan 'Get-AzBatchApplicationPackage'. Misalnya: 'Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication'.
* Saat membuat kumpulan menggunakan 'New-AzBatchPool', properti 'VirtualMachineImageId’ dari 'PSImageReference' sekarang hanya dapat merujuk ke gambar Shared Image Gallery.
* Saat membuat kumpulan menggunakan 'New-AzBatchPool', kumpulan dapat disediakan tanpa IP publik menggunakan properti 'PublicIPAddressConfiguration' baru dari 'PSNetworkConfiguration'.
  - Properti 'PublicIPs' dari 'PSNetworkConfiguration' telah pindah ke 'PSPublicIPAddressConfiguration' juga. Properti ini hanya dapat ditentukan jika 'IPAddressProvisioningType' adalah 'UserManaged'.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HostId ke cmdlet 'Update-AzVM'
* Mmeperbarui dokumen Bantuan untuk cmdlet 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVmss', 'Set-AzVMOperatingSystem' dan 'Set-AzVmssOsProfile'.
* Perubahan mencolok
    - Parameter FilterExpression dihapus dari cmdlet 'Get-AzVMImage'.
    - Parameter AssignIdentity dihapus dari cmdlet 'New-AzVmssConfig', 'New-AzVMConfig' dan 'Update-AzVM'.
    - AutomaticRepairMaxInstanceRepairsPercent dihapus dari cmdlet 'New-AzVmssConfig' dan 'Update-AzVmss'.
    - Properti AvailabilitySetsColocationStatus, VirtualMachinesColocationStatus dan VirtualMachineScaleSetsColocationStatus dihapus dari ProximityPlacementGroup.
    - Properti MaxInstanceRepairsPercent dihapus dari AutomaticRepairsPolicy.
    - Jenis AvailabilitySets, VirtualMachines, dan VirtualMachineScaleSets diubah dari `IList<SubResource>` menjadi `IList<SubResourceWithColocationStatus>`.
* Deskripsi untuk cmdlet 'Get-AzVM' telah diperbarui untuk menggambarkannya dengan lebih baik.

#### <a name="azdatafactory"></a>Az.DataFactory
* Mendukung CRUD properti runtime aliran data di IR Terkelola.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan cmdlet baru untuk pembuatan, pembaruan, percoban kembali, dan penghapusan objek Mesin Aturan Front Door
* Menambahkan cmdlet pembantu untuk konstruksi objek Mesin Aturan Front Door
* Menambahkan referensi Mesin Aturan ke objek Aturan Perutean Front Door.
* Menambahkan parameter Private Link ke objek Backend Front Door

#### <a name="azfunctions"></a>Az.Functions
* Ketersediaan umum modul ''Az.Functions''

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung Enkripsi disk kunci terkelola pelanggan.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Kebijakan akses tidak lagi default ke prinsipal saat ini

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan cmdlet untuk memanggil kueri di IoT hub untuk mengambil informasi menggunakan bahasa seperti SQL.
* Memperbaiki masalah yang mana 'Add-AzIotHubDevice' gagal membuat Perangkat Berkemampuan Edge tanpa perangkat turunan [#11597]
* Menambahkan cmdlet untuk menghasilkan token SAS untuk Iot Hub, perangkat atau modul.
* Menambahkan cmdlet untuk memanggil kueri metrik konfigurasi.
* Mengelola penyebaran otomatis IoT Edge dalam skala besar. Cmdlet yang baru adalah:
    - 'Add-AzIotHubDeployment'
    - 'Get-AzIotHubDeployment'
    - 'Remove-AzIotHubDeployment'
    - 'Set-AzIotHubDeployment'
* Menambahkan cmdlet untuk memanggil kueri metrik penyebaran IoT Edge.
* Menambahkan cmdlet untuk menerapkan konten konfigurasi ke perangkat tepi yang ditentukan.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menghapus dua alias: 'New-AzKeyVaultCertificateAdministratorDetails' dan 'New-AzKeyVaultCertificateOrganizationDetails'
* Mengaktifkan penghapusan sementara secara default saat membuat brankas kunci
* Aturan jaringan dapat diatur untuk mengatur aksesibilitas dari lokasi jaringan tertentu saat membuat brankas kunci
* Menambahkan dukungan untuk membawa kunci Anda sendiri (BYOK)
    - 'Add-AzKeyVaultKey' mendukung pembuatan kunci pertukaran kunci
    - 'Get-AzKeyVaultKey' mendukung pengunduhan kunci publik dalam format PEM
* Memperbarui bagian 'KeyOps' dari dokumen bantuan 'Add-AzKeyVaultKey'

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug untuk 'Set-AzDiagnosticSettings', kebijakan retensi tidak akan berlaku untuk semua kategori [#11589]
* Mendukung kriteria ketersediaan WebTest untuk peringatan metrik V2
    - 'New-AzMetricAlertRuleV2Criteria': opsi untuk membuat kriteria ketersediaan webtest ditambahkan
    - 'Add-AzMetricAlertRuleV2': mendukung kriteria ketersediaan webtest baru
* Menghapus definisi redundan untuk RetentionPolicy di PSLogProfile [#7608]
* Menghapus properti redundan yang didefinisikan di PSEventData [#11353]
* Mengganti nama 'Get-AzLog' menjadi 'Get-AzActivityLog'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan atribut perubahan yang berisiko untuk memberi tahu bahwa perilaku default Zona akan diubah
    - 'New-AzPublicIpAddress'
    - 'New-AzPublicIpPrefix'
    - 'New-AzLoadBalancerFrontendIpConfig'
* Menambahkan dukungan untuk sumber daya tingkat atas baru SecurityPartnerProvider
    - Cmdlet baru yang ditambahkan:
        - New-AzSecurityPartnerProvider
        - Remove-AzSecurityPartnerProvider
        - Get-AzSecurityPartnerProvider
        - Set-AzSecurityPartnerProvider
* Menambahkan 'RequiredZoneNames' di 'PSPrivateLinkResource' dan 'GroupId' di 'PSPrivateEndpointConnection'
* Memperbaiki jenis parameter SuccessThresholdRoundTripTimeMs yang salah untuk New-AzNetworkWatcherConnectionMonitorTestConfigurationObject
* Memperbarui cmdlet VirtualWan untuk mengatur nilai default argumen AllowVnetToVnetTraffic ke True.
    - 'New-AzVirtualWan'
    - 'Update-AzVirtualWan'
* Menambahkan cmdlet baru untuk mendukung grup zona DNS untuk titik akhir privat
    - 'New-AzPrivateDnsZoneConfig'
    - 'Get-AzPrivateDnsZoneGroup'
    - 'New-AzPrivateDnsZoneGroup'
    - 'Set-AzPrivateDnsZoneGroup'
    - 'Remove-AzPrivateDnsZoneGroup'
* Menambahkan parameter 'DNSEnableProxy', 'DNSRequireProxyForNetworkRules' dan 'DNSServers' ke 'AzureFirewall'
* Menambahkan parameter 'EnableDnsProxy', 'DnsProxyNotRequiredForNetworkRule' dan 'DnsServer' ke 'AzureFirewall'
    - Cmdlet yang diperbarui:
        - New-AzFirewall

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbaarui kode lama untuk menerapkan SDK baru yang dihasilkan
* Menghapus cmdlet karena API yang tidak digunakan lagi
    - 'Get-AzOperationalInsightsSavedSearchResult' (alias 'Get-AzOperationalInsightsSavedSearchResults')
    - 'Get-AzOperationalInsightsSearchResult' (alias 'Get-AzOperationalInsightsSearchResults')
    - 'Get-AzOperationalInsightsLinkTarget' (alias 'Get-AzOperationalInsightsLinkTargets')
* Menambahkan parameter untuk 'Set-AzOperationalInsightsWorkspace' dan 'New-AzOperationalInsightsWorkspace'
* Membuat cmdlet untuk Akun Stoarge Tertaut
* Membuat cmdlet untuk Kluster dan Layanan Tertaut

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery menambahkan dukungan untuk melindungi mesin virtual grup penempatan kedekatan untuk Azure ke penyedia Azure.
* Azure Site Recovery menambahkan dukungan untuk replikasi zona ke zona.
* Azure Backup Menambahkan Dukungan retensi jangka panjang untuk Titik Pemulihan Azure FileShare.
* Azure Backup Menambahkan properti pengecualian disk ke output cmdlet 'Get-AzRecoveryServicesBackupItem'.
* Menambahkan titik akhir privat untuk file info masuk Vault untuk layanan pemulihan situs.

#### <a name="azresources"></a>Az.Resources
* Menambahkan peringatan pesan tentang menampilkan penundaan saat membuat Definisi Peran baru
* Mengubah cmdlet kebijakan untuk mengeluarkan objek yang diketik dengan kuat
* Menghapus parameter '-TenantLevel' yang digunakan untuk pada cmdlet 'Get-AzResourceLock' [#11335]
* Memperbaiki 'Remove-AzResourceGroup -Id ResourceId'[#9882]
* Menambahkan cmdlet baru untuk mendapatkan hasil What-If templat ARM di cakupan grup sumber daya: 'Get-AzDeploymentResourceGroupWhatIfResult'
* Menambahkan cmdlet baru untuk mendapatkan hasil What-If templat ARM pada cakupan langganan: 'Get-AzDeploymentWhatIfResult'
   - Alias: 'Get-AzSubscriptionDeploymentApaIf'
* Mengambil alih parameter '-WhatIf' dan '-Confirm' untuk 'New-AzDeployment' dan 'New-AzResourceGroupDeployment' untuk menggunakan hasil What-If templat ARM
* Menambahkan pesan penghentian untuk parameter 'ApiVersion' di cmdlet penyebaran
* Menambahkan kemampuan untuk menampilkan pesan kesalahan yang ditingkatkan untuk kegagalan penyebaran
* Menambahkan pengelogan correlationId untuk kegagalan penyebaran
* Menambahkan properti 'error' ke output skrip penyebaran
* Memperbarui nuget Microsoft.Azure.Management.ResourceManager ke '3.7.1-pratinjau'
* Menghapus kasus pengujian tertentu seperti properti Kesalahan di DeploymentValidateResult telah berubah menjadi readonly dari nuget 3.7.1-pratinjau
* Membawa GenericResourceExpanded dari SDK ResourceManager 3.7.1-pratinjau
* Menambahkan dukungan tag untuk semua cmdlet Get untuk penyebaran, serta
    - 'New-AzDeployment'
    - 'New-AzManagementGroupDeployment'
    - 'New-AzResourceGroupDeployment'
    - 'New-AzTenantDeployment'

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki bug dalam menambahkan sertifikat menggunakan --SecretIdentifier yang mendapatkan thumbprint sertifikat yang salah

#### <a name="azsql"></a>Az.Sql
* Meningkatkan performa:
    - 'Set-AzSqlDatabaseSensitivityClassification'
    - 'Set-AzSqlInstanceDatabaseSensitivityClassification'
    - 'Remove-AzSqlDatabaseSensitivityClassification'
    - 'Remove-AzSqlInstanceDatabaseSensitivityClassification'
    - 'Enable-AzSqlDatabaseSensitivityRecommendation'
    - 'Enable-AzSqlInstanceDatabaseSensitivityRecommendation'
    - 'Disable-AzSqlDatabaseSensitivityRecommendation'
    - 'Disable-AzSqlInstanceDatabaseSensitivityRecommendation'
* Menghapus validasi sisi klien parameter 'RetentionDays' dari cmdlet 'Set-AzSqlDatabaseBackupShortTermRetentionPolicy'
* Mengaudit ke akun penyimpanan di Vnet, memperbaiki bug saat membuat peran Kontributor Data Blob Storage.

#### <a name="azstorage"></a>Az.Storage
* Menambahkan '-AsJob' untuk mendapatkan/mendaftarkan cmdlet akun 'Get-AzStorageAccount'
* Menjadikan KeyVersion opsional saat memperbarui Akun penyimpanan dengan KeyvaultEncryption, untuk mendukung rotasi otomatis kunci
    - 'Set-AzStorageAccount'
* Memperbaiki penghapusan Azure File Directory gagal dengan alur
    - 'Remove-AzStorageDirectory'
* Memperbaiki [#9880]: Mengubah definisi nilai NetWorkRule DefaultAction agar selaras dengan swagger.
    - 'Update-AzStorageAccountNetworkRuleSet'
    - 'Get-AzStorageAccountNetworkRuleSet'
* Memperbaiki [#11624]: Melewati aturan duplikat saat menambahkan NetworkRules, untuk menghindari kegagalan server
    - 'Add-AzStorageAccountNetworkRule'
* Meningkatkan SDK Microsoft.Azure.Cosmos.Table ke 1.0.7
* Menambahkan pesan peringatan untuk mengingatkan pengguna agar daftar lagi dengan ContinuationToken ketika hanya sebagian item yang ditampilkan dalam daftar Item DataLake Gen2,
    - 'Get-AzDataLakeGen2ChildItem'
* Mendukung untuk membuat atau memperbarui Akun penyimpanan dengan Autentikasi Layanan Domain Direktori Aktif Azure Files
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung ke kunci Kerberos baru atau daftar Akun penyimpanan
    -  'New-AzStorageAccountKey'
    -  'Get-AzStorageAccountKey'
* Mendukung failover Akun penyimpanan
    - 'Invoke-AzStorageAccountFailover'
* Memperbarui bantuan dari 'Get-AzStorageBlobCopyState'
* Memperbarui bantuan dari 'Get-AzStorageFileCopyState' dan 'Start-AzStorageBlobCopy'
* Mengintegrasikan Pustaka klien Storage v12 ke cmdlet Antrean dan File
* Mengubah jenis output dari CloudFile ke AzureStorageFile, output asli akan menjadi properti turunan dari output baru
    - 'Get-AzStorageFile'
    - 'Remove-AzStorageFile'
    - 'Get-AzStorageFileContent'
    - 'Set-AzStorageFileContent'
    - 'Start-AzStorageFileCopy'
* Mengubah jenis output dari CloudFileDirectory ke AzureStorageFileDirectory, output asli akan menjadi properti turunan dari output baru
    - 'New-AzStorageDirectory'
    - 'Remove-AzStorageDirectory'
* Mengubah jenis output dari CloudFile ke AzureStorageFile, output asli akan menjadi properti turunan dari output baru
    - 'Get-AzStorageShare'
    - 'New-AzStorageShare'
    - 'Remove-AzStorageShare'
* Mengubah jenis output dari FileShareProperties ke AzureStorageFileShare, output asli akan menjadi properti sub-turunan dari output baru
    - 'Set-AzStorageShareQuota'

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Memperbaiki nama profil yang salah di output verbose 'DisableAzureTrafficManagerEndpoint'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki kesalahan ketik pada bantuan 'Update-AzWebAppAccessRestrictionConfig'.

## <a name="380---april-2020"></a>3.8.0 - April 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui URL survei Azure PowerShell di 'Resolve-AzError' [#11507]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan pemberitahuan perubahan yang berisiko untuk perubahan output cmdlet Azure File dalam rilis mendatang
* 'Set-AzApiManagementGroup' Memperbarui dokumentasi untuk menentukan parameter GroupId

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki tampilan SKU harga terkait ChinaCDN

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung Identitas, Enkripsi, UserOwnedStorage

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet 'Set-AzVmssOrchestrationServiceState'.
* 'Get-AzVmss' dengan -InstanceView menampilkan status OrchestrationService.

#### <a name="aziothub"></a>Az.IotHub
* Mengelola konfigurasi kembar perangkat IoT, Cmdlet baru adalah:
    - 'Get-AzIotHubDeviceTwin'
    - 'Update-AzIotHubDeviceTwin'
* Menambahkan cmdlet untuk memanggil metode langsung pada perangkat di Iot Hub.
* Mengelola konfigurasi kembar modul perangkat IoT, Cmdlet baru adalah:
    - 'Get-AzIotHubModuleTwin'
    - 'Update-AzIotHubModuleTwin'
* Mengelola konfigurasi manajemen perangkat otomatis IoT dalam skala besar. Cmdlet yang baru adalah:
    - 'Add-AzIotHubConfiguration'
    - 'Get-AzIotHubConfiguration'
    - 'Remove-AzIotHubConfiguration'
    - 'Set-AzIotHubConfiguration'
* Menambahkan cmdlet untuk memanggil metode modul tepi dalam Iot Hub.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan cmdlet baru 'Update-AzKeyVault' yang dapat mengaktifkan perlindungan penghapusan sementara dan pembersihan di brankas
* Menambahkan dukungan ke Microsoft.PowerShell.SecretManagement [#11178]
* Memperbaiki kesalahan dalam contoh 'Remove-AzKeyVaultManagedStorageSasDefinition' [#11479]
* Menambahkan dukungan ke titik akhir privat

#### <a name="azmaintenance"></a>Az.Maintenance
* Menerbitkan versi rilis cmdlet Pemeliharaan untuk GA

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan cmdlet untuk cakupan link privat
    - 'Get-AzInsightsPrivateLinkScope'
    - 'Remove-AzInsightsPrivateLinkScope'
    - 'New-AzInsightsPrivateLinkScope'
    - 'Update-AzInsightsPrivateLinkScope'
    - 'Get-AzInsightsPrivateLinkScopedResource'
    - 'New-AzInsightsPrivateLinkScopedResource'
    - 'Remove-AzInsightsPrivateLinkScopedResource'

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk mengaktifkan koneksi pada IP privat untuk Gateway Virtual Network.
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Memperbarui cmdlet untuk mengaktifkan LocalNetworkGateways dan VpnSites berbasis FQDN
    - 'New-AzLocalNetworkGateway'
    - 'New-AzVpnSiteLink'
* Menambahkan dukungan untuk keluarga alamat IPv6 di ExpressRouteCircuitConnectionConfig (Jangkauan Global)
    - Menambahkan 'Set-AzExpressRouteCircuitConnectionConfig'
        - memungkinkan pengaturan semua properti yang ada termasuk IPv6CircuitConnectionProperties
    - Memperbarui 'Add-AzExpressRouteCircuitConnectionConfig'
        - Menambahkan parameter opsional lain AddressPrefixType untuk menentukan keluarga alamat awalan alamat
* Memperbarui cmdlet untuk mengaktifkan pengaturan Batas Waktu DPD pada Koneksi Gateway Virtual Network.
    - Baru-AzVirtualNetworkGatewayConnection
    - Set-AzVirtualNetworkGatewayConnection

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan cmdlet 'Start-AzPolicyComplianceScan' untuk memicu pemindaian kepatuhan kebijakan
* Menambahkan definisi kebijakan, mengatur definisi, dan versi penetapan ke output 'Get-AzPolicyState'

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Meningkatkan pemformatan kode dan kegunaan contoh 'New-AzServiceFabricCluster'

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet 'Get-AzSqlInstanceOperation' dan 'Stop-AzSqlInstanceOperation'
* Mendukung pengauditan ke akun penyimpanan di VNet.

#### <a name="azstorage"></a>Az.Storage
* Menambahkan pemberitahuan perubahan yang berisiko untuk perubahan output cmdlet Azure File dalam rilis mendatang
* Mendukung SkuName baru StandardGZRS, StandardRAGZRS saat membuat/memperbarui akun Penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung DataLake Gen2
    - 'New-AzDataLakeGen2Item'
    - 'Get-AzDataLakeGen2Item'
    - 'Get-AzDataLakeGen2ChildItem'
    - 'Move-AzDataLakeGen2Item'
    - 'Set-AzDataLakeGen2ItemAclObject'
    - 'Update-AzDataLakeGen2Item'
    - 'Get-AzDataLakeGen2ItemContent'
    - 'Remove-AzDataLakeGen2Item'

## <a name="0100-preview---april-2020"></a>0.10.0-preview - April 2020
### <a name="general"></a>Umum
* Modul Az sekarang tersedia dalam pratinjau di Azure Stack Hub. Hal ini memungkinkan kompatibilitas lintas platform dengan Linux dan macOs. Azure Stack Hub sekarang mendukung inti PowerShell dengan modul Az, informasi lebih lanjut [di sini](https://aka.ms/az4AzureStack)
* Profil dukungan modul Az 01-03-2019-hibrid:
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
* Tiga modul PowerShell baru untuk az telah diperkenalkan yang bekerja dengan Azure Stack Hub, yaitu Az.Databox, Az.IotHub, dan Az.EventHub
* Perintah tetap relatif sama, dengan perubahan kecil seperti mengubah AzureRM ke Az
* Link yang diperbarui ke dokumentasi PowerShell untuk Azure Stack Hub dapat ditemukan [di sini](https://aka.ms/InstallASHPowerShell)

#### <a name="azaccounts"></a>Az.Accounts
* Meningkatkan dari ADAL ke MSAL

## <a name="370---march-2020"></a>3.7.0 - Maret 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki 'Get-AzTenant'/'Get-AzDefault'/'Set-AzDefault' yang mengeluarkan NullReferenceException saat tidak login [#10292]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter berikut ke cmdlet 'New-AzDiskConfig':
    - DiskIOPSReadOnly, DiskMBpsReadOnly, MaxSharesCount, GalleryImageReference
* Memungkinkan properti Enkripsi ke Parameter target cmdlet 'New-AzGalleryImageVersion'.
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
* Memperbarui versi SDK .Net ADF ke 4.8.0
* Menambahkan parameter opsional ke perintah 'Invoke-AzDataFactoryV2Pipeline' untuk mendukung eksekusi ulang

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan deskripsi perubahan yang berisiko untuk 'Export-AzDataLakeStoreItem' dan 'Import-AzDataLakeStoreItem'
* Menambahkan opsi pengodean Byte untuk 'New-AzDataLakeStoreItem', 'Add-AzDAtaLakeStoreItemContent', dan 'Get-AzDAtaLakeStoreItemContent'

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung penentuan versi TLS yang didukung minimal saat membuat kluster.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola pengaturan terdistribusi per perangkat. Cmdlet yang baru adalah:
    - 'Get-AzIotHubDistributedTracing'
    - 'Set-AzIotHubDistributedTracing'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan atribut perubahan yang berisiko ke 'New-AzKeyVault'

#### <a name="azmonitor"></a>Az.Monitor
* Memperbarui dokumentasi untuk 'New-AzScheduledQueryRuleLogMetricTrigger'

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk memungkinkan VirtualHubVnetConnections lintas penyewa
    - 'New-AzVirtualHubVnetConnection'
    - 'Update-AzVirtualHubVnetConnection'
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Menghapus dependensi SDK Manajemen Sql
* Cmdlet yang diperbarui untuk memungkinkan asosiasi firewallPolicy paksa
    - 'New-AzApplicationGateway'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Meningkatkan pesan kesalahan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery menambahkan dukungan untuk melakukan perlindungan ulang dan memperbarui properti mesin virtual untuk Virtual Machines terenkripsi disk Azure.
* Menambahkan pemantauan DR properti VmwareToAzure Azure Site Recovery
* Azure Backup menambahkan dukungan untuk pembaruan kebijakan percobaan kembali pada item yang gagal.
* Azure Backup Menambahkan dukungan untuk pengaturan pengecualian disk selama pencadangan dan pemulihan.
* Azure Backup Menambahkan Dukungan untuk Memulihkan Beberapa file/folder di AzureFileShare
* Azure Backup Menambahkan dukungan untuk dukungan Resourcegroup yang ditentukan Pengguna saat memperbarui Kebijakan IaasVM

#### <a name="azresources"></a>Az.Resources
* Memperbaiki 'Get-AzResource -ResourceGroupName -Name -ExpandProperties -ResourceType' agar menggunakan apiVersion sumber daya yang sebenarnya dan bukan apiVersion default [#11267]
* Menambahkan pengelogan correlationId untuk skenario kesalahan
* Perubahan dokumentasi kecil pada 'Get-AzResourceLock'. Menambahkan contoh.
* Kutipan tunggal yang lolos dalam nilai parameter 'Get-AzADUser' [#11317]
* Menambahkan cmdlet baru untuk Skrip Penyebaran ('Get-AzDeploymentScript', 'Get-AzDeploymentScriptLog', 'Save-AzDeploymentScriptLog', 'Remove-AzDeploymentScript')

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter sekunder yang dapat dibaca ke 'Invoke-AzSqlDatabaseFailover'
* Menambahkan cmdlet 'Disable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menyimpan pangkat sensitivitas saat mengklasifikasikan kolom dalam database.

#### <a name="azsupport"></a>Az.Support
* Ketersediaan umum modul 'Az.Support'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk bekerja dengan Aturan Perutean Lalu Lintas webapp melalui cmdlet baru di bawah ini
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
* Menambahkan dukungan untuk mengelola perangkat di Iot Hub. Cmdlet yang baru adalah:
  - 'Add-AzIotHubDevice'
  - 'Get-AzIotHubDevice'
  - 'Remove-AzIotHubDevice'
  - 'Set-AzIotHubDevice'
* Menambahkan dukungan untuk mengelola modul pada perangkat Iot target di Iot Hub. Cmdlet yang baru adalah:
  - 'Add-AzIotHubModule'
  - 'Get-AzIotHubModule'
  - 'Remove-AzIotHubModule'
  - 'Set-AzIotHubModule'
* Menambahkan cmdlet untuk mendapatkan string koneksi perangkat IoT target di Iot Hub.
* Menambahkan cmdlet untuk mendapatkan string koneksi modul pada perangkat IoT target di Iot Hub.
* Menambahkan dukungan untuk mendapatkan/mengatur perangkat induk perangkat IoT. Cmdlet yang baru adalah:
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
* Menandai pengalihan '-Force' dan '-PassThru' sebagai opsional di 'Remove-AzADGroup' [#10849]
* Memperbaiki masalah 'MailNickname' tidak muncul di 'Remove-AzADGroup' [#11167]
* Memperbaiki masalah operasi pipa 'Remove-AzADGroup' tidak berfungsi [#11171]
* Memperbaiki bug referensi null di GetAzureRoleAssignmentCommand
* Menambahkan atribut perubahan yang berisiko untuk perubahan yang akan datang ke cmdlet kebijakan
* Memperbarui 'Get-AzResourceGroup' untuk melakukan pemfilteran tag grup sumber daya di sisi server
* Memperpanjang tag cmdlet untuk menerima -ResourceId
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
* Menambahkan pesan peringatan perubahan yang berisiko untuk perubahan jenis AzureStorageTable di rilis mendatang
    - 'New-AzStorageTable'
    - 'Get-AzStorageTable'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan parameter Tag untuk 'New-AzAppServicePlan' dan 'Set-AzAppServicePlan'
* Menghentikan eksekusi cmdlet jika pengecualian dikeluarkan saat menambahkan domain kustom ke situs web
* Menambahkan dukungan untuk melakukan operasi untuk App Services yang tidak berada dalam grup sumber daya yang sama dengan Paket App Service
* Menerapkan pembatasan akses ke Aplikasi Web/Fungsi di grup sumber daya yang berbeda
* Memperbaiki masalah saat mengatur nama host kustom untuk WebAppSlots

## <a name="350---february-2020"></a>3.5.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Mempebarui telemetri sisi klien.
* Az.IotHub menambahkan cmdlet untuk mendukung pengelolaan perangkat.
* Az.SqlVirtualMachine menambahkan cmdlet untuk Pendengar Grup Ketersediaan.

#### <a name="azresource"></a>Az.Resource
* Memperbaiki bug yang mencegah pembuatan id sumber daya tingkat penyewa yang benar.
* Memperbaiki kesalahan ketik.

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan SubscriptionId, TenantId, dan waktu eksekusi ke dalam data telemetri sisi klien

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan ketik di Contoh 1 dalam dokumentasi referensi untuk 'New-AzAutomationSoftwareUpdateConfiguration'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui SDK ke 7.0
* Memperbarui pesan kesalahan saat isi respons server kosong

#### <a name="azcompute"></a>Az.Compute
* Memungkinkan nilai kosong untuk ProximityPlacementGroupId selama pembaruan

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan cmdlet untuk mendapatkan definisi aturan terkelola yang dapat digunakan di WAF

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola perangkat di Iot Hub. Cmdlet yang baru adalah:
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
* Menambahkan satu catatan parameter tambahan untuk parameter '-EnableProxyProtocol' untuk cmdlet 'New-AzPrivateLinkService'.
* Memperbaiki contoh FilterData di Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Menambahkan contoh Pengambilan Paket untuk mengambil semua paket dalam dan luar di Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Mendukung Kebijakan Azure Firewall pada Firewall VNet
    - Tidak ada cmdlet baru yang ditambahkan. Melonggarkan pembatasan untuk kebijakan firewall pada firewall VNet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Dukungan untuk Restore-as-files pada SQL Database.

#### <a name="azresources"></a>Az.Resources
* Merefaktorisasi cmdlet penyebaran templat
    - Menambahkan cmdlet baru untuk mengelola penyebaran di grup manajemen: *-AzManagementGroupDeployment
    - Menambahkan cmdlet baru untuk mengelola penyebaran di cakupan penyewa: *-AzTenantDeployment
    - Merefaktorisasi cmdlet *-AzDeployment untuk bekerja secara khusus di cakupan langganan
    - Membuat alias *-AzSubscriptionDeployment untuk *-cmdlet AzDeployment
* Memperbaiki 'Update-AzADApplication' saat parameter 'AvailableToOtherTenants' tidak diatur
* Menghapus ApplicationObjectWithoutCredentialParameterSet untuk menghindari AmbiguousParameterSetException.
* Meregenerasi file bantuan

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk pemulihan titik waktu tertentu antar langganan di Instans Terkelola.
* Menambahkan dukungan untuk mengubah generasi perangkat keras Instans Terkelola Sql yang ada
* Memperbaiki contoh bantuan 'Update-AzSqlServerVulnerabilityAssessmentSetting': parameter/output properti - EmailAdmins

#### <a name="azsqlvirtualmachine"></a>Az.SqlVirtualMachine
* Menambahkan cmdlet untuk Pendengar Grup Ketersediaan

#### <a name="azstoragesync"></a>Az.StorageSync
* Memperbarui tataan karakter yang didukung di 'Invoke-AzStorageSyncCompatibilityCheck'.

## <a name="340---february-2020"></a>3.4.0 - Februari 2020

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Menambahkan cmdlet untuk Gremlin, MongoDB, Cassandra, dan Table API.
* Versi .NET SDK yang diperbarui ke 1.0.1
* Menambahkan parameter ConflictResolutionPolicyMode, ConflictResolutionPolicyPath dan ConflictResolutionPolicyPath di Set-AzCosmosDBSqlContainer.
* Menambahkan cmdlet baru untuk Sql API: New-CosmosDBSqlSpatialSpec, New-CosmosDBSqlCompositePath, New-CosmosDBSqlIncludedPathIndex, New-CosmosDBSqlIncludedPath

#### <a name="azaccounts"></a>Az.Accounts
* Menonaktifkan penyimpanan otomatis konteks saat AzureRmContext.json tidak tersedia
* Memperbarui referensi ke Azure Powershell Common ke 1.3.5-pratinjau

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
* Menambahkan alias Name ke atribut VaultName untuk membuat Remove-AzureKeyVault konsisten dengan New-AzureKeyVault.

#### <a name="aznetwork"></a>Az.Network
* Contoh baru ditambahkan ke Set-AzNetworkWatcherConfigFlowLog.md untuk menunjukkan skenario nonaktif Analitik Lalu Lintas.
* Menambahkan dukungan untuk menetapkan konfigurasi IP manajemen ke Azure Firewall - subnet khusus dan IP Publik yang akan digunakan firewall untuk lalu lintas manajemennya
    - Memperbarui cmdlet New-AzFirewall:
        - Menambahkan parameter -ManagementPublicIpAddress (tidak wajib) yang menerima objek Alamat IP Publik
        - Menambahkan metode SetManagementIpConfiguration pada objek firewall - memerlukan subnet dan alamat IP Publik sebagai input - nama subnet harus 'AzureFirewallManagementSubnet'
* Mengoreksi contoh Get-AzNetworkSecurityGroup untuk menampilkan contoh untuk NSG, bukan antarmuka jaringan.
* Memperbaiki kesalahan ketik dalam perintah New-AzVpnSite yang mencegah completer id sumber daya menyelesaikan parameter.
* Menambahkan dukungan untuk Url Konfigurasi dalam Set Tindakan Aturan Penulisan Ulang di Application Gateway
    - Cmdlet baru yang ditambahkan:
        - New-AzApplicationGatewayRewriteRuleUrlConfiguration
    - Memperbarui cmdlet dengan parameter opsional - UrlConfiguration
        - New-AzApplicationGatewayRewriteRuleActionSet
* Menambahkan dukungan untuk sumber daya NetworkWatcher ConnectionMonitor versi 2

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Mendukung evaluasi kepatuhan sebelum menentukan sumber daya apa yang akan diremediasi
    - Menambahkan parameter '-ResourceDiscoverMode' ke Start-AzPolicyRemediation
* Menambahkan cmdlet Get-AzPolicyMetadata untuk mendapatkan sumber daya metadata kebijakan
* Memperbarui Get-AzPolicyState dan Get-AzPolicyStateSummary untuk API versi 01-10-2019

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk menghapus disk yang direplikasi.
* Azure Backup menambahkan dukungan untuk menambahkan tag saat membuat Brankas Layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Menjadikan -Scope sebagai opsional di cmdlet *-AzPolicyAssignment dengan langganan default ke konteks
* Menambahkan contoh pembuatan ADServicePrincipal dengan kata sandi dan info masuk utama

#### <a name="azsql"></a>Az.Sql
Memperbaiki cmdlet New-AzSqlDatabaseSecondary untuk memeriksa keberadaan PartnerDatabaseName, bukan keberadaan DatabaseName.

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaturan Keytype Enkripsi Tabel/Antrean di Buat Akun penyimpanan
    - New-AzStorageAccount
* Menampilkan RequestId saat StorageException tidak memiliki ExtendedErrorInformation
* Memperbaiki Contoh 6 cmdlet Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Az.Websites
* Set-AzWebapp dan Set-AzWebappSlot mendukung properti Grup Ketersediaan AlwaysOn, MinTls, dan FtpsState
* Memperbaiki masalah saat mengatur HttpsOnly bersama dengan mengubah AppservicePlan pada saat yang sama menggunakan Perintah Set-AzWebApp tunggal, sedang mengatur ulang HttpsOnly ke nilai default

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
  - Membuat Kontainer Storage Edge baru
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
* Tambahkan parameter 'PublicIPs' untuk cmd 'Set-AzDataFactoryV2IntegrationRuntime' untuk mengaktifkan pembuatan runtime integrasi Azure-SSIS dengan alamat IP publik statis.

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
* Meningkatkan dependensi Microsoft.Azure.Management.Sql dari 1.36-pratinjau ke 1.37-pratinjau

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery mengubah dukungan untuk vm disk terkelola yang dienkripsi saat tidak aktif dengan ley yang dikelola pelanggan untuk penyedia Azure ke Azure.
* Azure Site Recovery mendukung untuk memasukkan enkripsi disk Set Id sebagai input opsional untuk mengaktifkan perlindungan Vmware ke Azure.
* Azure Site Recovery mendukung untuk memasukkan enkripsi disk Set Id sebagai input opsional di tingkat disk untuk mengaktifkan perlindungan Vmware ke Azure.
* Azure Site Recovery mendukung untuk memperbarui item yang dilindungi replikasi dengan Peta set enkripsi disk untuk HyperV ke Azure.

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
* Dukungan Dapatkan waktu sinkronisasi terakhir akun Storage dengan menjalankan get-AzStorageAccount dengan parameter -IncludeGeoReplicationStats
    - Dapatkan-AkunPenyimpananAz

## <a name="320---december-2019"></a>3.2.0 - Desember 2019

### <a name="general"></a>Umum
* Memperbarui referensi di .psd1 guna menggunakan jalur relatif untuk semua modul

#### <a name="azaccounts"></a>Az.Accounts
* Mengatur UserAgent yang benar pada telemetri sisi klien untuk pratinjau Az 4.0
* Menampilkan pesan kesalahan yang ramah pengguna saat konteks null di pratinjau Az 4.0

#### <a name="azbatch"></a>Az.Batch
* Perbaiki masalah #10602, di mana **New-AzBatchPool** tidak mengirim 'VirtualMachineConfiguration.ContainerConfiguration' atau 'VirtualMachineConfiguration.DataDisks' dengan benar ke server.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.5.0

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
* Menambahkan argumen opsional ke perintah Tambahkan Pengaturan Diagnostik. Argumen pengalihan yang, jika ada, menunjukkan bahwa ekspor ke Log Analytics harus ke skema tetap (alias jenis data khusus)

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk IpGroups di Aplikasi AzureFirewall, Nat & Aturan Jaringan.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan fitur SoftDelete untuk mesin virtual dan menambahkan pengujian untuk softdelete
* Dukungan Azure Site Recovery untuk Azure Disk Encryption One Pass untuk Azure ke Azure.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah ketika penyebaran templat gagal membaca parameter templat jika namanya bertentangan dengan beberapa nama parameter bawaan.
* Memperbarui cmdlet kebijakan untuk menggunakan api baru versi 01-09-2019 yang memperkenalkan dukungan pengelompokan dalam definisi set kebijakan.

#### <a name="azsql"></a>Az.Sql
* Meningkatkan pembuatan penyimpanan dalam pengaktifan otomatis Penilaian Kerentanan ke StorageV2

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan token SAS berbasis Blob/Identitas Kontainer dengan Konteks Penyimpanan berdasarkan autentikasi Oauth
    - New-AzStorageContainerSASToken
    - New-AzStorageBlobSASToken
* Mendukung pencabutan Kunci Delegasi Pengguna Akun Penyimpanan, sehingga semua token SAS Identitas dicabut
    - Revoke-AzStorageAccountUserDelegationKeys
* Meningkatkan ke Microsoft.Azure.Management.Storage 14.2.0, untuk mendukung API baru versi 01-06-2019.
* Mendukung KuotaGiB Berbagi lebih dari 5120 di cmdlet Berbagi File bidang Manajemen, dan tambahkan alias parameter 'Kuota' ke parameter 'QuotaGiB'
  - New-AzRmStorageShare
  - Update-AzRmStorageShare
* Menambahkan alias parameter 'QuotaGiB' ke parameter 'Quota'
  - Set-AzStorageShareQuota
* Memperbaiki masalah Set-AzStorageContainerAcl dapat menghapus Kebijakan Akses yang tersimpan
  - Set-AzStorageContainerAcl

## <a name="310---november-2019"></a>3.1.0 - November 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
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
* Perubahan cmdlet `New-AzDataBoxEdgeShare`
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
* Memperbarui versi SDK .Net ADF ke 4.4.0
* Tambahkan parameter 'ExpressCustomSetup' untuk cmd 'Set-AzDataFactoryV2IntegrationRuntime' untuk mengaktifkan konfigurasi penyiapan dan komponen pihak ke-3 tanpa skrip penyiapan kustom.

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
* Menambahkan parameter 'MinimumTlsVersion' di cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'. Juga, menambahkan 'MinimumTlsVersion' dalam output cmdlet 'Get-AzRedisCache'.
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
* Mengganti nama `CoreQuota` di `BatchAccountContext` menjadi `DedicatedCoreQuota`. Ada juga `LowPriorityCoreQuota` baru .
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
* Memperbarui versi SDK .Net ADF ke 4.3.0

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
    - Get-AzHDInsightMonitoring untuk menggantikan Get-AzHDInsightOMS.
    - Enable-AzHDInsightMonitoring untuk menggantikan Enable-AzHDInsightOMS.
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
* Perubahan yang Berisiko:
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
* Azure Site Recovery mendukung untuk mengonfigurasi sumber daya jaringan seperti NSG, IP publik, dan penyeimbang beban internal untuk Azure ke Azure.
* Azure Site Recovery mendukung untuk menulis ke disk terkelola untuk vMWare ke Azure.
* Azure Site Recovery mendukung pengurangan NIC untuk vMWare ke Azure.
* Azure Site Recovery mendukung jaringan yang dipercepat untuk Azure ke Azure.
* Azure Site Recovery mendukung agen pembaruan otomatis untuk Azure ke Azure.
* Azure Site Recovery mendukung SSD Standar untuk Azure ke Azure.
* Azure Site Recovery mendukung Azure Disk Encryption dua langkah untuk Azure ke Azure.
* Azure Site Recovery Mendukung untuk melindungi disk yang baru ditambahkan untuk Azure ke Azure.
* Menambahkan fitur SoftDelete untuk mesin virtual dan menambahkan pengujian untuk softdelete

#### <a name="azresources"></a>Az.Resources
* Memperbarui perakitan dependensi Microsoft.Extensions.Caching.Memory dari 1.1.1 hingga 2.2

#### <a name="aznetwork"></a>Az.Network
* Mengubah semua cmdlet untuk PrivateEndpointConnection untuk mendukung penyedia layanan generik.
    - Cmdlet yang diperbarui:
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
    - Cmdlet baru yang ditambahkan:
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
    - Cmdlet baru yang ditambahkan:
        - Update-AzVirtualHubVnetConnection
    - Memperbarui cmdlet dengan parameter opsional:
        - New-AzVirtualHubVnetConnection : parameter tambahan EnableInternetSecurity
        - New-AzVpnConnection : parameter tambahan EnableInternetSecurity
        - Update-AzVpnConnection : parameter tambahan EnableInternetSecurity
        - New-AzExpressRouteConnection : parameter tambahan EnableInternetSecurity
        - Set-AzExpressRouteConnection : parameter tambahan EnableInternetSecurity
* Menambahkan dukungan untuk Mengonfigurasi Kebijakan TopLevel WebApplicationFirewall
    - Cmdlet baru yang ditambahkan:
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
* Memperbaiki subnet yang diperlukan dengan nama AzureBastionSubnet di 'PSBastion' tidak peka huruf besar atau kecil
* Dukungan untuk FQDN Tujuan dalam Aturan Jaringan dan FQDN yang Diterjemahkan dalam Aturan NAT untuk Azure Firewall
* Menambahkan dukungan untuk RouteTables sumber daya tingkat atas dari IpGroup
    - Cmdlet baru yang ditambahkan:
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
* Mendukung pengaktifan berbagi File Besar saat membuat atau memperbarui Akun penyimpanan
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Saat menutup/mendapatkan gagang File, lewati periksa jalur input adalah Direktori file atau File, untuk menghindari kegagalan dengan objek di status DeletePending
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
* Memperbarui versi SDK .Net ADF ke 4.2.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki validasi akun sehingga akun dengan '-' dapat diteruskan tanpa domain

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Memperbarui versi powershell ke 1.0.0
* Memperbarui versi SDK ke 1.0.2
* Pembaruan dalam pengujian untuk merujuk ke versi SDK baru
* Memperbarui struktur output dari berlapis menjadi diratakan.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan sumber perutean baru: DigitalTwinChangeEvents
* Perbaikan bug kecil: Get-AzIothub tidak memunculkan subscriptionId

#### <a name="azmonitor"></a>Az.Monitor
* Penerima grup tindakan baru ditambahkan untuk grup tindakan -ItsmReceiver -VoiceReceiver -ArmRoleReceiver -AzureFunctionReceiver -LogicAppReceiver -AutomationRunbookReceiver -AzureAppPushReceiver
* Menggunakan skema peringatan umum yang diaktifkan untuk penerima. Hal ini tidak berlaku untuk SMS, pendorongan Aplikasi Azure, ITSM, dan penerima Voice
* Webhook sekarang mendukung autentikasi direktori aktif Azure .

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru Get-AzAvailableServiceAlias yang dapat dipanggil untuk mendapatkan alias yang dapat digunakan untuk Kebijakan Titik Akhir Layanan.
* Menambahkan dukungan untuk menambahkan pemilih lalu lintas ke Koneksi Gateway Virtual Network
    - Cmdlet baru yang ditambahkan:
        - New-AzureRmTrafficSelectorPolicy
    - Cmdlet diperbarui dengan parameter opsional -TrafficSelectorPolicies -New-AzVirtualNetworkGatewayConnection -Set-AzVirtualNetworkGatewayConnection
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
* Mencantumkan Akun penyimpanan dari langganan, akan mencantumkan dengan NextPageLink
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
* Memperbarui versi SDK .Net ADF ke 4.1.3

#### <a name="azhdinsight"></a>Az.HDInsight
* Memanggil perubahan yang berisiko

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk memanggil failover untuk IotHub ke wilayah pemulihan bencana yang dipasangkan secara geografis.
* Menambahkan dukungan untuk mengelola pengayaan pesan untuk IotHub. Cmdlet yang baru adalah:
  - Add-AzIotHubMessageEnrichment
  - Get-AzIotHubMessageEnrichment
  - Remove-AzIotHubMessageEnrichment
  - Set-AzIotHubMessageEnrichment

#### <a name="azmonitor"></a>Az.Monitor
* Menunjuk ke Monitor SDK terbaru, yaitu 0.24.1-preview
   - Menambahkan perubahan yang tidak berisiko pada cmdlet Metrik, yaitu enumerasi Unit mendukung beberapa nilai baru. Ini adalah cmdlet hanya baca, jadi tidak akan ada perubahan dalam input cmdlet.
   - Permintaan **ActionGroups** versi api sekarang **01-06-2019**, sebelumnya **01-03-2018**. Tes skenario telah diperbarui untuk mengakomodasi perubahan ini.
   - Konstruktor untuk kelas **EmailReceiver** dan **WebhookReceiver** menambahkan satu argumen wajib baru, yaitu nilai Boolean yang disebut **useCommonAlertSchema**. Saat ini, nilainya ditetapkan ke **false** untuk menyembunyikan perubahan yang berisiko ini dari cmdlet. **CATATAN**: perubahan ini bersifat sementara yang harus divalidasi oleh tim Peringatan.
   - Urutan argumen untuk konstruktor **Sumber** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua pengujian unit untuk diperbaiki: mereka dikompilasi, tetapi gagal lulus pengujian.
   - Urutan argumen untuk konstruktor **AlertingAction** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua pengujian unit untuk diperbaiki: mereka dikompilasi, tetapi gagal lulus pengujian.
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
    - Cmdlet yang diperbarui:
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
* Di upload/Downalod Azure File,support perserve properti SMB File sumber (File Attributtes, Waktu Pembuatan File, Waktu Penulisan Terakhir File) di file tujuan
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
* Menambahkan dukungan untuk MSI yang ditetapkan pengguna dalam autentikasi Azure Functions (#9479)

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah output untuk 'Get-AzAks' ([#9847](https://github.com/Azure/azure-powershell/issues/9847))

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbaiki masalah dengan spasi kosong di `productId`, `apiId`, `groupId`, `userId` ([#9351](https://github.com/Azure/azure-powershell/issues/9351))
* **Get-AzApiManagementProduct** - Menambahkan dukungan untuk mengkueri produk menggunakan API ([#9482](https://github.com/Azure/azure-powershell/issues/9482))
* **New-AzApiManagementApiRevision** - Memperbaiki masalah di mana ApiRevisionDescription tidak diatur saat membuat revisi API baru ([#9752](https://github.com/Azure/azure-powershell/issues/9752))
* Memperbaiki kesalahan ketik dalam model `PsApiManagementOAuth2AuthrozationServer` ke `PsApiManagementOAuth2AuthorizationServer`

#### <a name="azbatch"></a>Az.Batch
* Memperbaiki kesalahan ketik dalam pesan bantuan dan dokumentasi

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki kesalahan ketik di CDN pembantu konversi modul

#### <a name="azcompute"></a>Az.Compute
* Menambahkan VmssId ke cmdlet **New-AzVMConfig**
* Menambahkan `TerminateScheduledEvents` parameter dan `TerminateScheduledEventNotBeforeTimeoutInMinutes` ke **New-AzVmssConfig** dan **Update-AzVmss**
* Menambahkan `HyperVGeneration` properti ke objek gambar VM
* Menambahkan fitur Host dan HostGroup
  - Cmdlet baru:
    - **New-AzHostGroup**
    - **New-AzHost**
    - **Get-AzHostGroup**
    - **Get-AzHost**
    - **Remove-AzHostGroup**
    - **Remove-AzHost**
  - Menambahkan `HostId` parameter ke **New-AzVMConfig** dan **New-AzVM**
* Contoh yang diperbarui dalam dokumentasi **Invoke-AzVMRunCommand** untuk menggunakan nama parameter yang benar
* Deskripsi yang diperbarui `-VolumeType` dalam dokumentasi referensi **Set-AzVMDiskEncryptionExtension** dan **Set-AzVmssDiskEncryptionExtension**

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki kesalahan ketik dalam dokumentasi **New-AzDataFactoryEncryptValue**
* Memperbarui versi SDK .Net ADF ke 4.1.2
* Menambahkan parameter ke **Set-AzureRmDataFactoryV2IntegrationRuntime** untuk mengaktifkan Self-Hosted Integration Runtime sebagai proksi untuk SSIS Integration Runtime:
  - `DataProxyIntegrationRuntimeName`
  - `DataProxyStagingLinkedServiceName`
  - `DataProxyStagingPath`
* **PSTriggerRun** yang diperbarui untuk menampilkan alur, pesan, dan properti yang dipicu, dan **PSActivityRun** untuk menampilkan jenis aktivitas

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki masalah di mana **Get-DataLakeStoreDeletedItem** akan menggantung pada kesalahan dan pengecualian jarak jauh

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki kesalahan ketik `VirtualNteworkRule` di Set-AzEventHubNetworkRuleSet ([#9658](https://github.com/azure/azure-powershell/issues/9658))
* Memperbaiki masalah saat Set-AzEventHubNamespace menggunakan PATCH alih-alih PUT ([#9558](https://github.com/azure/azure-powershell/issues/9558))
* Menambahkan `EnableKafka` parameter ke cmdlet **Set-AzEventHubNamespace**
* Memperbaiki masalah pembuatan aturan dengan `Listen` hak ([#9786](https://github.com/azure/azure-powershell/issues/9786))

#### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* Memperbaiki kesalahan ketik dokumentasi

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam dokumentasi bantuan

#### <a name="aznetwork"></a>Az.Network
* **New-AzPrivateLinkServiceIpConfig yang Diperbarui**:
  - Menghentikan parameter `PublicIpAddress` karena ini tidak pernah digunakan di sisi server.
  - Menambahkan parameter `Primary` opsional yang menunjukkan apakah konfigurasi IP saat ini adalah yang utama
* Peningkatan penanganan pengecualian kesalahan permintaan dari SDK
* Memperbaiki logika validasi untuk Awalan IP Ipv6 untuk memeriksa panjang awalan IPv6 yang benar
* Menambahkan parameter yang diatur untuk mendapatkan dengan id sumber daya subnet ke **Get-AzVirtualNetworkSubnetConfig**
* Deskripsi parameter **Lokasi** yang diperbarui untuk **AzNetworkServiceTag**

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Dokumentasi yang diperbarui untuk **New-AzOperationalInsightsLinuxSyslogDataSource**:
  - Menambahkan contoh
  - Deskripsi yang diperbarui untuk `-Name` parameter
* Menambahkan contoh untuk **New-AzOperationalInsightsWindowsEventDataSource**
* Mengubah deskripsi `-Name` parameter untuk **New-AzOperationalInsightsWindowsEventDataSource**

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dokumentasi yang diperbarui untuk **Get-AzRecoveryServicesBackupJobDetail**

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk API versi baru 2019-05-10 untuk Microsoft.Resource
  - Menambahkan dukungan untuk 'copy.count = 0' untuk variabel, sumber daya, dan properti
  - Sumber daya dengan 'condition = false' atau 'copy.count = 0' akan dihapus dalam mode lengkap
* Menambahkan contoh penetapan kebijakan di tingkat langganan

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki parameter kesalahan ketik `VirtualNetworkRule` di **Set-AzServiceBusNetworkRuleSet** Fix untuk masalah #9658 : Typo
* Memperbaiki masalah pembuatan `Listen`aturan -only ([#9786](https://github.com/azure/azure-powershell/issues/9786))
* Menambahkan perintah baru **Test-AzServiceBusNameAvailability** untuk memeriksa ketersediaan nama untuk antrean dan topik

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki NullReferenceException ketika grup sumber daya memiliki VMSS yang tidak terkait dengan kluster service fabric ([#8681](https://github.com/Azure/azure-powershell/issues/8681))
* Memperbaiki bug di mana cmdlet gagal jika virtualNetwork berada dalam grup sumber daya yang berbeda dari kluster ([#8407](https://github.com/Azure/azure-powershell/issues/8407))
* Cmdlet **Add-AzServiceFabricApplicationCertificate** yang tidak digunakan lagi

#### <a name="azsql"></a>Az.Sql
* Dokumentasi yang diperbarui untuk cmdlet Audit lama

#### <a name="azstorage"></a>Az.Storage
* Bantuan yang diperbarui untuk **Close-AzStorageFileHandle** dan **Get-AzStorageFileHandle**, menambahkan lebih banyak skenario ke contoh cmdlet dan deskripsi parameter yang diperbarui
* Menambahkan dukungan untuk `StandardBlobTier` dalam unggahan dan salinan blob
* Menambahkan dukungan untuk `Rehydrate` prioritas dalam salinan blob

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan klarifikasi sekeliling `-AppSettings` parameter untuk **Set-AzWebApp** dan **Set-AzWebAppSlot**

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
* Memperbarui versi SDK .Net ADF ke 4.1.0
* Memperbaiki kesalahan ketik dalam dokumentasi untuk 'Get-AzDataFactoryV2PipelineRun'

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru yang ditambahkan untuk menghasilkan token SAS: New-AzEventHubAuthorizationRuleSASToken
* Menambahkan pesan verifikasi dan kesalahan untuk authorizationrules benar hanya jika 'Kelola' yang ditetapkan

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk menentukan Kebijakan KeySize for Certificate

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki Get-AzIntegrationAccountMap untuk mencantumkan semua jenis peta
  - Menambahkan parameter MapType baru untuk pemfilteran

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan dukungan untuk api versi 01-06-2019 (GA)

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
        - Menambahkan parameter opsional -PrivateEndpointNetworkPoliciesFlag untuk menunjukkan bahwa mengaktifkan atau menonaktifkan penerapan kebijakan jaringan pada titik akhir pivate di subnet ini.
        - Menambahkan parameter opsional -PrivateLinkServiceNetworkPoliciesFlag untuk menunjukkan bahwa mengaktifkan atau menonaktifkan penerapan kebijakan jaringan pada layanan tautan privat di subnet ini.
* Parameter cmdlet AzPrivateLinkService 'ServiceName' diganti namanya menjadi 'Name' dengan alias 'ServiceName' untuk kompatibilitas mundur
* Mengaktifkan protokol ICMP untuk konfigurasi aturan keamanan jaringan
    - Memperbarui cmdlet
        - Tambahkan-AzNetworkSecurityRuleConfig
        - New-AzNetworkSecurityRuleConfig
        - Set-AzNetworkSecurityRuleConfig
* Menambahkan ConnectionProtocolType (Ikev1/Ikev2) sebagai parameter yang dapat dikonfigurasi untuk New-AzVirtualNetworkGatewayConnection
* Menambahkan PrivateIpAddressVersion di LoadBalancerFrontendIpConfiguration
    - Cmdlet yang diperbarui:
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
* Menambahkan pesan verifikasi dan kesalahan untuk authorizationrules benar hanya jika 'Kelola' yang ditetapkan

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
* Rilis GA `Az.Advisor`
* Modul ini sekarang disertakan sebagai bagian dari modul `Az` roll-up

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8671
    - **Get-AzApiManagementSubscription**
        - Menambahkan dukungan untuk mengkueri langganan oleh Pengguna dan Produk
        - Menambahkan dukungan untuk kueri menggunakan Cakupan '/', '/apis', '/apis/echo-api'
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/9307 dan https://github.com/Azure/azure-powershell/issues/8432
    - **Import-AzApiManagementApi**
        - Menambahkan dukungan untuk menspesifikasikan 'ApiVersion' dan 'ApiVersionSetId' saat mengimpor Api

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug cmdlet Set-AzAutomationConnectionFieldValue untuk menangani nilai string.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HyperVGeneration ke New-AzImageConfig

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui output dari aktivitas mendapatkan berjalan, mendapatkan pipa berjalan, dan mendapatkan pemicu menjalankan cmdlet ADF untuk mendukung pipa Select-Object.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbaiki kesalahan ketik dalam dokumentasi 'New-AzEventGridSubscription'

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk meregenerasi kunci kebijakan otorisasi.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan 'RoutingPreference' ke tag ip publik
* Meningkatkan contoh untuk dokumentasi referensi 'Get-AzNetworkServiceTag'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi null di Get-AzPolicyState
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/9446

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbaiki model sumber data CustomLog yang ditampilkan dalam Get-AzOperationalInsightsDataSource

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki perintah get-policy untuk IaaSVMs

#### <a name="azresources"></a>Az.Resources
   - Memperbaiki teks bantuan untuk `Get-AzPolicyState -Top` parameter
   - Menambahkan dukungan halaman sisi klien untuk `Get-AzPolicyAlias`
   - Tambahkan parameter baru untuk `Set-AzPolicyAssignment`, `-PolicyParameters` dan `-PolicyParametersObject`
   - Beberapa dokumen dan contoh pembaruan untuk cmdlet Kebijakan

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaikan untuk masalah #4938 - New-AzServiceBusQueue mengembalikan BadRequest saat mengatur MaxSizeInMegabytes

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet Grup Failover Instans dari rilis pratinjau ke rilis publik
* Mendukung Audit Database/Azure SQL Server dengan cmdlet baru.
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
* Mendukung pembuatan atau pembaruan Akun penyimpanan dengan Autentikasi DS AAD Azure Files
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
* Memperbarui penggunaan versi API 01-06-2019.
* Cmdlet baru:
    - New-AzEventGridDomain
        - Membuat Domain Azure Event Grid baru.
    - Get-AzEventGridDomain
        - Mendapatkan detail Domain Event Grid, atau mendapatkan daftar semua Domain Event Grid dalam langganan Azure saat ini.
    - Remove-AzEventGridDomain
        - Menghapus Domain Azure Event Grid.
    - New-AzEventGridDomainKey
        - Meregenerasi kunci akses bersama untuk Domain Azure Event Grid.
    - Get-AzEventGridDomainKey
        - Mendapatkan kunci akses bersama yang digunakan untuk menerbitkan peristiwa ke Domain Event Grid.
    - New-AzEventGridDomainTopic:
        - Membuat Topik Domain Azure Event Grid baru.
    - Get-AzEventGridDomainTopic
        - Mendapatkan detail Topik Domain Event Grid, atau mendapatkan daftar semua Topik Domain Event Grid di bawah Domain Event Grid tertentu di Azure saat ini
    - Remove-AzEventGridDomainTopic:
        - Menghapus Topik Domain Azure Event Grid yang ada.
* Memperbarui cmdlet:
    - New-AzEventGridSubscription/Update-AzEventGridSubscription:
        - Menambahkan parameter wajib baru untuk mendukung penyaluran untuk Domain Event Grid baru dan Topik Domain Event Grid untuk memungkinkan pembuatan langganan peristiwa baru di bawah sumber daya ini.
        - Menambahkan parameter wajib baru untuk menentukan nama Domain Event Grid baru dan/atau nama Topik Domain Event Grid untuk memungkinkan pembuatan langganan peristiwa baru di bawah sumber daya ini.
        - Menambahkan set Parameter baru untuk domain dan topik domain untuk memungkinkan penggunaan kembali parameter yang ada (misalnya, EndPointType, SubjectBeginsWith, dll).
        - Menambahkan parameter opsional baru untuk menentukan:
            - Masa kedaluwarsa langganan peristiwa,
            - Parameter pemfilteran tingkat lanjut.
        - Menambahkan enum baru untuk servicebusqueue sebagai tujuan.
        - Melarang penggunaan 'Semua' dalam opsi -IncludedEventType dan menggantinya dengan
    - Get-AzEventGridTopic, Get-AzEventGridDomain, Get-AzEventGridDomainTopic, Get-AzEventGridSubscription:
        - Menambahkan parameter opsional baru (Top, ODataQuery dan NextLink) untuk mendukung hasil penomoran dan penyaringan.
    - Remove-AzEventGridSubscription
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
        - Tidak menggunakan lagi parameter -PublicIpName dan -VirtualNetworkName
* Memperbarui perintah fitur di bawah ini: Atur opsi autentikasi AAD VpnClient ke sumber daya gateway virtual.
    - Memperbarui New-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi autentikasi AAD VpnClient di Gateway.
    - Memperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi autentikasi AAD VpnClient di Gateway.
    - Memperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter sakelar opsional RemoveAadAuthentication untuk menghapus opsi autentikasi AAD VpnClient dari Gateway.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Aktifkan tingkat harga **pergb2018** di perintah 'New-AzOperationalInsightsWorkspace'

#### <a name="azresources"></a>Az.Resources
* Mendukung opsi Ekspor Templat tambahan
    - Menambahkan parameter '-SkipResourceNameParameterization' ke Export-AzResourceGroup
    - Menambahkan parameter '-SkipAllParameterization' ke Export-AzResourceGroup
    - Menambahkan parameter '-Resource' ke Export-AzResourceGroup untuk pemfilteran sumber daya yang diekspor

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Perbaiki tambahkan sertifikat ByExistingKeyVault mendapatkan cap jempol yang salah dalam beberapa kasus

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
* Mendukung Jenis FileStorage dan Premium_ZRS SkuName saat membuat Akun penyimpanan
    - New-AzStorageAccount
* Mengklarifikasi deskripsi tentang cmdlet kekebalan blob
    -  Remove-AzRmStorageContainerImmutabilityPolicy

#### <a name="azwebsites"></a>Az.Websites
* Mengoptimalkan Get-AzWebAppCertificate untuk memfilter berdasarkan grup sumber daya di server, bukan klien
* Menambahkan parameter pengalihan -UseDisasterRecovery ke Get-AzWebAppSnapshot

## <a name="220---june-2019"></a>2.2.0 - Juni 2019
#### <a name="azcdn"></a>Az.Cdn
* Memperbarui cmdlet untuk mendukung fitur rulesEngine berdasarkan API versi 15-04-2019.

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
* Tidak menggunakan lagi cmdlet Get-AzSqlDatabaseSecureConnectionPolicy
* Mengganti nama cmdlet Deteksi Ancaman menjadi Perlindungan Ancaman Tingkat Lanjut
* Parameter New-AzSqlInstance -StorageSizeInGB dan -LicenseType sekarang bersifat opsional.

#### <a name="azwebsites"></a>Az.Websites
* memperbaiki masalah saat menggunakan Set-AzWebApp dan Set-AzWebAppSlot dengan properti -WebApp telah menghapus tag

## <a name="210---may-2019"></a>2.1.0 - Mei 2019
#### <a name="azapimanagement"></a>Az.ApiManagement
* Membuat Cmdlet baru untuk mengelola diagnostik di Cakupan global dan API
    - **Get-AzApiManagementDiagnostic** - Mendapatkan diagnostik yang dikonfigurasi Cakupan global atau api
    - **New-AzApiManagementDiagnostic** - Membuat diagnostik baru di cakupan global atau Cakupan api
    - **New-AzApiManagementHttpMessageDiagnostic** - Membuat pengaturan diagnostik tempat Header untuk log dan ukuran Byte Body
    - **New-AzApiManagementPipelineDiagnosticSetting** - Membuat pengaturan Diagnostik untuk pesan HTTP masuk/keluar ke Gateway.
    - **New-AzApiManagementSamplingSetting** - Membuat Pengaturan Pengambilan Sampel untuk permintaan/respons untuk diagnostik
    - **Remove-AzApiManagementDiagnostic** - Menghapus entitas diagnostik di cakupan global atau api
    - **Set-AzApiManagementDiagnostic** - Memperbarui Entitas diagnostik di cakupan global atau api
* Membuat Cmdlet baru untuk mengelola Cache di layanan ApiManagement
    - **Get-AzApiManagementCache** - Mendapatkan detail Cache yang ditentukan oleh pengidentifikasi atau semua cache
    - **New-AzApiManagementCache** - Membuat Cache atau Cache 'default' baru di 'wilayah' azure tertentu
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
     - `PS D:\github\azure-powershell> Set-AzApiManagementPolicy -Context  -PolicyFilePath C:\wrongpolicy.xml -ApiId httpbin`
       - `Set-AzApiManagementPolicy :`
       - `Error Code: ValidationError`
       - `Error Message: One or more fields contain incorrect values:`
       - `Error Details: [Code=ValidationError, Message=Error in element 'log-to-eventhub' on line 3, column 10: Logger not found, Target=log-to-eventhub]`
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
    - Untuk mengganti 'ServiceUrl' saat mengkloning API.
* Memperbarui cmdlet **New-AzApiManagementIdentityProvider**
    - Untuk mengonfigurasi 'AAD' atau 'AADB2C' dengan 'Otoritas'
    - Untuk menyiapkan 'SignupPolicy', 'SigninPolicy', 'ProfileEditingPolicy' dan 'PasswordResetPolicy'
* Memperbarui cmdlet **New-AzApiManagementSubscription**
    - Untuk memperhitungkan SubscriptonModel baru menggunakan 'Scope' dan 'UserId'
    - Untuk memperhitungkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Menambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Memperbarui cmdlet **Set-AzApiManagementSubscription**
    - Untuk memperhitungkan SubscriptonModel baru menggunakan 'Scope' dan 'UserId'
    - Untuk memperhitungkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Menambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Memperbarui cmdlet berikut untuk menerima 'ResourceId' sebagai input
    - 'New-AzApiManagementContext'
      - `New-AzApiManagementContext -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso`
    - 'Get-AzApiManagementApiRelease'
      - `Get-AzApiManagementApiRelease -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso/apis/echo-api/releases/releaseId`
    - 'Get-AzApiManagementApiVersionSet'
      - `Get-AzApiManagementApiVersionSet -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/constoso/apiversionsets/pathversionset`
    - 'Get-AzApiManagementAuthorizationServer'
    - 'Get-AzApiManagementBackend'
      - `Get-AzApiManagementBackend -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso/backends/servicefabric`
    - 'Get-AzApiManagementCertificate'
    - 'Remove-AzApiManagementApiVersionSet'
    - 'Remove-AzApiManagementSubscription'

#### <a name="azautomation"></a>Az.Automation
* Memperbarui Get-AzAutomationJobOutputRecord untuk menangani nilai JSON dan catatan Teks.
    - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/7977
    - Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8600
* Mengubah perilaku bagi Start-AzAutomationDscCompilationJob untuk memulai pekerjaan bukan menunggu hingga selesai.
    * Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8347
* Memperbaiki Get-AzAutomationDscNode saat menggunakan -Name memunculkan semua node. Sekarang menampilkan node yang cocok saja.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter ProtectFromScaleIn dan ProtectFromScaleSetAction ke cmdlet Update-AzVmssVM.
* New-AzVM yang diatur sekarang menggunakan lokasi yang tersedia secara default jika 'US Timur' tidak didukung

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui sdk ADLS untuk menggunakan httpclient, mengintegrasikan pengujian dataplane dengan azure framework

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam contoh bantuan

#### <a name="aznetwork"></a>Az.Network
* Menambahkan bendera DisableBgpRoutePropagation ke output Tabel Rute yang Efektif
    - Cmdlet yang diperbarui:
        - Get-AzEffectiveRouteTable
* Memperbaiki tanda hubung ganda dalam dokumentasi New-AzApplicationGatewayTrustedRootCertificate

#### <a name="azresources"></a>Az.Resources
* Menambahkan Get-AzDenyAssignment cmdlet baru untuk mengambil penugasan penolakan

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
  - Parameter baru, ProximityPlacementGroupId, ditambahkan ke cmdlet berikut: New-AzAvailabilitySet New-AzVMConfig New-AzVmssConfig
* Parameter StorageAccountType ditambahkan ke New-AzGalleryImageVersion.
* TargetRegion of New-AzGalleryImageVersion dapat berisi StorageAccountType.
* Parameter sakelar SkipShutdown ditambahkan ke Stop-AzVM dan Stop-AzVmss
* Perubahan mencolok
    - Set-AzVMBootDiagnostics diubah menjadi Set-AzVMBootDiagnostic.
    - Export-AzLogAnalyticThrottledRequests diubah menjadi Export-AzLogAnalyticThrottledRequests.

#### <a name="azdeploymentmanager"></a>Az.DeploymentManager
* Rilis cmdlet Manajer Penyebaran Azure Pertama yang Tersedia Secara Umum

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
  - Informasi [lebih lanjut](/rest/api/monitor/scheduledqueryrules) tentang API SQR
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
* Perbaikan untuk rencana tindakan akhir rencana pemulihan Azure Site Recovery.
* Perbaikan untuk pemetaan jaringan Pembaruan Azure Site Recovery untuk Azure ke Azure.
* Perbaikan untuk arah perlindungan pembaruan Azure Site Recovery untuk Azure ke Azure untuk disk terkelola.
* Perbaikan kecil lainnya.

#### <a name="azrelay"></a>Az.Relay
* Memperbaiki kesalahan ketik dalam pesan yang menghadap pelanggan

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru untuk NetworkRuleSet dari Namespace

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan ke Storage Client Library 10.0.1 (namespace semua objek dari SDK ini berubah dari 'Microsoft.WindowsAzure.Storage. *' ke 'Microsoft.Azure.Storage.* ')
* Meningkatkan ke Microsoft.Azure.Management.Storage 11.0.0, untuk mendukung API baru versi 01-04-2019.
* Jenis Akun penyimpanan default di Buat Akun penyimpanan berubah dari 'Storage' menjadi 'StorageV2'
    - New-AzStorageAccount
* Mengubah output cmdlet Akun penyimpanan Sku.Name disejajarkan dengan input SkuName dengan menambahkan '-', seperti perubahan 'StandardLRS' menjadi 'Standard_LRS'
    - New-AzStorageAccount
    - Dapatkan-AkunPenyimpananAz
    - Set-AzStorageAccount

#### <a name="azwebsites"></a>Az.Websites
* Properti 'Kind' sekarang akan ditetapkan untuk objek PSSite yang ditampilkan oleh Get-AzWebApp
* Get-AzWebApp*Metrics dan Get-AzAppServicePlanMetrics ditandai tidak digunakan lagi

## <a name="180---april-2019"></a>1.8.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Uninstall-AzureRm untuk menghapus modul dengan benar di Mac

#### <a name="azbatch"></a>Az.Batch
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azcdn"></a>Az.Cdn
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah terkait instalasi AEM jika id sumber daya disk memiliki resourcegroups berhuruf kecil di id sumber daya
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan SsisProperties jika NodeCount tidak null untuk runtime integrasi terkelola.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui teks bantuan untuk titik akhir guna menunjukkan bahwa sumber daya harus dibuat sebelum menggunakan cmdlet langganan acara buat/perbarui.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru untuk NetworkRuleSet dari Namespace

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azmachinelearning"></a>Az.MachineLearning
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azmedia"></a>Az.Media
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azmonitor"></a>Az.Monitor
  * Cmdlet baru untuk aturan peringatan berbasis metrik GenV2 (non klasik)
      - New-AzMetricAlertRuleV2DimensionSelection
      - New-AzMetricAlertRuleV2Criteria
      - Remove-AzMetricAlertRuleV2
      - Get-AzMetricAlertRuleV2
      - Add-AzMetricAlertRuleV2
  * Memperbarui SDK Monitor ke versi 0.22.0-pratinjau

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="aznotificationhubs"></a>Az.NotificationHubs
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.
* Memperbarui format tabel untuk SQL di mesin virtual azure
* Menambahkan metode alternatif untuk mengambil lokasi di AzureFileShare
* Memperbarui ScheduleRunDays di objek SchedulePolicy berdasarkan zona waktu

#### <a name="azrediscache"></a>Az.RedisCache
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azsql"></a>Az.Sql
* Mengganti dependensi pada Monitor SDK dengan kode umum
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.
* Menyempurnakan proses dari klasifikasi beberapa kolom.
* Menyertakan properti sku (nama, keluarga, kapasitas sku) sebagai respons dari Get-AzSqlServerServiceObjective dan format sebagai tabel secara default.
* Kemampuan untuk Get-AzSqlServerServiceObjective berdasarkan lokasi tanpa memerlukan server yang sudah ada sebelumnya di wilayah tersebut.
* Dukungan untuk parameter zona waktu dalam pembuatan Instans Terkelola.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azwebsites"></a>Az.Websites
* memperbaiki Set-AzWebApp dan Set-AzWebAppSlot untuk tidak menghapus tag pada eksekusi
* Memperbarui cmdlet dengan kata benda jamak menjadi nama jamak tunggal, dan tidak digunakan lagi.
* Memperbarui SDK WebSites.
* Menghapus properti AdminSiteName dari PSAppServicePlan.

## <a name="170---april-2019"></a>1.7.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAnalysisServicesEndpointResourceId

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Menggunakan ServiceClient dalam cmdlet dataplane dan menghapus logika autentikasi asli
* Membuat Add-AzureASAccount pembungkus Connect-AzAccount guna menghindari perubahan yang berisiko

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug cmdlet New-AzAutomationSoftwareUpdateConfiguration untuk Inklusi. Sekarang parameter IncludedKbNumber dan IncludedPackageNameMask akan berfungsi.
* Perbaikan bug untuk grup dinamis manajemen pembaruan otomatisasi azure

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HyperVGeneration ke New-AzDiskConfig dan New-AzSnapshotConfig
* Memungkinkan pembuatan mesin virtual dengan gambar galeri dari penyewa lain.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbaiki masalah dalam parameter -Command New-AzContainerGroup yang menambahkan argumen kosong di belakang

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 3.0.2
* Memperbarui cmdlet Set-AzDataFactoryV2 dengan parameter tambahan untuk pengaturan terkait RepoConfiguration.

#### <a name="azresources"></a>Az.Resources
* Meningkatkan penanganan penyedia untuk parameter 'Get-AzResource' saat menyediakan parameter '-ResourceId' atau '-ResourceGroupName', '-Name', dan '-ResourceType'
* Meningkatkan penanganan kesalahan untuk 'Test-AzDeployment' dan 'Test-AzResourceGroupDeployment'
    - Menangani kesalahan yang dilemparkan di luar validasi penyebaran dan memasukkannya ke dalam output perintah sebagai gantinya
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/6856
* Menambahkan parameter pengalihan '-IgnoreDynamicParameters' ke set cmdlet penyebaran untuk melewati prompt dalam skenario skrip dan pekerjaan
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/6856

#### <a name="azsql"></a>Az.Sql
* Mendukung Klasifikasi Data Database.

#### <a name="azstorage"></a>Az.Storage
* Melaporkan kesalahan detail saat konteks membuat Penyimpanan dengan parameter -UseConnectedAccount, tetapi tanpa proses masuk akun Azure
    - New-AzStorageContext
* Mendukung Pengelolaan Properti Layanan Blob dari Akun penyimpanan tertentu dengan API bidang Manajemen
    - Update-AzStorageBlobServiceProperty
    - Get-AzStorageBlobServiceProperty
    - Enable-AzStorageBlobDeleteRetentionPolicy
    - Disable-AzStorageBlobDeleteRetentionPolicy
* Dukungan -AsJob untuk Blob dan pengunggahan file serta pengunduhan cmdlet
    - Get-AzStorageBlobContent
    - Set-AzStorageBlobContent
    - Get-AzStorageFileContent
    - Set-AzStorageFileContent

## <a name="160---march-2019"></a>1.6.0 - Maret 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

#### <a name="azautomation"></a>Az.Automation
* Manajemen pembaruan otomatisasi Azure berubah untuk mendukung fitur baru berikut:
    * Pengelompokan dinamis
    * Skrip pra-posting
    * Pengaturan penghidupan ulang

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah terkait resolusi jalur di Get-AzVmBootDiagnosticsData
* Memperbarui pustaka klien Komputasi ke 25.0.0.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan kartubebas ke cmdlet KeyVault

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan Inteligensi Ancaman untuk Azure Firewall
* Menambahkan sumber daya tingkat atas Kebijakan Firewall Application Gateway dan Aturan Kustom
* Menambahkan jenis tindakan Pemberitahuan untuk Kumpulan Aturan Jaringan dan Aplikasi Azure Firewall
* Menambahkan dukungan untuk kondisi di RewriteRules di Application Gateway
    - Cmdlet baru yang ditambahkan:
        - New-AzApplicationGatewayRewriteRuleCondition
    - Cmdlet diperbarui dengan parameter opsional - RuleSequence dan Kondisi
        - New-AzApplicationGatewayRewriteRule

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan SnapshotRetentionInDays dalam kebijakan mesin virtual Azure untuk mendukung RP Instan
* Menambahkan dukungan pipa untuk kontainer yang tidak terdaftar

#### <a name="azresources"></a>Az.Resources
* Memperbarui dukungan kartubebas untuk Get-AzResource dan Get-AzResourceGroup
* Memperbarui info masuk yang digunakan saat melakukan panggilan umum ke ARM

#### <a name="azsql"></a>Az.Sql
* mengubah param cmdlet Deteksi Ancaman (ExcludeDetectionType) dari DetectionType ke string[] untuk menjadikannya bukti masa depan ketika DetectionTypes baru ditambahkan dan untuk mendukung pelengkapan otomatis juga.
* Menambahkan cmdlet Penilaian Kerentanan di Server dan Instans Terkelola

#### <a name="azstorage"></a>Az.Storage
* Mendukung untuk Mendapatkan/Mengatur/Menghapus Kebijakan Manajemen pada Akun penyimpanan
    - Atur-AzStorageAccountManagementPolicy
    - Get-AzStorageAccountManagementPolicy
    - Hapus-AzStorageAccountManagementPolicy
    - Tambahkan-AzstorageAccountManagementPolicyaction
    - Baru-AzStorageAccountManagementPolicyFilter
    - Baru-AzStorageAccountManagementPolicyRule

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug templat ARM yang merusak kloning semua slot menggunakan 'New-AzWebApp -IncludeSourceWebAppSlots'

## <a name="150---march-2019"></a>1.5.0 - Maret 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan perintah 'Register-AzModule' untuk mendukung cmdlet yang dihasilkan AutoRest
* Memperbarui contoh untuk Connect-AzAccount

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah saat menerima jadwal bulanan tertentu di beberapa cmdlet Azure Automation
* Memperbaiki Get-AzAutomationDscNode yang menampilkan hanya 20 node teratas. Sekarang ia menampilkan semua node

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet Powershell baru untuk Mengaktifkan/Menonaktifkan Https Domain Kustom dan tidak menggunakan lagi yang lama

#### <a name="azcompute"></a>Az.Compute
* Menambahkan dukungan kartubebas ke cmdlet Dapatkan

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 3.0.1

#### <a name="azlogicapp"></a>Az.LogicApp
* Perbaikan untuk ListWorkflows yang hanya mengambil halaman pertama hasil

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan kartubebas ke cmdlet Jaringan

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
* Mendukung Jenis BlockBlobStorage saat membuat Akun penyimpanan - New-AzStorageAccount

## <a name="140---february-2019"></a>1.4.0 - Februari 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Tidak menggunakan lagi cmdlet AddAzureASAccount

#### <a name="azautomation"></a>Az.Automation
* Memperbarui bantuan untuk Import-AzAutomationDscNodeConfiguration
* Menambahkan validasi nama konfigurasi ke cmdlet Import-AzAutomationDscConfiguration
* Meningkatkan penanganan kesalahan untuk cmdlet Import-AzAutomationDscConfiguration

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan CustomSubdomainName sebagai parameter opsional baru untuk New-AzCognitiveServicesAccount yang digunakan untuk menentukan subdomain untuk sumber daya.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah terkait set parameter ID
* Memperbarui Get-AzVMExtension untuk mencantumkan semua ekstensi yang diinstal jika parameter Name tidak disediakan
* Menambahkan parameter Tag dan ResourceId ke cmdlet Update-AzImage
* Get-AzVmssVM tanpa ID instans dan dengan InstanceView dapat mencantumkan mesin virtual VMSS dengan tampilan instans.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan cmdlet untuk pencacahan dan pemulihan item yang dihapus ADL

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan properti boolean baru SkipEmptyArchives untuk Melewatkan Arsip Kosong di kelas CaptureDescription Eventhub

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki penandaan di Set-AzKeyVaultSecret

#### <a name="azlogicapp"></a>Az.LogicApp
* Menambahkan sku Dasar untuk Akun Integrasi
* Menambahkan XSLT 2.0, XSLT 3.0, dan Jenis Peta Cair
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
* Memperbaru SDK Logic App ke versi 4.1.0

#### <a name="azmonitor"></a>Az.Monitor
* Memperbarui bantuan untuk Get-AzMetric

#### <a name="aznetwork"></a>Az.Network
* Memperbarui contoh bantuan untuk Add-AzApplicationGatewayCustomError

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Dukungan tambahan untuk Baru dan Dapatkan sumber data ApplicationInsights.
    - Menambahkan jenis 'ApplicationInsights' baru untuk mendukung Dapatkan spesifik dan Dapatkan semua sumber data ApplicationInsights untuk ruang kerja tertentu.
    - Menambahkan cmdlet New-AzOperationalInsightsApplicationInsightsDataSource untuk membuat sumber data dengan parameter sumber daya yang diberikan Application-Insights: Id berlangganan, resourceGroupName, dan nama.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8166
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/8235
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6219
* Memperbaiki bug yang mencegah pembuatan KeyCredentials berulang

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk tingkat Hyperscale DB SQL
* Memperbaiki bug di mana pemulihan bisa gagal karena pengaturan properti yang tidak perlu dalam permintaan pemulihan

#### <a name="azwebsites"></a>Az.Websites
* Contoh yang benar dalam Get-AzWebAppSlotMetrics

## <a name="130---february-2019"></a>1.3.0 - Februari 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation

#### <a name="azaccounts"></a>Az.Accounts
* Perbarui ke versi terbaru ClientRuntime

#### <a name="azanalysisservices"></a>Az.AnalysisServices
Ketersediaan umum untuk modul Az.AnalysisServices.

#### <a name="azcompute"></a>Az.Compute
* Ekstensi AEM: Menambahkan dukungan untuk disk UltraSSD dan P60, P70, dan P80
* Memperbarui deskripsi bantuan untuk Set-AzVMBootDiagnostics
* Memperbarui deskripsi dan contoh bantuan untuk Update-AzImage

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
Ketersediaan umum untuk modul Az.RecoveryServices.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki penandaan untuk grup sumber daya
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8166
* Memperbaiki masalah di mana `Get-AzRoleAssignment` tidak menghormati -ErrorAction
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8235

#### <a name="azsql"></a>Az.Sql
* Menambahkan Get/Set AzSqlDatabaseBackupShortTermRetentionPolicy
* Memperbaiki masalah saat tidak masuk ke akun Azure akan menghasilkan pengecualian nullref saat menjalankan cmdlet SQL
* Memperbaiki pengecualian ref null di Get-AzSqlCapability

## <a name="121---january-2019"></a>1.2.1 - Januari 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation

#### <a name="azaccounts"></a>Az.Accounts
* Rilis dengan versi Autentikasi yang benar

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Rilis dengan dependensi Autentikasi yang diperbarui

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Rilis dengan dependensi Autentikasi yang diperbarui


## <a name="120---january-2019"></a>1.2.0 - Januari 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan autentikasi nama pengguna/kata sandi dan interaktif hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation

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
* Memperbaiki permasalahan titik akhir ADLS saat menggunakan MSI
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
* Memperbaiki masalah di mana jalur untuk parameter '-TemplateFile' tidak diselesaikan sebelum menjalankan cmdlet penyebaran grup sumber daya
* Az.Resources: Dokumentasi yang benar untuk nilai default New-AzPolicyDefinition -Mode
* Az.Resources: Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/7522
* Az.Resources: Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/5747
* Memperbaiki masalah pemformatan dengan objek 'PSResourceGroupDeployment'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/2123

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Rollback ketika sertifikat ditambahkan ke model VMSS tetapi pengecualian dilemparkan ini adalah untuk memperbaiki bug: https://github.com/Azure/service-fabric-issues/issues/932
* Memperbaiki beberapa pesan kesalahan.
* Memperbaiki pembuatan kluster dengan templat ARM default untuk New-AzServiceFabriCluster yang tidak berfungsi dengan migrasi ke Az.
* Memperbaiki penambahan sertifikat kluster/aplikasi untuk hanya ditambahkan ke VM Scale Sets yang sesuai dengan kluster dengan memeriksa id kluster di ekstensi.

#### <a name="azsignalr"></a>Az.SignalR
* Memperbarui URL bantuan online yang salah

#### <a name="azsql"></a>Az.Sql
* Memperbarui URL bantuan online yang salah
* Memperbarui deskripsi parameter untuk parameter LicenseType dengan nilai yang mungkin
* Memperbaiki pembaruan identitas instans terkelola yang tidak berfungsi saat itu adalah satu-satunya properti yang diperbarui
* Dukungan untuk kolektasi kustom pada instans terkelola

#### <a name="azstorage"></a>Az.Storage
* Memperbarui URL bantuan online yang salah
* Memberikan pesan kesalahan detail saat mendapatkan/mengatur Pengelogan/Metrik klasik di Akun Premium Storage, karena Akun Premium Storage tidak mendukung Pengelogan/Metrik klasik.
    - Get/Set-AzStorageServiceLoggingProperty
    - Get/Set-AzStorageServiceMetricsProperty

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Memperbarui URL bantuan online yang salah

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui URL bantuan online yang salah
* Memperbaiki 'New-AzWebAppSSLBinding' untuk mengunggah sertifikat ke resourcegroup+location yang benar jika aplikasi dihosting di ASE.
* Memperbaiki 'New-AzWebAppSSLBinding' untuk tidak menimpa tag saat mengikat sertifikat SSL ke aplikasi

## <a name="110---january-2019"></a>1.1.0 - Januari 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Cakupan 'Lokal' ke Enable-AzureRmAlias

#### <a name="azcompute"></a>Az.Compute
* Nama sekarang opsional dalam parameter ID yang ditetapkan untuk Restart/Start/Stop/Remove/Set-AzVM dan Save-AzVMImage
* Memperbarui deskripsi ID dalam file bantuan
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui versi sdk dataplane ke 1.1.14 untuk perbaikan SDK.
    - Memperbaiki penanganan acesstime negatif dan waktu modifikasi untuk getfilestatus dan liststatus, Memperbaiki token pembatalan asinkron

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui penggunaan versi API 01-01-2019.
* Memperbarui cmdlet berikut untuk mendukung skenario baru dalam versi API 01-01-2019
    - New-AzEventGridSubscription: Tambahkan parameter opsional baru untuk menentukan:
        - Waktu Aktif Kejadian,
        - Jumlah maksimum upaya pengiriman untuk kejadian tersebut,
        - Titik akhir pengiriman yang gagal.
    - Update-AzEventGridSubscription: Tambahkan parameter opsional baru untuk menentukan:
        - Waktu Aktif Kejadian,
        - Jumlah maksimum upaya pengiriman untuk kejadian tersebut,
        - Titik akhir pengiriman yang gagal.
* Tambahkan nilai enum baru (yaitu, storageQueue dan hybridConnection) untuk opsi EndpointType di cmdlet New-AzEventGridSubscription dan Update-AzEventGridSubscription.
* Menampilkan pesan peringatan jika membuat atau memperbarui langganan acara diharapkan memerlukan tindakan manual dari pengguna.

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui SDK IotHub ke versi terbaru

#### <a name="azlogicapp"></a>Az.LogicApp
* Get-AzLogicApp mencantumkan semua tanpa Nama yang ditentukan

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah set parameter saat menyediakan parameter '-ODataQuery' dan '-ResourceId' untuk 'Get-AzResource'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/7875
* Memperbaiki penanganan parameter -Custom di New/Set-AzPolicyDefinition
* Memperbaiki kesalahan ketik dalam dokumentasi New-AzDeployment
* Membuat parameter '-MailNickname' wajib untuk 'New-AzADUser'
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8220

#### <a name="azsignalr"></a>Az.SignalR
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

#### <a name="azsql"></a>Az.Sql
* Mengonversi Ketergantungan klien manajemen penyimpanan ke implementasi SDK umum.

#### <a name="azstorage"></a>Az.Storage
* Mengatur StorageAccountName dari konteks Penyimpanan sebagai Nama Akun Penyimpanan yang sebenarnya, saat dibuat dengan Token Sas, OAuth, atau Anonymous
    - New-AzStorageContext
* Membuat Token Sas Objek Snapshot Blob dengan parameter '-FullUri', memperbaiki Uri yang ditampilkan menjadi Uri snapshot
    - New-AzStorageBlobSASToken

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug penguraian tanggal di 'Get-AzDeletedWebApp'
* Memperbaiki masalah kompatibilitas mundur dengan modul Az.Accounts

## <a name="version-100---december-2018"></a>Versi 1.0.0 - Desember 2018
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum dari modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
