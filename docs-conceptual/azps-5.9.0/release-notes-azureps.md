---
title: Catatan rilis Azure PowerShell
description: Pelajari tentang semua pembaruan terbaru untuk modul Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/10/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: fe4c9df2dd16effbd76910a6068e3354c515547b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427992"
---
# <a name="azure-powershell-release-notes"></a>Catatan rilis Azure PowerShell

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
    - 'Remove-AzStorageAccount'
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
* Menambahkan cmdlet baru untuk menggantikan nama produk lama 'virtual router' dengan nama baru 'route server' di masa mendatang.
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
* 'Add-AzServiceFabricNodeType' sekarang menyalin ekstensi LinuxDiagnostic dengan benar. Sebelumnya tidak berfungsi untuk Linux.
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
* Menambahkan cmdlet baru untuk menggantikan nama produk lama 'virtual router' dengan nama baru 'route server' di masa mendatang.
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
* Menambahkan Redundansi Zona untuk Vault Layanan Pemulihan.
* Dukungan Azure Site Recovery untuk grup penempatan Kedekatan untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk Zona Ketersediaan untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Azure Site Recovery untuk UseManagedDisk untuk penyedia HyperV ke Azure

#### <a name="azresources"></a>Az.Resources
* Menghapus jenis perwakilan pada New-AzRoleAssignment dan Set-AzRoleAssignment karena pemetaan saat ini memutus skenario tertentu

#### <a name="azsql"></a>Az.Sql
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlElasticPool' dan 'Set-AzSqlElasticPool'
* Memperbaiki regresi di 'Set-AzSqlServerAudit' saat argumen PredicateExpression disediakan

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaturan RoutingPreference dalam pembuatan/pembaruan akun Penyimpanan
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
* Memperbaiki masalah saat deskripsi tidak diisi untuk jadwal manajemen pembaruan

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
    - 'New-AzVpnGatewayNatRule'
    - 'Update-AzVpnGatewayNatRule'
    - 'Get-AzVpnGatewayNatRule'
    - 'Remove-AzVpnGatewayNatRule'
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
* Memperbarui cmdlet New-AzFirewallPolicy:
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
* Memperbarui logika saat schemaName, tableName, dan columnName sedang diekstraksi dari id perintah Klasifikasi Data SQL.
* Memperbaiki status dan bidang StatusMessage di 'Get-AzSqlDatabaseImportExportStatus' agar sesuai dengan dokumentasi
* Menambahkan cmdlet audit operasi dukungan Microsoft (DevOps): Get-AzSqlServerMSSupportAudit, Set-AzSqlServerMSSupportAudit, Remove-AzSqlServerMSSupportAudit

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan/pembaruan/pendapatan/pencantuman EnkripsiSkop akun Penyimpanan
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
* Memperbaiki masalah saat What-If menunjukkan dua cakupan grup sumber daya dengan huruf besar atau kecil yang berbeda
* Memperbarui 'Export-AzResourceGroup' untuk menggunakan SDK.
* Menambahkan info budaya untuk mengurai metode

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah saat Set-AzSqlDatabaseAudit tidak mendukung database Hyperscale dan edisi database tidak dapat ditentukan
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
* Memperbaiki masalah saat cmdlet penyebaran templat crash jika '-WhatIf' diatur pada cakupan yang lebih tinggi [#13038]
* Memperbaiki masalah saat cmdlet penyebaran templat tidak mempertahankan kasus untuk parameter templat
* Menambahkan versi API default untuk digunakan di cmdlet 'Export-AzResourceGroup'
* Menambahkan cmdlet untuk Spesifikasi Templat ('Get-AzTemplateSpec', 'Set-AzTemplateSpec', 'New-AzTemplateSpec', 'Remove-azTemplateSpec', 'Export-AzTemplateSpec')
* Menambahkan dukungan untuk menyebarkan Spesifikasi Templat menggunakan cmdlet penyebaran yang ada (melalui parameter -TemplateSpecId baru)
* Memperbarui 'Get-AzResourceGroupDeploymentOperation' untuk menggunakan SDK.
* Menghapus parameter '-ApiVersion' dari cmdlet '*-AzDeployment'.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah saat New-AzSqlDatabaseExport gagal jika networkIsolation tidak ditentukan [#13097]
* Memperbaiki masalah saat New-AzSqlDatabaseExport dan New-AzSqlDatabaseImport tidak mengembalikan OperationStatusLink di objek hasil [#13097]
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
* Matius Burleigh (@mburleigh)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13203)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13190)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13189)
  * menambahkan tautan ke cmdlet yang direferensikan (#13137)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13204)
  * Menambahkan tautan ke cmdlet PowerShell yang direferensikan dalam dokumen (#13205)

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
* Mendukung mengaktifkan/menonaktifkan/mendapatkan properti penghapusan sementara berbagi pada file Layanan akun Penyimpanan
    - 'Update-AzStorageFileServiceProperty'
    - 'Get-AzStorageFileServiceProperty'
* Mendukung daftar berbagi file termasuk akun Penyimpanan yang dihapus, dan Mendapatkan penggunaan berbagi file tunggal
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
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.
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
* Mendukung untuk mendapatkan status pemulihan blob akun Penyimpanan dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeBlobRestoreStatus
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
* Mendukung untuk Mengatur/Mendapatkan/Menghapus Kebijakan Replikasi Objek di akun Penyimpanan
    - 'New-AzStorageObjectReplicationPolicyRule'
    - 'Set-AzStorageObjectReplicationPolicy'
    - 'Get-AzStorageObjectReplicationPolicy'
    - 'Remove-AzStorageObjectReplicationPolicy'
* Mendukung pengaktifan/penonaktifan ChangeFeed di Layanan Blob akun Penyimpanan
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
* Memperbaiki masalah saat pengecualian sedang dilemparkan ketika Enum.Parse mencoba memaksa nilai null ke nilai enum yang Diaktifkan atau Dinonaktifkan [#12344]

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan enkripsi dalam fitur transit.
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightCluster'
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightClusterConfig'
* Mendukung pembuatan kluster dengan fitur link privat:
    - Menambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightCluster'
    - Menambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightClusterConfig'
* Menampilkan informasi jaringan virtual saat memanggil 'New-AzHDInsightCluster' atau 'Get-AzHDInsightCluster'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Menambahkan perubahan yang tidak berisiko: Fungsi PeerAddressType untuk Peering Privat di 'Remove-AzExpressRouteCircutPeeringConfig'.
* Perubahan kode untuk mengabaikan huruf besar atau kecil untuk parameter AddressPrefixType dan PeerAddressType.
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.

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
* Memperbaiki potensi kesalahan ketidaksensitifan huruf besar atau kecil nama server di 'New-AzSqlServer' dan 'Set-AzSqlServer'
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
* Mendukung pembuatan/pembaruan akun Penyimpanan dengan MinimumTlsVersion dan AllowBlobPublicAccess
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung pengaktifan/penonaktifan penerapan versi di Layanan Blob akun Penyimpanan
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
* Menambahkan cmdlet baru untuk Azure FirewallPolicy
    - 'New-AzFirewallPolicyDnsSetting'
    - Dukungan untuk FQDN Tujuan dalam Aturan Jaringan untuk Kebijakan Firewall
* Menambahkan dukungan untuk operasi kumpulan alamat backend
    - 'New-AzLoadBalancerBackendAddressConfig'
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'
    - 'Remove-AzLoadBalancerBackendAddressPool'
    - 'Get-AzLoadBalancerBackendAddressPool'
* Menambahkan validasi nama untuk 'New-AzIpGroup'
* Menambahkan cmdlet baru untuk Azure FirewallPolicy
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
* Mendukung pembuatan akun Penyimpanan dengan RequireInfrastructureEncryption
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
* Memperbarui versi assembly cmdlet data plane

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbarui versi assembly dari cmdlet manajemen layanan

#### <a name="azbilling"></a>Az.Billing
* Versi assembly dari cmdlet konsumsi

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
* Memperbarui versi assembly cmdlet data plane

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
* 'New-AzApiManagement' dan 'Set-AzApiManagement': Parameter baru ditambahkan: [-UserAssignedIdentity <String[]>]
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
* Memperbarui dokumen Bantuan untuk cmdlet 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVmss', 'Set-AzVMOperatingSystem' dan 'Set-AzVmssOsProfile'.
* Perubahan mencolok
    - Parameter FilterExpression dihapus dari cmdlet 'Get-AzVMImage'.
    - Parameter AssignIdentity dihapus dari cmdlet 'New-AzVmssConfig', 'New-AzVMConfig' dan 'Update-AzVM'.
    - AutomaticRepairMaxInstanceRepairsPercent dihapus dari cmdlet 'New-AzVmssConfig' dan 'Update-AzVmss'.
    - Properti AvailabilitySetsColocationStatus, VirtualMachinesColocationStatus dan VirtualMachineScaleSetsColocationStatus dihapus dari ProximityPlacementGroup.
    - Properti MaxInstanceRepairsPercent dihapus dari AutomaticRepairsPolicy.
    - Jenis AvailabilitySets, VirtualMachines, dan VirtualMachineScaleSets diubah dari <SubResource> menjadi <SubResourceWithColocationStatus>.
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
* Kebijakan akses tidak lagi default ke perwakilan saat ini

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan cmdlet untuk memanggil kueri di IoT hub untuk mengambil informasi menggunakan bahasa seperti SQL.
* Memperbaiki masalah yang mana 'Add-AzIotHubDevice' gagal membuat Perangkat Berkemampuan Edge tanpa perangkat turunan [#11597]
* Menambahkan cmdlet untuk menghasilkan token SAS untuk Iot Hub, perangkat atau modul.
* Menambahkan cmdlet untuk memanggil kueri metrik konfigurasi.
* Mengelola penyebaran otomatis IoT Edge dalam skala besar. Cmdlet baru adalah:
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
    - Cmdlet baru ditambahkan:
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
* Menjadikan KeyVersion opsional saat memperbarui akun Penyimpanan dengan KeyvaultEncryption, untuk mendukung rotasi otomatis kunci
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
* Mendukung untuk membuat atau memperbarui akun Penyimpanan dengan Autentikasi Layanan Domain Direktori Aktif Azure Files
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung ke kunci Kerberos baru atau daftar akun Penyimpanan
    -  'New-AzStorageAccountKey'
    -  'Get-AzStorageAccountKey'
* Mendukung failover akun Penyimpanan
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
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Versi PowerShell yang didukung Az.Storage: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7

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
* Mengelola konfigurasi manajemen perangkat otomatis IoT dalam skala besar. Cmdlet baru adalah:
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

## <a name="0100-preview---april-2020"></a>0.10.0-pratinjau - April 2020
### <a name="general"></a>Umum
* Modul Az sekarang tersedia dalam pratinjau di Azure Stack Hub. Hal ini memungkinkan kompatibilitas lintas platform dengan Linux dan macOs. Azure Stack Hub sekarang mendukung inti PowerShell dengan modul Az, informasi lebih lanjut [di sini](/azure-stack/operator/powershell-install-az-module)
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
* Link yang diperbarui ke dokumentasi PowerShell untuk Azure Stack Hub dapat ditemukan [di sini](/azure-stack/operator/powershell-install-az-module)

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
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Az.CosmosDB versi awal 0.1.0 dirilis
* Dukungan Az.Network ConnectionMonitor V2 ditambahkan

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
    - Cmdlet baru ditambahkan:
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
* Meningkatkan dependensi Microsoft.Azure.Management.Sql dari 1.36-pratinjau ke 1.37-pratinjau

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery mengubah dukungan untuk mesin virtual disk terkelola yang dienkripsi saat tidak aktif dengan kunci yang dikelola pelanggan untuk penyedia Azure ke Azure.
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
* Mendukung untuk mendapatkan waktu sinkronisasi terakhir akun Penyimpanan dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeGeoReplicationStats
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
* Dukungan QuotaGiB (Kuota Bersama di Gibibye) untuk nilai lebih dari 5120 di bidang Manajemen cmdlet Berbagi File dan menambahkan alias parameter 'Quota' ke parameter 'QuotaGiB'.
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
    - Memanggil pembaruan pemindaian, mengunduh pembaruan, menginstal pembaruan pada perangkat
* Menambahkan cmdlet `Get-AzDataBoxEdgeTrigger`
    - Mendapatkan informasi tentang Pemicu
* Menambahkan cmdlet `New-AzDataBoxEdgeTrigger`
    - Membuat Pemicu baru
* Menambahkan cmdlet `Remove-AzDataBoxEdgeTrigger`
    - Hapus Pemicu

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.4.0
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
* Menambahkan parameter 'MinimumTlsVersion' di cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'. Juga, menambahkan 'MinimumTlsVersion' dalam output cmdlet 'Get-AzRedisCache'.
* Menambahkan validasi pada parameter '-Size' untuk cmdlet 'Set-AzRedisCache' dan 'New-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
- Memperbarui cmdlet kebijakan untuk menggunakan api baru versi 2019-06-01 yang memiliki properti EnforcementMode baru dalam penetapan kebijakan.
- Memperbarui contoh bantuan definisi kebijakan pembuatan
- Memperbaiki bug Remove-AZADServicePrincipal -ServicePrincipalName, yang mengeluarkan referensi null saat nama perwakilan layanan tidak ditemukan.
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
* Mengganti nama `CoreQuota` di `BatchAccountContext` menjadi `DedicatedCoreQuota`. Ada juga `LowPriorityCoreQuota` baru.
  - Hal ini berdampak pada **Get-AzBatchAccount**.
* **New-AzBatchTask** parameter `-ResourceFile` sekarang mengambil koleksi objek `PSResourceFile`, yang dapat dibangun menggunakan cmdlet **New-AzBatchResourceFile** baru.
* Cmdlet **New-AzBatchResourceFile** baru untuk membantu membuat objek `PSResourceFile`. Objek ini dapat dipasok ke **New-AzBatchTask** pada parameter `-ResourceFile`.
  - Hal ini mendukung dua jenis file sumber daya baru selain cara `HttpUrl` yang ada:
    - File sumber daya berbasis `AutoStorageContainerName` mengunduh seluruh kontainer penyimpanan otomatis ke node Batch.
    - File sumber daya berbasis `StorageContainerUrl` mengunduh kontainer yang ditentukan dalam URL ke node Batch.
* Menghapus properti `ApplicationPackages` dari `PSApplication` yang dimunculkan oleh **Get-AzBatchApplication**.
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
* Menghapus **Get-AzBatchNodeAgentSku** dan menggantinya dengan **Get-AzBatchSupportedImage**.
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
* Dukungan Azure Site Recovery untuk mengonfigurasi sumber daya jaringan seperti NSG, IP publik, dan penyeimbang beban internal untuk Azure ke Azure.
* Dukungan Azure Site Recovery untuk menulis ke disk terkelola untuk vMWare ke Azure.
* Dukungan Azure Site Recovery untuk pengurangan NIC untuk vMWare ke Azure.
* Dukungan Azure Site Recovery ke jaringan yang dipercepat untuk Azure ke Azure.
* Dukungan Azure Site Recovery ke agen pembaruan otomatis untuk Azure ke Azure.
* Dukungan Azure Site Recovery ke SSD Standar untuk Azure ke Azure.
* Dukungan Azure Site Recovery ke dua langkah Azure Disk Encryption untuk Azure ke Azure.
* Dukungan Azure Site Recovery untuk melindungi disk yang baru ditambahkan untuk Azure ke Azure.
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
    - Cmdlet baru ditambahkan:
        - Add-AzVirtualHubRoute
        - Add-AzVirtualHubRouteTable
        - Get-AzVirtualHubRouteTable
        - Remove-AzVirtualHubRouteTable
        - Set-AzVirtualHub
* Menambahkan dukungan untuk properti baru Sku dari VirtualHub dan VirtualWANType dari VirtualWan
    - Cmdlet diperbarui dengan parameter opsional:
        - New-AzVirtualHub : menambahkan parameter Sku
        - Update-AzVirtualHub : menambahkan parameter Sku
        - New-AzVirtualWan : menambahkan parameter VirtualWANType
        - Update-AzVirtualWan : menambahkan parameter VirtualWANType
* Menambahkan dukungan untuk properti EnableInternetSecurity untuk HubVnetConnection, VpnConnection, dan ExpressRouteConnection
    - Cmdlet baru ditambahkan:
        - Update-AzureRmVirtualHubVnetConnection
    - Cmdlet diperbarui dengan parameter opsional:
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
    - Cmdlet diperbarui dengan parameter opsional:
        - New-AzApplicationGatewayFirewallPolicy : menambahkan parameter PolicySetting, ManagedRule
* Menambahkan dukungan untuk operator Geo-Match di CustomRule
    - Menambahkan GeoMatch ke operator di FirewallCondition
* Menambahkan dukungan untuk kebijakan Firewall perListener dan perSite
    - Cmdlet diperbarui dengan parameter opsional:
        - New-AzApplicationGatewayHttpListener : menambahkan parameter FirewallPolicy, FirewallPolicyId
        - New-AzApplicationGatewayPathRuleConfig : menambahkan parameter FirewallPolicy, FirewallPolicyId
* Memperbaiki subnet yang diperlukan dengan nama AzureBastionSubnet di 'PSBastion' tidak peka huruf besar atau kecil
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
* Penerima grup tindakan baru ditambahkan untuk grup tindakan   -ItsmReceiver   -VoiceReceiver   -ArmRoleReceiver   -AzureFunctionReceiver   -LogicAppReceiver   -AutomationRunbookReceiver   -AzureAppPushReceiver
* Menggunakan skema peringatan umum yang diaktifkan untuk penerima. Hal ini tidak berlaku untuk SMS, pendorongan Aplikasi Azure, ITSM, dan penerima Voice
* Webhook sekarang mendukung autentikasi direktori aktif Azure .

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru Get-AzAvailableServiceAlias yang dapat dipanggil untuk mendapatkan alias yang dapat digunakan untuk Kebijakan Titik Akhir Layanan.
* Menambahkan dukungan untuk menambahkan pemilih lalu lintas ke Koneksi Gateway Virtual Network
    - Cmdlet baru ditambahkan:
        - New-AzureRmTrafficSelectorPolicy
    - Cmdlet diperbarui dengan parameter opsional -TrafficSelectorPolicies -New-AzureRmVirtualNetworkGatewayConnection -Set-AzureRmVirtualNetworkGatewayConnection
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
* Memperbaiki metode Pencarian VHD untuk posisi relatif akhir.
* Memperbaiki masalah UltraSSD untuk New-AzVM dan Update-AzVM.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan 3 perintah baru untuk ADF V2 - Add-AzDataFactoryV2TriggerSubscription, Remove-AzDataFactoryV2TriggerSubscription, dan Get-AzDataFactoryV2TriggerSubscriptionStatus
* Memperbarui versi SDK .Net ADF ke 4.1.3

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
* Menunjuk ke Monitor SDK terbaru, yaitu 0.24.1-preview
   - Menambahkan perubahan yang tidak berisiko pada cmdlet Metrik, yaitu enumerasi Unit mendukung beberapa nilai baru. Ini adalah cmdlet hanya baca, jadi tidak akan ada perubahan dalam input cmdlet.
   - Permintaan **ActionGroups** versi api sekarang **01-06-2019**, sebelumnya **01-03-2018**. Pengujian skenario telah diperbarui untuk mengakomodasi perubahan ini.
   - Konstruktor untuk kelas **EmailReceiver** dan **WebhookReceiver** menambahkan satu argumen wajib baru, yaitu nilai Boolean yang disebut **useCommonAlertSchema**. Saat ini, nilainya ditetapkan ke **false** untuk menyembunyikan perubahan yang berisiko ini dari cmdlet. **CATATAN**: perubahan ini bersifat sementara yang harus divalidasi oleh tim Peringatan.
   - Urutan argumen untuk konstruktor **Sumber** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua tes unit untuk diperbaiki: keduanya dikompilasi, tetapi gagal lulus uji.
   - Urutan argumen untuk konstruktor **AlertingAction** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua tes unit untuk diperbaiki: keduanya dikompilasi, tetapi gagal lulus uji.
* Mendukung kriteria Ambang Dinamis untuk peringatan metrik V2
    - New-AzMetricAlertRuleV2Criteria: sekarang juga menciptakan kriteria ambang batas dinamis
    - Add-AzMetricAlertRuleV2: sekarang juga menerima kriteria ambang dinamis
* Peningkatan cmdlet Aturan Kueri Terjadwal (SQR)
 - Cmdlet akan menerima paramater 'Location' dalam kedua format, baik lokasi (misalnya eastus) atau nama tampilan lokasi (misalnya US Timur)
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
* Menambahkan Pengujian untuk kebijakan mesin virtual dan Pemulihan Akun Penyimpanan Asli

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
* Di unggahan/unduhan Azure File,support perserve properti SMB File sumber (File Attributtes, Waktu Pembuatan File, Waktu Penulisan Terakhir File) di file tujuan
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
* Memperbarui versi SDK .Net ADF ke 4.1.2
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
* Memperbaiki kesalahan ketik dokumentasi tempat 'Azure' ditulis dalam huruf kecil

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam dokumentasi bantuan

#### <a name="aznetwork"></a>Az.Network
* Memperbarui New-AzPrivateLinkServiceIpConfig
    - Tidak menggunakan lagi parameter 'PublicIpAddress' karena parameter ini tidak pernah digunakan di sisi server.
    - Menambahkan satu parameter opsional 'Primer' yang menunjukkan konfigurasi ip saat ini adalah yang utama atau tidak.
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
* Memperbaiki bug cmdlet jenis node tambahkan:
    - Bug NullReferenceException ketika grup sumber daya memiliki vmss lain yang tidak terkait dengan kluster service fabric. Memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8681
    - Memperbaiki bug ketika cmdlet gagal jika virtualNetwork berada dalam grup sumber daya yang berbeda dengan kluster. memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8407
    - Tidak menggunakan lagi cmdlet Add-AzServiceFabricApplicationCertificate

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
* Memperbarui versi SDK .Net ADF ke 4.1.0
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
        - Menambahkan parameter opsional -PrivateEndpointNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan pada titik akhir privat di subnet ini atau tidak.
        - Menambahkan parameter opsional -PrivateLinkServiceNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan untuk kebijakan jaringan pada layanan link privat di subnet ini atau tidak.
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
* menambahkan pesan verifikasi dan kesalahan untuk hak otorisasi jika hanya 'Kelola' yang ditetapkan

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
   - Memperbaiki teks bantuan untuk Parameter -Top Get-AzPolicyState
   - Menambahkan dukungan penomoran sisi klien untuk Get-AzPolicyAlias
   - Menambahkan parameter baru untuk Set-AzPolicyAssignment, -PolicyParameters dan -PolicyParametersObject
   - Beberapa dokumen dan contoh pembaruan untuk cmdlet Kebijakan

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki masalah #4938 - New-AzureRmServiceBusQueue memunculkan BadRequest saat mengatur MaxSizeInMegabytes

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
        - Melarang penggunaan 'Semua' dalam opsi -IncludedEventType dan menggantinya dengan
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
        - Tidak menggunakan lagi parameter -PublicIpName dan -VirtualNetworkName
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
* Memperbaiki sertifikat ByExistingKeyVault tambahkan yang mendapatkan thumbprint yang salah dalam beberapa kasus

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
    - Cmdlet yang diperbarui:   Export-AzLogAnalyticRequestRateByInterval   Export-AzLogAnalyticThrottledRequest   Remove-AzVM   Remove-AzVMAccessExtension   Remove-AzVMAEMExtension   Remove-AzVMChefExtension   Remove-AzVMCustomScriptExtension   Remove-AzVMDiagnosticsExtension   Remove-AzVMDiskEncryptionExtension   Remove-AzVMDscExtension   Remove-AzVMSqlServerExtension   Restart-AzVM   Set-AzVM   Set-AzVMAccessExtension   Set-AzVMADDomainExtension   Set-AzVMAEMExtension   Set-AzVMBginfoExtension   Set-AzVMChefExtension   Set-AzVMCustomScriptExtension   Set-AzVMDiagnosticsExtension   Set-AzVMDscExtension   Set-AzVMExtension   Start-AzVM   Stop-AzVM   Update-AzVM

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
* memperbaiki masalah saat menggunakan Set-AzWebApp dan Set-AzWebAppSlot dengan properti -WebApp yang menghapus tag

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
    - Cmdlet baru **New-AzApiManagementSslSetting** memungkinkan konfigurasi pengaturan 'TLS/SSL' pada 'Backend' dan 'Frontend'. Hal ini juga dapat digunakan untuk mengonfigurasi 'Cipher' seperti '3DES' dan 'ServerProtocols' seperti 'Http2' pada 'Frontend' dari layanan ApiManagement.
    - Menambahkan dukungan untuk mengonfigurasi nama host 'DeveloperPortal' pada layanan ApiManagement.
* Memperbarui cmdlet **Get-AzApiManagementSsoToken** untuk mengambil objek 'PsApiManagement' sebagai input
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
    - Untuk mengganti 'ServiceUrl' saat mengkloning API.
* Memperbarui cmdlet **New-AzApiManagementIdentityProvider**
    - Untuk mengonfigurasi 'AAD' atau 'AADB2C' dengan 'Otoritas'
    - Untuk menyiapkan 'SignupPolicy', 'SigninPolicy', 'ProfileEditingPolicy' dan 'PasswordResetPolicy'
* Memperbarui cmdlet **New-AzApiManagementSubscription**
    - Untuk menjelaskan SubscriptonModel baru menggunakan 'Cakupan' dan 'UserId'
    - Untuk memperhitungkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Menambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Memperbarui cmdlet **Set-AzApiManagementSubscription**
    - Untuk menjelaskan SubscriptonModel baru menggunakan 'Cakupan' dan 'UserId'
    - Untuk memperhitungkan model langganan lama menggunakan 'ProductId' dan 'UserId'
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
* Rilis cmdlet Manajer Penyebaran Azure Pertama yang Tersedia Secara Umum

#### <a name="azdns"></a>Az.Dns
* Delegasi NameServer DNS Otomatis
    - Membuat cmdlet zona DNS yang menerima nama zona induk sebagai parameter opsional tambahan.
    - Menambahkan catatan NS di zona induk untuk zona turunan yang baru dibuat.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Rilis cmdlet Azure FrontDoor Pertama yang Tersedia Secara Umum
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
* Mendukung Antarlangganan Azure ke pemulihan situs Azure.
* Menandai perubahan berisiko yang akan datang untuk Azure Site Recovery.
* Memperbaiki rencana tindakan akhir pemulihan Azure Site Recovery.
* Memperbaiki pemetaan jaringan Pembaruan Azure Site Recovery untuk Azure ke Azure.
* Memperbaiki arah perlindungan pembaruan Azure Site Recovery untuk Azure ke Azure pada disk terkelola.
* Perbaikan kecil lainnya.

#### <a name="azrelay"></a>Az.Relay
* Memperbaiki kesalahan ketik dalam pesan yang diterima pelanggan

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru untuk NetworkRuleSet pada Namespace layanan

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan ke Pustaka Klien Penyimpanan 10.0.1 (namespace layanan semua objek dari SDK ini berubah dari 'Microsoft.WindowsAzure.Storage. *' menjadi 'Microsoft.Azure. Storage.* ')
* Meningkatkan ke Microsoft.Azure.Management.Storage 11.0.0, untuk mendukung API baru versi 2019-04-01.
* Jenis Akun penyimpanan default di Buat Akun penyimpanan berubah dari 'Storage' menjadi 'StorageV2'
    - New-AzStorageAccount
* Mengubah output cmdlet Akun penyimpanan Sku.Name disejajarkan dengan input SkuName dengan menambahkan '-', seperti perubahan 'StandardLRS' menjadi 'Standard_LRS'
    - New-AzStorageAccount
    - Dapatkan-AkunPenyimpananAz
    - Set-AzStorageAccount

#### <a name="azwebsites"></a>Az.Websites
* Properti 'Kind' sekarang akan ditetapkan untuk objek PSSite yang dimunculkan oleh Get-AzWebApp
* Get-AzWebApp*Metrics dan Get-AzAppServicePlanMetrics ditandai sebagai tidak digunakan lagi

## <a name="180---april-2019"></a>1.8.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, silakan kunjungi: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan resourcename: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Uninstall-AzureRm untuk menghapus modul dengan benar di Mac

#### <a name="azbatch"></a>Az.Batch
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azcdn"></a>Az.Cdn
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah dengan penginstalan AEM jika id sumber daya disk memiliki kumpulan sumber daya huruf kecil di id sumber daya
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan SsisProperties jika NodeCount tidak null untuk runtime integrasi terkelola.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui teks bantuan untuk titik akhir guna menunjukkan bahwa sumber daya harus dibuat sebelum menggunakan cmdlet langganan peristiwa buat/perbarui.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru untuk NetworkRuleSet pada Namespace layanan

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azmachinelearning"></a>Az.MachineLearning
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azmedia"></a>Az.Media
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azmonitor"></a>Az.Monitor
  * Cmdlet baru untuk aturan peringatan berbasis metrik GenV2 (non klasik)
      - New-AzMetricAlertRuleV2DimensionSelection
      - New-AzMetricAlertRuleV2Criteria
      - Remove-AzMetricAlertRuleV2
      - Get-AzMetricAlertRuleV2
      - Add-AzMetricAlertRuleV2
  * Memperbarui SDK Monitor ke versi 0.22.0-pratinjau

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="aznotificationhubs"></a>Az.NotificationHubs
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.
* Memperbarui format tabel untuk SQL di mesin virtual azure
* Menambahkan metode alternatif untuk mengambil lokasi di AzureFileShare
* Memperbarui ScheduleRunDays di objek SchedulePolicy berdasarkan zona waktu

#### <a name="azrediscache"></a>Az.RedisCache
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azsql"></a>Az.Sql
* Mengganti dependensi pada SDK Monitor dengan kode umum
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.
* Menyempurnakan proses pada klasifikasi beberapa kolom.
* Menyertakan properti sku (nama sku, keluarga, kapasitas) sebagai respons dari Get-AzSqlServerServiceObjective dan format sebagai tabel secara default.
* Kemampuan untuk Get-AzSqlServerServiceObjective berdasarkan lokasi tanpa memerlukan server yang sudah ada sebelumnya di wilayah tersebut.
* Mendukung parameter zona waktu dalam pembuatan Instans Terkelola.
* Memperbaiki dokumentasi untuk kartubebas

#### <a name="azwebsites"></a>Az.Websites
* memperbaiki Set-AzWebApp dan Set-AzWebAppSlot agar tidak menghapus tag pada eksekusi
* Memperbarui cmdlet dengan kata benda jamak menjadi tunggal, dan menghentikan nama jamak.
* Memperbarui SDK WebSites.
* Menghapus properti AdminSiteName dari PSAppServicePlan.

## <a name="170---april-2019"></a>1.7.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, silakan kunjungi: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan resourcename: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

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
* Memperbarui cmdlet Set-AzDataFactoryV2 dengan parameter tambahan untuk pengaturan terkait RepoConfiguration.

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
* Mendukung Pengelolaan Properti Layanan Blob dari Akun penyimpanan tertentu dengan API bidang Manajemen
    - Update-AzStorageBlobServiceProperty
    - Get-AzStorageBlobServiceProperty
    - Enable-AzStorageBlobDeleteRetentionPolicy
    - Disable-AzStorageBlobDeleteRetentionPolicy
* -Dukungan AsJob untuk Blob dan pengunggahan file dan pengunduhan cmdlet
    - Get-AzStorageBlobContent
    - Set-AzStorageBlobContent
    - Get-AzStorageFileContent
    - Set-AzStorageFileContent

## <a name="160---march-2019"></a>1.6.0 - Maret 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum modul `Az`
* Untuk informasi lebih lanjut tentang modul `Az`, silakan kunjungi: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan resourcename: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke cmdlet Get untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Konfigurasi Batch dan Rakitan Akun Integrasi

#### <a name="azautomation"></a>Az.Automation
* Otomatisasi Azure memperbarui perubahan manajemen untuk mendukung fitur baru berikut:
    * Pengelompokan dinamis
    * Skrip Pra-Posting
    * Pengaturan Booting Ulang

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
* Mendukung untuk Mendapatkan/Mengatur/Menghapus Kebijakan Manajemen pada Akun penyimpanan
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
* Menambahkan server Sql di dukungan VM Azure
* Pembaruan SDK
* Menghapus pemeriksaan VMappContainer di Get-ProtectableItem
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
* Nama sekarang bersifat opsional dalam parameter ID yang ditetapkan untuk Restart/Start/Stop/Remove/Set-AzVM dan Save-AzVMImage
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
        - Titik akhir huruf mati.
    - Update-AzureRmEventGridSubscription: Menambahkan parameter opsional baru untuk menentukan:
        - Waktu Hidup Peristiwa,
        - Jumlah maksimum upaya pengiriman untuk peristiwa tersebut,
        - Titik akhir huruf mati.
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
    - Cmdlet diperbarui dengan parameter opsional -RewriteRuleSet
        - New-AzureRmApplicationGateway
        - New-AzureRmApplicationGatewayRequestRoutingRule
        - Add-AzureRmApplicationGatewayRequestRoutingRule
        - New-AzureRmApplicationGatewayPathRuleConfig
        - Add-AzureRmApplicationGatewayUrlPathMapConfig
        - New-AzureRmApplicationGatewayUrlPathMapConfig Menambahkan Dukungan KeyVault ke Application Gateway menggunakan Identity.
    - Cmdlet diperbarui dengan parameter opsional -KeyVaultSecretId, -KeyVaultSecret
        - Add-AzApplicationGatewaySslCertificate
        - New-AzApplicationGatewaySslCertificate
        - Set-AzApplicationGatewaySslCertificate
    - Cmdlet New-AzApplicationGateway diperbarui dengan parameter opsional -UserAssignedIdentity
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
- Mendukung penentuan sertifikat berdasarkan nama umum dan thumbprint
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
    - Dalam artikel New-AzureRmFrontDoor dan Set-AzureRmFrontDoor, memperbaiki link ke artikel cmdlet New-AzureRmFrontDoorHealthProbeSettingObject.
    - Dalam artikel New-AzureRmFrontDoorManagedRuleObject, memperbaiki link ke artikel cmdlet New-AzureRmFrontDoorRuleGroupOverrideObject.

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
* Menambahkan Pelengkap Sumber Daya ke banyak cmdlet inti - hal ini memungkinkan Anda untuk menandai nama sumber daya yang ada saat memanggil cmdlet secara interaktif

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
* Memperbaiki penambahan sertifikat ke Vmss Linux.
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
* Dukungan mendapatkan penggunaan sumber daya Penyimpanan dari lokasi tertentu, dan menambahkan pesan peringatan untuk mendapatkan penggunaan sumber daya Penyimpanan global yang sudah kedaluwarsa.
    - Get-AzStorageUsage

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung Get-AzCognitiveServicesAccountSkus tanpa akun yang ada.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki <rg> Get-AzVM -ResourceGroupName untuk memunculkan lebih dari 50 hasil jika diperlukan
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
