---
title: Azure PowerShell rilis
description: Pelajari tentang semua pembaruan terkini untuk Azure PowerShell baru.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 12/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 5421eb05a8e58c17505ee1bddf7eaeabe3089b58
ms.sourcegitcommit: 2b90f2e68e4992e43f16a51f69e5581db189440b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/26/2022
ms.locfileid: "137778640"
---
# <a name="azure-powershell-release-notes"></a>Azure PowerShell rilis
## <a name="700---december-2021"></a>7.0.0 - Desember 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menghapus 'ServicePrincipalSecret' dan 'CertificatePassword' di 'PSAzureRmAccount' [#15427]
* Menambahkan parameter opsional 'MicrosoftGraphAccessToken' ke 'Koneksi-AzAccount'
* Menambahkan parameter opsional 'MicrosoftGraphEndpointResourceId', 'MicrosoftGraphUrl' ke 'Add-AzEnvironment' dan 'Set-AzEnvironment'
* Menambahkan properti '-AccountId' ke 'UserWithSubscriptionId' kumpulan parameter 'Koneksi-AzAccount' yang memungkinkan nama pengguna untuk dipilih sebelumnya untuk masuk interaktif
* Menambahkan '-Uri' dan '-ResourceId' ke 'Invoke-AzMethod'
* Menambahkan Lingkungan lengkapi otomatis ke cmdlet berikut: Koneksi-AzAccount, Get-AzEnvironment, Set-AzEnvironment, Remove-AzEnvironment [#15991]
* Menambahkan nama dan versi modul ke User-Agent string [#16291]

#### <a name="azadvisor"></a>Az.Advisor
* Memperbaiki masalah ketika 'Az.Advisor.psd1' tidak ditandatangani [#16226]

#### <a name="azaks"></a>Az.Aks
* [Breaking Change] Alias parameter dan tipe output yang diperbarui dari 'Get-AzAksVersion'
* Menambahkan 'Invoke-AzAksRunCommand' untuk mendukung menjalankan perintah shell (dengan kubectl, helm) di kluster tinta. [#16104]
* Menambahkan dukungan 'EnableNodePublicIp' dan 'NodePublicIPPrefixID' untuk 'New-AzAksCluster' dan 'New-AzAksNodePool'. [#15656]
* Melakukan migrasi logika pembuatan prinsipal layanan dalam 'New-AzAksCluster' dari 'Azure Active Directory Graph' ke 'Microsoft Graph'.
* Memperbaiki masalah yang menyebabkan 'Set-AzAksCluster' tidak dapat memutakhirkan kluster ketika versi node pool tidak sesuai dengan versi kluster. [#14583]
* Ditambahkan 'ResourceGroupName' dalam 'PSKgroupsCluster'. [#15802]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan fungsi WebTest. Di bawah ini adalah cmdlet baru
    * 'Get-AzApplicationInsightsWebTest'
    * 'New-AzApplicationInsightsWebTest'
    * 'New-AzApplicationInsightsWebTestGeolocationObject'
    * 'New-AzApplicationInsightsWebTestHeaderFieldObject'
    * 'Remove-AzApplicationInsightsWebTest'
    * 'Update-AzApplicationInsightsWebTestTag'

#### <a name="azautomation"></a>Az.Automation
* Contoh tetap dalam dokumen referensi untuk 'Remove-AzAutomationHybridWorkerGroup'

#### <a name="azcloudservice"></a>Az.CloudService
* Ketersediaan umum modul 'Az.CloudService'

#### <a name="azcompute"></a>Az.Compute
* Berisi pembaruan untuk cmdlet powershell berikut
    - 'SetAzVmssDiskEncryptionExtension' : Menambahkan parameter ekstensi untuk cmdlet agar berfungsi dengan ekstensi uji dan parameter 'EncryptFormatAll' untuk Kumpulan Skala Komputer Virtual
    - 'GetAzVmssVMDiskEncryptionStatus': Mengubah fungsionalitas cmdlet untuk menampilkan status enkripsi disk data kumpulan Skala Komputer Virtual dengan benar
    - 'SetAzDiskEncryptionExtension' : Memperbaiki bug dalam cmdlet dalam skenario migrasi dari 2pass ke enkripsi 1pass
* Menambahkan 'Add-AzVhd' untuk mengonversi VHD menggunakan Hyper-V
* Menambahkan parameter 'UserData' pada cmdlet VM dan VMSS
* Menambahkan parameter string 'PublicNetworkAccess' ke diskConfig dan cmdlet SnapshotConfig
* Menambahkan parameter boolean 'AcceleratedNetwork' ke cmdlet DiskConfig dan SnapshotConfig
* Menambahkan properti 'CompletionPercent' ke model PSSnapshot sehingga terlihat bagi pengguna.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Meningkatkan versi API ke 2021-09-01
  - [Breaking Change] Mengubah tipe parameter 'LogAnalyticWorkspaceResourceId' di 'New-AzContainerGroup' dari Hashtable menjadi String
  - [Breaking Change] Parameter yang dihapus 'NetworkProfileId' di 'New-AzContainerGroup', menambahkan 'SubnetId' sebagai alternatifnya
  - [Breaking Change] Parameter yang dihapus 'ReadinessProbeHttpGetHttpHeadersName' dan 'ReadinessProbeHttpGetHttpHeadersValue' di 'New-AzContainerInstanceObject', ditambahkan 'ReadinessProbeHttpGetHttpHeader' sebagai alternatifnya
  - [Breaking Change] Parameter yang dihapus 'LivenessProbeHttpGetHttpHeadersName' dan 'LivenessProbeHttpGetHttpHeadersValue' di 'New-AzContainerInstanceObject', menambahkan 'LivenessProbeHttpGetHttpHeader' sebagai alternatifnya
  - Ditambahkan 'Zone' di 'New-AzContainerGroup', 'AcrIdentity' di 'New-AzContainerGroupImageRegistryCredentialObject'
  - Ubah 'Nama pengguna' di 'New-AzContainerGroupImageRegistryCredentialObject' dari wajib menjadi opsional
* Untuk 'Invoke-AzContainerInstanceCommand'
    - [Breaking Change] Hasil eksekusi perintah yang ditampilkan sebagai output cmdlet dengan menyambungkan websocket dalam backend [#15754]
    - Menambahkan '-PassThru' untuk mendapatkan hasil eksekusi terakhir saat perintah berhasil
    - Mengubah 'TerminalSizeCol' dan 'TerminalSizeRow' dari wajib ke opsional, mengatur nilai defaultnya menurut ukuran jendela PowerShell saat ini
* Ditambahkan 'Restart-AzContainerGroup', 'Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint' dan 'New-AzContainerInstanceHttpHeaderObject'

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Diperbaiki ketika peringatan tentang nilai AnalyticalStorageSchemaType ditampilkan saat tidak ada nilai yang diberikan.
* Dukungan yang ditambahkan untuk Properti terkelola.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 4.28.0

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah yang 'New-AzEventHubKey' selalu menghasilkan kunci primer baru dan bukan kunci sekunder sejak versi 1.9.0 [#16362]

#### <a name="azfunctions"></a>Az.Functions
* [Perubahan pecah] 'Update-AzFunctionAppPlan' meminta konfirmasi [#16490]
* [Perubahan pecah] 'Remove-AzFunctionApp' tidak menghapus ASP jika aplikasi tersebut adalah aplikasi terakhir dalam paket [#16487]
* [Perubahan pecah] Atur 'FunctionsVersion' ke 4 untuk pembuatan FunctionApp [#16426]
* [Perubahan pecah] 'Update-AzFunctionApp' meminta konfirmasi [#14442]
* Memperbaiki kesalahan saat membuat fungsi dengan 'New-AzFunctionApp' di PowerShell 5.1 [#15430]
* SKU 'Standard_GZRS' akun penyimpanan yang didukung [#14633]

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan dua parameter '-Zona' dan '-PrivateLinkConfiguration' ke cmdlet 'New-AzHDInsightCluster'
  - Parameter yang ditambahkan 'Zona-' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung pembuatan kluster dengan fitur zona ketersediaan
  - Menambahkan parameter '-PrivateLinkConfiguration' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung penambahan konfigurasi tautan pribadi saat membuat kluster dengan fitur tautan privat.
* Menambahkan cmdlet New-AzHDInsightIPConfiguration untuk membuat objek konfigurasi ip dalam memori.
* Cmdlet New-AzHDInsightPrivateLinkConfiguration untuk membuat objek konfigurasi tautan pribadi di memori.
* Perbaikan tipe output dalam dokumen cmdlet Set-AzHDInsightClusterDiskEncryptionKey bantuan dari 'Microsoft.Azure.Management.HDInsight.Models.Cluster' hingga 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster' agar tetap konsisten dengan tipe asli objek yang dikembalikan.
* Mengubah pengaturan:
  - Mengubah tipe parameter 'OSType' dari 'Microsoft.Azure.Management.HDInsight.Models.OSType' menjadi 'System.string' di cmdlet 'New-AzHDInsightCluster'.
  - Mengubah tipe parameter 'ClusterTier' dari 'Microsoft.Azure.Management.HDInsight.Models.ClusterTier' menjadi 'System.string' di cmdlet 'New-AzHDInsightCluster' dan 'New-AzHDInsightClusterConfig'.
  - Mengubah tipe properti 'VmSizes' di kelas 'AzureHDInsightCapabilities' `IDictionary<string, AzureHDInsightVmSizesCapability>` dari ke `IList<string>` .
  - Mengubah tipe properti 'AssignedIdentity' di kelas 'AzureHDInsightCluster' dari 'Microsoft.Azure.Management.HDInsight.Models.ClusterIdentity' menjadi 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightClusterIdentity'.

#### <a name="azkeyvault"></a>Az.KeyVault
* [Breaking Change] Properti 'PSKeyVaultPermission' yang diganti namanya untuk mengikuti pola Azure RBAC.
* API migrasi AAD Graph ke API MSGraph.
* Menambahkan pesan ke 'Set-AzKeyVaultAccessPolicy' yang menyatakan bahwa untuk parameter Izin, menggunakan opsi 'Semua' tidak akan menyertakan izin ' Purge'.

#### <a name="azmanagedservices"></a>Az.ManagedServices
* [Breaking Change] Memperbarui versi API ke pratinjau 2020-02-01

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan properti baru EventName, Category, ResourceProviderName, OperationName, Status, SubStatus dengan string tipe sebagai output untuk perintah Get-AzLog [#15833]
* Penerima hub kejadian yang didukung di grup tindakan [#16348]
* Menambahkan kumpulan parameter default 'GetByResourceGroup' untuk perintah 'Get-AzAlertRule' [#16356]

#### <a name="aznetwork"></a>Az.Network
* Bugfix di PSAzureFirewallPolicyThreatIntelWalllist for FirewallPolicy
* Menambahkan parameter opsional '-IsSecuritySite' ke cmdlet berikut:
    - 'New-AzVpnSite'
* Menambahkan dukungan untuk Variabel Kecocokan yang baru dalam Pengecualian WAF
* Onboard Virtual Network Encryption to Virtual Network Cmdlets
* Menambahkan dukungan untuk parameter rentang port NAT dalam sumber daya aturan VPN NAT
    - 'New-AzVpnGatewayNatRule.md'
    - 'Update-AzVpnGatewayNatRule.md'
    - 'New-AzVirtualNetworkGatewayNatRule.md'
    - 'Update-AzVirtualNetworkGatewayNatRule.md'
* Menambahkan cmdlet baru untuk mendukung Per Pengecualian Aturan untuk WAF Gateway Aplikasi
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet'
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup'
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRule'
    - Cmdlet juga diperbarui untuk menambahkan properti untuk mengonfigurasi ExclusionManagedRuleSet dalam Pengecualian
        - 'New-AzApplicationGatewayFirewallPolicyExclusion'
* Perbaikan Bug dalam cmdlet Sertifikat Klien Tepercaya Gateway Aplikasi untuk memuat seluruh rantai sertifikat dari file.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* DataSourceType yang diperluas dengan nilai 'Kueri', 'Peringatan' untuk cmdlet LinkedStorageAccount
* [Breaking Change] mengganti nama 'StorageAccountId' menjadi 'StorageAccountIds'
  - 'New-AzOperationalInsightsLinkedStorageAccount'
* [Breaking Change] Mengembalikan 'PSSavedSearch' bukan 'HttpStatusCode' oleh 'New-AzOperationalInsightsComputerGroup'
* [Breaking Change] Mengembalikan 'PSCluster' bukan 'PSLinkedService' oleh 'Update-AzOperationalInsightsCluster'
* Sku yang diperluas dengan nilai 'capacityreservation', 'lacluster' untuk Ruang Kerja
* Menambahkan properti baru:'SkuCapacity', 'ForceCmkForQuery', 'DisableLocalAuth' untuk Ruang Kerja
* Properti baru yang ditambahkan: 'DailyQuotaGb'on'Set-AzOperationalInsightsWorkspace'
* Properti baru yang ditambahkan: 'ETag', 'Tag' untuk cmdlet StorageInsight
* Menambahkan properti baru 'StorageAccountResourceId' ke cmdlet:
  - 'Set-AzOperationalInsightsStorageInsight'
* Ditambahkan atribut SupportsShouldProcess ke cmdlet:
  - 'Set-AzOperationalInsightsStorageInsight'
* Menambahkan cmdlet baru untuk mendukung Table, DataExport, WorkspaceShareKey, PurgeWorkspace, dan AvailableServiceTier
* Menambahkan properti 'Kesalahan' dalam hasil 'Invoke-AzOperationalInsightsQuery' untuk mengambil kesalahan sebagian saat menjalankan kueri [#16378]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup diperbarui memvalidasi kumpulan untuk BackupManagementType yang didukung di 'Get-AzRecoveryServicesBackupItem', 'Get-AzRecoveryServicesBackupContainer', Get-AzRecoveryServicesBackupJob cmdlet.
* Azure Backup menambahkan dukungan untuk SAPHanaDatabase untuk 'Disable-AzRecoveryServicesBackupProtection', 'Unregister-AzRecoveryServicesBackupContainer', 'Get-AzRecoveryServicesBackupItem', 'Get-AzRecoveryServicesBackupContainer'.
* Perubahan Berganti: 'Get-AzRecoveryServicesBackupJob', 'Get-AzRecoveryServicesBackupContainer' dan 'Get-AzRecoveryServicesBackupItem' hanya akan mendukung perintah 'BackupManagementType MAB' dan bukan 'MARS'.
* Dukungan Pemulihan Situs Azure untuk reservasi kapasitas bagi azure ke penyedia Azure.

#### <a name="azresources"></a>Az.Resources
* Ditambahkan 'Get-AzProviderPreviewFeature', 'Register-AzProviderPreviewFeature' dan 'Unregister-AzProviderPreviewFeature'.
* Memperbaiki bug ketika menjalankan Get-AzPolicyAlias dengan nilai kosong dari parameter NamespaceMatch [#16370]
* [Perubahan pecah] Dimigrasikan dari AAD Graph ke Microsoft Graph
* [Perubahan pecah] Mengubah 'Id' yang dikembalikan di PSDenyAssignment dari string GUID menjadi ID yang sepenuhnya memenuhi syarat
* Parameter yang diperbolehkan 'Id' dalam 'Get-AzDenyAssignment' untuk menerima ID yang sepenuhnya memenuhi syarat
* Menambahkan cmdlet baru 'Publish-AzBicepModule' untuk menerbitkan modul Bicep
* Pesan penghentian yang ditambahkan untuk parameter 'AssignIdentity' dalam cmdlet '*-AzPolicyAssignment'.
* Menambahkan dukungan untuk identitas terkelola yang ditetapkan pengguna dalam penetapan kebijakan dengan menambahkan parameter 'IdentityType' dan 'IdentityId' ke cmdlet '*-AzPolicyAssignment'.
* Cmdlet kebijakan yang diperbarui untuk menggunakan api versi 2021-06-01 baru yang memperkenalkan dukungan untuk identitas terkelola yang ditetapkan pengguna dalam penetapan kebijakan.
* Izin API yang dipersempit ketika mendapatkan informasi tentang objek direktori aktif untuk *-AzRoleAssignment [#16054]

#### <a name="azsql"></a>az.sql
* Perbaikan pemfilteran wildcard FirewallRuleName di 'Get-AzSqlServerFirewallRule' [#16199]
* Memindahkan SQL Server dan SQL Instance AAD dari ActiveDirectoryClient ke MicrosoftGraphClient

#### <a name="azstackhci"></a>az.stackhci
* Az.StackHCI yang dipromosikan menjadi GA

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki kegagalan 'Get-AzStorageContainerStoredAccessPolicy' ketika izin null [#15644]
* Token Sas layanan blob yang didukung atau token akun Sas dengan izin i
    -  'New-AzStorageBlobSASToken'
    -  'New-AzStorageContainerSASToken'
    -  'New-AzStorageAccountSASToken'
* Perbaikan pembuatan token SAS wadah gagal dari kebijakan akses tanpa waktu kedaluwarsa, dan tetapkan waktu kedaluwarsa token SAS [#16266]
    -  'New-AzStorageContainerSASToken'
* Menghapus parameter -Name dari Get-AzRmStorageShare ShareResourceIdParameterSet
    - 'Get-AzRmStorageShare'
* Wadah buat atau migrasi yang didukung untuk mengaktifkan fitur yang Storage dengan pembuatan versi.
    -  'New-AzRmStorageContainer'
    -  'Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration'
* Kebijakan ketidakterbacaan yang didukung pada Storage blob.
    -  'Set-AzStorageBlobImmutabilityPolicy'
    -  'Remove-AzStorageBlobImmutabilityPolicy'
* Dukungan mengaktifkan/menonaktifkan perlindungan hukum pada Storage blob.
    -  'Set-AzStorageBlobLegalHold'
* Akun pembuatan penyimpanan yang didukung dengan mengaktifkan keterbacaan tingkat akun dengan penerapan versi, dan membuat/memperbarui akun penyimpanan dengan kebijakan penggunaan tingkat akun.
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbarui MICROSOFT.Azure.Management.Websites SDK ke 3.1.2

## <a name="660---november-2021"></a>6.6.0 - November 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan versi baru klien AAD menggunakan API Microsoft Graph

#### <a name="azaks"></a>Az.Aks
* Dukungan tambahan untuk parameter baru 'NetworkPolicy', 'PodCidr', 'ServiceCidr', 'DnsServiceIP', 'DockerBridgeCidr', 'NodePoolLabel', 'AksCustomHeader' di 'New-AzAksCluster'. [#13795]
* Peringatan tentang perubahan terbaru dalam melakukan migrasi ke Microsoft Graph.
* Dukungan tambahan untuk mengubah jumlah node di dalam kolam simpul. [#12379]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbaikan bug dalam cmdlet 'Get-AzApiManagementTenantGitAccess'.

#### <a name="azbatch"></a>Az.Batch
* Dihapus perakitan 'System.Text.Encodings.Web.dll' [#16062]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet untuk menambahkan properti VMGalleryApplication ke VM/VMSS
    - New-AzVmGalleryApplication
    - New-AzVmssGalleryApplication
    - Add-AzVmGalleryApplication
    - Add-AzVmssGalleryApplication
    - Remove-AzVmGalleryApplication
    - Remove-AzVmssGalleryApplication
* Menambahkan dukungan untuk pengaturan proksi dan debug untuk Ekstensi VM untuk SAP (AEM)
* Diperbarui New-AzGalleryImageVersion mengambil properti 'Encryption' dengan benar dari parameter '-TargetRegion'.
* Memperbarui Set-AzVmBootDiagnostic ke akun penyimpanan terkelola default jika tidak disediakan.
* Diedit New-AzVmss secara default saat 'OrchestrationMode' diatur ke Fleksibel.
    - Menghapus Pool NAT.
    - Removed UpgradePolicy. Memberikan kesalahan jika disediakan.
    - SinglePlacementGroup harus false. Memberikan kesalahan jika true.
    - Versi API Profil Jaringan adalah 2020-11-01 atau lebih baru.
    - Properti Utama Konfigurasi IP Profil Jaringan diatur ke true.

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Diperkenalkan Get-AzCosmosDBMongoDBBackupInformation untuk mengambil informasi cadangan terbaru untuk Persingadb.
* Updated New-AzCosmosDBAccount, Update-AzCosmosDBAccount to accept BackupStorageRedundancy
* Memperkenalkan Get-AzCosmosDBLocation untuk mencantumkan Akun Azure CosmosDB dan properti lokasinya.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan PublicNetworkAccess ke Update_AzDataFactoryV2 Command
* Memperbarui versi .Net SDK ADF ke 4.26.0

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Meningkatkan versi api ke 2021-07-12.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan dukungan untuk Premium sku dan namesapce serta parameter sakelar opsional 'DisableLocalAuth' ke 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Set site config netFrameworkVersion for Windows V4 apps only
* Pembuatan aplikasi fungsi yang diaktifkan untuk Tumpukan Fungsi V4 [#15919]

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui SDK Manajemen IoT Hub ke versi 4.1.0 (api-versi 2021-07-10)

#### <a name="azkeyvault"></a>Az.KeyVault
* Pesan peringatan ditambahkan tentang perubahan pecah yang akan datang menjadi 'New-AzKeyVaultRoleDefinition' dan 'Get-AzKeyVaultRoleDefinition'.
    - Untuk mematuhi sintaks 'New-AzRoleDefinition' dan 'Get-AzRoleDefinition' kami akan mengganti nama beberapa properti model 'PSKeyVaultPermission', yang mungkin mempengaruhi kedua cmdlet ini.
* Peringatan tentang perubahan terbaru dalam melakukan migrasi ke Microsoft Graph.

#### <a name="azmigrate"></a>Az.Migrate
* Pemeriksaan tambahan untuk alamat IP yang tidak valid

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Perbaikan bug di 'Set-AzOperationalInsightsLinkedService: saat layanan tertaut tidak ada, jalankan create(update) dan bukan gagal'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup memperbaiki masalah dengan StorageConfig
* Azure Backup menambahkan NodeList dan AutoProtectionPolicy Get-AzRecoveryServicesBackupProtectableItem Cmdlets.
* Azure Backup memperbaiki GetItemsForContainerParamSet untuk mendukung pengambilan item cadangan MAB.
* Azure Backup memperbaiki Get-AzRecoveryServicesBackupContainer mendukung BackupManagementType MAB dan bukan MARS.
* Peringatan perubahan pecah yang ditambahkan: 'Get-AzRecoveryServicesBackupJob', 'Get-AzRecoveryServicesBackupContainer' dan 'Get-AzRecoveryServicesBackupProtectableItem' hanya akan mendukung perintah 'BackupManagementType MAB' dan bukan 'MARS', perubahan akan diterapkan dari rilis yang akan datang.
* Menambahkan dukungan untuk tipe disk ZRS untuk replikasi Azure ke Azure.
* Menambahkan informasi zona Ketersediaan dalam respons item dilindungi direplikasi untuk replikasi Azure ke Azure.

#### <a name="azrediscache"></a>Az.RedisCache
* Membuat contoh baru dalam dokumentasi 'New-AzRedisCache' dan 'Set-AzRedisCache'.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug tentang kode keluar Bicep [#16055]
* Peringatan perubahan pecah untuk cmdlet AAD ditambahkan
* Properti ditambahkan 'UIFormDefinition' ke Template Spec Versions, 'Export-AzTemplateSpec' sekarang akan menyertakan Template Spec Version UIFormDefinition (jika ada) sebagai bagian dari ekspor.
* Penambahan tangkapan kesalahan untuk pembuatan penetapan peran gagal saat membuat Prinsipal Layanan
* Peningkatan kinerja untuk Get-AzPolicyAlias ketika -NamespaceMatch cocok dengan satu ruang nama RP

#### <a name="azsecurity"></a>Az.Security
* Referensi paket .NET SDK Keamanan diperbarui ke versi 3.0.0

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan dukungan untuk ZoneRedundant dan parameter sakelar opsional 'DisableLocalAuth' ke 'New-AzServiceBusNamespace' dan 'Set-AzServiceBusNamespace'

#### <a name="azsignalr"></a>az.signalr
* Cmdlet Web PubSub yang ditambahkan
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
* bgomezangulo ( @beagam ), Pembaruan Resume-AzNetAppFilesReplication.md (#16040)
* Jim McCormick ( @eimajtrebor ), Memperbaiki kesalahan ketik (#16091)
* Lampson Rollup ( @lampson ), Update Get-AzDataShare.md (#16015)
* @MaxMeng1985, Perbarui Get-AzSynapseSqlPoolRestorePoint.md (#16138)
* Reggie Gibson ( @regedit32 ), New-AzBotService: Fix AppSecret conversion to plaintext on Windows PowerShell (#16160)
* Mosaar Jensen @Splaxi ( ), Detail Identitas Bisnis tidak cocok dengan implementasi saat ini (#16141)

## <a name="650---october-2021"></a>6.5.0 - Oktober 2021
#### <a name="azaccounts"></a>Az.Accounts
* Didukung mendapatkan token akses untuk Microsoft Graph.
* Menambahkan AuthorizeRequestDelegate untuk mengizinkan modul layanan menyesuaikan audiens token.
* Memanfaatkan [AssemblyLoadContext untuk mengatasi](/dotnet/api/system.runtime.loader.assemblyloadcontext) masalah perakitan konflik di PowerShell.
* Diperbarui Azure.Core dari 1.16.0 hingga 1.19.0.

#### <a name="azattestation"></a>Az.Attestation
* Ketersediaan umum modul 'Az.Attestation'

#### <a name="azcdn"></a>Az.Cdn
* Perbaikan pengecualian referensi null dan kesalahan ketik dalam cmdlet 'New-AzFrontDoorCdnRule'

#### <a name="azcompute"></a>Az.Compute
* Referensi paket Compute .NET SDK diperbarui ke versi 49.1.0
* Perbaikan bug dalam 'Get-AzVM' yang menyebabkan output status daya yang tidak benar.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan argumen DataFlowEnableQuickReuse untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mengaktifkan penggunaan kembali cepat kluster dalam aktivitas saluran berikutnya.
* Memperbarui versi .Net SDK ADF ke 4.25.0
* Menambahkan argumen VNetInjectionMethod untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mendukung injeksi jaringan virtual express Azure-SSIS Integration Runtime.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Pembuatan tindakan mesin aturan yang diperbolehkan tanpa RouteConfigurationOverride untuk 'New-AzFrontDoorRulesEngineActionObject'.
* Memperbaiki parameter DynamicCompression yang diabaikan masalah 'New-AzFrontDoorRulesEngineActionObject'.

#### <a name="azkeyvault"></a>Az.KeyVault
* Definisi peran kustom yang didukung di HSM terkelola:
    - Buat melalui 'New-AzKeyVaultRoleDefinition',
    - Hapus melalui 'Remove-AzKeyVaultRoleDefinition',
    - Memfilter semua peran kustom melalui 'Get-AzKeyVaultRoleDefinition -Custom'.
* Enkripsi/Dekripsi/Bungkus/Buka kunci yang Didukung [#15679]
* Enabled managing resources in other subscriptions without switching the context by adding `-Subscription <String>` .

#### <a name="azmaintenance"></a>Az.Maintenance
* Menambahkan Dukungan pemeliharaan patch tamu.

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk Sku, parameter ScaleUnits dari sumber dayaHostHost.
    - 'New-AzBastion'
    - 'Set-AzBastion'
* Onboard Azure Resource Manager to Private Link Common Cmdlets
* Cmdlet yang diperbarui untuk menambahkan properti agar mengaktifkan/menonaktifkan BgpRouteTranslationForNat untuk VpnGateway.
    - 'New-AzVpnGateway'
    - 'Update-AzVpnGateway'
* Cmdlet yang diperbarui untuk menambahkan properti untuk menonaktifkan InternetSecurity untuk P2SVpnGateway.
    - 'New-AzP2sVpnGateway'
* Menambahkan cmdlet baru untuk sumber daya anak HubBgpConnection dari VirtualHub.
    - 'Get-AzVirtualHubBgpConnection'
    - 'New-AzVirtualHubBgpConnection'
    - 'Update-AzVirtualHubBgpConnection'
    - 'Remove-AzVirtualHubBgpConnection'
* Cmdlet Umum Onboard Azure HDInsight ke Private Link Common

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaikan bug Pemulihan Situs Azure untuk VMware pada Azure Reprotect, Kebijakan pembaruan, dan Menonaktifkan skenario.
* Azure Backup menambahkan dukungan untuk UserAssigned MSI di RecoveryServices Vault.

#### <a name="azresources"></a>Az.Resources
* Menambahkan pesan kesalahan yang lebih jelas untuk kasus di mana TemplateUri tidak menerima file bicep.
* Memperbaiki kesalahan ketik dengan grup Manajemen memutus deskripsi perubahan [#15819].
* Masalah casing tag sumber daya telah diperbaiki - casing tag sumber daya tidak dipertahankan.
* Diperbarui ke Microsoft.Azure.Management.Authorization 2.13.0-preview.

#### <a name="azsql"></a>az.sql
* Memperbaiki 'Get-AzSqlDatabaseImportExportStatus' untuk melaporkan kesalahan yang dialami

#### <a name="azstorage"></a>Az.Storage
* Telah meningkatkan Azure. Storage. Blob ke 12.10.0
* Telah meningkatkan Azure. Storage. Files.Shares to 12.8.0
* Telah meningkatkan Azure. Storage. Files.DataLake to 12.8.0
* Telah meningkatkan Azure. Storage. Antrean ke 12.8.0
* Akun penyimpanan pemutakhiran yang didukung untuk mengaktifkan HierarchicalNamespace
    -  'Invoke-AzStorageAccountHierarchicalNameUpgrade'
    -  'Stop-AzStorageAccountHierarchicalNameSpaceUpgrade'
* AccessTierInferred yang Didukung, Tag dalam skema kebijakan inventaris blob
    - 'New-AzStorageBlobInventoryPolicyRule'
* Akun penyimpanan buat/perbarui yang didukung dengan PublicNetworkAccess diaktifkan/dinonaktifkan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Wadah blob penyimpanan buat/perbarui yang didukung dengan RootSquash
    - 'New-AzRmStorageContainer'
    - 'Update-AzRmStorageContainer'
* Didukung AllowProtectedAppendWriteAll in set container Immutability Policy, and add container LegalHold
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
    - 'Add-AzRmStorageContainerLegalHold'

#### <a name="azstoragesync"></a>Az.StorageSync
* Perbaikan bug yang tidak semua properti objek PSSyncSessionStatus dan PSSyncActivityStatus sedang diisi dengan benar.
* Hal ini memengaruhi cmdlet 'Get-AzStorageSyncServerEndpoint' ketika mencoba mengakses properti output berikut:
    - SyncStatus.UploadStatus
    - SyncStatus.DownloadStatus
    - SyncStatus.UploadActivity
    - SyncStatus.DownloadActivity

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbarui 'Import-AzWebAppKeyVaultCertificate1' untuk mengatur nama default dengan kombinasi nama keyvault dan nama sertifikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @DSakura207, Gunakan instans PowerState terakhir di Status untuk status ke daya (#15941)
* Yannic Graber ( @grabery ), Recode Example2 (#15808)
* @joelmforsyth, Memperbaiki contoh multi kawasan (#15918)
* Adam Rollupman ( @SysAdminforCoffee ), Update Set-AzNetworkInterfaceIpConfig.md (#15846)
* Michael Michael ( ), Kalimat yang disword ulang untuk menjelaskan bahwa versi kunci tertentu harus @x509cert disediakan (#15886)

## <a name="640---september-2021"></a>6.4.0 - September 2021
#### <a name="azaccounts"></a>Az.Accounts
* Koreksi URL ke Portal Azure dalam hasil 'Get-AzEnvironment' dan 'Get-AzContext'. [#15429]
* Made infrastructural changes to support overriding default subscription via a `-SubscriptionId <String>` parameter.
    - [Az.Aks](/powershell/module/az.aks/get-azakscluster) adalah modul pertama yang mendukungnya.

#### <a name="azaks"></a>Az.Aks
* Agar `-Subscription <String>` tersedia di semua cmdlet Aks. Anda bisa mengelola sumber daya Aks di langganan lain tanpa mengalihkan konteks.

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan cmdlet 'Sync-AzApiManagementKeyVaultSecret' baru.
* Menambahkan cmdlet baru 'New-AzApiManagementKeyVaultObject'.
* Ditambahkan parameter opsional baru [-useFromLocation] ke cmdlet 'Get-ApiManagementCache' 'New-ApiManagementCache''Update-ApiManagementCache'.
* Cmdlet **New-AzApiManagement yang diperbarui** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk SKU 'Diisolasi' baru
    - Dukungan tambahan untuk mengelola Zona Ketersediaan menggunakan properti 'Zona'
    - Menambahkan dukungan untuk Menonaktifkan Gateway dalam Kawasan menggunakan properti 'DisableGateway'
    - Menambahkan dukungan untuk mengelola Versi Api minimum untuk memperbolehkan Pesawat Kontrol menggunakan properti 'MinimalControlPlaneApiVersion'.
* Pembaruan cmdlet **New-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Dukungan tambahan untuk mengelola Zona Ketersediaan menggunakan properti 'Zona'
    - Menambahkan dukungan untuk Menonaktifkan Gateway dalam Kawasan menggunakan properti 'DisableGateway'
* Pembaruan cmdlet **Add-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Dukungan tambahan untuk mengelola Zona Ketersediaan menggunakan properti 'Zona'
    - Menambahkan dukungan untuk Menonaktifkan Gateway dalam Kawasan menggunakan properti 'DisableGateway'
* Cmdlet yang **diperbarui Update-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Dukungan tambahan untuk mengelola Zona Ketersediaan menggunakan properti 'Zona'
    - Menambahkan dukungan untuk Menonaktifkan Gateway dalam Kawasan menggunakan properti 'DisableGateway'
* Updated cmdlet **New-AzApiManagementCustomHostnameConfiguration** to manage Custom Hostname Configuration
    - Ditambahkan dukungan untuk menentukan 'IdentityClientId' untuk menyediakan Managed Identity User Assigned ClientId untuk digunakan dengan KeyVault

#### <a name="azautomation"></a>Az.Automation
* Bug tetap: Menutup gagang file input dalam Import-AzAutomationRunbook

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah parameter wajib dalam cmdlet 'Get-AzCdnEndpointResourceUsage'

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter baru '-LinuxConfigurationPatchMode', '-WindowsConfigurationPatchMode', dan '-LinuxConfigurationProvisionVMAgent' menjadi 'Set-AzVmssOSProfile'
* Menambahkan parameter baru '-LinuxKeyName' dan '-GenerateSshKey' ke 'New-AzVM' untuk membuat VM dengan VM dengan VM
* Memperbaiki bug dalam 'Add-AzVHD' di Linux yang menyebabkan gagalnya unggahan untuk URI tujuan tertentu
* Cmdlet baru yang ditambahkan untuk Pengumpulan Titik Pulihkan dan Pulihkan:
    - 'New-AzRestorePoint'
    - 'New-AzRestorePointCollection'
    - 'Get-AzRestorePoint'
    - 'Get-AzRestorePointCollection'
    - 'Update-AzRestorePointCollection'
    - 'Remove-AzRestorePoint'
    - 'Remove-AzRestorePointCollection'
* Menambahkan parameter baru '-EnableSpotRestore' dan '-SpotRestoreTimeout' ke 'New-AzVMSSConfig' untuk mengaktifkan Kebijakan Pemulihan Titik
* Menambahkan cmdlet baru: 'Update-AzCapacityReservationGroup' dan 'Update-AzCapacityReservation'

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Perbaikan bug yang menjadi tempat gagalnya pemulihan akun database yang dihapus.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan argumen subnetId untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mendukung pemeriksaan RBAC untuk injeksi VNet terhadap ID sumber daya subnet, bukan ID sumber daya VNet.
* Menambahkan cmdlet 'Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint' untuk menyediakan daftar dependensi jaringan keluar untuk runtime integrasi SSIS di Azure Data Factory yang menggabungkan jaringan virtual.
* Ditambahkan PublicNetworkAccess ke Data Factory.
* Memperbarui versi .Net SDK ADF ke 4.23.0

#### <a name="azkeyvault"></a>Az.KeyVault
* Didukung menambahkan tombol EC di kunci vault [#15699]

#### <a name="azmigrate"></a>Az.Migrate
* Disk duplikat yang didukung UUID di disk sumber.
* Subnet yang didukung di VNet yang sama untuk AVSet.
* RunAsAccount fetching yang didukung untuk beberapa Vcenter dalam situs yang sama.

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui untuk menambahkan properti 'Subnet' untuk pool alamat backend penyeimbang muat berbasis IP.
    - 'New-AzLoadBalancerBackendAddressConfig'
* Cmdlet yang diperbarui untuk menambahkan properti 'CmdletInterface' untuk operasi terkait backend pool.
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan alat multi Pemulihan Situs Azure untuk VMware ke skenario pemulihan bencana Azure menggunakan RCM sebagai pesawat kontrol.
* Azure Backup memperbaiki masalahPhysicalPath target dengan SQL CRR
* Azure Backup tetap menonaktifkan proteksi untuk SQL kerja
* Azure Backup mengatasi bug dalam pengaturan properti CMK dalam rilis terbaru
* Azure Backup menghapus karakter khusus dari teks bantuan perintah register-azrecoveryservicesbackupcontainer

#### <a name="azresources"></a>Az.Resources
* Gunakan JsonExtensions untuk membuat serialisasi objek JSON untuk memastikan penggunaan pengaturan serialisasi kustom [#15552]
* Menambahkan dukungan untuk tipe perubahan 'Tidak Didukung' dan 'NoEffect' ke What-If cmdlet.

#### <a name="azsecurityinsights"></a>Az.SecurityInsights
* Diperbarui menjadi parameter 'Get-AzSentinelIncident'
    - Menambahkan '-Filter' untuk mendukung filter OData
    - Menambahkan '-OrderBy' untuk mendukung pemesanan OData
    - Tambahkan '-Max' untuk mendukung pengambilan lebih dari 1000 insiden default.

#### <a name="azsql"></a>az.sql
* Mengubah penerapan yang mendasari 'Get-AzSqlDatabase' untuk mendukung respons penomoran dari server
* Menambahkan parameter 'ZoneRedundant' ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance' untuk memungkinkan pembuatan dan pembaruan zona - instans tak perlu.
* Ditambahkan bidang ZoneRedundant ke model instans terkelola agar menampilkan informasi tentang zona - kelebihan data untuk contoh yang dikembalikan oleh 'Get-AzSqlInstance'.
* Extended AuditActionGroups enum in server & database audit. Menambahkan DBCC_GROUP, DATABASE_OWNERSHIP_CHANGE_GROUP, DATABASE_CHANGE_GROUP.
* Menambahkan bendera 'AsJob' ke 'Remove-AzSqlInstance'
* Menambahkan parameter 'SubnetId' ke 'Set-AzSqlInstance' untuk mendukung pembaruan subnet silang SLO
* Ditakhirkan ke versi SDK terbaru

#### <a name="azstorage"></a>Az.Storage
* Tag get/set blob yang didukung di blob tertentu
    -  'Get-AzStorageBlobTag'
    -  'Set-AzStorageBlobTag'
* Didukung buat blob tujuan dengan tag blob tertentu saat mengunggah/menyalin Blob
    -  'Set-AzStorageBlobContent'
    -  'Start-AzStorageBlobCopy'
* Daftar blob yang didukung di seluruh wadah dengan ekspresi sql filter tag blob
    -  'Get-AzStorageBlobByTag'
* Daftar blob yang didukung di dalam wadah dan menyertakan Tag Blob
    -  'Get-AzStorageBlob'
* Didukung jalankan operasi blob dengan kondisi tag blob, dan gagal cmdlet ketika kondisi tag blob tidak cocok
    -  'Get-AzStorageBlob'
    -  'Get-AzStorageBlobContent'
    -  'Get-AzStorageBlobTag'
    -  'Remove-AzStorageBlob'
    -  'Set-AzStorageBlobContent'
    -  'Set-AzStorageBlobTag'
    -  'Start-AzStorageBlobCopy'
    -  'Stop-AzStorageBlobCopy'
* Buat token blob sas dengan versi API baru
    -  'New-AzStorageBlobSASToken'
    -  'New-AzStorageContainerSASToken'
    -  'New-AzStorageAccountSASToken'
* Memperbaiki kegagalan salinan blob dengan kredensial OAuth ketika klien dan server memiliki perbedaan waktu [#15644]
    -  'Copy-AzStorageBlob'
* Perbaikan item Data Lake Gen2 gagal dengan token baca-saja SAS
    -  'Remove-AzDataLakeGen2Item'
* Cek masuk tujuan yang sudah direvisi memindahkan item Data Lake Gen2
    -  'Move-AzDataLakeGen2Item'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan kumpulan parameter ke 'Invoke-AzStorageSyncChangeDetection'
    - Dapat memanggil cmdlet tanpa parameter -DirectoryPath dan -Path untuk memicu deteksi perubahan di seluruh berbagi file
* Menambahkan dukungan untuk unggahan otoritatif sebagai bagian dari New-AzStorageSyncServerEndpoint.
* Menambahkan informasi status enumerasi perubahan awan dalam objek Titik Akhir Awan.
* Objek Titik Akhir Server yang diperbarui dengan berbagai properti kesehatan
* Menambahkan properti 'ServerName' di objek Titik Akhir Server dan Server Terdaftar untuk mendukung menampilkan FQDN server saat ini.

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki 'Set-AzWebApp' untuk mengembalikan pesan peringatan yang valid ketika gagal menambahkan -Hostname #9316
* Memperbaiki 'Get-AzWebApp' untuk mengembalikan CustomDomainVerificationId dalam respons. #9316

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Sears ( @asears )
  * Memperbaiki ejaan nama akun (#15779)
  * Memperbaiki Ejaan, contoh (#15780)
* @cawrites, Perbarui New-AzDataMigrationService.md (#15646)
* @harpaul-gill, Menambahkan dukungan untuk penomoran halaman di Sql Get Databases (#15772)
* @jeepingben, Membuat nama mutex yang aman untuk Linux (perbaikan #15653) (#15666)
* @LosManos, Dokumen: Parameter diabaikan saat rahasia daftar (#15788)
* Mats Docnsen ( @matsest ), docs: tambahkan contoh untuk Update-AzSubscription (#15748)
* Mauricio Cmdlet ( @mauricio-msft ), Fix typo dalam contoh cmdlet (#15719)

## <a name="630---august-2021"></a>6.3.0 - Agustus 2021
#### <a name="azaccounts"></a>Az.Accounts
* Penyimpanan otomatis konteks yang dinonaktifkan ketika penyimpanan cache token gagal Windows dan macOS
* Menambahkan versi PowerShell ke rekaman telemetri
* Meningkatkan Microsoft.ApplicationInsights dari 2.4.0 ke 2.12.0
* Memperbarui Azure.Core ke 1.16.0

#### <a name="azaks"></a>Az.Aks
* Ditambahkan 'Start-AzAksCluster', 'Stop-AzAksCluster', 'Get-AzAksUpgradeProfile' dan 'Get-AzAksNodePoolUpgradeProfile'. [#14194]
* Properti tambahan 'IdentityProfile' dalam output 'Get-AzAksCluster'. [#12546]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* [Breaking Change] Tipe PSCognitiveServicesAccount.Identity.Type dari IdentityType diubah menjadi ResourceIdentityType.
* [Breaking Change] Mengubah tipe PSCognitiveServicesAccount.Sku.Tier dari SkuTier menjadi string.
* [Breaking Change] Tindakan Yang DihapusRequired dari PrivateLinkServiceConnectionState.
* Memperbarui PowerShell untuk menggunakan versi 2021-04-30.
* Ditambahkan cmdlet 'Undo-AzCognitiveServicesAccountRemoval'.
* Parameter ditambahkan '-RestrictOutboundNetworkAccess', '-AllowedFqdnList', '-DisableLocalAuth', '-KeyVaultIdentityClientId', '-IdentityType', '-UserAssignedIdentityId' ke 'New-AzureCognitiveServicesAccount' dan 'Set-AzureCognitiveServicesAccount'.
* Parameter yang ditambahkan '-InRemovedState', '-Location' ke 'Remove-AzureCognitiveServicesAccount' dan 'Get-AzureCognitiveServicesAccount'.

#### <a name="azcompute"></a>Az.Compute
* Perbaikan peringatan dalam cmdlet 'New-AzVM' yang mengatakan bahwa sku VM sedang default meskipun ukuran sku disediakan oleh pengguna. Sekarang ini hanya terjadi saat pengguna tidak menyediakan ukuran sku.
* Cmdlet 'Set-AzVmOperatingSystem' yang diedit tidak lagi menimpa nilai EnableAutomaticUpdates apa pun yang sudah ada di komputer virtual yang diteruskan jika terdapat.
* Memperbarui modul Hitung untuk menggunakan .Net SDK versi 48.0.0 terbaru.
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
* Memperbarui versi .Net SDK ADF ke 4.21.0

#### <a name="azmigrate"></a>Az.Migrate
* Tipe SQL Server lisensi yang ditambahkan.
* Fitur CRN yang ditambahkan.
* Fitur tag sumber daya yang ditambahkan.
* Diperbarui ke versi api 10-02-2021.

#### <a name="azmonitor"></a>Az.Monitor
* Parameter yang ditambahkan 'ResourceGroupName' kembali untuk parameter 'Add-AzAutoscaleSetting' atur 'AddAzureRmAutoscaleSettingUpdateParamGroup' dan menjadikannya opsional [#15491]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Arsip untuk vault V1.
* Ditambahkan ProtectedItemsCount di Get-AzRecoveryServicesBackupProtectionPolicy.
* Perbaikan bug pemulihan situs Azure bagi Azure dalam memperbarui properti vm.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'RedisVersion' dalam 'New-AzRedisCache' dan 'Set-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
* Perbaikan bug dengan 'PSResource' ketika beberapa constructors meninggalkan properti 'SubscriptionId' yang belum ditetapkan/null.  [#10783]
* Menambahkan dukungan untuk membuat dan memperbarui Spesifikasi Templat dalam file Bicep [#15313]
* Menambahkan parameter '-ProceedIfNoChange' ke cmdlet pembuatan penyebaran.

#### <a name="azservicefabric"></a>az.servicefabric
* Perbaikan model Aplikasi Terkelola dan Klasik (Aplikasi, Kluster, Layanan) dengan memperbarui constructor untuk membawa semua properti baru
    - Hal ini menyelesaikan masalah pemipaan ketika pemipaan hasil langsung dari masuk ke cmdlet Dan Memperbarui atau Mengatur panggilan menghapus beberapa properti yang ditetapkan secara sengaja
    - Pembaruan file uji yang sesuai untuk membahas kasus yang disebutkan di atas

#### <a name="azsql"></a>az.sql
* Logika identitas tetap dalam 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Waktu Akses Terakhir Blob yang Didukung
    -  'Enable-AzStorageBlobLastAccessTimeTracking'
    -  'Disable-AzStorageBlobLastAccessTimeTracking'
    -  'Add-AzStorageAccountManagementPolicyAction'
* Membuat daftar 'Get-AzDataLakeGen2ChildItem' semua item datalake gen2 secara default, alih-alih membutuhkan pengguna untuk mencantumkan bagian demi bagian.
* Memperbaiki BlobProperties merupakan masalah kosong ketika menggunakan sas tanpa prefiks '?' [#15460]
* Menyalin kegagalan blob kecil secara sinkron [#15548]
    - 'Copy-AzStorageBlob'

#### <a name="azwebsites"></a>Situs Web Az.
* Perbaikan 'Add-AzWebAppAccessRestrictionRule' gagal saat pengguna tidak memiliki izin untuk mendapatkan daftar Tag Layanan #15316 dan #14862

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Borys Generalov ( @bgener ), Update Get-AzPolicyState.md (#15455)
* Dean Rollup ( @deanmock ), Update New-AzAutomationSchedule.md (#15371)
* John Bevan ( @JohnLBevan ), #10783 - Fix for Get-AzResource mengembalikan PSResource dengan null SubscriptionId (#15106)
* Michael Me deployments Sanchez ( @mikemej ), Update - Update deployment (external VNET) (#15391)
* @mjsharma, Menambahkan catatan untuk perintah alternatif (#15360)
* Ked Mardemootoo ( ), Memperbaiki beberapa kesalahan ketik untuk meningkatkan @nocticdr kejelasan (#15428)
* Pascal Berger ( @pascalberger ), Fix parameter name in Sync-AzVirtualNetworkPeering examples (#15493)
* @rcabr, Perbaikan dokumen di Get-AzStorageContainer (#15476)
* AAron ( @S-AA-RON ), Perbarui New-AzNetworkSecurityGroup.md (#15512)
* 坂本ポテコ ( @sakamoto-poteko ), Update New-AzVMConfig.md (#15376)
* @Shawn-Yuen, Perbarui Remove-AzDataLakeGen2Item.md (#15388)

## <a name="621---july-2021"></a>6.2.1 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki kesalahan akses ketika subsripiton tidak memiliki properti 'Tag' [#15425]

## <a name="620---july-2021"></a>6.2.0 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Tag, AuthorizationSource ke PSAzureSusbscripiton dan menambahkan TenantType, DefaultDomain, TenantBrandingLogoUrl, CountryCode ke PSAzureTenant [#15220]
* Meningkatkan klien langganan ke 01-01-2021 [#15220]
* Pemeriksaan mode Interaktif yang dihapus di lib umum
* Menambahkan titik akhir OperationalInsights ke lingkungan AzureChinaCloud [#15305]
* Log default modul dihasilkan otomatis yang dicetak ke aliran verbose

#### <a name="azaks"></a>Az.Aks
* Parameter tambahan 'AvailabilityZone' untuk 'New-AzAksNodePool'. [#14505]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Properti baca-saja yang ditambahkan 'ConnectionString' dan 'ApplicationId' ke komponen applicationinsights

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-OrchestrationMode' ke 'New-AzVmss' dan 'New-AzVmssConfig'
* Memperbarui cmdlet berikut agar berfungsi ketika sumber daya menggunakan sumber gambar jarak jauh menggunakan AKS atau Galeri Gambar Bersama.
    - 'Update-AzVm'
    - 'Update-AzVmss'
    - 'Update-AzGalleryImageVersion'
* Parameter yang ditambahkan '-EnableCrossZoneUpgrade' dan '-PrioritizeUnhealthyInstance' ke 'Set-AzVmssRollingUpgradePolicy'
* Menambahkan parameter 'AssessmentMode' ke cmdlet 'Set-AzVMOperatingSystem'.
* Memperbaiki bug di 'Add-AzVmssNetworkInterfaceConfiguration'
* Pemeriksaan throughput dan IOPS diperbaiki dalam 'Test-AzVMAEMExtension'
* Menambahkan cmdlet baru untuk versi API DISKRP 2020-12-01
    - New-AzDiskPurchasePlanConfig
    - Set-AzDiskSecurityProfile
* Cmdlet yang diubah untuk versi API DISKRP 2020-12-01
    - New-AzDiskConfig
    - New-AzSnapshotConfig
    - New-AzSnapshotUpdateConfig
    - New-AzDiskUpdateConfig
    - New-AzDiskEncryptionSetConfig
    - Update-AzDiskEncryptionSet

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Rilis ini memperkenalkan cmdlet untuk fitur Pencadangan Berkelanjutan(Titik dalam pemulihan waktu):
  - Diperkenalkan dukungan untuk membuat akun dengan kebijakan pencadangan mode berkelanjutan.
  - Diperkenalkan dukungan untuk Pemulihan titik waktu untuk akun dengan kebijakan pencadangan mode berkelanjutan.
  - Diperkenalkan dukungan untuk memperbarui interval cadangan dan penyimpanan cadangan untuk akun dengan kebijakan pencadangan mode berkala.
  - Diperkenalkan dukungan untuk mencantumkan sumber daya yang dapat dikembalikan di akun database langsung.
  - Memperkenalkan dukungan untuk menentukan tipe skema penyimpanan analitik pada pembuatan/pembaruan akun.
  - Cmdlet berikut ditambahkan:
    - Restore-AzCosmosDBAccount, New-AzCosmosDBDatabaseToRestore, Get-AzCosmosDBRestorableDatabaseAccount,
    - Get-AzCosmosDBSqlRestorableDatabase, Get-AzCosmosDBSqlRestorableContainer, Get-AzCosmosDBSqlRestorableResource,
    - Get-AzCosmosDBMongoDBRestorableDatabase, Get-AzCosmosDBMongoDBRestorableCollection, Get-AzCosmosDBMongoDBRestorableResource.

#### <a name="azdatafactory"></a>Az.DataFactory
* Added Customer Managed Key Encryption to DataFactory

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dua pengaturan aplikasi tambahan (WEBSITE_CONTENTSHARE dan WEBSITE_CONTENTAZUREFILECONNECTIONSTRING) untuk aplikasi Konsumsi Linux. [15124]
* Memperbaiki bug New-AzFunctionApp saat dibuat pada Azure Gov. [13379]
* Cmdlet Az.Functions ditambahkan perlu mendukung pembuatan dan penyalinan pengaturan aplikasi dengan nilai kosong. [14511]

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug referensi null untuk 'Get-AzMetric' ketika 'ResultType' diatur ke 'Metadata'
* Perbaikan bug untuk 'Add-AzAutoscaleSetting' tidak dapat pipe hasil dari 'Get-AzAutoscaleSetting' [#13861]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan alamat ip publik sebagai parameter opsional untuk membuat server rute
    - 'New-AzRouteServer'
* Cmdlet yang diperbarui untuk mengaktifkan spesifikasi zona edge
    - 'New-AzPublicIpPrefix'
    - 'New-AzLoadBalancer'
    - 'New-AzPrivateLinkService'
    - 'New-AzPrivateEndpoint'
* Menambahkan dukungan untuk menampilkan lokasi jaringan virtual yang diperluas dalam konsol
    - 'New-AzVirtualNetwork'
    - 'Get-AzVirtualNetwork'
* Menambahkan dukungan untuk menampilkan lokasi alamat IP publik yang diperluas dalam konsol
    - 'New-AzPublicIpAddress'
    - 'Get-AzPublicIpAddress'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaikan Nonaktifkan SQL Proteksi Otomatis AG.

#### <a name="azsecurity"></a>Az.Security
* Ketersediaan umum modul Az.Security
* Mengubah nama akun Get-AzRegulatoryComplainceAssessment menjadi Get-AzRegulatoryComplianceAssessment memperbaiki kesalahan ketik

#### <a name="azsql"></a>az.sql
* Menambahkan parameter 'RestrictOutboundNetworkAccess' ke cmdlet berikut
    - 'New-AzSqlServer'
    - 'Set-AzSqlServer'
* Menambahkan cmdlet baru untuk operasi CRUD di FQDN yang diperbolehkan dari aturan Firewall Keluar 'Get-AzSqlServerOutboundFirewallRule' 'New-AzSqlServerOutboundFirewallRule' 'Remove-AzSqlServerOutboundFirewallRule'
* Memperbaiki logika identitas untuk identitas SystemAssigned,UserAssigned untuk New-AzSqlServer, New-AzSqlInstance
* Cmdlet yang diperbarui untuk mendapatkan dan memperbarui frekuensi pencadangan SQL database berbeda 'Get-AzSqlDatabaseBackupShortTermRetentionPolicy' 'Set-AzSqlDatabaseBackupShortTermRetentionPolicy'
* Memperbaiki masalah PUT parsial untuk Kebijakan Azure di 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Penghapusan sementara wadah Blob yang didukung
    -  'Enable-AzStorageContainerDeleteRetentionPolicy'
    -  'Disable-AzStorageContainerDeleteRetentionPolicy'
* Daftar penampung Blob yang didukung yang dihapus
    -  'Get-AzRmStorageContainer'
    -  'Get-AzStorageContainer'
* Pemulihan penampung Blob yang didukung yang dihapus
    -  'Restore-AzStorageContainer'
* Pengaturan SMB aman yang didukung di properti layanan File
    - 'Update-AzStorageFileServiceProperty'
* Akun buat yang didukung dengan EnableNfsV3
    - 'New-AzStorageAccount'
* Input yang didukung parameter blob salinan lainnya dari pipeline [#15301]
    -  'Start-AzStorageBlobCopy'

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki 'Import-AzWebAppKeyVaultCertificate' untuk mendukung ServerFarmId [#15091]
* Memperbaiki 'Parameter opsional untuk menghapus atau mempertahankan Paket layanan aplikasi ketika WebApp terakhir dihapus dari paket'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Mikey Pertanyaaan ( @MikeyBronowski )
  * Memperbarui Get-AzSynapseTriggerRun.md (#15231)
  * Pembaruan Get-AzSynapsePipelineRun.md dengan menambahkan lebih banyak contoh yang membahas skenario lainnya (#15232)
* @mjsharma, Menambahkan catatan untuk perintah alternatif (#15359)
* @tomswedlund, Menambahkan dukungan untuk mengatur tipe skema penyimpanan analitik pada pembuatan/pembaruan akun untuk CosmosDB (#15362)
* @ylabade, Perbaiki nama parameter aplikasi web dalam contoh (#15291)

## <a name="610---june-2021"></a>6.1.0 - Juni 2021
#### <a name="azaccounts"></a>Az.Accounts
* Cmdlet yang ditambahkan 'Open-AzSurveyLink'
* File sertifikat yang didukung sebagai parameter input Connect-AzAccount

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah yang 'Set-AzAks' akan gagal dalam Runbook Otomatisasi. [#15006]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Memperbaiki masalah 'ResourcegroupName' yang terlewatkan saat menjalankan cmdlet di bawah ini dengan parameter 'InputObject' [#14848]
  * 'Get-AzApplicationInsightsLinkedStorageAccount'
  * 'New-AzApplicationInsightsLinkedStorageAccount'
  * 'Update-AzApplicationInsightsLinkedStorageAccount'
  * 'Remove-AzApplicationInsightsLinkedStorageAccount'

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah yang hilang di cmdlet 'Remove-AzCdnProfile'

#### <a name="azcompute"></a>Az.Compute
* Memperbarui modul Hitung untuk menggunakan .Net SDK versi 47.0.0 terbaru.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Menghapus tampilan kredensial berbagi file [#15224]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.19.0

#### <a name="azeventhub"></a>Az.EventHub
* Fungsionalitas tambahan untuk menerima input dari pipeline untuk 'Get-AzEventHub' dari 'Get-AzEventHubNamespace'.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung fitur monitor Azure baru di HDInsight:
    - Tambahkan cmdlet 'Get-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mendapatkan status Monitor Azure kluster HDInsight.
    - Tambahkan cmdlet 'Enable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mengaktifkan monitor Azure di kluster HDInsight.
    - Tambahkan cmdlet 'Disable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan menonaktifkan monitor Azure dalam kluster HDInsight.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menghapus item daftar duplikat dalam 'Get-AzKeyVault' [#15164]
* Menambahkan tag 'SecretManagement' ke modul 'Az.KeyVault' [#15173]

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui untuk merutekan server untuk cara yang lebih stabil dalam menambahkan konfigurasi IP.
* Dukungan tambahan untuk mendapatkan satu sumber daya tautan privat.
* Menambahkan deskripsi yang lebih mendetail tentang GroupId di 'New-AzPrivateLinkServiceConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan PrivateRange di AzureFirewallPolicy.
    - 'New-AzFirewallPolicy'
    - 'Set-AzFirewallPolicy'
* Cmdlet yang diperbarui untuk menambahkan NatRules di VirtualNetworkGateway dan BgpRouteTranslationForNat.
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'
* Cmdlet yang diperbarui untuk menambahkan EngressNatRules dan EgressNatRules di Koneksi VirtualNetworkGateway.
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan FlowTimeout di VirtualNetwork.
    - 'New-AzVirtualNetwork'
* Menambahkan cmdlet untuk Get/Create/Update/Delete VirtualNetworkGatewayNatRules.
    - 'New-AzVirtualNetworkGatewayNatRule'
    - 'Update-AzVirtualNetworkGatewayNatRule'
    - 'Get-AzVirtualNetworkGatewayNatRule'
    - 'Remove-AzVirtualNetworkGatewayNatRule'
* Menambahkan cmdlet baru untuk Sinkronisasi di VirtualNetworkPeering
    - 'Sync-AzVirtualNetworkPeering'
* Cmdlet yang diperbarui untuk menambahkan properti baru dan mendefinisikan ulang properti yang sudah ada di VirtualNetworkPeering
    - 'Add-AzVirtualNetworkPeering'
    - 'Get-AzVirtualNetworkPeering'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan PreferredRoutingGateway di VirtualHub.
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Cmdlet yang diperbarui untuk mengekspos dua properti baca-saja sertifikat klien.
    - 'Get-AzApplicationGatewayTrustedClientCertificate'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Pemindahan DS lintas penyewa yang ditambahkan.
* Menghapus batasan untuk mengambil poin pemulihan hanya untuk rentang waktu 30 hari.
* Mengaktifkan CRR untuk wilayah baru.

#### <a name="azresources"></a>Az.Resources
* Mengizinkan penamaan penyebaran ketika menguji penyebaran [#11497]

#### <a name="azsignalr"></a>az.signalr
* Diubah ke parameter 'Allow' dan 'Deny' dari cmdlet 'Update-AzSignalRNetworkAcl':
    - Menerima 'Jejak' sebagai nilai yang valid.
    - Menerima '@()' sebagai kumpulan kosong untuk menghapus daftar.
* Didukung 'ResourceGroupCompleter' dan 'ResourceNameCompleter' di cmdlet yang berlaku.
* Tidak berlaku lagi properti 'HostNamePrefix' tipe output 'PSSignalRResource' dari cmdlet berikut:
    - 'Get-AzSignalr'
    - 'New-AzSignalr'
    - 'Update-AzSignalr'

#### <a name="azsql"></a>az.sql
* Opsi ditambahkan untuk mendukung versi pendek id konfigurasi pemeliharaan untuk Instans Terkelola dalam cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Menambahkan HighAvailabilityReplicaCount ke 'New-AzSqlDatabaseSecavary'
* Menambahkan Administrator Eksternal dan AAD Hanya Properti ke AzSqlServer dan AzSqlInstance
    - Opsi ditambahkan untuk menentukan '-ExternalAdminName', '-ExternalAdminSid', '-EnableActiveDirectoryOnlyAuthentication' dalam cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
    - Opsi ditambahkan untuk memperluas informasi administrator eksternal menggunakan '-ExpandActiveDirectoryAdministrator' dalam cmdlet 'Get-AzSqlServer' dan 'Get-AzSqlInstance'
* Memperbaiki 'Set-AzSqlDatabase' agar ReadScale tidak lagi diatur ke Dinonaktifkan saat tidak ditentukan
* Memperbaiki 'Set-AzSqlServer' dan 'Set-AzSqlInstance' untuk PUT sebagian dengan hanya identitas dan properti null
* Parameter tambahan yang terkait dengan UMI dalam cmdlet 'New-AzSqlServer', 'New-AzSqlInstance', 'Set-AzSqlServer' dan 'Set-AzSqlInstance'.
* Ditambahkan parameter -AutoRotationEnabled ke cmdlet berikut:
    - 'Set-AzSqlServerTransparentDataEncryptionProtector'
    - 'Get-AzSqlServerTransparentDataEncryptionProtector'
    - 'Set-AzSqlInstanceTransparentDataEncryptionProtector'
    - 'Get-AzSqlInstanceTransparentDataEncryptionProtector'

#### <a name="azstorage"></a>Az.Storage
* Berbagi file pembuatan yang didukung dengan NFS/SMB enabledEnabledProtocol dan RootSquash, serta pembaruan berbagi dengan RootSquash
    - 'New-AzRmStorageShare'
    - 'Update-AzRmStorageShare'
* Didukung mengaktifkan Smb Multichannel pada layanan File
    -  'Update-AzStorageFileServiceProperty'
* Memperbaiki masalah salinan dalam akun yang sama dengan sumber akses dengan kredensial anonim ketika menyalin Blob di dalam akun yang sama dengan kredensial Oauth
* Removed StorageFileDataSmbShareOwner from value set of parameter DefaultSharePermission in create/update storage account
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki masalah yang mencegah penghapusan aturan berdasarkan nama dan pengidentifikasi unik dalam 'Remove-AzWebAppAccessRestrictionRule'
* Memperbaiki masalah pengaturan default AlwaysOn menjadi false di 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andy Roberts ( @andyr8939 ), Menghapus variabel TimeGrain yang tidak digunakan dari contoh (#15062)
* Roll Roll ( @AshleyRoll ), Write-Host menyimpan kredensial berbagi file (#15225)
* Kailash Mandal ( @KaishM ), Perbarui New-AzPublicIpAddress.md (#15040)
* Potpotsec ( @omiossec ), Update Get-AzExpressRouteCircuitRouteTable.md (#15054)
* Scott ( @S-T-S ), Perbarui Set-AzNetworkInterface.md (#15112)
* @sohaibMSFT, Contoh Skala Otomatis Gateway Aplikasi (#15071)
* @Srihsu, Perbarui Split-AzReservation.md (#15049)
* @srozemuller, kesalahan ketik dalam contoh parameter resourcegroup (#15146)

## <a name="600---may-2021"></a>6.0.0 - Mei 2021

#### <a name="supported-versions-of-powershell"></a>Versi PowerShell yang didukung

Karena [VBA-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) Az 6.0.0 hanya didukung pada versi PowerShell berikut:
 - Windows PowerShell 5.1
 - PowerShell 7.0.6 atau lebih baru
 - PowerShell 7.1.3 atau di atasnya

Untuk informasi selengkapnya dan cara memutakhirkan, lihat [Azure PowerShell Siklus Hidup modul](/powershell/azure/azureps-support-lifecycle).

#### <a name="azaccounts"></a>Az.Accounts
* Telah meningkatkan Azure.Identity ke 1.4 dan MSAL ke 4.30.1
* Parameter yang sudah tidak t ubah lagi 'ManagedServiceHostName', 'ManagedServicePort' dan 'ManagedServiceSecret' dari cmdlet 'Koneksi-AzAccount', variabel lingkungan 'MSI_ENDPOINT' dan 'MSI_SECRET' bisa digunakan sebagai gantinya
* Kustomisasi format tampilan PSAzureRmAccount untuk menyembunyikan rahasia prinsipal layanan [#14208]
* Menambahkan parameter opsional 'AuthScope' ke 'Koneksi-AzAccount' untuk mendukung autentikasi fitur bidang data yang disempurnakan
* Mengatur waktu coba ulang menurut variabel lingkungan [#14748]
* Autentikasi penerbit nama subjek yang didukung

#### <a name="azcompute"></a>Az.Compute
* Menambahkan 'Invoke-AzVmInstallPatch' untuk mendukung penginstalan patch di VM menggunakan PowerShell.
* Memperbarui modul Hitung untuk menggunakan .Net SDK versi 46.0.0 terbaru.
* Menambahkan parameter opsional '-EdgeZone' ke cmdlet berikut:
    - 'Get-AzvMImage
    - 'Get-AzvMImageOffer'
    - 'Get-AzvMImageSku'
    - 'New-AzDiskConfig'
    - 'New-AzImageConfig'
    - 'New-AzSnapshotConfig'
    - 'New-Azvm'
    - 'New-AzVmssConfig'
    - 'New-AzvMSS'

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Cmdlets baru ditambahkan: 'Start-AzContainerGroup', 'Stop-AzContainerGroup' [#10773], 'Invoke-AzContainerInstanceCommand' [#7648], 'Update-AzContainerGroup', 'Add-AzContainerInstanceOutput', 'Get-AzContainerInstanceCachedImage', 'Get-AzContainerInstanceCapability', 'Get-AzContainerInstanceUsage', 'New-AzContainerGroupImageRegistryCredentialObject', 'New-AzContainerGroupPortObject', 'New-AzContainerGroupVolumeObject', 'New-AzContainerInstanceEnvironmentVariableObject',  'New-AzContainerInstanceInitDefinitionObject', 'New-AzContainerInstanceObject', 'New-AzContainerInstancePortObject' dan 'New-AzContainerInstanceVolumeMountObject'
* Parameter Analitik Log yang Didukung dalam 'New-AzContainerGroup' [#11117]
* Menambahkan dukungan untuk menentukan profil jaringan dan nama Berbagi File Azure di 'New-AzContainerGroup' [#9993] [#12218]
* Menambahkan dukungan untuk menentukan variabel lingkungan sebagai SecureValue [#10110] [#10640]

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki masalah nama pengguna dan kata sandi di 'Import-AzContainerRegistryImage' [#14971]
* Memperbaiki operasi pesawat data (penyimpanan, tag, manifes) gagal pada registri silang dalam sesi Powershell tunggal [#14849]

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Diperkenalkan dukungan untuk RBAC data sql data, yang memungkinkan pembuatan, pembaruan, penghapusan, dan pengambilan Definisi Peran dan Penetapan Peran
  - Cmdlet berikut ditambahkan:
    - Get-AzCosmosDBSqlRoleDefinition, Get-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlRoleDefinition, New-AzCosmosDBSqlRoleAssignment,
    - Remove-AzCosmosDBSqlRoleDefinition, Remove-AzCosmosDBSqlRoleAssignment,
    - Update-AzCosmosDBSqlRoleDefinition, Update-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlPermission

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Peningkatan versi api ke pratinjau 2021-02-01.

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dukungan dalam pembuatan aplikasi fungsi untuk aplikasi fungsi Python 3.9 dan Node 14
* Menghapus dukungan dalam pembuatan aplikasi fungsi untuk V2, Python 3.6, Node 8, dan aplikasi fungsi Node 10
* Memperbarui parameter IdentityID dari string ke array string di Update-AzFunctionApp. Ini harus konsisten dengan New-AzFunctionApp yang memiliki parameter yang sama seperti array string
* Diperbarui FullyQualifiedErrorId untuk versi Fungsi yang tidak valid dari FunctionsVersionIsInvalid ke FunctionsVersionNotSupported
* Saat membuat aplikasi Node.js, jika tidak ada versi runtime yang ditentukan, versi runtime default diatur ke 14, bukan 12

#### <a name="azkeyvault"></a>Az.KeyVault
* Ukuran kunci yang disediakan untuk tombol RSA [#14819]

#### <a name="azkusto"></a>Az.Kusto
* Versi API benturan menjadi stabil 2021-01-01

#### <a name="azmaintenance"></a>Az.Maintenance
* Versi API benturan menjadi stabil 2021-05-01

#### <a name="azmigrate"></a>Az.Migrate
* Memperbaiki masalah di Initialize-AzMigrateReplicationInfrastructure.ps1

#### <a name="aznetwork"></a>Az.Network
* Validasi yang diperbarui untuk memperbolehkan memberikan nilai nol untuk parameter saDataSizeKilobytes
    - 'New-AzureRmIpsecPolicy'
* Menambahkan parameter opsional '-EdgeZone' ke cmdlet berikut:
    - 'New-AzNetworkInterface'
    - 'New-AzPublicIpAddress'
    - 'New-AzVirtualNetwork'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaikan masalah keamanan dengan SQL pulihkan, hal ini merupakan perubahan yang perlu dilakukan. TargetContainer menjadi wajib untuk Pemulihan Lokasi Alternatif.
* Alias cmdlet Set-AzRecoveryServicesBackupProperties dihapus, Set-AzRecoveryServicesBackupProperty cmdlet didukung.
* Alias cmdlet Get-AzRecoveryServicesBackupJobDetails dihapus, Get-AzRecoveryServicesBackupJobDetail cmdlet didukung.
* Dukungan tambahan untuk Pemindahan DS lintas langganan.
* Dukungan Pemulihan Situs Azure untuk VMware ke skenario pemulihan bencana Azure menggunakan RCM sebagai pesawat kontrol.

#### <a name="azresources"></a>Az.Resources
* Mengubah '-PengidentifikasiUris' dalam 'New-AzADApplication' menjadi parameter opsional
* Menghapus 'DisplayName' dari ADApplication yang dibuat oleh 'New-AzADServicePrincipal'
* SDK yang diperbarui ke 3.13.1-preview untuk menggunakan versi API Spesifik Templat GA
* Menambahkan 'AdditionalProperties' kePROPERTIES DANAMPILAN danAMPILGROUP [#14568]
* Didukung 'CustomKeyIdentifier' dalam 'New-AzADAppCredential' dan 'Get-AzADAppCredential' [#11457], [#13723]
* Mengubah 'MainTemplate' agar diperlihatkan oleh formatter default untuk Versi Spesifikasi Templat

#### <a name="azsecurityinsights"></a>Az.SecurityInsights
* Rilis GA untuk `Az.SecurityInsights`

#### <a name="azservicefabric"></a>az.servicefabric
* Perintah sertifikat kluster yang dihapus:
    - 'Add-AzServiceFabricClusterCertificate'
    - 'Remove-AzServiceFabricClusterCertificate'
* Mengubah model PSManagedService untuk menghindari penggunaan parameter properti secara langsung dari sdk.
* Menghapus parameter yang tidak berlaku untuk cmdlet terkelola:
    - 'ReverseProxyEndpointPort'
    - 'InstanceCloseDelayDuration'
    - 'ServiceDnsName'
    - 'InstanceCloseDelayDuration'
    - 'DropSourceReplicaOnMove'
* Perbaikan 'Update-AzServiceFabricReliability' untuk memperbarui jumlah instans vm yang benar dari tipe node utama pada sumber daya kluster.

#### <a name="azsql"></a>az.sql
* Dokumentasi 'Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline' diperbarui untuk menyertakan contoh mendefinisikan array array dengan satu array dalam.
* Cmdlet tambahan 'Copy-AzSqlDatabaseLongTermRetentionBackup'
    - Menyalin cadangan LTR ke server berbeda
* Cmdlet tambahan 'Update-AzSqlDatabaseLongTermRetentionBackup'
    - Perbarui Cadangan Storage kelebihan data untuk cadangan LTR
* Added CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy to 'Get-AzSqlDatabase', 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzDatabaseSecirisanry', 'Set-AzSqlDatabaseSecbasery', 'New-AzSqlDatabaseCopy'
    - Changed BackupStorageRedundancy value to CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy to reflect both the current value and what has been requested if a change was made

#### <a name="azstorage"></a>Az.Storage
* Snapshot berbagi file yang didukung
    - 'New-AzRmStorageShare'
    - 'Get-AzRmStorageShare'
    - 'Remove-AzRmStorageShare'
* Supported remove file share with it's snapshot (leased and not leased), by default remove file share will fail when share has snapshot
    - 'Remove-AzRmStorageShare'
* Kebijakan inventaris blob Set/Get/Remove blob yang Didukung
    - 'New-AzStorageBlobInventoryPolicyRule'
    - 'Set-AzStorageBlobInventoryPolicy'
    - 'Get-AzStorageBlobInventoryPolicy'
    - 'Remove-AzStorageBlobInventoryPolicy'
* DefaultSharePermission yang Didukung dalam membuat/memperbarui akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* AllowCrossTenantReplication yang Didukung dalam akun penyimpanan buat/perbarui
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Kebijakan Setel Kebijakan Replikasi Objek yang Didukung dengan SourceAccount/DestinationAccount Storage id sumber daya akun
    - 'Set-AzStorageObjectReplicationPolicy'
* Kumpulan SasExpirationPeriod yang didukung sebagai TimeSpan.Zero
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount
* Pastikan nama akun yang benar digunakan saat membuat kredensial akun
    - 'New-AzStorageContext'

#### <a name="azstoragesync"></a>Az.StorageSync
* Deprecated 'Invoke-AzStorageSyncFileRecall'
    - Pelanggan harus sebaliknya menggunakan 'Invoke-StorageSyncFileRecall', cmdlet yang dikirim dengan agen Sinkronisasi File Azure.
* Fitur transfer data offline yang dihapus di 'New-AzStorageSyncServerEndpoint'.

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Versi API benturan untuk 2017-04-01-preview
* Dukungan Kluster StreamAnalytics yang ditambahkan

#### <a name="azwebsites"></a>Situs Web Az.
* diperbarui 'Set-AzAppServicePlan' untuk mempertahankan Tag yang sudah ada saat menambahkan Tag baru
* Memperbaiki 'Set-AzWebApp' untuk mengatur AppSettings
* memperbarui 'Set-AzWebAppSlot' untuk mengatur FtpsState
* Menambahkan dukungan untuk Situs Statis.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @corichte, Perbarui New-AzVirutalNetworkGatewayConnection Ex 1 (#14858)
* ShishiOka ( @hyoshioka0128 )
  * Ketik "Database Azure SQL"→"Azure SQL Database" (#14883)
  * Typo "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14891)
  * Typo "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14892)
  * Typo "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14902)
  * Typo "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14901)
  * Typo "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14900)
  * Typo "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14898)
  * Typo "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14899)
* Zelos ( @jzelos ), Contoh 3 yang diperbarui untuk menggunakan parameter yang benar (#14852)
* @StevePantol, Perbarui New-AzVMwarePrivateCloud.md (#14996)

## <a name="590---may-2021"></a>5.9.0 - Mei 2021
#### <a name="azaks"></a>Az.Aks
* Dukungan tambahan 'AcrNameToAttach' di 'Set-AzAksCluster'. [#14692]
* Dukungan tambahan 'AcrNameToDetach' di 'Set-AzAksCluster'. [#14693]
* Ditambahkan 'Set-AzAksClusterCredential' untuk mengatur ulang ServicePrincipal kluster AKS yang sudah ada.

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk Identitas yang Ditetapkan Pengguna dan bendera PublicNetworkAccess

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung dukungan AFD Premium / SKU Standar

#### <a name="azcompute"></a>Az.Compute
* Memperbarui cmdlet 'Set-AzVMDiskEncryptionExtension' untuk mendukung migrasi ekstensi ADE dari dua pass (versi dengan AAD parameter input) untuk akses tunggal (versi tanpa AAD parameter input).
    - Menambahkan parameter beralih '-Migrasi' untuk memicu alur kerja migrasi.
    - Menambahkan parameter sakelar '-MigrationRecovery' untuk memicu alur kerja pemulihan untuk VM yang mengalami kegagalan setelah migrasi dari dua ADE pass.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan Identitas yang Ditetapkan Pengguna ke Data Factory.
* Memperbarui versi .Net SDK ADF ke 4.18.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Parameter Enable-AzFrontDoorCustomDomainHttps's SecretVersion yang diizinkan bersifat opsional untuk mendukung rotasi otomatis sertifikat-sendiri

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -IncludeVersions' ketika versi saat ini dinonaktifkan [#14740]
* Ditampilkan kode kesalahan dan pesan ketika memperbarui rahasia yang di pembersihan [#14800]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk Beberapa IP per NIC untuk Azure ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk SqlServerLicenseType untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk Ketersediaan diatur ke VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk TargetVmSize untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk Penyimpanan Sumber Daya untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk Kumpulan Skala Mesin Virtual bagi Azure ke penyedia Azure.
* Added support for restoring unmanaged disks vm as managed disks.

#### <a name="azresources"></a>Az.Resources
* Parameter yang ditambahkan 'ObjectType' untuk 'New-AzRoleAssignment'

#### <a name="azservicefabric"></a>az.servicefabric
* Upgraded Managed Cluster commands to use Service Fabric Managed Cluster SDK version 1.0.0 which uses service fabric resource provider api-version 2021-05-01.
* 'New-AzServiceFabricManagedCluster' menambahkan parameter UpgradeCadence dan ZonalResiliency.
* 'New-AzServiceFabricManagedNodeType' menambahkan parameter DiskType, VmUserAssignedIdentity, IsStateless dan MultiplePlacementGroup.
* 'New-AzServiceFabricManagedClusterService' dan 'Set-AzServiceFabricManagedClusterService' menandai parameter untuk penghentian: InstanceCloseDelayDuration, DropSourceReplicaOnMove dan ServiceDnsName. Dukungan mereka tidak didukung.

#### <a name="azresourcemover"></a>Az.ResourceMover
* Ketersediaan umum modul 'Az.ResourceMover'

#### <a name="azstorage"></a>Az.Storage
* Akun penyimpanan buat/perbarui yang didukung dengan KeyExpirationPeriod dan SasExpirationPeriod
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Akun penyimpanan buat/perbarui yang didukung dengan enkripsi keyvault dan access keyvault dengan identitas yang ditetapkan pengguna
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* EdgeZone yang Didukung dalam membuat akun penyimpanan
    - 'New-AzStorageAccount'
* Memperbaiki masalah yang menghapus blob yang tidak tetap akan menampilkan pesan yang salah.
    - 'Remove-AzStorageAccount'
* Pembaruan yang Storage properti Account KeyVault dengan pembersihan Keyversion untuk mengaktifkan rotasi otomatis tombol [#14769]
    - 'Set-AzStorageAccount'
* Pesan peringatan perubahan perubahan yang ditambahkan untuk perubahan pemecahan cmdlet yang akan datang
    - 'Remove-AzRmStorageShare'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Thomas Lee ( @doctordns ), Update Get-AzEnvironment.md (#14704)
* Fa faq ( @FullByte ), Contoh dengan parameter yang salah (salah ketik) (#14743)
* @gradinDotCom, Perbarui Get-AzNetworkWatcherNextHop.md (#14813)
* Dr Low ( @greglow-sdu ), Update Get-AzSqlServerDnsAlias.md (#14737)
* Prateek Montgomery ( @PrateekKumarSingh )
  * memperbaiki kesalahan ketik (#14779)
  * memperbaiki kesalahan ketik (#14773)
* Remco Eissing ( @remcoeissing )
  * Memperbaiki kesalahan ketik Restore-AzApiManagement (#14770)
  * Contoh 2 untuk menggunakan New-AzPolicyExemption (#14716)
* @sharma224
  * Perubahan identitas pengguna (#14803)
  * Kunci terkelola Pelanggan Pendukung (#14680)
* Yannick Dils ( @yannickdils ), Penjelasan Pembaruan Lokasi (#14719)

## <a name="580---april-2021"></a>5.8.0 - April 2021
#### <a name="azaccounts"></a>Az.Accounts
* Kembali ke konteks valid pertama jika tombol konteks default saat ini adalah 'Default' yang tidak valid

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk Enkripsi Kunci yang Dikelola Pelanggan dengan Identitas Ditetapkan Sistem
* Memperbaiki masalah yang menonaktifkan jadwal penyebaran pembaruan jika jadwal dibuat ulang dengan nama yang sama

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki bug ketika disk data 1 yang dilampirkan ke VMSS untuk Remove-AzVmssDataDisk [#13368]
* Menambahkan cmdlet baru untuk mendukung cmdlet terkait TrustedLaunch:
    - 'Set-AzVmSecurityProfile'
    - 'Set-AzVmUefi'
    - 'Set-AzVmssSecurityProfile'
    - 'Set-AzvmssUefi'
* Nilai default yang diedit untuk parameter Size New-AzVM cmdlet from Standard_DS1_v2 to Standard_D2s_v3.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Perbaikan bug di 'Get-AzContainerRegistryRegistryFest' yang memperlihatkan nama gambar yang salah

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung mendapatkan vmsize default dari backend jika pelanggan tidak menyediakan parameter terkait: '-WorkerNodeSize', '-HeadNodeSize', '-MasukkeeperNodeSize', '-EdgeNodeSize', '-DatakaManagementNodeSize'.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Menambahkan dukungan untuk LoginServer Acr

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -AsPlainText' jika rahasia tidak ditemukan [#14645]

#### <a name="azmigrate"></a>Az.Migrate
* Nullref Bug diperbaiki saat menemukan server dan memulai commandlet infrastruktur replikasi.

#### <a name="azmonitor"></a>Az.Monitor
* Cmdlet yang ditambahkan untuk mendapatkan kategori pengaturan diagnostik bagi langganan
    - 'Get-AzSubscriptionDiagnosticSettingCategory'
* Operasi pengaturan diagnostik langganan yang didukung dengan parameter baru: SubscriptionId
    - 'Get-AzDiagnosticSetting'
    - 'New-AzDiagnosticSetting'
    - 'Remove-AzDiagnosticSetting'
* Parameter 'AutoMitigate' yang didukung dalam properti aturan pemberitahuan metrik. Bendera menunjukkan apakah pemberitahuan sebaiknya diatasi secara otomatis atau tidak.

#### <a name="azresources"></a>Az.Resources
* Ditambahkan peringatan perubahan pecah yang akan datang di cmdlet di bawah, karena nilai parameter 'IdentifierUris' akan memerlukan domain terverifikasi.
  - 'New-AzADApplication'
  - 'Update-AzADApplication'
  - 'New-AzADServicePrincipal'
  - 'Update-AzADServicePrincipal'
* Pesan peringatan Bicep diabaikan di aliran kesalahan jika kode keluar sama dengan nol.

#### <a name="azsql"></a>az.sql
* Peringatan perubahan pecah output cmdlet ditambahkan ke hal berikut:
    - 'New-AzSqlDatabase'
    - 'Get-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
    - 'Remove-AzSqlDatabase'
    - 'New-AzSqlDatabaseSecbasery'
    - 'Remove-AzSqlDatabaseSecbasery'
    - 'Get-AzSqlDatabaseReplicationLink'
    - 'New-AzSqlDatabaseCopy'
    - 'Set-AzSqlDatabaseSecbasery'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki kegagalan menyalin blob dengan konteks sumber sebagai Oauth [#14662]
    -  'Start-AzStorageBlobCopy'

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Menambahkan pesan peringatan perubahan perubahan yang akan datang ke semua cmdlet karena perubahan yang akan datang pada parameter.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* And fix @BurgerZ typo (#14575)
* Mark Allison ( @markallisongit ), Perbarui Invoke-AzSqlInstanceFailover.md (#14603)

## <a name="570---march-2021"></a>5.7.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki pesan peringatan yang tidak Windows PowerShell [#14556]
* Mengatur variabel Azure Environment 'AzureKeyVaultServiceEndpointResourceId' sesuai dengan nilai 'AzureKeyVaultDnsFix' saat menemukan lingkungan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah untuk memulai runbooks Python3 dengan parameter

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.15.0

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan bahwa 'New-AzServiceBusAuthorizationRuleSASToken' mengembalikan token yang tidak valid. [#12975]

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui SDK dan model Manajemen IoT Hub ke versi 3.0.0 (api-versi 2020-03-01)

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung desain API baru yang akan datang untuk 'Export-AzKeyVaultSecurityDomain'
* Memperbaiki beberapa kesalahan ketik dalam pesan cmdlet [#14341]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk mengganti nama produk lama 'router virtual' dengan nama baru 'server rute' di masa mendatang.
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - Menambahkan peringatan atribut penghentian ke cmdlet yang lama.
* Memperbarui 'set-azExpressRouteGateway' untuk memperbolehkan parameter -MinScaleUnits tanpa menentukan -MaxScaleUnits
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan VpnLinkConnectionMode di VpnSiteLinkConnections.
    - 'New-AzVpnSiteLinkConnection'
    - 'Update-AzVpnConnection'
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Link Situs VPN.
    - 'Get-VpnSiteLinkConnectionIkeSa'
* Menambahkan cmdlet baru untuk mereset Koneksi Gateway Jaringan Virtual.
    - 'Reset-AzVirtualNetworkGatewayConnection'
* Menambahkan cmdlet baru untuk mereset Koneksi Link Situs Vpn.
    - 'Reset-VpnSiteLinkConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan parameter opsional -TrafficSelectorPolicies
    - 'New-AzVpnConnection'
    - 'Update-AzVpnConnection'
* Perbaikan bug untuk pembaruan vpnServerConfiguration.
* Tambahkan skenarioTest untuk VWAN multi-auth p2s.
* Menambahkan dukungan fitur multi-auth untuk VNG
    - 'Get-AzVpnClientConfiguration'
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Pemulihan Lintas Zona untuk mesin virtual yang dikelola.

#### <a name="azredisenterprisecache"></a>Az.RedisEnterpriseCache
* Versi GA az.RedisEnterpriseCache

#### <a name="azresources"></a>Az.Resources
* Pesan bicep yang dialihkan ke verbose stream
* Menghapus logika menyalin file templat Bicep ke folder sementara.
* Tambahkan dukungan jenis sumber daya pengecualian kebijakan
* Memperbaiki fungsionalitas what-if saat menggunakan parameter '-QueryString'.
* Dinormalkan '-QueryString' yang dimulai dengan '?' untuk skenario yang melibatkan parameter dinamis.

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaikan bahwa 'New-AzServiceBusAuthorizationRuleSASToken' mengembalikan token yang tidak valid. [#12975]

#### <a name="azservicefabric"></a>az.servicefabric
* Parameter tambahan 'VMImagePublisher', 'VMImageOffer', 'VMImageSku', 'VMImageVersion' menjadi 'Add-AzServiceFabricNodeType' untuk memudahkan pembuatan gambar OS alternatif yang mudah untuk tipe node baru.
* Parameter yang ditambahkan 'IsPrimaryNodeType' ke 'Add-AzServiceFabricNodeType' agar dapat membuat tipe node utama tambahan, untuk tujuan transisi tipe node utama ke tipe node utama dalam kasus migrasi OS.
* 'Add-AzServiceFabricNodeType' kini menyalin ekstensi LinuxDiagnostic dengan benar. Masalah ini sebelumnya tidak berfungsi untuk Linux.
* 'Add-AzServiceFabricNodeType' sekarang menyalin dengan benar pemetaan port PORT NAT masuk KE tipe simpul baru.
* Templat yang ditambahkan untuk 'UbuntuServer1804' untuk membuat kluster Ubuntu 18.04 menggunakan 'New-AzServiceFabricCluster'.
* 'Remove-AzServiceFabricNodeType' tidak benar memblokir tipe node perunggu untuk dihapus, dan telah diperbarui menjadi blok hanya ketika tingkat kulit perunggu berbeda antara tipe node SF dan pengaturan VMSS.
* Ditambahkan cmdlet 'Update-AzServiceFabricVmImage' untuk memperbarui tipe paket runtime SF yang dikirimkan. Hal ini harus diubah saat melakukan migrasi dari Ubuntu 16 ke 18.
* Ditambahkan cmdlet 'Update-AzServiceFabricNodeType' untuk memperbarui properti tipe node kluster. Untuk saat ini, semata-mata digunakan untuk memperbarui apakah tipe node utama melalui parameter bool '-IsPrimaryNodeType False'.
* 'Update-AzServiceFabricReliability' kini dapat memperbarui tingkat keandalan ketika kluster memiliki lebih dari satu tipe node utama. Untuk melakukan ini, nama tipe node disediakan melalui parameter -NodeType baru.
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
* Upgraded Managed Cluster commands to use Service Fabric Managed Cluster SDK version 1.0.0-beta.1 which uses service fabric resource provider api-version 2021-01-01-preview.

#### <a name="azsql"></a>az.sql
* Cmdlet yang ditambahkan 'New-AzSqlServerTrustGroup'
* Cmdlet yang ditambahkan 'Remove-AzSqlServerTrustGroup'
* Cmdlet yang ditambahkan 'Get-AzSqlServerTrustGroup'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah akun daftar dari grup sumber daya tidak akan menggunakan nextlink
    - 'Get-AzStorageAccount'
* Supported ChangeFeedRetentionInDays when Enable ChangeFeed on Blob service
    - 'Update-AzStorageBlobServiceProperty'

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbarui 'Add-AzWebAppAccessRestrictionRule' untuk memperbolehkan semua Tag Layanan yang didukung dan memvalidasi terhadap Service Tag API.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Fred sintaks Sackur ( @fsackur ), Perbaiki token SAS yang tidak valid dari New-AzServiceBusAuthorizationRuleSASToken dan New-AzEventHubAuthorizationRuleSASToken (#14535)
* Serafín Corre ( @infoTrainingym ), Parameter Unkown (#14515)
* João Rollup de Almeida ( @Jalmeida1994 ), Pembaruan Get-AzAksNodePool.md (#14503)
* Liam Barnett ( @liambarnett ), Memperbaiki 3 kesalahan ketik dalam dokumen (#14335)
* @sbojjawar-Msft, Perbarui Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline.md (#14432)
* Yannick Dils ( @yannickdils ), Hapus grup sumber daya dari get-azloadbalancer ini menghasilkan pembaruan kawasan /zona. (#14417)

## <a name="560---march-2021"></a>5.6.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Mutakhirkan Azure.Identity untuk memperbaiki masalah Connect-AzAccount saat kredensial ADFS digunakan [#13560]

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah string yang tidak bisa di serialkan dengan benar. [#14215]
* Dukungan tambahan untuk Tipe Python3 Runbook

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EnableHotpatching' ke cmdlet 'Set-AzVMOperatingSystem' untuk Windows komputer.
* Parameter yang ditambahkan '-PatchMode' ke kumpulan parameter Linux dalam cmdlet 'Set-AzVMOperatingSystem'.
* [Breaking Change] Memutus perubahan bagi pengguna di pratinjau publik untuk fitur Patching Tamu VM.
    - Properti yang dihapus 'RebootStatus' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Properti yang dihapus 'StartedBy' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Properti yang diganti namanya 'Kbid' menjadi 'KbId' dalam objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineSoftwarePatchProperties'.
    - Properti 'patches' yang diganti namanya menjadi 'availablePatches' di objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineAssessPatchesResult'.
    - Objek yang diganti namanya 'Microsoft.Azure.Management.Compute.Models.SoftwareUpdateRebootBe azureior' menjadi 'Microsoft.Azure.Management.Compute.Models.VMGuestPatchRebootBe azureior'.
    - Objek yang diganti namanya 'Microsoft.Azure.Management.Compute.Models.InGuestPatchMode' menjadi 'Microsoft.Azure.Management.Compute.Models.WindowsVMGuestPatchMode'.
* [Breaking Change] Menghapus semua cmdlet 'ContainerService'. API Layanan Kontainer mulai ditolak pada bulan Januari 2020.
    - 'Add-AzContainerServiceAgentPoolProfile'
    - 'Get-AzContainerService'
    - 'New-AzContainerService'
    - 'New-AzContainerServiceConfig'
    - 'Remove-AzContainerService'
    - 'Remove-AzContainerServiceAgentPoolProfile'
    - 'Update-AzContainerService'

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Perbaikan autentikasi untuk `Connect-AzContainerRegistry`

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan cmdlet NetworkAclBypass dan NetworkAclBypassResourceIds untuk Akun Database.
* Memperkenalkan parameter ServerVersion ke Update-AzCosmosDBAccount.
* Memperkenalkan cmdlet BackupInterval dan BackupRetention untuk Akun Database

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 4.14.0

#### <a name="azmigrate"></a>Az.Migrate
* Az.Migrate GA
* Memadukan Initialize-AzMigrateReplicationInfrastructure sebagai cmdlet dalam modul Az.Migrate, dari skrip eksternal yang sedang dijalankan saat ini.
* Membuat beberapa parameter New-AzMigrateServerReplication, New-AzMigrateDiskMapping peka huruf besar/huruf.
* Penambahan dukungan untuk perubahan perlengkapan skala, untuk menangani tombol V3 baru.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Added null check for target storage account in FileShare restore.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk penyebaran sumber daya Azure dalam bahasa Bicep
* Memperbaiki masalah terkait Penggunaan Templat Penyebaran dalam 'New-AzTenantDeployment' dan 'New-AzManagementGroupDeployment'
* Menambahkan dukungan untuk parameter '-QueryString' dalam cmdlet 'Test-Az*Deployments'
* Memperbaiki masalah terkait parameter dinamis ketika 'New-Az*Deployments' digunakan dengan '-QueryString'
* Menambahkan dukungan untuk parameter '-TemplateParameterObject' saat menggunakan parameter '-TemplateSpecId' dalam cmdlet 'New-Az*Deployments'
* Memperbaiki pesan kesalahan yang tidak akurat yang diterima ketika mencoba menyebarkan spesifikasi templat yang tidak ada

#### <a name="azstorage"></a>Az.Storage
* Ditakhirkan ke Microsoft.Azure.Management. Storage 19.0.0, untuk mendukung API versi baru 2021-01-01.
* Aturan akses sumber daya yang didukung di NetworkRuleSet
    - 'Update-AzStorageAccountNetworkRuleSet'
    - 'Add-AzStorageAccountNetworkRule'
    - 'Remove-AzStorageAccountNetworkRule'
* Versi Blob yang didukung dan tipe Tambah Blob dalam Kebijakan Manajemen
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyFilter'
    - 'Set-AzStorageAccountManagementPolicy'
* Akun buat/perbarui yang didukung dengan AllowSharedKeyAccess
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Cakupan Pembuatan Enkripsi yang Didukung dengan RequireInfrastructureEncryption
    - 'New-AzStorageEncryptionScope'
* Blok salinan yang didukung secara asinkron, dengan lingkup enkripsi
    - 'Copy-AzStorageBlob'
* Memperbaiki masalah ketika Get-AzStorageBlobContent menggunakan karakter pemisah direktori yang salah di Linux dan MacOS [#14234]

#### <a name="azwebsites"></a>Situs Web Az.
* Memperkenalkan opsi untuk memberikan waktu kustom untuk 'Publish-AzWebApp'
* Menambahkan dukungan untuk Lingkungan Layanan Aplikasi
    - 'New-AzAppServiceEnvironment'
    - 'Remove-AzAppServiceEnvironment'
    - 'Get-AzAppServiceEnvironment'
    - 'New-AzAppServiceEnvironmentInboundServices'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @alunmj, Ejaan kecil, perubahan pemformatan (#14155)
* @chakra146, Perbarui Add-AzLoadBalancerInboundNatPoolConfig.md (#14231)
* Martin Ehrnst ( @ehrnst ), Memperbaiki kesalahan ketik dalam cmdlet (#14112)
* Jan David Narkiekie ( @jdnark )
  * Contoh yang New-AzAks cmdlet warisan dan alias untuk New-AzAksCluster. Contoh yang diubah agar New-AzAksCluster cmdlet halaman dokumentasi ini. (#14088)
  * Tipe fox: changed LinuxKeyVaule menjadiKeyValue (#14087)
* Deskripsi konfigurasi pemeliharaan @kukislav sql mi (#14216)
* @webguynj, Perbarui Set-AzNetworkSecurityRuleConfig.md (#14176)
* Yannick Dils ( ), Menambahkan cmdline tambahan ke contoh yang menerapkan perubahan ke @yannickdils penyeimbang muat (#14185)

## <a name="550---february-2021"></a>5.5.0 - Februari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Kode CloudError Terlacak dalam pengecualian
* Kejadian 'ContextCleared' yang dinaikkan ketika 'Clear-AzContext' dijalankan

#### <a name="azaks"></a>Az.Aks
* Pesan kesalahan yang disempurnakan dari kegagalan cmdlet.
* Melakukan peningkatan penanganan pengecualian untuk Azure PowerShell pengecualian terkait.
* Memperbaiki masalah pengguna tidak dapat menggunakan prinsipal layanan yang disediakan untuk membuat kluster Kjadwal. [#13938]

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
* Menambahkan parameter '-RentetanEnabled' ke 'New-AzDiskConfig' dan 'New-AzDiskUpdateConfig'
* Menambahkan parameter '-GroupByApplicationId' dan '-GroupByUserAgent' ke cmdlet 'Export-AzLogAnalyticThrottledRequest' dan 'Export-AzLogAnalyticRequestRateByInterval'.
* Menambahkan parameter 'VMParameterSet' diatur ke cmdlet 'Get-AzVMExtension'. Menambahkan parameter baru '-VM' ke kumpulan parameter ini.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Menambahkan cmdlet ke operasi repositori, manifes, dan tag yang didukung:
    - 'Get-AzContainerRegistryRepository'
    - 'Update-AzContainerRegistryRepository'
    - 'Remove-AzContainerRegistryRepository'
    - 'Get-AzContainerRegistryFestfest'
    - 'Update-AzContainerRegistryFestfest'
    - 'Remove-AzContainerRegistryFestfest'
    - 'Get-AzContainerRegistryTag'
    - 'Update-AzContainerRegistryTag'
    - 'Remove-AzContainerRegistryTag'

#### <a name="azdatabricks"></a>Az.Databricks
Didukung -EnableNoPublicIP saat membuat ruang kerja Databricks

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan FrontDoorId ke properti
* Menambahkan pengecualian JSON dan dukungan Request BodyCheck untuk aturan terkelola

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan parameter baru '-EnableComputeIsolation' dan '-ComputeIsolationHostSku' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur hitung isolation
* Properti tambahan 'ComputeIsolationProperties' dan 'ConnectivityEndpoints' di kelas AzureHDInsightCluster.

#### <a name="azkeyvault"></a>Az.KeyVault
* Didukung untuk menentukan tipe kunci dan nama kurva ketika mengimpor kunci melalui file BYOK

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk mengganti nama produk lama 'router virtual' dengan nama baru 'server rute' di masa mendatang.
    - 'New-AzRouteServer'
    - 'Get-AzRouteServer'
    - 'Remove-AzRouteServer'
    - 'Update-AzRouteServer'
    - 'Get-AzRouteServerPeer'
    - 'Add-AzRouteServerPeer'
    - 'Update-AzRouteServerPeer'
    - 'Remove-AzRouteServerPeer'
    - Menambahkan peringatan atribut penghentian ke cmdlet yang lama.
* Perbaikan bug di ExpressRouteLink MacSecConfig. Menambahkan properti baru 'SciState' ke 'PSExpressRouteLinkMacSecConfig'
* Memformat daftar dan memformat tampilan tabel untuk Get-AzVirtualNetworkGatewayConnectionIkeSa

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Perubahan yang dibuat di powershell yang ditambahi batas baris permintaan. Menghapus pernyataan yang salah untuk halaman pendukung

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* batasan validasi kebijakan yang dimodifikasi sesuai dengan layanan pencadangan.
* Kelebihan Zona yang Ditambahkan untuk Vault Layanan Pemulihan.
* Dukungan Pemulihan Situs Azure untuk grup penempatan Kedekatan untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk zona Ketersediaan untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk UseManagedDisk untuk HyperV ke penyedia Azure

#### <a name="azresources"></a>Az.Resources
* Tipe pokok yang dihapus New-AzRoleAssignment dan Set-AzRoleAssignment karena pemetaan saat ini memutus skenario tertentu

#### <a name="azsql"></a>az.sql
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlElasticPool' dan 'Set-AzSqlElasticPool'
* Regresi diperbaiki dalam 'Set-AzSqlServerAudit' ketika argumen PredicateExpression disediakan

#### <a name="azstorage"></a>Az.Storage
* Pengaturan RoutingPreference yang Didukung di buat/perbarui Storage saya
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Telah meningkatkan Azure. Storage. Blob ke 12.8.0
* Telah meningkatkan Azure. Storage. Files.Shares to 12.6.0
* Telah meningkatkan Azure. Storage. Files.DataLake to 12.6.0

#### <a name="azwebsites"></a>Situs Web Az.
* Menambahkan dukungan untuk Mengimpor sertifikat kunci vault ke WebApp.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Perbarui Set-AzEventHub.md (#13921)
* Meister Bergmeister [MVP] ( @bergmeister ), Set-AzDataLakeGen2AclRecursive.md - Fix typo (directiry -> directory) (#14082)
* Fix broken @devdeer-alex link to contribution guidelines (#14009)
* @JiangYuchun, Perbarui Get-AzApplicationGatewayAuthenticationCertificate.md (#13972)
* Sebastian Olsen ( @Spacebjorn ), Perintah contoh yang diperbaiki (#13901)

## <a name="540---january-2021"></a>5.4.0 - Januari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Diperlihatkan id permintaan klien yang benar pada pesan debug [#13745]
* Tipe pengecualian Azure PowerShell umum yang ditambahkan
* API penyimpanan yang didukung 2019-06-01

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah deskripsi yang tidak diisi untuk jadwal manajemen pembaruan

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Ketersediaan umum modul 'Az.CosmosDB'
* Membatasi New-AzCosmosDBAccount cmdlet untuk melakukan panggilan pembaruan ke Akun Database yang sudah ada.
* Memperkenalkan AnalyticalStorageTTL di SqlContainer.

#### <a name="aziothub"></a>Az.IotHub
* Memperbaiki regresi terkait pembuatan token SAS

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki masalah dalam modul Manajemen Rahasia

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki masalah 'Get-AzLogicAppTriggerHistory' dan 'Get-AzLogicAppRunAction' yang hanya mengambil halaman pertama hasil [#9141]

#### <a name="azmonitor"></a>Az.Monitor
* Cmdlet yang ditambahkan untuk aturan pengumpulan data:
    - 'Get-AzDataCollectionRule'
    - 'New-AzDataCollectionRule'
    - 'Set-AzDataCollectionRule'
    - 'Update-AzDataCollectionRule'
    - 'Remove-AzDataCollectionRule'
* Cmdlet untuk asosiasi aturan pengumpulan data ditambahkan
    - 'Get-AzDataCollectionRuleAssociation'
    - 'New-AzDataCollectionRuleAssociation'
    - 'Remove-AzDataCollectionRuleAssociation'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk CRUD VpnGatewayNATRule.
    - 'New-AzVpnGatewayNatRule'
    - 'Update-AzVpnGatewayNatRule'
    - 'Get-AzVpnGatewayNatRule'
    - 'Remove-AzVpnGatewayNatRule'
* Cmdlet yang diperbarui untuk mengatur NATRule di sumber daya VpnGateway dan mengaitkannya dengan sumber daya VpnSiteLinkConnection.
    - 'New-AzVpnGateway'
    - 'Update-AzVpnGateway'
    - 'New-AzVpnSiteLinkConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan ConnectionMode pada Virtual Network Gateway Connections.
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Cmdlet 'New-AzFirewallPolicyApplicationRule':
    - Parameter tambahan TargetUrl
    - Parameter yang ditambahkan TerminateTLS
* Menambahkan cmdlet baru untuk Azure Firewall Premium Features
    - 'New-AzFirewallPolicyIntrusionDetection'
    - 'New-AzFirewallPolicyIntrusionDetectionBypassTraffic'
    - 'New-AzFirewallPolicyIntrusionDetectionSignatureOverride'
* Cmdlet New-AzFirewallPolicy yang diperbarui:
    - Parameter yang ditambahkan -SkuTier
    - Parameter yang ditambahkan -Identity
    - Parameter yang ditambahkan -UserAssignedIdentityId
    - Parameter yang ditambahkan -IntrusionDetection
    - Parameter yang ditambahkan -TransportSecurityName
    - Parameter yang ditambahkan -TransportSecurityKeyVaultSecretId
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Gateway Jaringan Virtual.
    - 'Get-AzVirtualNetworkGatewayConnectionIkeSa'
* Menambahkan beberapa dukungan Autentikasi untuk p2sVpnGateway
    - Pembaruan New-AzVpnServerConfiguration dan Update-AzVpnServerConfiguration untuk memperbolehkan beberapa parameter autentikasi diatur.
* Diperbarui cmdlet 'New-AzVpnGateway' dan 'New-AzP2sVpnGateway':
    - Parameter tambahan EnableRoutingPreferenceInternetFlag

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Fitur Pulihkan Lintas Wilayah ditambahkan.
* Konfigurasi beban kerja terblokal bila item target adalah grup ketersediaan.

#### <a name="azresources"></a>Az.Resources
* Penambahan dukungan untuk parameter -QueryString dalam cmdlet New-Az*Deployments

#### <a name="azsql"></a>az.sql
* Cmdlet 'Start-AzSqlInstanceDatabaseLogReplay' asinkron, ditambahkan -AsJob flag

#### <a name="azstorage"></a>Az.Storage
* Fix ContinuationToken never null when list blob with -IncludeVersion
    - 'Get-AzStorageBlob'

#### <a name="azwebsites"></a>Situs Web Az.
* Menambahkan dukungan untuk sertifikat yang Dikelola Layanan Aplikasi
    - 'New-AzWebAppCertificate'
    - 'Remove-AzWebAppCertificate'
* Memperbaiki masalah yang menyebabkan Kata Sandi Docker dihapus dari appsettings di 'Set-AzWebApp' dan 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Lv Akcheurov ( @ivanakcheurov ), Update Set-AzSecurityWorkspaceSetting.md (#13877)
* @javiermarasco, Contoh pembaruan (#13837)
* @jhaprakash26, Perbarui Set-AzVirtualNetwork.md (#13857)
* MichaelUpdate ( @MichaelHolmesWP ), Update New-AzStorageTableStoredAccessPolicy.md (#13871)
* Michael James ( ), Perbolehkan Get-AzLogicAppTriggerHistory dan Get-AzLogicAppRunAction untuk mengembalikan lebih dari @mikejwhat 30 hasil (#13846)
* @Willem-J-an, Perbaiki bug yang menyebabkan Kata Sandi Docker dihapus dari appsettings di Set-AzWebApp(Slot) (#13866)

## <a name="530---december-2020"></a>5.3.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah proksi Http yang tidak dihargai dalam Windows PowerShell [#13647]
* Log debug operasi panjang yang ditingkatkan dalam modul yang dihasilkan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah parameter 'Start-AzAutomationRunbook' tidak dapat mengonversi string yang dibungkus PSObject menjadi string JSON [#13240]
* Completer lokasi tetap untuk New-AzAutomationUpdateManagementAzureQuery cmdlet

#### <a name="azcompute"></a>Az.Compute
* Parameter baru 'VM' dalam kumpulan parameter baru 'VMParameterSet' ditambahkan ke cmdlet 'Get-AzVMDscExtensionStatus' dan 'Get-AzVMDscExtension'.

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki masalah yang mungkin menyebabkan 'New-AzDatabricksVNetPeering' untuk dikembalikan sebelum sepenuhnya disediakan (https://github.com/Azure/autorest.powershell/issues/610)

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki perintah 'Invoke-AzDataFactoryV2Pipeline' untuk SupportsShouldProcess masalah

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan properti StartVMOnConnect ke hostpool.

#### <a name="azhdinsight"></a>Az.HDInsight
* Properti yang ditambahkan: Fqdn dan EffectiveDiskEncryptionKeyUrl di kelas AzureHDInsightHostInfo.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan parameter baru '-AsPlainText' ke 'Get-AzKeyVaultSecret' untuk langsung mengembalikan rahasia tersebut dalam teks biasa [#13630]
* Mendukung pemulihan selektif kunci dari pencadangan penuh HSM terkelola [#13526]
* Memperbaiki beberapa masalah minor [#13583] [#13584]
* Menambahkan objek pengembalian yang hilang dari 'Get-Secret' di modul SecretManagement
* Memperbaiki masalah yang mungkin menyebabkan vault dibuat tanpa kebijakan akses default [#13687]

#### <a name="azkusto"></a>Az.Kusto
* Memperbarui versi API ke 2020-09-18.

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki masalah dalam skenario remove peering and connection cmdlet for ExpressRouteCircuit
    - 'Remove-AzExpressRouteCircuitPeeringConfig' dan 'Remove-AzExpressRouteCircuitConnectionConfig'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan dukungan untuk mengembalikan hasil penomoran untuk Get-AzPolicyState

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Fitur softdelete yang diaktifkan untuk SQL.
* Memperbaiki SQL ag memulihkan dan menghapus pemeriksaan nama wadah.
* Format nama kontainer yang diubah untuk item cadangan File Azure.
* Menambahkan dukungan fitur CMK untuk vault layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Perbaikan masalah pengecualian NullRef dalam 'New-AzureManagedApplication' dan 'Set-AzureManagedApplication'.
* Memperbarui SDK Azure Resource Manager agar menggunakan versi api GA DeploymentScripts terbaru: 2020-10-01.

#### <a name="azservicefabric"></a>az.servicefabric
* Memperbaiki 'Add-AzServiceFabricNodeType'. Tipe node yang ditambahkan ke kluster kain layanan sebelum membuat kumpulan skala mesin virtual.

#### <a name="azsql"></a>az.sql
* Deskripsi parameter tetap untuk perintah 'InstanceFailoverGroup'.
* Memperbarui logika di skemaName, nama tabel, dan columnName yang diekstrak dari id SQL Klasifikasi Data.
* Memperbaiki Status dan StatusPesanan bidang di 'Get-AzSqlDatabaseImportExportStatus' agar sesuai dengan dokumentasi
* Menambahkan cmdlet audit operasi dukungan Microsoft (DevOps): Get-AzSqlServerMSSupportAudit, Set-AzSqlServerMSSupportAudit, Remove-AzSqlServerMSSupportAudit

#### <a name="azstorage"></a>Az.Storage
* EnkripsiScope buat/perbarui/dapatkan/daftar yang didukung dari Storage pengguna
    - 'New-AzStorageEncryptionScope'
    - 'Update-AzStorageEncryptionScope'
    - 'Get-AzStorageEncryptionScope'
* Didukung buat wadah dan unggah blob dengan pengaturan Lingkup Enkripsi
    - 'New-AzRmStorageContainer'
    - 'New-AzStorageContainer'
    - 'Set-AzStorageBlobContent'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andreas Wolter ( @AndreasWolter ), menghapus bahasa pemasaran, filter contoh yang lebih baik (#13671)
* Tarkan Belmansour ( @BelRarr ), Pembaruan Get-AzBillingInvoice.md (#13634)
* David Ugatmpfner ( @DavidKlempfner )
  * Memperbaiki kesalahan ejaan (#13677)
  * Memperbarui PSMetricNoDetails.cs (#13676)
* @kilobyte97, bugfix for remove cmdlet to delete config (#13655)
* @kongou-ae, Perbarui Set-AzFirewall.md (#13727)
* @MasterKuat, Memperbaiki tukar antara judul dan kode dalam dokumentasi (#13666)
* NickT ( @nukeulis ), Perbarui Set-AzContext.md (#13702)
* @PaulHCode, Perbarui Start-AzJitNetworkAccessPolicy.md - Perbaiki Contoh untuk menampilkan cmdlet yang tepat yang ditunjukkan (#13713)
* Ryan Borstelmann ( @ryanborMSFT ), ID Langganan Dihapus (#13715)
* Shashikant Shakya ( @shshakya ), Pembaruan Set-AzSqlDatabase.md (#13674)
* Sebastian Olsen ( @Spacebjorn ), Pembaruan Get-AzRecoveryServicesBackupItem.md (#13719)

## <a name="520---december-2020"></a>5.2.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Dikelola untuk menguraikan waktu KedaluwarsaOn dari token mentah jika tidak bisa masuk ke pustaka dasar
* Pesan peringatan yang ditingkatkan jika autentikasi Interaktif tidak tersedia

#### <a name="azapimanagement"></a>Az.ApiManagement
* [Perubahan pecah] 'New-AzApiManagementProduct' secara default tidak memiliki batas langganan.

#### <a name="azcompute"></a>Az.Compute
* Pengeditan Get-AzVm untuk memfilter menurut '-Nama' sebelum memeriksa pembatasan karena terlalu banyak sumber daya.
* Cmdlet baru 'Start-AzVmssRollingExtensionUpgrade'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Parameter yang didukung 'Nama' untuk dan nilai dari input saluran untuk 'Get-AzContainerRegistryUsage' [#13605]
* Pengecualian yang lebih halus untuk 'Koneksi-AzContainerRegistry'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.13.0

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Dukungan tambahan untuk kunci terkelola pelanggan

#### <a name="aziothub"></a>Az.IotHub
* Memperbaiki masalah token SAS.

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung 'semua' sebagai opsi saat mengatur kebijakan akses kunci vault
* Versi baru modul SecretManagement yang didukung [#13366]
* Didukung ByteArray, String, PSCredential dan Hashtable untuk 'SecretValue' di SecretManagementModule [#12190]
* [Breaking change] redesigned the API surface of cmdlets related to managed HSM.

#### <a name="azmonitor"></a>Az.Monitor
* Parameter yang diubah 'Rule' dari 'New-AzAutoscaleProfile' untuk menerima daftar kosong. [#12903]
* Menambahkan cmdlet baru untuk mendukung pembuatan pengaturan diagnostik lebih fleksibel:
    * 'Get-AzDiagnosticSettingCategory'
    * 'New-AzDiagnosticSetting'
    * 'New-AzDiagnosticDetailSetting'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Buat perubahan nama teks bantuan dan parameter pada cmdlet 'Restore-AzRecoveryServicesBackupItem'.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan parameter '-Tag' ke 'Set-AzTemplateSpec' dan 'New-AzTemplateSpec'
* Menambahkan dukungan tampilan Tag ke formatter default untuk Spesifikasi Templat

#### <a name="azservicefabric"></a>az.servicefabric
* Contoh yang ditambahkan untuk 'Set-AzServiceFabricSetting' dengan SettingsSectionDescription param
* Cmdlet terkait aplikasi yang diperbarui untuk mencari tahu bahwa dukungan hanya untuk sumber daya arm yang disebarkan
* Ditandai untuk cmdlet sertifikat kluster penghentian 'Add-AzureRmServiceFabricClusterCertificate' dan 'Remove-AzureRmServiceFabricClusterCertificate'

#### <a name="azsql"></a>az.sql
* Menambahkan SecondaryType ke yang berikut ini:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
    - 'New-AzSqlDatabaseSecbasery'
* Ditambahkan HighAvailabilityReplicaCount ke yang berikut ini:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
* Made ReadReplicaCount an alias of HighAvailabilityReplicaCount in the following:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'

#### <a name="azstorage"></a>Az.Storage
* Unggah ukuran File Azure hingga 4 TiB yang didukung
    - 'Set-AzStorageFileContent'
* Telah meningkatkan Azure. Storage. Blob ke 12.7.0
* Telah meningkatkan Azure. Storage. Files.Shares to 12.5.0
* Telah meningkatkan Azure. Storage. Files.DataLake to 12.5.0

#### <a name="azstoragesync"></a>Az.StorageSync
* Fitur kebijakan tingkatan Sinkronisasi ditambahkan dengan kebijakan unduhan dan mode cache lokal

#### <a name="azwebsites"></a>Situs Web Az.
* Mencegah aturan pembatasan akses duplikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Dawson ( ), Perbarui Get-AzKeyVaultCertificate.md - Dapatkan sertifikat dan simpan sebagai bagian pfx untuk bekerja dengan @dawsonar802 PowerShell Core (#13557)
* @iviark, Pembaruan BYOK Powershell Layanan Kesehatan (#13518)
* John Bebekmanton ( @johnduckmanton ), Mengoreksi ejaan TagPatchOperation (#13508)
* Michael James ( @mikejwhat )
  * Get-AzLogicAppRunHistory Bantuan Merapikan (#13513)
* Richard de Z slow ( @mountain65 )
  * Memperbarui Update-AzAppConfigurationStore.md (#13485)
  * Memperbarui New-AzCosmosDBAccount.md (#13490)
* @SteppingRazor, New-AzApiManagementProduct: Change SubscriptionsLimit parameter default value to None (#13457)
* Steve Burkett ( @SteveBurkettNZ ), Fix Typo for WorkspaceResourceId parameter dalam contoh (#13589)

## <a name="510---november-2020"></a>5.1.0 - November 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah tenantId yang mungkin tidak dihargai jika menggunakan 'Koneksi-AzAccount -DeviceCode'[#13477]
* Menambahkan cmdlet baru 'Get-AzAccessToken'
* Memperbaiki masalah yang terjadi jika jalur profil pengguna tidak dapat diakses
* Memperbaiki masalah yang Write-Object saat terjadi Connect-AzAccount [#13419]
* Parameter yang ditambahkan 'ContainerRegistryEndpointFix' menjadi: 'Add-AzEnvironment', 'Set-AzEnvironment'
* Menyela masuk yang didukung dengan menekan <kbd>CTRL</kbd> + <kbd>C</kbd>
* Memperbaiki masalah yang menyebabkan 'Koneksi-AzAccount -KeyVaultAccessToken' tidak berfungsi [#13127]
* Referensi null dan kasus metode insensitive di 'Invoke-AzMethod'

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah yang tidak dapat digunakan prinsipal layanan untuk membuat kluster Kluster Baru. [#13012]

#### <a name="azappconfiguration"></a>Az.AppConfiguration
* Ketersediaan umum modul 'Az.AppConfiguration'

#### <a name="azdatafactory"></a>Az.DataFactory
* Pesan kesalahan yang ditingkatkan dari perintah 'New-AzDataFactoryV2LinkedServiceEncryptedCredential'

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui SDK dataplane ADLS ke 1.2.4-alpha. Perubahan:https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-124-alpha

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan cmdlet Paket MSIX baru dan cmdlet Aplikasi yang diperbarui.

#### <a name="azeventhub"></a>Az.EventHub
* Perintah Kluster tetap untuk kluster EventHub tanpa tag
* Memperbarui teks bantuan untuk PartnerNamespace dari AzEventHubGeoDRConfiguration commands

#### <a name="azhdinsight"></a>Az.HDInsight
* Tambahkan parameter 'ResourceProviderConnection' dan 'PrivateLink' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur relay tautan keluar dan pribadi
* Menambahkan parameter 'AmbariDatabase' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur database Ambari kustom
* Tambahkan nilai terima 'AmbariDatabase' ke parameter 'MetastoreType' cmdlet 'Add-AzHDInsightMetastore'

#### <a name="aziothub"></a>Az.IotHub
* Tag yang diperbolehkan dalam Hub IoT membuat cmdlet.

#### <a name="azkeyvault"></a>Az.KeyVault
* Tag pembaruan kunci vault yang didukung

#### <a name="azlogicapp"></a>Az.LogicApp
* Diperbaiki untuk Get-AzLogicAppRunHistory hanya mengambil halaman pertama hasil

#### <a name="aznetwork"></a>Az.Network
* Diperbarui di bawah cmdlet
    - 'New-AzLoadBalancerFrontIpConfigCommand', 'Set-AzLoadBalancerFrontendIpConfigCommand', 'Add-AzLoadBalancerFrontendIpConfigCommand':
        - Properti Added PublicIpAddressPrefix
        - Properti PublicIpAddressPrefixId ditambahkan
* Menambahkan properti baru ke cmdlet berikut untuk memungkinkan penyeimbangan muat global
    - 'New-AzLoadBalancer':
        - Properti Sku Tier yang ditambahkan
    - 'New-AzPuplicIpAddress':
        - Properti Sku Tier yang ditambahkan
    - 'New-AzPublicIpPrefix':
        - Properti Sku Tier yang ditambahkan
    - 'New-AzLoadBalancerBackendAddressConfig':
        - Properti LoadBalancerFrontendIPConfigurationId ditambahkan
* Rencana yang diperbarui untuk menghapus peringatan untuk cmdlet berikut -'New-AzVirtualHubRoute' -'New-AzVirtualHubRouteTable' -'Add-AzVirtualHubRoute' -'Add-AzVirtualHubRouteTable' -'Get-AzVirtualHubRouteTable' -'Remove-AzVirtualHubRouteTable'
* Ditambahkan perencanaan untuk penghentian peringatan pada argumen 'RouteTable' untuk cmdlet berikut -'New-AzVirtualHub' -'Set-AzVirtualHub' -'Update-AzVirtualHub'
* Membuat argumen '-MinScaleUnits' dan '-MaxScaleUnits' opsional dalam 'Set-AzExpressRouteGateway'
* Menambahkan cmdlet baru untuk mendukung Autentikasi Bersama dan Profil SSL pada Gateway Aplikasi
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
* Menentukan kebijakan BackupTime berada dalam UTC.
* Memodifikasi peringatan perubahan pecah di Get-AzRecoveryServicesBackupJobDetails cmdlet.
* Memperbarui contoh teks bantuan skrip Set-AzRecoveryServicesBackupProtectionPolicy cmdlet.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah ketika What-If memperlihatkan dua lingkup grup sumber daya dengan casing berbeda
* Memperbarui 'Export-AzResourceGroup' untuk menggunakan SDK.
* Informasi budaya yang ditambahkan untuk menguraikan metode

#### <a name="azsql"></a>az.sql
* Memperbaiki masalah Set-AzSqlDatabaseAudit tidak mendukung database Hyperscale dan edisi database tidak dapat ditentukan
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Memperbaiki bug di GetAzureSqlDatabaseReplicationLink.cs tempat parameter PartnerServerName diperiksa menurut nilai, bukan kunci

#### <a name="azwebsites"></a>Situs Web Az.
* Dukungan tambahan untuk fitur batasan akses yang baru: ServiceTag, multi-ip, dan http-header

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* John Q. Martin ( @johnmart82 ), Menambahkan informasi prasyarat firewall (#13385)
* Manikandan Manipulasiisamy ( @madurais-msft ), Mengoreksi argumen PublicSubnetName (#13417)
* @mahortas, Pembaruan untuk nilai parameter -HostNames (#13349)
* @MariachiForHire, menambahkan nilai TrafficAnalyticsInterval yang didukung (#13304)
* Michael James ( @mikejwhat ), Perbolehkan Get-AzLogicAppRunHistory untuk mengembalikan lebih dari 30 entri (#13393)
* Shashikant Shakya ( @shshakya ), Pembaruan Restore-AzSqlInstanceDatabase.md (#13404)

## <a name="500---october-2020"></a>5.0.0 - Oktober 2020
#### <a name="azaccounts"></a>Az.Accounts
* [Breaking Change] Menghapus 'Get-AzProfile' dan 'Select-AzProfile'
* Mengganti Pustaka Autentikasi Azure Directory dengan Pustaka Autentikasi Microsoft(MSAL)

#### <a name="azaks"></a>Az.Aks
* [Breaking Change] Alias parameter yang dihapus 'ClientIdAndSecret' dalam 'New-AzAksCluster' dan 'Set-AzAksCluster'.
* [Breaking Change] Mengubah nilai default 'NodeVmSetType' di 'New-AzAksCluster' dari 'AvailabilitySet' menjadi 'VirtualMachineScaleSets'.
* [Breaking Change] Mengubah nilai default 'NetworkPlugin' dalam 'New-AzAksCluster' dari 'None' menjadi 'azure'.
* [Breaking Change] Parameter yang dihapus 'NodeOsType' di 'New-AzAksCluster' karena hanya mendukung satu nilai Linux.

#### <a name="azbilling"></a>Az.Billing
* Cmdlet 'Get-AzBillingAccount' ditambahkan
* Cmdlet 'Get-AzBillingProfile' ditambahkan
* Cmdlet 'Get-AzInvoiceSection' ditambahkan
* Menambahkan parameter baru dalam cmdlet 'Get-AzBillingInvoice'
* Properti yang dihapus DownloadUrlExpiry, Type, BillingPeriodNames dari respons Get-AzBillingInvoice cmdlet

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung fungsionalitas tautan multi-origin dan privat

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* SDK yang diperbarui ke pratinjau 7.4.0.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-VmssId' ke 'New-AzVm'
* Menambahkan parameter 'PlatformFaultDomainCount' ke cmdlet 'New-AzVmss'.
* Cmdlet baru 'Get-AzDiskEncryptionSetAssociatedResource'
* Menambahkan parameter opsional 'Tier' dan 'LogicalSectorSize' pada New-AzDiskConfig cmdlet.
* Ditambahkan dengan 'Tier', 'MaxSharesCount', 'DiskIOPSReadOnly', dan 'DiskMBpsReadOnly' pada cmdlet 'New-AzDiskUpdateConfig'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* [Breaking Change] Memperbarui versi API ke 01-05-2019
* [Breaking Change] SKU yang dihapus 'Klasik' dan parameter 'StorageAccountName' dari 'New-AzContainerRegistry'
* Cmdlet baru yang ditambahkan: 'Koneksi-AzContainerRegistry', 'Import-AzContainerRegistry', 'Get-AzContainerRegistryUsage', 'New-AzContainerRegistryNetworkRule', 'Set-AzContainerRegistryNetworkRule'
* Menambahkan parameter baru 'NetworkRuleSet' ke 'Update-AzContainerRegistry'

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki bug yang mungkin menyebabkan pembaruan ruang kerja berdata tanpa `-EncryptionKeyVersion` gagal.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 4.12.0
* Memperbarui versi SDK klien enkripsi ADF ke versi 4.14.7587.7
* Menambahkan perintah 'Stop-AzDataFactoryV2TriggerRun' dan 'Invoke-AzDataFactoryV2TriggerRun'

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Memerlukan properti Lokasi untuk membuat objek arm tingkat atas.
        * Made `ApplicationGroupType` required for `New-AzWvdApplicationGroup` .
        * Made `HostPoolArmPath` required for `New-AzWvdApplicationGroup` .
        * Ditambahkan `PreferredAppGroupType` untuk `New-AzWvdHostPool` .

#### <a name="azfunctions"></a>Az.Functions
* [Breaking Change] Menghapus parameter sakelar 'IncludeSlot' dari semua parameter selain satu kumpulan parameter 'Get-AzFunctionApp'. Cmdlet kini mendukung pengambilan slot penyebaran di hasil ketika '-IncludeSlot' ditentukan.
* Diperbarui 'New-AzFunctionApp':
  - Fixed -DisableApplicationInsights sehingga tidak ada proyek wawasan aplikasi yang dibuat saat opsi ini ditentukan. [#12728]
  - [Breaking Change] Menghapus dukungan untuk membuat aplikasi fungsi PowerShell 6.2.
  - [Breaking Change] Mengubah versi runtime default dalam Functions versi 3 di Windows untuk aplikasi fungsi PowerShell dari 6.2 menjadi 7.0 saat parameter RuntimeVersion tidak ditentukan.
  - [Breaking Change] Mengubah versi runtime default dalam Functions versi 3 di Windows dan Linux untuk aplikasi fungsi Node dari 10 menjadi 12 ketika parameter RuntimeVersion tidak ditentukan.
  - [Breaking Change] Mengubah versi runtime default dalam Functions versi 3 di Linux untuk aplikasi fungsi Python dari 3.7 menjadi 3.8 ketika parameter RuntimeVersion tidak ditentukan.

#### <a name="azhdinsight"></a>Az.HDInsight
 * Untuk New-AzHDInsightCluster cmdlet:
     - Parameter yang diganti 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
     - Parameter yang diganti 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
     - Parameter yang diganti 'DefaultStorageAccountType' dengan 'StorageAccountType'
     - Menghapus parameter 'PublicNetworkAccessType'
     - Parameter yang dihapus 'OutboundPublicNetworkAccessType'
     - Menambahkan parameter baru: 'StorageFileSystem' dan 'StorageAccountManagedIdentity' untuk mendukung ADLSGen2
     - Menambahkan parameter baru 'EnableIDBroker' ke Support HDInsight ID Broker
     - Ditambahkan parameter baru: 'PrioritasKaClientGroupId', 'KursorkaClientGroupName' dan 'KursorkaManagementNodeSize' untuk mendukung Proksi Rest Andi
 * Untuk New-AzHDInsightClusterConfig cmdlet:
     - Parameter yang diganti 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
     - Parameter yang diganti 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
     - Parameter yang diganti 'DefaultStorageAccountType' dengan 'StorageAccountType'
     - Menghapus parameter 'PublicNetworkAccessType'
     - Parameter yang dihapus 'OutboundPublicNetworkAccessType'
* Untuk Set-AzHDInsightDefaultStorage cmdlet:
    - Parameter yang diganti 'StorageAccountName' dengan 'StorageAccountResourceId'
* Untuk Add-AzHDInsightSecurityProfile cmdlet:
    - Parameter yang diganti 'Domain' dengan 'DomainResourceId'
    - Menghapus persyaratan wajib untuk parameter 'OrganizationalUnitDN'

#### <a name="azkeyvault"></a>Az.KeyVault
* [Breaking Change] Parameter sudah tidak berlaku DisableSoftDelete dalam 'New-AzKeyVault' dan EnableSoftDelete dalam 'Update-AzKeyVault'
* [Breaking Change] Atribut yang dihapus SecretValueText untuk menghindari menampilkan SecretValue secara langsung [#12266]
* Tipe sumber daya baru yang didukung: HSM terkelola
    - CRUD dari HSM terkelola dan cmdlet untuk mengoperasikan kunci di HSM terkelola
    - Pencadangan/pemulihan HSM penuh, pembuatan kunci AES, pencadangan/pemulihan domain keamanan, RBAC

#### <a name="azmanagedservices"></a>Az.ManagedServices
* [Breaking Change] Pembaruan parameter konvensi penamaan dan contoh terkait

#### <a name="aznetwork"></a>Az.Network
* [Breaking Change] Parameter yang dihapus 'HostedSubnet' dan menambahkan 'Subnet' sebagai gantinya
* Menambahkan cmdlet baru untuk Rute Peer Router Virtual
    - 'Get-AzVirtualRouterPeerLearnedRoute'
    - 'Get-AzVirtualRouterPeerAdvertisedRoute'
* Cmdlet New-AzFirewall yang diperbarui:
    - Parameter yang ditambahkan '-SkuTier'
    - Parameter yang ditambahkan '-SkuName' dan membuat Sku sebagai Alias untuk ini
    - Menghapus parameter '-Sku'
* [Breaking Change] Argumen 'Connectionlink' dibuat wajib dalam 'Start-AzVpnConnectionPacketCapture' dan 'Stop-AzVpnConnectionPacketCapture'
* [Breaking Change] Memperbarui 'New-AzNetworkWatcherConnectionMonitorEndPointObject' untuk menghapus parameter '-Filter'
* [Breaking Change] Menggantikan cmdlet 'New-AzNetworkWatcherConnectionMonitorEndpointFilterItemObject' dengan 'New-AzNetworkWatcherConnectionMonitorEndpointScopeItemObject'
* Cmdlet 'New-AzNetworkWatcherConnectionMonitorEndPointObject':
    - Parameter yang ditambahkan '-Tipe'
    - Parameter yang ditambahkan '-CakupanLevel'
    - Parameter tambahan '-Lingkup'
* Memperbarui cmdlet 'New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject' dengan parameter baru '-DestinationPortBe cmdletior'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Pemulihan Beban Kerja untuk izin kontributor.
* Menambahkan kumpulan parameter baru dan validasi untuk Restore-AzRecoveryServicesBackupItem cmdlet.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug penguraian
* Cmdlets What-If templat ARM yang diperbarui untuk menghapus pesan pratinjau dari hasil
* Memperbaiki masalah ketika cmdlet penyebaran templat mengalami crash jika '-WhatIf' diatur pada lingkup yang lebih tinggi [#13038]
* Memperbaiki masalah cmdlet penyebaran templat yang tidak mempertahankan huruf besar/huruf untuk parameter templat
* Menambahkan versi API default yang akan digunakan dalam cmdlet 'Export-AzResourceGroup'
* Cmdlet untuk Spesifikasi Templat ditambahkan ('Get-AzTemplateSpec', 'Set-AzTemplateSpec', 'New-AzTemplateSpec', 'Remove-AzTemplateSpec', 'Export-AzTemplateSpec')
* Menambahkan dukungan untuk menyebarkan Spesifikasi Templat menggunakan cmdlet penyebaran yang sudah ada (melalui parameter baru -TemplateSpecId)
* Memperbarui 'Get-AzResourceGroupDeploymentOperation' untuk menggunakan SDK.
* Menghapus parameter '-ApiVersion' dari cmdlet '*-AzDeployment'.

#### <a name="azsql"></a>az.sql
* Memperbaiki masalah ketika New-AzSqlDatabaseExport jika networkIsolation tidak ditentukan [#13097]
* Memperbaiki masalah ketika New-AzSqlDatabaseExport lalu New-AzSqlDatabaseImport tidak mengembalikan OperationStatusLink dalam objek hasil [#13097]
* URL Perbarui Wilayah Azure yang Dipasangkan dalam Peringatan Kelebihan Storage Cadangan

#### <a name="azstorage"></a>Az.Storage
* Menghapus properti yang sudah tidak t fungsi RestorePolicy.LastEnabledTime
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Get-AzStorageBlobServiceProperty'
    - 'Update-AzStorageBlobServiceProperty'
* Ubah Tipe HariAfterModificationGreaterTerTerter dari int menjadi int?
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyRule'
* Berbagi file buat/perbarui yang didukung dengan tingkat akses
    - 'New-AzRmStorageShare'
    - 'Update-AzRmStorageShare'
* Set/update/remove Acl yang didukung secara berulang pada item Datalake Gen2
    -  'Set-AzDataLakeGen2AclRecursive'
    -  'Update-AzDataLakeGen2AclRecursive'
    -  'Remove-AzDataLakeGen2AclRecursive'
* Kebijakan akses Kontainer yang Didukung dengan izin baru x,t
    -  'New-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Mengubah output cmdlet kebijakan akses Kontainer yang ditetapkan/get/set, dengan mengubah tipe izin properti anak dari enum ke String
    -  'Get-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Perbaikan contoh masalah skrip kebijakan manajemen yang ditetapkan dengan json
    -  'Set-AzStorageAccountManagementPolicy'

#### <a name="azwebsites"></a>Situs Web Az.
* Dukungan tambahan untuk Premium harga V3 tingkat
* Memperbarui WEBSites SDK ke 3.1.0

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Perbarui Get-AzDelegation.md (#13176)
* @dineshreddy007, Dapatkan Peran Aplikasi yang ditetapkan dengan benar dalam kasus pendaftaran Tumpukan HCI menggunakan token WAC. (#13249)
* @kongou-ae, Perbarui New-AzOffice365PolicyProperty.md (#13217)
* Update @Lochiluk Set-AzApplicationGateway.md (#13150)
* Matthew Bur matthew ( @mburleigh )
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13203)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13190)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13189)
  * tambahkan tautan ke cmdlet yang direferensikan (#13137)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13204)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13205)

## <a name="480---october-2020"></a>4.8.0 - Oktober 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah pemilahan DateTime di pustaka umum [#13045]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Ditambahkan cmdlet 'New-AzCognitiveServicesAccountApiProperty'.
* Parameter 'ApiProperty' yang didukung untuk 'New-AzCognitiveServicesAccount' dan 'Set-AzCognitiveServicesAccount'

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah di 'Update-ASRRecoveryPlan' dengan mengisi FailoverTypes
* Menambahkan parameter opsional '-Atas' dan '-OrderBy' ke cmdlet 'Get-AzVmImage'.

#### <a name="azdatabricks"></a>Az.Databricks
* Ketersediaan umum modul 'Az.Databricks'
* Dukungan tambahan untuk peering jaringan virtual

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki kesalahan ketik dalam pesan output

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter sakelar opsional 'TrustedServiceAccessEnabled' ke cmdlet 'Set-AzEventHubNetworkRuleSet'

#### <a name="azhdinsight"></a>Az.HDInsight
* Pesan peringatan tambahan untuk perencanaan penghentian parameter 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType'
* Pesan peringatan yang ditambahkan untuk perencanaan mengganti parameter 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
* Pesan peringatan yang ditambahkan untuk perencanaan untuk mengganti parameter 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
* Pesan peringatan yang ditambahkan untuk perencanaan mengganti parameter 'DefaultStorageAccountType' dengan 'StorageAccountType'
* Pesan peringatan yang ditambahkan untuk perencanaan untuk mengganti parameter 'DefaultStorageContainer' dengan 'StorageContainer'
* Menambahkan pesan peringatan untuk perencanaan untuk mengganti parameter 'DefaultStorageRootPath' dengan 'StorageRootPath'

#### <a name="aziothub"></a>Az.IotHub
* Sdk perangkat yang diperbarui.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menyediakan tanggal mendetail tentang menghapus properti SecretValueText

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Peringatan perubahan yang diperbarui pada cmdlet penetapan dan definisi layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Perbaikan bug yang tidak dapat menyembunyikan pesan peringatan. [#12889]
* Parameter 'SkipMetricValidation' yang didukung dalam kriteria aturan peringatan. Memungkinkan pembuatan aturan pemberitahuan pada metrik kustom yang belum diasingkan, dengan menyebabkan validasi metrik dilewati.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan Kebijakan Office365 ke Sumber Daya VpnSite
    - 'New-AzO365PolicyProperty'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Penambahan validasi nama kontainer untuk cadangan beban kerja.

#### <a name="azrediscache"></a>Az.RedisCache
* Cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache' tidak gagal karena masalah izin yang terkait dengan mendaftarkan Microsoft.Cache RP

#### <a name="azsql"></a>az.sql
* Added BackupStorageRedundancy to the following:
    - 'Restore-AzureRmSqlDatabase'
    - 'New-AzSqlDatabaseCopy'
    - 'New-AzSqlDatabaseSecbasery'
* Sensitivitas huruf besar/kecil untuk parameter cadanganSensial untuk SQL DB saya
* Nama pesan peringatan BackupStorageRedundancy diperbarui

#### <a name="azstorage"></a>Az.Storage
* Properti aktifkan/nonaktifkan/nonaktifkan/bagikan properti penghapusan sementara yang didukung pada Layanan Storage ini
    - 'Update-AzStorageFileServiceProperty'
    - 'Get-AzStorageFileServiceProperty'
* Berbagi daftar file yang didukung mencakup file yang telah dihapus dari Storage, dan Mendapatkan penggunaan berbagi satu file
    - 'Get-AzRmStorageShare'
* Memulihkan berbagi file terhapus yang didukung
    - 'Restore-AzRmStorageShare'
* Mengubah cmdlet untuk mengubah properti layanan blob, tidak akan mendapatkan properti asli dari server, tetapi hanya mengatur properti yang dimodifikasi ke server.
    - 'Enable-AzStorageBlobDeleteRetentionPolicy'
    - 'Disable-AzStorageBlobDeleteRetentionPolicy'
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Update-AzStorageBlobServiceProperty'
* Memperbaiki masalah bantuan terkait New-AzStorageAccount parameter -Nilai default Kind [#12189]
* Memperbaiki masalah dengan menambahkan contoh untuk menunjukkan cara mengatur ContentType yang benar pada unggahan blob [#12989]

## <a name="470---september-2020"></a>4.7.0 - September 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memformat pesan perubahan yang akan datang
* Memperbarui Azure.Core ke 1.4.1

#### <a name="azaks"></a>Az.Aks
* Menambahkan logika validasi parameter sisi klien untuk 'New-AzAksCluster', 'Set-AzAksCluster' dan 'New-AzAksNodePool'. [#12372]
* Dukungan tambahan untuk add-on di 'New-AzAksCluster'. [#11239]
* Cmdlet yang ditambahkan 'Enable-AzAksAddOn' dan 'Disable-AzAksAddOn' untuk add-on. [#11239]
* Parameter tambahan 'GenerateSshKey' untuk 'New-AzAksCluster'. [#12371]
* Memperbarui versi api ke 2020-06-01.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperlihatkan persyaratan hukum tambahan untuk API tertentu.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-EncryptionType' ke 'New-AzVmDiskEncryptionSetConfig'
* Cmdlet baru untuk tipe sumber daya baru: DiskAccess 'Get-AzDiskAccess', 'New-AzDiskAccess', 'Get-AzDiskAccess'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzSnapshotConfig'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzDiskConfig'
* Menambahkan properti 'PatchStatus' ke Tampilan Contoh VirtualMachine
* Menambahkan properti 'VMHealth' ke tampilan contoh mesin virtual, yang merupakan objek yang dikembalikan saat 'Get-AzVm' diminta dengan '-Status'
* Menambahkan bidang 'AssignedHost' ke tampilan contoh 'Get-AzVM' dan 'Get-AzVmss'. Bidang memperlihatkan id sumber daya instans mesin virtual
* Menambahkan parameter opsional '-SupportAutomaticPlacement' ke 'New-AzHostGroup'
* Menambahkan parameter '-HostGroupId' ke 'New-AzVm' dan 'New-AzVmss'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke versi 4.11.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet Kluster baru - 'New-AzEventHubCluster', 'Set-AzEventHubCluster', 'Get-AzEventHubCluster', 'Remove-AzEventHubCluster', 'Get-AzEventHubClustersAvailableRegions'.
* Perbaikan untuk masalah #10722 : Perbaikan untuk penetapan hak 'Dengarkan' hingga Otorisasi Hak.

#### <a name="azfunctions"></a>Az.Functions
* Menghapus kemampuan untuk membuat v2 Fungsi di wilayah yang tidak mendukungnya.
* PowerShell 6.2 yang sudah tidak berlaku lagi. Menambahkan peringatan ketika pengguna membuat aplikasi fungsi PowerShell 6.2 yang menyarankan mereka untuk membuat aplikasi fungsi PowerShell 7.0 sebagai gantinya.

#### <a name="azhdinsight"></a>Az.HDInsight
* Pembuatan kluster yang didukung dengan konfigurasi Skala Otomatis
    - Menambahkan parameter baru 'AutoscaleConfiguration' ke cmdlet 'New-AzHDInsightCluster'
* Konfigurasi Skala Otomatis kluster operasi yang didukung
    - Tambahkan cmdlet baru 'Get-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'Set-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'Remove-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleScheduleCondition'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk otorisasi RBAC [#10557]
* Penanganan kesalahan yang disempurnakan dalam 'Set-AzKeyVaultAccessPolicy' [#4007]

#### <a name="azkusto"></a>Az.Kusto
* Ketersediaan umum modul 'Az.Kusto'

#### <a name="aznetwork"></a>Az.Network
* [Breaking Change] Diperbarui di bawah cmdlet untuk meratakan perute virtual sumber daya dan hub virtual
    - 'New-AzVirtualRouter':
        - Menambahkan parameter -HostedSubnet untuk mendukung sumber daya anak konfigurasi IP
        - deleted -HostedGateway and -HostedGatewayId
    - 'Get-AzVirtualRouter':
        - Kumpulan parameter tingkat langganan yang ditambahkan
    - 'Remove-AzVirtualRouter'
    - 'Add-AzVirtualRouterPeer'
    - 'Get-AzVirtualRouterPeer'
    - 'Remove-AzVirtualRouterPeer'
* Cmdlet baru untuk Port Rute Azure Express
    - 'New-AzExpressRoutePortLOA'
* Menambahkan properti RemoteBgpCommunities ke Sumber Daya Peering VirtualNetwork
* Mengubah pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.
* Menambahkan VpnGatewayIpConfigurations ke output 'Get-AzVpnGateway'
* Memperbaiki bug 'Set-AzApplicationGatewaySsslCertificate' [#9488]
* Menambahkan parameter 'AllowActiveFTP' ke 'AzureFirewall'
* Diperbarui di bawah perintah untuk fitur: Mengaktifkan kumpulan/hapus keamanan internet di VirtualWan P2SVpnGateway.
- Diperbarui 'New-AzP2sVpnGateway': Added optional switch parameter 'EnableInternetSecurityFlag' for customers to set true to enable internet security on P2SVpnGateway, which will be applied for Point to site clients.
- Diperbarui 'Update-AzP2sVpnGateway': Added optional switch parameters 'EnableInternetSecurityFlag' atau 'DisableInternetSecurityFlag' agar pelanggan mengatur true/false untuk mengaktifkan/menonaktifkan keamanan internet di P2SVpnGateway, yang akan diterapkan untuk klien Poin ke situs.
* Ditambahkan cmdlet baru 'Reset-AzP2sVpnGateway' agar pelanggan dapat mengatur ulang/memulai ulang VirtualWan P2SVpnGateway mereka untuk pemecahan masalah.
* Menambahkan cmdlet baru 'Reset-AzVpnGateway' bagi pelanggan untuk mereset/memulai ulang VirtualWan VpnGateway mereka untuk pemecahan masalah.
* Diperbarui 'Set-AzVirtualNetworkSubnetConfig'
    - Mengatur properti NSG dan Route Table subnet to null jika secara eksplisit diatur dalam parameter [#1548][#9718]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Status Penghapusan untuk item cadangan beban kerja.

#### <a name="azresources"></a>Az.Resources
* Penambahan pemeriksaan yang hilang untuk Set-AzRoleAssignment
* Ditambahkan breaking change attribute to 'SubscriptionId' parameter of 'Get-AzResourceGroupDeploymentOperation'
* Cmdlets What-If templat ARM yang diperbarui untuk memperlihatkan perubahan sumber daya 'Abaikan' yang terakhir
* Memperbaiki masalah serialisasi parameter aman dan array untuk cmdlet penyebaran [#12773]

#### <a name="azservicefabric"></a>az.servicefabric
* Cmdlet baru yang ditambahkan untuk kluster dan tipe node yang dikelola:
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
* Upgraded Service Fabric SDK to version 1.2.0 which uses service fabric resource provider api-version 2020-03-01 for the current model and 2020-01-01-preview for managed clusters.

#### <a name="azsql"></a>az.sql
* Added BackupStorageRedundancy to 'New-AzSqlInstance' and 'Get-AzSqlInstance'
* Cmdlet yang ditambahkan 'Get-AzSqlServerActiveDirectoryOnlyAuthentication'
* Cmdlet ditambahkan 'Enable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menambahkan parameter Paksa ke 'New-AzSqlInstance'
* Cmdlet yang ditambahkan untuk layanan Pemutaran Ulang Log Database Terkelola
    - 'Start-AzSqlInstanceDatabaseLogReplay'
    - 'Get-AzSqlInstanceDatabaseLogReplay'
    - 'Complete-AzSqlInstanceDatabaseLogReplay'
    - 'Stop-AzSqlInstanceDatabaseLogReplay'
* Cmdlet tambahan 'Get-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Cmdlet ditambahkan 'Enable-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Cmdlet tambahan 'Disable-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Cmdlet yang diperbarui 'New-AzSqlDatabaseImport' dan 'New-AzSqlDatabaseExport' untuk mendukung fungsionalitas isolasi jaringan
* Cmdlet tambahan 'New-AzSqlDatabaseImportExisting'
* Cmdlet Database yang diperbarui untuk mendukung spesifikasi tipe penyimpanan cadangan
* Menambahkan parameter Paksa ke 'New-AzSqlDatabase'
* Peringatan tambahan untuk konfigurasi BackupStorageRedundancy di kawasan tertentu di 'New-AzSqlDatabase'
* Cmdlet ActiveDirectoryOnlyAuthentication yang diperbarui untuk server dan contoh untuk menyertakan ResourceId dan InputObject

#### <a name="azstorage"></a>Az.Storage
* Perbaikan kegagalan pengunggahan blob dengan memutakhirkan ke Microsoft.Azure. Storage. DataMovement 2.0.0 [#12220]
* Titik yang didukung dalam Pemulihan Waktu
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'New-AzStorageBlobRangeToRestore'
    - 'Restore-AzStorageBlobRange'
* Didukung dapatkan status pemulihan blob akun Storage dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeBlobRestoreStatus
    - 'Get-AzureRMStorageAccount'
* Pesan peringatan perubahan perubahan yang ditambahkan untuk perubahan output cmdlet yang akan datang
    - 'Get-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyRule'
* Telah meningkatkan Microsoft.Azure.Cosmos.Table SDK ke 1.0.8

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Thomas Van Laere ( @ThomVanL ), Tambahkan Dockerfile-alpine-3.10 (#12911)
* Update @Lochiluk Remove-AzNetworkInterfaceIpConfig.md (#12807)
* Roberth Strand ( @roberthstrand ), Get-AzResourceGroup - Contoh baru, dan pembersihan (#12828)
* Dropbox Mishra ( @inmishrar ), memperbarui tumpukan runtime Azure Web App ke DOTNETCORE (#12833)
* @jack-education, diperbarui Set-AzVirtualNetworkSubnetConfig mengizinkan NSG dan Route Table untuk dihapus dari subnet (#12351)
* @hagop-globanet, Perbarui Add-AzApplicationGatewayCustomError.md (#12784)
* Joshua Van Daalen ( @greenSacrifice )
  * Memperbarui ejaan Properti ke Properti (#12821)
  * Memperbarui New-AzResourceLock.md contoh (#12806)
* Eragon Riddle ( @eragonriddle ), Corrected parameter field name in the example (#12825)
* @rossifumax, Memperbaiki kesalahan ketik New-AzConfigurationAssignment.md (#12701)

## <a name="461---august-2020"></a>4.6.1 - Agustus 2020
#### <a name="azcompute"></a>Az.Compute
* Parameter '-EncryptionAtHost' Patched dalam 'New-AzVm' untuk menghapus nilai default false [#12776]

## <a name="460---august-2020"></a>4.6.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memuat semua lingkungan awan publik saat titik akhir penemuan tidak mengembalikan AzureCloud default atau lingkungan publik lainnya [#12633]
* Exposed SubscriptionPolicies dalam 'Get-AzSubscription' [#12551]

#### <a name="azautomation"></a>Az.Automation
* Menambahkan parameter '-RunOn' ke 'Set-AzAutomationWebhook' untuk menentukan Grup Pekerja Hibrid

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EncryptionAtHost' ke 'New-AzVm', 'New-AzVmss', 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVM', dan 'Update-AzVmss'
* Menambahkan 'SecurityProfile' ke 'Get-AzVM' dan 'Get-AzVmss' objek kembali
* Menambahkan sakelar '-InstanceView' sebagai parameter opsional ke 'Get-AzHostGroup'
* Menambahkan cmdlet baru 'Invoke-AzVmPatchAssessment'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan properti yang hilang ke kelas PSPipelineRun.

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung pembuatan kluster dengan fitur enkripsi di host.

#### <a name="azkeyvault"></a>Az.KeyVault
* Pesan peringatan tambahan untuk perencanaan untuk menonaktifkan penghapusan sementara
* Pesan peringatan yang ditambahkan untuk merencanakan untuk menghapus atribut SecretValueText

#### <a name="azmaintenance"></a>Az.Maintenance
* Menambahkan jadwal opsional terkait bidang ke 'New-AzMaintenanceConfiguration'
* Menambahkan cmdlet baru untuk 'Get-AzMaintenancePublicConfiguration'

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Peringatan perubahan yang ditambahkan pada cmdlet penetapan dan definisi layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Extended the parameter set in 'Set-AzDiagnosticSetting' for separation of Logs and Metrics enablement [#12482]
* Memperbaiki bug 'Add-AzMetricAlertRuleV2' ketika mendapatkan peringatan metrik dari saluran

#### <a name="azresources"></a>Az.Resources
* Diperbarui respons 'Get-AzPolicyAlias' untuk menyertakan informasi yang menunjukkan apakah alias tersebut dapat dimodifikasi oleh Kebijakan Azure.
* Cmdlet baru yang dibuat 'Set-AzRoleAssignment'
* Ditambahkan 'Get-AzDeploymentManagementGroupWhatIfResult' untuk mendapatkan hasil What-If templat ARM di lingkup Grup manajemen
* Menambahkan cmdlet baru 'Get-AzTenantWhatIfResult' untuk mendapatkan templat ARM What-If hasil pada lingkup penyewa
* Overrode '-WhatIf' dan '-Confirm' untuk 'New-AzManagementGroupDeployment' dan 'New-AzTenantDeployment' untuk menggunakan arm template What-If results
* Memperbaiki perilaku '-WhatIf' dan '-Confirm' untuk cmdlet penyebaran baru agar sesuai dengan False dan
* Memperbaiki kesalahan serialisasi untuk '-TemplateObject' dan 'TemplateParameterObject' [#1528] [#6292]
* Ditambahkan breaking change attribute to 'Get-AzResourceGroupDeploymentOperation' untuk perubahan tipe output yang akan datang

#### <a name="azsignalr"></a>az.signalr
* Memperbaiki kesalahan file bantuan 'Mulai Ulang-AzSignalR' dan 'Update-AzSignalR'
* Cmdlet yang ditambahkan 'Update-AzSignalRNetworkAcl', 'Set-AzSignalRUpstream'

#### <a name="azstorage"></a>Az.Storage
* Akselerasi kueri blob yang didukung
    -  'Get-AzStorageBlobQueryResult'
    -  'New-AzStorageBlobQueryConfig'
* Memperbarui file bantuan, menambahkan lebih banyak deskripsi, dan memperbaiki kesalahan ketik
    -  'Start-AzStorageBlobCopy'
    -  'Get-AzDataLakeGen2Item'
* Memperbaiki kegagalan dalam mengunduh blob ketika sub directory terkait tidak ada [#12592]
    -  'Get-AzStorageBlobContent'
* Kebijakan Set/Dapatkan/Hapus Replikasi Objek yang Didukung Storage baru
    - 'New-AzStorageObjectReplicationPolicyRule'
    - 'Set-AzStorageObjectReplicationPolicy'
    - 'Get-AzStorageObjectReplicationPolicy'
    - 'Remove-AzStorageObjectReplicationPolicy'
* Mendukung aktifkan/nonaktifkan ChangeFeed di Layanan Blob layanan Storage ini
    - 'Update-AzStorageBlobServiceProperty'

## <a name="450---august-2020"></a>4.5.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui 'Koneksi-AzAccount' untuk menerima parameter 'MaxContextPopulation' [#9865]
* Memperbarui versi SubscriptionClient ke 2019-06-01 dan menampilkan domain penyewa [#9838]
* Penyewa di rumah yang didukung dan informasi penyewa langganan yang dikelolaOleh
* Nama modul yang diperbaiki, informasi versi dalam data telemetri
* SqlDatabaseDns Adjusted dan ServiceManagementUrl jika titik akhir metadata lingkungan mengembalikan nilai yang tidak kompatibel

#### <a name="azaks"></a>Az.Aks
* Hapus 'ClientIdAndSecret' ke 'ServicePrincipalIdAndSecret' dan setel 'ClientIdAndSecret' sebagai alias [#12381].
* Hapus 'Get-AzAks'/'New-AzAks'/'Remove-AzAks'/'Set-AzAks' ke 'Get-AzAksCluster'/'New-AzAksCluster'/'Remove-AzAksCluster'/'Set-AzAksCluster' dan atur yang asli sebagai alias [#12373].

#### <a name="azapimanagement"></a>Az.ApiManagement
* Ditambahkan cmdlet 'Add-AzApiManagementApiToGateway' baru.
* Ditambahkan cmdlet 'Get-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'Get-AzApiManagementGatewayHostnameConfiguration' baru.
* Ditambahkan cmdlet 'Get-AzApiManagementGatewayKey' baru.
* Ditambahkan cmdlet 'New-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'New-AzApiManagementGatewayHostnameConfiguration' baru.
* Menambahkan cmdlet baru 'New-AzApiManagementResourceLocationObject'.
* Menambahkan cmdlet baru 'Remove-AzApiManagementApiFromGateway'.
* Ditambahkan cmdlet baru 'Remove-AzApiManagementGateway'.
* Menambahkan cmdlet 'Remove-AzApiManagementGatewayHostnameConfiguration' baru.
* Menambahkan cmdlet baru 'Update-AzApiManagementGateway'.
* Menambahkan parameter opsional baru [-GatewayId] ke cmdlet 'Get-AzApiManagementApi'.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Digunakan 'Tolak' khususnya sebagai tindakan default NetworkRules.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbaiki masalah ketika pengecualian sedang dilakukan saat Enum.Parse berusaha mengerahkan nilai null ke nilai enum Diaktifkan atau Dinonaktifkan [#12344]

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung pembuatan kluster dengan enkripsi dalam fitur transit.
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightCluster'
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightClusterConfig'
* Supported creating cluster with private link feature:
    - Menambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightCluster'
    - Tambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightClusterConfig'
* Informasi jaringan virtual yang dikembalikan saat menghubungi 'New-AzHDInsightCluster' atau 'Get-AzHDInsightCluster'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Perubahan tidak memutus: PeerAddressType fungsionalitas untuk Peering Privat dalam 'Remove-AzExpressRouteCircutPeeringConfig'.
* Kode berubah untuk mengabaikan huruf besar/huruf untuk parameter AddressPrefixType dan PeerAddressType.
* Mengubah pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Opsi '-ForceDelete' ditambahkan untuk 'Remove-AzOperationalInsightsworkspace'
* Menambahkan cmdlet baru 'Get-AzOperationalInsightsDeletedWorkspace'
* Menambahkan cmdlet baru 'Restore-AzOperationalInsightsWorkspace'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menyempurnakan pengalaman penemuan item/wadah Cadangan Azure.

#### <a name="azresources"></a>Az.Resources
* Properti ditambahkan 'Condition', 'ConditionVersion' dan 'Description' ke 'New-AzRoleAssignment'
    - Ini menyertakan semua perubahan yang relevan pada model data

#### <a name="azsql"></a>az.sql
* Memperbaiki potensi kesalahan insensitif nama server dalam 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Memperbaiki nama database yang salah dikembalikan pada kesalahan database yang sudah ada di 'New-AzSqlDatabaseSec azurery'

#### <a name="azstorage"></a>Az.Storage
* Token buat wadah/blob Sas yang didukung dengan izin baru x,t
    -  'New-AzStorageBlobSASToken'
    -  'New-AzStorageContainerSASToken'
* Token buat akun yang didukung Sas dengan izin baru x,t,f
    -  'New-AzStorageAccountSASToken'
* Mendapatkan penggunaan berbagi satu file yang didukung
    - 'Get-AzRmStorageShare'

## <a name="440---july-2020"></a>4.4.0 - Juli 2020
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan cmdlet baru 'Invoke-Az CmdletMethod'
* Memperbaiki masalah yang mungkin menyebabkan kesalahan autentikasi dalam skenario multi-proses seperti menjalankan beberapa cmdlet Azure PowerShell menggunakan 'Start-Job' [#9448]

#### <a name="azaks"></a>Az.Aks
* Perbaikan bug 'Get-AzAks' tidak mendapatkan semua kluster [#12296]

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Referensi proyek yang dihapus ke Autentikasi

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah string dengan karakter escape yang tidak dapat dikonversi menjadi objek json.

#### <a name="azcompute"></a>Az.Compute
* Peringatan tambahan saat menggunakan 'New-AzVmss' tanpa versi gambar 'terbaru'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan parameter global ke Data Factory.

#### <a name="azeventgrid"></a>Az.EventGrid
* Diperbarui untuk menggunakan versi API 2020-06-01.
* Fitur baru yang ditambahkan:
    - Pemetaan input
    - Skema Pengiriman Kejadian
    - Tautan Pribadi
    - Skema Cloud Event V10
    - Bus Layanan Topik Sebagai Tujuan
    - Fungsi Azure Sebagai Tujuan
    - Kumpulan WebHook
    - Secure webhook (AAD dukungan)
    - IpFiltering
* Cmdlet yang diperbarui:
    - 'New-AzeventGridSubscription'/'Update-AzEventGridSubscription':
        - Tambahkan parameter opsional baru untuk mendukung batch webhook.
        - Tambahkan parameter opsional baru untuk mendukung webhook yang aman menggunakan AAD.
        - Tambahkan enum baru untuk parameter EndpointType untuk mendukung topik bus layanan dan fungsi Azure sebagai tujuan baru.
        - Tambahkan parameter opsional baru untuk skema pengiriman.
    - 'New-AzEventGridTopic'/'Update-AzEventGridTopic' dan 'New-AzEventGridDomain'/'Update-AzEventGridDomain':
        - Tambahkan parameter opsional baru untuk mendukung IpFiltering.
    - 'New-AzEventGridTopic'/'New-AzEventGridDomain':
        - Tambahkan parameter opsional baru untuk mendukung pemetaan Input.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Modul yang diperbarui untuk menggunakan API 2020-05-01
* Menambahkan dukungan tautan pribadi untuk Storage, Keyvault, dan Layanan Web App

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung pembuatan kluster dengan penyimpanan ADLSGen1/2 di awan nasional.

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug untuk 'Get-AzDiagnosticSetting' ketika metrik atau log null [#12272]

#### <a name="aznetwork"></a>Az.Network
* Tukar parameter tetap di koneksi VWan HubVnet
* Menambahkan cmdlet baru untuk Situs Peralatan Virtual Azure Network
    - 'Get-AzVirtualApplianceSite'
    - 'New-AzVirtualApplianceSite'
    - 'Remove-AzVirtualApplianceSite'
    - 'Update-AzVirtualApplianceSite'
    - 'New-AzOffice365PolicyProperty'
* Menambahkan cmdlet baru untuk Peralatan Virtual Azure Network
    - 'Get-AzNetworkVirtualAppliance'
    - 'New-AzNetworkVirtualAppliance'
    - 'Remove-AzNetworkVirtualAppliance'
    - 'Update-AzNetworkVirtualAppliance'
    - 'Get-AzNetworkVirtualApplianceSku'
    - 'New-AzVirtualApplianceSkuProperty'
* Gateway Aplikasi Onboarded ke Cmdlet Umum Link Privat
* Onboarded StorageSync to Private Link Common Cmdlets
* Cmdlet Umum Onboarded SignalR ke Private Link

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Referensi proyek yang dihapus ke Autentikasi
* Cmdlets Azure Backup tuned membantu agar teks menjadi lebih akurat.
* Azure Backup menambahkan dukungan untuk mengambil pekerjaan agen MAB menggunakan cmdlet 'Get-AzRecoveryServicesBackupJob'.

#### <a name="azresources"></a>Az.Resources
* Diperbarui 'Save-AzResourceGroupDeploymentTemplate' untuk menggunakan SDK.
* Menambahkan cmdlet 'Unregister-AzResourceProvider'.

#### <a name="azsql"></a>az.sql
* Menambahkan dukungan untuk Prinsipal layanan dan pengguna tamu Set-AzSqlInstanceActiveDirectoryAdministrator cmdlet'
* Perbaikan bug dalam cmdlet Klasifikasi Data.'
* Menambahkan dukungan untuk Azure SQL Failover Instans Terkelola: 'Invoke-AzSqlInstanceFailover'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah yang tidak ditambahkan UserAgent untuk beberapa cmdlet bidang data.
* Akun pembuatan/pembaruan Storage yang didukung dengan MinimumTlsVersion dan AllowBlobPublicAccess
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung mengaktifkan/menonaktifkan versi pada Layanan Blob akun Storage
    - 'Update-AzStorageBlobServiceProperty'
* Daftar dukungan blob dengan versi blob
    - 'Get-AzStorageBlob'
* Dukungan untuk mendapatkan/menghapus snapshot blob tunggal atau versi blob
    - 'Get-AzStorageBlob'
    - 'Remove-AzStorageBlob'
* Saluran dukungan dari objek blob yang dihasilkan dari Azure. Storage. Blobs V12
    - 'Get-AzStorageBlobContent'
    - 'New-AzStorageBlobSASToken'
    - 'Remove-AzStorageBlob'
    - 'Set-AzStorageBlobContent'
    - 'Start-AzStorageBlobCopy'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan versi baru StorageSync SDK menargetkan ApiVersion 2020-03-01
* Cmdlet Added Update Storage Sync Service
    - 'Set-AzStorageSyncService'
* Menambahkan IncomingTrafficPolicy dan PrivateEndpointConnections ke cmdlet StorageSyncService.

#### <a name="azwebsites"></a>Situs Web Az.
* Dukungan yang ditambahkan untuk menjalankan operasi untuk Slot yang tidak berada dalam grup sumber daya yang sama seperti Paket Layanan Aplikasi

## <a name="430---june-2020"></a>4.3.0 - Juni 2020
#### <a name="azaccounts"></a>Az.Accounts
* Pengaturan lingkungan penemuan yang didukung secara default dan menambahkan lingkungan melalui 'Add-AzEnvironment'
* Perbarui assemblies yang sudah dimuat sebelumnya [#12024], [#11976]
* Pembaruan perakitan Azure.Core
* Memperbaiki masalah yang mungkin mengakibatkan 'Koneksi-AzAccount' gagal dalam eksekusi multi-alur [#11201]

#### <a name="azaks"></a>Az.Aks
* Penggunaan API [AccessProfile lama yang telah diganti](/rest/api/aks/managedclusters/getaccessprofile) dengan panggilan ke [ListClusterAdmin](/rest/api/aks/managedclusters/listclusteradmincredentials) [dan API ListClusterUser](/rest/api/aks/managedclusters/listclusterusercredentials)

#### <a name="azbatch"></a>Az.Batch
* Diperbarui az.batch untuk menggunakan versi SDK 'Microsoft.Azure.Management.Batch' ke 11.0.0
* Menambahkan kemampuan untuk mengatur Identitas BatchAccount di cmdlet 'New-AzBatchAccount'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Didukung menampilkan kapabilitas akun.
* Perubahan yang didukung PublicNetworkAccess.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter simulateEviction Set-AzVM dan Set-AzVmssVM cmdlet.
* Menambahkan 'Premium_LRS' ke alat lengkap argumen parameter StorageAccountType untuk New-AzGalleryImageVersion cmdlet.
* Menambahkan Substatus ke VMCustomScriptExtension [#11297]
* Menambahkan 'Delete' ke argumen lengkap parameterMentpolicy pada New-AzVM dan New-AzVMConfig cmdlet.
* Nama tetap Ekstensi VM baru untuk SAP

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi .Net SDK ADF ke 4.9.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter Identitas Terkelola ke cmdlet 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Dukungan tambahan untuk membuat aplikasi fungsi PowerShell 7.0 dan Java 11

#### <a name="azhdinsight"></a>Az.HDInsight
* Host daftar yang didukung dan mulai ulang host tertentu dari kluster HDInsight.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Memperbarui versi SDK ke 1.1.0
* Menambahkan dukungan untuk pengaturan Ekspor dan Identitas Terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki parameter objek input untuk 'Set-AzActivityLogAlert'
* Memperbaiki parameter 'InputObject' untuk 'Set-AzActionGroup' [#10868]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Menambahkan cmdlet baru untuk Azure FirewallPolicy
    - 'New-AzFirewallPolicyDnsSetting'
    - Dukungan untuk FQDN Tujuan dalam Aturan Jaringan untuk Kebijakan Firewall
* Dukungan tambahan untuk operasi pool alamat backend
    - 'New-AzLoadBalancerBackendAddressConfig'
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'
    - 'Remove-AzLoadBalancerBackendAddressPool'
    - 'Get-AzLoadBalancerBackendAddressPool'
* Validasi nama yang ditambahkan untuk 'New-AzIpGroup'
* Menambahkan cmdlet baru untuk Azure FirewallPolicy
    - 'New-AzFirewallPolicyThreatIntelWalllist'
* Diperbarui di bawah perintah untuk fitur: Server dns kustom diatur/dihapus di VirtualWan P2SVpnGateway.
    - Diperbarui New-AzP2sVpnGateway: Added optional parameter '-CustomDnsServer' for customers to specify their dns servers to set on P2SVpnGateway, which can be used by Point to site clients.
    - Updated Update-AzP2sVpnGateway: Added optional parameter '-CustomDnsServer' for customers to specify their dns servers to set on P2SVpnGateway, which can be used by Point to site clients.
* Diperbarui 'Update-AzVpnGateway'
    - Menambahkan parameter opsional '-BgpPeeringAddress' bagi pelanggan untuk menentukan bgp kustom mereka untuk diatur di VpnGateway.
* Menambahkan cmdlet baru untuk mendukung pengaturan ulang status perutean sumber daya VirtualHub:
    - 'Reset-AzHubRouter'
* Diperbarui di bawah ini berdasarkan perubahan perubahan terbaru untuk Kebijakan Firewall
    - Mengubah nama untuk RuleGroup, RuleCollectionGroup dan RuleType
    - Menambahkan dukungan untuk Kumpulan Aturan NAT Kebijakan Firewall untuk mendukung beberapa Kumpulan Aturan NAT
* [Breaking Change] Ditambahkan parameter wajib 'SourceIpGroup' untuk 'New-AzFirewallPolicyApplicationRule' dan 'New-AzFirewallPolicyNetworkRule'.
* [Breaking Change] Memperbaiki 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' harus wajib dilakukan.
* [Breaking Change] Memperbaiki 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' harus wajib dilakukan.
* [Breaking Change] Removed mandatory parameters: 'TranslatedAddress', 'TranslatedPort' for 'New-AzFirewallPolicyNatRuleCollection'.
* Menambahkan cmdlet baru untuk mendukung PrivateLink On Application Gateway
    - 'New-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Get-AzApplicationGatewayPrivateLinkConfiguration'
    - 'New-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Set-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Remove-AzApplicationGatewayPrivateLinkConfiguration'
    - 'New-AzApplicationGatewayPrivateLinkIpConfiguration'
* Menambahkan cmdlet baru untuk HubRouteTables child resource of VirtualHub.
    - 'New-AzvHubRoute'
    - 'New-AzvHubRouteTable'
    - 'Get-AzvHubRouteTable'
    - 'Update-AzvHubRouteTable'
    - 'Remove-AzvHubRouteTable'
* Memperbarui cmdlet yang sudah ada untuk mendukung parameter input RoutingConfiguration opsional untuk perutean kustom di VirtualWan.
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
* Menambahkan 'pergb2018' ke kumpulan nilai yang valid dari parameter 'Sku' di 'Set-AzOperationalInsightsWorkspace'
* Alias yang ditambahkan 'FunctionParameters' untuk parameter 'FunctionParameter' untuk
    - 'New-AzOperationalInsightsSavedSearch'
    - 'Set-AzOperationalInsightsSavedSearch'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup menambahkan dukungan untuk mengambil item MAB.
* Pemulihan Situs Azure mendukung 'pengaturan StandardSSD_LRS' tipe disk

#### <a name="azresources"></a>Az.Resources
* Ditambahkan 'UsageLocation', 'GivenName', 'Surname', 'AccountEnabled', 'MailNickname', 'Mail' pada 'INDAHDUser' [#10526] [#10497]
* Memperbaiki masalah yang '-Mail' tidak berfungsi pada 'Get-AzADUser' [#11981]
* Menambahkan parameter '-ExcludeChangeType' ke 'Get-AzDeploymentWhatIfResult' dan 'Get-AzResourceGroupDeploymentWhatIfResult'
* Menambahkan parameter '-WhatIfExcludeChangeType' ke 'New-AzDeployment' dan 'New-AzResourceGroupDeployment'
* Cmdlet 'Test-Az*Deployment' diperbarui untuk memperlihatkan pesan kesalahan yang lebih baik
* Memperbaiki pesan bantuan untuk parameter '-Nama' pembuatan dan pembuatan What-If cmdlet penyebaran

#### <a name="azsql"></a>az.sql
* Dukungan tambahan untuk prinsipal layanan untuk cmdlet Set SQL Server Azure Active Directory Admin
* Memperbaiki masalah sinkronisasi dalam cmdlet Klasifikasi Data.
* Didukung pencarian pengguna melalui email di 'Set-AzSqlServerActiveDirectoryAdministrator' [#12192]

#### <a name="azstorage"></a>Az.Storage
* Pembuatan akun Storage yang didukung dengan RequireInfrastructureEncryption
    -  'New-AzStorageAccount'
* Memindahkan logika pemuatan Azure.Core ke Az.Accounts

#### <a name="azwebsites"></a>Situs Web Az.
* Tindakan pengamanan tambahan untuk menghapus aplikasi web yang dibuat jika pemulihan gagal di 'Restore-AzDeletedWebApp'
* Menambahkan 'SourceWebApp.Location' untuk 'New-AzWebApp' dan 'New-AzWebAppSlot'
* Memperbaiki bug yang mencegah pengubahan pengaturan Kontainer di 'Set-AzWebApp' dan 'Set-AzWebAppSlot'
* Fixed bug to get SiteConfig when -Name is not given for Get-AzWebApp
* Menambahkan dukungan untuk membuat ASP untuk Aplikasi Linux
* Pengecualian yang ditambahkan untuk kloning di seluruh grup sumber daya

## <a name="420---june-2020"></a>4.2.0 - Juni 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah yang mungkin mengakibatkan Az melewatkan log dalam pekerjaan Azure Automation atau PowerShell [#11492]

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Versi perakitan cmdlet bidang data yang diperbarui

#### <a name="azapimanagement"></a>Az.ApiManagement
* Versi perakitan cmdlet manajemen layanan yang diperbarui

#### <a name="azbilling"></a>Az.Billing
* Versi perakitan cmdlet konsumsi yang diperbarui

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung kontrol PrivateEndpoint dan PublicNetworkAccess.

#### <a name="azdatafactory"></a>Az.DataFactory
* Versi perakitan terbaru cmdlet data factory V2

#### <a name="azdatashare"></a>Az.DataShare
* Ketersediaan umum modul ''Az.DataShare''

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Ketersediaan umum modul ''Az.DesktopVirtualization''

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Peningkatan SDK ke 0.21.0
* Menambahkan parameter opsional ke
    - 'New-AzOperationalInsightsSavedSearch'
    - 'Set-AzOperationalInsightsSavedSearch'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Contoh 3 yang diperbaiki untuk 'Start-AzPolicyComplianceScan'

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Versi perakitan cmdlet PowerBI yang diperbarui

#### <a name="azprivatedns"></a>Az.PrivateDns
* Pemformatan string output verbose yang diperbaiki untuk Remove-AzPrivateDnsRecordSet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk membuat rencana pemulihan bagi replikasi zona ke zona dari input xml.
* Versi perakitan terbaru cmdlet SiteRecovery dan Backup

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter Tail Get-AzDeploymentScriptLog cmdlet Save-AzDeploymentScriptLog baru
* Properti Output Terformat dan memperlihatkannya di Get-AzDeploymentScript output cmdlet
* Parameter -DeploymentScriptInputObject diubah namanya menjadi -DeploymentScriptObject
* Perbaikan nama file/target yang hilang dalam pesan cmdlet.
* Versi perakitan yang diperbarui dari manajer sumber daya dan cmdlet tag

#### <a name="azsql"></a>az.sql
* Ditambahkan UsePrivateLinkConnection ke 'New-AzSqlSyncGroup', 'Update-AzSqlSyncGroup', 'New-AzSqlSyncMember' dan 'Update-AzSqlSyncMember'
* Menambahkan SyncMemberAzureDatabaseResourceId ke 'New-AzSqlSyncMember' dan 'Update-AzSqlSyncMember'
* Menambahkan dukungan pencarian pengguna Tamu ke Cmdlet SQL Server Azure Active Directory Admin Baru

#### <a name="azstorage"></a>Az.Storage
* Versi perakitan cmdlet bidang data yang diperbarui

## <a name="410---may-2020"></a>4.1.0 - Mei 2020
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Versi PowerShell yang Didukung: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7
* Ketersediaan umum Az.Functions
* Az.ApiManagement, Az.Batch, Az.Compute, Az.KeyVault, Az.Monitor, Az.Network, Az.OperationalInsights, Az.Resources, dan Az.Storage memiliki rilis utama

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui 'Add-AzEnvironment' dan 'Set-AzEnvironment' untuk menerima parameter 'AzureSynapseAnalyticsEndpointResourceId' dan 'AzureSynapseAnalyticsEndpointFix'
* Menambahkan perakitan terkait Azure.Core ke Az.Accounts, platform PowerShell yang didukung termasuk Windows PowerShell 5.1, PowerShell Core 6.2.4, PowerShell 7+

#### <a name="azaks"></a>Az.Aks
* Meningkatkan Versi API ke 2019-10-01
* Didukung untuk membuat AKS menggunakan Windows penampung
* Cmdlet baru yang disediakan: 'New-AzAksNodePool', 'Update-AzAksNodePool', 'Remove-AzAksNodePool', 'Get-AzAksNodePool', 'Install-AzAksKubectl', 'Get-AzAksVersion'

#### <a name="azapimanagement"></a>Az.ApiManagement
* 'New-AzApiManagement' dan 'Set-AzApiManagement': [-AssignIdentity] parameter renamed as [-SystemAssignedIdentity]
* 'New-AzApiManagement' dan 'Set-AzApiManagement': Parameter baru ditambahkan: [-UserAssignedIdentity <String[]>]
* 'Get-AzApiManagementProperty': renamed as 'Get-AzApiManagementNamedValue'. Parameter PropertyId diganti namanya sebagai NamedValueId.
* 'New-AzApiManagementProperty': renamed as 'New-AzApiManagementNamedValue'. Parameter PropertyId diganti namanya sebagai NamedValueId.
* 'Set-AzApiManagementProperty': renamed as 'Set-AzApiManagementNamedValue'. Parameter PropertyId diganti namanya sebagai NamedValueId.
* 'Remove-AzApiManagementProperty': renamed as 'Remove-AzApiManagementNamedValue'. Parameter PropertyId diganti namanya sebagai NamedValueId.
* Ditambahkan cmdlet 'Get-AzApiManagementAuthorizationServerClientSecret' dan 'Get-AzApiManagementAuthorizationServer' tidak akan mengembalikan rahasia klien lagi.
* Ditambahkan cmdlet 'Get-AzApiManagementNamedValueSecretValue' dan 'Get-AzApiManagementNamedValue' tidak akan mengembalikan nilai rahasia.
* Ditambahkan cmdlet 'Get-AzApiManagementOpenIdConnectProviderClientSecret' dan 'Get-AzApiManagementOpenIdConnectProvider' tidak akan mengembalikan rahasia klien lagi.
* Ditambahkan cmdlet 'Get-AzApiManagementSubscriptionKey' dan 'Get-AzApiManagementSubscription' tidak akan mengembalikan kunci langganan lagi.
* Ditambahkan cmdlet 'Get-AzApiManagementTenantAccessSecret' dan 'Get-AzApiManagementTenantAccess' tidak akan mengembalikan tombol lagi.
* Ditambahkan cmdlet 'Get-AzApiManagementTenantGitAccessSecret' dan 'Get-AzApiManagementTenantGitAccess' tidak akan mengembalikan tombol lagi.

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Parameter Tambahan: 'RetentionInDays' 'PublicNetworkAccessForIngestion' 'PublicNetworkAccessForQuery' untuk 'New-AzApplicationInsights'
* Cmdlet yang dibuat 'Update-AzApplicationInsights'
* Cmdlet yang dibuat untuk Akun Storage Tertaut

#### <a name="azbatch"></a>Az.Batch
* Diperbarui az.Batch untuk menggunakan SDK versi 'Microsoft.Azure.Batch' versi 13.0.0 dan 'Microsoft.Azure.Management.Batch' SDK versi 9.0.0.
* Menambahkan kemampuan untuk memilih jenis sertifikat yang ditambahkan menggunakan parameter '-CertificateKind' baru untuk 'New-AzBatchCertificate'.
* Menghapus properti 'ApplicationPackages' dari 'PSApplication' yang sebelumnya selalu ''.
  - Paket tertentu di dalam aplikasi sekarang bisa diambil menggunakan 'Get-AzBatchApplicationPackage'. Misalnya: 'Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication'.
* Saat membuat kolam renang menggunakan 'New-AzBatchPool', properti 'VirtualMachineImageId' dari 'PSImageReference' sekarang hanya bisa merujuk ke gambar Galeri Gambar Bersama.
* Saat membuat pool menggunakan 'New-AzBatchPool', pool bisa disediakan tanpa IP publik menggunakan properti 'PublicIPAddressConfiguration' baru dari 'PSNetworkConfiguration'.
  - Properti 'PublicIPs' dari 'PSNetworkConfiguration' telah dipindahkan ke 'PSPublicIPAddressConfiguration' juga. Properti ini hanya dapat ditentukan jika 'IPAddressProvisioningType' adalah 'UserManaged'.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HostId ke cmdlet 'Update-AzVM'
* Memperbarui dokumen Bantuan untuk 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVmss', 'Set-AzVMOperatingSystem' dan 'Set-AzVmssOsProfile'.
* Memutus perubahan
    - Parameter FilterExpression dihapus dari cmdlet 'Get-AzVMImage'.
    - AssignIdentity parameter is removed from 'New-AzVmssConfig', 'New-AzVMConfig' and 'Update-AzVM' cmdlets.
    - AutomaticRepairMaxInstanceRepairsPercent dihapus dari cmdlet 'New-AzVmssConfig' dan 'Update-AzVmss'.
    - KetersediaanSetsColocationStatus, VirtualMachinesColocationStatus dan VirtualMachineScaleSetsColocationStatus properti dihapus dari ProximityPlacementGroup.
    - Properti MaxInstanceRepairsPercent dihapus dari AutomaticRepairsPolicy.
    - Tipe AvailabilitySets, VirtualMachines dan VirtualMachineScaleSets diubah `IList<SubResource>` dari menjadi `IList<SubResourceWithColocationStatus>` .
* Deskripsi untuk cmdlet 'Get-AzVM' telah diperbarui agar lebih menjelaskannya.

#### <a name="azdatafactory"></a>Az.DataFactory
* CruD properti runtime alur data yang didukung di IR yang Dikelola.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan cmdlet baru untuk pembuatan, pembaruan, rethabval, dan penghapusan objek Mesin Aturan Pintu Depan
* Menambahkan cmdlet bantuan untuk pembuatan objek Mesin Aturan Pintu Depan
* Ditambahkan referensi Mesin Aturan untuk objek Aturan Perutean Pintu Depan.
* Menambahkan parameter Link Privat pada objek Backend Pintu Depan

#### <a name="azfunctions"></a>Az.Functions
* Ketersediaan umum modul ''Az.Functions''

#### <a name="azhdinsight"></a>Az.HDInsight
* Enkripsi disk kunci yang dikelola oleh pelanggan yang Didukung.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Kebijakan akses tidak lagi default untuk pokok data saat ini

#### <a name="aziothub"></a>Az.IotHub
* Cmdlet tambahan untuk menjalankan kueri dalam hub IoT untuk mengambil informasi menggunakan SQL seperti ini.
* Memperbaiki masalah yang 'Add-AzIotHubDevice' gagal membuat Perangkat Edge yang Diaktifkan tanpa perangkat anak [#11597]
* Cmdlet tambahan untuk menghasilkan token SAS untuk Iot Hub, perangkat atau modul.
* Cmdlet ditambahkan untuk menjalankan kueri metrik konfigurasi.
* Kelola penyebaran otomatis IoT Edge pada skala tertentu. Cmdlet baru adalah:
    - 'Add-AziotHubDeployment'
    - 'Get-AziotHubDeployment'
    - 'Remove-AziotHubDeployment'
    - 'Set-AziotHubDeployment'
* Cmdlet tambahan untuk menjalankan kueri metrik penyebaran IoT Edge.
* Cmdlet ditambahkan untuk menerapkan konten konfigurasi ke perangkat tepi yang ditentukan.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menghapus dua alias: 'New-AzKeyVaultCertificateAdministratorDetails' dan 'New-AzKeyVaultCertificateOrganizationDetails'
* Mengaktifkan penghapusan sementara secara default saat membuat vault kunci
* Aturan jaringan dapat diatur untuk mengatur aksesibilitas dari lokasi jaringan tertentu saat membuat vault kunci
* Dukungan tambahan untuk menghadirkan kunci Anda sendiri (BYOK)
    - 'Add-AzKeyVaultKey' mendukung pembuatan kunci exchange kunci
    - 'Get-AzKeyVaultKey' mendukung pengunduhan kunci publik dalam format PEM
* Memperbarui bagian 'KeyOps' dari dokumen bantuan 'Add-AzKeyVaultKey'

#### <a name="azmonitor"></a>Az.Monitor
* Perbaikan bug untuk 'Set-AzDiagnosticSettings', kebijakan penyimpanan tidak akan berlaku untuk semua kategori [#11589]
* Kriteria ketersediaan WebTest yang didukung untuk peringatan metrik V2
    - 'New-AzMetricAlertRuleV2Criteria': opsi untuk membuat kriteria ketersediaan webtest ditambahkan
    - 'Add-AzMetricAlertRuleV2': mendukung kriteria ketersediaan webtest yang baru
* Menghapus definisi berlebihan untuk RetentionPolicy di PSLogProfile [#7608]
* Properti berlebihan yang dihapus difined di PSEventData [#11353]
* Diubah namanya 'Get-AzLog' menjadi 'Get-AzActivityLog'

#### <a name="aznetwork"></a>Az.Network
* Atribut perubahan pecah yang ditambahkan untuk memberi tahu bahwa default Zona akan diubah
    - 'New-AzPublicIpAddress'
    - 'New-AzPublicIpPrefix'
    - 'New-AzLoadBalancerFrontendIpConfig'
* Menambahkan dukungan untuk sumber daya tingkat atas yang baru SecurityPartnerProvider
    - Cmdlet baru ditambahkan:
        - New-AzSecurityPartnerProvider
        - Remove-AzSecurityPartnerProvider
        - Get-AzSecurityPartnerProvider
        - Set-AzSecurityPartnerProvider
* Ditambahkan 'RequiredZoneNames' di 'PSPrivateLinkResource' dan 'GroupId' di 'PSPrivateEndpointConnection'
* Memperbaiki tipe parameter SuccessThresholdRoundTripTimeMs yang tidak benar New-AzNetworkWatcherConnectionMonitorTestConfigurationObject
* Cmdlet VirtualWan yang diperbarui untuk mengatur nilai default argumen AllowVnetToVnetTraffic ke True.
    - 'New-AzVirtualWan'
    - 'Update-AzVirtualWan'
* Menambahkan cmdlet baru untuk mendukung grup zona DNS untuk titik akhir privat
    - 'New-AzPrivateDnsZoneConfig'
    - 'Get-AzPrivateDnsZoneGroup'
    - 'New-AzPrivateDnsZoneGroup'
    - 'Set-AzPrivateDnsZoneGroup'
    - 'Remove-AzPrivateDnsZoneGroup'
* Menambahkan 'DNSEnableProxy', 'DNSRequireProxyForNetworkRules' dan 'DNSServers' parameter ke 'AzureFirewall'
* Ditambahkan 'EnableDnsProxy', 'DnsProxyNotRequiredForNetworkRule' dan 'DnsServer' parameter untuk 'AzureFirewall'
    - Cmdlet yang diperbarui:
        - New-AzFirewall

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbarui kode warisan untuk menerapkan SDK baru yang dihasilkan
* Cmdlet yang dihapus karena API yang sudah tidak berlaku
    - 'Get-AzOperationalInsightsSavedSearchResult' (alias 'Get-AzOperationalInsightsSavedSearchResults')
    - 'Get-AzOperationalInsightsSearchResult' (alias 'Get-AzOperationalInsightsSearchResults')
    - 'Get-AzOperationalInsightsLinkTarget' (alias 'Get-AzOperationalInsightsLinkTargets')
* Parameter tambahan untuk 'Set-AzOperationalInsightsWorkspace' dan 'New-AzOperationalInsightsWorkspace'
* Cmdlet yang dibuat untuk Akun Linked Cmdlets
* Cmdlet yang dibuat untuk Kluster dan Layanan Tertaut

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Pemulihan Situs Azure menambahkan dukungan untuk melindungi mesin virtual grup penempatan kedekatan untuk Azure ke penyedia Azure.
* Pemulihan Situs Azure menambahkan dukungan untuk zona ke replikasi zona.
* Azure Backup Menambahkan dukungan penyimpanan jangka panjang untuk Titik Pemulihan Azure FileShare.
* Properti pengecualian disk Azure Backup Ditambahkan ke output cmdlet 'Get-AzRecoveryServicesBackupItem'.
* Menambahkan titik akhir privat untuk file kredensial Vault untuk layanan pemulihan situs.

#### <a name="azresources"></a>Az.Resources
* Peringatan pesan yang ditambahkan tentang penundaan tampilan saat membuat Definisi Peran baru
* Cmdlet kebijakan yang diubah untuk menghasilkan objek yang sangat diketik
* Parameter '-TenantLevel' yang dihapus digunakan untuk cmdlet 'Get-AzResourceLock' [#11335]
* Memperbaiki 'Remove-AzResourceGroup -Id ResourceId'[#9882]
* Ditambahkan cmdlet baru untuk mendapatkan hasil What-If templat ARM di lingkup grup sumber daya: 'Get-AzDeploymentResourceGroupWhatIfResult'
* Menambahkan cmdlet baru untuk mendapatkan templat ARM What-If hasil pada lingkup langganan: 'Get-AzDeploymentWhatIfResult'
   - Alias: 'Get-AzSubscriptionDeploymentWhatIf'
* Parameter '-WhatIf' dan '-Confirm' overrode untuk 'New-AzDeployment' dan 'New-AzResourceGroupDeployment' untuk menggunakan templat ARM What-If pencarian
* Pesan penghentian yang ditambahkan untuk parameter 'ApiVersion' dalam cmdlet penyebaran
* Kapabilitas tambahan untuk memperlihatkan pesan kesalahan yang ditingkatkan untuk kegagalan penggunaan
* Menambahkan pembuatan log ID korelasi untuk kegagalan penyebaran
* Menambahkan properti 'kesalahan' ke output skrip penyebaran
* Memperbarui nuget Microsoft.Azure.Management.ResourceManager ke '3.7.1-preview'
* Kasus uji tertentu yang dihapus sebagai properti Kesalahan dalam DeploymentValidateResult telah berubah ke baca saja dari nuget 3.7.1-preview
* Brought GenericResourceExpanded from SDK ResourceManager 3.7.1-preview
* Penambahan dukungan tag untuk semua cmdlet Dapatkan untuk penggunaan, serta
    - 'New-AzDeployment'
    - 'New-AzManagementGroupDeployment'
    - 'New-AzResourceGroupDeployment'
    - 'New-AzTenantDeployment'

#### <a name="azservicefabric"></a>az.servicefabric
* Perbaikan bug dalam menambahkan sertifikat menggunakan --SecretIdentifier yang mendapatkan thumbprint sertifikat yang salah

#### <a name="azsql"></a>az.sql
* Meningkatkan kinerja:
    - 'Set-AzSqlDatabaseSensitivityClassification'
    - 'Set-AzSqlInstanceDatabaseSensitivityClassification'
    - 'Remove-AzSqlDatabaseSensitivityClassification'
    - 'Remove-AzSqlInstanceDatabaseSensitivityClassification'
    - 'Enable-AzSqlDatabaseSensitivityRecommendation'
    - 'Enable-AzSqlInstanceDatabaseSensitivityRecommendation'
    - 'Disable-AzSqlDatabaseSensitivityRecommendation'
    - 'Disable-AzSqlInstanceDatabaseSensitivityRecommendation'
* Menghapus validasi sisi klien dari parameter 'RetentionDays' dari cmdlet 'Set-AzSqlDatabaseBackupShortTermRetentionPolicy'
* Auditing to a storage account in Vnet, fixing a bug when creating a Storage Blob Data Contributor role.

#### <a name="azstorage"></a>Az.Storage
* Menambahkan '-AsJob' untuk cmdlet akun get/list 'Get-AzStorageAccount'
* Buat KeyVersion menjadi opsional ketika memperbarui Storage dengan KeyvaultEncryption, untuk mendukung rotasi otomatis tombol
    - 'Set-AzStorageAccount'
* Perbaikan masalah kegagalan dalam saluran Menghapus Direktori File Azure
    - 'Remove-AzStorageDirectory'
* Diperbaiki [#9880]: Ubah definasi nilai DefaultAction NetWorkRule untuk diratakan dengan perubahan.
    - 'Update-AzStorageAccountNetworkRuleSet'
    - 'Get-AzStorageAccountNetworkRuleSet'
* Diperbaiki [#11624]: Lewati aturan duplikat saat menambahkan Aturan Jaringan, untuk menghindari kegagalan server
    - 'Add-AzStorageAccountNetworkRule'
* Telah meningkatkan Microsoft.Azure.Cosmos.Table SDK ke 1.0.7
* Menambahkan pesan peringatan untuk mengingatkan pengguna tentang daftar lagi dengan ContinuationToken ketika hanya sebagian item yang dikembalikan dalam daftar DataLake Gen2 Items,
    - 'Get-AzDataLakeGen2ChildItem'
* Didukung untuk membuat atau memperbarui Storage dengan Autentikasi Layanan Domain Azure Files Active Directory
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Tombol Kerberos baru atau daftar yang didukung dari Storage tersebut
    -  'New-AzStorageAccountKey'
    -  'Get-AzStorageAccountKey'
* Akun Storage failover yang didukung
    - 'Invoke-AzStorageAccountFailover'
* Pembaruan bantuan 'Get-AzStorageBlobCopyState'
* Pembaruan bantuan 'Get-AzStorageFileCopyState' dan 'Start-AzStorageBlobCopy'
* Solusi Storage klien v12 ke cmdlet Antre dan File
* Tipe output yang diubah dari CloudFile ke AzureStorageFile, output asli akan menjadi properti anak dari output baru
    - 'Get-AzStorageFile'
    - 'Remove-AzStorageFile'
    - 'Get-AzStorageFileContent'
    - 'Set-AzStorageFileContent'
    - 'Start-AzStorageFileCopy'
* Tipe output yang diubah dari CloudFileDirectory ke AzureStorageFileDirectory, output asli akan menjadi properti anak dari output baru
    - 'New-AzStorageDirectory'
    - 'Remove-AzStorageDirectory'
* Tipe output yang diubah dari CloudFileShare ke AzureStorageFileShare, output asli akan menjadi properti anak dari output baru
    - 'Get-AzStorageShare'
    - 'New-AzStorageShare'
    - 'Remove-AzStorageShare'
* Tipe output yang diubah dari FileShareProperties menjadi AzureStorageFileShare, output asli akan menjadi properti sub-anak dari output baru
    - 'Set-AzStorageShareQuota'

#### <a name="aztrafficmanager"></a>az.trafficmanager
* Memperbaiki nama profil yang salah dalam output verbose 'DisableAzureTrafficManagerEndpoint'

#### <a name="azwebsites"></a>Situs Web Az.
* Memperbaiki kesalahan ketik pada bantuan 'Update-AzWebAppAccessRestrictionConfig'.

## <a name="380---april-2020"></a>3.8.0 - April 2020
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Versi PowerShell yang didukung az.Storage: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7

#### <a name="azaccounts"></a>Az.Accounts
* Url Azure PowerShell yang diperbarui dalam 'Resolve-AzError' [#11507]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Pemberitahuan perubahan perubahan tambahan untuk perubahan output cmdlet Azure File dalam rilis yang akan datang
* 'Set-AzApiManagementGroup' Dokumentasi yang diperbarui untuk menentukan parameter GroupId

#### <a name="azcdn"></a>Az.Cdn
* Perbaikan tampilan SKU harga terkait ChinaCDN

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Identitas yang Didukung, Enkripsi, UserOwnedStorage

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet 'Set-AzVmssOrchestrationServiceState'.
* 'Get-AzVmss' dengan -InstanceView memperlihatkan negara-negara Layanan Esklar.

#### <a name="aziothub"></a>Az.IotHub
* Kelola konfigurasi konfigurasi konfigurasi perangkat IoT, Cmdlet baru adalah:
    - 'Get-AziotHubDeviceTwin'
    - 'Update-AziotHubDeviceTwin'
* Cmdlet tambahan untuk menjalankan metode langsung pada perangkat di Iot Hub.
* Kelola konfigurasi konfigurasi perangkat IoT, Cmdlet baru adalah:
    - 'Get-AziotHubModuletwin'
    - 'Update-AziotHubModuletwin'
* Kelola konfigurasi manajemen perangkat otomatis IoT pada skala tertentu. Cmdlet baru adalah:
    - 'Add-AziotHubConfiguration'
    - 'Get-AziotHubConfiguration'
    - 'Remove-AzIotHubConfiguration'
    - 'Set-AziotHubConfiguration'
* Cmdlet yang ditambahkan untuk menjalankan metode modul tepi di Iot Hub.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan cmdlet baru 'Update-AzKeyVault' yang dapat mengaktifkan perlindungan penghapusan sementara dan pembersihan di vault
* Menambahkan dukungan untuk Microsoft.PowerShell.SecretManagement [#11178]
* Memperbaiki kesalahan dalam contoh 'Remove-AzKeyVaultManagedStorageSasDefinition' [#11479]
* Menambahkan dukungan ke titik akhir privat

#### <a name="azmaintenance"></a>Az.Maintenance
* Menerbitkan versi rilis cmdlet Pemeliharaan untuk GA

#### <a name="azmonitor"></a>Az.Monitor
* Cmdlet yang ditambahkan untuk lingkup tautan privat
    - 'Get-AzInsightsPrivateLinkScope'
    - 'Remove-AzInsightsPrivateLinkScope'
    - 'New-AzInsightsPrivateLinkScope'
    - 'Update-AzInsightsPrivateLinkScope'
    - 'Get-AzInsightsPrivateLinkScopedResource'
    - 'New-AzInsightsPrivateLinkScopedResource'
    - 'Remove-AzInsightsPrivateLinkScopedResource'

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui untuk mengaktifkan koneksi pada IP privat untuk Gateway Jaringan Virtual.
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Cmdlet yang diperbarui untuk mengaktifkan FQDN berbasis LocalNetworkGateway dan VpnSites
    - 'New-AzLocalNetworkGateway'
    - 'New-AzVpnSiteLink'
* Menambahkan dukungan untuk keluarga alamat IPv6 di ExpressRouteCircuitConnectionConfig (Global Reach)
    - Added 'Set-AzExpressRouteCircuitConnectionConfig'
        - memungkinkan pengaturan semua properti yang sudah ada termasuk IPv6CircuitConnectionProperties
    - Diperbarui 'Add-AzExpressRouteCircuitConnectionConfig'
        - Menambahkan parameter opsional lainnya AddressPrefixType untuk menentukan keluarga alamat prefiks alamat
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan Waktu DPD pada Virtual Network Gateway Connections.
    - New-AzVirtualNetworkGatewayConnection
    - Set-AzVirtualNetworkGatewayConnection

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan cmdlet 'Start-AzPolicyComplianceScan' untuk memicu pemindaian kepatuhan kebijakan
* Menambahkan definisi kebijakan, menetapkan definisi, dan versi penetapan ke output 'Get-AzPolicyState'

#### <a name="azservicefabric"></a>az.servicefabric
* Pemformatan kode yang ditingkatkan dan kegunaan contoh 'New-AzServiceFabricCluster'

#### <a name="azsql"></a>az.sql
* Cmdlet yang ditambahkan 'Get-AzSqlInstanceOperation' dan 'Stop-AzSqlInstanceOperation'
* Pengauditan yang didukung untuk akun penyimpanan di VNet.

#### <a name="azstorage"></a>Az.Storage
* Pemberitahuan perubahan perubahan tambahan untuk perubahan output cmdlet Azure File dalam rilis yang akan datang
* Didukung SkuName StandardGZRS baru, StandardRAGZRS saat membuat/memperbarui Storage Anda
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* DataLake Gen2 yang Didukung
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
* Buka Azure PowerShell survei baru dalam 'Kirim-Umpan Balik' [#11020]
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
* Deskripsi tetap dari Get-AzLog cmdlet.
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
* Tambahkan Update-AzDiskEncryptionSet cmdlet
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
    - Cmdlet New-AzFirewall yang diperbarui:
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
* Kumpulan dukungan atur Table/Queue Encryption Keytype dalam Storage Baru
    - New-AzStorageAccount
* Memperlihatkan RequestId saat StorageException tidak memiliki ExtendedErrorInformation
* Memperbaiki contoh 6 cmdlet Start-AzStorageBlobCopy

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
* Memperbaiki kesalahan saat membuat SQL contoh failover

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
* Menambahkan argumen opsional ke perintah Tambahkan Pengaturan Diagnostik. Argumen sakelar yang jika ada menunjukkan bahwa ekspor ke Analitik Log harus ke skema tetap (alias khusus, tipe data)

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk IpGroups di AzureFirewall Application,Nat & Network Rules.

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
* Memperbaiki bug di New-AzRoleAssignment parameter yang tidak dapat disebut tanpa Lingkup parameter.

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
* Hapus validasi EmailAddresses dan periksa bahwa EmailAdmins tidak false dalam kasus EmailAddresses kosong dalam Set-AzSqlServerAdvancedThreatProtectionPolicy dan Set-AzSqlDatabaseAdvancedThreatProtectionPolicy
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
* Memperbaiki kesalahan ketik dalam CDN bantuan konversi modul

#### <a name="azcompute"></a>Az.Compute
* Menambahkan VmssId ke New-AzVMConfig cmdlet
* Tambahkan TerminateScheduledEvents dan TerminateScheduledEventNotBeforeTimeoutInMinutes untuk New-AzVmssConfig dan Update-AzVmss
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
    - Jangan gunakan parameter 'PublicIpAddress' karena parameter ini tidak akan pernah digunakan di sisi server.
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
* Pembaruan perintah New-AzApplicationGatewayProbeConfig Gateway Aplikasi untuk mendukung port kustom dalam Port
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
* Memperbaiki model sumber data CustomLog yang dikembalikan di Get-AzOperationalInsightsDataSource

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
* Diperbarui di bawah perintah untuk fitur: Atur VpnClient AAD autentikasi ke Sumber daya gateway jaringan virtual.
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
* Menambahkan perintah cmdlet Get-AzureRmDenyAssignment untuk mengambil penetapan penolakan

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
* Jenis akun Storage default dalam Membuat Storage default dari 'Storage' menjadi 'StorageV2'
    - New-AzStorageAccount
* Ubah output cmdlet Storage akun Sku.Name diratakan dengan SkuName input dengan menambahkan '-', seperti 'StandardLRS' menjadi 'Standard_LRS'
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
* Membuat Add-AzureASAccount pembungkus Connect-AzAccount untuk menghindari perubahan yang tak terhindarkan

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
* Kesalahan detail laporan ketika membuat Storage dengan parameter -UseConnectedAccount, tetapi tanpa masuk ke akun Azure
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
- Az.Insights diubah namanya menjadi Az.Monitor dan perubahan minor lainnya, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

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
- Menambahkan fitur Data_Exfiltration dan Unsafe_Action baru ke cmdlet Deteksi Ancaman
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
* Dokumentasi yang dimodifikasi tentang pesan bantuan terkait SQL Cmdlet Pengauditan.

### <a name="azstorage"></a>Az.Storage

* Tambahkan -EnableHierarchicalNamespace untuk New-AzureRmStorageAccount
* Perbaiki masalah cmdlet Salin File tidak dapat menggunakan kembali konteks sumber di tujuan ketika tidak memasukkan -DestContext
    - Start-AzureStorageFileCopy
* Mendukung konfigurasi Situs Web Statis
    - Enable-AzureStorageStaticWebsite
    - Disable-AzureStorageStaticWebsite

### <a name="azwebsites"></a>Situs Web Az.

* Set-AzureRmWebApp dan Set-AzureRmWebAppSlot
    - Parameter baru (-AzureStoragePath) ditambahkan untuk menentukan jalur Azure Storage akan terpasang di aplikasi wadah Windows Linux dan Windows. Gunakan output cmdlet baru New-AzureRmWebAppAzureStoragePath parameter untuk mengatur jalur Azure Storage.

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
    - Cmdlet telah dimodifikasi untuk menggunakan klien SQL, bukan klien Warisan.
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
* Deskripsi Id Tenant yang diperbarui untuk Connect-AzAccount
* Pesan kesalahan perbaikan gagal masuk saat menyediakan domain penyewa
    - https://github.com/Azure/azure-powershell/issues/6936
* Perbaiki masalah terkait nama konteks yang bentrok untuk akun tanpa langganan dalam penyewa
    - https://github.com/Azure/azure-powershell/issues/7453
* Memperbaiki masalah titik akhir DataLake saat menggunakan MSI
    - https://github.com/Azure/azure-powershell/issues/7462
* Memperbaiki masalah ketika 'Disconnect-AzAccount' akan muncul jika tidak tersambung
    - https://github.com/Azure/azure-powershell/issues/7167

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan Get-AzCognitiveServicesAccountSkus operasi.

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
