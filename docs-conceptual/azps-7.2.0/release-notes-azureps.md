---
description: Pelajari semua pembaruan terbaru untuk modul Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Catatan rilis Azure PowerShell
ms.openlocfilehash: e9dfd6b4bba37cd8e725ff8e387472b99850d54f
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855405"
---
# <a name="azure-powershell-release-notes"></a>Catatan rilis Azure PowerShell
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

## <a name="660---november-2021"></a>6.6.0 - November 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan versi baru klien layanan AAD menggunakan Microsoft Graph API

#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan untuk parameter baru 'NetworkPolicy', 'PodCidr', 'ServiceCidr', 'DnsServiceIP', 'DockerBridgeCidr', 'NodePoolLabel', 'AksCustomHeader' di 'New-AzAksCluster'. [#13795]
* Menambahkan peringatan tentang perubahan mencolok mendatang dari migrasi ke Microsoft Graph.
* Menambahkan dukungan untuk mengubah jumlah node dalam kumpulan node. [#12379]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbaiki bug di cmdlet 'Get-AzApiManagementTenantGitAccess'.

#### <a name="azbatch"></a>Az.Batch
* Menghapus assembly 'System.Text.Encodings.Web.dll' [#16062]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet untuk menambahkan properti VMGalleryApplication ke VM/VMSS
    - New-AzVmGalleryApplication
    - New-AzVmssGalleryApplication
    - Add-AzVmGalleryApplication
    - Add-AzVmssGalleryApplication
    - Remove-AzVmGalleryApplication
    - Remove-AzVmssGalleryApplication
* Menambahkan dukungan untuk pengaturan proksi dan debug untuk Ekstensi VM untuk SAP (AEM)
* Memperbarui New-AzGalleryImageVersion untuk mengambil properti 'Encryption' dengan benar dari parameter '-TargetRegion'.
* Memperbarui Set-AzVmBootDiagnostic ke default untuk akun penyimpanan terkelola jika tidak disediakan.
* Mengedit perilaku mengubah ke default New-AzVmss saat 'OrchestrationMode' diatur ke Fleksibel.
    - Menghapus Kumpulan NAT.
    - Menghapus UpgradePolicy. Melemparkan kesalahan jika disediakan.
    - SinglePlacementGroup harus false. Melempar kesalahan jika true.
    - Versi API Profil Jaringan adalah 2020-11-01 atau lebih baru.
    - Properti utama Konfigurasi IP Profil Jaringan diatur ke true.

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan Get-AzCosmosDBMongoDBBackupInformation untuk mengambil informasi cadangan terbaru untuk MongoDB.
* Memperbarui New-AzCosmosDBAccount, Update-AzCosmosDBAccount untuk menerima BackupStorageRedundancy
* Memperkenalkan Get-AzCosmosDBLocation untuk mencantumkan Akun Azure CosmosDB serta properti lokasinya.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan PublicNetworkAccess ke Perintah Update_AzDataFactoryV2
* Memperbarui versi SDK .Net ADF ke 4.26.0

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Meningkatkan versi api ke 2021-07-12.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan dukungan untuk Sku premium dan namespace layanan dan parameter switch opsional 'DisableLocalAuth' ke 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Mengatur konfigurasi situs netFrameworkVersion hanya untuk aplikasi V4 Windows
* Mengaktifkan pembuatan aplikasi fungsi untuk tumpukan Functions V4 [#15919]

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui SDK Manajemen IoT Hub ke versi 4.1.0 (versi-api 2021-07-10)

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan pesan peringatan mengenai perubahan mencolok mendatang ke 'New-AzKeyVaultRoleDefinition' dan 'Get-AzKeyVaultRoleDefinition'.
    - Untuk mematuhi sintaks 'New-AzRoleDefinition' dan 'Get-AzRoleDefinition', kita akan mengganti nama beberapa properti model 'PSKeyVaultPermission', yang dapat memengaruhi kedua cmdlet ini.
* Menambahkan peringatan tentang perubahan mencolok mendatang dari migrasi ke Microsoft Graph.

#### <a name="azmigrate"></a>Az.Migrate
* Menambahkan pemeriksaan untuk alamat IP yang tidak valid

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbaiki bug pada 'Set-AzOperationalInsightsLinkedService: ketika layanan tertaut tidak ada, lakukan create(update) alih-alih gagal'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup memperbaiki masalah terkait StorageConfig
* Azure Backup menambahkan NodesList dan AutoProtectionPolicy ke cmdlet Get-AzRecoveryServicesBackupProtectableItem.
* Azure Backup memperbaiki GetItemsForContainerParamSet untuk mendukung pengambilan item cadangan MAB.
* Azure Backup memperbaiki Get-AzRecoveryServicesBackupContainer untuk mendukung BackupManagementType MAB, bukan MARS.
* Menambahkan peringatan perubahan mencolok: perintah 'Get-AzRecoveryServicesBackupJob', 'Get-AzRecoveryServicesBackupContainer' dan 'Get-AzRecoveryServicesBackupProtectableItem' hanya akan mendukung alias 'BackupManagementType MAB' alih-alih 'MARS', perubahan akan berlaku dari rilis penting mendatang.
* Menambahkan dukungan untuk jenis disk ZRS untuk replikasi Azure ke Azure.
* Menambahkan informasi Zona ketersediaan dalam respons item terproteksi yang direplikasi untuk replikasi Azure ke Azure.

#### <a name="azrediscache"></a>Az.RedisCache
* Membuat contoh baru dalam dokumentasi 'New-AzRedisCache' dan 'Set-AzRedisCache'.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug mengenai kode keluar Bicep [#16055]
* Menambahkan peringatan perubahan mencolok untuk cmdlet AAD
* Menambahkan properti 'UIFormDefinition' ke Versi Spesiifkasi Templat, 'Export-AzTemplateSpec' sekarang akan menyertakan UIFormDefinition Versi Spesifikasi Templat (jika ada) sebagai bagian dari ekspor.
* Menambahkan penangkapan kesalahan untuk pembuatan penetapan peran yang gagal saat membuat Perwakilan Layanan
* Peningkatan performa untuk Get-AzPolicyAlias saat -NamespaceMatch cocok dengan namespace layanan RP tunggal

#### <a name="azsecurity"></a>Az.Security
* Memperbarui referensi paket Keamanan .NET SDK ke versi 3.0.0

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan dukungan untuk ZoneRedundant dan parameter switch opsional 'DisableLocalAuth' ke 'New-AzServiceBusNamespace' dan 'Set-AzServiceBusNamespace'

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
* Jim McCormick (@eimajtrebor), Memperbaiki kesalahan pengetikan (#16091)
* Lampson Nguyen (@lampson), Memperbarui Get-AzDataShare.md (#16015)
* @MaxMeng1985, Memperbarui Get-AzSynapseSqlPoolRestorePoint.md (#16138)
* Reggie Gibson (@regedit32), New-AzBotService: Memperbaiki konversi AppSecret menjadi teks biasa di Windows PowerShell (#16160)
* Mötz Jensen (@Splaxi), Detail BusinessIdentities tidak cocok dengan implementasi saat ini (#16141)

## <a name="650---october-2021"></a>6.5.0 - Oktober 2021
#### <a name="azaccounts"></a>Az.Accounts
* Mendukung pengambilan token akses untuk Microsoft Graph.
* Menambahkan AuthorizeRequestDelegate untuk memungkinkan modul layanan menyesuaikan audiens token.
* Memanfaatkan [AssemblyLoadContext](/dotnet/api/system.runtime.loader.assemblyloadcontext) untuk menyelesaikan masalah konflik assembly di PowerShell.
* Memperbarui Azure.Core dari 1.16.0 ke 1.19.0.

#### <a name="azattestation"></a>Az.Attestation
* Ketersediaan umum modul 'Az.Attestation'

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki pengecualian referensi null dan kesalahan pengetikan pada cmdlet 'New-AzFrontDoorCdnRule'

#### <a name="azcompute"></a>Az.Compute
* Memperbarui referensi paket Komputasi .NET SDK ke versi 49.1.0
* Memperbaiki bug pada 'Get-AzVM' yang menyebabkan output status daya salah.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan argumen DataFlowEnableQuickReuse untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mengaktifkan penggunaan kembali kluster dengan cepat dalam aktivitas alur berikutnya.
* Memperbarui versi SDK .Net ADF ke 4.25.0
* Menambahkan argumen VNetInjectionMethod untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mendukung injeksi jaringan virtual ekspres Integration Runtime Azure-SSIS.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memungkinkan pembuatan mesin aturan tanpa RouteConfigurationOverride untuk 'New-AzFrontDoorRulesEngineActionObject'.
* Memperbaiki masalah parameter DynamicCompression diabaikan dari 'New-AzFrontDoorRulesEngineActionObject'.

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung definisi peran kustom pada HSM terkelola:
    - Buat melalui 'New-AzKeyVaultRoleDefinition',
    - Hapus melalui 'Remove-AzKeyVaultRoleDefinition',
    - Filter semua peran kustom melalui 'Get-AzKeyVaultRoleDefinition -Custom'.
* Mendukung Enkripsi/Dekripsi/Bungkus/Pembukaan bungkus menggunakan kunci [#15679]
* Mengaktifkan pengelolaan sumber daya di langganan lain tanpa mengalihkan konteks dengan menambahkan `-Subscription <String>`.

#### <a name="azmaintenance"></a>Az.Maintenance
* Menambahkan dukungan pemeliharaan patch Tamu.

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk Sku, parameter ScaleUnits dari sumber daya BastionHost.
    - 'New-AzBastion'
    - 'Set-AzBastion'
* Melakukan onboard Azure Resource Manager ke Cmdlet Umum Private Link
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
* Melakukan onboard Azure HDInsight ke Cmdlet Umum Private Link

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaikan bug Azure Site Recovery untuk VMware ke Azure Reprotect, Memperbarui kebijakan, dan Menonaktifkan skenario.
* Azure Backup menambahkan dukungan untuk UserAssigned MSI pada Vault RecoveryServices.

#### <a name="azresources"></a>Az.Resources
* Menambahkan pesan kesalahan yang lebih jelas untuk kasus di mana TemplateUri tidak menerima file bicep.
* Memperbaiki kesalahan pengetikan pada deskripsi perubahan mencolok ManagementGroups [#15819].
* Memperbaiki masalah kapitalisasi tag sumber daya - kapitalisasi tag sumber daya tidak dipertahankan.
* Memperbarui ke Microsoft.Azure.Management.Authorization 2.13.0-pratinjau.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki 'Get-AzSqlDatabaseImportExportStatus' untuk melaporkan kesalahan yang dihadapi

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan Azure.Storage.Blob ke 12.10.0
* Meningkatkan Azure.Storage.Files.Shares ke 12.8.0
* Meningkatkan Azure.Storage.Files.DataLake ke 12.8.0
* Meningkatkan Azure.Storage.Queues ke 12.8.0
* Mendukung peningkatan akun penyimpanan untuk mengaktifkan HierarchicalNamespace
    -  'Invoke-AzStorageAccountHierarchicalNamespaceUpgrade'
    -  'Stop-AzStorageAccountHierarchicalNamespaceUpgrade'
* Mendukung AccessTierInferred, Tag dalam skema kebijakan inventaris blob
    - 'New-AzStorageBlobInventoryPolicyRule'
* Mendukung pembuatan/pembaruan akun penyimpanan dengan PublicNetworkAccess diaktifkan/dinonaktifkan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung pembuatan/pembaruan kontainer blob penyimpanan dengan RootSquash
    - 'New-AzRmStorageContainer'
    - 'Update-AzRmStorageContainer'
* Mendukung AllowProtectedAppendWriteAll dalam mengatur Kebijakan Kekekalan kontainer, serta menambahkan kontainer LegalHold
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
    - 'Add-AzRmStorageContainerLegalHold'

#### <a name="azstoragesync"></a>Az.StorageSync
* Memperbaiki bug di mana tidak semua properti objek PSSyncSessionStatus dan PSSyncActivityStatus diisi dengan benar.
* Hal ini memengaruhi cmdlet 'Get-AzStorageSyncServerEndpoint' saat mencoba mengakses properti output berikut:
    - SyncStatus.UploadStatus
    - SyncStatus.DownloadStatus
    - SyncStatus.UploadActivity
    - SyncStatus.DownloadActivity

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'Import-AzWebAppKeyVaultCertificate1' untuk mengatur nama default dengan kombinasi nama brankas kunci dan nama sertifikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @DSakura207, Menggunakan instans PowerState terakhir pada Status untuk status daya (#15941)
* Yannic Graber (@grabery), Mengodekan ulang Example2 (#15808)
* @joelmforsyth, Memperbaiki contoh multi-regional (#15918)
* Adam Coffman (@SysAdminforCoffee), Memperbarui Set-AzNetworkInterfaceIpConfig.md (#15846)
* Michael Howard (@x509cert), Menyusun ulang kalimat untuk memperjelas bahwa versi kunci tertentu harus disediakan (# 15886)

## <a name="640---september-2021"></a>6.4.0 - September 2021
#### <a name="azaccounts"></a>Az.Accounts
* Mengoreksi URL ke Portal Microsoft Azure dalam hasil 'Get-AzEnvironment' dan 'Get-AzContext'. [#15429]
* Membuat perubahan infrastruktur untuk mendukung pengambilalihan langganan default melalui parameter `-SubscriptionId <String>`.
    - [Az.Aks](/powershell/module/az.aks/get-azakscluster) merupakan modul pertama yang mendukungnya.

#### <a name="azaks"></a>Az.Aks
* Menyediakan `-Subscription <String>` di semua cmdlet Aks. Anda dapat mengelola sumber daya Aks di langganan lain tanpa mengalihkan konteksnya.

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan cmdlet 'Sync-AzApiManagementKeyVaultSecret' baru.
* Menambahkan cmdlet 'New-AzApiManagementKeyVaultObject' baru.
* Menambahkan parameter [-useFromLocation] opsional baru ke cmdlet 'Get-ApiManagementCache' 'New-ApiManagementCache''Update-ApiManagementCache'.
* Memperbarui cmdlet **New-AzApiManagement** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk SKU 'Isolated' baru
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
    - Menambahkan dukungan untuk menentukan 'IdentityClientId' guna menyediakan ClientId yang Ditentukan Pengguna Identitas Terkelola untuk digunakan dengan Brankas Kunci

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug: Menutup handel file input pada Import-AzAutomationRunbook

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah parameter wajib dalam cmdlet 'Get-AzCdnEndpointResourceUsage'

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter baru '-LinuxConfigurationPatchMode', '-WindowsConfigurationPatchMode', dan '-LinuxConfigurationProvisionVMAgent' ke 'Set-AzVmssOSProfile'
* Menambahkan parameter baru '-SshKeyName' dan '-GenerateSshKey' ke 'New-AzVM' untuk membuat VM menggunakan SSH
* Memperbaiki bug pada 'Add-AzVHD' di Linux yang menyebabkan unggahan gagal untuk URI tujuan tertentu
* Menambahkan cmdlet baru untuk Titik Pemulihan dan Pengambilan Titik Pemulihan:
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
* Memperbaiki bug di mana pemulihan akun database yang dihapus gagal.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan argumen subnetId untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mendukung RBAC memeriksa injeksi VNet terhadap ID sumber daya subnet alih-alih ID sumber daya VNet.
* Menambahkan cmdlet 'Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint' untuk menyediakan daftar dependensi jaringan keluar untuk runtime integrasi SSIS di Azure Data Factory yang bergabung dengan jaringan virtual.
* Menambahkan PublicNetworkAccess ke Data Factory.
* Memperbarui versi SDK .Net ADF ke 4.23.0

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung penambahan kunci EC di brankas kunci [#15699]

#### <a name="azmigrate"></a>Az.Migrate
* Mendukung UUID disk duplikat di disk sumber.
* Mendukung subnet di VNet yang sama untuk AVSet.
* Mendukung runAsAccount mengambil beberapa Vcenter di situs yang sama.

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk menambahkan properti 'Subnet' untuk kumpulan alamat backend penyeimbang beban berbasis IP.
    - 'New-AzLoadBalancerBackendAddressConfig'
* Memperbarui cmdlet untuk menambahkan properti 'TunnelInterface' untuk operasi terkait kumpulan backend.
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan multi appliance Azure Site Recovery untuk skenario pemulihan bencana VMware ke Azure menggunakan RCM sebagai sarana kontrol.
* Azure Backup memperbaiki masalah targetPhysicalPath dengan SQL CRR
* Azure Backup memperbaiki penonaktifan perlindungan untuk beban kerja SQL
* Azure Backup mengatasi bug dalam mengatur properti CMK pada rilis terbaru
* Azure Backup menghapus karakter khusus dari teks bantuan perintah register-azrecoveryservicesbackupcontainer

#### <a name="azresources"></a>Az.Resources
* Menggunakan JsonExtensions untuk serialisasi deserialisasi objek JSON untuk memastikan penggunaan pengaturan serialisasi kustom [#15552]
* Menambahkan dukungan untuk jenis perubahan 'Unsupported' dan 'NoEffect' ke penyebaran cmdlet What-If.

#### <a name="azsecurityinsights"></a>Az.SecurityInsights
* Memperbarui ke parameter 'Get-AzSentinelIncident'
    - Menambahkan '-Filter' untuk mendukung filter OData
    - Menambahkan '-OrderBy' untuk mendukung pemesanan OData
    - Menambahkan '-Max' untuk mendukung pengambilan lebih banyak dari default sebesar 1000 insiden.

#### <a name="azsql"></a>Az.Sql
* Mengubah implementasi yang mendasari 'Get-AzSqlDatabase' untuk mendukung respons paginasi dari server
* Menambahkan parameter 'ZoneRedundant' ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance' untuk mengaktifkan pembuatan dan pembaruan zona - instans redundan.
* Menambahkan bidang ZoneRedundant ke model instans terkelola sehingga menampilkan informasi mengenai zona - redundansi untuk instans yang dikembalikan oleh 'Get-AzSqlInstance'.
* Memperluas enumerasi AuditActionGroups pada audit server & database. Menambahkan DBCC_GROUP, DATABASE_OWNERSHIP_CHANGE_GROUP dan DATABASE_CHANGE_GROUP.
* Menambahkan bendera 'AsJob' ke 'Remove-AzSqlInstance'
* Menambahkan parameter 'SubnetId' ke 'Set-AzSqlInstance' untuk mendukung pembaruan SLO lintas-subnet
* Meningkatkan ke versi SDK terbaru

#### <a name="azstorage"></a>Az.Storage
* Mendukung dapatkan/atur tag blob pada blob tertentu
    -  'Get-AzStorageBlobTag'
    -  'Set-AzStorageBlobTag'
* Mendukung pembuatan blob tujuan dengan tag blob tertentu saat mengunggah/menyalin Blob
    -  'Set-AzStorageBlobContent'
    -  'Start-AzStorageBlobCopy'
* Mendukung pencantuman blob di seluruh kontainer dengan ekspresi sql filter tag blob
    -  'Get-AzStorageBlobByTag'
* Mendukung pencantuman blob di dalam kontainer dan menyertakan Tag Blob
    -  'Get-AzStorageBlob'
* Mendukung operasi jalankan blob dengan kondisi tag blob, dan menggagalkan cmdlet saat kondisi tag blob tidak cocok
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
* Memperbaiki kegagalan penghapusan item Data Lake Gen2 dengan token SAS baca saja
    -  'Remove-AzDataLakeGen2Item'
* Merevisi tujuan cek masuk yang ada dalam pindahkan item Data Lake Gen2
    -  'Move-AzDataLakeGen2Item'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan set parameter ke 'Invoke-AzStorageSyncChangeDetection'
    - Dapat memanggil cmdlet tanpa parameter -DirectoryPath dan -Path untuk memicu deteksi perubahan pada seluruh berbagi file
* Menambahkan dukungan untuk pengunggahan otoritatif sebagai bagian dari New-AzStorageSyncServerEndpoint.
* Menambahkan informasi status enumerasi perubahan cloud di objek Cloud Endpoint.
* Memperbarui objek Titik Akhir Server dengan berbagai properti kesehatan
* Menambahkan properti 'ServerName' di Titik Akhir Server dan objek Server Terdaftar untuk mendukung menampilkan FQDN server saat ini.

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Set-AzWebApp' untuk mengembalikan pesan peringatan yang valid saat gagal menambahkan -Hostname #9316
* Memperbaiki 'Get-AzWebApp' untuk mengembalikan CustomDomainVerificationId dalam respons. #9316

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Sears (@asears)
  * Memperbaiki ejaan accountname (#15779)
  * Memperbaiki Ejaan, contoh (#15780)
* @cawrites, Memperbarui New-AzDataMigrationService.md (#15646)
* @harpaul-gill, Menambahkan dukungan untuk paginasi di Sql Get Databases (#15772)
* @jeepingben, Membuat nama mutex yang aman untuk Linux (perbaiki #15653) (#15666)
* @LosManos, Dokumen: Parameter diabaikan saat mencantumkan rahasia ( #15788 )
* Mats Estensen (@matsest), dokumen: menambahkan contoh untuk Update-AzSubscription (#15748)
* Mauricio Arroyo (@mauricio-msft), Memperbaiki kesalahan pengetikan dalam contoh cmdlet (#15719 )

## <a name="630---august-2021"></a>6.3.0 - Agustus 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menonaktifkan penyimpanan otomatis konteks saat persistensi cache token gagal di Windows dan macOS
* Menambahkan versi PowerShell ke dalam rekaman telemetri
* Meningkatkan Microsoft.ApplicationInsights dari 2.4.0 ke 2.12.0
* Memperbarui Azure.Core ke 1.16.0

#### <a name="azaks"></a>Az.Aks
* Menambahkan 'Start-AzAksCluster', 'Stop-AzAksCluster', 'Get-AzAksUpgradeProfile' dan 'Get-AzAksNodePoolUpgradeProfile'. [#14194]
* Menambahkan properti 'IdentityProfile' dalam output 'Get-AzAksCluster'. [#12546]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* [Perubahan Mencolok] Mengubah jenis PSCognitiveServicesAccount.Identity.Type dari IdentityType menjadi ResourceIdentityType.
* [Perubahan Mencolok] Mengubah jenis PSCognitiveServicesAccount.Sku.Tier dari SkuTier menjadi string.
* [Perubahan Mencolok] Menghapus ActionRequired dari PrivateLinkServiceConnectionState.
* Memperbarui PowerShell untuk menggunakan versi 2021-04-30.
* Menambahkan cmdlet 'Undo-AzCognitiveServicesAccountRemoval'.
* Menambahkan parameter '-RestrictOutboundNetworkAccess', '-AllowedFqdnList', '-DisableLocalAuth', '-KeyVaultIdentityClientId', '-IdentityType', '-UserAssignedIdentityId' ke 'New-AzureCognitiveServicesAccount' dan 'Set-AzureCognitiveServicesAccount'.
* Menambahkan parameter '-InRemovedState', '-Location' ke 'Remove-AzureCognitiveServicesAccount' dan 'Get-AzureCognitiveServicesAccount'.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki peringatan pada cmdlet 'New-AzVM' yang menyatakan sku VM sedang dikembalikan ke default bahkan jika ukuran sku disediakan oleh pengguna. Sekarang ini hanya terjadi ketika pengguna tidak memberikan ukuran sku.
* Mengedit cmdlet 'Set-AzVmOperatingSystem' untuk tidak lagi menimpa nilai EnableAutomaticUpdates yang ada pada yang diteruskan di mesin virtual jika ada.
* Memperbarui modul Komputasi untuk menggunakan .Net SDK versi terbaru 48.0.0.
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
* Memperbarui ke versi api 2021-02-10.

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan parameter 'ResourceGroupName' kembali untuk set parameter 'Add-AzAutoscaleSetting' 'AddAzureRmAutoscaleSettingUpdateParamGroup' dan menjadikannya opsional [#15491]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Arsip untuk brankas V1.
* Menambahkan ProtectedItemsCount di Get-AzRecoveryServicesBackupProtectionPolicy.
* Perbaikan bug pemulihan situs Azure untuk azure ke azure pada properti perbarui vm.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'RedisVersion' di 'New-AzRedisCache' dan 'Set-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug dengan 'PSResource' di mana beberapa konstruktor meninggalkan properti 'SubscriptionId' tanpa ditetapkan/null.  [#10783]
* Menambahkan dukungan untuk membuat dan memperbarui Spesifikasi Templat dalam file Bicep [#15313]
* Menambahkan parameter '-ProceedIfNoChange' ke cmdlet buat penyebaran.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki model Aplikasi Terkelola dan Klasik (Aplikasi, Kluster, Layanan) dengan memperbarui konstruktor untuk mengambil semua properti baru
    - Hal ini memecahkan masalah terkait penyaluran di mana menyalurkan hasil langsung dari panggilan cmdlet Get ke dalam dan panggilan Update atau Set menghapus beberapa properti yang sengaja diatur
    - Memperbarui file pengujian yang sesuai untuk mencakup kasus-kasus yang disebutkan di atas

#### <a name="azsql"></a>Az.Sql
* Memperbaiki logika identitas di 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Mendukung Waktu Akses Terakhir Blob
    -  'Enable-AzStorageBlobLastAccessTimeTracking'
    -  'Disable-AzStorageBlobLastAccessTimeTracking'
    -  'Add-AzStorageAccountManagementPolicyAction'
* Membuat 'Get-AzDataLakeGen2ChildItem' mencantumkan semua item datalake gen2 secara default alih-alih membutuhkan pengguna untuk mencantumkan potongan demi potongan.
* Memperbaiki masalah BlobProperties kosong saat menggunakan sas tanpa prefiks '?' [#15460]
* Memperbaiki kegagalan penyalinan blob kecil secara sinkron [#15548]
    - 'Copy-AzStorageBlob'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Add-AzWebAppAccessRestrictionRule' gagal ketika pengguna tidak memiliki izin untuk mendapatkan daftar Tag Layanan #15316 dan #14862

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Borys Generalov (@bgener), Memperbarui Get-AzPolicyState.md (#15455)
* Dean Mock (@deanmock), Memperbarui New-AzAutomationSchedule.md (#15371)
* John Bevan (@JohnLBevan), #10783 - Perbaikan untuk Get-AzResource mengembalikan PSResource dengan SubscriptionId null (#15106)
* Michael Mejias Sanchez (@mikemej), Pembaruan - Memperbarui penyebaran (VNET eksternal) (#15391)
* @mjsharma, Menambahkan catatan untuk perintah alternatif (#15360)
* Ked Mardemootoo (@nocticdr), Memperbaiki beberapa kesalahan pengetikan demi kejelasan tambahan (#15428)
* Pascal Berger (@pascalberger), Memperbaiki nama parameter dalam contoh Sync-AzVirtualNetworkPeering (#15493)
* @rcabr, Perbaikan dokumen di Get-AzStorageContainer ( #15476 )
* AAron (@S-AA-RON), Memperbarui New-AzNetworkSecurityGroup.md (#15512)
* 坂本ポテコ (@sakamoto-poteko), Memperbarui New-AzVMConfig.md (#15376)
* @Shawn-Yuen, Memperbarui Remove-AzDataLakeGen2Item.md (#15388)

## <a name="621---july-2021"></a>6.2.1 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki kesalahan akses saat langganan tidak memiliki properti 'Tag' [#15425]

## <a name="620---july-2021"></a>6.2.0 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Tag, AuthorizationSource ke PSAzureSusbscripiton, serta menambahkan TenantType, DefaultDomain, TenantBrandingLogoUrl, CountryCode ke PSAzureTenant [#15220]
* Meningkatkan klien langganan ke 2021-01-01 [#15220]
* Menghapus lib umum cek masuk mode Interaktif
* Menambahkan titik akhir OperationalInsights ke lingkungan AzureChinaCloud [#15305]
* Mencetak log default modul yang dibuat otomatis dicetak ke aliran verbose

#### <a name="azaks"></a>Az.Aks
* Menambahkan parameter 'AvailabilityZone' untuk 'New-AzAksNodePool'. [#14505]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan properti baca saja 'ConnectionString' dan 'ApplicationId' ke komponen applicationinsights

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-OrchestrationMode' ke 'New-AzVmss' dan 'New-AzVmssConfig'
* Memperbarui cmdlet berikut agar berfungsi saat sumber daya menggunakan sumber citra jarak jauh menggunakan AKS atau Shared Image Gallery.
    - 'Update-AzVm'
    - 'Update-AzVmss'
    - 'Update-AzGalleryImageVersion'
* Menambahkan parameter '-EnableCrossZoneUpgrade' dan '-PrioritizeUnhealthyInstance' ke 'Set-AzVmssRollingUpgradePolicy'
* Menambahkan parameter 'AssessmentMode' ke cmdlet 'Set-AzVMOperatingSystem'.
* Memperbaiki bug pada 'Add-AzVmssNetworkInterfaceConfiguration'
* Memperbaiki IOPS dan cek masuk throughput 'Test-AzVMAEMExtension'
* Menambahkan cmdlet baru untuk versi API DiskRP 2020-12-01
    - New-AzDiskPurchasePlanConfig
    - Set-AzDiskSecurityProfile
* Mengubah Cmdlet untuk versi API DiskRP 2020-12-01
    - New-AzDiskConfig
    - New-AzSnapshotConfig
    - New-AzSnapshotUpdateConfig
    - New-AzDiskUpdateConfig
    - New-AzDiskEncryptionSetConfig
    - Update-AzDiskEncryptionSet

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Rilis ini memperkenalkan cmdlet untuk fitur Pencadangan Berkelanjutan (Pemulihan titik waktu tertentu):
  - Memperkenalkan dukungan untuk membuat akun dengan kebijakan pencadangan mode berkelanjutan.
  - Memperkenalkan dukungan untuk Pemulihan titik waktu untuk akun dengan kebijakan pencadangan mode berkelanjutan.
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
* Memperbaiki bug dengan New-AzFunctionApp saat dibuat di Azure Gov. [13379]
* Menambahkan kebutuhan cmdlet Az.Functions untuk mendukung pembuatan dan penyalinan pengaturan aplikasi dengan nilai kosong. [14511]

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
* Menambahkan dukungan untuk melihat lokasi jaringan virtual yang diperluas di konsol
    - 'New-AzVirtualNetwork'
    - 'Get-AzVirtualNetwork'
* Menambahkan dukungan untuk melihat lokasi alamat IP publik yang diperluas di konsol
    - 'New-AzPublicIpAddress'
    - 'Get-AzPublicIpAddress'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Nonaktifkan AutoProtection SQL AG.

#### <a name="azsecurity"></a>Az.Security
* Ketersediaan umum modul Az.Security
* Mengubah nama Get-AzRegulatoryComplainceAssessment menjadi Get-AzRegulatoryComplianceAssessment untuk memperbaiki kesalahan pengetikan

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter 'RestrictOutboundNetworkAccess' ke cmdlet berikut
    - 'New-AzSqlServer'
    - 'Set-AzSqlServer'
* Menambahkan cmdlet baru untuk operasi CRUD pada FQDN yang Diizinkan dari aturan Firewall Keluar     'Get-AzSqlServerOutboundFirewallRule'     'New-AzSqlServerOutboundFirewallRule'     'Remove-AzSqlServerOutboundFirewallRule'
* Memperbaiki logika identitas untuk identitas SystemAssigned,UserAssigned untuk New-AzSqlServer, New-AzSqlInstance
* Memperbarui cmdlet untuk mendapatkan dan memperbarui frekuensi pencadangan diferensial SQL database     'Get-AzSqlDatabaseBackupShortTermRetentionPolicy'     'Set-AzSqlDatabaseBackupShortTermRetentionPolicy'
* Memperbaiki masalah PUT Parsial untuk Azure Policy di 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaktifan/penonaktifan penghapusan sementara kontainer Blob
    -  'Enable-AzStorageContainerDeleteRetentionPolicy'
    -  'Disable-AzStorageContainerDeleteRetentionPolicy'
* Mendukung pencantuman kontainer Blob yang dihapus
    -  'Get-AzRmStorageContainer'
    -  'Get-AzStorageContainer'
* Mendukung pemulihan kontainer Blob yang dihapus
    -  'Restore-AzStorageContainer'
* Mendukung pengaturan SMB aman dalam properti layanan File
    - 'Update-AzStorageFileServiceProperty'
* Mendukung pembuatan akun menggunakan EnableNfsV3
    - 'New-AzStorageAccount'
* Mendukung pemasukan lebih banyak parameter salin blob dari alur [#15301]
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
* Memperbaiki masalah bahwa 'Set-AzAks' akan gagal pada Runbook Automation. [#15006]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Memperbaiki masalah bahwa 'ResourcegroupName' terlewatkan saat mengeksekusi cmdlet berikut dengan parameter 'InputObject' [#14848]
  * 'Get-AzApplicationInsightsLinkedStorageAccount'
  * 'New-AzApplicationInsightsLinkedStorageAccount'
  * 'Update-AzApplicationInsightsLinkedStorageAccount'
  * 'Remove-AzApplicationInsightsLinkedStorageAccount'

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah profil yang hilang di cmdlet 'Remove-AzCdnProfile'

#### <a name="azcompute"></a>Az.Compute
* Memperbarui modul Komputasi untuk menggunakan versi .Net SDK terbaru 47.0.0.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Menghapus tampilan info masuk berbagi file [#15224]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.19.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan fungsionalitas untuk menerima input dari alur untuk 'Get-AzEventHub' dari 'Get-AzEventHubNamespace'.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung fitur azure monitor baru di HDInsight:
    - Menambahkan cmdlet 'Get-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mendapatkan status Azure Monitor dari kluster HDInsight.
    - Menambahkan cmdlet 'Enable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mengaktifkan Azure Monitor di kluster HDInsight.
    - Menambahkan cmdlet 'Disable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan menonaktifkan Azure Monitor di kluster HDInsight.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menghapus item daftar duplikat di 'Get-AzKeyVault' [#15164]
* Menambahkan tag 'SecretManagement' ke modul 'Az.KeyVault' [#15173]

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk server rute sebagai cara yang lebih stabil untuk menambahkan konfigurasi IP.
* Menambahkan dukungan untuk mendapatkan satu sumber daya tautan pribadi.
* Menambahkan deskripsi lebih rinci mengenai GroupId di 'New-AzPrivateLinkServiceConnection'
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
* Menambahkan cmdlet untuk Menambahkan/Membuat/Memperbarui/Menghapus VirtualNetworkGatewayNatRules.
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
* Memperbarui cmdlet untuk mengekspos dua properti baca-saja dari sertifikat klien.
    - 'Get-AzApplicationGatewayTrustedClientCertificate'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Pemindahan DS lintas penyewa.
* Menghapus batasan untuk mengambil titik pemulihan hanya untuk rentang waktu 30 hari.
* Mengaktifkan CRR untuk wilayah baru.

#### <a name="azresources"></a>Az.Resources
* Memungkinkan penamaan penyebaran saat menguji penyebaran [#11497]

#### <a name="azsignalr"></a>Az.SignalR
* Diubah menjadi parameter 'Allow' dan 'Deny' cmdlet 'Update-AzSignalRNetworkAcl':
    - Menerima 'Trace' sebagai nilai yang valid.
    - Menerima '@()' sebagai koleksi kosong untuk menghapus daftar.
* Mendukung 'ResourceGroupCompleter' dan 'ResourceNameCompleter' dalam cmdlet yang berlaku.
* Menghentikan penggunaan properti 'HostNamePrefix' dari jenis output 'PSSignalRResource' dari cmdlet berikut:
    - 'Get-AzSignalR'
    - 'New-AzSignalR'
    - 'Update-AzSignalR'

#### <a name="azsql"></a>Az.Sql
* Menambahkan opsi untuk mendukung versi singkat id konfigurasi pemeliharaan untuk Instans Terkelola di cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Menambahkan HighAvailabilityReplicaCount ke 'New-AzSqlDatabaseSecondary'
* Menambahkan Properti Administrator Eksternal dan AAD ke AzSqlServer dan AzSqlInstance
    - Menambahkan opsi untuk menentukan cmdlet '-ExternalAdminName', '-ExternalAdminSid', '-EnableActiveDirectoryOnlyAuthentication' di cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
    - Menambahkan opsi untuk memperluas informasi administrator eksternal menggunakan cmdlet '-ExpandActiveDirectoryAdministrator' di 'Get-AzSqlServer' dan 'Get-AzSqlInstance'
* Memperbaiki 'Set-AzSqlDatabase' agar tidak lagi mengatur default ReadScale ke Nonaktif saat tidak ditentukan
* Memperbaiki 'Set-AzSqlServer' dan 'Set-AzSqlInstance' untuk PUT parsial hanya dengan properti identitas dan null
* Menambahkan parameter terkait UMI di cmdlet 'New-AzSqlServer', 'New-AzSqlInstance', 'Set-AzSqlServer' dan 'Set-AzSqlInstance'.
* Menambahkan parameter -AutoRotationEnabled ke cmdlet berikut:
    - 'Set-AzSqlServerTransparentDataEncryptionProtector'
    - 'Get-AzSqlServerTransparentDataEncryptionProtector'
    - 'Set-AzSqlInstanceTransparentDataEncryptionProtector'
    - 'Get-AzSqlInstanceTransparentDataEncryptionProtector'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan berbagi file dengan NFS/SMB enabledEnabledProtocol dan RootSquash, serta memperbarui berbagi dengan RootSquash
    - 'New-AzRmStorageShare'
    - 'Update-AzRmStorageShare'
* Mendukung pengaktifan Multisaluran Smb di layanan File
    -  'Update-AzStorageFileServiceProperty'
* Memperbaiki masalah salin di dalam akun yang sama dengan mengakses sumber dengan info masuk anonim, saat menyalin Blob di dalam akun yang sama dengan info masuk Oauth
* Menghapus StorageFileDataSmbShareOwner dari kumpulan nilai parameter DefaultSharePermission pada pembuatan/pembaruan akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki masalah yang mencegah penghapusan aturan berdasarkan nama dan pengenal unik di 'Remove-AzWebAppAccessRestrictionRule'
* Memperbaiki masalah di mana AlwaysOn default menjadi false di 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andy Roberts (@andyr8939), Menghapus variabel TimeGrain yang tidak digunakan dari contoh (#15062)
* Ashley Roll (@AshleyRoll), Menghapus info masuk berbagi file Write-Host yang bocor (#15225)
* Kailash Mandal (@KaishM), Memperbarui New-AzPublicIpAddress.md (#15040)
* Olivier Miossec (@omiossec), Memperbarui Get-AzExpressRouteCircuitRouteTable.md (#15054)
* Scott (@S-T-S), Memperbarui Set-AzNetworkInterface.md (#15112)
* @sohaibMSFT, Contoh Penskalaan Otomatis Application Gateway (#15071)
* @Srihsu, Memperbarui Split-AzReservation.md (#15049)
* @srozemuller, kesalahan pengetikan dalam contoh parameter resourcegroup ( #15146 )

## <a name="600---may-2021"></a>6.0.0 - Mei 2021

#### <a name="supported-versions-of-powershell"></a>Versi PowerShell yang didukung

Karena [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) Az 6.0.0 hanya didukung pada versi PowerShell berikut:
 - Windows PowerShell 5.1
 - PowerShell 7.0.6 atau lebih tinggi
 - PowerShell 7.1.3 atau lebih tinggi

Untuk informasi selengkapnya serta cara meningkatkan, lihat [Siklus Hidup modul Azure PowerShell](/powershell/azure/azureps-support-lifecycle).

#### <a name="azaccounts"></a>Az.Accounts
* Meningkatkan Azure.Identity ke 1.4 dan MSAL ke 4.30.1
* Menghapus parameter usang 'ManagedServiceHostName', 'ManagedServicePort' dan 'ManagedServiceSecret' dari cmdlet 'Connect-AzAccount', variabel lingkungan 'MSI_ENDPOINT' dan 'MSI_SECRET' dapat digunakan sebagai gantinya
* Mengkustomisasi format tampilan PSAzureRmAccount untuk menyembunyikan rahasia perwakilan layanan [#14208]
* Menambahkan parameter opsional 'AuthScope' ke 'Connect-AzAccount' untuk mendukung autentikasi fitur data plane yang ditingkatkan
* Mengatur banyaknya percobaan ulang berdasarkan variabel lingkungan [#14748]
* Mendukung autentikasi penerbit nama subjek

#### <a name="azcompute"></a>Az.Compute
* Menambahkan 'Invoke-AzVmInstallPatch' untuk mendukung penginstalan patch di VM menggunakan PowerShell.
* Memperbarui modul Komputasi untuk menggunakan versi .Net SDK terbaru 46.0.0.
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
* Menambahkan cmdlet baru: 'Start-AzContainerGroup', 'Stop-AzContainerGroup' [#10773], 'Invoke-AzContainerInstanceCommand' [#7648], 'Update-AzContainerGroup', 'Add-AzContainerInstanceOutput', 'Get-AzContainerInstanceCachedImage', 'Get-AzContainerInstanceCapability', 'Get-AzContainerInstanceUsage', 'New-AzContainerGroupImageRegistryCredentialObject', 'New-AzContainerGroupPortObject', 'New-AzContainerGroupVolumeObject', 'New-AzContainerInstanceEnvironmentVariableObject', 'New-AzContainerInstanceInitDefinitionObject', 'New-AzContainerInstanceObject', 'New-AzContainerInstancePortObject' dan 'New-AzContainerInstanceVolumeMountObject'
* Mendukung parameter Log Analytics dalam 'New-AzContainerGroup' [#11117]
* Menambahkan dukungan untuk menentukan profil jaringan dan nama Azure File Share di 'New-AzContainerGroup' [#9993] [#12218]
* Menambahkan dukungan untuk menentukan variabel lingkungan sebagai SecureValue [#10110] [#10640]

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki masalah nama pengguna dan kata sandi pada 'Import-AzContainerRegistryImage' [#14971]
* Memperbaiki operasi data plane (repositori, tag, manifes) gagal melintasi registri dalam satu sesi Powershell [#14849]

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan dukungan untuk data plane Sql RBAC, memungkinkan pembuatan, pembaruan, penghapusan, dan pengambilan Definisi Peran dan Penetapan Peran
  - Cmdlet berikut ditambahkan:
    - Get-AzCosmosDBSqlRoleDefinition, Get-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlRoleDefinition, New-AzCosmosDBSqlRoleAssignment,
    - Remove-AzCosmosDBSqlRoleDefinition, Remove-AzCosmosDBSqlRoleAssignment,
    - Update-AzCosmosDBSqlRoleDefinition, Update-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlPermission

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Meningkatkan versi api ke 2021-02-01-pratinjau.

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dukungan dalam pembuatan aplikasi fungsi untuk aplikasi fungsi Python 3.9 dan Node 14
* Menghapus dukungan dalam pembuatan aplikasi fungsi untuk aplikasi fungsi V2, Python 3.6, Node 8, dan Node 10
* Memperbarui parameter IdentityID dari string ke array string pada Update-AzFunctionApp. Ini harus konsisten dengan New-AzFunctionApp yang memiliki parameter yang sama dengan array string.
* Memperbarui FullyQualifiedErrorId untuk versi Functions yang tidak valid dari FunctionsVersionIsInvalid ke FunctionsVersionNotSupported
* Saat membuat aplikasi fungsi Node.js, apabila tidak ada versi runtime yang ditentukan, versi runtime default diatur ke 14, bukan 12

#### <a name="azkeyvault"></a>Az.KeyVault
* Menyediakan ukuran kunci untuk kunci RSA [#14819]

#### <a name="azkusto"></a>Az.Kusto
* Mengubah versi API ke stabil 2021-01-01

#### <a name="azmaintenance"></a>Az.Maintenance
* Mengubah versi API ke stabil 2021-05-01

#### <a name="azmigrate"></a>Az.Migrate
* Memperbaiki masalah pada Initialize-AzMigrateReplicationInfrastructure.ps1

#### <a name="aznetwork"></a>Az.Network
* Memperbarui validasi untuk memungkinkan melewati nilai nol untuk parameter saDataSizeKilobytes
    - 'New-AzureRmIpsecPolicy'
* Menambahkan parameter opsional '-EdgeZone' ke cmdlet berikut:
    - 'New-AzNetworkInterface'
    - 'New-AzPublicIpAddress'
    - 'New-AzVirtualNetwork'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki masalah keamanan pada pemulihan SQL, ini adalah perubahan mencolok yang diperlukan. TargetContainer menjadi wajib untuk Pemulihan Lokasi Alternatif.
* Menghapus alias cmdlet Set-AzRecoveryServicesBackupProperties, Set-AzRecoveryServicesBackupProperty didukung.
* Menghapus alias cmdlet Get-AzRecoveryServicesBackupJobDetails, Get-AzRecoveryServicesBackupJobDetail didukung.
* Menambahkan dukungan untuk Pemindahan DS lintas langganan.
* Dukungan Azure Site Recovery untuk skenario pemulihan bencana VMware ke Azure menggunakan RCM sebagai sarana kontrol.

#### <a name="azresources"></a>Az.Resources
* Mengubah '-IdentifierUris' di 'New-AzADApplication' menjadi parameter opsional
* Menghapus 'DisplayName' ADApplication yang dibuat oleh 'New-AzADServicePrincipal'
* Memperbarui SDK ke 3.13.1-pratinjau untuk menggunakan Versi API TemplateSpecs GA
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
* Menghapus parameter yang tidak digunakan lagi untuk cmdlet terkelola:
    - 'ReverseProxyEndpointPort'
    - 'InstanceCloseDelayDuration'
    - 'ServiceDnsName'
    - 'InstanceCloseDelayDuration'
    - 'DropSourceReplicaOnMove'
* Memperbaiki 'Update-AzServiceFabricReliability' untuk memperbarui dengan benar jumlah instans vm dari jenis node utama pada sumber daya kluster.

#### <a name="azsql"></a>Az.Sql
* Memperbarui dokumentasi 'Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline' untuk menyertakan contoh array definisi dari array dengan satu array dalam.
* Menambahkan cmdlet 'Copy-AzSqlDatabaseLongTermRetentionBackup'
    - Menyalin cadangan LTR ke server yang berbeda
* Menambahkan cmdlet 'Update-AzSqlDatabaseLongTermRetentionBackup'
    - Memperbarui nilai Redundansi Penyimpanan Cadangan untuk pencadangan LTR
* Menambahkan CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy ke 'Get-AzSqlDatabase', 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlDatabaseSecondary', 'Set-AzSqlDatabaseSecondary', 'New-AzSqlDatabaseCopy'
    - Mengubah nilai BackupStorageRedundancy menjadi CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy untuk mencerminkan nilai saat ini dan apa yang telah diminta apabila perubahan dilakukan

#### <a name="azstorage"></a>Az.Storage
* Mendukung snapshot berbagi file
    - 'New-AzRmStorageShare'
    - 'Get-AzRmStorageShare'
    - 'Remove-AzRmStorageShare'
* Mendukung penghapusan berbagi file beserta snapshot (disewakan dan tidak disewakan), secara default penghapusan berbagi file akan gagal saat berbagi memiliki snapshot
    - 'Remove-AzRmStorageShare'
* Mendukung kebijakan inventaris blob Atur/Dapatkan/Hapus
    - 'New-AzStorageBlobInventoryPolicyRule'
    - 'Set-AzStorageBlobInventoryPolicy'
    - 'Get-AzStorageBlobInventoryPolicy'
    - 'Remove-AzStorageBlobInventoryPolicy'
* Mendukung DefaultSharePermission pada pembuatan/pembaruan akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung AllowCrossTenantReplication pada pembuatan/pembaruan akun penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung Atur Kebijakan Replikasi Objek dengan SourceAccount/DestinationAccount sebagai Id sumber daya akun Penyimpanan
    - 'Set-AzStorageObjectReplicationPolicy'
* Mendukung atur SasExpirationPeriod sebagai TimeSpan.Zero
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount
* Pastikan nama akun yang benar digunakan saat membuat info masuk akun
    - 'New-AzStorageContext'

#### <a name="azstoragesync"></a>Az.StorageSync
* Deprecated 'Invoke-AzStorageSyncFileRecall'
    - Pelanggan sebagai gantinya menggunakan 'Invoke-StorageSyncFileRecall', cmdlet yang dikirim dengan agen Azure File Sync.
* Menghapus fitur transfer data offline di 'New-AzStorageSyncServerEndpoint'.

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Mengubah versi API ke 2017-04-01-pratinjau
* Menambahkan dukungan Kluster StreamAnalytics

#### <a name="azwebsites"></a>Az.Websites
* memperbarui 'Set-AzAppServicePlan' untuk menyimpan Tag yang ada saat menambahkan Tag baru
* Memperbaiki 'Set-AzWebApp' untuk mengatur AppSettings
* memperbarui 'Set-AzWebAppSlot' untuk mengatur FtpsState
* Menambahkan dukungan untuk StaticSites.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @corichte, Memperbarui New-AzVirutalNetworkGatewayConnection Ex 1 (#14858)
* Hiroshi Yoshioka (@hyoshioka0128)
  * Kesalahan pengetikan "Azure SQL database"→"Azure SQL Database" (#14883)
  * Kesalahan pengetikan "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14891)
  * Kesalahan pengetikan "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14892)
  * Kesalahan pengetikan "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14902)
  * Kesalahan pengetikan "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14901)
  * Kesalahan pengetikan "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14900)
  * Kesalahan pengetikan "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14898)
  * Kesalahan pengetikan "Azure SQL managed instance"→"Azure SQL Managed Instance" (#14899)
* Jay Zelos (@jzelos), Memperbarui contoh 3 untuk menggunakan parameter yang benar (#14852)
* @StevePantol, Memperbarui New-AzVMwarePrivateCloud.md (#14996)

## <a name="590---may-2021"></a>5.9.0 - Mei 2021
#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan 'AcrNameToAttach' pada 'Set-AzAksCluster'. [#14692]
* Menambahkan dukungan 'AcrNameToDetach' pada 'Set-AzAksCluster'. [#14693]
* Menambahkan 'Set-AzAksClusterCredential' untuk mengatur ulang ServicePrincipal dari kluster AKS yang ada.

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk Identitas yang Ditetapkan Pengguna dan bendera PublicNetworkAccess

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung AFD Premium/SKU Standar baru

#### <a name="azcompute"></a>Az.Compute
* Memperbarui cmdlet 'Set-AzVMDiskEncryptionExtension' untuk mendukung migrasi ekstensi ADE dari dua pass (versi dengan parameter input AAD) ke pass tunggal (versi tanpa parameter input AAD).
    - Menambahkan parameter switch '-Migrate' untuk memicu alur kerja migrasi.
    - Menambahkan parameter switch '-MigrationRecovery' untuk memicu alur kerja pemulihan untuk VM yang mengalami kegagalan setelah migrasi dari dua pass ADE.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan Identitas yang Ditetapkan Pengguna ke Data Factory.
* Memperbarui versi SDK .Net ADF ke 4.18.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memungkinkan parameter SecretVersion Enable-AzFrontDoorCustomDomainHttps untuk menjadi opsional guna mendukung rotasi otomatis bawa-sertifikat-Anda-sendiri

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -IncludeVersions' saat versi saat ini dinonaktifkan [#14740]
* Menampilkan kode galat dan pesan saat memperbarui rahasia yang dihapus menyeluruh [#14800]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk Beberapa IP per NIC untuk Azure ke penyedia Azure.
* Dukungan Azure Site Recovery untuk SqlServerLicenseType untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk Set ketersediaan untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk TargetVmSize untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk ResourceTagging untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk Set Skala Mesin Virtual untuk Azure ke penyedia Azure.
* Menambahkan dukungan untuk memulihkan vm disk yang tidak dikelola sebagai disk terkelola.

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter 'ObjectType' untuk 'New-AzRoleAssignment'

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Meningkatkan perintah Kluster Terkelola untuk menggunakan Service Fabric Managed Cluster SDK versi 1.0.0 yang menggunakan penyedia sumber daya fabric layanan api-version 2021-05-01.
* 'New-AzServiceFabricManagedCluster' menambahkan parameter UpgradeCadence dan ZonalResiliency.
* 'New-AzServiceFabricManagedNodeType' menambahkan parameter DiskType, VmUserAssignedIdentity, IsStateless dan MultiplePlacementGroup.
* 'New-AzServiceFabricManagedClusterService' dan 'Set-AzServiceFabricManagedClusterService' menandai parameter untuk penghentian: InstanceCloseDelayDuration, DropSourceReplicaOnMove dan ServiceDnsName. Mereka tidak didukung.

#### <a name="azresourcemover"></a>Az.ResourceMover
* Ketersediaan umum modul 'Az.ResourceMover'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan/pembaruan akun penyimpanan dengan KeyExpirationPeriod dan SasExpirationPeriod
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung pembuatan/pembaruan akun penyimpanan dengan enkripsi keyvault dan keyvault akses dengan identitas yang ditetapkan pengguna
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Mendukung EdgeZone dalam membuat akun penyimpanan
    - 'New-AzStorageAccount'
* Memperbaiki masalah yang menghapus blob yang tidak dapat diubah akan meminta pesan yang salah.
    - 'Remove-AzStorageAccount'
* Memungkinkan pembaruan properti KeyVault Akun Penyimpanan dengan membersihkan Keyversion untuk mengaktifkan rotasi otomatis kunci [#14769]
    - 'Set-AzStorageAccount'
* Menambahkan pesan peringatan perubahan mencolok untuk perubahan mencolok cmdlet mendatang
    - 'Remove-AzRmStorageShare'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Thomas Lee (@doctordns), Memperbarui Get-AzEnvironment.md (#14704)
* Fabian (@FullByte), Contoh dengan parameter yang salah (salah ketik) (#14743)
* @gradinDotCom, Memperbarui Get-AzNetworkWatcherNextHop.md (#14813)
* Dr Greg Low (@greglow-sdu), Memperbarui Get-AzSqlServerDnsAlias.md (#14737)
* Prateek Singh (@PrateekKumarSingh)
  * memperbaiki kesalahan pengetikan (#14779)
  * memperbaiki kesalahan pengetikan (#14773)
* Remco Eissing (@remcoeissing)
  * Memperbaiki kesalahan pengetikan di Restore-AzApiManagement (#14770)
  * Contoh 2 untuk menggunakan New-AzPolicyExemption (#14716)
* @sharma224
  * Perubahan identitas pengguna (#14803)
  * Mendukung kunci yang dikelola Pelanggan (#14680)
* Yannick Dils (@yannickdils), Memperbarui penjelasan Lokasi (#14719)

## <a name="580---april-2021"></a>5.8.0 - April 2021
#### <a name="azaccounts"></a>Az.Accounts
* Kembali ke konteks valid pertama jika kunci konteks default saat ini adalah 'Default', yang bersifat tidak valid

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
* Memperbaiki bug pada 'Get-AzContainerRegistryManifest' yang menampilkan nama citra yang salah

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pengambilan vmsize default dari backend apabila pelanggan tidak menyediakan parameter terkait: '-WorkerNodeSize', '-HeadNodeSize', '-ZookeeperNodeSize', '-EdgeNodeSize', '-KafkaManagementNodeSize'.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Menambahkan dukungan untuk Acr LoginServers

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -AsPlainText' apabila rahasia tidak ditemukan [#14645]

#### <a name="azmigrate"></a>Az.Migrate
* Nullref Bug diperbaiki dalam dapatkan server yang ditemukan dan menginisialisasi commandlet infrastruktur replikasi

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan cmdlet untuk mendapatkan kategori pengaturan diagnostik untuk langganan
    - 'Get-AzSubscriptionDiagnosticSettingCategory'
* Mendukung operasi pengaturan diagnostik langganan dengan parameter baru: SubscriptionId
    - 'Get-AzDiagnosticSetting'
    - 'New-AzDiagnosticSetting'
    - 'Remove-AzDiagnosticSetting'
* Mendukung parameter 'AutoMitigate' dalam properti aturan pemberitahuan metrik. Bendera menandakan apakah peringatan harus diselesaikan secara otomatis atau tidak.

#### <a name="azresources"></a>Az.Resources
* Menambahkan peringatan perubahan mencolok mendatang di bawah cmdlet, karena nilai parameter 'IdentifierUris' akan memerlukan domain terverifikasi.
  - 'New-AzADApplication'
  - 'Update-AzADApplication'
  - 'New-AzADServicePrincipal'
  - 'Update-AzADServicePrincipal'
* Mengabaikan pesan peringatan Bicep dalam aliran kesalahan apabila kode keluar sama dengan nol.

#### <a name="azsql"></a>Az.Sql
* Menambahkan peringatan perubahan mencolok output cmdlet menjadi seperti berikut:
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
* Memperbaiki kegagalan penyalinan blob dengan konteks sumber sebagai Oauth [#14662]
    -  'Start-AzStorageBlobCopy'

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Menambahkan pesan perubahan mencolok mendatang ke semua cmdlet karena perubahan mendatang terhadap parameter.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrei Zhukouski (@BurgerZ), Memperbaiki kesalahan pengetikan (#14575)
* Mark Allison (@markallisongit), Memperbarui Invoke-AzSqlInstanceFailover.md (#14603)

## <a name="570---march-2021"></a>5.7.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki pesan peringatan yang salah di Windows PowerShell [#14556]
* Mengatur variabel Azure Environment 'AzureKeyVaultServiceEndpointResourceId' berdasarkan nilai 'AzureKeyVaultDnsSuffix' saat menemukan lingkungan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah untuk memulai runbook Python3 dengan parameter

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.15.0

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki bahwa 'New-AzServiceBusAuthorizationRuleSASToken' mengembalikan token yang tidak valid. [#12975]

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui SDK dan model IoT Hub Management ke versi 3.0.0 (api-version 2020-03-01)

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung desain API baru yang mendatang untuk 'Export-AzKeyVaultSecurityDomain'
* Memperbaiki beberapa kesalahan pengetikan dalam pesan cmdlet [#14341]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk menggantikan nama produk lama 'virtual router' dengan nama baru 'route server' di masa mendatang.
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - Menambahkan peringatan atribut penghentian ke cmdlet lama.
* Memperbarui 'set-azExpressRouteGateway' untuk mengizinkan parameter -MinScaleUnits tanpa menentukan -MaxScaleUnits
* Memperbarui cmdlet untuk mengaktifkan pengaturan VpnLinkConnectionMode pada VpnSiteLinkConnections.
    - 'New-AzVpnSiteLinkConnection'
    - 'Update-AzVpnConnection'
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Tautan Situs VPN.
    - 'Get-VpnSiteLinkConnectionIkeSa'
* Menambahkan cmdlet baru untuk mengatur ulang Koneksi Virtual Network Gateway.
    - 'Reset-AzVirtualNetworkGatewayConnection'
* Menambahkan cmdlet baru untuk mengatur ulang Koneksi Tautan Situs Vpn.
    - 'Reset-VpnSiteLinkConnection'
* Memperbarui cmdlet untuk mengaktifkan pengaturan parameter opsional -TrafficSelectorPolicies
    - 'New-AzVpnConnection'
    - 'Update-AzVpnConnection'
* Perbaikan bug untuk memperbarui vpnServerConfiguration.
* Menambahkan scenarioTest untuk p2s multi auth VWAN.
* Menambahkan dukungan fitur multi-otorisasi untuk VNG
    - 'Get-AzVpnClientConfiguration'
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Pemulihan Lintas Zonal untuk mesin virtual terkelola.

#### <a name="azredisenterprisecache"></a>Az.RedisEnterpriseCache
* Versi GA dari Az.RedisEnterpriseCache

#### <a name="azresources"></a>Az.Resources
* Mengarahkan pesan bicep ke aliran verbose
* Menghapus logika menyalin file templat Bicep ke folder temp.
* Menambahkan dukungan jenis sumber daya pengecualian kebijakan
* Memperbaiki fungsi bagaimana-jika saat menggunakan parameter '-QueryString'.
* Menormalisasi '-QueryString' yang dimulai dengan '?' untuk skenario yang melibatkan parameter dinamis.

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki bahwa 'New-AzServiceBusAuthorizationRuleSASToken' mengembalikan token yang tidak valid. [#12975]

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan parameter 'VMImagePublisher', 'VMImageOffer', 'VMImageSku', 'VMImageVersion' ke 'Add-AzServiceFabricNodeType' untuk memfasilitasi pembuatan citra OS alternatif yang mudah untuk jenis node baru.
* Menambahkan parameter 'IsPrimaryNodeType' ke 'Add-AzServiceFabricNodeType' agar dapat membuat jenis node utama tambahan, untuk tujuan transisi jenis node utama ke yang lain dalam kasus migrasi OS.
* 'Add-AzServiceFabricNodeType' sekarang menyalin ekstensi LinuxDiagnostic dengan benar. Ini sebelumnya tidak berfungsi untuk Linux.
* 'Add-AzServiceFabricNodeType' sekarang menyalin pemetaan port NAT masuk penyeimbang beban RDP/SSH dengan benar ke jenis node baru.
* Menambahkan templat untuk 'UbuntuServer1804' untuk membuat kluster Ubuntu 18.04 menggunakan 'New-AzServiceFabricCluster'.
* 'Remove-AzServiceFabricNodeType' secara tidak sengaja memblokir jenis node ketahanan Perunggu untuk dihapus, dan ini telah diperbarui untuk hanya memblokir ketika tingkat ketahanan Perunggu berbeda antara jenis node SF dan pengaturan VMSS.
* Menambahkan cmdlet 'Update-AzServiceFabricVmImage' untuk memperbarui jenis paket runtime SF yang dikirimkan. Ini harus diubah saat memigrasikan dari Ubuntu 16 ke 18.
* Menambahkan cmdlet 'Update-AzServiceFabricNodeType' untuk memperbarui properti jenis node kluster. Untuk saat ini, ini hanya digunakan untuk memperbarui apakah jenis node tersebut adalah jenis utama melalui parameter bool '-IsPrimaryNodeType False'.
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
* Meningkatkan perintah Kluster Terkelola untuk menggunakan Service Fabric Managed Cluster SDK versi 1.0.0-beta.1 yang menggunakan penyedia sumber daya fabric layanan api-version 2021-01-01-pratinjau.

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet 'New-AzSqlServerTrustGroup'
* Menambahkan cmdlet 'Remove-AzSqlServerTrustGroup'
* Menambahkan cmdlet 'Get-AzSqlServerTrustGroup'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah di mana mencantumkan akun dari grup sumber daya tidak akan menggunakan nextlink
    - 'Get-AzStorageAccount'
* Mendukung ChangeFeedRetentionInDays saat Mengaktifkan ChangeFeed pada layanan Blob
    - 'Update-AzStorageBlobServiceProperty'

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui 'Add-AzWebAppAccessRestrictionRule' untuk mengizinkan semua Tag Layanan yang didukung dan memvalidasi terhadap API Tag Layanan.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Freddie Sackur (@fsackur), Memperbaiki token SAS yang tidak valid dari New-AzServiceBusAuthorizationRuleSASToken dan New-AzEventHubAuthorizationRuleSASToken (#14535)
* Serafín Martín (@infoTrainingym), Parameter tidak diketahui (#14515)
* João Carlos Ferra de Almeida (@Jalmeida1994), Memperbarui Get-AzAksNodePool.md (#14503)
* Liam Barnett (@liambarnett), Memperbaiki 3 kesalahan pengetikan dalam dokumen (#14335)
* @sbojjawar-Msft, Memperbarui Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline.md (#14432)
* Yannick Dils (@yannickdils), Menghapus grup sumber daya dari get-azloadbalancer ini mengakibatkan pembaruan wilayah/zona. (#14417)

## <a name="560---march-2021"></a>5.6.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Meningkatkan Azure.Identity untuk memperbaiki masalah di mana Connect-AzAccount gagal saat info masuk ADFS digunakan [#13560]

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah di mana string tidak dapat diserialisasikan dengan benar. [#14215]
* Menambahkan Dukungan untuk Jenis Runbook Python3

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EnableHotpatching' ke cmdlet 'Set-AzVMOperatingSystem' untuk mesin Windows.
* Menambahkan parameter'-PatchMode' ke set parameter Linux di cmdlet 'Set-AzVMOperatingSystem'.
* [Perubahan Mencolok] Perubahan Mencolok untuk pengguna dalam pratinjau publik untuk fitur Patching Tamu VM.
    - Menghapus properti 'RebootStatus' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Menghapus properti 'StartedBy' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Mengganti nama properti 'Kbid' menjadi 'KbId' pada objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineSoftwarePatchProperties'.
    - Mengganti nama properti 'patches' menjadi 'availablePatches' di objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineAssessPatchesResult'.
    - Mengganti nama objek 'Microsoft.Azure.Management.Compute.Models.SoftwareUpdateRebootBehavior' menjadi 'Microsoft.Azure.Management.Compute.Models.VMGuestPatchRebootBehavior'.
    - Mengganti nama objek 'Microsoft.Azure.Management.Compute.Models.InGuestPatchMode' menjadi 'Microsoft.Azure.Management.Compute.Models.WindowsVMGuestPatchMode'.
* [Perubahan Mencolok] Menghapus semua cmdlet 'ContainerService'. API Layanan Kontainer tidak digunakan lagi pada Januari 2020.
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
* Memperkenalkan parameter ServerVersion untuk Update-AzCosmosDBAccount.
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
* Memperbaiki masalah dengan penyebaran TemplateSpec di 'New-AzTenantDeployment' dan 'New-AzManagementGroupDeployment'
* Menambahkan dukungan untuk parameter '-QueryString' di cmdlet 'Test-Az*Deployments'
* Memperbaiki masalah dengan parameter dinamis saat 'New-Az*Deployments' digunakan dengan '-QueryString'
* Menambahkan dukungan untuk parameter '-TemplateParameterObject' saat menggunakan parameter '-TemplateSpecId' di cmdlet 'New-Az*Deployments'
* Memperbaiki pesan kesalahan yang tidak akurat yang diterima saat mencoba menyebarkan spesifikasi templat yang tidak ada

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan ke Microsoft.Azure.Management.Storage 19.0.0, untuk mendukung API versi baru 2021-01-01.
* Mendukung aturan akses sumber daya di NetworkRuleSet
    - 'Update-AzStorageAccountNetworkRuleSet'
    - 'Add-AzStorageAccountNetworkRule'
    - 'Remove-AzStorageAccountNetworkRule'
* Mendukung versi Blob dan jenis Blob Tambahan dalam Kebijakan Manajemen
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
* Memperbaiki masalah di mana Get-AzStorageBlobContent menggunakan karakter pemisah direktori yang salah di Linux dan MacOS [#14234]

#### <a name="azwebsites"></a>Az.Websites
* Memperkenalkan opsi untuk memberikan batas waktu kustom untuk 'Publish-AzWebApp'
* Menambahkan dukungan untuk Lingkungan Layanan Aplikasi
    - 'New-AzAppServiceEnvironment'
    - 'Remove-AzAppServiceEnvironment'
    - 'Get-AzAppServiceEnvironment'
    - 'New-AzAppServiceEnvironmentInboundServices'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @alunmj, Ejaan kecil, perubahan pemformatan (#14155)
* @chakra146, Memperbarui Add-AzLoadBalancerInboundNatPoolConfig.md (#14231)
* Martin Ehrnst (@ehrnst), Memperbaiki kesalahan pengetikan di cmdlet (#14112)
* Jan David Narkiewicz (@jdnark)
  * Contoh menggunakan New-AzAks yang merupakan cmdlet warisan dan alias untuk New-AzAksCluster. Mengubah contoh untuk menggunakan New-AzAksCluster yang merupakan cmdlet yang ditargetkan halaman dokumentasi ini. (#14088)
  * Type fox: mengubah SshKeyVaule menjadi SshKeyValue (#14087)
* Ivan Kulezic (@kukislav), Menambahkan contoh konfigurasi pemeliharaan sql mi (#14216)
* @webguynj, Memperbarui Set-AzNetworkSecurityRuleConfig.md (#14176)
* Yannick Dils (@yannickdils), Menambahkan cmdline tambahan ke contoh yang menerapkan perubahan pada penyeimbang beban (#14185)

## <a name="550---february-2021"></a>5.5.0 - Februari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Melacak kode CloudError dalam pengecualian
* Mengangkat peristiwa 'ContextCleared' ketika 'Clear-AzContext' dieksekusi

#### <a name="azaks"></a>Az.Aks
* Menyempurnakan pesan kesalahan dari kegagalan cmdlet.
* Meningkatkan penanganan pengecualian untuk menggunakan pengecualian terkait Azure PowerShell.
* Memperbaiki masalah di mana pengguna tidak dapat menggunakan perwakilan layanan yang disediakan untuk membuat kluster Kubernetes. [#13938]

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
* Menambahkan dukungan Pengecualian JSON dan RequestBodyCheck ke aturan terkelola

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
* Menarik perubahan yang dibuat di powershell yang meningkatkan batas baris permintaan. Menghapus pernyataan yang salah dari paginasi pendukung

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* memodifikasi batas validasi kebijakan sesuai layanan pencadangan.
* Menambahkan Redundansi Zona untuk Brankas Layanan Pemulihan.
* Dukungan Azure Site Recovery untuk grup penempatan Terdekat untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk Zona Ketersediaan untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk UseManagedDisk untuk HyperV ke penyedia Azure

#### <a name="azresources"></a>Az.Resources
* Menghapus jenis prinsipal pada New-AzRoleAssignment dan Set-AzRoleAssignment karena pemetaan saat ini melanggar skenario tertentu

#### <a name="azsql"></a>Az.Sql
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlElasticPool' dan 'Set-AzSqlElasticPool'
* Memperbaiki regresi di 'Set-AzSqlServerAudit' saat argumen PredicateExpression disediakan

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaturan RoutingPreference dalam pembuatan/pembaruan akun Penyimpanan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Meningkatkan Azure.Storage.Blob ke 12.8.0
* Meningkatkan Azure.Storage.Files.Shares ke 12.6.0
* Meningkatkan Azure.Storage.Files.DataLake ke 12.6.0

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk Mengimpor sertifikat brankas kunci ke WebApp.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Memperbarui Set-AzEventHub.md (#13921)
* Christoph Bergmeister [MVP] (@bergmeister), Set-AzDataLakeGen2AclRecursive.md - Memperbaiki kesalahan pengetikan (directiry -> directory) (#14082)
* Alexander Schmidt (@devdeer-alex), Memperbaiki hyperlink rusak ke pedoman kontribusi (#14009)
* @JiangYuchun, Memperbarui Get-AzApplicationGatewayAuthenticationCertificate.md (#13972)
* Sebastian Olsen (@Spacebjorn), Mengoreksi perintah contoh(#13901)

## <a name="540---january-2021"></a>5.4.0 - Januari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menampilkan id permintaan klien yang benar pada pesan debug [#13745]
* Menambahkan jenis pengecualian Azure PowerShell umum
* Mendukung API penyimpanan 2019-06-01

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah di mana deskripsi tidak diisi untuk jadwal manajemen pembaruan

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Ketersediaan umum modul 'Az.CosmosDB'
* Membatasi cmdlet New-AzCosmosDBAccount untuk melakukan panggilan pembaruan ke Akun Database yang ada.
* Memperkenalkan AnalyticalStorageTTL di SqlContainer.

#### <a name="aziothub"></a>Az.IotHub
* Memperbaiki regresi terkait pembuatan token SAS

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki masalah dalam modul Manajemen Rahasia

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki masalah di mana 'Get-AzLogicAppTriggerHistory' dan 'Get-AzLogicAppRunAction' hanya mengambil halaman pertama hasil [#9141]

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
* Memperbarui cmdlet untuk mengaktifkan pengaturan ConnectionMode pada Koneksi Gateway Jaringan Virtual.
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
    - Menambahkan parameter -Identity
    - Menambahkan parameter -UserAssignedIdentityId
    - Menambahkan parameter -IntrusionDetection
    - Menambahkan parameter -TransportSecurityName
    - Menambahkan parameter -TransportSecurityKeyVaultSecretId
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Gateway Jaringan Virtual.
    - 'Get-AzVirtualNetworkGatewayConnectionIkeSa'
* Menambahkan beberapa dukungan Autentikasi untuk p2sVpnGateway
    - Memperbarui New-AzVpnServerConfiguration dan Update-AzVpnServerConfiguration untuk memungkinkan pengaturan beberapa parameter autentikasi.
* Memperbarui cmdlet 'New-AzVpnGateway' dan 'New-AzP2sVpnGateway':
    - Menambahkan parameter EnableRoutingPreferenceInternetFlag

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan fitur Pemulihan Lintas Wilayah.
* Membloikir pengambilan konfigurasi beban kerja saat item target adalah grup ketersediaan.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk parameter -QueryString di cmdlet New-Az*Deployments

#### <a name="azsql"></a>Az.Sql
* Membuat cmdlet 'Start-AzSqlInstanceDatabaseLogReplay' sinkron, menambahkan bendera -AsJob

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki ContinuationToken tidak pernah null saat mencantumkan blob dengan -IncludeVersion
    - 'Get-AzStorageBlob'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk Sertifikat terkelola App Service
    - 'New-AzWebAppCertificate'
    - 'Remove-AzWebAppCertificate'
* Memperbaiki masalah yang menyebabkan Docker Password dihapus dari appsettings di 'Set-AzWebApp' dan 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Ivan Akcheurov (@ivanakcheurov), Memperbarui Set-AzSecurityWorkspaceSetting.md (#13877)
* @javiermarasco, Memperbarui contoh (#13837)
* @jhaprakash26, Memperbarui Set-AzVirtualNetwork.md ( #13857)
* Michael Holmes (@MichaelHolmesWP), Memperbarui New-AzStorageTableStoredAccessPolicy.md (#13871)
* Michael James (@mikejwhat), Memungkinkan Get-AzLogicAppTriggerHistory dan Get-AzLogicAppRunAction untuk mengembalikan lebih dari 30 hasil (#13846)
* @Willem-J-an, Memperbaiki bug yang menyebabkan Docker Password dihapus dari appsettings di Set-AzWebApp(Slot) (#13866)

## <a name="530---december-2020"></a>5.3.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah di mana proksi Http tidak dihormati di Windows PowerShell [#13647]
* Meningkatkan log debug dari operasi yang berjalan lama di modul yang dihasilkan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah di mana parameter 'Start-AzAutomationRunbook' tidak dapat mengonversi string yang dibungkus PSObject ke string JSON [#13240]
* Memperbaiki pelengkap lokasi untuk cmdlet New-AzAutomationUpdateManagementAzureQuery

#### <a name="azcompute"></a>Az.Compute
* Parameter baru 'VM' dalam set parameter baru 'VMParameterSet' ditambahkan ke cmdlet 'Get-AzVMDscExtensionStatus' dan 'Get-AzVMDscExtension'.

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki masalah yang dapat menyebabkan 'New-AzDatabricksVNetPeering' kembali sebelum sepenuhnya diprovisikan (https://github.com/Azure/autorest.powershell/issues/610)

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki perintah 'Invoke-AzDataFactoryV2Pipeline' untuk masalah SupportsShouldProcess

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan properti StartVMOnConnect ke kumpulan host.

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan properti: Fqdn dan EffectiveDiskEncryptionKeyUrl di kelas AzureHDInsightHostInfo.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan parameter baru '-AsPlainText' ke 'Get-AzKeyVaultSecret' untuk langsung mengembalikan rahasia dalam teks biasa [#13630]
* Mendukung pemulihan selektif kunci dari pencadangan penuh HSM terkelola [#13526]
* Memperbaiki beberapa masalah kecil [#13583] [#13584]
* Menambahkan objek ditampilkan yang hilang dari 'Get-Secret' dalam modul SecretManagement
* Memperbaiki masalah yang dapat menyebabkan brankas dibuat tanpa kebijakan akses default [#13687]

#### <a name="azkusto"></a>Az.Kusto
* Memperbarui versi API ke 2020-09-18.

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki masalah dalam menghapus cmdlet peering dan koneksi untuk skenario ExpressRouteCircuit
    - 'Remove-AzExpressRouteCircuitPeeringConfig' dan 'Remove-AzExpressRouteCircuitConnectionConfig'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan dukungan untuk hasil terpaginasi yang ditampilkan untuk Get-AzPolicyState

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Mengaktifkan fitur penghapusan sementara untuk SQL.
* Memperbaiki pemulihan AG SQL dan menghapus pemeriksaan nama kontainer.
* Mengubah format nama kontainer untuk item cadangan Azure Files.
* Menambahkan dukungan fitur CMK untuk brankas Layanan pemulihan.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah pengecualian NullRef di 'New-AzureManagedApplication' dan 'Set-AzureManagedApplication'.
* Memperbarui SDK Azure Resource Manager SDK untuk menggunakan DeploymentScripts GA api-version terbaru: 2020-10-01.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki 'Add-AzServiceFabricNodeType'. Menambahkan jenis node ke kluster fabric layanan sebelum membuat set skala mesin virtual.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki deskripsi parameter untuk perintah 'InstanceFailoverGroup'.
* Memperbarui logika di mana schemaName, tableName, dan columnName diekstraksi dari id perintah Klasifikasi Data SQL.
* Memperbaiki bidang Status dan StatusMessage di 'Get-AzSqlDatabaseImportExportStatus' agar sesuai dengan dokumentasi
* Menambahkan cmdlet audit operasi dukungan Microsoft (DevOps): Get-AzSqlServerMSSupportAudit, Set-AzSqlServerMSSupportAudit, Remove-AzSqlServerMSSupportAudit

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan/pembaruan/perolehan/pencantuman EncryptionScope akun Penyimpanan
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
* @MasterKuat, Memperbaiki pertukaran antara judul dan kode dalam dokumentasi (#13666)
* NickT (@nukeulis), Memperbarui Set-AzContext.md (#13702)
* @PaulHCode, Memperbarui Start-AzJitNetworkAccessPolicy.md - Memperbaiki Contoh untuk menampilkan cmdlet yang tepat dengan yang ditunjukkan (#13713)
* Ryan Borstelmann (@ryanborMSFT), Menghapus ID Langganan (#13715)
* Shashikant Shakya (@shshakya), Memperbarui Set-AzSqlDatabase.md (#13674)
* Sebastian Olsen (@Spacebjorn), Memperbarui Get-AzRecoveryServicesBackupItem.md (#13719)

## <a name="520---december-2020"></a>5.2.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Berhasil mengurai waktu ExpiresOn dari token mentah jika tidak bisa didapatkan dari pustaka yang mendasarinya
* Meningkatkan pesan peringatan apabila autentikasi Interaktif tidak tersedia

#### <a name="azapimanagement"></a>Az.ApiManagement
* [Perubahan Mencolok] 'New-AzApiManagementProduct' secara default tidak memiliki batas langganan.

#### <a name="azcompute"></a>Az.Compute
* Mengedit Get-AzVm untuk memfilter berdasarkan '-Name' sebelum memeriksa pembatasan akibat terlalu banyak sumber daya.
* Cmdlet baru 'Start-AzVmssRollingExtensionUpgrade'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Mendukung parameter 'Name' untuk dan nilai dari input alur untuk 'Get-AzContainerRegistryUsage' [#13605]
* Memoles pengecualian untuk 'Connect-AzContainerRegistry'

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
* [Breaking change] mendesain ulang permukaan API cmdlet yang terkait dengan HSM terkelola.

#### <a name="azmonitor"></a>Az.Monitor
* Mengubah parameter 'Rule' dari 'New-AzAutoscaleProfile' untuk menerima daftar kosong. [#12903]
* Menambahkan cmdlet baru untuk mendukung pembuatan pengaturan diagnostik yang lebih fleksibel:
    * 'Get-AzDiagnosticSettingCategory'
    * 'New-AzDiagnosticSetting'
    * 'New-AzDiagnosticDetailSetting'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Membuat perubahan nama teks bantuan dan set parameter ke cmdlet 'Restore-AzRecoveryServicesBackupItem'.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan parameter '-Tag' ke 'Set-AzTemplateSpec' dan 'New-AzTemplateSpec'
* Menambahkan dukungan tampilan Tag ke pemformat default untuk Spesifikasi Templat

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan contoh untuk 'Set-AzServiceFabricSetting' dengan parameter SettingsSectionDescription
* Memperbarui cmdlet terkaitaplikasi untuk memanggil dukungan tersebut hanya untuk sumber daya yang disebarkan ARM
* Ditandai untuk cmdlet penghentian sertifikat kluster ‘Add-AzureRmServiceFabricClusterCertificate' dan 'Remove-AzureRmServiceFabricClusterCertificate'

#### <a name="azsql"></a>Az.Sql
* Menambahkan SecondaryType untuk cmdlet berikut:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
    - 'New-AzSqlDatabaseSecondary'
* Menambahkan HighAvailabilityReplicaCount untuk cmdlet berikut:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
* Membuatkan ReadReplicaCount sebuah alias berupa HighAvailabilityReplicaCount dalam cmdlet berikut:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengunggahan ukuran Azure File hingga 4 TiB
    - 'Set-AzStorageFileContent'
* Meningkatkan Azure.Storage.Blobs ke 12.7.0
* Meningkatkan Azure.Storage.Files.Shares ke 12.5.0
* Meningkatkan Azure.Storage.Files.DataLake ke 12.5.0

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan Fitur kebijakan tingkatan sinkronisasi dengan kebijakan pengunduhan dan mode cache lokal

#### <a name="azwebsites"></a>Az.Websites
* Mencegah aturan pembatasan akses duplikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Dawson (@dawsonar802), Memperbarui Get-AzKeyVaultCertificate.md - Mendapatkan sertifikat dan menyimpannya sebagai bagian pfx untuk bekerja dengan PowerShell Core (#13557)
* @iviark, Pembaruan BYOK Powershell API Kesehatan (#13518)
* John Duckmanton (@johnduckmanton), Mengoreksi ejaan TagPatchOperation (#13508)
* Michael James (@mikejwhat)
  * Get-AzLogicAppRunHistory Help Tidy (#13513)
* Richard de Zwart (@mountain65)
  * Update Update-AzAppConfigurationStore.md (#13485)
  * Update New-AzCosmosDBAccount.md (#13490)
* @SteppingRazor, New-AzApiManagementProduct: Mengubah nilai default parameter SubscriptionsLimit menjadi Tidak Ada (#13457)
* Steve Burkett (@SteveBurkettNZ), Memperbaiki Kesalahan Pengetikan untuk parameter WorkspaceResourceId dalam contoh (#13589 )

## <a name="510---november-2020"></a>5.1.0 - November 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah yang mungkin tidak dihormati TenantId apabila menggunakan 'Connect-AzAccount -DeviceCode'[#13477]
* Menambahkan cmdlet baru 'Get-AzAccessToken'
* Memperbaiki masalah di mana kesalahan terjadi apabila jalur profil pengguna tidak dapat diakses
* Memperbaiki masalah yang menyebabkan kesalahan Write-Object selama Connect-AzAccount [#13419]
* Menambahkan parameter 'ContainerRegistryEndpointSuffix' ke: 'Add-AzEnvironment', 'Set-AzEnvironment'
* Mendukung penggangguan proses masuk dengan menekan <kbd>CTRL</kbd>+<kbd>C</kbd>
* Memperbaiki masalah yang menyebabkan 'Connect-AzAccount -KeyVaultAccessToken' tidak berfungsi [#13127]
* Memperbaiki referensi null dan metode tidak sensitif huruf besar atau kecil di 'Invoke-AzRestMethod'

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah di mana pengguna tidak dapat menggunakan perwakilan layanan untuk membuat kluster Kubernetes baru. [#13012]

#### <a name="azappconfiguration"></a>Az.AppConfiguration
* Ketersediaan umum modul 'Az.AppConfiguration'

#### <a name="azdatafactory"></a>Az.DataFactory
* Meningkatkan pesan kesalahan perintah 'New-AzDataFactoryV2LinkedServiceEncryptedCredential'

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui SDK dataplane ADLS ke 1.2.4-alpha. Perubahan: https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-124-alpha

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan cmdlet Paket MSIX baru dan memperbarui cmdlet Aplikasi.

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki perintah Kluster untuk kluster EventHub tanpa tag
* Memperbarui teks bantuan untuk PartnerNamespace perintah AzEventHubGeoDRConfiguration

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan parameter 'ResourceProviderConnection' dan 'PrivateLink' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur relai keluar dan tautan privat
* Menambahkan parameter 'AmbariDatabase' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur database Ambari kustom
* Menambahkan nilai terima 'AmbariDatabase' ke parameter 'MetastoreType' cmdlet 'Add-AzHDInsightMetastore'

#### <a name="aziothub"></a>Az.IotHub
* Memungkinkan tag di IoT Hub membuat cmdlet.

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung pembaruan tag brankas kunci

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki agar Get-AzLogicAppRunHistory hanya mengambil halaman pertama hasil

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet di bawah ini
    - 'New-AzLoadBalancerFrontendIpConfigCommand', 'Set-AzLoadBalancerFrontendIpConfigCommand', 'Add-AzLoadBalancerFrontendIpConfigCommand':
        - Menambahkan properti PublicIpAddressPrefix
        - Menambahkan properti PublicIpAddressPrefixId
* Menambahkan properti baru ke cmdlet berikut untuk memungkinkan penyeimbangan muatan global
    - 'New-AzLoadBalancer':
        - Menambahkan properti Tingkat Sku
    - 'New-AzPuplicIpAddress':
        - Menambahkan properti Tingkat Sku
    - 'New-AzPublicIpPrefix':
        - Menambahkan properti Tingkat Sku
    - 'New-AzLoadBalancerBackendAddressConfig':
        - Menambahkan properti LoadBalancerFrontendIPConfigurationId
* Memperbarui perencanaan untuk menghentikan peringatan untuk cmdlet berikut   -'New-AzVirtualHubRoute'   -'New-AzVirtualHubRouteTable'   -'Add-AzVirtualHubRoute'   -'Add-AzVirtualHubRouteTable'   -'Get-AzVirtualHubRouteTable'   -'Remove-AzVirtualHubRouteTable'
* MEnambahkan perencanaan untuk menghentikan peringatan terhadap argumen 'RouteTable' untuk cmdlet berikut   -'New-AzVirtualHub'   -'Set-AzVirtualHub'   -'Update-AzVirtualHub'
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
* Memodifikasi peringatan perubahan mencolok di cmdlet Get-AzRecoveryServicesBackupJobDetails.
* Memperbarui teks bantuan skrip sampel untuk cmdlet Set-AzRecoveryServicesBackupProtectionPolicy.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah di mana What-If menunjukkan dua cakupan grup sumber daya dengan kapitalisasi yang berbeda
* Memperbarui 'Export-AzResourceGroup' untuk menggunakan SDK.
* Menambahkan info budaya untuk mengurai metode

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah di mana Set-AzSqlDatabaseAudit tidak mendukung database Hyperscale dan edisi database tidak dapat ditentukan
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Memperbaiki bug di GetAzureSqlDatabaseReplicationLink.cs di mana parameter PartnerServerName diperiksa berdasarkan nilai, bukan kunci

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk fitur pembatasan akses baru: ServiceTag, multi-ip dan http-header

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* John Q. Martin (@johnmart82), Menambahkan informasi prasyarat firewall (#13385)
* Manikandan Duraisamy (@madurais-msft), Mengoreksi argumen PublicSubnetName (#13417)
* @mahortas, Pembaruan untuk nilai parameter -HostNames ( #13349)
* @MariachiForHire, menambahkan nilai TrafficAnalyticsInterval yang didukung (#13304)
* Michael James (@mikejwhat), Memungkinkan Get-AzLogicAppRunHistory untuk mengembalikan lebih dari 30 entri (#13393)
* Shashikant Shakya (@shshakya), Memperbarui Restore-AzSqlInstanceDatabase.md (#13404)

## <a name="500---october-2020"></a>5.0.0 - Oktober 2020
#### <a name="azaccounts"></a>Az.Accounts
* [Perubahan Mencolok] Menghapus 'Get-AzProfile' dan 'Select-AzProfile'
* Mengganti Pustaka Autentikasi Direktori Azure dengan Pustaka Autentikasi Microsoft (MSAL)

#### <a name="azaks"></a>Az.Aks
* [Perubahan Mencolok] Menghapus alias parameter 'ClientIdAndSecret' di 'New-AzAksCluster' dan 'Set-AzAksCluster'.
* [Perubahan Mencolok] Mengubah nilai default 'NodeVmSetType' di 'New-AzAksCluster' dari 'AvailabilitySet' menjadi 'VirtualMachineScaleSets'.
* [Perubahan Mencolok] Mengubah nilai default 'NetworkPlugin' di 'New-AzAksCluster' dari 'None' menjadi 'azure'.
* [Perubahan Mencolok] Menghapus parameter 'NodeOsType' di 'New-AzAksCluster' karena hanya mendukung satu nilai Linux.

#### <a name="azbilling"></a>Az.Billing
* Menambahkan cmdlet 'Get-AzBillingAccount'
* Menambahkan cmdlet 'Get-AzBillingProfile'
* Menambahkan cmdlet 'Get-AzInvoiceSection'
* Menambahkan parameter baru di cmdlet 'Get-AzBillingInvoice'
* Menghapus properti DownloadUrlExpiry, Type, BillingPeriodNames dari respons cmdlet Get-AzBillingInvoice

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung fungsionalitas multi-asal dan tautan privat

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui SDK ke 7.4.0-pratinjau.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-VmssId' ke 'New-AzVm'
* Menambahkan parameter 'PlatformFaultDomainCount' ke cmdlet 'New-AzVmss'.
* Cmdlet baru 'Get-AzDiskEncryptionSetAssociatedResource'
* Menambahkan parameter opsional 'Tier' dan 'LogicalSectorSize' ke cmdlet New-AzDiskConfig.
* Menambahkan parameter opsional 'Tier', 'MaxSharesCount', 'DiskIOPSReadOnly', dan 'DiskMBpsReadOnly' ke cmdlet 'New-AzDiskUpdateConfig'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* [Perubahan Mencolok] Memperbarui versi API ke 2019-05-01
* [Perubahan Mencolok] Menghapus SKU 'Classic' dan parameter 'StorageAccountName' dari 'New-AzContainerRegistry'
* Menambahkan cmdlet Baru: 'Connect-AzContainerRegistry', 'Import-AzContainerRegistry', 'Get-AzContainerRegistryUsage', 'New-AzContainerRegistryNetworkRule', 'Set-AzContainerRegistryNetworkRule'
* Menambahkan parameter baru 'NetworkRuleSet' ke 'Update-AzContainerRegistry'

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki bug yang dapat menyebabkan kegagalan pembaruan ruang kerja databricks tanpa `-EncryptionKeyVersion`.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.12.0
* Memperbarui versi SDK klien enkripsi ADF ke 4.14.7587.7
* Menambahkan perintah 'Stop-AzDataFactoryV2TriggerRun' dan 'Invoke-AzDataFactoryV2TriggerRun'

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Memerlukan properti Lokasi untuk membuat objek lengan tingkat atas.
        * Membuat `ApplicationGroupType` diperlukan untuk `New-AzWvdApplicationGroup`.
        * Membuat `HostPoolArmPath` diperlukan untuk `New-AzWvdApplicationGroup`.
        * Menambahkan `PreferredAppGroupType` untuk `New-AzWvdHostPool`.

#### <a name="azfunctions"></a>Az.Functions
* [Perubahan Mencolok] Menghapus parameter switch 'IncludeSlot' dari semua kecuali satu set parameter 'Get-AzFunctionApp'. Cmdlet sekarang mendukung pengambilan slot penyebaran dalam hasil saat '-IncludeSlot' ditentukan.
* Memperbarui 'New-AzFunctionApp':
  - Memperbaiki -DisableApplicationInsights sehingga tidak ada proyek wawasan aplikasi yang dibuat saat opsi ini ditentukan. [#12728]
  - [Perubahan Mencolok] Menghapus dukungan untuk membuat aplikasi fungsi PowerShell 6.2.
  - [Perubahan Mencolok] Mengubah versi runtime default di Functions versi 3 pada Windows untuk aplikasi fungsi PowerShell dari 6.2 menjadi 7.0 saat parameter RuntimeVersion tidak ditentukan.
  - [Perubahan Mencolok] Mengubah versi runtime default di Functions versi 3 di Windows dan Linux untuk aplikasi fungsi Node dari 10 menjadi 12 saat parameter RuntimeVersion tidak ditentukan.
  - [Perubahan Mencolok] Mengubah versi runtime default di Functions versi 3 di Linux untuk aplikasi fungsi Python dari 3.7 menjadi 3.8 saat parameter RuntimeVersion tidak ditentukan.

#### <a name="azhdinsight"></a>Az.HDInsight
 * Untuk cmdlet New-AzHDInsightCluster:
     - Mengganti parameter 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
     - Mengganti parameter 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
     - Mengganti parameter 'DefaultStorageAccountType' dengan 'StorageAccountType'
     - Menghapus parameter 'PublicNetworkAccessType'
     - Menghapus parameter 'OutboundPublicNetworkAccessType'
     - Menambahkan parameter baru: 'StorageFileSystem' dan 'StorageAccountManagedIdentity' untuk mendukung ADLSGen2
     - Menambahkan parameter baru 'EnableIDBroker' untuk Mendukung Broker ID HDInsight
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
* [Perubahan Mencolok] Menghentikan penggunaan parameter DisableSoftDelete di 'New-AzKeyVault' dan EnableSoftDelete di 'Update-AzKeyVault'
* [Perubahan Mencolok] Menghapus atribut SecretValueText untuk menghindari menampilkan SecretValue secara langsung [#12266]
* Mendukung jenis sumber daya baru: HSM terkelola
    - CRUD dari HSM dan cmdlet terkelola untuk mengoperasikan kunci pada HSM terkelola
    - Pencadangan/pemulihan HSM penuh, pembuatan kunci AES, pencadangan/pemulihan domain keamanan, RBAC

#### <a name="azmanagedservices"></a>Az.ManagedServices
* [Perubahan Mencolok] Memperbarui konvensi penamaan parameter dan contoh terkait

#### <a name="aznetwork"></a>Az.Network
* [Perubahan Mencolok] Menghapus parameter 'HostedSubnet' dan menambahkan 'Subnet' sebagai gantinya
* Menambahkan cmdlet baru untuk Rute Serekan Perute Virtual
    - 'Get-AzVirtualRouterPeerLearnedRoute'
    - 'Get-AzVirtualRouterPeerAdvertisedRoute'
* Memperbarui cmdlet New-AzFirewall:
    - Menambahkan parameter '-SkuTier'
    - Menambahkan parameter '-SkuName' dan menjadikan Sku sebagai Alias untuk ini
    - Menghapus paramter '-Sku'
* [Perubahan Mencolok] Menjadikan argumen 'Connectionlink' wajib di 'Start-AzVpnConnectionPacketCapture' dan 'Stop-AzVpnConnectionPacketCapture'
* [Perubahan Mencolok] Memperbarui 'New-AzNetworkWatcherConnectionMonitorEndPointObject' untuk menghapus parameter '-Filter'
* [Perubahan Mencolok] Mengganti cmdlet 'New-AzNetworkWatcherConnectionMonitorEndpointFilterItemObject' dengan 'New-AzNetworkWatcherConnectionMonitorEndpointScopeItemObject'
* Memperbarui cmdlet 'New-AzNetworkWatcherConnectionMonitorEndPointObject':
    - Menambahkan paramter '-Type'
    - Menambahkan parameter '-CoverageLevel'
    - Menambahkan parameter '-Scope'
* Memperbarui cmdlet 'New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject' dengan parameter baru '-DestinationPortBehavior'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Pemulihan Beban Kerja untuk izin kontributor.
* Menambahkan set parameter dan validasi baru untuk cmdlet Restore-AzRecoveryServicesBackupItem.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug penguraian
* Memperbarui cmdlet What-If templat ARM untuk menghapus pesan pratinjau dari hasil
* Memperbaiki masalah di mana cmdlet penyebaran templat macet apabila '-WhatIf' diatur pada cakupan yang lebih tinggi [#13038]
* Memperbaiki masalah di mana cmdlet penyebaran templat tidak mempertahankan kapitalisasi untuk parameter templat
* Menambahkan versi API default untuk digunakan di cmdlet 'Export-AzResourceGroup'
* Menambahkan cmdlet untuk Spesifikasi Templat ('Get-AzTemplateSpec', 'Set-AzTemplateSpec', 'New-AzTemplateSpec', 'Remove-AzTemplateSpec', 'Export-AzTemplateSpec')
* Menambahkan dukungan untuk menyebarkan Spesifikasi Templat menggunakan cmdlet penyebaran yang ada (melalui parameter -TemplateSpecId baru)
* Memperbarui 'Get-AzResourceGroupDeploymentOperation' untuk menggunakan SDK.
* Menghapus parameter '-ApiVersion' dari cmdlet '*-AzDeployment'.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah di mana New-AzSqlDatabaseExport gagal apabila networkIsolation tidak ditentukan [#13097]
* Memperbaiki masalah di mana New-AzSqlDatabaseExport dan New-AzSqlDatabaseImport tidak menampilkan OperationStatusLink di objek hasil [#13097]
* Memperbarui URL Wilayah Berpasangan Azure dalam Peringatan Redundansi Penyimpanan Cadangan

#### <a name="azstorage"></a>Az.Storage
* Menghapus properti RestorePolicy.LastEnabledTime yang usang
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Get-AzStorageBlobServiceProperty'
    - 'Update-AzStorageBlobServiceProperty'
* Mengubah Jenis DaysAfterModificationGreaterThan dari int menjadi int?
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyRule'
* Mendukung pembuatan/pembaruan berbagi file dengan tingkat akses
    - 'New-AzRmStorageShare'
    - 'Update-AzRmStorageShare'
* Mendukung pengaturan/pembaruan/penghapusan Acl secara berulang pada item Datalake Gen2
    -  'Set-AzDataLakeGen2AclRecursive'
    -  'Update-AzDataLakeGen2AclRecursive'
    -  'Remove-AzDataLakeGen2AclRecursive'
* Mendukung kebijakan akses Kontainer dengan izin baru x,t
    -  'New-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Mengubah output cmdlet kebijakan akses kontainer get/set, dengan mengubah properti turunan jenis Izin dari enumerasi ke String
    -  'Get-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Memperbaiki masalah skrip sampel mengatur kebijakan manajemen dengan json
    -  'Set-AzStorageAccountManagementPolicy'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk tingkat harga Premium V3
* Memperbarui SDK WebSites ke 3.1.0

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Memperbarui Get-AzDelegation.md (#13176)
* @dineshreddy007, Tetapkan Peran Aplikasi dengan benar jika terjadi pendaftaran Stack HCI menggunakan token WAC. (#13249)
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
* Memperbaiki kesalahan pengetikan dalam pesan output

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter switch opsional 'TrustedServiceAccessEnabled' ke cmdlet 'Set-AzEventHubNetworkRuleSet'

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan pesan peringatan untuk merencanakan penghentian parameter 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType'
* Menambahkan pesan peringatan untuk merencanakan penggantian parameter 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
* Menambahkan pesan peringatan untuk merencanakan penggantian parameter 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
* Menambahkan pesan peringatan untuk merencanakan penggantian parameter 'DefaultStorageAccountType' dengan 'StorageAccountType'
* Menambahkan pesan peringatan untuk merencanakan penggantian parameter 'DefaultStorageContainer' dengan 'StorageContainer'
* Menambahkan pesan peringatan untuk merencanakan penggantian parameter 'DefaultStorageRootPath' dengan 'StorageRootPath'

#### <a name="aziothub"></a>Az.IotHub
* Memperbarui sdk perangkat.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memberikan tanggal terperinci penghapusan properti SecretValueText

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Memperbarui peringatan perubahan mencolok pada cmdlet penetapan dan definisi layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug di mana pesan peringatan tidak dapat ditekan. [#12889]
* Mendukung parameter 'SkipMetricValidation' dalam kriteria aturan peringatan. Memungkinkan pembuatan aturan peringatan pada metrik kustom yang belum dipancarkan, dengan menyebabkan validasi metrik untuk dilewati.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan Kebijakan Office365 ke Sumber Daya VPNSite
    - 'New-AzO365PolicyProperty'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan validasi nama kontainer untuk pencadangan beban kerja.

#### <a name="azrediscache"></a>Az.RedisCache
* Membuat cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache' tidak gagal karena masalah izin terkait pendaftaran Microsoft.Cache RP

#### <a name="azsql"></a>Az.Sql
* Menambahkan BackupStorageRedundancy untuk cmdlet berikut:
    - 'Restore-AzureRmSqlDatabase'
    - 'New-AzSqlDatabaseCopy'
    - 'New-AzSqlDatabaseSecondary'
* Menghapus sensitivitas kapitalisasi untuk parameter BackupStorageRedundancy untuk semua referensi SQL DB
* Memperbarui nama pesan peringatan BackupStorageRedundancy

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaktifan/penonaktifan/perolehan berbagi properti penghapusan sementara pada file Layanan akun Penyimpanan
    - 'Update-AzStorageFileServiceProperty'
    - 'Get-AzStorageFileServiceProperty'
* Daftar berbagi file yang didukung mencakup file yang dihapus dari akun Penyimpanan, dan Mendapatkan penggunaan berbagi file tunggal
    - 'Get-AzRmStorageShare'
* Mendukung pemulihan berbagi file yang terhapus
    - 'Restore-AzRmStorageShare'
* Mengubah cmdlet untuk memodifikasi properti layanan blob, tidak akan mendapatkan properti asli dari server, tetapi hanya mengatur properti yang dimodifikasi ke server.
    - 'Enable-AzStorageBlobDeleteRetentionPolicy'
    - 'Disable-AzStorageBlobDeleteRetentionPolicy'
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Update-AzStorageBlobServiceProperty'
* Memperbaiki masalah bantuan untuk nilai default parameter -Kind New-AzStorageAccount [#12189]
* Memperbaiki masalah dengan menambahkan contoh untuk menunjukkan cara mengatur ContentType yang benar dalam pengunggahan blob [#12989]

## <a name="470---september-2020"></a>4.7.0 - September 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memformat pesan perubahan mencolok mendatang
* Memperbarui Azure.Core ke 1.4.1

#### <a name="azaks"></a>Az.Aks
* Menambahkan logika validasi parameter sisi klien untuk 'New-AzAksCluster', 'Set-AzAksCluster' dan 'New-AzAksNodePool'. [#12372]
* Menambahkan dukungan untuk add-on di 'New-AzAksCluster'. [#11239]
* Menambahkan cmdlet 'Enable-AzAksAddOn' dan 'Disable-AzAksAddOn' untuk add-on. [#11239]
* Menambahkan parameter 'GenerateSshKey' untuk 'New-AzAksCluster'. [#12371]
* Memperbarui versi api ke 2020-06-01.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menunjukkan persyaratan hukum tambahan untuk API tertentu.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-EncryptionType' ke 'New-AzVmDiskEncryptionSetConfig'
* Cmdlet baru untuk jenis sumber daya baru: DiskAccess 'Get-AzDiskAccess', 'New-AzDiskAccess', 'Get-AzDiskAccess'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzSnapshotConfig'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzDiskConfig'
* Menambahkan properti 'PatchStatus' ke Tampilan Instans VirtualMachine
* Menambahkan properti 'VMHealth' ke tampilan instans mesin virtual, yang merupakan objek yang ditampilkan saat 'Get-AzVm' dipanggil dengan '-Status'
* Menambahkan bidang 'AssignedHost' ke tampilan instans 'Get-AzVM' dan 'Get-AzVmss'. Bidang ini menampilkan id sumber daya instans mesin virtual
* Menambahkan parameter opsional '-SupportAutomaticPlacement' untuk 'New-AzHostGroup'
* Menambahkan parameter '-HostGroupId' untuk 'New-AzVm' dan 'New-AzVmss'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.11.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet Cluster baru - 'New-AzEventHubCluster', 'Set-AzEventHubCluster', 'Get-AzEventHubCluster', 'Remove-AzEventHubCluster', 'Get-AzEventHubClustersAvailableRegions'.
* Diperbaiki untuk masalah #10722 : Perbaikan untuk menetapkan hanya 'Dengarkan' untuk hak AuthorizationRule.

#### <a name="azfunctions"></a>Az.Functions
* Menghapus kemampuan untuk membuat Functions v2 di wilayah yang tidak mendukungnya.
* Menghentikan penggunaan Powershell 6.2. Menambahkan peringatan saat pengguna membuat aplikasi fungsi PowerShell 6.2 yang menyarankan mereka untuk membuat aplikasi fungsi PowerShell 7.0 sebagai gantinya.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan konfigurasi Penskalaan Otomatis
    - Menambahkan parameter baru 'AutoscaleConfiguration' ke cmdlet 'New-AzHDInsightCluster'
* Mendukung konfigurasi Penskalaan Otomatis kluster yang beroperasi
    - Menambahkan cmdlet baru 'Get-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'Set-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'Remove-AzHDInsihgtClusterAutoscaleConfiguration'
    - Menambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleScheduleCondition'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk otorisasi RBAC [#10557]
* Meningkatkan penanganan kesalahan pada 'Set-AzKeyVaultAccessPolicy' [#4007]

#### <a name="azkusto"></a>Az.Kusto
* Ketersediaan umum modul 'Az.Kusto'

#### <a name="aznetwork"></a>Az.Network
* [Perubahan Mencolok] Memperbarui cmdlet berikut untuk menyelaraskan router virtual sumber daya dan hub virtual
    - 'New-AzVirtualRouter':
        - Menambahkan parameter -HostedSubnet untuk mendukung sumber daya turunan konfigurasi IP
        - menghapus -HostedGateway dan -HostedGatewayId
    - 'Get-AzVirtualRouter':
        - Menambahkan set parameter tingkat langganan
    - 'Remove-AzVirtualRouter'
    - 'Add-AzVirtualRouterPeer'
    - 'Get-AzVirtualRouterPeer'
    - 'Remove-AzVirtualRouterPeer'
* Menambahkan cmdlet baru untuk Port Rute Azure Express
    - 'New-AzExpressRoutePortLOA'
* Menambahkan properti RemoteBgpCommunities ke Sumber Daya Peering VirtualNetwork
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.
* Menambahkan VpnGatewayIpConfigurations ke output 'Get-AzVpnGateway'
* Memperbaiki bug untuk 'Set-AzApplicationGatewaySslCertificate' [#9488]
* Menambahkan parameter 'AllowActiveFTP' ke 'AzureFirewall'
* Memperbarui perintah berikut untuk fitur: Aktifkan pengaturan/penghapusan keamanan internet di VirtualWan P2SVpnGateway.
- Memperbarui 'New-AzP2sVpnGateway': Menambahkan parameter switch opsional 'EnableInternetSecurityFlag' bagi pelanggan untuk mengatur true untuk mengaktifkan keamanan internet di P2SVpnGateway, yang akan diterapkan untuk klien Titik ke situs.
- Memperbarui 'Update-AzP2sVpnGateway': Menambahkan parameter switch opsional 'EnableInternetSecurityFlag' atau 'DisableInternetSecurityFlag' bagi pelanggan untuk mengatur true/false untuk mengaktifkan/menonaktifkan keamanan internet di P2SVpnGateway, yang akan diterapkan untuk klien Titik ke situs.
* Menambahkan cmdlet baru 'Reset-AzP2sVpnGateway' bagi pelanggan untuk mengatur ulang/me-reboot VirtualWan P2SVpnGateway mereka untuk pemecahan masalah.
* Menambahkan cmdlet baru 'Reset-AzVpnGateway' bagi pelanggan untuk mengatur ulang/me-reboot VirtualWan VpnGateway mereka untuk pemecahan masalah.
* Memperbarui 'Set-azVirtualNetworkSubnetConfig'
    - Mengatur properti NSG dan Tabel Rute subnet ke null jika secara eksplisit diatur dalam parameter [#1548][#9718]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Status Hapus untuk Item Cadangan beban kerja.

#### <a name="azresources"></a>Az.Resources
* Menambahkan pemeriksaan yang hilang untuk Set-AzRoleAssignment
* Menambahkan atribut perubahan mencolok ke parameter 'SubscriptionId' dari 'Get-AzResourceGroupDeploymentOperation'
* Memperbarui cmdlet What-If templat ARM untuk menampilkan perubahan sumber daya 'Ignore' terakhir
* Memperbaiki masalah serialisasi parameter aman dan array untuk cmdlet penyebaran [#12773]

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan cmdlet baru untuk kluster terkelola dan jenis node:
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
* Meningkatkan SDK Service Fabric ke versi 1.2.0 yang menggunakan penyedia sumber daya fabric layanan api-version 2020-03-01 untuk model saat ini dan 2020-01-01-pratinjau untuk kluster terkelola.

#### <a name="azsql"></a>Az.Sql
* Menambahkan BackupStorageRedundancy ke 'New-AzSqlInstance' dan 'Get-AzSqlInstance'
* Menambahkan cmdlet 'Get-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menambahkan cmdlet 'Enable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menambahkan parameter Force ke 'New-AzSqlInstance'
* Menambahkan cmdlet untuk layanan Pemutaran Ulang Log Database Terkelola
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
* Memperbarui cmdlet ActiveDirectoryOnlyAuthentication untuk server dan instans guna menyertakan ResourceId dan InputObject

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki pengunggahan blob gagal dengan meningkatkan ke Microsoft.Azure.Storage.DataMovement 2.0.0 [#12220]
* Mendukung Pemulihan Titik Waktu Tertentu
    - 'Enable-AzStorageBlobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'New-AzStorageBlobRangeToRestore'
    - 'Restore-AzStorageBlobRange'
* Mendukung didapatkannya status pemulihan blob akun Penyimpanan dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeBlobRestoreStatus
    - 'Get-AzureRMStorageAccount'
* Menambahkan pesan peringatan perubahan mencolok untuk perubahan output cmdlet mendatang
    - 'Get-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyAction'
    - 'New-AzStorageAccountManagementPolicyRule'
* Meningkatkan Microsoft.Azure.Cosmos.Table SDK yang ditingkatkan ke 1.0.8

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
* @rossifumax, Memperbaiki kesalahan pengetikan di New-AzConfigurationAssignment.md (#12701)

## <a name="461---august-2020"></a>4.6.1 - Agustus 2020
#### <a name="azcompute"></a>Az.Compute
* Melakukan patch parameter '-EncryptionAtHost' di 'New-AzVm' untuk menghapus nilai default false [#12776]

## <a name="460---august-2020"></a>4.6.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memuat semua lingkungan cloud publik saat titik akhir penemuan tidak mengembalikan AzureCloud default atau lingkungan publik lainnya [#12633]
* Mengekspos SubscriptionPolicies di 'Get-AzSubscription' [#12551]

#### <a name="azautomation"></a>Az.Automation
* Menambahkan parameter '-RunOn' ke 'Set-AzAutomationWebhook' untuk menentukan Grup Pekerja Hibrida

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EncryptionAtHost' ke 'New-AzVm', 'New-AzVmss', 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVM', dan 'Update-AzVmss'
* Menambahkan 'SecurityProfile' ke objek kembali 'Get-AzVM' dan 'Get-AzVmss'
* Menambahkan switch '-InstanceView' sebagai parameter opsional untuk 'Get-AzHostGroup'
* Menambahkan cmdlet baru 'Invoke-AzVmPatchAssessment'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan properti yang hilang ke kelas PSPipelineRun.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan enkripsi di fitur host

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan pesan peringatan untuk berencana menonaktifkan penghapusan sementara
* Menambahkan pesan peringatan untuk berencana menghapus atribut SecretValueText

#### <a name="azmaintenance"></a>Az.Maintenance
* Menambahkan bidang terkait jadwal opsional ke 'New-AzMaintenanceConfiguration'
* Menambahkan cmdlet baru untuk 'Get-AzMaintenancePublicConfiguration'

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan peringatan perubahan mencolok pada cmdlet penetapan dan definisi layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperluas parameter yang diatur dalam 'Set-AzDiagnosticSetting' untuk pemisahan pengaktifan Log dan Metrik [#12482]
* Memperbaiki bug untuk 'Add-AzMetricAlertRuleV2' saat mendapatkan peringatan metrik dari alur

#### <a name="azresources"></a>Az.Resources
* Memperbarui respons 'Get-AzPolicyAlias' untuk menyertakan informasi yang menunjukkan apakah alias tersebut dapat dimodifikasi oleh Azure Policy.
* Membuat cmdlet baru 'Set-AzRoleAssignment'
* Menambahkan 'Get-AzDeploymentManagementGroupWhatIfResult' untuk mendapatkan hasil What-If templat ARM di cakupan Grup manajemen
* Menambahkan cmdlet baru 'Get-AzTenantWhatIfResult' untuk mendapatkan hasil What-If templat ARM di cakupan penyewa
* Mengambil alih '-WhatIf' dan '-Confirm' untuk 'New-AzManagementGroupDeployment' dan 'New-AzTenantDeployment' untuk menggunakan hasil What-If templat ARM
* Memperbaiki perilaku '-WhatIf' dan '-Confirm' untuk cmdlet penyebaran baru sehingga mereka mematuhi False dan
* Memperbaiki kesalahan serialisasi untuk '-TemplateObject' dan 'TemplateParameterObject' [#1528] [#6292]
* Menambahkan atribut perubahan mencolok ke 'Get-AzResourceGroupDeploymentOperation' untuk perubahan jenis output mendatang

#### <a name="azsignalr"></a>Az.SignalR
* Memperbaiki kesalahan file bantuan 'Restart-AzSignalR' dan 'Update-AzSignalR'
* Menambahkan cmdlet 'Update-AzSignalRNetworkAcl', 'Set-AzSignalRUpstream'

#### <a name="azstorage"></a>Az.Storage
* Mendukung akselerasi kueri blob
    -  'Get-AzStorageBlobQueryResult'
    -  'New-AzStorageBlobQueryConfig'
* Memperbarui file bantuan, menambahkan lebih banyak deskripsi, dan memperbaiki kesalahan pengetikan
    -  'Start-AzStorageBlobCopy'
    -  'Get-AzDataLakeGen2Item'
* Memperbaiki blob unduhan gagal saat sub direktori terkait tidak ada [#12592]
    -  'Get-AzStorageBlobContent'
* Mendukung Kebijakan Replikasi Objek Atur/Dapatkan/Hapus di akun Storage
    - 'New-AzStorageObjectReplicationPolicyRule'
    - 'Set-AzStorageObjectReplicationPolicy'
    - 'Get-AzStorageObjectReplicationPolicy'
    - 'Remove-AzStorageObjectReplicationPolicy'
* Mendukung mengaktifkan/menonaktifkan ChangeFeed di Layanan Blob akun Penyimpanan
    - 'Update-AzStorageBlobServiceProperty'

## <a name="450---august-2020"></a>4.5.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui 'Connect-AzAccount' untuk menerima parameter 'MaxContextPopulation' [#9865]
* Memperbarui versi SubscriptionClient ke 2019-06-01 dan menampilkan domain penyewa [#9838]
* Mendukung penyewa rumah dan dikelola Oleh informasi langganan penyewa
* Mengoreksi nama modul yang dikoreksi, info versi dalam data telemetri
* Menyesuaikan SqlDatabaseDnsSuffix dan ServiceManagementUrl jika titik akhir metadata lingkungan mengembalikan nilai yang tidak kompatibel

#### <a name="azaks"></a>Az.Aks
* Menghapus 'ClientIdAndSecret' ke 'ServicePrincipalIdAndSecret' dan mengatur 'ClientIdAndSecret' sebagai alias [#12381].
* Menghapus 'Get-AzAks'/'New-AzAks'/'Remove-AzAks'/'Set-AzAks' ke 'Get-AzAksCluster'/'New-AzAksCluster'/'Remove-AzAksCluster'/'Set-AzAksCluster' dan tetapkan yang asli sebagai alias [#12373].

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
* Memperbaiki masalah di mana pengecualian sedang dilemparkan ketika Enum.Parse mencoba memaksa nilai null ke nilai enumerasi Yang Diaktifkan atau Dinonaktifkan [#12344]

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan enkripsi dalam fitur transit.
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightCluster'
    - Menambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightClusterConfig'
* Mendukung pembuatan kluster dengan fitur tautan privat:
    - Menambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightCluster'
    - Menambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightClusterConfig'
* Mengembalikan informasi jaringan virtual saat menelepon 'New-AzHDInsightCluster' atau 'Get-AzHDInsightCluster'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Menambahkan perubahan yang tidak mencolok: Fungsi PeerAddressType untuk Peering Privat di 'Remove-AzExpressRouteCircutPeeringConfig'.
* Kode berubah untuk mengabaikan kapitalisasi untuk parameter AddressPrefixType dan PeerAddressType.
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Menambahkan opsi '-ForceDelete' untuk 'Remove-AzOperationalInsightsworkspace'
* Menambahkan cmdlet baru 'Get-AzOperationalInsightsDeletedWorkspace'
* Menambahkan cmdlet baru 'Restore-AzOperationalInsightsWorkspace'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Meningkatkan pengalaman penemuan kontainer/item Azure Backup.

#### <a name="azresources"></a>Az.Resources
* Menambahkan properti 'Condition', 'ConditionVersion' dan 'Description' ke 'New-AzRoleAssignment'
    - Ini termasuk semua perubahan yang relevan pada model data

#### <a name="azsql"></a>Az.Sql
* Memperbaiki potensi kesalahan tidak sensitif huruf besar atau kecil nama server di 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Memperbaiki nama database yang salah dikembalikan pada kesalahan database yang ada di 'New-AzSqlDatabaseSecondary'

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan token Sas kontainer/blob dengan izin baru x,t
    -  'New-AzStorageBlobSASToken'
    -  'New-AzStorageContainerSASToken'
* Mendukung pembuatan token Sas akun dengan izin baru x,t,f
    -  'New-AzStorageAccountSASToken'
* Mendukung mendapatkan penggunaan berbagi file tunggal
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
* Memperbaiki masalah di mana string dengan karakter escape tidak dapat diubah menjadi objek json.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan peringatan saat menggunakan 'New-AzVmss' tanpa versi citra 'terbaru'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan parameter global ke Data Factory.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui untuk menggunakan versi API 2020-06-01.
* Menambahkan fitur baru:
    - Pemetaan input
    - Skema Pengiriman Peristiwa
    - Private Link
    - Skema V10 Peristiwa Cloud
    - Topik Sebagai Tujuan Bus Layanan
    - Azure Function Sebagai Tujuan
    - Pembuatan Batch WebHook
    - Webhook aman (dukungan AAD)
    - IpFiltering
* Memperbarui cmdlet:
    - 'New-AzEventGridSubscription'/'Update-AzEventGridSubscription':
        - Menambahkan parameter opsional baru untuk mendukung pembuatan batch webhook.
        - Menambahkan parameter opsional baru untuk mendukung webhook aman menggunakan AAD.
        - Menambahkan enumerasi baru untuk parameter EndpointType untuk mendukung fungsi azure dan topik bus layanan sebagai tujuan baru.
        - Menambahkan parameter opsional baru untuk skema pengiriman.
    - 'New-AzEventGridTopic'/'Update-AzEventGridTopic' dan 'New-AzEventGridDomain'/'Update-AzEventGridDomain':
        - Menambahkan parameter opsional baru untuk mendukung IpFiltering.
    - 'New-AzEventGridTopic'/'New-AzEventGridDomain':
        - Menambahkan parameter opsional baru untuk mendukung pemetaan input.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbarui modul untuk menggunakan API 2020-05-01
* Menambahkan dukungan tautan Privat untuk sumber daya Penyimpanan, Brankas Kunci, dan Layanan Aplikasi Web

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan kluster dengan penyimpanan ADLSGen1/2 di cloud nasional.

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug untuk 'Get-AzDiagnosticSetting' saat metrik atau log null [#12272]

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki penukaran parameter dalam koneksi VWan HubVnet
* Menambahkan cmdlet baru untuk Situs Alat Virtual Azure Network
    - 'Get-AzVirtualApplianceSite'
    - 'New-AzVirtualApplianceSite'
    - 'Remove-AzVirtualApplianceSite'
    - 'Update-AzVirtualApplianceSite'
    - 'New-AzOffice365PolicyProperty'
* Menambahkan cmdlet baru untuk Azure Network Virtual Appliance
    - 'Get-AzNetworkVirtualAppliance'
    - 'New-AzNetworkVirtualAppliance'
    - 'Remove-AzNetworkVirtualAppliance'
    - 'Update-AzNetworkVirtualAppliance'
    - 'Get-AzNetworkVirtualApplianceSku'
    - 'New-AzVirtualApplianceSkuProperty'
* Melakukan onboard Application Gateway ke Cmdlet Umum Private Link
* Melakukan onboard StorageSync ke Cmdlet Umum Private Link
* Melakukan onboard SignalR ke Cmdlet Umum Private Link

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menghapus referensi proyek ke Autentikasi
* Azure Backup menyetel teks bantuan cmdlet agar lebih akurat.
* Azure Backup menambahkan dukungan untuk mengambil pekerjaan agen MAB menggunakan cmdlet 'Get-AzRecoveryServicesBackupJob'.

#### <a name="azresources"></a>Az.Resources
* Memperbarui 'Save-AzResourceGroupDeploymentTemplate' untuk menggunakan SDK.
* Menambahkan cmdlet 'Unregister-AzResourceProvider'.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk Perwakilan layanan dan pengguna tamu di cmdlet Set-AzSqlInstanceActiveDirectoryAdministrator'
* Memperbaiki bug di cmdlet Klasifikasi Data.'
* Menambahkan dukungan untuk failover Azure SQL Managed Instance: 'Invoke-AzSqlInstanceFailover'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah di mana UserAgent tidak ditambahkan untuk beberapa cmdlet data plane.
* Mendukung pembuatan/pembaruan akun Penyimpanan dengan MinimumTlsVersion dan AllowBlobPublicAccess
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung pengaktifan/penonaktifan penerapan versi di Layanan Blob akun Penyimpanan
    - 'Update-AzStorageBlobServiceProperty'
* Mendukung daftar blob dengan versi blob
    - 'Get-AzStorageBlob'
* Mendukung perolehan/penghapusan snapshot blob tunggal atau versi blob
    - 'Get-AzStorageBlob'
    - 'Remove-AzStorageBlob'
* Mendukung alur dari objek blob yang dihasilkan dari Azure.Storage.Blobs V12
    - 'Get-AzStorageBlobContent'
    - 'New-AzStorageBlobSASToken'
    - 'Remove-AzStorageBlob'
    - 'Set-AzStorageBlobContent'
    - 'Start-AzStorageBlobCopy'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan versi baru StorageSync SDK yang menargetkan ApiVersion 2020-03-01
* Menambahkan cmdlet Perbarui Layanan Sinkronisasi Penyimpanan
    - 'Set-AzStorageSyncService'
* Menambahkan cmdlet IncomingTrafficPolicy dan PrivateEndpointConnections ke StorageSyncService.

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk melakukan operasi untuk Slot yang tidak berada dalam grup sumber daya yang sama dengan Paket Layanan Aplikasi

## <a name="430---june-2020"></a>4.3.0 - Juni 2020
#### <a name="azaccounts"></a>Az.Accounts
* Mendukung penemuan pengaturan lingkungan secara default dan menambahkan lingkungan melalui 'Add-AzEnvironment'
* Memperbarui assembly yang dimuat sebelumnya [#12024], [#11976]
* Memperbarui assembly Azure.Core
* Memperbaiki masalah yang dapat menyebabkan 'Connect-AzAccount' gagal dalam eksekusi multi-threaded [#11201]

#### <a name="azaks"></a>Az.Aks
* Mengganti penggunaan [AccessProfile API](/rest/api/aks/managedclusters/getaccessprofile) lama dengan panggilan ke [ListClusterAdmin](/rest/api/aks/managedclusters/listclusteradmincredentials) dan [ListClusterUser](/rest/api/aks/managedclusters/listclusterusercredentials) API

#### <a name="azbatch"></a>Az.Batch
* Memperbarui Az.Batch untuk menggunakan versi SDK 'Microsoft.Azure.Management.Batch' ke 11.0.0
* Menambahkan kemampuan untuk mengatur Identitas BatchAccount di cmdlet 'New-AzBatchAccount'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung menampilkan kemampuan akun.
* Mendukung modifikasi PublicNetworkAccess.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter SimulateEviction ke cmdlet Set-AzVM dan Set-AzVmssVM.
* Menambahkan 'Premium_LRS' ke pelengkap argumen parameter StorageAccountType untuk cmdlet New-AzGalleryImageVersion.
* Menambahkan Substatus ke VMCustomScriptExtension [#11297]
* Menambahkan 'Delete' ke pelengkap argumen parameter EvictionPolicy untuk cmdlet New-AzVM dan New-AzVMConfig.
* Memperbaiki nama Ekstensi VM baru untuk SAP

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.9.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter Identitas Terkelola ke cmdlet 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dukungan untuk membuat aplikasi fungsi PowerShell 7.0 dan Java 11

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung host daftar dan memulai ulang host tertentu dari kluster HDInsight.

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
* Memperbarui perintah di bawah ini untuk fitur: Server dns kustom diatur/dihapus di VirtualWan P2SVpnGateway.
    - Memperbarui New-AzP2sVpnGateway: Menambahkan parameter opsional '-CustomDnsServer' bagi pelanggan untuk menentukan server dns mereka untuk diatur di P2SVpnGateway, yang dapat digunakan oleh klien Titik ke situs.
    - Memperbarui Update-AzP2sVpnGateway: Menambahkan parameter opsional '-CustomDnsServer' bagi pelanggan untuk menentukan server dns mereka untuk diatur di P2SVpnGateway, yang dapat digunakan oleh klien Titik ke situs.
* Memperbarui 'Update-AzVpnGateway'
    - Menambahkan parameter opsional '-BgpPeeringAddress' bagi pelanggan untuk menentukan bgps kustom mereka untuk diatur di VpnGateway.
* Menambahkan cmdlet baru untuk mendukung pengaturan ulang kondisi perutean sumber daya VirtualHub:
    - 'Reset-AzHubRouter'
* Memperbarui hal-hal di bawah berdasarkan perubahan swagger baru-baru ini untuk Kebijakan Firewall
    - Mengubah nama untuk RuleGroup, RuleCollectionGroup, dan RuleType
    - Menambahkan dukungan untuk Koleksi Aturan NAT Kebijakan Firewall untuk mendukung beberapa Kumpulan Aturan NAT
* [Perubahan Mencolok] Menambahkan parameter wajib 'SourceIpGroup' untuk 'New-AzFirewallPolicyApplicationRule' dan 'New-AzFirewallPolicyNetworkRule'.
* [Perubahan Mencolok] Memperbaiki 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' menjadi wajib.
* [Perubahan Mencolok] Memperbaiki 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' menjadi wajib.
* [Perubahan Mencolok] Menghapus parameter wajib: 'TranslatedAddress', 'TranslatedPort' untuk 'New-AzFirewallPolicyNatRuleCollection'.
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
* Menambahkan 'pergb2018' ke set nilai yang valid parameter 'Sku' di 'Set-AzOperationalInsightsWorkspace'
* Menambahkan alias 'FunctionParameters' untuk parameter 'FunctionParameter' ke
    - 'New-AzOperationalInsightsSavedSearch'
    - 'Set-AzOperationalInsightsSavedSearch'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup menambahkan dukungan untuk mengambil item MAB.
* Azure Site Recovery mendukung jenis disk 'StandardSSD_LRS'

#### <a name="azresources"></a>Az.Resources
* Menambahkan 'UsageLocation', 'GivenName', 'Surname', 'AccountEnabled', 'MailNickname', 'Mail' di 'PSADUser' [#10526] [#10497]
* Memperbaiki masalah di mana '-Mail' tidak berfungsi di 'Get-AzADUser' [#11981]
* Menambahkan parameter '-ExcludeChangeType' ke 'Get-AzDeploymentWhatIfResult' dan 'Get-AzResourceGroupDeploymentWhatIfResult'
* Menambahkan parameter '-WhatIfExcludeChangeType' ke 'New-AzDeployment' dan 'New-AzResourceGroupDeployment'
* Memperbarui cmdlet 'Test-Az*Deployment' untuk menampilkan pesan kesalahan yang lebih baik
* Memperbaiki pesan bantuan untuk parameter '-Name' dari pembuatan penyebaran dan cmdlet What-If

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk perwakilan layanan untuk cmdlet Set SQL Server Azure Active Directory Admin
* Memperbaiki masalah sinkronisasi dalam cmdlet Klasifikasi Data.
* Mendukung pencarian pengguna melalui email di 'Set-AzSqlServerActiveDirectoryAdministrator' [#12192]

#### <a name="azstorage"></a>Az.Storage
* Mendukung pembuatan akun Penyimpanan dengan RequireInfrastructureEncryption
    -  'New-AzStorageAccount'
* Memindahkan logika pemuatan Azure.Core ke Az.Accounts

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan perlindungan tambahan untuk menghapus aplikasi web yang dibuat jika pemulihan gagal di 'Restore-AzDeletedWebApp'
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
* Memperbarui versi assembly cmdlet manajemen layanan

#### <a name="azbilling"></a>Az.Billing
* Memperbarui versi assembly cmdlet konsumsi

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung kontrol PrivateEndpoint dan PublicNetworkAccess.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi assembly cmdlet V2 pabrik data

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
* Memperbarui versi assembly cmdlet PowerBI

#### <a name="azprivatedns"></a>Az.PrivateDns
* Mengoreksi pemformatan string output verbose untuk Remove-AzPrivateDnsRecordSet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk membuat rencana pemulihan untuk replikasi zona ke zona dari input xml.
* Memperbarui versi assembly cmdlet SiteRecovery dan Backup

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter Tail ke cmdlet Get-AzDeploymentScriptLog dan Save-AzDeploymentScriptLog
* Memformat properti Output dan menampilkannya pada output cmdlet Get-AzDeploymentScript
* Mengganti nama parameter -DeploymentScriptInputObject menjadi -DeploymentScriptObject
* Memperbaiki nama file/target yang hilang di pesan cmdlet.
* Memperbarui versi assembly cmdlet manajer sumber daya dan tag

#### <a name="azsql"></a>Az.Sql
* Menambahkan UsePrivateLinkConnection ke 'New-AzSqlSyncGroup', 'Update-AzSqlSyncGroup', 'New-AzSqlSyncMember' dan 'Update-AzSqlSyncMember'
* Menambahkan SyncMemberAzureDatabaseResourceId ke 'New-AzSqlSyncMember' dan 'Update-AzSqlSyncMember'
* Menambahkan dukungan pencarian pengguna Tamu ke cmdlet Set SQL Server Azure Active Directory Admin

#### <a name="azstorage"></a>Az.Storage
* Memperbarui versi assembly cmdlet data plane

## <a name="410---may-2020"></a>4.1.0 - Mei 2020
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Versi PowerShell yang didukung: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7
* Ketersediaan umum Az.Functions
* Az.ApiManagement, Az.Batch, Az.Compute, Az.KeyVault, Az.Monitor, Az.Network, Az.OperationalInsights, Az.Resources, dan Az.Storage memiliki rilisan besar

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui 'Add-AzEnvironment' dan 'Set-AzEnvironment' untuk menerima parameter 'AzureSynapseAnalyticsEndpointResourceId' dan 'AzureSynapseAnalyticsEndpointSuffix'
* Menambahkan assembly terkait Azure.Core ke Az.Accounts, mendukung platform PowerShell meliputi Windows PowerShell 5.1, PowerShell Core 6.2.4, PowerShell 7+

#### <a name="azaks"></a>Az.Aks
* Meningkatkan Versi API ke 2019-10-01
* Mendukung untuk membuat AKS menggunakan kontainer Windows
* Menyediakan cmdlet baru: 'New-AzAksNodePool', 'Update-AzAksNodePool', 'Remove-AzAksNodePool', 'Get-AzAksNodePool', 'Install-AzAksKubectl', 'Get-AzAksVersion'

#### <a name="azapimanagement"></a>Az.ApiManagement
* Parameter 'New-AzApiManagement' dan 'Set-AzApiManagement': [-AssignIdentity] berganti nama menjadi [-SystemAssignedIdentity]
* 'New-AzApiManagement' dan 'Set-AzApiManagement': Parameter baru ditambahkan: [-UserAssignedIdentity <String[]>]
* 'Get-AzApiManagementProperty': berganti nama menjadi 'Get-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'New-AzApiManagementProperty': berganti nama menjadi 'New-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'Set-AzApiManagementProperty': berganti nama menjadi 'Set-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'Remove-AzApiManagementProperty': berganti nama menjadi 'Remove-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* Menambahkan cmdlet 'Get-AzApiManagementAuthorizationServerClientSecret' baru dan 'Get-AzApiManagementAuthorizationServer' tidak akan mengembalikan rahasia klien lagi.
* Menambahkan cmdlet 'Get-AzApiManagementNamedValueSecretValue' baru dan 'Get-AzApiManagementNamedValue' tidak akan mengembalikan nilai rahasia.
* Menambahkan cmdlet 'Get-AzApiManagementOpenIdConnectProviderClientSecret' baru dan cmdlet 'Get-AzApiManagementOpenIdConnectProvider' tidak akan mengembalikan rahasia klien lagi.
* Menambahkan cmdlet 'Get-AzApiManagementSubscriptionKey' baru dan 'Get-AzApiManagementSubscription' tidak akan mengembalikan kunci berlangganan lagi.
* Menambahkan cmdlet 'Get-AzApiManagementTenantAccessSecret' baru dan 'Get-AzApiManagementTenantAccess' tidak akan mengembalikan kunci lagi.
* Menambahkan cmdlet 'Get-AzApiManagementTenantGitAccessSecret' baru dan 'Get-AzApiManagementTenantGitAccess' tidak akan mengembalikan kunci lagi.

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan Parameter: 'RetentionInDays' 'PublicNetworkAccessForIngestion' 'PublicNetworkAccessForQuery' untuk 'New-AzApplicationInsights'
* Membuat cmdlet 'Update-AzApplicationInsights'
* Membuat cmdlet untuk Akun Penyimpanan Tertaut

#### <a name="azbatch"></a>Az.Batch
* Memperbarui Az.Batch untuk menggunakan SDK 'Microsoft.Azure.Batch' versi 13.0.0 dan SDK 'Microsoft.Azure.Management.Batch' versi 9.0.0.
* Menambahkan kemampuan untuk memilih jenis sertifikat yang ditambahkan menggunakan parameter '-CertificateKind' baru ke 'New-AzBatchCertificate'.
* Menghapus properti 'ApplicationPackages' dari 'PSApplication' yang sebelumnya selalu ''.
  - Paket spesifik di dalam aplikasi sekarang dapat diambil menggunakan 'Get-AzBatchApplicationPackage'. Misalnya: 'Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication'.
* Saat membuat kumpulan menggunakan 'New-AzBatchPool', properti 'VirtualMachineImageId’ dari 'PSImageReference' sekarang hanya dapat merujuk ke citra Shared Image Gallery.
* Saat membuat kumpulan menggunakan 'New-AzBatchPool', kumpulan dapat disediakan tanpa IP publik menggunakan properti 'PublicIPAddressConfiguration' baru dari 'PSNetworkConfiguration'.
  - Properti 'PublicIPs' dari 'PSNetworkConfiguration' juga telah berpindah ke 'PSPublicIPAddressConfiguration'. Properti ini hanya dapat ditentukan jika 'IPAddressProvisioningType' adalah 'UserManaged'.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HostId ke cmdlet 'Update-AzVM'
* Memperbarui dokumen Bantuan untuk cmdlet 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVmss', 'Set-AzVMOperatingSystem' dan 'Set-AzVmssOsProfile'.
* Perubahan mencolok
    - Parameter FilterExpression dihapus dari cmdlet 'Get-AzVMImage'.
    - Parameter AssignIdentity dihapus dari cmdlet 'New-AzVmssConfig', 'New-AzVMConfig' dan 'Update-AzVM'.
    - AutomaticRepairMaxInstanceRepairsPercent dihapus dari cmdlet 'New-AzVmssConfig' dan 'Update-AzVmss'.
    - Properti AvailabilitySetsColocationStatus, VirtualMachinesColocationStatus dan VirtualMachineScaleSetsColocationStatus dihapus dari ProximityPlacementGroup.
    - Properti MaxInstanceRepairsPercent dihapus dari AutomaticRepairsPolicy.
    - Jenis AvailabilitySets, VirtualMachines dan VirtualMachineScaleSets diubah dari `IList<SubResource>` menjadi `IList<SubResourceWithColocationStatus>`.
* Deskripsi untuk cmdlet 'Get-AzVM' telah diperbarui untuk menggambarkannya dengan lebih baik.

#### <a name="azdatafactory"></a>Az.DataFactory
* Mendukung CRUD properti runtime aliran data di IR Terkelola.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan cmdlet baru untuk pembuatan, pembaruan, pengambilan, dan penghapusan objek Front Door Rules Engine
* Menambahkan cmdlet pembantu untuk konstruksi objek Front Door Rules Engine
* Menambahkan referensi Rules Engine ke objek Aturan Perutean Front Door.
* Menambahkan parameter Private Link ke objek Backend Front Door

#### <a name="azfunctions"></a>Az.Functions
* Ketersediaan umum modul ''Az.Functions''

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung enkripsi kunci yang dikelola pelanggan

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Kebijakan akses tidak lagi default ke prinsipal saat ini

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan cmdlet untuk memanggil kueri di hub IoT untuk mengambil informasi menggunakan bahasa seperti SQL.
* Memperbaiki masalah di mana 'Add-AzIotHubDevice' gagal membuat Perangkat Berkemampuan Edge tanpa perangkat turunan [#11597]
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
* Menghapus properti redundan yang ditentukan di PSEventData [#11353]
* Mengganti nama 'Get-AzLog' menjadi 'Get-AzActivityLog'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan atribut perubahan mencolok untuk memberi tahu bahwa perilaku default Zona akan diubah
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
* Memperbarui kode warisan untuk menerapkan SDK baru yang dihasilkan
* Menghapus cmdlet akibat API yang tidak digunakan lagi
    - 'Get-AzOperationalInsightsSavedSearchResult' (alias 'Get-AzOperationalInsightsSavedSearchResults')
    - 'Get-AzOperationalInsightsSearchResult' (alias 'Get-AzOperationalInsightsSearchResults')
    - 'Get-AzOperationalInsightsLinkTarget' (alias 'Get-AzOperationalInsightsLinkTargets')
* Menambahkan parameter untuk 'Set-AzOperationalInsightsWorkspace' dan 'New-AzOperationalInsightsWorkspace'
* Membuat cmdlet untuk Akun Penyimpanan Tertaut
* Membuat cmdlet untuk Kluster dan Layanan Tertaut

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery menambahkan dukungan untuk melindungi mesin virtual grup penempatan kedekatan untuk Azure ke penyedia Azure.
* Azure Site Recovery menambahkan dukungan untuk replikasi zona ke zona.
* Azure Backup Menambahkan Dukungan retensi jangka panjang untuk Titik Pemulihan Azure FileShare.
* Azure Backup Menambahkan properti pengecualian disk ke output cmdlet 'Get-AzRecoveryServicesBackupItem'.
* Menambahkan titik akhir privat untuk file info masuk Vault untuk layanan pemulihan situs.

#### <a name="azresources"></a>Az.Resources
* Menambahkan peringatan pesan tentang penundaan tampilan saat membuat Definisi Peran baru
* Mengubah cmdlet kebijakan untuk menghasilkan objek yang ditetapkan dengan kuat
* Menghapus parameter '-TenantLevel' yang digunakan untuk pada cmdlet 'Get-AzResourceLock' [#11335]
* Memperbaiki 'Remove-AzResourceGroup -Id ResourceId'[#9882]
* Menambahkan cmdlet baru untuk mendapatkan hasil What-If templat ARM di cakupan grup sumber daya: 'Get-AzDeploymentResourceGroupWhatIfResult'
* Menambahkan cmdlet baru untuk mendapatkan hasil What-If templat ARM pada cakupan langganan: 'Get-AzDeploymentWhatIfResult'
   - Alias: 'Get-AzSubscriptionDeploymentWhatIf'
* Mengambil alih parameter '-WhatIf' dan '-Confirm' untuk 'New-AzDeployment' dan 'New-AzResourceGroupDeployment' untuk menggunakan hasil What-If templat ARM
* Menambahkan pesan penghentian untuk parameter 'ApiVersion' di cmdlet penyebaran
* Menambahkan kemampuan untuk menampilkan pesan kesalahan yang ditingkatkan untuk kegagalan penyebaran
* Menambahkan pengelogan correlationId untuk kegagalan penyebaran
* Menambahkan properti 'error' untuk output skrip penyebaran
* Memperbarui nuget Microsoft.Azure.Management.ResourceManager untuk '3.7.1-pratinjau'
* Menghapus kasus pengujian tertentu sebagai properti Kesalahan di DeploymentValidateResult telah berubah menjadi baca saja dari nuget 3.7.1-pratinjau
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
* Mengaudit ke akun penyimpanan di Vnet, memperbaiki bug saat membuat peran Kontributor Data Blob Penyimpanan.

#### <a name="azstorage"></a>Az.Storage
* Menambahkan '-AsJob' untuk mendapatkan/mencantumkan akun cmdlet 'Get-AzStorageAccount'
* Menjadikan KeyVersion opsional saat memperbarui akun Penyimpanan dengan KeyvaultEncryption, untuk mendukung rotasi otomatis kunci
    - 'Set-AzStorageAccount'
* Memperbaiki penghapusan Azure File Directory gagal dengan alur
    - 'Remove-AzStorageDirectory'
* Memperbaiki [#9880]: Mengubah definisi nilai NetWorkRule DefaultAction agar selaras dengan swagger.
    - 'Update-AzStorageAccountNetworkRuleSet'
    - 'Get-AzStorageAccountNetworkRuleSet'
* Memperbaiki [#11624]: Melewati aturan duplikat saat menambahkan NetworkRules, untuk menghindari kegagalan server
    - 'Add-AzStorageAccountNetworkRule'
* Meningkatkan Microsoft.Azure.Cosmos.Table SDK ke 1.0.7
* Menambahkan pesan peringatan untuk mengingatkan pengguna untuk mencantumkan kembali dengan ContinuationToken ketika hanya sebagian item yang dikembalikan dalam daftar Item DataLake Gen2,
    - 'Get-AzDataLakeGen2ChildItem'
* Mendukung pembuatan atau pembaruan akun Penyimpanan dengan Autentikasi Azure Files Active Directory Domain Service
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung untuk daftar kunci Kerberos atau kunci baru akun Penyimpanan
    -  'New-AzStorageAccountKey'
    -  'Get-AzStorageAccountKey'
* Mendukung failover akun Penyimpanan
    - 'Invoke-AzStorageAccountFailover'
* Memperbarui bantuan 'Get-AzStorageBlobCopyState'
* Memperbarui bantuan 'Get-AzStorageFileCopyState' dan 'Start-AzStorageBlobCopy'
* Mengintegrasikan pustaka klien Penyimpanan v12 ke cmdlet Antrean dan File
* Mengubah jenis output dari CloudFile ke AzureStorageFile, output asli akan menjadi properti turunan dari output baru
    - 'Get-AzStorageFile'
    - 'Remove-AzStorageFile'
    - 'Get-AzStorageFileContent'
    - 'Set-AzStorageFileContent'
    - 'Start-AzStorageFileCopy'
* Mengubah jenis output dari CloudFileDirectory menjadi AzureStorageFileDirectory, output asli akan menjadi properti turunan dari output baru
    - 'New-AzStorageDirectory'
    - 'Remove-AzStorageDirectory'
* Mengubah jenis output dari CloudFileShare menjadi AzureStorageFileShare, output asli akan menjadi properti turunan dari output baru
    - 'Get-AzStorageShare'
    - 'New-AzStorageShare'
    - 'Remove-AzStorageShare'
* Mengubah jenis output dari FileShareProperties menjadi AzureStorageFileShare, output asli akan menjadi properti sub turunan dari output baru
    - 'Set-AzStorageShareQuota'

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Memperbaiki nama profil yang salah di output verbose 'DisableAzureTrafficManagerEndpoint'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki kesalahan pengetikan pada bantuan 'Update-AzWebAppAccessRestrictionConfig'.

## <a name="380---april-2020"></a>3.8.0 - April 2020
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Versi PowerShell yang didukung Az.Storage: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui URL survei Azure PowerShell di 'Resolve-AzError' [#11507]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan pemberitahuan perubahan mencolok untuk perubahan output cmdlet Azure File dalam rilis mendatang
* 'Set-AzApiManagementGroup' Memperbarui dokumentasi untuk menentukan parameter GroupId

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki tampilan SKU harga terkait ChinaCDN

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung Identity, Encryption, UserOwnedStorage

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet 'Set-AzVmssOrchestrationServiceState'.
* 'Get-AzVmss' dengan -InstanceView menampilkan status OrchestrationService.

#### <a name="aziothub"></a>Az.IotHub
* Mengelola konfigurasi kembar perangkat IoT, Cmdlet baru yaitu:
    - 'Get-AzIotHubDeviceTwin'
    - 'Update-AzIotHubDeviceTwin'
* Menambahkan cmdlet untuk memanggil metode langsung pada perangkat di Iot Hub.
* Mengelola konfigurasi kembar modul perangkat IoT, Cmdlet baru yaitu:
    - 'Get-AzIotHubModuleTwin'
    - 'Update-AzIotHubModuleTwin'
* Mengelola konfigurasi manajemen perangkat otomatis IoT dalam skala besar. Cmdlet baru adalah:
    - 'Add-AzIotHubConfiguration'
    - 'Get-AzIotHubConfiguration'
    - 'Remove-AzIotHubConfiguration'
    - 'Set-AzIotHubConfiguration'
* Menambahkan cmdlet untuk memanggil metode modul tepi dalam Iot Hub.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan cmdlet baru 'Update-AzKeyVault' yang dapat mengaktifkan perlindungan penghapusan sementara dan penghapusan menyeluruh pada brankas
* Menambahkan dukungan ke Microsoft.PowerShell.SecretManagement [#11178]
* Memperbaiki kesalahan dalam contoh 'Remove-AzKeyVaultManagedStorageSasDefinition' [#11479]
* Menambahkan dukungan ke titik akhir privat

#### <a name="azmaintenance"></a>Az.Maintenance
* Menerbitkan versi rilis cmdlet Pemeliharaan untuk GA

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan cmdlet untuk cakupan tautan pribadi
    - 'Get-AzInsightsPrivateLinkScope'
    - 'Remove-AzInsightsPrivateLinkScope'
    - 'New-AzInsightsPrivateLinkScope'
    - 'Update-AzInsightsPrivateLinkScope'
    - 'Get-AzInsightsPrivateLinkScopedResource'
    - 'New-AzInsightsPrivateLinkScopedResource'
    - 'Remove-AzInsightsPrivateLinkScopedResource'

#### <a name="aznetwork"></a>Az.Network
* Memperbarui cmdlet untuk mengaktifkan koneksi pada IP privat untuk Virtual Network Gateway.
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
        - Menambahkan parameter opsional lain AddressPrefixType untuk menentukan keluarga alamat prefiks alamat
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
* Mendukung audit ke akun penyimpanan di VNet.

#### <a name="azstorage"></a>Az.Storage
* Menambahkan pemberitahuan perubahan mencolok untuk perubahan output cmdlet Azure File dalam rilis mendatang
* Mendukung SkuName StandardGZRS, StandardRAGZRS baru saat membuat/memperbarui akun Penyimpanan
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
* Modul Az sekarang tersedia dalam pratinjau di Azure Stack Hub. Hal ini memungkinkan kompatibilitas lintas platform dengan Linux dan macOs. Azure Stack Hub sekarang mendukung inti PowerShell dengan modul Az, informasi selengkapnya [di sini](/azure-stack/operator/powershell-install-az-module)
* Profil dukungan modul Az 2019-03-01-hibrida:
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
* Perintah relatif tetap sama, dengan perubahan kecil seperti mengubah AzureRM menjadi Az
* Tautan ke dokumentasi PowerShell yang diperbarui untuk Azure Stack Hub dapat ditemukan [di sini](/azure-stack/operator/powershell-install-az-module)

## <a name="370---march-2020"></a>3.7.0 - Maret 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki 'Get-AzTenant'/'Get-AzDefault'/'Set-AzDefault' melemparkan NullReferenceException saat tidak login [#10292]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter berikut ke cmdlet 'New-AzDiskConfig':
    - DiskIOPSReadOnly, DiskMBpsReadOnly, MaxSharesCount, GalleryImageReference
* Memungkinkan properti Enkripsi ke parameter Target cmdlet 'New-AzGalleryImageVersion'.
* Memperbaiki masalah tempDisk untuk cmdlet 'Set-AzVmss' -Reimage dan 'Invoke-AzVMReimage'. [#11354]
* Menambahkan dukungan untuk cmdlet di bawah ini untuk Ekstensi SAP baru
    - 'Set-AzVMAEMExtension'
    - 'Get-AzVMAEMExtension'
    - 'Remove-AzVMAEMExtension'
    - 'Update-AzVMAEMExtension'
* Memperbaiki kesalahan dalam contoh dokumen bantuan
* Menampilkan nilai string yang tepat untuk VM PowerState dalam format tabel.
* 'New-AzVmssConfig': memperbaiki serialisasi properti AutomaticRepairs saat SinglePlacementGroup dinonaktifkan. [#11257]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.8.0
* Menambahkan parameter opsional untuk perintah 'Invoke-AzDataFactoryV2Pipeline' untuk mendukung eksekusi ulang

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan deskripsi perubahan mencolok untuk 'Export-AzDataLakeStoreItem' dan 'Import-AzDataLakeStoreItem'
* Menambahkan opsi pengodean Byte untuk 'New-AzDataLakeStoreItem', 'Add-AzDAtaLakeStoreItemContent', dan 'Get-AzDAtaLakeStoreItemContent'

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung penentuan versi TLS minimal yang didukung saat membuat kluster.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola pengaturan terdistribusi per perangkat. Cmdlet baru adalah:
    - 'Get-AzIotHubDistributedTracing'
    - 'Set-AzIotHubDistributedTracing'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan atribut perubahan mencolok ke 'New-AzKeyVault'

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
* Azure Site Recovery menambahkan dukungan untuk melakukan perlindungan ulang dan memperbarui properti vm untuk Virtual Machines yang dienkripsi disk Azure.
* Menambahkan pemantauan DR properti VmwareToAzure Azure Site Recovery
* Azure Backup menambahkan dukungan untuk pembaruan kebijakan percobaan kembali untuk item yang gagal.
* Azure Backup Menambahkan dukungan untuk pengaturan pengecualian disk selama pencadangan dan pemulihan.
* Azure Backup Menambahkan Dukungan untuk Memulihkan Beberapa file/folder di AzureFileShare
* Azure Backup Menambahkan dukungan untuk dukungan Resourcegroup yang ditentukan Pengguna saat memperbarui Kebijakan IaasVM

#### <a name="azresources"></a>Az.Resources
* Memperbaiki 'Get-AzResource -ResourceGroupName -Name -ExpandProperties -ResourceType' untuk menggunakan apiVersion sumber daya yang sebenarnya alih-alih apiVersion default [#11267]
* Menambahkan pengelogan correlationId untuk skenario kesalahan
* Perubahan dokumentasi kecil untuk 'Get-AzResourceLock'. Menambahkan contoh.
* Memberi tanda escape pada kutipan tunggal dalam nilai parameter 'Get-AzADUser' [#11317]
* Menambahkan cmdlet baru untuk Skrip Penyebaran ('Get-AzDeploymentScript', 'Get-AzDeploymentScriptLog', 'Save-AzDeploymentScriptLog', 'Remove-AzDeploymentScript')

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter sekunder yang dapat dibaca untuk 'Invoke-AzSqlDatabaseFailover'
* Menambahkan cmdlet 'Disable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menyimpan peringkat sensitivitas saat mengklasifikasikan kolom dalam database.

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
* Buka halaman survei Azure PowerShell di 'Send-Feedback' [#11020]
* Menampilkan URL survei Azure PowerShell di 'Resolve-Error' [#11021]
* Menambahkan versi Az di UserAgent

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan dukungan untuk mengambil dan mengonfigurasi Domain Kustom pada Titik Akhir DeveloperPortal [#11007]
* 'Export-AzApiManagementApi' Menambahkan dukungan untuk mengunduh Definisi Api dalam format Json [#9987]
* 'Import-AzApiManagementApi' Menambahkan dukungan untuk mengimpor definisi OpenApi 3.0 dari dokumen Json
* 'New-AzApiManagementIdentityProvider' dan 'Set-AzApiManagementIdentityProvider' Menambahkan dukungan untuk mengonfigurasi 'Signin Tenant' untuk Penyedia B2C AAD [#9784]

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
* Menambahkan dukungan untuk mengelola hubungan orang tua-anak perangkat.

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nilai output untuk 'Get-AzMetricDefinition' [#9714]

#### <a name="aznetwork"></a>Az.Network
* Memperbarui SDK Manajemen Sql.
* Memperbaiki masalah perbedaan penamaan di kelas PrivateLinkServiceConnectionState.
    - Memetakan bidang ActionsRequired ke ActionRequired.
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug referensi null di 'Get-AzRoleAssignment'
* Menandai switch '-Force' dan '-PassThru' opsional di 'Remove-AzADGroup' [#10849]
* Memperbaiki masalah di mana 'MailNickname' tidak kembali di 'Remove-AzADGroup' [#11167]
* Memperbaiki masalah di mana operasi pipa 'Remove-AzADGroup' tidak berfungsi [#11171]
* Memperbaiki bug referensi null di GetAzureRoleAssignmentCommand
* Menambahkan atribut perubahan mencolok untuk perubahan mendatang ke cmdlet kebijakan
* Memperbarui 'Get-AzResourceGroup' untuk melakukan pemfilteran tag grup sumber daya di sisi server
* Memperluas cmdlet Tag untuk menerima -ResourceId
    - Get-AzTag -ResourceId
    - New-AzTag -ResourceId
    - Remove-AzTag -ResourceId
* Menambahkan cmdlet Tag baru
    - Update-AzTag -ResourceId
* Membawa ScopedDeployment dari SDK 3.3.0

#### <a name="azsql"></a>Az.Sql
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Menambahkan dukungan untuk konfigurasi cadangan Retensi Jangka Panjang untuk Database Terkelola
    - Dapatkan/Atur kebijakan LTR pada database terkelola
    - Dapatkan pencadangan LTR berdasarkan database terkelola, instans terkelola, atau berdasarkan lokasi
    - Menghapus cadangan LTR
    - Memulihkan cadangan LTR untuk membuat database terkelola baru
* Menambahkan MinimalTlsVersion ke New-AzSqlServer dan Set-AzSqlServer
* Menambahkan MinimalTlsVersion ke New-AzSqlInstance dan Set-AzSqlInstance
* Mengubah versi SDK SQL untuk Az.Network

#### <a name="azstorage"></a>Az.Storage
* Mendukung AllowProtectedAppendWrite pada ImmutabilityPolicy
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
* Menambahkan pesan peringatan perubahan mencolok untuk perubahan jenis AzureStorageTable di rilis mendatang
    - 'New-AzStorageTable'
    - 'Get-AzStorageTable'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan parameter Tag untuk 'New-AzAppServicePlan' dan 'Set-AzAppServicePlan'
* Hentikan eksekusi cmdlet apabila pengecualian dilemparkan saat menambahkan domain kustom ke situs web
* Menambahkan dukungan untuk melakukan operasi untuk Layanan Aplikasi yang tidak berada dalam grup sumber daya yang sama dengan Paket Layanan Aplikasi
* Menerapkan pembatasan akses untuk WebApp/Function di grup sumber daya yang berbeda
* Memperbaiki masalah untuk mengatur nama host kustom untuk WebAppSlots

## <a name="350---february-2020"></a>3.5.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Memperbarui telemetri sisi klien.
* Az.IotHub menambahkan cmdlet untuk mendukung pengelolaan perangkat.
* Az.SqlVirtualMachine menambahkan cmdlet untuk Pendengar Grup Ketersediaan.

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan SubscriptionId, TenantId, dan waktu eksekusi ke dalam data telemetri sisi klien

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan pengetikan di Contoh 1 dalam dokumentasi referensi untuk 'New-AzAutomationSoftwareUpdateConfiguration'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui SDK ke 7.0
* Meningkatkan pesan kesalahan saat isi respons server kosong

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
* Menambahkan contoh Pengambilan Paket untuk mengambil semua paket dalam dan luar dalam Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Mendukung Kebijakan Azure Firewall pada Firewall VNet
    - Tidak ada cmdlet baru yang ditambahkan. Melonggarkan pembatasan untuk kebijakan firewall pada firewall VNet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Dukungan untuk Restore-as-files untuk SQL Database.

#### <a name="azresources"></a>Az.Resources
* Merefaktorisasi cmdlet penyebaran templat
    - Menambahkan cmdlet baru untuk mengelola penyebaran di grup manajemen: *-AzManagementGroupDeployment
    - Menambahkan cmdlet baru untuk mengelola penyebaran di cakupan penyewa: *-AzTenantDeployment
    - Merefaktorisasi cmdlet *-AzDeployment untuk bekerja secara khusus di cakupan langganan
    - Membuat alias *-AzSubscriptionDeployment untuk cmdlet *-AzDeployment
* Memperbaiki 'Update-AzADApplication' saat parameter 'AvailableToOtherTenants' tidak diatur
* Menghapus ApplicationObjectWithoutCredentialParameterSet untuk menghindari AmbiguousParameterSetException.
* Meregenerasi file bantuan

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk pemulihan titik waktu lintas langganan pada Instans Terkelola.
* Menambahkan dukungan untuk mengubah generasi perangkat keras Instans Terkelola Sql yang ada
* Memperbaiki contoh bantuan 'Update-AzSqlServerVulnerabilityAssessmentSetting': output parameter/properti - EmailAdmins

#### <a name="azsqlvirtualmachine"></a>Az.SqlVirtualMachine
* Menambahkan cmdlet untuk Pendengar Grup Ketersediaan

#### <a name="azstoragesync"></a>Az.StorageSync
* Memperbarui set karakter yang didukung di 'Invoke-AzStorageSyncCompatibilityCheck'.

## <a name="340---february-2020"></a>3.4.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Az.CosmosDB versi awal 0.1.0 dirilis
* Dukungan Az.Network ConnectionMonitor V2 ditambahkan

#### <a name="azaccounts"></a>Az.Accounts
* Nonaktifkan penyimpanan otomatis konteks saat AzureRmContext.json tidak tersedia
* Memperbarui referensi untuk Azure Powershell Common ke 1.3.5-pratinjau

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Get-AzApiManagementApiSchema** Memperbaiki pengaitan Skema Open-Api dengan API   https://github.com/Azure/azure-powershell/issues/10626
* **New-AzApiManagementProduct** _ dan _ *Set-AzApiManagementProduct**
  - Memperbaiki dokumentasi untuk https://github.com/Azure/azure-powershell/issues/10472
* **Set-AzApiManagementApi** Menambahkan contoh untuk menunjukkan cara memperbarui ServiceUrl menggunakan cmdlet

#### <a name="azcompute"></a>Az.Compute
* Batasi jumlah status VM hingga 100 untuk menghindari pembatasan saat Get-AzVM -Status dijalankan tanpa nama VM.
* Menambahkan cmdlet Update-AzDiskEncryptionSet
* Menambahkan parameter EncryptionType dan DiskEncryptionSetId ke cmdlet berikut:
    - New-AzDiskUpdateConfig, New-AzSnapshotUpdateConfig
* Menambahkan parameter ColocationStatus untuk cmdlet Get-AzProximityPlacementGroup.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.7.0

#### <a name="azdeploymentmanager"></a>Az.DeploymentManager
* Menambahkan operasi LIST untuk sumber daya
* Menambahkan kemampuan untuk melakukan operasi pada langkah-langkah Pemeriksaan Kesehatan

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki kesalahan dokumen New-AzHDInsightCluster.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan alias Nama untuk atribut VaultName untuk membuat Remove-AzureKeyVault konsisten dengan New-AzureKeyVault.

#### <a name="aznetwork"></a>Az.Network
* Contoh baru ditambahkan ke Set-AzNetworkWatcherConfigFlowLog.md untuk menunjukkan skenario penonaktifan Analitik Lalu Lintas.
* Menambahkan dukungan untuk menetapkan konfigurasi IP manajemen ke Azure Firewall - subnet khusus dan IP Publik yang akan digunakan firewall untuk lalu lintas manajemennya
    - Memperbarui cmdlet New-AzFirewall:
        - Menambahkan parameter -ManagementPublicIpAddress (tidak wajib) yang menerima objek Alamat IP Publik
        - Menambahkan metode SetManagementIpConfiguration pada objek firewall - memerlukan subnet dan alamat IP Publik sebagai input - nama subnet harus 'AzureFirewallManagementSubnet'
* Mengoreksi contoh Get-AzNetworkSecurityGroup untuk menampilkan contoh untuk NSG, bukan antarmuka jaringan.
* Memperbaiki kesalahan pengetikan dalam perintah New-AzVpnSite yang mencegah pelengkap id sumber daya menyelesaikan parameter.
* Menambahkan dukungan untuk Konfigurasi Url dalam Set Tindakan Aturan Penulisan Ulang di Application Gateway
    - Cmdlet baru ditambahkan:
        - New-AzApplicationGatewayRewriteRuleUrlConfiguration
    - Cmdlet diperbarui dengan parameter opsional - UrlConfiguration
        - New-AzApplicationGatewayRewriteRuleActionSet
* Menambahkan dukungan untuk sumber daya NetworkWatcher ConnectionMonitor versi 2

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Mendukung evaluasi kepatuhan sebelum menentukan sumber daya apa yang akan diremediasi
    - Menambahkan parameter '-ResourceDiscoverMode' untuk Start-AzPolicyRemediation
* Menambahkan cmdlet Get-AzPolicyMetadata untuk mendapatkan sumber daya metadata kebijakan
* Memperbarui Get-AzPolicyState dan Get-AzPolicyStateSummary untuk API versi 2019-10-01

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk menghapus disk yang direplikasi.
* Azure Backup menambahkan dukungan untuk menambahkan tag saat membuat Brankas Layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Menjadikan -Scope opsional di cmdlet *-AzPolicyAssignment dengan default untuk langganan konteks
* Menambahkan contoh pembuatan ADServicePrincipal dengan kata sandi dan info masuk kunci

#### <a name="azsql"></a>Az.Sql
Memperbaiki cmdlet New-AzSqlDatabaseSecondary untuk memeriksa keberadaan PartnerDatabaseName alih-alih keberadaan DatabaseName.

#### <a name="azstorage"></a>Az.Storage
* Mendukung pengaturan Jenis Kunci Enkripsi Tabel/Antrean di Buat Akun Penyimpanan
    - New-AzStorageAccount
* Menampilkan RequestId saat StorageException tidak memiliki ExtendedErrorInformation
* Memperbaiki Contoh 6 cmdlet Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Az.Websites
* Set-AzWebapp dan Set-AzWebappSlot mendukung properti AlwaysOn, MinTls, dan FtpsState
* Memperbaiki masalah di mana mengatur HttpsOnly bersama dengan mengubah AppservicePlan pada saat yang sama menggunakan Perintah Set-AzWebApp tunggal, mengatur ulang HttpsOnly ke nilai default

## <a name="330---january-2020"></a>3.3.0 - Januari 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAttestationServiceEndpointResourceId dan AzureAttestationServiceEndpointSuffix

#### <a name="azcdn"></a>Az.Cdn
* Menampilkan detail respons kesalahan di cmdlet New-AzCdnEndpoint

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki cmdlet Set-AzVMCustomScriptExtension untuk VM dengan disk OD terkelola yang tidak memiliki profil OS.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbaiki nama parameter yang digunakan oleh contoh New-AzContainerGroup

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Menambahkan cmdlet 'Get-AzDataBoxEdgeStorageContainer'
  - Mendapatkan Kontainer Penyimpanan Tepi
* Menambahkan cmdlet 'New-AzDataBoxEdgeStorageContainer'
  - Membuat Kontainer Penyimpanan Tepi baru
* Menambahkan cmdlet 'Remove-AzDataBoxEdgeStorageContainer'
  - Menghapus Kontainer Penyimpanan Tepi
* Menambahkan cmdlet 'Invoke-AzDataBoxEdgeStorageContainer'
  - Memanggil tindakan untuk me-refresh data di Kontainer Penyimpanan Tepi
* Menambahkan cmdlet 'Get-AzDataBoxEdgeStorageAccount'
  - Mendapatkan Akun Penyimpanan Tepi
* Menambahkan cmdlet 'New-AzDataBoxEdgeStorageAccount'
  - Membuat Akun Penyimpanan Tepi baru
* Menambahkan cmdlet 'Remove-AzDataBoxEdgeStorageAccount'
  - Menghapus Akun Penyimpanan Tepi
* Memanggil cmdlet 'Invoke-AzDataBoxEdgeShare'
  - Memanggil tindakan untuk me-refresh data pada berbagi
* Menambahkan cmdlet 'Set-AzDataBoxEdgeStorageAccountCredential'
  - Mengatur info masuk akun penyimpanan az databoxedge

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan properti AutoUpdateETA, LatestVersion, PushedVersion, TaskQueueId, dan VersionStatus untuk cmd Get-AzDataFactoryV2IntegrationRuntime
* Memperbarui versi SDK .Net ADF ke 4.6.0
* Menambahkan parameter 'PublicIPs' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan pembuatan Azure-SSIS IR dengan alamat IP publik statis.

#### <a name="azdevtestlabs"></a>Az.DevTestLabs
* Menghapus hyperlink rusak di Get-AzDtlAllowedVMSizesPolicy.md

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan untuk masalah 10634 : Memperbaiki referensi Objek null untuk menghapus eventhubnamespace

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
* Azure Site Recovery mengubah dukungan untuk vm disk terkelola yang dienkripsi saat tidak aktif dengan kunci yang dikelola pelanggan untuk Azure ke penyedia Azure.
* Dukungan Azure Site Recovery untuk memasukkan enkripsi disk Set Id sebagai input opsional untuk mengaktifkan perlindungan Vmware ke Azure.
* Dukungan Azure Site Recovery untuk memasukkan enkripsi disk Set Id sebagai input opsional di tingkat disk untuk mengaktifkan perlindungan Vmware ke Azure.
* Dukungan Azure Site Recovery untuk memperbarui item yang dilindungi replikasi dengan set enkripsi disk Map untuk HyperV ke Azure.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki kesalahan dalam dokumen bantuan 'Remove-AzTag'.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki penilaian kerentanan dan mengatur fungsionalitas cmdlet garis besar untuk mengerjakan master db untuk database azure dan membatasinya pada database sistem instans terkelola.
* Memperbaiki kesalahan saat membuat grup failover instans SQL

#### <a name="azsqlvirtualmachine"></a>Az.SqlVirtualMachine
* Menambahkan DR sebagai jenis Lisensi baru yang valid

#### <a name="azstorage"></a>Az.Storage
* Menambahkan pesan peringatan perubahan mencolok untuk perubahan Nilai DefaultAction dalam rilis mendatang
    - Update-AzStorageAccountNetworkRuleSet
* Mendukung Get waktu sinkronisasi terakhir akun Penyimpanan dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeGeoReplicationStats
    - Get-AzureRMStorageAccount

## <a name="320---december-2019"></a>3.2.0 - Desember 2019

### <a name="general"></a>Umum
* Memperbarui referensi di .psd1 untuk menggunakan jalur relatif untuk semua modul

#### <a name="azaccounts"></a>Az.Accounts
* Mengatur UserAgent yang benar pada telemetri sisi klien untuk pratinjau Az 4.0
* Menampilkan pesan kesalahan yang ramah pengguna saat konteks null di pratinjau Az 4.0

#### <a name="azbatch"></a>Az.Batch
* Memperbaiki masalah [#10602](https://github.com/Azure/azure-powershell/issues/10602), di mana **New-AzBatchPool** tidak mengirim 'VirtualMachineConfiguration.ContainerConfiguration' atau 'VirtualMachineConfiguration.DataDisks' ke server dengan benar.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.5.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan dukungan pengecualian aturan terkelola WAF
* Menambahkan SocketAddr untuk penyelesaian otomatis

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Penanganan Pengecualian

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki kesalahan mengakses nilai yang berpotensi tidak diatur
* Manajemen Sertifikat Kriptografi Kurva Elips
    - Menambahkan dukungan untuk menentukan Kurva untuk Kebijakan Sertifikat

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan argumen opsional untuk perintah Tambahkan Pengaturan Diagnostik. Argumen switch yang jika ada menunjukkan bahwa ekspor ke Log Analytics harus ke skema tetap (a.k.a. khusus, jenis data)

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk IpGroups di Aplikasi AzureFirewall, Nat & Aturan Jaringan.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah di mana penyebaran templat gagal membaca parameter templat jika namanya bertentangan dengan beberapa nama parameter bawaan.
* Memperbarui cmdlet kebijakan untuk menggunakan versi api baru 2019-09-01 yang memperkenalkan dukungan pengelompokan dalam definisi set kebijakan.

#### <a name="azsql"></a>Az.Sql
* Meningkatkan pembuatan penyimpanan dalam pengaktifan otomatis Penilaian Kerentanan ke StorageV2

#### <a name="azstorage"></a>Az.Storage
* Dukungan menghasilkan token SAS berbasis Identitas Blob/Kontainer dengan Konteks Penyimpanan berdasarkan autentikasi Oauth
    - New-AzStorageContainerSASToken
    - New-AzStorageBlobSASToken
* Dukungan mencabut Kunci Delegasi Pengguna Akun Penyimpanan, sehingga semua token SAS Identitas dicabut
    - Revoke-AzStorageAccountUserDelegationKeys
* Meningkatkan ke Microsoft.Azure.Management.Storage 14.2.0, untuk mendukung API baru versi 2019-06-01.
* Dukungan QuotaGiB (Berbagi Kuota dalam Gibibye) untuk nilai melebihi 5120 di bidang Manajemen cmdlet Berbagi File dan menambahkan alias parameter 'Quota' ke parameter 'QuotaGiB'.
    - New-AzRmStorageShare
    - Update-AzRmStorageShare
* Menambahkan alias parameter 'QuotaGiB' untuk parameter 'Kuota'
    - Set-AzStorageShareQuota
* Memperbaiki masalah di mana Set-AzStorageContainerAcl dapat membersihkan Kebijakan Akses yang tersimpan
    - Set-AzStorageContainerAcl

## <a name="310---november-2019"></a>3.1.0 - November 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Az.DataBoxEdge 1.0.0 dirilis
* Az.SqlVirtualMachine 1.0.0 dirilis

#### <a name="azcompute"></a>Az.Compute
* Fitur Pengaplikasian ulang mesin virtual
    - Menambahkan parameter Pengaplikasian ulang untuk cmdlet Set-AzVM
* Fitur AutomaticRepairs Set Skala VM:
    - Menambahkan EnableAutomaticRepair, AutomaticRepairGracePeriod, dan AutomaticRepairMaxInstanceRepairsPercent parameter ke cmdlet berikut: New-AzVmssConfig Update-AzVmss
* Dukungan citra galeri lintas penyewa untuk New-AzVM
* Menambahkan 'Spot' ke pelengkap argumen parameter Prioritas di cmdlet New-AzVM, New-AzVMConfig, dan New-AzVmss
* Menambahkan parameter DiskIOPSReadWrite dan DiskMBpsReadWrite ke cmdlet Add-AzVmssDataDisk
* Mengubah parameter SourceImageId dari cmdlet New-AzGalleryImageVersion menjadi opsional
* Menambahkan parameter OSDiskImage dan DataDiskImage ke cmdlet New-AzGalleryImageVersion
* Menambahkan parameter HyperVGeneration ke cmdlet New-AzGalleryImageDefinition
* Menambahkan parameter SkipExtensionsOnOverprovisionedVMs untuk cmdlet New-AzVmss, New-AzVmssConfig, dan Update-AzVmss

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Menambahkan cmdlet `Get-AzDataBoxEdgeOrder`
    - Mendapatkan Pesanan
* Menambahkan cmdlet `New-AzDataBoxEdgeOrder`
    - Membuat Pesanan baru
* Menambahkan cmdlet `Remove-AzDataBoxEdgeOrder`
    - Menghapus Pesanan
* Perubahan dalam cmdlet `New-AzDataBoxEdgeShare`
    - Sekarang membuat Berbagi Lokal
* Menambahkan cmdlet `Set-AzDataBoxEdgeRole`
    - Sekarang IotRole dapat dipetakan ke Berbagi
* Menambahkan cmdlet `Invoke-AzDataBoxEdgeDevice`
    - Memanggil pembaruan pemindaian, mengunduh pembaruan, menginstal pembaruan pada perangkat
* Menambahkan cmdlet `Get-AzDataBoxEdgeTrigger`
    - Mendapatkan informasi mengenai Pemicu
* Menambahkan cmdlet `New-AzDataBoxEdgeTrigger`
    - Membuat Pemicu baru
* Menambahkan cmdlet `Remove-AzDataBoxEdgeTrigger`
    - Menghapus Pemicu

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.4.0
* Menambahkan parameter 'ExpressCustomSetup' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan konfigurasi penyiapan dan komponen pihak ke-3 tanpa skrip penyiapan kustom.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui dokumentasi Get-AzDataLakeStoreDeletedItem dan Restore-AzDataLakeStoreDeletedItem

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan untuk masalah 10301 : Memperbaiki format tanggal Token SAS

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan parameter MinimumTlsVersion untuk Enable-AzFrontDoorCustomDomainHttps dan New-AzFrontDoorFrontendEndpointObject
* Menambahkan parameter HealthProbeMethod dan EnabledState untuk New-AzFrontDoorHealthProbeSettingObject
* Menambahkan cmdlet baru untuk membuat objek BackendPoolsSettings untuk masuk ke pembuatan/pembaruan Front Door
    - New-AzFrontDoorBackendPoolsSettingObject

#### <a name="aznetwork"></a>Az.Network
* Mengubah contoh opsi FilterData 'Start-AzVirtualNetworkGatewayConnectionPacketCapture.md' dan 'Start-AzVirtualnetworkGatewayPacketCapture.md'.

#### <a name="azprivatedns"></a>Az.PrivateDns
* Memperbarui PrivateDns .net sdk ke versi 1.0.0

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk memilih jenis disk saat mengaktifkan perlindungan.
* Perbaikan bug Azure Site Recovery untuk pengeditan tindakan rencana pemulihan.
* Dukungan Pemulihan Azure Backup SQL untuk menerima aliran file DB.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'MinimumTlsVersion' di cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'. Selain itu, menambahkan 'MinimumTlsVersion' dalam output cmdlet 'Get-AzRedisCache'.
* Menambahkan validasi pada parameter '-Size' untuk cmdlet 'Set-AzRedisCache' dan 'New-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
- Memperbarui cmdlet kebijakan untuk menggunakan versi api baru 2019-06-01 yang memiliki properti EnforcementMode baru dalam penetapan kebijakan.
- Memperbarui contoh bantuan definisi pembuatan kebijakan
- Memperbaiki bug Remove-AZADServicePrincipal -ServicePrincipalName, melemparkan referensi null saat nama prinsipal layanan tidak ditemukan.
- Memperbaiki bug New-AZADServicePrincipal, melemparkan referensi null saat penyewa tidak memiliki langganan apa pun.
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
* Mengganti nama `CoreQuota` pada `BatchAccountContext` menjadi `DedicatedCoreQuota`. Juga terdapat `LowPriorityCoreQuota` baru.
  - Hal ini memengaruhi **Get-AzBatchAccount**.
* Parameter `-ResourceFile` **New-AzBatchTask** sekarang mengambil koleksi objek `PSResourceFile`, yang dapat dibangun menggunakan cmdlet **New-AzBatchResourceFile** baru.
* Cmdlet **New-AzBatchResourceFile** baru untuk membantu membuat objek `PSResourceFile`. Ini dapat dipasok ke **New-AzBatchTask** pada parameter `-ResourceFile`.
  - Ini mendukung dua jenis file sumber daya baru selain cara `HttpUrl` yang ada:
    - File sumber daya berbasis `AutoStorageContainerName` mengunduh seluruh kontainer penyimpanan otomatis ke node Batch.
    - File sumber daya berbasis `StorageContainerUrl` mengunduh kontainer yang ditentukan dalam URL ke node Batch.
* Menghapus properti `ApplicationPackages` dari `PSApplication` yang dikembalikan oleh **Get-AzBatchApplication**.
  - Paket spesifik di dalam aplikasi sekarang dapat diambil menggunakan **Get-AzBatchApplicationPackage**. Misalnya: `Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication`.
* Mengganti nama`ApplicationId` menjadi `ApplicationName`di **Get-AzBatchApplicationPackage**, **New-AzBatchApplicationPackage**, **Remove-AzBatchApplicationPackage**, **Get-AzBatchApplication**, **New-AzBatchApplication**, **Remove-AzBatchApplication**, dan **Set-AzBatchApplication**.
  - `ApplicationId` sekarang adalah alias dari `ApplicationName`.
* Menambahkan properti `PSWindowsUserConfiguration` baru ke `PSUserAccount`.
* Mengganti nama `Version` menjadi `Name` di `PSApplicationPackage`.
* Mengganti nama `BlobSource` menjadi `HttpUrl` di `PSResourceFile`.
* Menghapus properti `OSDisk` dari `PSVirtualMachineConfiguration`.
* Menghapus **Set-AzBatchPoolOSVersion**. Operasi ini tidak lagi didukung.
* Menghapus `TargetOSVersion` dari `PSCloudServiceConfiguration`
* Mengganti nama `CurrentOSVersion` menjadi `OSVersion` di `PSCloudServiceConfiguration`.
* Menghapus `DataEgressGiB` dan `DataIngressGiB` dari `PSPoolUsageMetrics`.
* Menghapus **Get-AzBatchNodeAgentSku** dan menggantinya dengan **Get-AzBatchSupportedImage**.
  - **Get-AzBatchSupportedImage** memunculkan data yang sama dengan **Get-AzBatchNodeAgentSku** tetapi dalam format yang lebih ramah.
  - Citra baru yang tidak diverifikasi juga sekarang dikembalikan. Informasi tambahan mengenai `Capabilities` dan `BatchSupportEndOfLife` untuk setiap citra juga disertakan.
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
    - Cmdlet baru:   New-AzDiskEncryptionSetConfig   New-AzDiskEncryptionSet   Get-AzDiskEncryptionSet   Remove-AzDiskEncryptionSet
    - Parameter DiskEncryptionSetId ditambahkan ke cmdlet berikut:   Set-AzImageOSDisk   Set-AzVMOSDisk   Set-AzVmssStorageProfile   Add-AzImageDataDisk   New-AzVMDataDisk   Set-AzVMDataDisk   Add-AzVMDataDisk   Add-AzVmssDataDisk   Add-AzVmssVMDataDisk
    - Parameter DiskEncryptionSetId dan EncryptionType ditambahkan ke cmdlet berikut:   New-AzDiskConfig   New-AzSnapshotConfig
* Menambahkan parameter PublicIPAddressVersion untuk New-AzVmssIPConfig
* Memindahkan FileUris ekstensi skrip kustom dari pengaturan publik ke pengaturan yang dilindungi
* Menambahkan ScaleInPolicy untuk cmdlet New-AzVmss, New-AzVmssConfig, dan Update-AzVmss
* Perubahan mencolok
    - Parameter UploadSizeInBytes digunakan, bukan DiskSizeGB, untuk New-AzDiskConfig saat CreateOption adalah Upload
    - PublishingProfile.Source.ManagedImage.Id diganti dengan StorageProfile.Source.Id di objek GalleryImageVersion

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.3.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui versi SDK ADLS (https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-123-alpha), menghadirkan perbaikan berikut
* Hindari pembuangan pengecualian saat tidak dapat melakukan deserialisasi creationtime dari entri keranjang sampah atau direktori.
* Mengekspos pengaturan per batas waktu permintaan di adlsclient
* Memperbaiki penyerahan syncflag asli untuk pemulihan badoffset
* Memperbaiki EnumerateDirectory untuk mengambil token kelanjutan setelah respons diperiksa
* Memperbaiki Bug Concat

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbaiki kesalahan pengetikan lain-lain di seluruh modul

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki bug di mana pelanggan akan mendapatkan kesalahan 'Bukan string Base-64 yang valid' saat menggunakan Get-AzHDInsightCluster untuk mendapatkan kluster dengan penyimpanan ADLSGen1.
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
* Menghapus set parameter('Spark1', 'Spark2') dari Add-AzHDInsightConfigValue.
* Menambahkan contoh ke dokumen bantuan cmdlet Add-AzHDInsightSecurityProfile.
* Mengubah jenis output dari cmdlet berikut:
*  - Mengubah jenis output Get-AzHDInsightProperties dari CapabilitiesResponse ke AzureHDInsightCapabilities.
*  - Mengubah jenis output Remove-AzHDInsightCluster dari ClusterGetResponse menjadi bool.
*  - Mengubah jenis output Set-AzHDInsightGatewaySettings HttpConnectivitySettings menjadi GatewaySettings.
* Menambahkan beberapa kasus uji skenario.
* Menghapus beberapa alias: 'Add-AzHDInsightConfigValues', 'Get-AzHDInsightProperties'.

#### <a name="aziothub"></a>Az.IotHub
* Perubahan mencolok:
    - Cmdlet 'Add-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Set parameter '__AllParameterSets' untuk cmdlet 'Add-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Get-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Set parameter '__AllParameterSets' untuk cmdlet 'Get-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Properti 'OperationsMonitoringProperties' dari jenis 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubProperties' telah dihapus.
    - Properti 'OperationsMonitoringProperties' dari jenis 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubInputProperties' telah dihapus.
    - Cmdlet 'New-AzIotHubExportDevice' tidak lagi mendukung alias 'New-AzIotHubExportDevices'.
    - Cmdlet 'New-AzIotHubImportDevice' tidak lagi mendukung alias 'New-AzIotHubImportDevices'.
    - Cmdlet 'Remove-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Set parameter '__AllParameterSets' untuk cmdlet 'Remove-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Set-AzIotHub' tidak lagi mendukung parameter 'OperationsMonitoringProperties' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Set parameter 'UpdateOperationsMonitoringProperties' untuk cmdlet 'Set-AzIotHub' telah dihapus.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk mengonfigurasi sumber daya jaringan seperti NSG, IP publik, dan penyeimbang beban internal untuk Azure ke Azure.
* Dukungan Azure Site Recovery untuk menulis ke disk terkelola untuk vMWare ke Azure.
* Dukungan Azure Site Recovery untuk pengurangan NIC untuk vMWare ke Azure.
* Dukungan Azure Site Recovery ke jaringan yang dipercepat untuk Azure ke Azure.
* Dukungan Azure Site Recovery ke agen pembaruan otomatis untuk Azure ke Azure.
* Dukungan Azure Site Recovery ke SSD Standar untuk Azure ke Azure.
* Dukungan Azure Site Recovery ke Azure Disk Encryption dua sandi untuk Azure ke Azure.
* Dukungan Azure Site Recovery untuk melindungi disk yang baru ditambahkan untuk Azure ke Azure.
* Menambahkan fitur SoftDelete untuk VM dan menambahkan pengujian untuk softdelete

#### <a name="azresources"></a>Az.Resources
* Memperbarui assembly dependensi Microsoft.Extensions.Caching.Memory dari 1.1.1 menjadi 2.2

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
* Menambahkan bidang dan parameter baru untuk fitur Protokol Proksi V2.
    - Menambahkan properti EnableProxyProtocol di PrivateLinkService
    - Menambahkan properti LinkIdentifier di PrivateEndpointConnection
    - Memperbarui New-AzPrivateLinkService untuk menambahkan parameter opsional baru EnableProxyProtocol.
* Memperbaiki deskripsi parameter yang salah dalam dokumentasi referensi 'New-AzApplicationGatewaySku'
* Cmdlet baru untuk mendukung kebijakan firewall azure
* Menambahkan dukungan untuk RouteTables sumber daya turunan VirtualHub
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
* Menambahkan dukungan untuk Mengonfigurasi Kebijakan WebApplicationFirewall TopLevel
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
* Menambahkan dukungan untuk kebijakan perListener dan perSite Firewall
    - Cmdlet diperbarui dengan parameter opsional:
        - New-AzApplicationGatewayHttpListener : menambahkan parameter FirewallPolicy, FirewallPolicyId
        - New-AzApplicationGatewayPathRuleConfig : menambahkan parameter FirewallPolicy, FirewallPolicyId
* Memperbaiki subnet yang diperlukan dengan nama AzureBastionSubnet di 'PSBastion' dapat tidak peka huruf besar atau kecil
* Dukungan untuk FQDN Tujuan dalam Aturan Jaringan dan FQDN yang Diterjemahkan dalam Aturan NAT untuk Azure Firewall
* Menambahkan dukungan untuk RouteTable sumber daya tingkat atas dari IpGroup
    - Cmdlet baru ditambahkan:
        - Baru-AzIpGroup
        - Remove-AzIpGroup
        - Dapatkan-AzIpGroup
        - Atur-AzIpGroup

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menghapus cmdlet Add-AzServiceFabricApplicationCertificate karena skenario ini dicakup oleh Add-AzVmssSecret.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk memulihkan database yang dihilangkan pada Instans Terkelola.
* Dihentikan dari cmdlet kode audit lama.
* Menghapus alias yang tidak digunakan lagi:
* Get-AzSqlDatabaseIndexRecommendations (gunakan Get-AzSqlDatabaseIndexRecommendation sebagai gantinya)
* Get-AzSqlDatabaseRestorePoints (gunakan Get-AzSqlDatabaseRestorePoint sebagai gantinya)
* Menghapus cmdlet Get-AzSqlDatabaseSecureConnectionPolicy
* Menghapus alias untuk cmdlet Pengaturan Penilaian Kerentanan yang tidak digunakan lagi
* Menghentikan cmdlet Pengaturan Deteksi Ancaman Tingkat Lanjut
* Menambahkan cmdlet untuk Menonaktifkan dan mengaktifkan rekomendasi sensitivitas pada kolom dalam database.

#### <a name="azstorage"></a>Az.Storage
* Dukungan mengaktifkan berbagi File Besar saat membuat atau memperbarui akun Penyimpanan
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Saat menutup/mendapatkan handel File, lewati periksa jalur input adalah Direktori file atau File, untuk menghindari kegagalan dengan objek di status DeletePending
    -  Get-AzStorageFileHandle
    -  Close-AzStorageFileHandle

## <a name="280---october-2019"></a>2.8.0 - Oktober 2019
### <a name="general"></a>Umum
* Az.HealthcareApis 1.0.0 release

#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui telemetri dan penulisan ulang url untuk modul yang dihasilkan, memperbaiki pengujian unit windows.

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Set-AzApiManagementApi** - Menambahkan dukungan untuk Memperbarui Api ke ApiVersionSet
    - Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/10068

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki cmdlet New-AzureAutomationSoftwareUpdateConfiguration untuk parameter pengaturan boot ulang Linux.

#### <a name="azbatch"></a>Az.Batch
* **Get-AzBatchNodeAgentSku** tidak digunakan lagi dan akan digantikan oleh **Get-AzBatchSupportImage** di versi 2.0.0.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter Priority, EvictionPolicy, dan MaxPrice ke cmdlet New-AzVM dan New-AzVmss
* Memperbaiki pesan peringatan dan dokumen bantuan untuk cmdlet Add-AzVMAdditionalUnattendContent dan Add-AzVMSshPublicKey
* Memperbaiki pengecualian -skipVmBackup untuk VM Linux dengan disk terkelola untuk Set-AzVMDiskEncryptionExtension.
* Memperbaiki bug dalam pengaturan enkripsi pembaruan di Set-AzVMDiskEncryptionExtension, skenario dua sandi.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan perintah CRUD untuk aliran data ADF V2: Set-AzDataFactoryV2DataFlow, Remove-AzDataFactoryV2DataFlow, dan Get-AzDataFactoryV2DataFlow.
* Menambahkan perintah tindakan untuk Sesi debug aliran data ADF V2: Start-AzDataFactoryV2DataFlowDebugSession, Get-AzDataFactoryV2DataFlowDebugSession, Add-AzDataFactoryV2DataFlowDebugSessionPackage, Invoke-AzDataFactoryV2DataFlowDebugSessionCommand dan Stop-AzDataFactoryV2DataFlowDebugSession.
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
* Perbaikan bug kecil: Get-AzIothub tidak mengembalikan subscriptionId

#### <a name="azmonitor"></a>Az.Monitor
* Penerima grup tindakan ditambahkan untuk grup tindakan   -ItsmReceiver   -VoiceReceiver   -ArmRoleReceiver   -AzureFunctionReceiver   -LogicAppReceiver   -AutomationRunbookReceiver   -AzureAppPushReceiver
* Gunakan skema peringatan umum yang diaktifkan untuk penerima. Hal ini tidak berlaku untuk SMS, pendorongan Aplikasi Azure, ITSM, dan penerima Voice
* Webhook sekarang mendukung autentikasi direktori aktif Azure .

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru Get-AzAvailableServiceAlias yang dapat dipanggil untuk mendapatkan alias yang dapat digunakan untuk Kebijakan Titik Akhir Layanan.
* Menambahkan dukungan untuk menambahkan pemilih lalu lintas ke Koneksi Gateway Virtual Network
    - Cmdlet baru ditambahkan:
        - New-AzureRmTrafficSelectorPolicy
    - Cmdlet diperbarui dengan parameter opsional -TrafficSelectorPolicies   -New-AzureRmVirtualNetworkGatewayConnection   -Set-AzureRmVirtualNetworkGatewayConnection
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
* Memperbaiki kesalahan pengetikan contoh dalam dokumentasi referensi untuk 'Register-AzAutomationDscNode'
* Klarifikasi tambahan mengenai pembatasan OS untuk Register-AzAutomationDSCNode
* Memperbaiki pengecualian referensi Null cmdlet Start-AzAutomationRunbook untuk opsi -Wait.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter UploadSizeInBytes tp New-AzDiskConfig
* Menambahkan parameter Bertambah bertahap untuk New-AzSnapshotConfig
* Menambahkan fitur mesin virtual prioritas rendah:
    - Parameter MaxPrice, EvictionPolicy, dan Priority ditambahkan ke New-AzVMConfig.
    - Parameter MaxPrice ditambahkan ke cmdlet New-AzVmssConfig, Update-AzVM, dan Update-AzVmss.
* Memperbaiki masalah referensi VM untuk cmdlet Get-AzAvailabilitySet saat mencantumkan semua set ketersediaan dalam langganan.
* Memperbaiki pengecualian null untuk Get-AzRemoteDesktopFile.
* Memperbaiki metode Pencarian VHD untuk posisi relatif akhir.
* Memperbaiki masalah UltraSSD untuk New-AzVM dan Update-AzVM.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan 3 perintah baru untuk ADF V2 - Add-AzDataFactoryV2TriggerSubscription, Remove-AzDataFactoryV2TriggerSubscription, dan Get-AzDataFactoryV2TriggerSubscriptionStatus
* Memperbarui versi SDK .Net ADF ke 4.1.3

#### <a name="azhdinsight"></a>Az.HDInsight
* Memanggil perubahan mencolok

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk memanggil failover untuk IotHub ke wilayah pemulihan bencana yang dipasangkan secara geografis.
* Menambahkan dukungan untuk mengelola pengayaan pesan untuk IotHub. Cmdlet baru adalah:
    - Add-AzIotHubMessageEnrichment
    - Get-AzIotHubMessageEnrichment
    - Remove-AzIotHubMessageEnrichment
    - Set-AzIotHubMessageEnrichment

#### <a name="azmonitor"></a>Az.Monitor
* Menunjuk ke SDK Monitor terbaru, yaitu 0.24.1-pratinjau
   - Menambahkan perubahan tanpa terputus pada cmdlet Metrik, yaitu enumerasi Unit mendukung beberapa nilai baru. Ini adalah cmdlet baca saja, jadi tidak akan ada perubahan dalam input cmdlet.
   - Versi api permintaan **ActionGroups** sekarang **2019-06-01**, sebelumnya **2018-03-01**. Pengujian skenario telah diperbarui untuk mengakomodasi perubahan ini.
   - Konstruktor untuk kelas **EmailReceiver** dan **WebhookReceiver** menambahkan satu argumen wajib baru, yaitu nilai Boolean yang disebut **useCommonAlertSchema**. Saat ini, nilainya ditetapkan ke **false** untuk menyembunyikan perubahan mencolok ini dari cmdlet. **CATATAN**: ini adalah perubahan sementara yang harus divalidasi oleh tim Peringatan.
   - Urutan argumen untuk konstruktor **Source** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua pengujian unit untuk diperbaiki: mereka dikompilasi, tetapi gagal lulus pengujian.
   - Urutan argumen untuk konstruktor **AlertingAction** kelas (terkait dengan kelas **ScheduledQueryRuleSource**) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua pengujian unit untuk diperbaiki: mereka dikompilasi, tetapi gagal lulus pengujian.
* Mendukung kriteria Ambang Dinamis untuk peringatan metrik V2
    - New-AzMetricAlertRuleV2Criteria: sekarang juga menciptakan kriteria ambang batas dinamis
    - Add-AzMetricAlertRuleV2: sekarang juga menerima kriteria ambang dinamis
* Peningkatan cmdlet Aturan Kueri Terjadwal (SQR)
 - Cmdlet akan menerima parameter 'Location' dalam kedua format, baik lokasi (misalnya eastus) atau nama tampilan lokasi (misalnya US Timur)
 - Mengilustrasikan parameter 'Enabled' dalam file bantuan dengan benar
 - Menambahkan contoh untuk parameter opsional 'ActionGroup'
 - Meningkatkan file bantuan secara keseluruhan
* Memperbaiki bug dalam menentukan jenis cakupan untuk 'Set-AzActionRule'

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki contoh yang salah dalam dokumentasi referensi 'New-AzApplicationGateway'
* Menambahkan catatan dalam dokumentasi referensi 'Get-AzNetworkWatcherPacketCapture' tentang mengambil semua properti untuk pengambilan paket
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
* Memperbaiki dokumen untuk beberapa contoh PowerShell untuk menggunakan cmdlet Az alih-alih cmdlet AzureRM

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbarui Objek AzureVMpolicy dengan Atribut ProtectedItemsCount
* Menambahkan Pengujian untuk kebijakan VM dan Pemulihan Akun Penyimpanan Asli

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug di mana New-AzRoleAssignment tidak dapat dipanggil tanpa Cakupan parameter.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki kesalahan pengetikan dalam contoh untuk dokumentasi referensi 'Update-AzServiceFabricReliability'
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
* Meningkatkan SDK Service Fabric ke versi 1.2.0 yang menggunakan penyedia sumber daya fabric layanan api-version 2019-03-01.

#### <a name="azsignalr"></a>Az.SignalR
* Menambahkan Cmdlet Pembaruan, Mulai Ulang, CheckNameAvailability, GetUsage

#### <a name="azsql"></a>Az.Sql
* Memperbarui contoh dalam dokumentasi referensi untuk 'Get-AzSqlElasticPool'
* Menambahkan contoh vCore untuk membuat kumpulan elastis (New-AzSqlElasticPool).
* Menghapus validasi EmailAddresses dan periksa bahwa EmailAdmins tidak salah apabila EmailAddresses kosong di Set-AzSqlServerAdvancedThreatProtectionPolicy dan Set-AzSqlDatabaseAdvancedThreatProtectionPolicy
* Mengaktifkan penghapusan pengaturan audit server/database saat beberapa pengaturan diagnostik yang mengaktifkan kategori audit ada.
* Memperbaiki validasi alamat email di beberapa cmdlet Penilaian Kerentanan Sql (Update-AzSqlDatabaseVulnerabilityAssessmentSetting, Update-AzSqlServerVulnerabilityAssessmentSetting, Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting dan Update-AzSqlInstanceVulnerabilityAssessmentSetting).

#### <a name="azstorage"></a>Az.Storage
* Memperbarui contoh dalam dokumentasi referensi untuk 'Get-AzStorageAccountKey'
* Di pengunggahan/Pengunduhan File Azure, didukung untuk mempertahankan properti File SMB sumber (Atribut File, Waktu Pembuatan File, Waktu Penulisan File Terakhir) di file tujuan
    -  Set-AzStorageFileContent
    -  Get-AzStorageFileContent
* Memperbaiki Pengunggahan blob blok dengan properti/metadate gagal pada ImmutabilityPolicy yang diaktifkan kontainer.
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
* Memperbaiki kesalahan pengetikan lain-lain di berbagai modul

#### <a name="azaccounts"></a>Az.Accounts
* Mendukung MSI yang ditetapkan pengguna di Autentikasi Azure Functions (#9479)

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah dengan output untuk 'Get-AzAks'
    * Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/9847

#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/9351
    - Memperbarui versi nuget .net, yang tidak memberlakukan pembatasan pada productId, apiId, groupId, dan userId
* **Get-AzApiManagementProduct** - Menambahkan dukungan untuk mengkueri produk menggunakan Api.
  https://github.com/Azure/azure-powershell/issues/9482
* **New-AzApiManagementApiRevision** - Memperbaiki masalah ketika ApiRevisionDescription tidak diatur saat membuat revisi api baru https://github.com/Azure/azure-powershell/issues/9752
* Memperbaiki kesalahan pengetikan dalam model 'PsApiManagementOAuth2AuthrozationServer' menjadi 'PsApiManagementOAuth2AuthorizationServer'

#### <a name="azbatch"></a>Az.Batch
* Memperbaiki kesalahan pengetikan dalam pesan bantuan dan dokumentasi untuk mengkapitalisasi Windows

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki kesalahan pengetikan di CDN pembantu konversi modul

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
* Memperbaiki kesalahan pengetikan untuk mengkapitalisasi 'Windows' di dokumentasi 'New-AzDataFactoryEncryptValue'
* Memperbarui versi SDK .Net ADF ke 4.1.2
* Menambahkan parameter 'DataProxyIntegrationRuntimeName', 'DataProxyStagingLinkedServiceName' dan 'DataProxyStagingPath' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan pengaturan Runtime Integrasi yang Dihost Sendiri sebagai proksi untuk Runtime Integrasi SSIS
* Memperbarui PSTriggerRun untuk menampilkan alur, pesan, dan properti yang dipicu, dan PSActivityRun untuk menampilkan jenis aktivitas

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki Get-DataLakeStoreDeletedItem untuk kesalahan atau pengecualian jarak jauh.

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan untuk masalah #9658 : Kesalahan pengetikan parameter VirtualNteworkRule di Set-AzEventHubNetworkRuleSet
* Perbaikan untuk masalah #9558 : Set-AzEventHubNamespace menggunakan PATCH alih-alih PUT
* menambahkan parameter EnableKafka ke cmdlet Set-AzEventHubNamespace
* Perbaikan untuk masalah #9786 : tidak dapat membuat aturan dengan hak Dengarkan saja

#### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* Memperbaiki kesalahan pengetikan dokumentasi di mana 'Azure' ditulis dalam huruf kecil

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam dokumentasi bantuan

#### <a name="aznetwork"></a>Az.Network
* Memperbarui New-AzPrivateLinkServiceIpConfig
    - Menghentikan penggunaan parameter 'PublicIpAddress' karena ini tidak pernah digunakan di sisi server.
    - Menambahkan satu parameter opsional 'Primary' yang menunjukkan konfigurasi ip saat ini adalah yang utama atau tidak.
* Meningkatkan penanganan pengecualian kesalahan permintaan dari SDK -Memperbaiki masalah pengecualian SDK sebelumnya yang tidak ditangani dengan benar sehingga mengakibatkan detail kesalahan utama tidak ditampilkan
* Menyesuaikan logika validasi untuk Prefiks IP Ipv6 untuk memeriksa panjang prefiks IPv6 yang benar.
* Memperbarui Get-AzVirtualNetworkSubnetConfig: Menambahkan set parameter untuk mendapatkan id sumber daya subnet.
* Memperbarui deskripsi parameter Lokasi untuk AzNetworkServiceTag

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
* Perbaikan untuk masalah #9658 : Kesalahan pengetikan parameter VirtualNetworkRule di Set-AzServiceBusNetworkRuleSet
* Perbaikan untuk masalah #9786 : tidak dapat membuat aturan dengan hak Dengarkan saja
* Menambahkan perintah baru 'Test-AzServiceBusNameAvailability' untuk memeriksa ketersediaan nama untuk antrean dan topik

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki bug cmdlet penambahan jenis node:
    - Bug NullReferenceException ketika grup sumber daya memiliki vmss lain yang tidak terkait dengan kluster service fabric. Memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8681
    - Memperbaiki bug ketika cmdlet gagal jika virtualNetwork berada dalam grup sumber daya yang berbeda dengan kluster. memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8407
    - Menghentikan penggunaan cmdlet Add-AzServiceFabricApplicationCertificate

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
* Memperbaiki kesalahan pengetikan contoh dalam dokumentasi 'Remove-AzApplicationInsightsApiKey'

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan pengetikan dalam string sumber daya

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan dukungan NetworkRuleSet.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan properti yang hilang (ComputerName, OsName, OsVersion, dan HyperVGeneration) pada objek tampilan instans mesin virtual.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki kesalahan pengetikan dalam Remove-AzContainerRegistryReplication untuk parameter Replikasi
    - Informasi selengkapnya di sini https://github.com/Azure/azure-powershell/issues/9633

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi SDK .Net ADF ke 4.1.0
* Memperbaiki kesalahan pengetikan dalam dokumentasi untuk 'Get-AzDataFactoryV2PipelineRun'

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru yang ditambahkan untuk menghasilkan token SAS: New-AzEventHubAuthorizationRuleSASToken
* menambahkan pesan verifikasi dan kesalahan untuk hak-hak aturan otorisasi jika hanya 'Manage' yang ditetapkan

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk menentukan Kebijakan KeySize for Certificate

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki Get-AzIntegrationAccountMap untuk mencantumkan semua jenis peta
    - Menambahkan parameter MapType baru untuk pemfilteran

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan dukungan untuk api versi 2019-06-01 (GA)

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk titik akhir privat dan layanan tautan privat
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
    - Cmdlet yang diperbarui
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
* Memperbarui panggilan layanan untuk Kontainer Tidak Terdaftar untuk Berbagi File Azure
* Memperbarui 'Set-AzRecoveryServicesAsrAlertSetting.md'

#### <a name="azresources"></a>Az.Resources
- Menghapus cmdlet yang hilang yang dirujuk dalam dokumentasi 'New-AzResourceGroupDeployment'
- Memperbarui cmdlet kebijakan untuk menggunakan api baru versi 2019-01-01

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru yang ditambahkan untuk menghasilkan token SAS: New-AzServiceBusAuthorizationRuleSASToken
* menambahkan pesan verifikasi dan kesalahan untuk hak-hak aturan otorisasi jika hanya 'Manage' yang ditetapkan

#### <a name="azsql"></a>Az.Sql
* Memperbaiki contoh yang hilang untuk cmdlet Set-AzSqlDatabaseSecondary
* Memperbaiki pemindaian berulang pada Penilaian Kerentanan yang ditetapkan tanpa memberikan alamat email apa pun
* Memperbaiki kesalahan pengetikan kecil dalam pesan peringatan.

#### <a name="azstorage"></a>Az.Storage
* Memperbarui contoh dalam dokumentasi referensi pada 'Get-AzStorageAccount' untuk menggunakan nama parameter yang benar

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan cmdlet Invoke-AzStorageSyncChangeDetection.
* Memperbaiki Masalah 9551 untuk mematuhi TierFilesOlderThanDays

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug ketika beberapa properti SiteConfig tidak dimunculkan oleh Get-AzWebApp dan Set-AzWebApp
* Menambahkan parameter Location baru ke Get-AzDeletedWebApp dan Restore-AzDeletedWebApp
* Memperbaiki bug dengan mengkloning slot aplikasi web menggunakan New-AzWebApp -IncludeSourceWebAppSlots

## <a name="240---july-2019"></a>2.4.0 - Juli 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan dukungan untuk cmdlet profil
* Menambahkan dukungan untuk lingkungan dan data plane di cmdlet yang dihasilkan
* Memperbaiki bug ketika titik akhir yang salah digunakan dalam beberapa kasus pada cmdlet data plane di Windows PowerShell

#### <a name="azadvisor"></a>Az.Advisor
* Rilis GA pada Az.Advisor
* Modul ini sekarang disertakan sebagai bagian dari modul roll-up `Az`

#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/8671
    - **Get-AzApiManagementSubscription**
        - Menambahkan dukungan untuk mengkueri langganan oleh Pengguna dan Produk
        - Menambahkan dukungan untuk kueri menggunakan Cakupan '/', '/apis', '/apis/echo-api'
* Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/9307 dan https://github.com/Azure/azure-powershell/issues/8432
    - **Import-AzApiManagementApi**
        - Menambahkan dukungan untuk menentukan 'ApiVersion' dan 'ApiVersionSetId' saat mengimpor Apis

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug cmdlet Set-AzAutomationConnectionFieldValue untuk menangani nilai string.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HyperVGeneration ke New-AzImageConfig

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui output aktivitas get yang berjalan, get alur yang berjalan, dan get pemicu yang menjalankan cmdlet ADF untuk mendukung alur Select-Object.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbaiki kesalahan pengetikan dalam dokumentasi 'New-AzEventGridSubscription'

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
   - Beberapa dokumen dan contoh pembaruan untuk cmdlet Policy

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaikan untuk masalah #4938 - New-AzureRmServiceBusQueue memunculkan BadRequest saat mengatur MaxSizeInMegabytes

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
* Modul ini sekarang disertakan sebagai bagian dari modul roll-up `Az`

## <a name="232---june-2019"></a>2.3.2 - Juni 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki bug ketika URL yang salah digunakan dalam beberapa kasus untuk panggilan Functions
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8983
* Memperbaiki Masalah alias dari AzureRM ke cmdlet Az
  - Set-AzureRmVMBootDiagnostics -> Set-AzVMBootDiagnostic
  - Export-AzureRMLogAnalyticThrottledRequests -> Export-AzLogAnalyticThrottledRequest

#### <a name="azcompute"></a>Az.Compute
* Set parameter sederhana New-AzVm dan New-AzVmss sekarang menerima parameter 'ProximityPlacementGroup'.
* Memperbaiki kesalahan pengetikan dalam dokumentasi referensi 'New-AzVM'

#### <a name="azdns"></a>Az.Dns
* Memperbaiki kesalahan pengetikan dalam contoh bantuan 'Set-AzDnsZone'.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui penggunaan versi API 2019-06-01.
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
        - Mendapatkan detail Topik Domain Event Grid, atau mendapatkan daftar semua Topik Domain Event Grid pada Domain Event Grid tertentu di Azure saat ini
    - Remove-AzureRmEventGridDomainTopic:
        - Menghapus Topik Domain Azure Event Grid yang ada.
* Memperbarui cmdlet:
    - New-AzureRmEventGridSubscription/Update-AzureRmEventGridSubscription:
        - Menambahkan parameter wajib baru untuk mendukung penyaluran untuk Domain Event Grid baru dan Topik Domain Event Grid untuk memungkinkan pembuatan langganan peristiwa baru pada sumber daya ini.
        - Menambahkan parameter wajib baru untuk menentukan nama Domain Event Grid baru dan/atau nama Topik Domain Event Grid untuk memungkinkan pembuatan langganan peristiwa baru pada sumber daya ini.
        - Menambahkan set Parameter baru untuk domain dan topik domain untuk memungkinkan penggunaan kembali parameter yang ada (misalnya, EndPointType, SubjectBeginsWith, dll).
        - Menambahkan parameter opsional baru untuk menentukan:
            - Masa kedaluwarsa langganan peristiwa,
            - Parameter pemfilteran tingkat lanjut.
        - Menambahkan enumerasi baru untuk servicebusqueue sebagai tujuan.
        - Melarang penggunaan 'All' dalam opsi -IncludedEventType dan menggantinya dengan
    - Get-AzEventGridTopic, Get-AzEventGridDomain, Get-AzEventGridDomainTopic, Get-AzEventGridSubscription:
        - Menambahkan parameter opsional baru (Top, ODataQuery dan NextLink) untuk mendukung hasil penomoran dan penyaringan.
    - Remove-AzureRmEventGridSubscription
        - Menambahkan parameter wajib baru untuk mendukung penyaluran untuk Domain Event Grid dan Topik Domain Event Grid untuk memungkinkan menghapus langganan peristiwa yang ada pada sumber daya ini.
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
* Memperbarui perintah fitur di bawah ini: Bendera UseLocalAzureIpAddress di VpnConnection
    - Memperbarui New-AzVpnConnection: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
    - Memperbarui Set-AzVpnConnection: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
* Menambahkan peeredConnections bidang baca saja di peering ExpressRoute.
* Menambahkan bidang baca saja GlobalReachEnabled di ExpressRoute.
* Menambahkan atribut perubahan mencolok untuk memanggil penghentian bidang AllowGlobalReach di model ExpressRouteCircuit
* Memperbaiki Masalah Kesalahan 8756 menggunakan TargetListenerID dengan cmdlet AzApplicationGatewayRedirectConfiguration
* Memperbaiki bug di New-AzApplicationGatewayPathRuleConfig yang mencegah set aturan penulisan ulang diterapkan.
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
        - Menghentikan parameter -PublicIpName dan -VirtualNetworkName
* Memperbarui perintah fitur di bawah ini: Atur opsi autentikasi AAD VpnClient ke sumber daya gateway virtual.
    - Memperbarui New-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi autentikasi AAD VpnClient di Gateway.
    - Memperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi autentikasi AAD VpnClient di Gateway.
    - Memperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter switch opsional RemoveAadAuthentication untuk menghapus opsi autentikasi AAD VpnClient dari Gateway.

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
* Mengklarifikasi deskripsi cmdlet kekebalan blob
    -  Remove-AzRmStorageContainerImmutabilityPolicy

#### <a name="azwebsites"></a>Az.Websites
* Mengoptimalkan Get-AzWebAppCertificate untuk memfilter berdasarkan grup sumber daya di server, bukan klien
* Menambahkan parameter switch -UseDisasterRecovery ke Get-AzWebAppSnapshot

## <a name="220---june-2019"></a>2.2.0 - Juni 2019
#### <a name="azcdn"></a>Az.Cdn
* Memperbarui cmdlet untuk mendukung fitur rulesEngine berdasarkan API versi 2019-04-15.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter `NoWait` yang memulai operasi dan segera memunculkannya, sebelum operasi selesai.
    - Cmdlet yang diperbarui:   Export-AzLogAnalyticRequestRateByInterval   Export-AzLogAnalyticThrottledRequest   Remove-AzVM   Remove-AzVMAccessExtension   Remove-AzVMAEMExtension   Remove-AzVMChefExtension   Remove-AzVMCustomScriptExtension   Remove-AzVMDiagnosticsExtension   Remove-AzVMDiskEncryptionExtension   Remove-AzVMDscExtension   Remove-AzVMSqlServerExtension   Restart-AzVM   Set-AzVM   Set-AzVMAccessExtension   Set-AzVMADDomainExtension   Set-AzVMAEMExtension   Set-AzVMBginfoExtension   Set-AzVMChefExtension   Set-AzVMCustomScriptExtension   Set-AzVMDiagnosticsExtension   Set-AzVMDscExtension   Set-AzVMExtension   Start-AzVM   Stop-AzVM   Update-AzVM

#### <a name="azeventhub"></a>Az.EventHub
* Perbaikan untuk #9231 - Get-AzEventHubNamespace tidak memunculkan tag
* Perbaikan untuk #9230 - Get-AzEventHubNamespace memunculkan ResourceGroup, bukan ResourceGroupName

#### <a name="aznetwork"></a>Az.Network
* Memperbarui ResourceId dan InputObject untuk Gateway Nat
    - Menambahkan alias untuk ResourceId dan InputObject

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi Null di Get-AzPolicyEvent

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Retensi minimum kebijakan IaaSVM dalam beberapa hari berubah menjadi 7, sebelumnya 1

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaikan untuk masalah #9182 - Get-AzServiceBusNamespace memunculkan ResourceGroup, bukan ResourceGroupName

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki kesalahan pengetikan dalam pesan kesalahan untuk 'Update-AzServiceFabricReliability'
* Memperbaiki karakter yang hilang di cmdline Service Fabric

#### <a name="azsql"></a>Az.Sql
* Menambahkan Parameter DnsZonePartner untuk cmdlet New-AzureSqlInstance guna mendukung AutoDr pada Instans Terkelola.
* Menghentikan penggunaan cmdlet Get-AzSqlDatabaseSecureConnectionPolicy
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
    - Kemampuan untuk mengonfigurasi 'SubscriptionRequired' dalam cakupan Api.
* Memperbarui cmdlet **Set-AzApiManagementApi**
    - Untuk mengonfigurasi API dengan server otorisasi 'OpenId'.
    - Untuk memperbarui API menjadi 'ApiVersionSet'
    - Kemampuan untuk mengonfigurasi 'SubscriptionRequired' dalam cakupan Api.
* Memperbarui cmdlet **New-AzApiManagementRevision**
    - Untuk mengkloning (salin tag, produk, operasi, dan kebijakan) revisi yang ada menggunakan 'SourceApiRevision'. Revisi baru mengasumsikan 'ApiId' dari induk.
    - Untuk menyediakan 'ApiRevisionDescription'
    - Untuk mengganti 'ServiceUrl' saat mengkloning API.
* Memperbarui cmdlet **New-AzApiManagementIdentityProvider**
    - Untuk mengonfigurasi 'AAD' atau 'AADB2C' dengan 'Authority'
    - Untuk menyiapkan 'SignupPolicy', 'SigninPolicy', 'ProfileEditingPolicy' dan 'PasswordResetPolicy'
* Memperbarui cmdlet **New-AzApiManagementSubscription**
    - Untuk mempertanggungjawabkan SubscriptonModel baru menggunakan 'Scope' dan 'UserId'
    - Untuk mempertanggungjawabkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Menambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Memperbarui cmdlet **Set-AzApiManagementSubscription**
    - Untuk mempertanggungjawabkan SubscriptonModel baru menggunakan 'Scope' dan 'UserId'
    - Untuk mempertanggungjawabkan model langganan lama menggunakan 'ProductId' dan 'UserId'
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
    - Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/7977
    - Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/8600
* Mengubah perilaku bagi Start-AzAutomationDscCompilationJob untuk memulai pekerjaan bukan menunggu hingga selesai.
    * Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/8347
* Memperbaiki Get-AzAutomationDscNode saat menggunakan -Name memunculkan semua node. Sekarang hanya menampilkan node yang cocok.

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
* Menambahkan cmdlet baru Get-AzureRmDenyAssignment untuk mengambil tugas tolak

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
* Parameter switch SkipShutdown ditambahkan ke Stop-AzVM dan Stop-AzVmss
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
    - Informasi [selengkapnya](/rest/api/monitor/scheduledqueryrules) mengenai API SQR
    - Memperbarui Az.Monitor.md untuk menyertakan cmdlet pada aturan peringatan berbasis metrik GenV2 (non klasik)

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk Sumber Daya Gateway Nat
    - Cmdlet baru
        - New-AzNatGateway
        - Get-AzNatGateway
        - Set-AzNatGateway
        - Remove-AzNatGateway
   - Cmdlet yang diperbarui
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
* Memperbaiki kesalahan pengetikan dalam pesan yang diterima pelanggan

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru untuk NetworkRuleSet dari Namespace Layanan

#### <a name="azstorage"></a>Az.Storage
* Meningkatkan ke Pustaka Klien Penyimpanan 10.0.1 (namespace layanan semua objek dari SDK ini berubah dari 'Microsoft.WindowsAzure.Storage. *' menjadi 'Microsoft.Azure. Storage.* ')
* Meningkatkan ke Microsoft.Azure.Management.Storage 11.0.0, untuk mendukung API baru versi 2019-04-01.
* Akun Penyimpanan Kind default di Buat perubahan akun Penyimpanan dari 'Storage' menjadi 'StorageV2'
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
* Untuk informasi selengkapnya mengenai modul `Az`, harap kunjungi tautan berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke Get cmdlet untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Assembly Akun Integrasi dan Konfigurasi Batch

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
* Menambahkan cmdlet baru untuk NetworkRuleSet dari Namespace Layanan

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
* Untuk informasi selengkapnya mengenai modul `Az`, harap kunjungi tautan berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke Get cmdlet untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Assembly Akun Integrasi dan Konfigurasi Batch

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
* Dukungan -AsJob untuk Blob dan pengunggahan file dan pengunduhan cmdlet
    - Get-AzStorageBlobContent
    - Set-AzStorageBlobContent
    - Get-AzStorageFileContent
    - Set-AzStorageFileContent

## <a name="160---march-2019"></a>1.6.0 - Maret 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan umum modul `Az`
* Untuk informasi selengkapnya mengenai modul `Az`, harap kunjungi tautan berikut: https://aka.ms/azps-announce
* Menambahkan pelengkap Location, ResourceGroup, dan ResourceName: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan kartubebas ke Get cmdlet untuk Az.Compute dan Az.Network
* Menambahkan autentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Assembly Akun Integrasi dan Konfigurasi Batch

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
* mengubah parameter cmdlet Deteksi Ancaman (ExcludeDetectionType) dari DetectionType ke string[] untuk menjadikannya sebagai bukti di masa mendatang ketika DetectionTypes baru ditambahkan dan juga untuk mendukung pelengkapan otomatis.

#### <a name="azstorage"></a>Az.Storage
* Mendukung Kebijakan Manajemen Get/Set/Remove pada Akun penyimpanan
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
* Menambahkan cmdlet Powershell baru untuk Mengaktifkan/Menonaktifkan Https Domain Kustom dan menghentikan yang lama

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
* Mendukung Jenis BlockBlobStorage saat membuat Akun penyimpanan      - New-AzStorageAccount

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
* Menambahkan cmdlet untuk enumerasi dan pemulihan item yang dihapus ADL

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan properti boolean baru SkipEmptyArchives untuk Melewati Arsip Kosong di kelas CaptureDescription Eventhub

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki pemberian tag di Set-AzKeyVaultSecret

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
* Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/8166
* Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/8235
* Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/6219
* Memperbaiki bug yang mencegah pembuatan KeyCredentials berulang

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk tingkat DB Hyperscale SQL
* Memperbaiki bug ketika pemulihan bisa gagal karena pengaturan properti yang tidak perlu dalam permintaan pemulihan

#### <a name="azwebsites"></a>Az.Websites
* Mengoreksi contoh pada Get-AzWebAppSlotMetrics

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
* Memperbaiki pemberian tag untuk grup sumber daya
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8166
* Memperbaiki masalah ketika `Get-AzureRmRoleAssignment` tidak mematuhi -ErrorAction
    - Informasi selengkapnya di sini: https://github.com/Azure/azure-powershell/issues/8235

#### <a name="azsql"></a>Az.Sql
* Add Get/Set AzSqlDatabaseBackupShortTermRetentionPolicy
* Memperbaiki masalah ketika tidak masuk ke akun Azure akan mengakibatkan pengecualian nullref saat menjalankan cmdlet SQL
* Memperbaiki pengecualian ref null di Get-AzSqlCapability

## <a name="121---january-2019"></a>1.2.1 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Merilis dengan versi Autentikasi yang benar

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Rilisan dengan dependensi Autentikasi yang diperbarui

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Rilisan dengan dependensi Autentikasi yang diperbarui

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
* Memperbaiki masalah di mana jalur untuk parameter '-TemplateFile' tidak diselesaikan sebelum menjalankan cmdlet penyebaran grup sumber daya
* Az.Resources: Memperbaiki dokumentasi untuk nilai default New-AzureRmPolicyDefinition -Mode
* Az.Resources: Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/7522
* Az.Resources: Perbaikan untuk masalah https://github.com/Azure/azure-powershell/issues/5747
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
* Memperbarui penggunaan versi API 2019-01-01.
* Memperbarui cmdlet berikut untuk mendukung skenario baru dalam versi API 2019-01-01
    - New-AzureRmEventGridSubscription: Menambahkan parameter opsional baru untuk menentukan:
        - Waktu Hingga Aktif Peristiwa,
        - Jumlah maksimum upaya pengiriman untuk peristiwa tersebut,
        - Titik akhir pengiriman yang gagal.
    - Update-AzureRmEventGridSubscription: Menambahkan parameter opsional baru untuk menentukan:
        - Waktu Hingga Aktif Peristiwa,
        - Jumlah maksimum upaya pengiriman untuk peristiwa tersebut,
        - Titik akhir pengiriman yang gagal.
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
* Memperbaiki kesalahan pengetikan dalam dokumentasi New-AzDeployment
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
- Perbaikan untuk #7002
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azbatch"></a>Az.Batch
- Menambahkan kemampuan untuk melihat versi Agen Node Azure Batch yang berjalan di masing-masing mesin virtual dalam kumpulan, melalui properti `NodeAgentInformation` baru di `PSComputeNode`.
- Default `Caching` untuk `PSDataDisk` sekarang `ReadWrite`, bukan `None`.
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azbilling"></a>Az.Billing
- Menggabungkan Penagihan, Konsumsi, dan cmdlet UsageAggregates, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azcognitivservices"></a>Az.CognitivServices
- Menambahkan pelengkap untuk SkuName dan Typem yang tersedia di New-AzureRmCognitiveServicesAccount operasi
- Menghapus set parameter GetSkusWithAccountParamSetName dari Get-AzCognitiveServicesAccountSkus

### <a name="azcontainerinstance"></a>Az.ContainerInstance
- Menambahkan dukungan ManagedIdentity

### <a name="azdatalakeanalytics"></a>Az.DataLakeAnalytics
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azdatalakestore"></a>Az.DataLakeStore
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

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
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azoperationalinsights"></a>Az.OperationalInsights
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azprofile"></a>Az.Profile
- Mengubah nama modul menjadi Az.Accounts

### <a name="azrecoveryservices"></a>Az.RecoveryServices
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azresources"></a>Az.Resources
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azservicefabric"></a>Az.ServiceFabric
- Mendukung penentuan sertifikat berdasarkan nama umum dan thumbprint
- Perubahan berisiko kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azsignalr"></a>Az.SIgnalR
- Ketersediaan Umum untuk cmdlet PowerShell pada SIgnalR

### <a name="azsql"></a>Az.Sql
- Menambahkan jenis deteksi Data_Exfiltration dan Unsafe_Action baru ke cmdlet Deteksi Ancaman
- Memperbarui contoh dokumentasi untuk cmdlet Audit Sql
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azstorage"></a>Az.Storage
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azwebsites"></a>Az.Websites
- Perubahan mencolok kecil, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

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

* Perbaikan untuk https://github.com/Azure/azure-powershell/issues/7679
    - Memperbarui Get-AzureRmRoleAssignment untuk menggunakan cakupan langganan jika disediakan saat meminta administrator klasik.

### <a name="azsql"></a>Az.Sql

* Perubahan kecil untuk transisi AzureRM ke Az mendatang
* Memperbaiki masalah dengan menggunakan Get-AzureRmSqlDatabaseVulnerabilityAssessment dengan inti DotNet
* Memodifikasi dokumentasi pesan bantuan yang terkait dengan cmdlet Audit SQL.

### <a name="azstorage"></a>Az.Storage

* Menambahkan -EnableHierarchicalNamespace ke New-AzureRmStorageAccount
* Memperbaiki masalah di mana cmdlet Copy File tidak dapat menggunakan kembali konteks sumber di tujuan saat tidak memasukkan -DestContext
    - Start-AzureStorageFileCopy
* Mendukung konfigurasi Situs Web Statis
    - Enable-AzureStorageStaticWebsite
    - Disable-AzureStorageStaticWebsite

### <a name="azwebsites"></a>Az.Websites

* Set-AzureRmWebApp and Set-AzureRmWebAppSlot
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
* Mengoreksi contoh di New-AzureRmRecoveryServicesAsrProtectableItem
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
* Menambahkan cmdlet baru untuk operasi CRUD pada Azure Sql Database Managed Instance dan Azure Sql Managed Database
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
* Mengganti nama parameter TenantId di cmdlet Connect-AzAccount ke Penyewa dan menambahkan alias untuk TenantId
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
* Memperbaiki masalah #7267 (Area penskalaan otomatis)
    - Masalah pembuatan aturan skala otomatis baru yang tidak mengatur parameter yang dienumerasi dengan benar (akan selalu diatur ke nilai default).
* Memperbaiki masalah #7513 [Insights] Set-AzDiagnosticSetting memerlukan spesifikasi kategori eksplisit selama pembuatan pengaturan
    - Sekarang cmdlet tidak memerlukan indikasi eksplisit pada kategori agar aktif selama pembuatan, yaitu berfungsi saat didokumentasikan

#### <a name="aznetwork"></a>Az.Network
* Mengubah PeeringType menjadi parameter wajib untuk cmdlet berikut:-
    - Get-AzExpressRouteCircuitRouteTable
    - Get-AzExpressRouteCircuitARPTable
    - Get-AzExpressRouteCircuitRouteTableSummary
    - Get-AzExpressRouteCrossConnectionArpTable
    - Get-AzExpressRouteCrossConnectionRouteTable
    - Get-AzExpressRouteCrossConnectionRouteTableSummary

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan cmdlet remediasi kebijakan

#### <a name="azresources"></a>Az.Resources
* Perbaikan untuk https://github.com/Azure/azure-powershell/issues/7402
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
* Menambahkan ukuran baru ke daftar yang memungkinkan ukuran mesin virtual untuk mengaktifkan jaringan yang dipercepat saat menggunakan set parameter sederhana untuk 'New-AzVm'
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
* Memperbaiki masalah ketika Get-AzRoleDefinition memberikan pengecualian yang tidak dapat dipahami (ketika profil default tidak memiliki langganan di dalamnya dan tidak ada cakupan yang ditentukan) dengan menambahkan pengecualian yang berarti dalam skenario. Juga mengatur parameter default ke 'RoleDefinitionNameParameterSet'.

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
* Memperbaiki `<rg>` Get-AzVM -ResourceGroupName untuk memunculkan lebih dari 50 hasil jika diperlukan
* Menambahkan contoh 'SimpleParameterSet' ke bantuan cmdlet New-AzVmss.
* Memperbaiki kesalahan pengetikan di pesan progres Azure Disk Encryption

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
