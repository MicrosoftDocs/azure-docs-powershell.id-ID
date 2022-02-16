---
description: Pelajari tentang semua pembaruan terbaru untuk modul Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: catatan rilis Azure PowerShell
ms.openlocfilehash: e9dfd6b4bba37cd8e725ff8e387472b99850d54f
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855405"
---
# <a name="azure-powershell-release-notes"></a>catatan rilis Azure PowerShell
## <a name="720---february-2022"></a>7.2.0 - Februari 2022
#### <a name="azaccounts"></a>Az.Accounts
* Menghapus perakitan lama System.Private.ServiceModel dan System.ServiceModel.Primitives [#16063]

#### <a name="azaks"></a>Az.Aks
* Memperbaiki kesalahan ketik di 'New-AzAksCluster' [#16733]

#### <a name="azcompute"></a>Az.Compute
* Hapus ProvisioningDetails properti dari objek PSRestorePoint.
* Cmdlet 'Set-AzVmExtension' yang diperbarui untuk menampilkan parameter '-Nama' dan '-Lokasi' dengan benar sebagai wajib.
* Contoh kedua 'New-AzVmssConfig' yang diedit sehingga berhasil berjalan dengan mengubah input Tag ke format yang benar. 
* Menambahkan parameter 'Hibernate' ke cmdlet 'Stop-AzVm'. 
* Menambahkan parameter 'HibernationEnabled' ke cmdlet 'New-AzVm', 'New-AzVmConfig', dan 'Update-AzVm'.
* Menambahkan parameter 'EnableHotpatching' ke cmdlet 'Set-AzVmssOSProfile'.
* Menambahkan parameter 'ForceDeletion' ke Remove-AzVM dan Remove-AzVMSS.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 5.1.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan akses jaringan publik ke cmdlet set 'Set-AzEventHubNetworkRuleSet'
* Ditambahkan 'New-AzEventHubSchemaGroup', 'Remove-AzEventHubSchemaGroup' dan 'Get-AzEventHubSchemaGroup' di eventhubs PS.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Cmdlet HealthcareApis akan menabrak versi API yang dapat memperkenalkan perubahan yang melanggar. Silakan hubungi kami untuk informasi lebih lanjut.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki pesan kesalahan Az.KeyVault.Extension [#16798]
* Menambahkan kebijakan akses default untuk kunci Key Vault sebagai 'Semua kecuali pembersihan'
* Menyerap KeyOps dari parameter saat mengimpor kunci dari sertifikat pada HSM terkelola [#16773]
* Memperbaiki bug saat memperbarui operasi utama pada HSM terkelola [#16774]
* Memperbaiki masalah saat mengimpor sertifikat tanpa kata sandi [#16742]

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Menambahkan logika untuk mencegah pengecualian saat menggunakan cmdlet 'StorageInsight'.

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan dukungan untuk properti remediasi baru yang memungkinkan remediasi lebih banyak sumber daya dengan kontrol yang lebih baik atas tingkat remediasi dan penanganan kesalahan
* Menambahkan dukungan untuk mengambil set hasil yang sangat besar dengan secara internal menggunakan panggilan API paginated untuk negara kebijakan dan perintah peristiwa kebijakan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Mengembalikan konfigurasi pencadangan per batas kebijakan untuk VM dari 1000 menjadi 100. Batas ini sebelumnya dilonggarkan tetapi karena portal Azure memiliki batas 100 VM per kebijakan, kami mengembalikan batas ini.
* Menambahkan dukungan untuk beberapa cadangan per hari untuk FileShares.
* Memisahkan beberapa alur CRR dan non-CRR berdasarkan pembaruan SDK.
* Tambahkan parameter EdgeZone ke cmdlet layanan pemulihan Azure Site 'New-AzRecoveryServicesAsrRecoveryPlan'

#### <a name="azresources"></a>Az.Resources
* Menambahkan proeprties 'onPremisesLastSyncDateTime', 'onPremisesSyncEnabled' ke objek 'User' [#16892]
* Menambahkan properti tambahan saat membuat permintaan untuk 'New-AzADServicePrincipal' dan 'Update-AzADServicePrincipal' [#16847] [#16841]
* Memperbaiki 'DisplayName' dan 'ApplicationId' untuk 'New-AzADAppCredential' [#16764]
* Reset kata sandi yang diaktifkan untuk 'Update-AzADUser' [#16869]
* Nama parameter yang diperbarui 'EnableAccount' ke 'AccountEnabled', dan menambahkan alias 'EnableAccount' untuk 'Update-AzADUser' [#16753] [#16795]
* Tetap 'Set-AzPolicyAssignment' tidak menghapus 'notScope' jika kosong [#15828]

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan dukungan untuk Mengaktifkan atau Menonaktifkan Akses Jaringan Publik sebagai parameter opsional 'PublicNetworkAccess' ke 'Set-AzServiceBusNetworkRuleSet'
* Memperbaiki 'Set-AzServiceBusNamespace' dengan Tag 

#### <a name="azsql"></a>Az.Sql
* Deprecation cmdlet Get-AzSqlDatabaseTransparentDataEncryptionActivity
* Cmdlet tetap untuk Azure Active Directory Admin 'AzureSqlServerActiveDirectoryAdministratorAdapter' dan 'AzureSqlInstanceActiveDirectoryAdministratorAdapter' bermigrasi dari 'AzureEnvironment.Endpoint.AzureEnvironment.Endpoint.Graph' ke 'AzureEnvironment.ExtendedEndpoint.MicrosoftGraphUrl'

#### <a name="azstackhci"></a>Az.StackHCI
* Menambahkan cmdlet dukungan untuk Dukungan Jarak Jauh 
    - Cmdlet baru - Install-AzStackHCIRemoteSupport, Remove-AzStackHCIRemoteSupport, Enable-AzStackHCIRemoteSupport, Disable-AzStackHCIRemoteSupport, Get-AzStackHCIRemoteSupportAccess,Get-AzStackHCIRemoteSupportSessionHistory

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah nomor output di konsol saat memperbarui/menyalin blob terkadang [#16783]
    -  'Set-AzStorageBlobContent' 
    -  'Copy-azStorageBlob' 
* File bantuan yang diperbarui, menambahkan lebih banyak deskripsi untuk salinan blob asinkron.
    -  'Start-AzStorageBlobCopy'

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Menambahkan dua parameter opsional baru 'MinChildEndpointsIPv4' dan 'MinChildEndpointsIPv6' untuk titik akhir bersarang

#### <a name="azwebsites"></a>Az.Websites
* Diperbarui 'New-AzAppServicePlan' untuk membuat paket layanan aplikasi dengan id lingkungan host #16094

## <a name="710---january-2022"></a>7.1.0 - Januari 2022
#### <a name="azaccounts"></a>Az.Accounts
* Disalin 'ServicePrincipalSecret' dan 'CertificatePassword' dari Az.Accounts buildin profile ke customer set profile. [#16617]
* Pesan bantuan yang diperbarui dan tanda suara untuk parameter 'Penyewa' cmdlet 'Set-AzContext'. [#16515]
* Memperbaiki masalah yang tidak dapat Azure PowerShell kerjakan dalam alur kerja. [#16408]
* Memperbaiki Versi Api dua kali lipat di URI dari permintaan yang mendasari yang dikeluarkan oleh 'Invoke-AzRestMethod'. [#16615]

#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan 'load balancer' dan 'api server access' di 'New-AzAksCluster' dan 'Set-AzAksCluster'. [#16575]

#### <a name="azautomation"></a>Az.Automation
* 'New-AzAutomationSchedule' memungkinkan defnining StartTime dengan offset.
*  Bug tetap: diperbarui 'Set-AzAutomationModule' untuk menggunakan panggilan PUT saat memperbarui modul dengan versi tertentu [#12552]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Memperbarui PowerShell untuk menggunakan versi 2021-10-01.
* Menambahkan cmdlet CommitmentTier dan CommitmentPlan.
* Menambahkan cmdlet Deployment.
* Menambahkan cmdlet 'New-AzCognitiveServicesObject' untuk menghasilkan objek CommitmentPlan/Deployment.

#### <a name="azcompute"></a>Az.Compute
* Parameter 'UserData' yang diperbarui di cmdlet VM dan VMSS untuk disalurkan dengan Nama Properti untuk memastikan skenario perpipaan terjadi dengan benar.
* Mengubah cmdlet 'New-AzVM' saat menggunakan SimpleParameterSet untuk tidak membuat 'PublicIPAddress' ketika nama 'PublicIPAddress' tidak disediakan.
* Menambahkan parameter 'PlatformFaultDomain' ke cmdlet: 'New-AzVM' dan 'New-AzVMConfig'
* Menambahkan parameter '-Fitur' untuk 'New-AzGalleryImageDefinition'
* Menambahkan parameter string 'DiffDiskPlacement' ke cmdlet 'Set-AzVmOSDisk' dan 'Set-AzVmssStorageProfile'.

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Exposed BackupPolicyMigrationState sebagai bagian dari respons Get-AzCosmosDBAccount.
  - Ini menyadangkan status status migrasi kebijakan cadangan ketika akun dikonversi dari mode pencadangan peroidik menjadi berkelanjutan.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 5.0.0

#### <a name="azfunctions"></a>Az.Functions
* Pratinjau yang dihapus dari tumpukan PowerShell 7.0 di Linux

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan cmdlet: 'Invoke-AzKeyVaultKeyRotation', 'Get-AzKeyVaultKeyRotationPolicy' dan 'Set-AzKeyVaultKeyRotationPolicy'

#### <a name="azmysql"></a>Az.MySql
* Ketersediaan umum Az.MySql

#### <a name="aznetwork"></a>Az.Network
* Perbandingan kasus-tidak sensitif yang digunakan untuk ResourceId (Set/New-NetworkWatcherFlowLog)
* Menambahkan properti baru 'ApplicationSecurityGroup', 'IpConfiguration' dan 'CustomNetworkInterfaceName' untuk cmdlet Private Endpoint
    - 'Get-AzPrivateEndpoint'
    - 'New-AzPrivateEndpoint'
* Menambahkan cmdlet baru untuk membuat objek 'IpConfiguration' baru untuk membangun Titik Akhir Pribadi
    - 'New-AzPrivateEndpointIpConfiguration'
* Menambahkan OrdinalIgnoreCase untuk perbandingan string tipe 'ResourceIdentifier' untuk cmdlet FlowLog
* Memperbaiki kesalahan ketik dalam pesan kesalahan 'InvalidWorkspaceResourceId'

#### <a name="azpostgresql"></a>Az.PostgreSql
* Ketersediaan umum Az.PostgreSql

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'IdentityType' dan 'UserAssignedIdentity' di cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'.
    - Ini digunakan untuk menetapkan dan memodifikasi Identitas Azure Cache untuk Redis.

#### <a name="azresourcemover"></a>Az.Resourcemover
* Menambahkan dukungan untuk Tag di penggerak sumber daya azure
* Menambahkan dukungan untuk SystemData in azure resource mover
* Dirilis versi api 2021-08-01

#### <a name="azresources"></a>Az.Resources
* Memperbaiki alias yang salah untuk 'Get-AzADSpCredential' [#16592]
* Memperbaiki parameter 'ServicePrincipalName' dan 'InputObject' untuk 'Update-AzADServicePrincipal' [#16620]
* Contoh tetap untuk 'New-AzADAppCredential' [#16682]
* Menambahkan parameter 'Web' untuk 'New-AzADApplication' [#16659]
* Menambahkan teks rahasia sebagai tanggapan atas 'New-AzADApplication' dan 'New-AzADServicePrincipal' [#16659]
* Deserialized 'Value' di 'DeploymentVariable' sebagai array objek jika tipenya adalah Array [#16523]
* Memperbaiki penggunaan 'SignInName' di 'New-AzRoleAssignment' [#16627]
* Memformat format output 'DeploymentVariable'
* Hapus filter operasi 'isUser' dari GetAzureProviderOperation Cmdlet

#### <a name="azsignalr"></a>Az.Signalr
* Memperbaiki bug cmdlet 'Update-AzSignalR' yang mengatur ulang status sumber daya secara tidak sengaja.

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter 'ZoneRedundant' ke 'New-AzSqlDatabaseCopy', 'New-AzSqlDatabaseSecondary' dan 'Restore-AzSqlDatabase' untuk mengaktifkan salinan redundan zona, geo secondary dan dukungan PITR untuk database hyperscale

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki kegagalan blob salinan sinkronisasi dengan nama blob tujuan panjang [#16628]
    -  'Copy-azStorageBlob'

#### <a name="azsynapse"></a>Az.Synapse
* Ketersediaan umum Az.Synapse
* Fitur Azure AD yang dimigrasikan di Az.Synapse ke API MSGraph. Cmdlet di bawah ini disebut MSGraph API sesuai dengan parameter input:
    - Cmdlet 'New-AzSynapseRoleAssignment'
    - Cmdlet 'Get-AzSynapseRoleAssignment'
    - Cmdlet 'Remove-AzSynapseRoleAssignment'
    - Cmdlet 'Set-AzSynapseSqlActiveDirectoryAdministrator'
* Menambahkan nilai default untuk parameter perintah [-AutoPauseDelayInMinute] 'New-AzSynapseSparkpool' dan 'Update-AzSynapseSparkpool'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @adishiritwick, diperbarui Set-AzAutomationModule untuk menggunakan panggilan PUT saat memperbarui modul dengan versi tertentu (#16505)
* @anuraj, Perbarui New-AzWebAppCertificate (#16634)
* @BrajaMS, Memperbarui perintah contoh dengan param NodeType (#16670)
* @geologyrocks, Kesalahan ketik utama (adalah princial) (#16699)
* Hen Itzhaki (@HenItzhaki), Menambahkan lebih banyak contoh (#16424)
* Chris (@isjwuk), Peningkatan pemformatan (#15826)
* Jaromir Kaspar (@jaromirk), Contoh tambahan untuk kredensial kata sandi (#16600)
* Martin Falkus (@mfalkus), Perbaiki kesalahan ketik di Perbarui Az-Tags doc di mana "Repalces" ditentukan alih-alih "Ganti" (#16541)
* Radoslav Gatev (@RadoslavGatev), [Az.Accounts] Perbaiki Versi Api ganda di Uri dari permintaan yang dikeluarkan oleh Invoke-AzRestMethod (#16616)
* @Skuldo, Perbaikan kesalahan ketik (#16585)
* Sujit Singh (@sujitks), Set-AzApplicationGatewayFirewallPolicy.md Pembaruan (#16583)
* @trudolf-msft, contoh baru 4/solusi (#16437)

## <a name="700---december-2021"></a>7.0.0 - Desember 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menghapus 'ServicePrincipalSecret' dan 'CertificatePassword' di 'PSAzureRmAccount' [#15427]
* Menambahkan parameter opsional 'MicrosoftGraphAccessToken' ke 'Koneksi-AzAccount'
* Menambahkan parameter opsional 'MicrosoftGraphEndpointResourceId', 'MicrosoftGraphUrl' ke 'Add-AzEnvironment' dan 'Set-AzEnvironment'
* Menambahkan properti '-AccountId' ke kumpulan parameter 'UserWithSubscriptionId' dari 'Koneksi-AzAccount' yang memungkinkan nama pengguna dipilih sebelumnya untuk login interaktif
* Menambahkan '-Uri' dan '-ResourceId' ke 'Invoke-AzRestMethod'
* Menambahkan auto completer Environment ke cmdlet berikut: Koneksi-AzAccount, Get-AzEnvironment, Set-AzEnvironment, dan Remove-AzEnvironment [#15991]
* Menambahkan nama modul dan versi ke string User-Agent [#16291]

#### <a name="azadvisor"></a>Az.Advisor
* Memperbaiki masalah bahwa 'Az.Advisor.psd1' tidak ditandatangani [#16226]

#### <a name="azaks"></a>Az.Aks
* [Melanggar Perubahan] Alias parameter yang diperbarui dan jenis output 'Get-AzAksVersion'
* Menambahkan 'Invoke-AzAksRunCommand' untuk mendukung menjalankan perintah shell (dengan kubectl, helm) pada cluster aks. [#16104]
* Menambahkan dukungan 'EnableNodePublicIp' dan 'NodePublicIPPrefixID' untuk 'New-AzAksCluster' dan 'New-AzAksNodePool'. [#15656]
* Memigrasikan logika pembuatan prinsipal layanan di 'New-AzAksCluster' dari 'Azure Active Directory Graph' ke 'Microsoft Graph'.
* Memperbaiki masalah bahwa 'Set-AzAksCluster' tidak dapat meningkatkan klaster saat versi kumpulan node tidak cocok dengan versi klaster. [#14583]
* Menambahkan 'ResourceGroupName' di 'PSKubernetesCluster'. [#15802]

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
* Berisi pembaruan pada cmdlet powershell berikut
    - 'SetAzVmssDiskEncryptionExtension': Menambahkan parameter ekstensi untuk cmdlet untuk bekerja dengan ekstensi uji dan parameter 'EncryptFormatAll' untuk Set Timbangan Mesin Virtual
    - 'GetAzVmssVMDiskEncryptionStatus': Memodifikasi fungsionalitas cmdlet untuk menampilkan status enkripsi disk data dari Set Timbangan Mesin Virtual dengan benar
    - 'SetAzDiskEncryptionExtension' : Memperbaiki bug di cmdlet dalam skenario migrasi dari enkripsi 2pass ke 1pass
* Menambahkan 'Add-AzVhd' untuk mengonversi VHD menggunakan Hyper-V
* Menambahkan parameter 'UserData' ke cmdlet VM dan VMSS
* Menambahkan parameter string 'PublicNetworkAccess' ke cmdlet DiskConfig dan SnapshotConfig
* Menambahkan parameter boolean 'AcceleratedNetwork' ke cmdlet DiskConfig dan SnapshotConfig
* Menambahkan properti 'CompletionPercent' ke model PSSnapshot sehingga terlihat oleh pengguna.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Versi API yang ditingkatkan ke 2021-09-01
  - [Melanggar Perubahan] Mengubah jenis parameter 'LogAnalyticWorkspaceResourceId' di 'New-AzContainerGroup' dari Hashtable ke String
  - [Melanggar Perubahan] Parameter dihapus 'NetworkProfileId' di 'New-AzContainerGroup', menambahkan 'SubnetId' sebagai alternatifnya
  - [Melanggar Perubahan] Parameter dihapus 'ReadinessProbeHttpGetHttpHeadersName' dan 'ReadinessProbeHttpGetHttpHeadersValue' di 'New-AzContainerInstanceObject', menambahkan 'ReadinessProbeHttpGetHttpHeader' sebagai alternatif mereka
  - [Melanggar Perubahan] Parameter dihapus 'LivenessProbeHttpGetHttpHeadersName' dan 'LivenessProbeHttpGetHttpHeadersValue' di 'New-AzContainerInstanceObject', menambahkan 'LivenessProbeHttpGetHttpHeader' sebagai alternatif mereka
  - Menambahkan 'Zone' di 'New-AzContainerGroup', 'AcrIdentity' di 'New-AzContainerGroupImageRegistryCredentialObject'
  - Mengubah 'Nama Pengguna' di 'New-AzContainerGroupImageRegistryCredentialObject' dari wajib menjadi opsional
* Untuk 'Invoke-AzContainerInstanceCommand'
    - [Melanggar Perubahan] Menampilkan hasil eksekusi perintah sebagai output cmdlet dengan menghubungkan websocket di backend [#15754]
    - Menambahkan '-PassThru' untuk mendapatkan hasil eksekusi terakhir ketika perintah berhasil
    - Mengubah 'TerminalSizeCol' dan 'TerminalSizeRow' dari wajib menjadi opsional, atur nilai defaultnya berdasarkan ukuran jendela PowerShell saat ini
* Menambahkan 'Restart-AzContainerGroup', 'Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint' dan 'New-AzContainerInstanceHttpHeaderObject'

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Tetap ketika peringatan tentang nilai AnalyticalStorageSchemaType ditampilkan ketika tidak ada nilai yang diberikan.
* Menambahkan dukungan untuk Cassandra yang dikelola.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.28.0

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah bahwa 'New-AzEventHubKey' selalu menghasilkan kunci utama baru, bukan kunci sekunder sejak versi 1.9.0 [#16362]

#### <a name="azfunctions"></a>Az.Functions
* [Melanggar perubahan] 'Update-AzFunctionAppPlan' meminta konfirmasi [#16490]
* [Melanggar perubahan] 'Remove-AzFunctionApp' tidak menghapus ASP jika itu adalah aplikasi terakhir dalam paket [#16487]
* [Melanggar perubahan] Atur 'FunctionsVersion' ke 4 untuk pembuatan FunctionApp [#16426]
* [Melanggar perubahan] 'Update-AzFunctionApp' meminta konfirmasi [#14442]
* Memperbaiki fungsi pembuatan kesalahan dengan 'New-AzFunctionApp' di PowerShell 5.1 [#15430]
* Akun penyimpanan yang didukung SKU 'Standard_GZRS' [#14633]

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan dua parameter '-Zone' dan '-PrivateLinkConfiguration' ke cmdlet 'New-AzHDInsightCluster'
  - Menambahkan parameter '-Zone' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung pembuatan cluster dengan fitur availability zone
  - Menambahkan parameter '-PrivateLinkConfiguration' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung penambahan konfigurasi tautan pribadi saat membuat klaster dengan fitur tautan pribadi.
* Menambahkan cmdlet New-AzHDInsightIPConfiguration untuk membuat objek konfigurasi IP dalam memori.
* Menambahkan cmdlet New-AzHDInsightPrivateLinkConfiguration untuk membuat objek konfigurasi tautan pribadi dalam memori.
* Memperbaiki jenis output dalam dokumen bantuan cmdlet Set-AzHDInsightClusterDiskEncryptionKey dari 'Microsoft.Azure.Management.HDInsight.Models.Cluster' ke 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster' agar tetap konsisten dengan jenis nyata objek yang dikembalikan.
* Melanggar perubahan:
  - Mengubah jenis parameter 'OSType' dari 'Microsoft.Azure.Management.HDInsight.Models.OSType' menjadi 'System.string' dalam cmdlet 'New-AzHDInsightCluster'.
  - Mengubah jenis parameter 'ClusterTier' dari 'Microsoft.Azure.Management.HDInsight.Models.ClusterTier' menjadi 'System.string' dalam cmdlet 'New-AzHDInsightCluster' dan 'New-AzHDInsightClusterConfig'.
  - Mengubah jenis properti 'VmSizes' di kelas 'AzureHDInsightCapabilities' dari `IDictionary<string, AzureHDInsightVmSizesCapability>` ke `IList<string>`.
  - Mengubah jenis properti 'AssignedIdentity' di kelas 'AzureHDInsightCluster' dari 'Microsoft.Azure.Management.HDInsight.Models.ClusterIdentity' menjadi 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightClusterIdentity'.

#### <a name="azkeyvault"></a>Az.KeyVault
* [Melanggar Perubahan] Properti yang berganti nama dari tipe 'PSKeyVaultPermission' untuk mengikuti pola Azure RBAC.
* Api AAD Graph yang dimigrasikan ke API MSGraph.
* Menambahkan pesan ke 'Set-AzKeyVaultAccessPolicy' yang menyatakan bahwa untuk parameter Izin, menggunakan opsi 'Semua' tidak akan menyertakan izin 'Purge'.

#### <a name="azmanagedservices"></a>Az.ManagedServices
* [Melanggar Perubahan] Versi API yang diperbarui ke pratinjau 2020-02-01

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan properti baru EventName, Category, ResourceProviderName, OperationName, Status, SubStatus dengan string tipe sebagai output untuk command Get-AzLog [#15833]
* Penerima hub peristiwa yang didukung dalam grup aksi [#16348]
* Menambahkan kumpulan parameter default 'GetByResourceGroup' untuk perintah 'Get-AzAlertRule' [#16356]

#### <a name="aznetwork"></a>Az.Network
* Bugfix in PSAzureFirewallPolicyThreatIntelWhitelist for FirewallPolicy
* Menambahkan parameter opsional '-IsSecuritySite' ke cmdlet berikut:
    - 'New-AzVpnSite'
* Menambahkan dukungan untuk Variabel Pencocokan baru dalam Pengecualian WAF
* Enkripsi Jaringan Virtual Onboard ke Cmdlet Jaringan Virtual
* Menambahkan dukungan untuk parameter rentang port NAT di sumber daya aturan NAT VPN
    - 'New-AzVpnGatewayNatRule.md'
    - 'Update-AzVpnGatewayNatRule.md'
    - 'New-AzVirtualNetworkGatewayNatRule.md'
    - 'Update-AzVirtualNetworkGatewayNatRule.md'
* Menambahkan cmdlet baru untuk mendukung Pengecualian Per Aturan untuk Application Gateway WAF
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleSet'
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRuleGroup'
    - 'New-AzApplicationGatewayFirewallPolicyExclusionManagedRule'
    - Cmdlet yang diperbarui juga untuk menambahkan properti untuk mengonfigurasi ExclusionManagedRuleSet dalam Pengecualian
        - 'New-AzApplicationGatewayFirewallPolicyExclusion'
* Perbaikan Bug di cmdlet Sertifikat Klien Tepercaya Application Gateway untuk memuat seluruh rantai sertifikat dari file.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperluas DataSourceType dengan nilai 'Query', 'Alerts' untuk cmdlet LinkedStorageAccount
* [Breaking Change] ganti nama 'StorageAccountId' menjadi 'StorageAccountIds'
  - 'New-AzOperationalInsightsLinkedStorageAccount'
* [Melanggar Perubahan] Mengembalikan 'PSSavedSearch' alih-alih 'HttpStatusCode' oleh 'New-AzOperationalInsightsComputerGroup'
* [Melanggar Perubahan] Mengembalikan 'PSCluster' alih-alih 'PSLinkedService' oleh 'Update-AzOperationalInsightsCluster'
* Sku diperluas dengan nilai 'capacityreservation', 'lacluster' for Workspace
* Menambahkan properti baru:'SkuCapacity', 'ForceCmkForQuery', 'DisableLocalAuth' untuk Workspace
* Menambahkan properti baru: 'DailyQuotaGb'on'Set-AzOperationalInsightsWorkspace'
* Menambahkan properti baru: 'ETag', 'Tag' untuk cmdlet StorageInsight
* Menambahkan properti baru 'StorageAccountResourceId' ke cmdlet:
  - 'Set-AzOperationalInsightsStorageInsight'
* Menambahkan Atribut SupportsShouldProcess ke cmdlet:
  - 'Set-AzOperationalInsightsStorageInsight'
* Menambahkan cmdlet baru untuk mendukung Table, DataExport, WorkspaceShareKey, PurgeWorkspace, dan AvailableServiceTier
* Menambahkan properti 'Kesalahan' dalam hasil 'Invoke-AzOperationalInsightsQuery' untuk mengambil sebagian kesalahan saat menjalankan kueri [#16378]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup memperbarui set validasi untuk BackupManagementType yang didukung di 'Get-AzRecoveryServicesBackupItem', 'Get-AzRecoveryServicesBackupContainer', Get-AzRecoveryServicesBackupJob cmdlet.
* Azure Backup menambahkan dukungan untuk SAPHanaDatabase untuk 'Disable-AzRecoveryServicesBackupProtection', cmdlet 'Unregister-AzRecoveryServicesBackupContainer', 'Get-AzRecoveryServicesBackupItem', cmdlet 'Get-AzRecoveryServicesBackupContainer'.
* Melanggar Perubahan: Perintah 'Get-AzRecoveryServicesBackupJob', 'Get-AzRecoveryServicesBackupContainer' dan 'Get-AzRecoveryServicesBackupItem' hanya akan mendukung perintah 'BackupManagementType MAB' alih-alih 'MARS'.
* Dukungan Azure Site Recovery untuk reservasi kapasitas untuk penyedia Azure ke Azure.

#### <a name="azresources"></a>Az.Resources
* Ditambahkan 'Get-AzProviderPreviewFeature', 'Register-AzProviderPreviewFeature' dan cmdlet 'Unregister-AzProviderPreviewFeature'.
* Memperbaiki bug saat menjalankan Get-AzPolicyAlias dengan nilai kosong parameter NamespaceMatch [#16370]
* [Melanggar perubahan] Bermigrasi dari AAD Graph ke Microsoft Graph
* [Melanggar perubahan] Mengubah 'Id' yang dikembalikan di PSDenyAssignment dari string GUID ke ID yang memenuhi syarat sepenuhnya
* Parameter yang diizinkan 'Id' di 'Get-AzDenyAssignment' untuk menerima ID yang memenuhi syarat sepenuhnya
* Menambahkan cmdlet baru 'Publish-AzBicepModule' untuk menerbitkan modul Bicep
* Menambahkan pesan deprekasi untuk parameter 'AssignIdentity' di cmdlet '*-AzPolicyAssignment'.
* Menambahkan dukungan untuk identitas terkelola yang ditetapkan pengguna dalam penetapan kebijakan dengan menambahkan parameter 'IdentityType' dan 'IdentityId' ke cmdlet '*-AzPolicyAssignment'.
* Cmdlet kebijakan yang diperbarui untuk menggunakan api baru versi 2021-06-01 yang memperkenalkan dukungan untuk identitas terkelola yang ditetapkan pengguna dalam penetapan kebijakan.
* Izin API yang dipersempit saat mendapatkan informasi tentang objek direktori aktif untuk *-AzRoleAssignment [#16054]

#### <a name="azsql"></a>Az.Sql
* Pemfilteran wildcard FirewallRuleName tetap di 'Get-AzSqlServerFirewallRule' [#16199]
* AAD Instans SQL Server dan SQL dipindahkan dari ActiveDirectoryClient ke MicrosoftGraphClient

#### <a name="azstackhci"></a>Az.StackHCI
* Mempromosikan Az.StackHCI ke GA

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki kegagalan 'Get-AzStorageContainerStoredAccessPolicy' ketika izin batal [#15644]
* Didukung buat layanan gumpalan Sas token atau akun Sas token dengan izin i
    -  'New-AzstorageblobSASToken'
    -  'New-AzstorageContainersASToken'
    -  'New-AzstorageAccountsASToken'
* Memperbaiki pembuatan kontainer token SAS gagal dari kebijakan akses tanpa waktu kedaluwarsa, dan menetapkan waktu kedaluwarsa token SAS [#16266]
    -  'New-AzstorageContainersASToken'
* Parameter dihapus -Nama dari Get-AzRmStorageShare ShareResourceIdParameterSet
    - 'Get-AzRmStorageShare'
* Kontainer buat atau migrasi yang didukung untuk memungkinkan Storage yang tidak berubah dengan pembuatan versi.
    -  'New-AzRmStorageContainer'
    -  'Invoke-AzRmstorageContainerImmutablestorageWithVersioningMigration'
* Kebijakan set/remove immutability yang didukung pada gumpalan Storage.
    -  'Set-AzStorageBlobImmutabilityPolicy'
    -  'Remove-AzStorageBlobImmutabilityPolicy'
* Didukung mengaktifkan / menonaktifkan penahanan hukum pada gumpalan Storage.
    -  'Set-AzStorageBlobLegalHold'
* Didukung membuat akun penyimpanan dengan mengaktifkan immutability tingkat akun dengan versi, dan membuat / memperbarui akun penyimpanan dengan kebijakan immutability tingkat akun.
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui SDK Microsoft.Azure.Management.Websites ke 3.1.2

## <a name="660---november-2021"></a>6.6.0 - November 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan versi baru klien layanan AAD menggunakan Microsoft Graph API

#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan untuk parameter baru 'NetworkPolicy', 'PodCidr', 'ServiceCidr', 'DnsServiceIP', 'DockerBridgeCidr', 'NodePoolLabel', 'AksCustomHeader' di 'New-AzAksCluster'. [#13795]
* Menambahkan peringatan tentang perubahan migrasi yang akan datang ke Microsoft Graph.
* Menambahkan dukungan untuk mengubah jumlah node dalam kumpulan node. [#12379]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbaiki bug di cmdlet 'Get-AzApiManagementTenantGitAccess'.

#### <a name="azbatch"></a>Az.Batch
* Perakitan dihapus 'System.Text.Encodings.Web.dll' [#16062]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan cmdlet untuk menambahkan properti VMGalleryApplication ke VM/VMSS
    - New-AzVmGalleryApplication
    - New-AzVmssGalleryApplication
    - Add-AzVmGalleryApplication
    - Add-AzVmssGalleryApplication
    - Remove-AzVmGalleryApplication
    - Remove-AzVmssGalleryApplication
* Menambahkan dukungan untuk pengaturan proxy dan debug untuk Ekstensi VM untuk SAP (AEM)
* Diperbarui New-AzGalleryImageVersion untuk mengambil properti 'Enkripsi' dengan benar dari parameter '-TargetRegion'.
* Diperbarui Set-AzVmBootDiagnostic ke default ke akun penyimpanan terkelola jika tidak disediakan.
* Diedit New-AzVmss perilaku default saat 'OrchestrationMode' diatur ke Fleksibel.
    - Menghapus Nat Pool.
    - Dihapus UpgradePolicy. Melemparkan kesalahan jika disediakan.
    - SinglePlacementGroup harus salah. Lemparkan kesalahan jika benar.
    - Versi API Profil Jaringan adalah 2020-11-01 atau yang lebih baru.
    - Konfigurasi IP Profil Jaringan Properti utama diatur ke true.

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan Get-AzCosmosDBMongoDBBackupInformation untuk mengambil informasi cadangan terbaru untuk MongoDB.
* Diperbarui New-AzCosmosDBAccount, Update-AzCosmosDBAccount untuk menerima BackupStorageRedundancy
* Memperkenalkan Get-AzCosmosDBLocation untuk mencantumkan Akun Azure CosmosDB dan properti lokasinya.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan PublicNetworkAccess ke Update_AzDataFactoryV2 Command
* Memperbarui versi ADF .Net SDK ke 4.26.0

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Versi API yang ditingkatkan ke 2021-07-12.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan dukungan untuk Premium sku dan namesapce dan parameter switch opsional 'DisableLocalAuth' ke 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Atur konfigurasi situs netFrameworkVersion hanya untuk Windows aplikasi V4
* Pembuatan aplikasi fungsi diaktifkan untuk tumpukan Fungsi V4 [#15919]

#### <a name="aziothub"></a>Az.IotHub
* IoT Hub Management SDK yang diperbarui ke versi 4.1.0 (api-version 2021-07-10)

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan pesan peringatan tentang perubahan yang akan datang ke 'New-AzKeyVaultRoleDefinition' dan 'Get-AzKeyVaultRoleDefinition'.
    - Untuk mematuhi sintaks 'New-AzRoleDefinition' dan 'Get-AzRoleDefinition' kita akan mengganti nama beberapa sifat model 'PSKeyVaultPermission', yang mungkin mempengaruhi kedua cmdlet ini.
* Menambahkan peringatan tentang perubahan migrasi yang akan datang ke Microsoft Graph.

#### <a name="azmigrate"></a>Az.Migrate
* Pemeriksaan tambahan untuk alamat IP yang tidak valid

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Memperbaiki bug di 'Set-AzOperationalInsightsLinkedService: ketika layanan tertaut tidak ada, lakukan create(update) alih-alih gagal"

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup memperbaiki masalah dengan StorageConfig
* Azure Backup menambahkan NodesList dan AutoProtectionPolicy ke cmdlet Get-AzRecoveryServicesBackupProtectableItem.
* Azure Backup tetap GetItemsForContainerParamSet untuk mendukung pengambilan item cadangan MAB.
* Azure Backup tetap Get-AzRecoveryServicesBackupContainer untuk mendukung BackupManagementType MAB alih-alih MARS.
* Menambahkan peringatan perubahan yang melanggar: perintah 'Get-AzRecoveryServicesBackupJob', 'Get-AzRecoveryServicesBackupContainer' dan 'Get-AzRecoveryServicesBackupProtectableItem' hanya akan mendukung perintah 'BackupManagementType MAB' alih-alih alias 'MARS', perubahan akan berlaku dari rilis yang akan datang.
* Menambahkan dukungan untuk tipe disk ZRS untuk replikasi Azure ke Azure.
* Menambahkan informasi availability zone dalam respons item terlindungi yang direplikasi untuk replikasi Azure ke Azure.

#### <a name="azrediscache"></a>Az.RedisCache
* Membuat contoh baru dalam dokumentasi 'New-AzRedisCache' dan 'Set-AzRedisCache'.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug tentang kode keluar Bicep [#16055]
* Menambahkan peringatan perubahan yang melanggar untuk cmdlet AAD
* Menambahkan properti 'UIFormDefinition' ke Versi Spesifikasi Template, 'Export-AzTemplateSpec' sekarang akan menyertakan UIFormDefinition Template Spec Version (jika ada) sebagai bagian dari ekspor.
* Menangkap kesalahan tambahan untuk pembuatan penetapan peran gagal saat membuat Kepala Sekolah Layanan
* Peningkatan kinerja untuk Get-AzPolicyAlias saat -NamespaceMatch cocok dengan satu ruang nama RP

#### <a name="azsecurity"></a>Az.Security
* Referensi paket Security .NET SDK yang diperbarui ke versi 3.0.0

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan dukungan untuk ZoneRedundant dan parameter switch opsional 'DisableLocalAuth' ke 'New-AzServiceBusNamespace' dan 'Set-AzServiceBusNamespace'

#### <a name="azsignalr"></a>Az.Signalr
* Menambahkan cmdlet Web PubSub
  - 'New-AzWebPubsub'
  - 'Get-AzWebPubsub'
  - 'Update-AzWebPubsub'
  - 'Restart-AzWebPubsub'
  - 'Remove-AzWebPubsub'
  - 'New-AzWebPubsubHub'
  - 'Get-AzWebPubsubHub'
  - 'Remove-AzWebPubsubHub'
  - 'New-AzWebPubsubKey'
  - 'Get-AzWebPubsubKey'
  - 'Get-AzWebPubsubsku'
  - 'Get-AzWebPubsubUsage'
  - 'Test-AzWebPubsubNameAvailability'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* bgomezangulo (@beagam), Resume-AzNetAppFilesReplication.md Pembaruan (#16040)
* Jim McCormick (@eimajtrebor), Kesalahan ketik tetap (#16091)
* Lampson Nguyen (@lampson), Get-AzDataShare.md Pembaruan (#16015)
* @MaxMeng1985, Perbarui Get-AzSynapseSqlPoolRestorePoint.md (#16138)
* Reggie Gibson (@regedit32), New-AzBotService: Perbaiki konversi AppSecret ke plaintext pada Windows PowerShell (#16160)
* Mötz Jensen (@Splaxi), Detail BusinessIdentities tidak sesuai dengan implementasi saat ini (#16141)

## <a name="650---october-2021"></a>6.5.0 - Oktober 2021
#### <a name="azaccounts"></a>Az.Accounts
* Didukung mendapatkan token akses untuk Microsoft Graph.
* Menambahkan AuthorizeRequestDelegate untuk memungkinkan modul layanan menyesuaikan audiens token.
* Memanfaatkan [AssemblyLoadContext](/dotnet/api/system.runtime.loader.assemblyloadcontext) untuk mengatasi masalah konflik perakitan di PowerShell.
* Memperbarui Azure.Core dari 1.16.0 ke 1.19.0.

#### <a name="azattestation"></a>Az.Pengesahan
* Ketersediaan umum modul 'Az.Attestation'

#### <a name="azcdn"></a>Az.Cdn
* Menetapkan pengecualian referensi null dan kesalahan ketik di cmdlet 'New-AzFrontDoorCdnRule'

#### <a name="azcompute"></a>Az.Compute
* Referensi paket Compute .NET SDK yang diperbarui ke versi 49.1.0
* Memperbaiki bug di 'Get-AzVM' yang menyebabkan output status daya yang salah.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan argumen DataFlowEnableQuickReuse untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk memungkinkan penggunaan kembali klaster dengan cepat dalam aktivitas pipeline berikutnya.
* Memperbarui versi ADF .Net SDK ke 4.25.0
* Menambahkan argumen VNetInjectionMethod untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mendukung injeksi jaringan virtual ekspres Azure-SSIS Integration Runtime.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Pembuatan tindakan mesin aturan yang diizinkan tanpa RouteConfigurationOverride untuk 'New-AzFrontDoorRulesEngineActionObject'.
* Parameter Fixed DynamicCompression diabaikan masalah 'New-AzFrontDoorRulesEngineActionObject'.

#### <a name="azkeyvault"></a>Az.KeyVault
* Definisi peran kustom yang didukung pada HSM terkelola:
    - Buat melalui 'New-AzKeyVaultRoleDefinition',
    - Hapus melalui 'Remove-AzKeyVaultRoleDefinition',
    - Filter semua peran kustom melalui 'Get-AzKeyVaultRoleDefinition -Custom'.
* Terenkripsi/Dekripsi/Bungkus/Buka kunci yang didukung [#15679]
* Mengaktifkan pengelolaan sumber daya di langganan lain tanpa mengalihkan konteks dengan menambahkan `-Subscription <String>`.

#### <a name="azmaintenance"></a>Az.Pemeliharaan
* Menambahkan dukungan pemeliharaan patch Tamu.

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk Sku, parameter ScaleUnits sumber daya BastionHost.
    - 'New-AzBastion'
    - 'Set-AzBastion'
* Onboard Azure Resource Manager ke Private Link Common Cmdlets
* Cmdlet yang diperbarui untuk menambahkan properti untuk mengaktifkan/menonaktifkan BgpRouteTranslationForNat for VpnGateway.
    - 'New-AzVpnGateway'
    - 'Update-AzVpnGateway'
* Cmdlet yang diperbarui untuk menambahkan properti untuk menonaktifkan InternetSecurity untuk P2SVpnGateway.
    - 'New-AzP2sVpnGateway'
* Menambahkan cmdlet baru untuk sumber daya anak HubBgpConnection dari VirtualHub.
    - 'Get-AzVirtualHubBgpConnection'
    - 'New-AzVirtualHubBgpConnection'
    - 'Update-AzVirtualHubBgpConnection'
    - 'Remove-AzVirtualHubBgpConnection'
* Onboard Azure HDInsight ke Private Link Common Cmdlets

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaikan bug Pemulihan Situs Azure untuk VMware ke Azure Reprotect, Perbarui kebijakan, dan Nonaktifkan skenario.
* Azure Backup menambahkan dukungan untuk MSI yang telah ditetapkan Pengguna di RecoveryServices Vault.

#### <a name="azresources"></a>Az.Resources
* Menambahkan pesan kesalahan yang lebih jelas untuk kasus di mana TemplateUri tidak menerima file bisep.
* Memperbaiki kesalahan ketik dengan ManagementGroups melanggar deskripsi perubahan [#15819].
* Memperbaiki masalah casing tag sumber daya - casing tag sumber daya tidak dipertahankan.
* Diperbarui ke Microsoft.Azure.Management.Authorization 2.13.0-preview.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki 'Get-AzSqlDatabaseImportExportStatus' untuk melaporkan kesalahan yang dihadapi

#### <a name="azstorage"></a>Az.Storage
* Azure yang ditingkatkan. Storage. Gumpalan ke 12.10.0
* Azure yang ditingkatkan. Storage. Files.Shares ke 12.8.0
* Azure yang ditingkatkan. Storage. Files.DataLake ke 12.8.0
* Azure yang ditingkatkan. Storage. Antrean ke 12.8.0
* Akun penyimpanan pemutakhiran yang didukung untuk mengaktifkan HierarchicalNamespace
    -  'Invoke-AzStorageAccountHierarchicalNamespaceUpgrade'
    -  'Stop-AzStorageAccountHierarchicalNamespaceUpgrade'
* Didukung AccessTierInferred, Tag dalam skema kebijakan inventaris blob
    - 'New-azstorageblobInventoryPolicyrule'
* Akun penyimpanan buat/perbarui yang didukung dengan PublicNetworkAccess diaktifkan/dinonaktifkan
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Kontainer gumpalan penyimpanan buat/perbarui yang didukung dengan RootSquash
    - 'New-AzRmStorageContainer'
    - 'Update-AzRmstorageContainer'
* Didukung Izinkan PerlindunganAppendWriteEmua dalam mengatur Kebijakan Keabadian Kontainer, dan tambahkan LegalHold kontainer
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
    - 'Add-AzRmstorageContainerLegalHold'

#### <a name="azstoragesync"></a>Az.StorageSync
* Memperbaiki bug di mana tidak semua properti objek PSSyncSessionStatus dan PSSyncActivityStatus diisi dengan benar.
* Hal ini memengaruhi cmdlet 'Get-AzStorageSyncServerEndpoint' saat mencoba mengakses properti output berikut:
    - SyncStatus.UploadStatus
    - SyncStatus.DownloadStatus
    - SyncStatus.UploadActivity
    - SyncStatus.DownloadActivity

#### <a name="azwebsites"></a>Az.Websites
* Diperbarui 'Import-AzWebAppKeyVaultCertificate1' untuk mengatur nama default dengan kombinasi nama keyvault dan nama sertifikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @DSakura207, Gunakan instans PowerState terakhir di Status untuk status daya (#15941)
* Yannic Graber (@grabery), Recode Example2 (#15808)
* @joelmforsyth, Perbaiki contoh multi-regional (#15918)
* Adam Coffman (@SysAdminforCoffee), Set-AzNetworkInterfaceIpConfig.md Pembaruan (#15846)
* Michael Howard (@x509cert), Kalimat reworded untuk memperjelas bahwa versi kunci tertentu harus disediakan (#15886)

## <a name="640---september-2021"></a>6.4.0 - September 2021
#### <a name="azaccounts"></a>Az.Accounts
* Mengoreksi URL ke Azure Portal dalam hasil 'Get-AzEnvironment' dan 'Get-AzContext'. [#15429]
* Membuat perubahan infrastruktur untuk mendukung langganan default utama melalui `-SubscriptionId <String>` parameter.
    - [Az.Aks](/powershell/module/az.aks/get-azakscluster) adalah modul pertama yang mendukungnya.

#### <a name="azaks"></a>Az.Aks
* `-Subscription <String>` Tersedia di semua cmdlet Aks. Anda dapat mengelola sumber daya Aks di langganan lain tanpa mengubah konteks.

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan cmdlet 'Sync-AzApiManagementKeyVaultSecret' baru.
* Menambahkan cmdlet 'New-AzApiManagementKeyVaultObject' baru.
* Menambahkan parameter opsional [-useFromLocation] baru ke cmdlet 'Get-ApiManagementCache' 'New-ApiManagementCache'''Update-ApiManagementCache'.
* Memperbarui cmdlet **New-AzApiManagement** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk SKU 'Terisolasi' baru
    - Menambahkan dukungan untuk mengelola Availability Zone menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
    - Menambahkan dukungan untuk mengelola Versi Api minimum untuk memungkinkan Control Plane menggunakan properti 'MinimalControlPlaneApiVersion'.
* Diperbarui cmdlet **New-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk mengelola Availability Zone menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
* Memperbarui cmdlet **Add-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk mengelola Availability Zone menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
* Diperbarui cmdlet **Update-AzApiManagementRegion** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk mengelola Availability Zone menggunakan properti 'Zone'
    - Menambahkan dukungan untuk Menonaktifkan Gateway di Wilayah menggunakan properti 'DisableGateway'
* Cmdlet **diperbarui New-AzApiManagementCustomHostnameConfiguration** untuk mengelola Konfigurasi Hostname Kustom
    - Menambahkan dukungan untuk menentukan 'IdentityClientId' untuk menyediakan ClientId yang Ditetapkan Pengguna Identitas Terkelola untuk digunakan dengan KeyVault

#### <a name="azautomation"></a>Az.Automation
* Bug tetap: Menutup gagang file input dalam Import-AzAutomationRunbook

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah parameter wajib di cmdlet 'Get-AzCdnEndpointResourceUsage'

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter baru '-LinuxConfigurationPatchMode', '-WindowsConfigurationPatchMode', dan '-LinuxConfigurationProvisionVMAgent' ke 'Set-AzVmssOSProfile'
* Menambahkan parameter baru '-SshKeyName' dan '-GenerateSshKey' ke 'New-AzVM' untuk membuat VM dengan SSH
* Memperbaiki bug di 'Add-AzVHD' di Linux yang menyebabkan unggahan gagal untuk URI tujuan tertentu
* Menambahkan cmdlet baru untuk Restore Points dan Restore Point Collection:
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
* Menambahkan argumen subnetId untuk cmdlet 'Set-AzDataFactoryV2IntegrationRuntime' untuk mendukung pemeriksaan RBAC untuk injeksi VNet terhadap ID sumber daya subnet alih-alih ID sumber daya VNet.
* Menambahkan cmdlet 'Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint' untuk menyediakan daftar dependensi jaringan keluar untuk runtime integrasi SSIS di Azure Data Factory yang bergabung dengan jaringan virtual.
* Menambahkan PublicNetworkAccess ke Data Factory.
* Memperbarui versi ADF .Net SDK ke 4.23.0

#### <a name="azkeyvault"></a>Az.KeyVault
* Didukung menambahkan kunci EC di brankas kunci [#15699]

#### <a name="azmigrate"></a>Az.Migrate
* UUID duplikat yang didukung di disk sumber.
* Subnet yang didukung di VNet yang sama untuk AVSet.
* RunAsAccount yang didukung mengambil beberapa Vcenters di situs yang sama.

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui untuk menambahkan properti 'Subnet' untuk kumpulan alamat backend penyeimbang beban berbasis IP.
    - 'New-AzLoadBalancerBackendAddressConfig'
* Cmdlet yang diperbarui untuk menambahkan properti 'TunnelInterface' untuk operasi terkait kumpulan backend.
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan multi appliance Azure Site Recovery untuk skenario pemulihan bencana VMware ke Azure menggunakan RCM sebagai bidang kontrol.
* Azure Backup fixed targetPhysicalPath masalah dengan SQL CRR
* Perlindungan nonaktifkan tetap Azure Backup untuk beban kerja SQL
* Azure Backup menyelesaikan bug dalam mengatur properti CMK dalam rilis terbaru
* Azure Backup menghapus karakter khusus dari register-azrecoveryservicesbackupcontainer command help text

#### <a name="azresources"></a>Az.Resources
* Gunakan JsonExtensions untuk serialisasi deserialize objek JSON untuk memastikan penggunaan pengaturan serialisasi kustom [#15552]
* Menambahkan dukungan untuk jenis perubahan 'Tidak didukung' dan 'NoEffect' ke What-If penyebaran cmdlet.

#### <a name="azsecurityinsights"></a>Az.SecurityInsights
* Diperbarui ke parameter 'Get-AzSentinelIncident'
    - Menambahkan '-Filter' untuk mendukung filter OData
    - Menambahkan '-OrderBy' untuk mendukung pemesanan OData
    - Menambahkan '-Max' untuk mendukung pengambilan lebih dari default 1000 insiden.

#### <a name="azsql"></a>Az.Sql
* Mengubah implementasi yang mendasari 'Get-AzSqlDatabase' untuk mendukung respons paginated dari server
* Menambahkan parameter 'ZoneRedundant' ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance' untuk mengaktifkan pembuatan dan pembaruan zona - instans berlebihan.
* Menambahkan bidang ZoneRedundant ke model instans terkelola sehingga menampilkan informasi tentang zona - redundansi misalnya yang dikembalikan oleh 'Get-AzSqlInstance'.
* Extended AuditActionGroups enum di server & audit database. Ditambahkan DBCC_GROUP, DATABASE_OWNERSHIP_CHANGE_GROUP dan DATABASE_CHANGE_GROUP.
* Menambahkan bendera 'AsJob' ke 'Remove-AzSqlInstance'
* Menambahkan parameter 'SubnetId' ke 'Set-AzSqlInstance' untuk mendukung pembaruan lintas subnet SLO
* Ditingkatkan ke versi SDK terbaru

#### <a name="azstorage"></a>Az.Storage
* Tag blob get/set yang didukung pada blob tertentu
    -  'Get-AzStorageBlobTag'
    -  'Set-AzStorageBlobTag'
* Didukung membuat blob tujuan dengan tag blob tertentu saat upload/copy Blob
    -  'Set-AzStorageBlobContent'
    -  'Start-AzStorageBlobCopy'
* Gumpalan daftar yang didukung di seluruh kontainer dengan ekspresi sql filter tag blob
    -  'Get-AzStorageBlobByTag'
* Gumpalan daftar yang didukung di dalam wadah dan menyertakan Tag Blob
    -  'Get-AzStorageBlob'
* Didukung menjalankan operasi gumpalan dengan kondisi tag blob, dan gagal cmdlet ketika kondisi tag gumpalan tidak cocok
    -  'Get-AzStorageBlob'
    -  'Get-AzStorageBlobContent'
    -  'Get-AzStorageBlobTag'
    -  'Remove-AzStorageBlob'
    -  'Set-AzStorageBlobContent'
    -  'Set-AzStorageBlobTag'
    -  'Start-AzStorageBlobCopy'
    -  'Stop-AzStorageBlobCopy'
* Hasilkan token sas blob dengan versi API baru
    -  'New-AzstorageblobSASToken'
    -  'New-AzstorageContainersASToken'
    -  'New-AzstorageAccountsASToken'
* Kegagalan salinan blob tetap dengan kredensial OAuth saat klien dan server memiliki perbedaan waktu [#15644]
    -  'Copy-azStorageBlob'
* Memperbaiki hapus item Data Lake Gen2 gagal dengan token SAS yang dibacakan
    -  'Remove-AzDataLakeGen2Item'
* Revisi tujuan check-in yang ada memindahkan item Data Lake Gen2
    -  'Move-AzDataLakeGen2Item'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan kumpulan parameter ke 'Invoke-AzStorageSyncChangeDetection'
    - Dapat memanggil cmdlet tanpa parameter -DirectoryPath dan -Path untuk memicu deteksi perubahan pada seluruh berbagi file
* Menambahkan dukungan untuk upload otoritatif sebagai bagian dari New-AzStorageSyncServerEndpoint.
* Menambahkan informasi status pencacahan perubahan cloud di objek Cloud Endpoint.
* Objek Endpoint Server yang diperbarui dengan berbagai properti kesehatan
* Menambahkan properti 'ServerName' di Objek Server Endpoint dan Registered Server untuk mendukung menunjukkan FQDN server saat ini.

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Set-AzWebApp' untuk mengembalikan pesan peringatan yang valid saat gagal menambahkan -Hostname #9316
* Memperbaiki 'Get-AzWebApp' untuk mengembalikan CustomDomainVerificationId sebagai tanggapan. #9316

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Sears (@asears)
  * Memperbaiki ejaan nama akun (#15779)
  * Memperbaiki Ejaan, contoh (#15780)
* @cawrites, Perbarui New-AzDataMigrationService.md (#15646)
* @harpaul-gill, Menambahkan dukungan untuk pagination di Sql Get Databases (#15772)
* @jeepingben, Buat nama mutex yang aman untuk Linux (memperbaiki #15653) (#15666)
* @LosManos, Docs: Parameter diabaikan saat mencantumkan rahasia (#15788)
* Mats Estensen (@matsest), dokumen: tambahkan contoh untuk Update-AzSubscription (#15748)
* Mauricio Arroyo (@mauricio-msft), Perbaiki kesalahan ketik dalam contoh cmdlet (#15719)

## <a name="630---august-2021"></a>6.3.0 - Agustus 2021
#### <a name="azaccounts"></a>Az.Accounts
* Penyimpanan otomatis konteks dinonaktifkan saat persistensi cache token gagal di Windows dan macOS
* Menambahkan versi PowerShell ke dalam catatan telemetri
* Upgrade Microsoft.ApplicationInsights dari 2.4.0 ke 2.12.0
* Diperbarui Azure.Core ke 1.16.0

#### <a name="azaks"></a>Az.Aks
* Ditambahkan 'Start-AzAksCluster', 'Stop-AzAksCluster', 'Get-AzAksUpgradeProfile' dan 'Get-AzAksNodePoolUpgradeProfile'. [#14194]
* Menambahkan properti 'IdentityProfile' dalam output 'Get-AzAksCluster'. [#12546]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* [Melanggar Perubahan] Mengubah jenis PSCognitiveServicesAccount.Identity.Type dari IdentityType ke ResourceIdentityType.
* [Melanggar Perubahan] Mengubah jenis PSCognitiveServicesAccount.Sku.Tier dari SkuTier menjadi string.
* [Melanggar Perubahan] Dihapus ActionRequired dari PrivateLinkServiceConnectionState.
* Memperbarui PowerShell untuk menggunakan versi 2021-04-30.
* Menambahkan cmdlet 'Undo-AzCognitiveServicesAccountRemoval'.
* Menambahkan parameter '-RestrictOutboundNetworkAccess', '-AllowedFqdnList', '-DisableLocalAuth', '-KeyVaultIdentityClientId', '-IdentityType', '-UserAssignedIdentityId' ke 'New-AzureCognitiveServicesAccount' dan 'Set-AzureCognitiveServicesAccount'.
* Menambahkan parameter '-InRemovedState', '-Location' ke 'Remove-AzureCognitiveServicesAccount' dan 'Get-AzureCognitiveServicesAccount'.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki peringatan di cmdlet 'New-AzVM' yang menyatakan sku VM sedang default bahkan jika ukuran sku disediakan oleh pengguna. Sekarang hanya terjadi ketika pengguna tidak memberikan ukuran sku.
* Cmdlet 'Set-AzVmOperatingSystem' yang diedit untuk tidak lagi menimpa nilai EnableAutomaticUpdates yang ada pada yang diteruskan di mesin virtual jika ada.
* Modul Compute yang diperbarui untuk menggunakan .Net SDK terbaru versi 48.0.0.
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
* Memperbarui versi ADF .Net SDK ke 4.21.0

#### <a name="azmigrate"></a>Az.Migrate
* Menambahkan SQL Server jenis lisensi.
* Menambahkan fitur CRN.
* Menambahkan fitur tag sumber daya.
* Diperbarui ke versi api 2021-02-10.

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan parameter 'ResourceGroupName' kembali untuk parameter 'Add-AzAutoscaleSetting' set parameter 'AddAzureRmAutoscaleSettingUpdateParamGroup' dan membuatnya opsional [#15491]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Arsip untuk kubah V1.
* Menambahkan ProtectedItemsCount di Get-AzRecoveryServicesBackupProtectionPolicy.
* Azure site recovery bug fix for azure to azure in update vm properties.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'RedisVersion' di 'New-AzRedisCache' dan 'Set-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
* Memperbaiki bug dengan 'PSResource' di mana beberapa konstruktor meninggalkan properti 'SubscriptionId' tanpa penugasan / null.  [#10783]
* Menambahkan dukungan untuk membuat dan memperbarui Spesifikasi Template dalam file Bicep [#15313]
* Menambahkan parameter '-ProceedIfNoChange' ke penyebaran membuat cmdlet.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Model Aplikasi Terkelola dan Klasik Tetap (Aplikasi, Klaster, Layanan) dengan memperbarui konstruktor untuk mengambil semua properti baru
    - Ini memecahkan masalah terkait perpipaan di mana perpipaan hasil langsung dari panggilan Masuk ke dalam cmdlet dan Perbarui atau Atur panggilan hapus beberapa properti yang sengaja diatur
    - Memperbarui file pengujian yang sesuai untuk mencakup kasus yang disebutkan di atas

#### <a name="azsql"></a>Az.Sql
* Logika identitas tetap di 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Waktu Akses Terakhir Blob yang Didukung
    -  'Enable-AzStorageBlobLastAccessTimeTracking'
    -  'Disable-AzStorageBlobLastAccessTimeTracking'
    -  'Add-AzStorageAccountManagementPolicyaction'
* Membuat daftar 'Get-AzDataLakeGen2ChildItem' semua item datalake gen2 secara default, alih-alih membutuhkan pengguna untuk mencantumkan potongan demi potongan.
* Fixed BlobProperties adalah masalah kosong saat menggunakan sas tanpa awalan '?' [#15460]
* Memperbaiki kegagalan gumpalan kecil secara sinkron [#15548]
    - 'Copy-azStorageBlob'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Add-AzWebAppAccessRestrictionRule' gagal ketika pengguna tidak memiliki izin untuk mendapatkan daftar Tag Layanan #15316 dan #14862

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Borys Generalov (@bgener), Get-AzPolicyState.md Pembaruan (#15455)
* Dean Mock (@deanmock), New-AzAutomationSchedule.md Pembaruan (#15371)
* John Bevan (@JohnLBevan), #10783 - Perbaiki psresource Get-AzResource kembali dengan null SubscriptionId (#15106)
* Michael Mejias Sanchez (@mikemej), Pembaruan - Pembaruan penyebaran (VNET eksternal) (#15391)
* @mjsharma, Menambahkan catatan untuk perintah alternatif (#15360)
* Ked Mardemootoo (@nocticdr), Memperbaiki beberapa kesalahan ketik untuk kejelasan tambahan (#15428)
* Pascal Berger (@pascalberger), Perbaiki nama parameter dalam contoh Sync-AzVirtualNetworkPeering (#15493)
* @rcabr, Perbaikan doc di Get-AzStorageContainer (#15476)
* AAron (@S-AA-RON), New-AzNetworkSecurityGroup.md Pembaruan (#15512)
* 坂本ポテコ (@sakamoto-poteko), Update New-AzVMConfig.md (#15376)
* @Shawn-Yuen, Perbarui Remove-AzDataLakeGen2Item.md (#15388)

## <a name="621---july-2021"></a>6.2.1 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki kesalahan akses saat subscripiton tidak memiliki properti 'Tag' [#15425]

## <a name="620---july-2021"></a>6.2.0 - Juli 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan Tag, AuthorizationSource ke PSAzureSusbscripiton dan menambahkan TenantType, DefaultDomain, TenantBrandingLogoUrl, CountryCode ke PSAzureTenant [#15220]
* Klien langganan yang ditingkatkan ke 2021-01-01 [#15220]
* Menghapus mode Interaktif check-in lib umum
* Menambahkan titik akhir OperationalInsights ke lingkungan AzureChinaCloud [#15305]
* Log default modul yang dihasilkan otomatis yang dicetak ke aliran verbose

#### <a name="azaks"></a>Az.Aks
* Menambahkan parameter 'AvailabilityZone' untuk 'New-AzAksNodePool'. [#14505]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Menambahkan hanya properti baca 'ConnectionString' dan 'ApplicationId' ke komponen applicationinsights

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-OrchestrationMode' ke 'New-AzVmss' dan 'New-AzVmssConfig'
* Memperbarui cmdlet berikut untuk berfungsi saat sumber daya menggunakan sumber gambar jarak jauh menggunakan AKS atau Galeri Gambar Bersama.
    - 'Update-AzVm'
    - 'Update-AzVmss'
    - 'Update-AzGalleryImageVersion'
* Menambahkan parameter '-EnableCrossZoneUpgrade' dan '-PrioritUnhealthyInstance' ke 'Set-AzVmssRollingUpgradePolicy'
* Menambahkan parameter 'AssessmentMode' ke cmdlet 'Set-AzVMOperatingSystem'.
* Memperbaiki bug di 'Add-AzVmssNetworkInterfaceConfiguration'
* Pemeriksaan IOPS dan throughput tetap di 'Test-AzVMAEMExtension'
* Menambahkan cmdlet baru untuk versi API DiskRP 2020-12-01
    - New-AzDiskPurchasePlanConfig
    - Set-AzDiskSecurityProfile
* Cmdlet yang diubah untuk versi API DiskRP 2020-12-01
    - New-AzDiskConfig
    - New-AzSnapshotConfig
    - New-AzSnapshotUpdateConfig
    - New-AzDiskUpdateConfig
    - New-AzDiskEncryptionSetConfig
    - Update-AzDiskEncryptionSet

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Rilis ini memperkenalkan cmdlet untuk fitur Pencadangan Berkelanjutan(Point in time restore):
  - Memperkenalkan dukungan untuk membuat akun dengan kebijakan pencadangan mode berkelanjutan.
  - Memperkenalkan dukungan untuk Pemulihan titik waktu untuk akun dengan kebijakan pencadangan mode berkelanjutan.
  - Memperkenalkan dukungan untuk memperbarui interval pencadangan dan retensi cadangan untuk akun dengan kebijakan pencadangan mode berkala.
  - Memperkenalkan dukungan untuk mencantumkan sumber daya yang dapat dipulihkan dalam akun database langsung.
  - Memperkenalkan dukungan untuk menentukan jenis skema penyimpanan analitik pada pembuatan/pembaruan akun.
  - Cmdlet berikut ditambahkan:
    - Restore-AzCosmosDBAccount, New-AzCosmosDBDatabaseToRestore, Get-AzCosmosDBRestorableDatabaseAccount,
    - Get-AzCosmosDBSqlRestorableDatabase, Get-AzCosmosDBSqlRestorableContainer, Get-AzCosmosDBSqlRestorableResource,
    - Get-AzCosmosDBMongoDBRestorableDatabase, Get-AzCosmosDBMongoDBRestorableCollection, Get-AzCosmosDBMongoDBRestorableResource.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan Enkripsi Kunci Terkelola Pelanggan ke DataFactory

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dua pengaturan aplikasi tambahan (WEBSITE_CONTENTSHARE dan WEBSITE_CONTENTAZUREFILECONNECTIONSTRING) untuk aplikasi Konsumsi Linux. [15124]
* Memperbaiki bug dengan New-AzFunctionApp saat dibuat di Azure Gov. [13379]
* Cmdlet Az.Functions yang ditambahkan perlu mendukung pembuatan dan penyalinan pengaturan aplikasi dengan nilai kosong. [14511]

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug referensi null untuk 'Get-AzMetric' saat 'ResultType' diatur ke 'Metadata'
* Bug tetap untuk 'Add-AzAutoscaleSetting' tidak dapat menyalurkan hasil dari 'Get-AzAutoscaleSetting' [#13861]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan alamat IP publik sebagai parameter opsional untuk membuat server rute
    - 'New-AzRouteServer'
* Cmdlet yang diperbarui untuk mengaktifkan spesifikasi zona tepi
    - 'New-AzPublicIpPrefix'
    - 'New-AzLoadBalancer'
    - 'Layanan New-AzPrivateLink'
    - 'New-AzPrivateEndpoint'
* Menambahkan dukungan untuk melihat lokasi jaringan virtual yang diperluas di konsol
    - 'New-AzVirtualNetwork'
    - 'Get-AzVirtualNetwork'
* Menambahkan dukungan untuk melihat lokasi alamat IP publik yang diperluas di konsol
    - 'New-AzPublicIpAddress'
    - 'Get-AzPublicIpAddress'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Nonaktifkan Perlindungan Otomatis SQL AG.

#### <a name="azsecurity"></a>Az.Security
* Ketersediaan umum modul Az.Security
* Mengubah nama Get-AzRegulatoryComplainceAssessment menjadi Get-AzRegulatoryComplianceAssessment untuk memperbaiki kesalahan ketik

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter 'RestrictOutboundNetworkAccess' ke cmdlet berikut
    - 'New-AzSqlServer'
    - 'Set-AzSqlServer'
* Menambahkan cmdlet baru untuk operasi CRUD pada aturan FQDNs of Outbound Firewall yang Diizinkan 'Get-AzSqlServerOutboundFirewallRule' 'New-AzSqlServerOutboundFirewallRule' 'Remove-AzSqlServerOutboundFirewallRule'
* Memperbaiki logika identitas untuk SystemAssigned, UserAssigned identitys for New-AzSqlServer, New-AzSqlInstance
* Cmdlet yang diperbarui untuk mendapatkan dan memperbarui frekuensi cadangan diferensial database SQL 'Get-AzSqlDatabaseBackupShortTermRetentionPolicy' 'Set-AzSqlDatabaseBackupShortTermRetentionPolicy'
* Memperbaiki masalah PUT Parsial untuk Kebijakan Azure di 'Set-AzSqlServer' dan 'Set-AzSqlInstance'

#### <a name="azstorage"></a>Az.Storage
* Diaktifkan/nonaktifkan penghapusan lunak kontainer Blob yang didukung
    -  'Enable-AzStorageContainerDeleteRetentionPolicy'
    -  'Disable-AzStorageContainerDeleteRetentionPolicy'
* Kontainer Blob yang dihapus daftar yang didukung
    -  'Get-AzRmStorageContainer'
    -  'Get-AzStorageContainer'
* Memulihkan kontainer Blob yang dihapus yang didukung
    -  'Restore-AzStorageContainer'
* Pengaturan SMB aman yang didukung di properti layanan File
    - 'Update-AzStorageFileServiceProperty'
* Membuat akun yang didukung dengan EnableNfsV3
    - 'New-AzStorageAccount'
* Input yang didukung lebih banyak menyalin parameter blob dari pipeline [#15301]
    -  'Start-AzStorageBlobCopy'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki 'Import-AzWebAppKeyVaultCertificate' untuk mendukung ServerFarmId [#15091]
* Memperbaiki 'Menambahkan parameter opsional untuk menghapus atau menyimpan paket Appservice saat WebApp terakhir dihapus dari paket'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Mikey Bronowski (@MikeyBronowski)
  * Perbarui Get-AzSynapseTriggerRun.md (#15231)
  * Perbarui Get-AzSynapsePipelineRun.md dengan menambahkan lebih banyak contoh yang mencakup lebih banyak skenario (#15232)
* @mjsharma, Menambahkan catatan untuk perintah alternatif (#15359)
* @tomswedlund, Menambahkan dukungan untuk mengatur jenis skema penyimpanan analitik pada pembuatan/pembaruan akun untuk CosmosDB (#15362)
* @ylabade, Perbaiki nama parameter aplikasi web dalam contoh (#15291)

## <a name="610---june-2021"></a>6.1.0 - Juni 2021
#### <a name="azaccounts"></a>Az.Accounts
* Ditambahkan cmdlet 'Open-AzSurveyLink'
* File sertifikat yang didukung sebagai parameter input Connect-AzAccount

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah bahwa 'Set-AzAks' akan gagal di Automation Runbook. [#15006]

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Memperbaiki masalah bahwa 'ResourcegroupName' terlewatkan saat mengeksekusi di bawah cmdlet dengan parameter 'InputObject' [#14848]
  * 'Get-AzApplicationInsightsLinkedStorageAccount'
  * 'New-AzApplicationInsightsLinkedStorageAccount'
  * 'Update-AzApplicationInsightsLinkedStorageAccount'
  * 'Remove-AzApplicationInsightsLinkedStorageAccount'

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki masalah yang hilang profil di cmdlet 'Remove-AzCdnProfile'

#### <a name="azcompute"></a>Az.Compute
* Modul Compute yang diperbarui untuk menggunakan .Net SDK terbaru versi 47.0.0.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Menghapus tampilan kredensial berbagi file [#15224]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.19.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan fungsionalitas untuk menerima masukan dari pipeline untuk 'Get-AzEventHub' dari 'Get-AzEventHubNamespace'.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung fitur monitor azure baru di HDInsight:
    - Tambahkan cmdlet 'Get-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mendapatkan status Azure Monitor dari klaster HDInsight.
    - Tambahkan cmdlet 'Enable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan mengaktifkan Azure Monitor di klaster HDInsight.
    - Tambahkan cmdlet 'Disable-AzHDInsightAzureMonitor' untuk memungkinkan pelanggan menonaktifkan Azure Monitor di klaster HDInsight.

#### <a name="azkeyvault"></a>Az.KeyVault
* Item daftar duplikat yang dihapus di 'Get-AzKeyVault' [#15164]
* Menambahkan tag 'SecretManagement' ke modul 'Az.KeyVault' [#15173]

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui untuk server rute untuk cara yang lebih stabil untuk menambahkan konfigurasi IP.
* Menambahkan dukungan untuk mendapatkan satu sumber daya tautan pribadi.
* Menambahkan deskripsi lebih rinci tentang GroupId di 'New-AzPrivateLinkServiceConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan PrivateRange di AzureFirewallPolicy.
    - 'New-AzFirewallPolicy'
    - 'Set-AzFirewallPolicy'
* Cmdlet yang diperbarui untuk menambahkan NatRules di VirtualNetworkGateway dan BgpRouteTranslationForNat.
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'
* Cmdlet yang diperbarui untuk menambahkan EngressNatRules dan EgressNatRules di VirtualNetworkGateway Connection.
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan FlowTimeout di VirtualNetwork.
    - 'New-AzVirtualNetwork'
* Menambahkan cmdlet untuk Get/Create/Update/Delete VirtualNetworkGatewayNatRules.
    - 'New-AzVirtualNetworkGatewayNatrule'
    - 'update-azVirtualNetworkGatewayNatrule'
    - 'Get-AzVirtualNetworkGatewayNatrule'
    - 'Remove-azVirtualNetworkGatewayNatrule'
* Menambahkan cmdlet baru untuk Sync di VirtualNetworkPeering
    - 'Sync-AzVirtualNetworkPeering'
* Cmdlet yang diperbarui untuk menambahkan properti baru dan mendefinisikan ulang properti yang ada di VirtualNetworkPeering
    - 'Add-AzVirtualNetworkPeering'
    - 'Get-AzVirtualNetworkPeering'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan PreferredRoutingGateway di VirtualHub.
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Cmdlet yang diperbarui untuk mengekspos dua properti baca-saja dari sertifikat klien.
    - 'Get-AzApplicationGatewayTrustedClientCertificate'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan cross tenant DS Move.
* Pembatasan yang dihapus untuk mengambil titik pemulihan hanya untuk rentang waktu 30 hari.
* MENGAKTIFKAN CRR untuk wilayah baru.

#### <a name="azresources"></a>Az.Resources
* Penamaan yang diizinkan saat menguji penyebaran [#11497]

#### <a name="azsignalr"></a>Az.Signalr
* Diubah menjadi parameter 'Izinkan' dan 'Tolak' cmdlet 'Update-AzSignalRNetworkAcl':
    - Menerima 'Trace' sebagai nilai yang valid.
    - Diterima '@()' sebagai koleksi kosong untuk menghapus daftar.
* Didukung 'ResourceGroupCompleter' dan 'ResourceNameCompleter' dalam cmdlet yang berlaku.
* Usang properti 'HostNamePrefix' dari jenis output 'PSSignalRResource' dari cmdlet berikut:
    - 'Get-AzSignalr'
    - 'New-AzSignalr'
    - 'Update-AzSignalr'

#### <a name="azsql"></a>Az.Sql
* Opsi tambahan untuk mendukung id konfigurasi pemeliharaan versi pendek untuk Instans Terkelola di cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Menambahkan HighAvailabilityReplicaCount ke 'New-AzSqlDatabaseSecondary'
* Menambahkan Administrator Eksternal dan AAD Saja Properti ke AzSqlServer dan AzSqlInstance
    - Opsi tambahan untuk menentukan cmdlet '-ExternalAdminName', '-ExternalAdminSid', '-EnableActiveDirectoryOnlyAuthentication' di cmdlet 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
    - Opsi tambahan untuk memperluas informasi administrator eksternal menggunakan cmdlet '-ExpandActiveDirectoryAdministrator' di cmdlet 'Get-AzSqlServer' dan 'Get-AzSqlInstance'
* Memperbaiki 'Set-AzSqlDatabase' agar tidak lagi default ReadScale ke Dinonaktifkan saat tidak ditentukan
* Memperbaiki 'Set-AzSqlServer' dan 'Set-AzSqlInstance' untuk PUT parsial hanya dengan identitas dan properti null
* Menambahkan parameter yang terkait dengan UMI di cmdlet 'New-AzSqlServer', 'New-AzSqlInstance', 'Set-AzSqlServer' dan 'Set-AzSqlInstance'.
* Menambahkan parameter -AutoRotationEnabled ke cmdlet berikut:
    - 'Set-AzSqlServerTransparentDataEncryptionProtector'
    - 'Get-AzSqlServerTransparentDataEncryptionProtector'
    - 'Set-AzSqlInstanceTransparentDataEncryptionProtector'
    - 'Get-AzSqlInstanceTransparentDataEncryptionProtector'

#### <a name="azstorage"></a>Az.Storage
* Didukung membuat berbagi file dengan NFS / SMB diaktifkanEnabledProtocol dan RootSquash, dan memperbarui berbagi dengan RootSquash
    - 'New-AzRmStorageShare'
    - 'Update-AzRmstorageShare'
* Didukung aktifkan Smb Multichannel pada layanan File
    -  'Update-AzStorageFileServiceProperty'
* Memperbaiki salinan di dalam masalah akun yang sama oleh sumber akses dengan kredensial anonim, saat menyalin Blob di dalam akun yang sama dengan kredensial Oauth
* Menghapus StorageFileDataSmbShareOwner dari kumpulan nilai parameter DefaultSharePermission di akun penyimpanan buat/perbarui
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki masalah yang mencegah penghapusan aturan berdasarkan nama dan pengenal unik di 'Remove-AzWebAppAccessRestrictionRule'
* Memperbaiki masalah yang default AlwaysOn ke false di 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andy Roberts (@andyr8939), Menghapus variabel TimeGrain yang tidak digunakan dari contoh (#15062)
* Ashley Roll (@AshleyRoll), Hapus kredensial berbagi file Write-Host bocor (#15225)
* Kailash Mandal (@KaishM), New-AzPublicIpAddress.md Pembaruan (#15040)
* Olivier Miossec (@omiossec), Get-AzExpressRouteCircuitRouteTable.md Pembaruan (#15054)
* Scott (@S-T-S), Set-AzNetworkInterface.md Pembaruan (#15112)
* @sohaibMSFT, Contoh Skala Otomatis Gateway Aplikasi (#15071)
* @Srihsu, Perbarui Split-AzReservation.md (#15049)
* @srozemuller, typo dalam contoh parameter resourcegroup (#15146)

## <a name="600---may-2021"></a>6.0.0 - Mei 2021

#### <a name="supported-versions-of-powershell"></a>Versi PowerShell yang didukung

Karena [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) Az 6.0.0 hanya didukung pada versi PowerShell berikut:
 - Windows PowerShell 5,1
 - PowerShell 7.0.6 ke atas
 - PowerShell 7.1.3 atau lebih tinggi

Untuk informasi selengkapnya dan cara meningkatkan, lihat [Azure PowerShell modul Lifecycle](/powershell/azure/azureps-support-lifecycle).

#### <a name="azaccounts"></a>Az.Accounts
* Azure.Identity yang ditingkatkan ke 1.4 dan MSAL ke 4.30.1
* Menghapus parameter usang 'ManagedServiceHostName', 'ManagedServicePort' dan 'ManagedServiceSecret' dari cmdlet 'Koneksi-AzAccount', variabel lingkungan 'MSI_ENDPOINT' dan 'MSI_SECRET' dapat digunakan sebagai gantinya
* Sesuaikan format tampilan PSAzureRmAccount untuk menyembunyikan rahasia utama layanan [#14208]
* Menambahkan parameter opsional 'AuthScope' ke 'Koneksi-AzAccount' untuk mendukung peningkatan autentikasi fitur bidang data
* Mengatur waktu percobaan ulang menurut variabel lingkungan [#14748]
* Autentikasi penerbit nama subjek yang didukung

#### <a name="azcompute"></a>Az.Compute
* Menambahkan 'Invoke-AzVmInstallPatch' untuk mendukung instalasi patch di VM menggunakan PowerShell.
* Modul Compute yang diperbarui untuk menggunakan .Net SDK terbaru versi 46.0.0.
* Menambahkan parameter opsional '-EdgeZone' ke cmdlet berikut:
    - 'Get-AzVMImage
    - 'Get-AzVMImageOffer'
    - 'Get-AzvmImagesku'
    - 'New-AzDiskConfig'
    - 'New-AzImageConfig'
    - 'New-AzSnapshotConfig'
    - 'New-AzVM'
    - 'New-AzVmssConfig'
    - 'New-AzVMSS'

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Menambahkan cmdlet baru: 'Start-AzContainerGroup', 'Stop-AzContainerGroup' [#10773], 'Invoke-AzContainerInstanceCommand' [#7648], 'Update-AzContainerGroup', 'Add-AzContainerInstanceOutput', 'Get-AzContainerInstanceCachedImage', 'Get-AzContainerInstanceCapability', 'Get-AzContainerInstanceUsage', 'New-AzContainerGroupImageRegistryCredentialObject', 'New-AzContainerGroupPortObject', 'New-AzContainerGroupVolumejectOb', 'New-AzContainerInstanceEnvironmentVariableObject',  'New-AzContainerInstanceInitDefinitionObject', 'New-AzContainerInstanceObject', 'New-AzContainerInstancePortObject' dan 'New-AzContainerInstanceVolumeMountObject'
* Parameter Analitik Log yang Didukung di 'New-AzContainerGroup' [#11117]
* Menambahkan dukungan untuk menentukan profil jaringan dan nama Azure File Share di 'New-AzContainerGroup' [#9993] [#12218]
* Menambahkan dukungan untuk menentukan variabel lingkungan sebagai SecureValue [#10110] [#10640]

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki masalah nama pengguna dan kata sandi di 'Import-AzContainerRegistryImage' [#14971]
* Operasi bidang data tetap (repositori, tag, manifes) gagal melakukan cross registry dalam satu sesi Powershell [#14849]

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan dukungan untuk Bidang data Sql RBAC, memungkinkan pembuatan, pembaruan, penghapusan, dan pengambilan Definisi Peran dan Penetapan Peran
  - Cmdlet berikut ditambahkan:
    - Get-AzCosmosDBSqlRoleDefinition, Get-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlRoleDefinition, New-AzCosmosDBSqlRoleAssignment,
    - Remove-AzCosmosDBSqlRoleDefinition, Remove-AzCosmosDBSqlRoleAssignment,
    - Update-AzCosmosDBSqlRoleDefinition, Update-AzCosmosDBSqlRoleAssignment,
    - New-AzCosmosDBSqlPermission

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Versi api yang ditingkatkan ke pratinjau 2021-02-01.

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dukungan dalam pembuatan aplikasi fungsi untuk aplikasi fungsi Python 3.9 dan Node 14
* Dukungan yang dihapus dalam pembuatan aplikasi fungsi untuk aplikasi fungsi V2, Python 3.6, Node 8, dan Node 10
* Parameter IdentityID yang diperbarui dari string ke array string di Update-AzFunctionApp. Ini harus konsisten dengan New-AzFunctionApp yang memiliki parameter yang sama dengan array string.
* Diperbarui FullyQualifiedErrorId untuk versi Fungsi yang tidak valid dari FunctionsVersionIsInvalid ke FunctionsVersionNotSupported
* Saat membuat aplikasi fungsi Node.js, jika tidak ada versi runtime yang ditentukan, versi runtime default diatur ke 14, bukan 12

#### <a name="azkeyvault"></a>Az.KeyVault
* Ukuran kunci yang disediakan untuk kunci RSA [#14819]

#### <a name="azkusto"></a>Az.Kusto
* Versi API yang ditabrak ke stabil 2021-01-01

#### <a name="azmaintenance"></a>Az.Pemeliharaan
* Versi API yang ditabrak ke stabil 2021-05-01

#### <a name="azmigrate"></a>Az.Migrate
* Memperbaiki masalah di Initialize-AzMigrateReplicationInfrastructure.ps1

#### <a name="aznetwork"></a>Az.Network
* Validasi yang diperbarui untuk memungkinkan melewati nilai nol untuk parameter saDataSizeKilobytes
    - 'New-AzureRmIpsecPolicy'
* Menambahkan parameter opsional '-EdgeZone' ke cmdlet berikut:
    - 'New-AzNetworkInterface'
    - 'New-AzPublicIpAddress'
    - 'New-AzVirtualNetwork'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki masalah keamanan dengan pemulihan SQL, ini adalah perubahan yang diperlukan. TargetContainer menjadi wajib untuk Pemulihan Lokasi Alternatif.
* Dihapus Set-AzRecoveryServicesBackupProperties cmdlet alias, Set-AzRecoveryServicesBackupProperty didukung.
* Dihapus Get-AzRecoveryServicesBackupJobDetails cmdlet alias, Get-AzRecoveryServicesBackupJobDetail didukung.
* Menambahkan dukungan untuk DS Move langganan silang.
* Dukungan Azure Site Recovery untuk skenario pemulihan bencana VMware ke Azure menggunakan RCM sebagai bidang kontrol.

#### <a name="azresources"></a>Az.Resources
* Mengubah '-IdentifierUris' di 'New-AzADApplication' menjadi parameter opsional
* Dihapus dihasilkan 'DisplayName' dari ADApplication dibuat oleh 'New-AzADServicePrincipal'
* SDK yang diperbarui ke pratinjau 3.13.1 untuk menggunakan versi API GA TemplateSpecs
* Menambahkan 'AdditionalProperties' ke PSADUser dan PSADGroup [#14568]
* Mendukung 'CustomKeyIdentifier' di 'New-AzADAppCredential' dan 'Get-AzADAppCredential' [#11457], [#13723]
* Diubah 'MainTemplate' untuk ditampilkan oleh formatter default untuk Versi Spesifikasi Template

#### <a name="azsecurityinsights"></a>Az.SecurityInsights
* Rilis GA untuk `Az.SecurityInsights`

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menghapus perintah sertifikat klaster yang tidak digunakan lagi:
    - 'Add-AzServiceFabricClusterCertificate'
    - 'Remove-AzServiceFabricClusterCertificate'
* Mengubah model PSManagedService untuk menghindari penggunaan parameter properti langsung dari sdk.
* Menghapus parameter yang tidak digunakan lagi untuk cmdlet terkelola:
    - 'ReverseProxyEndpointPort'
    - 'InstanceCloseDelayDuration'
    - 'ServiceDnsName'
    - 'InstanceCloseDelayDuration'
    - 'DropSourceReplicaOnMove'
* Memperbaiki 'Update-AzServiceFabricReliability' untuk memperbarui dengan benar jumlah instans vm dari jenis node utama pada sumber daya klaster.

#### <a name="azsql"></a>Az.Sql
* Dokumentasi 'Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline' yang diperbarui untuk menyertakan contoh define array of array dengan satu inner array.
* Menambahkan cmdlet 'Copy-AzSqlDatabaseLongTermRetentionBackup'
    - Menyalin cadangan LTR ke server yang berbeda
* Menambahkan cmdlet 'Update-AzSqlDatabaseLongTermRetentionBackup'
    - Perbarui nilai Redundansi Storage Cadangan untuk pencadangan LTR
* Menambahkan CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy ke 'Get-AzSqlDatabase', 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlDatabaseSecondary', 'Set-AzSqlDatabaseSecondary', 'New-AzSqlDatabaseCopy'
    - Mengubah Nilai Pencadangan Ke CurrentBackupStorageRedundancy, RequestedBackupStorageRedundancy untuk mencerminkan nilai saat ini dan apa yang telah diminta jika perubahan dibuat

#### <a name="azstorage"></a>Az.Storage
* Snapshot berbagi file yang didukung
    - 'New-AzRmStorageShare'
    - 'Get-AzRmStorageShare'
    - 'Remove-AzRmStorageShare'
* Didukung menghapus berbagi file dengan snapshot -nya (disewa dan tidak disewa), secara default menghapus berbagi file akan gagal ketika berbagi memiliki snapshot
    - 'Remove-AzRmStorageShare'
* Kebijakan inventaris Blob Set/Get/Remove blob yang didukung
    - 'New-azstorageblobInventoryPolicyrule'
    - 'Set-AzStorageBlobInventoryPolicy'
    - 'Get-AzStorageBlobInventoryPolicy'
    - 'Remove-AzStorageBlobInventoryPolicy'
* Dukungan DefaultSharePermission di akun penyimpanan buat/perbarui
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* AllowCrossTenantReplication yang Didukung di akun penyimpanan buat/perbarui
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Kebijakan Replikasi Objek Set yang Didukung dengan SourceAccount/DestinationAccount sebagai id sumber daya akun Storage
    - 'Set-AzStorageObjectReplicationPolicy'
* Didukung set SasExpirationPeriod sebagai TimeSpan.Zero
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount
* Pastikan nama akun yang benar digunakan saat membuat kredensial akun
    - 'New-AzStorageContext'

#### <a name="azstoragesync"></a>Az.StorageSync
* Usang 'Invoke-AzStorageSyncFileRecall'
    - Pelanggan sebaiknya menggunakan 'Invoke-StorageSyncFileRecall', cmdlet yang dikirimkan dengan agen Azure File Sync.
* Fitur transfer data offline yang dihapus di 'New-AzStorageSyncServerEndpoint'.

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Versi API yang ditabrak ke pratinjau 2017-04-01
* Menambahkan dukungan StreamAnalytics Cluster

#### <a name="azwebsites"></a>Az.Websites
* memperbarui 'Set-AzAppServicePlan' untuk menyimpan Tag yang ada saat menambahkan Tag baru
* Memperbaiki 'Set-AzWebApp' untuk mengatur AppSettings
* 'Set-AzWebAppSlot' untuk mengatur FtpsState
* Menambahkan dukungan untuk StaticSites.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @corichte, Perbarui New-AzVirutalNetworkGatewayConnection Ex 1 (#14858)
* Hiroshi Yoshioka (@hyoshioka0128)
  * Typo "Azure SQL database"→"Azure SQL Database" (#14883)
  * Kesalahan ketik "Instans terkelola Azure SQL"→"Azure SQL Managed Instance" (#14891)
  * Kesalahan ketik "Instans terkelola Azure SQL"→"Azure SQL Managed Instance" (#14892)
  * Kesalahan ketik "Instans terkelola Azure SQL"→"Azure SQL Managed Instance" (#14902)
  * Kesalahan ketik "Instans terkelola Azure SQL"→"Azure SQL Managed Instance" (#14901)
  * Kesalahan ketik "Instans terkelola Azure SQL"→"Azure SQL Managed Instance" (#14900)
  * Kesalahan ketik "Instans terkelola Azure SQL"→"Azure SQL Managed Instance" (#14898)
  * Kesalahan ketik "Instans terkelola Azure SQL"→"Azure SQL Managed Instance" (#14899)
* Jay Zelos (@jzelos), Contoh diperbarui 3 untuk menggunakan parameter yang benar (#14852)
* @StevePantol, Perbarui New-AzVMwarePrivateCloud.md (#14996)

## <a name="590---may-2021"></a>5.9.0 - Mei 2021
#### <a name="azaks"></a>Az.Aks
* Menambahkan dukungan 'AcrNameToAttach' di 'Set-AzAksCluster'. [#14692]
* Menambahkan dukungan 'AcrNameToDetach' di 'Set-AzAksCluster'. [#14693]
* Menambahkan 'Set-AzAksClusterCredential' untuk mengatur ulang ServicePrincipal dari klaster AKS yang ada.

#### <a name="azautomation"></a>Az.Automation
* Menambahkan dukungan untuk User Assigned Identitys dan PublicNetworkAccess flag

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung PREMIUM AFD / SKU Standar baru

#### <a name="azcompute"></a>Az.Compute
* Memperbarui cmdlet 'Set-AzVMDiskEncryptionExtension' untuk mendukung migrasi ekstensi ADE dari dua pass (versi dengan parameter input AAD) ke single pass (versi tanpa parameter input AAD).
    - Menambahkan parameter switch '-Migrate' untuk memicu alur kerja migrasi.
    - Menambahkan parameter switch '-MigrationRecovery' untuk memicu alur kerja pemulihan untuk VM yang mengalami kegagalan setelah migrasi dari dua pass ADE.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan Identitas yang Ditetapkan Pengguna ke Pabrik Data.
* Memperbarui versi ADF .Net SDK ke 4.18.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Parameter Rahasia Enable-AzFrontDoorCustomDomainHttps menjadi opsional untuk mendukung rotasi otomatis bawa-sertifikat Anda sendiri

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -IncludeVersions' saat versi saat ini dinonaktifkan [#14740]
* Menampilkan kode kesalahan dan pesan saat memperbarui rahasia yang dibersihkan [#14800]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk Multiple IP per NIC for Azure to Azure provider.
* Dukungan Azure Site Recovery untuk SqlServerLicenseType untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk Availability set untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk TargetVmSize untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk ResourceTagging untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Pemulihan Situs Azure untuk Set Timbangan Mesin Virtual untuk penyedia Azure ke Azure.
* Menambahkan dukungan untuk memulihkan disk vm yang tidak dikelola sebagai disk terkelola.

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter 'ObjectType' untuk 'New-AzRoleAssignment'

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Perintah Klaster Terkelola yang Ditingkatkan untuk menggunakan Service Fabric Managed Cluster SDK versi 1.0.0 yang menggunakan penyedia sumber daya kain layanan api-versi 2021-05-01.
* 'New-AzServiceFabricManagedCluster' menambahkan parameter UpgradeCadence dan ZonalResiliency.
* 'New-AzServiceFabricManagedNodeType' menambahkan parameter DiskType, VmUserAssignedIdentity, IsStateless dan MultiplePlacementGroup.
* Parameter tanda 'New-AzServiceFabricManagedClusterService' dan 'Set-AzServiceFabricManagedClusterService' untuk penghentian: InstanceCloseDelayDuration, DropSourceReplicaOnMove dan ServiceDnsName. Mereka tidak didukung.

#### <a name="azresourcemover"></a>Az.Resourcemover
* Ketersediaan umum modul 'Az.ResourceMover'

#### <a name="azstorage"></a>Az.Storage
* Akun penyimpanan buat/perbarui yang didukung dengan KeyExpirationPeriod dan SasExpirationPeriod
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Akun penyimpanan buat/perbarui yang didukung dengan enkripsi keyvault dan keyvault akses dengan identitas yang ditetapkan pengguna
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* EdgeZone yang didukung dalam membuat akun penyimpanan
    - 'New-AzStorageAccount'
* Memperbaiki masalah yang menghapus gumpalan yang tidak berubah akan meminta pesan yang salah.
    - 'Remove-AzStorageAccount'
* Pembaruan yang diizinkan Storage properti Account KeyVault dengan membersihkan Keyversion untuk mengaktifkan rotasi otomatis utama [#14769]
    - 'Set-AzStorageAccount'
* Menambahkan pesan peringatan perubahan yang melanggar untuk perubahan pemecahan cmdlet mendatang
    - 'Remove-AzRmStorageShare'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Thomas Lee (@doctordns), Get-AzEnvironment.md Pembaruan (#14704)
* Fabian (@FullByte), Contoh dengan parameter yang salah (typo) (#14743)
* @gradinDotCom, Perbarui Get-AzNetworkWatcherNextHop.md (#14813)
* Dr Greg Low (@greglow-sdu), Get-AzSqlServerDnsAlias.md Pembaruan (#14737)
* Prateek Singh (@PrateekKumarSingh)
  * memperbaiki kesalahan ketik (#14779)
  * memperbaiki kesalahan ketik (#14773)
* Remco Eissing (@remcoeissing)
  * Kesalahan ketik tetap dalam Restore-AzApiManagement (#14770)
  * Contoh 2 untuk menggunakan New-AzPolicyExemption (#14716)
* @sharma224
  * Perubahan identitas pengguna (#14803)
  * Mendukung kunci terkelola Pelanggan (#14680)
* Yannick Dils (@yannickdils), Perbarui Penjelasan Lokasi (#14719)

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
* Nilai default yang diedit untuk parameter Ukuran dalam cmdlet New-AzVM dari Standard_DS1_v2 ke Standard_D2s_v3.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki bug di 'Get-AzContainerRegistryManifest' memperlihatkan nama gambar yang salah

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung mendapatkan vmsize default dari backend jika pelanggan tidak memberikan parameter terkait: '-WorkerNodeSize', '-HeadNodeSize', '-ZookeeperNodeSize', '-EdgeNodeSize', '-KafkaManagementNodeSize'.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Menambahkan dukungan untuk Acr LoginServers

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki bug untuk 'Get-AzKeyVaultSecret -AsPlainText' jika rahasia tersebut tidak ditemukan [#14645]

#### <a name="azmigrate"></a>Az.Migrate
* Nullref Bug diperbaiki di server yang ditemukan dan menginisialisasi commandlet infrastruktur replikasi.

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan cmdlet untuk mendapatkan kategori pengaturan diagnostik untuk langganan
    - 'Get-AzSubscriptionDiagnosticSettingCategory'
* Operasi pengaturan diagnostik langganan yang didukung dengan parameter baru: SubscriptionId
    - 'Get-AzDiagnosticSetting'
    - 'New-AzDiagnosticSetting'
    - 'Remove-AzDiagnosticSetting'
* Mendukung parameter 'AutoMitigate' dalam properti aturan peringatan metrik. Bendera menunjukkan apakah peringatan harus diselesaikan secara otomatis atau tidak.

#### <a name="azresources"></a>Az.Resources
* Menambahkan peringatan perubahan berbuka yang akan datang pada cmdlet di bawah ini, karena nilai parameter 'IdentifierUris' akan membutuhkan domain terverifikasi.
  - 'New-AzADApplication'
  - 'Update-AzADApplication'
  - 'New-AzADServicePrincipal'
  - 'Update-AzADServicePrincipal'
* Mengabaikan pesan peringatan Bicep dalam aliran kesalahan jika exitcode sama dengan nol.

#### <a name="azsql"></a>Az.Sql
* Menambahkan peringatan perubahan perubahan output cmdlet yang melanggar hal-hal berikut:
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
* Blob salinan tetap gagal dengan konteks sumber sebagai Oauth [#14662]
    -  'Start-AzStorageBlobCopy'

#### <a name="azstreamanalytics"></a>Az.StreamAnalytics
* Menambahkan pesan peringatan perubahan yang akan datang ke semua cmdlet karena perubahan parameter yang akan datang.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrei Zhukouski (@BurgerZ), Perbaiki kesalahan ketik (#14575)
* Mark Allison (@markallisongit), Invoke-AzSqlInstanceFailover.md Pembaruan (#14603)

## <a name="570---march-2021"></a>5.7.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki pesan peringatan yang salah di Windows PowerShell [#14556]
* Atur variabel Azure Environment 'AzureKeyVaultServiceEndpointResourceId' sesuai dengan nilai 'AzureKeyVaultDnsSuffix' saat menemukan lingkungan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah untuk memulai runbook Python3 dengan parameter

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.15.0

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki bahwa 'New-AzServiceBusAuthorizationRuleSASToken' mengembalikan token yang tidak valid. [#12975]

#### <a name="aziothub"></a>Az.IotHub
* IoT Hub Management SDK dan model yang diperbarui ke versi 3.0.0 (api-versi 2020-03-01)

#### <a name="azkeyvault"></a>Az.KeyVault
* Mendukung desain API baru yang akan datang untuk 'Export-AzKeyVaultSecurityDomain'
* Memperbaiki beberapa kesalahan ketik dalam pesan cmdlet [#14341]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk menggantikan nama produk lama 'router virtual' dengan nama baru 'route server' di masa depan.
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - 'Get-AzRouteServerPeerAdvertisedRoute'
    - Menambahkan peringatan atribut deprekasi ke cmdlet lama.
* Diperbarui 'set-azExpressRouteGateway' untuk memungkinkan parameter -MinScaleUnits tanpa menentukan -MaxScaleUnits
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan VpnLinkConnectionMode di VpnSiteLinkConnections.
    - 'New-AzVpnSiteLinkConnection'
    - 'Update-AzVpnConnection'
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Tautan Situs VPN.
    - 'Get-VpnSiteLinkConnectionIkeSa'
* Menambahkan cmdlet baru untuk mengatur ulang Koneksi Gateway Jaringan Virtual.
    - 'Reset-AzVirtualNetworkGatewayConnection'
* Menambahkan cmdlet baru untuk mengatur ulang Koneksi Tautan Situs Vpn.
    - 'Reset-VpnSiteLinkConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan parameter opsional -TrafficSelectorPolicies
    - 'New-AzVpnConnection'
    - 'Update-AzVpnConnection'
* Perbaikan bug untuk memperbarui vpnServerConfiguration.
* Tambahkan scenarioTest for p2s multi auth VWAN.
* Menambahkan dukungan fitur multi-auth untuk VNG
    - 'Get-AzVpnClientConfiguration'
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Cross Zonal Restore untuk mesin virtual terkelola.

#### <a name="azredisenterprisecache"></a>Az.RedisEnterpriseCache
* Versi GA dari Az.RedisEnterpriseCache

#### <a name="azresources"></a>Az.Resources
* Pesan bisep yang dialihkan ke aliran verbose
* Menghapus logika menyalin file template Bicep ke folder temp.
* Menambahkan dukungan jenis sumber daya pembebasan kebijakan
* Memperbaiki fungsi bagaimana-jika saat menggunakan parameter '-QueryString'.
* Normalisasi '-QueryString' dimulai dengan '?' untuk skenario yang melibatkan parameter dinamis.

#### <a name="azservicebus"></a>Az.ServiceBus
* Memperbaiki bahwa 'New-AzServiceBusAuthorizationRuleSASToken' mengembalikan token yang tidak valid. [#12975]

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan parameter 'VMImagePublisher', 'VMImageOffer', 'VMImageSku', 'VMImageVersion' ke 'Add-AzServiceFabricNodeType' untuk memfasilitasi pembuatan gambar OS alternatif yang mudah untuk jenis node baru.
* Menambahkan parameter 'IsPrimaryNodeType' ke 'Add-AzServiceFabricNodeType' untuk dapat membuat tipe node utama tambahan, untuk tujuan transisi tipe node utama ke yang lain dalam kasus migrasi OS.
* 'Add-AzServiceFabricNodeType' sekarang menyalin ekstensi LinuxDiagnostic dengan benar. Ini sebelumnya tidak berfungsi untuk Linux.
* 'Add-AzServiceFabricNodeType' sekarang menyalin pemetaan port NAT inbound RDP /SSH dengan benar ke jenis node baru.
* Menambahkan template untuk 'UbuntuServer1804' untuk membuat cluster Ubuntu 18.04 menggunakan 'New-AzServiceFabricCluster'.
* 'Remove-AzServiceFabricNodeType' salah memblokir jenis node ketahanan Perunggu untuk dihapus, dan ini telah diperbarui untuk hanya memblokir ketika tingkat daya tahan Bronze berbeda antara jenis node SF dan pengaturan VMSS.
* Menambahkan cmdlet 'Update-AzServiceFabricVmImage' untuk memperbarui jenis paket runtime SF yang dikirimkan. Ini harus diubah saat bermigrasi dari Ubuntu 16 ke 18.
* Menambahkan cmdlet 'Update-AzServiceFabricNodeType' untuk memperbarui properti tipe node cluster. Untuk saat ini ini hanya digunakan untuk memperbarui apakah jenis node primer melalui parameter bool '-IsPrimaryNodeType False'.
* 'Update-AzServiceFabricReliability' sekarang dapat memperbarui tingkat keandalan ketika cluster memiliki lebih dari satu jenis node utama. Untuk melakukan ini, nama jenis node disediakan melalui parameter -NodeType baru.
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
* Perintah Klaster Terkelola yang Ditingkatkan untuk menggunakan Service Fabric Managed Cluster SDK versi 1.0.0-beta.1 yang menggunakan penyedia sumber daya kain layanan api-version 2021-01-01-preview.

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet 'New-AzSqlServerTrustGroup'
* Menambahkan cmdlet 'Remove-AzSqlServerTrustGroup'
* Menambahkan cmdlet 'Get-AzSqlServerTrustGroup'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah yang mencantumkan akun dari grup sumber daya tidak akan menggunakan tautan berikutnya
    - 'Get-AzStorageAccount'
* Didukung ChangeFeedRetentionInDays saat Aktifkan ChangeFeed pada layanan Blob
    - 'Update-AzStorageBlobServiceProperty'

#### <a name="azwebsites"></a>Az.Websites
* Diperbarui 'Add-AzWebAppAccessRestrictionRule' untuk memungkinkan semua Tag Layanan yang didukung dan memvalidasi terhadap Service Tag API.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Freddie Sackur (@fsackur), Perbaiki token SAS yang tidak valid dari New-AzServiceBusAuthorizationRuleSASToken dan New-AzEventHubAuthorizationRuleSASToken (#14535)
* Serafín Martín (@infoTrainingym), parameter Unkown (#14515)
* João Carlos Ferra de Almeida (@Jalmeida1994), Get-AzAksNodePool.md Pembaruan (#14503)
* Liam Barnett (@liambarnett), Memperbaiki 3 kesalahan ketik dalam dokumen (#14335)
* @sbojjawar-Msft, Perbarui Set-AzSqlDatabaseVulnerabilityAssessmentRuleBaseline.md (#14432)
* Yannick Dils (@yannickdils), Hapus grup sumber daya dari get-azloadbalancer hasil ini dalam pembaruan wilayah / zona. (#14417)

## <a name="560---march-2021"></a>5.6.0 - Maret 2021
#### <a name="azaccounts"></a>Az.Accounts
* Tingkatkan Azure.Identity untuk memperbaiki masalah yang Connect-AzAccount gagal saat kredensial ADFS digunakan [#13560]

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah yang string tidak dapat diserialkan dengan benar. [#14215]
* Menambahkan Dukungan untuk Tipe Runbook Python3

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EnableHotpatching' ke cmdlet 'Set-AzVMOperatingSystem' untuk mesin Windows.
* Menambahkan parameter '-PatchMode' ke set parameter Linux di cmdlet 'Set-AzVMOperatingSystem'.
* [Melanggar Perubahan] Melanggar perubahan untuk pengguna di pratinjau publik untuk fitur Patching Tamu VM.
    - Properti yang dihapus 'RebootStatus' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Properti yang dihapus 'StartedBy' dari objek 'Microsoft.Azure.Management.Compute.Models.LastPatchInstallationSummary'.
    - Berganti nama menjadi properti 'Kbid' menjadi 'KbId' di objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineSoftwarePatchProperties'.
    - 'Patch' properti yang diganti namanya menjadi 'availablePatches' di objek 'Microsoft.Azure.Management.Compute.Models.VirtualMachineAssessPatchesResult'.
    - Objek yang diganti namanya 'Microsoft.Azure.Management.Compute.Models.SoftwareUpdateRebootBehavior' menjadi 'Microsoft.Azure.Management.Compute.Models.VMGuestPatchRebootBehavior'.
    - Objek yang diganti namanya 'Microsoft.Azure.Management.Compute.Models.InGuestPatchMode' menjadi 'Microsoft.Azure.Management.Compute.Models.WindowsVMGuestPatchMode'.
* [Melanggar Perubahan] Menghapus semua cmdlet 'ContainerService'. Container Service API tidak digunakan lagi pada Januari 2020.
    - 'Add-azContainerServiceagentPoolProfile'
    - 'Get-AzContainerService'
    - 'New-AzContainerService'
    - 'New-AzContainerServiceConfig'
    - 'Remove-AzContainerService'
    - 'Remove-azContainerServiceagentPoolProfile'
    - 'Update-AzContainerService'

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Autentikasi tetap untuk `Connect-AzContainerRegistry`

#### <a name="azcosmosdb"></a>Az.CosmosDB
* Memperkenalkan NetworkAclBypass dan NetworkAclBypassResourceIds for Database Account cmdlets.
* Memperkenalkan parameter ServerVersion ke Update-AzCosmosDBAccount.
* Memperkenalkan BackupInterval dan BackupRetention untuk cmdlet Akun Database

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.14.0

#### <a name="azmigrate"></a>Az.Migrate
* Az.Migrate GA
* Dimasukkan Initialize-AzMigrateReplicationInfrastructure sebagai cmdlet dalam modul Az.Migrate, dari skrip eksternal yang dijalankan saat ini.
* Membuat beberapa parameter New-AzMigrateServerReplication, kasus New-AzMigrateDiskMapping tidak sensitif.
* Menambahkan dukungan untuk perubahan alat skala, untuk menangani tombol V3 baru.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan null check untuk akun penyimpanan target di pemulihan FileShare.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk penerapan sumber daya Azure dalam bahasa Bicep
* Memperbaiki masalah dengan penyebaran TemplateSpec di 'New-AzTenantDeployment' dan 'New-AzManagementGroupDeployment'
* Menambahkan dukungan untuk parameter '-QueryString' di cmdlet 'Test-Az*Deployments'
* Memperbaiki masalah dengan parameter dinamis saat 'New-Az*Deployments' digunakan dengan '-QueryString'
* Menambahkan dukungan untuk parameter '-TemplateParameterObject' saat menggunakan parameter '-TemplateSpecId' di cmdlet 'New-Az*Deployments'
* Memperbaiki pesan kesalahan yang tidak akurat yang diterima saat mencoba menyebarkan spesifikasi templat yang tidak ada

#### <a name="azstorage"></a>Az.Storage
* Ditingkatkan ke Microsoft.Azure.Management. Storage 19.0.0, untuk mendukung API baru versi 2021-01-01.
* Aturan akses sumber daya yang didukung di NetworkRuleSet
    - 'update-azstorageAccountNetworkruleSet'
    - 'Add-azStorageAccountNetworkrule'
    - 'Remove-azStorageAccountNetworkrule'
* Versi Blob yang didukung dan tipe Tambahkan Blob dalam Kebijakan Manajemen
    - 'Add-AzStorageAccountManagementPolicyaction'
    - 'New-AzStorageAccountManagementPolicyFilter'
    - 'Set-AzStorageAccountManagementPolicy'
* Akun buat/perbarui yang didukung dengan AllowSharedKeyAccess
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Didukung membuat Cakupan Enkripsi dengan RequireInfrastructureEncryption
    - 'New-AzStorageEncryptionScope'
* Blob blok salinan yang didukung secara sinkron, dengan cakupan enkripsi
    - 'Copy-azStorageBlob'
* Memperbaiki masalah yang Get-AzStorageBlobContent menggunakan char pemisah direktori yang salah di Linux dan MacOS [#14234]

#### <a name="azwebsites"></a>Az.Websites
* Memperkenalkan opsi untuk memberikan batas waktu khusus untuk 'Publish-AzWebApp'
* Menambahkan dukungan untuk Lingkungan Layanan Aplikasi
    - 'Lingkungan Layanan Baru-AzApp'
    - 'Remove-AzAppServiceEnvironment'
    - 'Get-AzAppServiceEnvironment'
    - 'New-AzAppServiceEnvironmentInboundServices'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @alunmj, Ejaan kecil, perubahan pemformatan (#14155)
* @chakra146, Perbarui Add-AzLoadBalancerInboundNatPoolConfig.md (#14231)
* Martin Ehrnst (@ehrnst), Memperbaiki kesalahan ketik di cmdlet (#14112)
* Jan David Narkiewicz (@jdnark)
  * Contoh yang digunakan New-AzAks yang merupakan cmdlet lama dan alias untuk New-AzAksCluster. Mengubah contoh untuk menggunakan New-AzAksCluster yang merupakan cmdlet target halaman dokumentasi ini. (#14088)
  * Ketik fox: mengubah SshKeyVaule menjadi SshKeyValue (#14087)
* Ivan Kulezic (@kukislav), Tambahkan contoh konfigurasi pemeliharaan sql mi (#14216)
* @webguynj, Perbarui Set-AzNetworkSecurityRuleConfig.md (#14176)
* Yannick Dils (@yannickdils), Menambahkan cmdline tambahan ke contoh yang menerapkan perubahan pada penyeimbang beban (#14185)

## <a name="550---february-2021"></a>5.5.0 - Februari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Kode CloudError yang dilacak dalam pengecualian
* Acara 'ContextCleared' yang diangkat saat 'Clear-AzContext' dijalankan

#### <a name="azaks"></a>Az.Aks
* Pesan kesalahan yang disempurnakan dari kegagalan cmdlet.
* Penanganan pengecualian yang ditingkatkan untuk menggunakan pengecualian terkait Azure PowerShell.
* Memperbaiki masalah yang tidak dapat digunakan pengguna untuk menggunakan prinsipal layanan yang disediakan untuk membuat klaster Kubernetes. [#13938]

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah pemrosesan 'PSCustomObject' dan 'Array'.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EnableAutomaticUpgrade' ke 'Set-AzVmExtension' dan 'Add-AzVmssExtension'.
* Menghapus Parameter FilterExpression dari dokumentasi cmdlet 'Get-AzVMImage'.
* Menambahkan pesan penghentian ke cmdlet ContainerService:
    - 'Add-AzureRmContainerServiceagentPoolProfileCommand'
    - 'Get-AzContainerService'
    - 'New-AzContainerService'
    - 'New-AzContainerServiceConfig'
    - 'Remove-AzContainerService'
    - 'Remove-azContainerServiceagentPoolProfile'
    - 'Update-AzContainerService'
* Menambahkan parameter '-BurstingEnabled' ke 'New-AzDiskConfig' dan 'New-AzDiskUpdateConfig'
* Menambahkan parameter '-GroupByApplicationId' dan '-GroupByUserAgent' ke cmdlet 'Export-AzLogAnalyticThrottledRequest' dan 'Export-AzLogAnalyticRequestRateByInterval'.
* Menambahkan parameter 'VMParameterSet' yang diatur ke cmdlet 'Get-AzVMExtension'. Menambahkan parameter baru '-VM' ke kumpulan parameter ini.

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
Didukung -EnableNoPublicIP saat membuat ruang kerja Databricks

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan FrontDoorId ke properti
* Menambahkan Pengecualian JSON dan dukungan RequestBodyCheck ke aturan terkelola

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan parameter baru '-EnableComputeIsolation' dan '-ComputeIsolationHostSku' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur isolasi komputasi
* Menambahkan properti 'ComputeIsolationProperties' dan 'ConnectivityEndpoints' di kelas AzureHDInsightCluster.

#### <a name="azkeyvault"></a>Az.KeyVault
* Didukung menentukan jenis kunci dan nama kurva saat mengimpor kunci melalui file BYOK

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk menggantikan nama produk lama 'router virtual' dengan nama baru 'route server' di masa depan.
    - 'New-AzRouteServer'
    - 'Get-AzRouteServer'
    - 'Remove-AzRouteServer'
    - 'Update-AzRouteServer'
    - 'Get-AzRouteServerPeer'
    - 'Add-AzRouteServerPeer'
    - 'Update-AzRouteServerPeer'
    - 'Remove-AzRouteServerPeer'
    - Menambahkan peringatan atribut deprekasi ke cmdlet lama.
* Perbaikan bug di ExpressRouteLink MacSecConfig. Menambahkan properti baru 'SciState' ke 'PSExpressRouteLinkMacSecConfig'
* Daftar format yang diperbarui dan tampilan tabel format untuk Get-AzVirtualNetworkGatewayConnectionIkeSa

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Perubahan yang ditarik yang dibuat di powershell yang meningkatkan batas baris permintaan. Menghapus pernyataan yang salah untuk mendukung paging

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* batas validasi kebijakan yang dimodifikasi sesuai layanan pencadangan.
* Menambahkan Redundansi Zona untuk Vault Layanan Pemulihan.
* Dukungan Pemulihan Situs Azure untuk grup penempatan Kedekatan untuk penyedia VMware ke Azure dan HyperV ke Azure.
* Dukungan Pemulihan Situs Azure untuk availability zone untuk VMware ke Azure dan HyperV ke penyedia Azure.
* Dukungan Azure Site Recovery untuk UseManagedDisk for HyperV to Azure provider

#### <a name="azresources"></a>Az.Resources
* Menghapus jenis utama pada New-AzRoleAssignment dan Set-AzRoleAssignment karena pemetaan saat ini melanggar skenario tertentu

#### <a name="azsql"></a>Az.Sql
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlDatabase', 'Set-AzSqlDatabase', 'New-AzSqlElasticPool' dan 'Set-AzSqlElasticPool'
* Regresi tetap dalam 'Set-AzSqlServerAudit' saat argumen PredicateExpression disediakan

#### <a name="azstorage"></a>Az.Storage
* Pengaturan RoutingPreference yang Didukung di akun Storage buat/perbarui
    - 'New-AzStorageAccount'
    - 'Set-AzStorageAccount'
* Azure yang ditingkatkan. Storage. Gumpalan ke 12.8.0
* Azure yang ditingkatkan. Storage. Files.Shares ke 12.6.0
* Azure yang ditingkatkan. Storage. Files.DataLake ke 12.6.0

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk Mengimpor sertifikat vault utama ke WebApp.

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Perbarui Set-AzEventHub.md (#13921)
* Christoph Bergmeister [MVP] (@bergmeister), Set-AzDataLakeGen2AclRecursive.md - Perbaiki kesalahan ketik (directiry -> directory) (#14082)
* Alexander Schmidt (@devdeer-alex), Tautan rusak tetap ke pedoman kontribusi (#14009)
* @JiangYuchun, Perbarui Get-AzApplicationGatewayAuthenticationCertificate.md (#13972)
* Sebastian Olsen (@Spacebjorn), Perintah contoh yang dikoreksi (#13901)

## <a name="540---january-2021"></a>5.4.0 - Januari 2021
#### <a name="azaccounts"></a>Az.Accounts
* Menunjukkan id permintaan klien yang benar pada pesan debug [#13745]
* Menambahkan tipe pengecualian Azure PowerShell umum
* API penyimpanan yang didukung 2019-06-01

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
* Memperbaiki masalah bahwa 'Get-AzLogicAppTriggerHistory' dan 'Get-AzLogicAppRunAction' hanya mengambil halaman pertama hasil [#9141]

#### <a name="azmonitor"></a>Az.Monitor
* Cmdlet tambahan untuk aturan pengumpulan data:
    - 'Get-AzDataCollectionRule'
    - 'New-AzDataCollectionRule'
    - 'Set-AzDataCollectionRule'
    - 'Update-AzDataCollectionRule'
    - 'Remove-AzDataCollectionRule'
* Cmdlet tambahan untuk asosiasi aturan pengumpulan data
    - 'Get-AzDataCollectionRuleAssociation'
    - 'New-AzDataCollectionRuleAssociation'
    - 'Remove-AzDataCollectionRuleAssociation'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan cmdlet baru untuk CRUD dari VpnGatewayNATRule.
    - 'New-azVpnGatewayNatrule'
    - 'update-azVpnGatewayNatrule'
    - 'Get-azVpnGatewayNatrule'
    - 'Remove-azVpnGatewayNatrule'
* Cmdlet yang diperbarui untuk mengatur NATRule pada sumber daya VpnGateway dan mengaitkannya dengan sumber daya VpnSiteLinkConnection.
    - 'New-AzVpnGateway'
    - 'Update-AzVpnGateway'
    - 'New-AzVpnSiteLinkConnection'
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan ConnectionMode pada Koneksi Gateway Jaringan Virtual.
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Cmdlet 'New-AzFirewallPolicyApplicationRule':
    - Menambahkan parameter TargetUrl
    - Parameter tambahan TerminateTLS
* Menambahkan cmdlet baru untuk Fitur Premium Azure Firewall
    - 'New-AzFirewallPolicyIntrusionDetection'
    - 'New-AzFirewallPolicyIntrusionDetectionBypassTraffic'
    - 'New-AzFirewallPolicyIntrusionDetectionSignatureOverride'
* Cmdlet New-AzFirewallPolicy diperbarui:
    - Menambahkan parameter -SkuTier
    - Menambahkan parameter -Identity
    - Menambahkan parameter -UserAssignedIdentityId
    - Menambahkan parameter -IntrusionDetection
    - Parameter tambahan -TransportSecurityName
    - Parameter tambahan -TransportSecurityKeyVaultSecretId
* Menambahkan cmdlet baru untuk mengambil Asosiasi Keamanan IKE untuk Koneksi Gateway Jaringan Virtual.
    - 'Get-AzVirtualNetworkGatewayConnectionIkeSa'
* Menambahkan beberapa dukungan Otentikasi untuk p2sVpnGateway
    - Diperbarui New-AzVpnServerConfiguration dan Update-AzVpnServerConfiguration untuk memungkinkan beberapa parameter otentikasi diatur.
* Cmdlet 'New-AzVpnGateway' dan 'New-AzP2sVpnGateway':
    - Parameter tambahan EnableRoutingPreferenceInternetFlag

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan fitur Pemulihan Lintas Wilayah.
* Diblokir mendapatkan konfigurasi beban kerja saat item target adalah grup ketersediaan.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk parameter -QueryString di cmdlet New-Az*Deployments

#### <a name="azsql"></a>Az.Sql
* Made 'Start-AzSqlInstanceDatabaseLogReplay' cmdlet sinkron, menambahkan bendera -AsJob

#### <a name="azstorage"></a>Az.Storage
* Perbaiki ContinuationToken tidak pernah null ketika daftar blob dengan -IncludeVersion
    - 'Get-AzStorageBlob'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk sertifikat Terkelola Layanan Aplikasi
    - 'New-AzWebAppCertificate'
    - 'Remove-AzWebAppCertificate'
* Memperbaiki masalah yang menyebabkan Kata Sandi Docker dihapus dari appsetting di 'Set-AzWebApp' dan 'Set-AzWebAppSlot'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Ivan Akcheurov (@ivanakcheurov), Set-AzSecurityWorkspaceSetting.md Pembaruan (#13877)
* @javiermarasco, Perbarui contoh (#13837)
* @jhaprakash26, Perbarui Set-AzVirtualNetwork.md (#13857)
* Michael Holmes (@MichaelHolmesWP), New-AzStorageTableStoredAccessPolicy.md Pembaruan (#13871)
* Michael James (@mikejwhat), Izinkan Get-AzLogicAppTriggerHistory dan Get-AzLogicAppRunAction untuk mengembalikan lebih dari 30 hasil (# 13846)
* @Willem-J-an, Perbaiki bug yang menyebabkan Kata Sandi Docker dihapus dari appsetting di Set-AzWebApp(Slot) (#13866)

## <a name="530---december-2020"></a>5.3.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah bahwa proxy Http tidak dihormati di Windows PowerShell [#13647]
* Log debug yang ditingkatkan dari operasi yang sudah berjalan lama dalam modul yang dihasilkan

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah bahwa parameter 'Start-AzAutomationRunbook' tidak dapat mengonversi string dibungkus PSObject ke string JSON [#13240]
* Lokasi tetap lebih lengkap untuk cmdlet New-AzAutomationUpdateManagementAzureQuery

#### <a name="azcompute"></a>Az.Compute
* Parameter baru 'VM' dalam kumpulan parameter baru 'VMParameterSet' ditambahkan ke cmdlet 'Get-AzVMDscExtensionStatus' dan 'Get-AzVMDscExtension'.

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki masalah yang dapat menyebabkan 'New-AzDatabricksVNetPeering' kembali sebelum sepenuhnya disediakan (https://github.com/Azure/autorest.powershell/issues/610)

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki perintah 'Invoke-AzDataFactoryV2Pipeline' untuk masalah SupportsShouldProcess

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan properti StartVMOnConnect ke hostpool.

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan properti: Fqdn dan EffectiveDiskEncryptionKeyUrl di kelas AzureHDInsightHostInfo.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan parameter baru '-AsPlainText' ke 'Get-AzKeyVaultSecret' untuk langsung mengembalikan rahasia dalam teks biasa [#13630]
* Mendukung pemulihan selektif kunci dari cadangan penuh HSM terkelola [#13526]
* Memperbaiki beberapa masalah kecil [#13583] [#13584]
* Menambahkan objek pengembalian yang hilang dari 'Get-Secret' di modul SecretManagement
* Memperbaiki masalah yang dapat menyebabkan vault dibuat tanpa kebijakan akses default [#13687]

#### <a name="azkusto"></a>Az.Kusto
* Versi API yang diperbarui ke 2020-09-18.

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki masalah dalam menghapus peering dan cmdlet koneksi untuk skenario ExpressRouteCircuit
    - 'Remove-AzExpressRouteCircuitPeeringConfig' dan 'Remove-AzExpressRouteCircuitConnectionConfig'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan dukungan untuk mengembalikan hasil paginated untuk Get-AzPolicyState

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Mengaktifkan fitur softdelete untuk SQL.
* Memperbaiki SQL AG memulihkan dan menghapus pemeriksaan nama kontainer.
* Mengubah format nama kontainer untuk item cadangan Azure Files.
* Menambahkan dukungan fitur CMK untuk vault layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah pengecualian NullRef di 'New-AzureManagedApplication' dan 'Set-AzureManagedApplication'.
* Diperbarui Azure Resource Manager SDK untuk menggunakan DeploymentScripts GA api-version terbaru: 2020-10-01.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Tetap 'add-azServiceFabricnodeType'. Menambahkan jenis node ke klaster kain layanan sebelum membuat set skala mesin virtual.

#### <a name="azsql"></a>Az.Sql
* Deskripsi parameter tetap untuk perintah 'InstanceFailoverGroup'.
* Memperbarui logika di mana schemaName, tableName, dan columnName sedang diekstraksi dari id perintah Klasifikasi Data SQL.
* Bidang Status dan StatusMessage Tetap di bidang 'Get-AzSqlDatabaseImportExportStatus' agar sesuai dengan dokumentasi
* Menambahkan cmdlet audit operasi dukungan Microsoft (DevOps): Get-AzSqlServerMSSupportAudit, Set-AzSqlServerMSSupportAudit, Remove-AzSqlServerMSSupportAudit

#### <a name="azstorage"></a>Az.Storage
* Didukung create/update/get/list EncryptionScope dari akun Storage
    - 'New-AzStorageEncryptionScope'
    - 'Update-AzStorageEncryptionScope'
    - 'Get-AzStorageEncryptionScope'
* Didukung membuat kontainer dan mengunggah blob dengan pengaturan Cakupan Enkripsi
    - 'New-AzRmStorageContainer'
    - 'New-AzStorageContainer'
    - 'Set-AzStorageBlobContent'

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andreas Wolter (@AndreasWolter), menghapus bahasa pemasaran, filter contoh yang lebih baik (#13671)
* Tidjani Belmansour (@BelRarr), Get-AzBillingInvoice.md Pembaruan (#13634)
* David Klempfner (@DavidKlempfner)
  * Kesalahan ejaan tetap (#13677)
  * Memperbarui PSMetricNoDetails.cs (#13676)
* @kilobyte97, bugfix untuk menghapus cmdlet untuk menghapus konfigurasi (#13655)
* @kongou-ae, Perbarui Set-AzFirewall.md (#13727)
* @MasterKuat, Perbaiki swap antara judul dan kode dalam dokumentasi (#13666)
* NickT (@nukeulis), Set-AzContext.md Pembaruan (#13702)
* @PaulHCode, Perbarui Start-AzJitNetworkAccessPolicy.md - Perbaiki Contoh untuk menampilkan cmdlet yang tepat yang ditunjukkan (#13713)
* Ryan Borstelmann (@ryanborMSFT), Dihapus ID Berlangganan (#13715)
* Shashikant Shakya (@shshakya), Set-AzSqlDatabase.md Pembaruan (#13674)
* Sebastian Olsen (@Spacebjorn), Pembaruan Get-AzRecoveryServicesBackupItem.md (#13719)

## <a name="520---december-2020"></a>5.2.0 - Desember 2020
#### <a name="azaccounts"></a>Az.Accounts
* Berhasil mengurai KedaluwarsaPada waktu dari token mentah jika tidak bisa mendapatkan dari pustaka yang mendasarinya
* Pesan peringatan yang ditingkatkan jika Autentikasi interaktif tidak tersedia

#### <a name="azapimanagement"></a>Az.ApiManagement
* [Melanggar perubahan] 'New-AzApiManagementProduct' secara default tidak memiliki batas berlangganan.

#### <a name="azcompute"></a>Az.Compute
* Get-AzVm diedit untuk memfilter dengan '-Nama' sebelum memeriksa throttling karena terlalu banyak sumber daya.
* Cmdlet baru 'Start-AzVmssRollingExtensionUpgrade'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Parameter yang didukung 'Nama' untuk dan nilai dari input pipeline untuk 'Get-AzContainerRegistryUsage' [#13605]
* Pengecualian yang dipoles untuk 'Koneksi-AzContainerRegistry'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.13.0

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Menambahkan dukungan untuk kunci terkelola pelanggan

#### <a name="aziothub"></a>Az.IotHub
* Memperbaiki masalah token SAS.

#### <a name="azkeyvault"></a>Az.KeyVault
* Didukung 'semua' sebagai opsi saat menetapkan kebijakan akses vault utama
* Modul SecretManagement versi baru yang didukung [#13366]
* Mendukung ByteArray, String, PSCredential dan Hashtable untuk 'SecretValue' di SecretManagementModule [#12190]
* [Melanggar perubahan] mendesain ulang permukaan API cmdlet yang terkait dengan HSM terkelola.

#### <a name="azmonitor"></a>Az.Monitor
* Mengubah parameter 'Rule' dari 'New-AzAutoscaleProfile' untuk menerima daftar kosong. [#12903]
* Menambahkan cmdlet baru untuk mendukung pembuatan pengaturan diagnostik yang lebih fleksibel:
    * 'Get-AzDiagnosticSettingCategory'
    * 'New-AzDiagnosticSetting'
    * 'New-AzDiagnosticDetailSetting'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Membuat teks bantuan dan parameter mengatur perubahan nama ke cmdlet 'Restore-AzRecoveryServicesBackupItem'.

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan parameter '-Tag' ke 'Set-AzTemplateSpec' dan 'New-AzTemplateSpec'
* Menambahkan dukungan tampilan Tag ke formatter default untuk Spesifikasi Templat

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan contoh ke 'Set-AzServiceFabricSetting' dengan SettingsSectionDescription param
* Cmdlet terkait aplikasi yang diperbarui untuk memanggil dukungan itu hanya untuk sumber daya yang digunakan ARM
* Ditandai untuk deprecation cluster cert cmdlets 'Add-AzureRmServiceFabricClusterCertificate' dan 'Remove-AzureRmServiceFabricClusterCertificate'

#### <a name="azsql"></a>Az.Sql
* Menambahkan SecondaryType ke yang berikut:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
    - 'New-AzSqlDatabaseSecondary'
* Menambahkan HighAvailabilityReplicaCount ke yang berikut:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'
* Made ReadReplicaCount alias HighAvailabilityReplicaCount sebagai berikut:
    - 'New-AzSqlDatabase'
    - 'Set-AzSqlDatabase'

#### <a name="azstorage"></a>Az.Storage
* Upload yang didukung Azure File ukuran hingga 4 TiB
    - 'Set-AzStorageFileContent'
* Azure yang ditingkatkan. Storage. Gumpalan ke 12.7.0
* Azure yang ditingkatkan. Storage. Files.Shares ke 12.5.0
* Azure yang ditingkatkan. Storage. Files.DataLake ke 12.5.0

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan fitur kebijakan tiering Sinkronisasi dengan kebijakan unduhan dan mode cache lokal

#### <a name="azwebsites"></a>Az.Websites
* Mencegah aturan pembatasan akses duplikat

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Andrew Dawson (@dawsonar802), Perbarui Get-AzKeyVaultCertificate.md - Dapatkan sertifikat dan simpan sebagai bagian pfx untuk bekerja dengan PowerShell Core (#13557)
* @iviark, Api Kesehatan Powershell BYOK Updates (#13518)
* John Duckmanton (@johnduckmanton), Ejaan yang benar dari TagPatchOperation (#13508)
* Michael James (@mikejwhat)
  * Get-AzLogicAppRunHistory Membantu Merapikan (#13513)
* Richard de Zwart (@mountain65)
  * Perbarui Update-AzAppConfigurationStore.md (#13485)
  * Pembaruan New-AzCosmosDBAccount.md (#13490)
* @SteppingRazor, New-AzApiManagementProduct: Ubah LanggananMenyapan nilai default parameter menjadi Tidak Ada (#13457)
* Steve Burkett (@SteveBurkettNZ), Perbaiki Typo untuk Parameter WorkspaceResourceId misalnya (#13589)

## <a name="510---november-2020"></a>5.1.0 - November 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah yang tenantid mungkin tidak dihormati jika menggunakan 'Koneksi-AzAccount -DeviceCode'[#13477]
* Menambahkan cmdlet baru 'Get-AzAccessToken'
* Memperbaiki masalah yang terjadi kesalahan jika jalur profil pengguna tidak dapat diakses
* Memperbaiki masalah yang menyebabkan kesalahan Write-Object selama Connect-AzAccount [#13419]
* Menambahkan parameter 'ContainerRegistryEndpointSuffix' ke: 'Add-AzEnvironment', 'Set-AzEnvironment'
* Mendukung mengganggu login dengan menekan <kbd>CTRLC</kbd>+<kbd></kbd>
* Memperbaiki masalah yang menyebabkan 'Koneksi-AzAccount -KeyVaultAccessToken' tidak berfungsi [#13127]
* Referensi null tetap dan kasus metode tidak sensitif dalam 'Invoke-AzRestMethod'

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah yang tidak dapat digunakan pengguna untuk menggunakan prinsipal layanan untuk membuat klaster Kubernetes baru. [#13012]

#### <a name="azappconfiguration"></a>Az.AppConfiguration
* Ketersediaan umum modul 'Az.AppConfiguration'

#### <a name="azdatafactory"></a>Az.DataFactory
* Pesan kesalahan yang ditingkatkan dari perintah 'New-AzDataFactoryV2LinkedServiceEncryptedCredential'

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* SDK pesawat data ADLS yang diperbarui ke 1.2.4-alpha. Perubahan:https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-124-alpha

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Menambahkan cmdlet Paket MSIX baru dan cmdlet Aplikasi yang diperbarui.

#### <a name="azeventhub"></a>Az.EventHub
* Perintah Klaster Tetap untuk klaster EventHub tanpa tag
* Teks bantuan yang diperbarui untuk perintah PartnerNamespace of AzEventHubGeoDRConfiguration

#### <a name="azhdinsight"></a>Az.HDInsight
* Tambahkan parameter 'ResourceProviderConnection' dan 'PrivateLink' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur tautan keluar dan pribadi relay
* Tambahkan parameter 'AmbariDatabase' ke cmdlet 'New-AzHDInsightCluster' untuk mendukung fitur database kustom Ambari
* Tambahkan nilai terima 'AmbariDatabase' ke parameter 'MetastoreType' dari cmdlet 'Add-AzHDInsightMetastore'

#### <a name="aziothub"></a>Az.IotHub
* Tag yang diizinkan di IoT Hub membuat cmdlet.

#### <a name="azkeyvault"></a>Az.KeyVault
* Tag vault kunci pembaruan yang didukung

#### <a name="azlogicapp"></a>Az.LogicApp
* Diperbaiki untuk Get-AzLogicAppRunHistory hanya mengambil halaman pertama hasil

#### <a name="aznetwork"></a>Az.Network
* Diperbarui di bawah cmdlet
    - 'New-AzLoadBalancerFrontendIpConfigCommand', 'Set-AzLoadBalancerFrontendIpConfigCommand', 'Add-AzLoadBalancerFrontendIpConfigCommand':
        - Menambahkan PublicIpAddressPrefix properti
        - Menambahkan PublicIpAddressPrefixId properti
* Menambahkan properti baru ke cmdlet berikut untuk memungkinkan penyeimbangan beban global
    - 'New-AzLoadBalancer':
        - Menambahkan properti Sku Tier
    - 'New-AzPuplicIpAddress':
        - Menambahkan properti Sku Tier
    - 'New-AzPublicIpPrefix':
        - Menambahkan properti Sku Tier
    - 'New-AzLoadBalancerBackendAddressConfig':
        - Menambahkan LoadBalancerFrontendIPConfigurationId properti
* Perencanaan terbaru untuk mendepresiasi peringatan untuk cmdlet berikut -'New-AzVirtualHubRoute' -'New-AzVirtualHubRouteTable' -'Add-AzVirtualHubRoute' -'Add-AzVirtualHubRouteTable' -'Get-AzVirtualHubRouteTable' -'Remove-AzVirtualHubRouteTable'
* Menambahkan perencanaan untuk membatalkan peringatan pada argumen 'RouteTable' untuk cmdlet berikut -'New-AzVirtualHub' -'Set-AzVirtualHub' -'Update-AzVirtualHub'
* Membuat argumen '-MinScaleUnits' dan '-MaxScaleUnits' opsional di 'Set-AzExpressRouteGateway'
* Menambahkan cmdlet baru untuk mendukung Profil Otentikasi Dan SSL Bersama di Application Gateway
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
* Menentukan kebijakan BackupTime ada di UTC.
* Memodifikasi peringatan perubahan yang melanggar di cmdlet Get-AzRecoveryServicesBackupJobDetails.
* Memperbarui teks bantuan skrip sampel untuk cmdlet Set-AzRecoveryServicesBackupProtectionPolicy.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah di mana What-If menampilkan dua cakupan grup sumber daya dengan casing yang berbeda
* Memperbarui 'Export-AzResourceGroup' untuk menggunakan SDK.
* Menambahkan info budaya untuk mengurai metode

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah di mana Set-AzSqlDatabaseAudit tidak mendukung database Hyperscale dan edisi database tidak dapat ditentukan
* Menambahkan MaintenanceConfigurationId ke 'New-AzSqlInstance' dan 'Set-AzSqlInstance'
* Memperbaiki bug di GetAzureSqlDatabaseReplicationLink.cs di mana parameter PartnerServerName sedang diperiksa berdasarkan nilai, bukan kunci

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk fitur pembatasan akses baru: ServiceTag, multi-ip, dan http-header

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* John Q. Martin (@johnmart82), Menambahkan informasi prasyarat firewall (#13385)
* Manikandan Duraisamy (@madurais-msft), Mengoreksi argumen PublicSubnetName (#13417)
* @mahortas, Perbarui untuk nilai parameter -HostNames (#13349)
* @MariachiForHire, ditambahkan didukung TrafficAnalytics Nilaiinterval (#13304)
* Michael James (@mikejwhat), Izinkan Get-AzLogicAppRunHistory untuk mengembalikan lebih dari 30 entri (#13393)
* Shashikant Shakya (@shshakya), Restore-AzSqlInstanceDatabase.md Pembaruan (#13404)

## <a name="500---october-2020"></a>5.0.0 - Oktober 2020
#### <a name="azaccounts"></a>Az.Accounts
* [Melanggar Perubahan] Menghapus 'Get-AzProfile' dan 'Select-AzProfile'
* Mengganti Azure Directory Authentication Library dengan Microsoft Authentication Library(MSAL)

#### <a name="azaks"></a>Az.Aks
* [Melanggar Perubahan] Menghapus parameter alias 'ClientIdAndSecret' di 'New-AzAksCluster' dan 'Set-AzAksCluster'.
* [Melanggar Perubahan] Mengubah nilai default 'NodeVmSetType' di 'New-AzAksCluster' dari 'AvailabilitySet' menjadi 'VirtualMachineScaleSets'.
* [Melanggar Perubahan] Mengubah nilai default 'NetworkPlugin' di 'New-AzAksCluster' dari 'None' menjadi 'azure'.
* [Melanggar Perubahan] Menghapus parameter 'NodeOsType' di 'New-AzAksCluster' karena hanya mendukung satu nilai Linux.

#### <a name="azbilling"></a>Az.Billing
* Menambahkan cmdlet 'Get-AzBillingAccount'
* Ditambahkan cmdlet 'Get-AzBillingProfile'
* Menambahkan cmdlet 'Get-AzInvoiceSection'
* Menambahkan parameter baru di cmdlet 'Get-AzBillingInvoice'
* Properti dihapus UnduhUrlExpiry, Type, BillingPeriodNames dari respons cmdlet Get-AzBillingInvoice

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet untuk mendukung fungsionalitas tautan multi-asal dan pribadi

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* SDK yang diperbarui ke pratinjau 7.4.0.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-VmssId' ke 'New-AzVm'
* Menambahkan parameter 'PlatformFaultDomainCount' ke cmdlet 'New-AzVmss'.
* Cmdlet baru 'Get-AzDiskEncryptionSetAssociatedResource'
* Menambahkan parameter opsional 'Tier' dan 'LogicalSectorSize' ke cmdlet New-AzDiskConfig.
* Menambahkan parameter opsional 'Tier', 'MaxSharesCount', 'DiskIOPSReadOnly', dan 'DiskMBpsReadOnly' ke cmdlet 'New-AzDiskUpdateConfig'.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* [Melanggar Perubahan] Memperbarui versi API ke 2019-05-01
* [Melanggar Perubahan] Menghapus SKU 'Classic' dan parameter 'StorageAccountName' dari 'New-AzContainerRegistry'
* Menambahkan cmdlet Baru: 'Koneksi-AzContainerRegistry', 'Import-AzContainerRegistry', 'Get-AzContainerRegistryUsage', 'New-AzContainerRegistryNetworkRule', 'Set-AzContainerRegistryNetworkRule'
* Menambahkan parameter baru 'NetworkRuleSet' ke 'Update-AzContainerRegistry'

#### <a name="azdatabricks"></a>Az.Databricks
* Memperbaiki bug yang dapat menyebabkan pembaruan ruang kerja databricks tanpa `-EncryptionKeyVersion` gagal.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.12.0
* Memperbarui versi SDK klien enkripsi ADF ke 4.14.7587.7
* Menambahkan perintah 'Stop-AzDataFactoryV2TriggerRun' dan 'Invoke-AzDataFactoryV2TriggerRun'

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Memerlukan properti Lokasi untuk membuat objek lengan tingkat atas.
        * Dibuat `ApplicationGroupType` diperlukan untuk `New-AzWvdApplicationGroup`.
        * Dibuat `HostPoolArmPath` diperlukan untuk `New-AzWvdApplicationGroup`.
        * Ditambahkan `PreferredAppGroupType` untuk `New-AzWvdHostPool`.

#### <a name="azfunctions"></a>Az.Functions
* [Melanggar Perubahan] Menghapus parameter switch 'IncludeSlot' dari semua kecuali satu set parameter 'Get-AzFunctionApp'. Cmdlet sekarang mendukung pengambilan slot penyebaran dalam hasil ketika '-IncludeSlot' ditentukan.
* Diperbarui 'New-AzFunctionApp':
  - Fixed -DisableApplicationInsights sehingga tidak ada proyek wawasan aplikasi yang dibuat saat opsi ini ditentukan. [#12728]
  - [Melanggar Perubahan] Menghapus dukungan untuk membuat aplikasi fungsi PowerShell 6.2.
  - [Melanggar Perubahan] Mengubah versi runtime default di Functions versi 3 pada Windows untuk aplikasi fungsi PowerShell dari 6.2 ke 7.0 ketika parameter RuntimeVersion tidak ditentukan.
  - [Melanggar Perubahan] Mengubah versi runtime default di Functions versi 3 pada Windows dan Linux untuk aplikasi fungsi Node dari 10 ke 12 ketika parameter RuntimeVersion tidak ditentukan.
  - [Melanggar Perubahan] Mengubah versi runtime default di Functions versi 3 di aplikasi fungsi Linux untuk Python dari 3.7 ke 3.8 ketika parameter RuntimeVersion tidak ditentukan.

#### <a name="azhdinsight"></a>Az.HDInsight
 * Untuk cmdlet New-AzHDInsightCluster:
     - Parameter yang diganti 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
     - Parameter yang diganti 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
     - Parameter yang diganti 'DefaultStorageAccountType' dengan 'StorageAccountType'
     - Parameter yang dihapus 'PublicNetworkAccessType'
     - Parameter dihapus 'OutboundPublicNetworkAccessType'
     - Menambahkan parameter baru: 'StorageFileSystem' dan 'StorageAccountManagedIdentity' untuk mendukung ADLSGen2
     - Menambahkan parameter baru 'EnableIDBroker' untuk Mendukung Broker ID HDInsight
     - Menambahkan parameter baru: 'KafkaClientGroupId', 'KafkaClientGroupName' dan 'KafkaManagementNodeSize' untuk mendukung Kafka Rest Proxy
 * Untuk cmdlet New-AzHDInsightClusterConfig:
     - Parameter yang diganti 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
     - Parameter yang diganti 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
     - Parameter yang diganti 'DefaultStorageAccountType' dengan 'StorageAccountType'
     - Parameter yang dihapus 'PublicNetworkAccessType'
     - Parameter dihapus 'OutboundPublicNetworkAccessType'
* Untuk cmdlet Set-AzHDInsightDefaultStorage:
    - Parameter yang diganti 'StorageAccountName' dengan 'StorageAccountResourceId'
* Untuk cmdlet Add-AzHDInsightSecurityProfile:
    - Parameter yang diganti 'Domain' dengan 'DomainResourceId'
    - Menghapus persyaratan wajib untuk parameter 'OrganizationalUnitDN'

#### <a name="azkeyvault"></a>Az.KeyVault
* [Melanggar Perubahan] Parameter yang tidak digunakan lagi DisableSoftDelete di 'New-AzKeyVault' dan EnableSoftDelete di 'Update-AzKeyVault'
* [Melanggar Perubahan] Atribut dihapus SecretValueText untuk menghindari menampilkan SecretValue secara langsung [#12266]
* Jenis sumber daya baru yang didukung: HSM terkelola
    - CRUD HSM dan cmdlet yang dikelola untuk mengoperasikan kunci pada HSM yang dikelola
    - Pencadangan/pemulihan HSM penuh, pembuatan kunci AES, pencadangan/pemulihan domain keamanan, RBAC

#### <a name="azmanagedservices"></a>Az.ManagedServices
* [Melanggar Perubahan] Konvensi penamaan parameter yang diperbarui dan contoh terkait

#### <a name="aznetwork"></a>Az.Network
* [Melanggar Perubahan] Parameter dihapus 'HostedSubnet' dan menambahkan 'Subnet' sebagai gantinya
* Menambahkan cmdlet baru untuk Rute Peer Router Virtual
    - 'Get-AzVirtualRouterPeerLearnedRoute'
    - 'Get-AzVirtualRouterPeerAdvertisedRoute'
* Cmdlet New-AzFirewall diperbarui:
    - Menambahkan parameter '-SkuTier'
    - Menambahkan parameter '-SkuName' dan menjadikan Sku sebagai Alias untuk ini
    - Parameter dihapus '-Sku'
* [Melanggar Perubahan] Membuat argumen 'Connectionlink' wajib di 'Start-AzVpnConnectionPacketCapture' dan 'Stop-AzVpnConnectionPacketCapture'
* [Melanggar Perubahan] Diperbarui 'New-AzNetworkWatcherConnectionMonitorEndPointObject' untuk menghapus parameter '-Filter'
* [Melanggar Perubahan] Diganti cmdlet 'New-AzNetworkWatcherConnectionMonitorEndpointFilterItemObject' dengan cmdlet 'New-AzNetworkWatcherConnectionMonitorEndpointScopeItemObject'
* Cmdlet 'New-AzNetworkWatcherConnectionMonitorEndPointObject':
    - Menambahkan parameter '-Type'
    - Menambahkan parameter '-CoverageLevel'
    - Menambahkan parameter '-Scope'
* Diperbarui 'New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject' cmdlet dengan parameter baru '-DestinationPortBehavior'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Pemulihan Beban Kerja untuk izin kontributor.
* Menambahkan kumpulan parameter dan validasi baru untuk cmdlet Restore-AzRecoveryServicesBackupItem.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki penguraian bug
* Templat ARM yang diperbarui What-If cmdlet untuk menghapus pesan pratinjau dari hasil
* Memperbaiki masalah di mana cmdlet penyebaran template macet jika '-WhatIf' diatur pada cakupan yang lebih tinggi [#13038]
* Memperbaiki masalah di mana cmdlet penyebaran template tidak menyimpan kasus untuk parameter template
* Menambahkan versi API default yang akan digunakan dalam cmdlet 'Export-AzResourceGroup'
* Menambahkan cmdlet untuk Spesifikasi Template ('Get-AzTemplateSpec', 'Set-AzTemplateSpec', 'New-AzTemplateSpec', 'Remove-AzTemplateSpec', 'Export-AzTemplateSpec')
* Menambahkan dukungan untuk menerapkan Spesifikasi Template menggunakan cmdlet penyebaran yang ada (melalui parameter -TemplateSpecId baru)
* Diperbarui 'Get-AzResourceGroupDeploymentOperation' untuk menggunakan SDK.
* Menghapus parameter '-ApiVersion' dari cmdlet '*-AzDeployment'.

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah di mana New-AzSqlDatabaseExport gagal jika networkIsolation tidak ditentukan [#13097]
* Memperbaiki masalah di mana New-AzSqlDatabaseExport dan New-AzSqlDatabaseImport tidak mengembalikan OperationStatusLink di objek hasil [#13097]
* Perbarui URL Azure Paired Regions dalam Peringatan Redundansi Storage Cadangan

#### <a name="azstorage"></a>Az.Storage
* Menghapus properti usang RestorePolicy.LastEnabledTime
    - 'Enable-azstorageblobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Get-AzStorageBlobServiceProperty'
    - 'Update-AzStorageBlobServiceProperty'
* Ubah Jenis Hari SetelahModifikasiGreaterThan dari int ke int?
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyaction'
    - 'New-AzStorageAccountManagementPolicyrule'
* Berbagi file buat/perbarui yang didukung dengan tingkat akses
    - 'New-AzRmStorageShare'
    - 'Update-AzRmstorageShare'
* Set/update/remove Acl yang didukung secara rekursif pada item Datalake Gen2
    -  'Set-AzDataLakeGen2AclRecursive'
    -  'Update-AzDataLakeGen2AclRecursive'
    -  'Remove-AzDataLakeGen2AclRecursive'
* Kebijakan akses Kontainer yang Didukung dengan izin baru x,t
    -  'New-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Mengubah output cmdlet kebijakan akses kontainer get/set, dengan mengubah jenis Izin properti anak dari enum ke String
    -  'Get-AzStorageContainerStoredAccessPolicy'
    -  'Set-AzStorageContainerStoredAccessPolicy'
* Memperbaiki masalah skrip sampel kebijakan manajemen set dengan json
    -  'Set-AzStorageAccountManagementPolicy'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk tingkat harga V3 Premium
* Memperbarui Sdk WebSites ke 3.1.0

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* @atul-ram, Perbarui Get-AzDelegation.md (#13176)
* @dineshreddy007, Dapatkan Peran Aplikasi yang ditetapkan dengan benar jika terjadi pendaftaran Stack HCI menggunakan token WAC. (#13249)
* @kongou-ae, Perbarui New-AzOffice365PolicyProperty.md (#13217)
* Lohith Chowdary Chilukuri (@Lochiluk), Pembaruan Set-AzApplicationGateway.md (#13150)
* Matthew Burleigh (@mburleigh)
  * Menambahkan tautan ke cmdlet PowerShell yang dirujuk dalam dokumen (#13203)
  * Menambahkan tautan ke cmdlet PowerShell yang dirujuk dalam dokumen (#13190)
  * Menambahkan tautan ke cmdlet PowerShell yang dirujuk dalam dokumen (#13189)
  * menambahkan tautan ke cmdlet yang direferensikan (#13137)
  * Menambahkan tautan ke cmdlet PowerShell yang dirujuk dalam dokumen (#13204)
  * Menambahkan tautan ke cmdlet PowerShell yang dirujuk dalam dokumen (#13205)

## <a name="480---october-2020"></a>4.8.0 - Oktober 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah parse DateTime di pustaka umum [#13045]

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Ditambahkan cmdlet 'New-AzCognitiveServicesAccountApiProperty'.
* Parameter 'ApiProperty' yang didukung untuk 'New-AzCognitiveServicesAccount' dan 'Set-AzCognitiveServicesAccount'

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah di 'Update-ASRRecoveryPlan' dengan mengisi FailoverTypes
* Menambahkan parameter opsional '-Top' dan '-OrderBy' ke cmdlet 'Get-AzVmImage'.

#### <a name="azdatabricks"></a>Az.Databricks
* Ketersediaan umum modul 'Az.Databricks'
* Menambahkan dukungan untuk peering jaringan virtual

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki kesalahan ketik dalam pesan output

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter switch opsional 'TrustedServiceAccessEnabled' ke cmdlet 'Set-AzEventHubNetworkRuleSet'

#### <a name="azhdinsight"></a>Az.HDInsight
* Menambahkan pesan peringatan untuk perencanaan untuk mendepresiasi parameter 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType'
* Menambahkan pesan peringatan untuk perencanaan mengganti parameter 'DefaultStorageAccountName' dengan 'StorageAccountResourceId'
* Menambahkan pesan peringatan untuk perencanaan mengganti parameter 'DefaultStorageAccountKey' dengan 'StorageAccountKey'
* Menambahkan pesan peringatan untuk perencanaan mengganti parameter 'DefaultStorageAccountType' dengan 'StorageAccountType'
* Menambahkan pesan peringatan untuk perencanaan mengganti parameter 'DefaultStorageContainer' dengan 'StorageContainer'
* Menambahkan pesan peringatan untuk perencanaan mengganti parameter 'DefaultStorageRootPath' dengan 'StorageRootPath'

#### <a name="aziothub"></a>Az.IotHub
* Sdk perangkat yang diperbarui.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memberikan tanggal detail penghapusan properti SecretValueText

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Peringatan perubahan yang diperbarui pada cmdlet penetapan dan definisi layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug bahwa pesan peringatan tidak dapat ditekan. [#12889]
* Mendukung parameter 'SkipMetricValidation' dalam kriteria aturan peringatan. Memungkinkan pembuatan aturan peringatan pada metrik kustom yang belum dipancarkan, dengan menyebabkan validasi metrik dilewati.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan Kebijakan Office365 ke Sumber Daya VPNSite
    - 'New-AzO365PolicyProperty'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan validasi nama kontainer untuk pencadangan beban kerja.

#### <a name="azrediscache"></a>Az.RedisCache
* Membuat cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache' tidak gagal karena masalah izin terkait dengan pendaftaran Microsoft.Cache RP

#### <a name="azsql"></a>Az.Sql
* Menambahkan BackupStorageRedundancy ke yang berikut:
    - 'Restore-AzureRmSqlDatabase'
    - 'New-AzSqlDatabaseCopy'
    - 'New-AzSqlDatabaseSecondary'
* Sensitivitas kasus yang dihapus untuk parameter BackupStorageRedundancy untuk semua referensi DB SQL
* Nama pesan peringatan BackupStorageRedundancy yang Diperbarui

#### <a name="azstorage"></a>Az.Storage
* Didukung mengaktifkan /menonaktifkan / mendapatkan berbagi properti penghapusan lunak pada file Layanan akun Storage
    - 'Update-AzStorageFileServiceProperty'
    - 'Get-AzStorageFileServiceProperty'
* Berbagi file daftar yang didukung termasuk yang dihapus dari akun Storage, dan Dapatkan penggunaan berbagi file tunggal
    - 'Get-AzRmStorageShare'
* Memulihkan berbagi file yang dihapus secara didukung
    - 'Restore-AzRmStorageShare'
* Mengubah cmdlet untuk memodifikasi properti layanan blob, tidak akan mendapatkan properti asli dari server, tetapi hanya mengatur properti yang dimodifikasi ke server.
    - 'Enable-AzStorageBlobDeleteRetentionPolicy'
    - 'Disable-AzStorageBlobDeleteRetentionPolicy'
    - 'Enable-azstorageblobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'Update-AzStorageBlobServiceProperty'
* Memperbaiki masalah bantuan untuk parameter New-AzStorageAccount -Jenis nilai default [#12189]
* Memperbaiki masalah dengan menambahkan contoh untuk memperlihatkan cara mengatur ContentType yang benar dalam upload blob [#12989]

## <a name="470---september-2020"></a>4.7.0 - September 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memformat pesan perubahan berbuka yang akan datang
* Diperbarui Azure.Core ke 1.4.1

#### <a name="azaks"></a>Az.Aks
* Menambahkan logika validasi parameter sisi klien untuk 'New-AzAksCluster', 'Set-AzAksCluster' dan 'New-AzAksNodePool'. [#12372]
* Menambahkan dukungan untuk add-on di 'New-AzAksCluster'. [#11239]
* Menambahkan cmdlet 'Enable-AzAksAddOn' dan 'Disable-AzAksAddOn' untuk add-on. [#11239]
* Menambahkan parameter 'GenerateSshKey' untuk 'New-AzAksCluster'. [#12371]
* Memperbarui versi API ke 2020-06-01.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menunjukkan persyaratan hukum tambahan untuk API tertentu.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter opsional '-EncryptionType' ke 'New-AzVmDiskEncryptionSetConfig'
* Cmdlet baru untuk jenis sumber daya baru: DiskAccess 'Get-AzDiskAccess', 'New-AzDiskAccess', 'Get-AzDiskAccess'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzSnapshotConfig'
* Menambahkan parameter opsional '-DiskAccessId' dan '-NetworkAccessPolicy' ke 'New-AzDiskConfig'
* Menambahkan properti 'PatchStatus' ke Tampilan Instans VirtualMachine
* Menambahkan properti 'VMHealth' ke tampilan instans mesin virtual, yang merupakan objek yang dikembalikan saat 'Get-AzVm' dipanggil dengan '-Status'
* Menambahkan bidang 'AssignedHost' ke tampilan instans 'Get-AzVM' dan 'Get-AzVmss'. Bidang ini menampilkan id sumber daya instans mesin virtual
* Menambahkan parameter opsional '-SupportAutomaticPlacement' ke 'New-AzHostGroup'
* Menambahkan parameter '-HostGroupId' ke 'New-AzVm' dan 'New-AzVmss'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.11.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet Cluster baru - 'New-AzEventHubCluster', 'Set-AzEventHubCluster', 'Get-AzEventHubCluster', 'Remove-AzEventHubCluster', 'Get-AzEventHubClustersAvailableRegions'.
* Diperbaiki untuk masalah #10722: Perbaiki untuk menetapkan hanya 'Dengarkan' Hak OtorisasiRule.

#### <a name="azfunctions"></a>Az.Functions
* Menghapus kemampuan untuk membuat Fungsi v2 di wilayah yang tidak mendukungnya.
* PowerShell yang tidak digunakan lagi 6.2. Menambahkan peringatan saat pengguna membuat aplikasi fungsi PowerShell 6.2 yang menyarankan mereka untuk membuat aplikasi fungsi PowerShell 7.0 sebagai gantinya.

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan klaster dengan konfigurasi Skala Otomatis
    - Tambahkan parameter baru 'AutoscaleConfiguration' ke cmdlet 'New-AzHDInsightCluster'
* Konfigurasi Skala Otomatis klaster operasi yang didukung
    - Tambahkan cmdlet baru 'Get-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'Set-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'Remove-AzHDInsihgtClusterAutoscaleConfiguration'
    - Tambahkan cmdlet baru 'New-AzHDInsihgtClusterAutoscaleScheduleCondition'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk otorisasi RBAC [#10557]
* Penanganan kesalahan yang ditingkatkan di 'Set-AzKeyVaultAccessPolicy' [#4007]

#### <a name="azkusto"></a>Az.Kusto
* Ketersediaan umum modul 'Az.Kusto'

#### <a name="aznetwork"></a>Az.Network
* [Melanggar Perubahan] Diperbarui di bawah cmdlet untuk menyelaraskan router virtual sumber daya dan hub virtual
    - 'New-AzVirtualRouter':
        - Menambahkan parameter -HostedSubnet untuk mendukung sumber daya anak konfigurasi IP
        - dihapus -HostedGateway dan -HostedGatewayId
    - 'Get-AzVirtualRouter':
        - Menambahkan kumpulan parameter tingkat langganan
    - 'Remove-AzVirtualRouter'
    - 'Add-AzVirtualRouterPeer'
    - 'Get-AzVirtualRouterPeer'
    - 'Remove-AzVirtualRouterPeer'
* Menambahkan cmdlet baru untuk Azure Express Route Port
    - 'New-AzExpressRoutePortLOA'
* Menambahkan properti RemoteBgpCommunities ke VirtualNetwork Peering Resource
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.
* Menambahkan VpnGatewayIpConfigurations ke output 'Get-AzVpnGateway'
* Bug tetap untuk 'Set-AzApplicationGatewaySslCertificate' [#9488]
* Menambahkan parameter 'AllowActiveFTP' ke 'AzureFirewall'
* Diperbarui di bawah perintah untuk fitur: Aktifkan set /hapus keamanan internet di VirtualWan P2SVpnGateway.
- Diperbarui 'New-AzP2sVpnGateway': Menambahkan parameter switch opsional 'EnableInternetSecurityFlag' bagi pelanggan untuk menetapkan true untuk mengaktifkan keamanan internet di P2SVpnGateway, yang akan diterapkan untuk klien Point to site.
- Diperbarui 'Update-AzP2sVpnGateway': Menambahkan parameter switch opsional 'EnableInternetSecurityFlag' atau 'DisableInternetSecurityFlag' bagi pelanggan untuk mengatur true/false untuk mengaktifkan/menonaktifkan keamanan internet di P2SVpnGateway, yang akan diterapkan untuk klien Point to site.
* Menambahkan cmdlet baru 'Reset-AzP2sVpnGateway' bagi pelanggan untuk mengatur ulang / me-reboot VirtualWan P2SVpnGateway mereka untuk pemecahan masalah.
* Menambahkan cmdlet baru 'Reset-AzVpnGateway' bagi pelanggan untuk mengatur ulang / me-reboot VirtualWan VpnGateway mereka untuk pemecahan masalah.
* Diperbarui 'Set-AzVirtualNetworkSubnetConfig'
    - Atur properti NSG dan Tabel Rute subnet ke null jika secara eksplisit diatur dalam parameter [#1548][#9718]

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Memperbaiki Item Cadangan Hapus Status untuk beban kerja.

#### <a name="azresources"></a>Az.Resources
* Menambahkan pemeriksaan yang hilang untuk Set-AzRoleAssignment
* Menambahkan atribut perubahan putus ke parameter 'SubscriptionId' dari 'Get-AzResourceGroupDeploymentOperation'
* Templat ARM yang diperbarui What-If cmdlet untuk menampilkan perubahan sumber daya 'Abaikan' terakhir
* Memperbaiki masalah serialisasi parameter aman dan array untuk cmdlet penyebaran [#12773]

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan cmdlet baru untuk klaster terkelola dan tipe node:
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
    - 'Add-AzServiceFabricManagednodeTypevMExtension'
    - 'Add-azServiceFabricManagednodeTypevMSecret'
    - 'Remove-AzServiceFabricManagedNodeTypeVMExtension'
    - 'Restart-AzServiceFabricManagedNodeTyp'
* Ditingkatkan Service Fabric SDK ke versi 1.2.0 yang menggunakan penyedia sumber daya kain layanan api-versi 2020-03-01 untuk model saat ini dan pratinjau 2020-01-01 untuk klaster terkelola.

#### <a name="azsql"></a>Az.Sql
* Menambahkan BackupStorageRedundancy ke 'New-AzSqlInstance' dan 'Get-AzSqlInstance'
* Menambahkan cmdlet 'Get-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menambahkan cmdlet 'Enable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Menambahkan parameter Force ke 'New-AzSqlInstance'
* Cmdlet yang ditambahkan untuk layanan Replay Log Database Terkelola
    - 'Start-AzSqlInstanceDatabaseLogReplay'
    - 'Get-AzSqlInstanceDatabaseLogReplay'
    - 'Complete-AzSqlInstanceDatabaseLogReplay'
    - 'Stop-AzSqlInstanceDatabaseLogReplay'
* Menambahkan cmdlet 'Get-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Menambahkan cmdlet 'Enable-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Menambahkan cmdlet 'Disable-AzSqlInstanceActiveDirectoryOnlyAuthentication'
* Cmdlet yang diperbarui 'New-AzSqlDatabaseImport' dan 'New-AzSqlDatabaseExport' untuk mendukung fungsionalitas isolasi jaringan
* Menambahkan cmdlet 'New-AzSqlDatabaseImportExisting'
* Cmdlet Database yang diperbarui untuk mendukung spesifikasi jenis penyimpanan cadangan
* Menambahkan parameter Force ke 'New-AzSqlDatabase'
* Peringatan tambahan untuk konfigurasi BackupStorageRedundancy di wilayah tertentu di 'New-AzSqlDatabase'
* Cmdlet ActiveDirectoryOnlyAuthentication yang diperbarui untuk server dan instans untuk menyertakan ResourceId dan InputObject

#### <a name="azstorage"></a>Az.Storage
* Blob upload tetap gagal dengan mengupgrade ke Microsoft.Azure. Storage. DataMovement 2.0.0 [#12220]
* Pemulihan titik waktu yang didukung
    - 'Enable-azstorageblobRestorePolicy'
    - 'Disable-AzStorageBlobRestorePolicy'
    - 'New-AzStorageBlobRangeToRestore'
    - 'Restore-AzStorageBlobRange'
* Didukung dapatkan status pemulihan blob akun Storage dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeBlobRestoreStatus
    - 'Get-AzureRMStorageAccount'
* Menambahkan pesan peringatan perubahan yang melanggar untuk perubahan output cmdlet mendatang
    - 'Get-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageContainerStoredAccessPolicy'
    - 'Set-AzStorageAccountManagementPolicy'
    - 'Get-AzStorageAccountManagementPolicy'
    - 'Add-AzStorageAccountManagementPolicyaction'
    - 'New-AzStorageAccountManagementPolicyrule'
* Microsoft.Azure.Cosmos.Table SDK yang ditingkatkan ke 1.0.8

### <a name="thanks-to-our-community-contributors"></a>Terima kasih kepada kontributor komunitas kami
* Thomas Van Laere (@ThomVanL), Tambahkan Dockerfile-alpine-3.10 (#12911)
* Lohith Chowdary Chilukuri (@Lochiluk), Pembaruan Remove-AzNetworkInterfaceIpConfig.md (#12807)
* Roberth Strand (@roberthstrand), Get-AzResourceGroup - Contoh baru, dan pembersihan (#12828)
* Ravi Mishra (@inmishrar), perbarui tumpukan runtime Azure Web App ke DOTNETCORE (#12833)
* @jack-education, diperbarui Set-AzVirtualNetworkSubnetConfig untuk memungkinkan NSG dan Route Table dihapus dari subnet (#12351)
* @hagop-globanet, Perbarui Add-AzApplicationGatewayCustomError.md (#12784)
* Joshua Van Daalen (@greenSacrifice)
  * Memperbarui ejaan Properti ke Properti (#12821)
  * Perbarui contoh New-AzResourceLock.md (#12806)
* Eragon Riddle (@eragonriddle), Nama bidang parameter terkoreksi dalam contoh (#12825)
* @rossifumax, Perbaiki kesalahan ketik di New-AzConfigurationAssignment.md (#12701)

## <a name="461---august-2020"></a>4.6.1 - Agustus 2020
#### <a name="azcompute"></a>Az.Compute
* Parameter '-EncryptionAtHost' yang ditambal di 'New-AzVm' untuk menghapus nilai default false [#12776]

## <a name="460---august-2020"></a>4.6.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memuat semua lingkungan cloud publik saat titik akhir penemuan tidak mengembalikan AzureCloud default atau lingkungan publik lainnya [#12633]
* Exposed SubscriptionPolicies di 'Get-AzSubscription' [#12551]

#### <a name="azautomation"></a>Az.Automation
* Menambahkan parameter '-RunOn' ke 'Set-AzAutomationWebhook' untuk menentukan Grup Pekerja Hibrida

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter '-EncryptionAtHost' ke 'New-AzVm', 'New-AzVmss', 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVM', dan 'Update-AzVmss'
* Menambahkan objek pengembalian 'SecurityProfile' ke 'Get-AzVM' dan 'Get-AzVmss'
* Menambahkan sakelar '-InstanceView' sebagai parameter opsional ke 'Get-AzHostGroup'
* Menambahkan cmdlet baru 'Invoke-AzVmPatchAssessment'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan properti yang hilang ke kelas PSPipelineRun.

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung membuat cluster dengan enkripsi di fitur host.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan pesan peringatan untuk merencanakan menonaktifkan penghapusan lunak
* Menambahkan pesan peringatan untuk perencanaan menghapus atribut SecretValueText

#### <a name="azmaintenance"></a>Az.Pemeliharaan
* Menambahkan bidang terkait jadwal opsional ke 'New-AzMaintenanceConfiguration'
* Menambahkan cmdlet baru untuk 'Get-AzMaintenancePublicConfiguration'

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan peringatan perubahan yang melanggar pada cmdlet penugasan dan definisi layanan terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Memperluas kumpulan parameter dalam 'Set-AzDiagnosticSetting' untuk pemisahan pengokan Log dan Metrik [#12482]
* Memperbaiki bug untuk 'Add-AzMetricAlertRuleV2' saat mendapatkan peringatan metrik dari pipeline

#### <a name="azresources"></a>Az.Resources
* Memperbarui respons 'Get-AzPolicyAlias' untuk menyertakan informasi yang menunjukkan apakah alias dapat dimodifikasi oleh Azure Policy.
* Membuat cmdlet baru 'Set-AzRoleAssignment'
* Menambahkan 'Get-AzDeploymentManagementGroupWhatIfResult' untuk mendapatkan template ARM What-If hasil di lingkup Grup manajemen
* Menambahkan cmdlet baru 'Get-AzTenantWhatIfResult' untuk mendapatkan template ARM What-If hasil di lingkup penyewa
* Overrode '-WhatIf' dan '-Confirm' untuk 'New-AzManagementGroupDeployment' dan 'New-AzTenantDeployment' untuk menggunakan template ARM What-If hasil
* Memperbaiki perilaku '-WhatIf' dan '-Confirm' untuk cmdlet penyebaran baru sehingga mereka mematuhi False dan
* Memperbaiki kesalahan serialisasi untuk '-TemplateObject' dan 'TemplateParameterObject' [#1528] [#6292]
* Menambahkan atribut perubahan yang melanggar ke 'Get-AzResourceGroupDeploymentOperation' untuk perubahan jenis output yang akan datang

#### <a name="azsignalr"></a>Az.Signalr
* Memperbaiki kesalahan file bantuan 'Restart-AzSignalR' dan 'Update-AzSignalR'
* Menambahkan cmdlet 'Update-AzSignalRNetworkAcl', 'Set-AzSignalRUpstream'

#### <a name="azstorage"></a>Az.Storage
* Akselerasi kueri blob yang didukung
    -  'Get-AzStorageBlobQueryResult'
    -  'New-AzStorageBlobQueryConfig'
* File bantuan yang diperbarui, menambahkan lebih banyak deskripsi, dan memperbaiki kesalahan ketik
    -  'Start-AzStorageBlobCopy'
    -  'Get-AzDataLakeGen2Item'
* Blob unduhan tetap gagal ketika sub direktori terkait tidak ada [#12592]
    -  'Get-AzStorageBlobContent'
* Kebijakan Replikasi Set/Get/Remove Objek yang Didukung di akun Storage
    - 'New-AzStorageObjectReplicationPolicyRule'
    - 'Set-AzStorageObjectReplicationPolicy'
    - 'Get-AzStorageObjectReplicationPolicy'
    - 'Remove-AzStorageObjectReplicationPolicy'
* Diaktifkan/nonaktifkan ChangeFeed yang didukung di Layanan Blob dari akun Storage
    - 'Update-AzStorageBlobServiceProperty'

## <a name="450---august-2020"></a>4.5.0 - Agustus 2020
#### <a name="azaccounts"></a>Az.Accounts
* Diperbarui 'Koneksi-AzAccount' untuk menerima parameter 'MaxContextPopulation' [#9865]
* Versi SubscriptionClient yang diperbarui ke 2019-06-01 dan menampilkan domain penyewa [#9838]
* Penyewa rumah yang didukung dan dikelolaOleh informasi penyewa langganan
* Nama modul yang diperbaiki, info versi dalam data telemetri
* SqlDatabaseDnsSuffix dan ServiceManagementUrl jika titik akhir metadata lingkungan mengembalikan nilai yang tidak kompatibel

#### <a name="azaks"></a>Az.Aks
* Dihapus 'ClientIdAndSecret' ke 'ServicePrincipalIdAndSecret' dan mengatur 'ClientIdAndSecret' sebagai alias [#12381].
* Menghapus 'Get-AzAks'/'New-AzAks'/'Remove-AzAks'/'Set-AzAks' ke 'Get-AzAksCluster'/'New-AzAksCluster'/'Remove-AzAksCluster'/'Set-AzAksCluster' dan mengatur yang asli sebagai alias [#12373].

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan cmdlet 'Add-AzApiManagementApiToGateway' yang baru.
* Menambahkan cmdlet 'Get-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'Get-AzApiManagementGatewayHostnameConfiguration'.
* Menambahkan cmdlet 'Get-AzApiManagementGatewayKey' baru.
* Menambahkan cmdlet 'New-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'New-AzApiManagementGatewayHostnameConfiguration' baru.
* Menambahkan cmdlet 'New-AzApiManagementResourceLocationObject' baru.
* Menambahkan cmdlet 'Remove-AzApiManagementApiFromGateway'.
* Menambahkan cmdlet 'Remove-AzApiManagementGateway' baru.
* Menambahkan cmdlet 'Remove-AzApiManagementGatewayHostnameConfiguration' baru.
* Menambahkan cmdlet 'Update-AzApiManagementGateway' baru.
* Menambahkan parameter opsional [-GatewayId] baru ke cmdlet 'Get-AzApiManagementApi'.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menggunakan 'Deny' secara khusus sebagai tindakan default NetworkRules.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbaiki masalah di mana pengecualian dilemparkan saat Enum.Parse mencoba memaksa nilai null ke nilai enum Diaktifkan atau Dinonaktifkan [#12344]

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung membuat klaster dengan enkripsi dalam fitur transit.
    - Tambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightCluster'
    - Tambahkan parameter baru 'EncryptionInTransit' ke cmdlet 'New-AzHDInsightClusterConfig'
* Mendukung pembuatan klaster dengan fitur tautan pribadi:
    - Tambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightCluster'
    - Tambahkan parameter baru 'PublicNetworkAccessType' dan 'OutboundPublicNetworkAccessType' ke cmdlet 'New-AzHDInsightClusterConfig'
* Mengembalikan informasi jaringan virtual saat menelepon 'New-AzHDInsightCluster' atau 'Get-AzHDInsightCluster'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Menambahkan perubahan yang tidak melanggar: Fungsi PeerAddressType untuk Private Peering di 'Remove-AzExpressRouteCircutPeeringConfig'.
* Kode diubah untuk mengabaikan kasus untuk parameter AddressPrefixType dan PeerAddressType.
* Memodifikasi pesan peringatan untuk 'New-AzLoadBalancerFrontendIpConfig', 'New-AzPublicIpAddress' dan 'New-AzPublicIpPrefix'.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Menambahkan opsi '-ForceDelete' untuk 'Remove-AzOperationalInsightsworkspace'
* Menambahkan cmdlet baru 'Get-AzOperationalInsightsDeletedWorkspace'
* Menambahkan cmdlet baru 'Restore-AzOperationalInsightsWorkspace'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Meningkatkan pengalaman penemuan kontainer/item Azure Backup.

#### <a name="azresources"></a>Az.Resources
* Menambahkan properti 'Kondisi', 'ConditionVersion' dan 'Deskripsi' ke 'New-AzRoleAssignment'
    - Ini termasuk semua perubahan yang relevan pada model data

#### <a name="azsql"></a>Az.Sql
* Memperbaiki kesalahan kasus nama server potensial yang tidak sensitif di 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Memperbaiki nama database yang salah dikembalikan pada kesalahan database yang ada di 'New-AzSqlDatabaseSecondary'

#### <a name="azstorage"></a>Az.Storage
* Didukung membuat container/blob Sas token dengan izin baru x,t
    -  'New-AzstorageblobSASToken'
    -  'New-AzstorageContainersASToken'
* Didukung buat akun Sas token dengan izin baru x,t,f
    -  'New-AzstorageAccountsASToken'
* Didukung mendapatkan penggunaan berbagi file tunggal
    - 'Get-AzRmStorageShare'

## <a name="440---july-2020"></a>4.4.0 - Juli 2020
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan cmdlet baru 'Invoke-AzRestMethod'
* Memperbaiki masalah yang dapat menyebabkan kesalahan autentikasi dalam skenario multi-proses seperti menjalankan beberapa cmdlet Azure PowerShell menggunakan 'Start-Job' [#9448]

#### <a name="azaks"></a>Az.Aks
* Bug tetap 'Get-AzAks' tidak mendapatkan semua klaster [#12296]

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Menghapus referensi proyek ke Autentikasi

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah yang string dengan escape chars tidak dapat dikonversi menjadi objek json.

#### <a name="azcompute"></a>Az.Compute
* Peringatan tambahan saat menggunakan 'New-AzVmss' tanpa versi gambar 'terbaru'

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan parameter global ke Data Factory.

#### <a name="azeventgrid"></a>Az.EventGrid
* Diperbarui untuk menggunakan versi API 2020-06-01.
* Menambahkan fitur baru:
    - Pemetaan input
    - Skema Pengiriman Peristiwa
    - Private Link
    - Skema Cloud Event V10
    - Topik Bus Layanan Sebagai Tujuan
    - Azure Function As Destination
    - WebHook Batching
    - Webhook aman (dukungan AAD)
    - IpFiltering
* Cmdlet yang diperbarui:
    - 'New-AzEventGridSubscription'/'Update-AzEventGridSubscription':
        - Tambahkan parameter opsional baru untuk mendukung batching webhook.
        - Tambahkan parameter opsional baru untuk mendukung webhook aman menggunakan AAD.
        - Tambahkan enum baru untuk parameter EndpointType untuk mendukung fungsi azure dan topik bus layanan sebagai tujuan baru.
        - Tambahkan parameter opsional baru untuk skema pengiriman.
    - 'New-AzEventGridTopic'/'Update-AzEventGridTopic' dan 'New-AzEventGridDomain'/'Update-AzEventGridDomain':
        - Tambahkan parameter opsional baru untuk mendukung IpFiltering.
    - 'New-AzeventGridTopic'/'new-azeventGridDomain':
        - Tambahkan parameter opsional baru untuk mendukung pemetaan Input.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Modul yang diperbarui untuk menggunakan API 2020-05-01
* Menambahkan dukungan tautan pribadi untuk sumber daya Storage, Keyvault, dan Layanan Aplikasi Web

#### <a name="azhdinsight"></a>Az.HDInsight
* Mendukung pembuatan klaster dengan penyimpanan ADLSGen1/2 di awan nasional.

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki bug untuk 'Get-AzDiagnosticSetting' saat metrik atau log null [#12272]

#### <a name="aznetwork"></a>Az.Network
* Pertukaran parameter tetap di koneksi VWan HubVnet
* Menambahkan cmdlet baru untuk Situs Alat Virtual Azure Network
    - 'Get-AzVirtualApplianceSite'
    - 'Situs Ketergantungan Baru-AzVirtualApp'
    - 'Remove-AzVirtualApplianceSite'
    - 'Update-AzVirtualApplianceSite'
    - 'New-AzOffice365PolicyProperty'
* Menambahkan cmdlet baru untuk Azure Network Virtual Appliance
    - 'Get-AzNetworkVirtualAppliance'
    - 'New-AzNetworkVirtualAppliance'
    - 'Remove-AzNetworkVirtualAppliance'
    - 'Update-AzNetworkVirtualAppliance'
    - 'Get-AzNetworkVirtualAppliancesku'
    - 'New-AzVirtualApplianceSkuProperty'
* Gateway Aplikasi Onboarded ke Cmdlet Umum Tautan Pribadi
* Onboarded StorageSync ke Private Link Common Cmdlets
* Onboarded SignalR ke Private Link Common Cmdlets

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menghapus referensi proyek ke Autentikasi
* Azure Backup disetel cmdlets membantu teks menjadi lebih akurat.
* Azure Backup menambahkan dukungan untuk mengambil pekerjaan agen MAB menggunakan cmdlet 'Get-AzRecoveryServicesBackupJob'.

#### <a name="azresources"></a>Az.Resources
* Diperbarui 'Save-AzResourceGroupDeploymentTemplate' untuk menggunakan SDK.
* Ditambahkan cmdlet 'Unregister-AzResourceProvider'.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk kepala layanan dan pengguna tamu di Set-AzSqlInstanceActiveDirectoryAdministrator cmdlet'
* Memperbaiki bug di cmdlet Klasifikasi Data.
* Menambahkan dukungan untuk failover Instans Terkelola Azure SQL: 'Invoke-AzSqlInstanceFailover'

#### <a name="azstorage"></a>Az.Storage
* Memperbaiki masalah bahwa UserAgent tidak ditambahkan untuk beberapa cmdlet bidang data.
* Akun Storage buat/pembaruan yang didukung dengan MinimumTlsVersion dan AllowBlobPublicAccess
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Mendukung mengaktifkan/menonaktifkan pembuatan versi di Blob Service dari akun Storage
    - 'Update-AzStorageBlobServiceProperty'
* Menghapus daftar dukungan dengan versi blob
    - 'Get-AzStorageBlob'
* Mendukung mendapatkan/menghapus snapshot blob tunggal atau versi blob
    - 'Get-AzStorageBlob'
    - 'Remove-AzStorageBlob'
* Mendukung pipeline dari objek blob yang dihasilkan dari Azure. Storage. Gumpalan V12
    - 'Get-AzStorageBlobContent'
    - 'New-AzstorageblobSASToken'
    - 'Remove-AzStorageBlob'
    - 'Set-AzStorageBlobContent'
    - 'Start-AzStorageBlobCopy'

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan versi baru StorageSync SDK yang menargetkan ApiVersion 2020-03-01
* Cmdlet Pembaruan Storage Sync Service Tambahan
    - 'Set-AzStorageSyncService'
* Menambahkan IncomingTrafficPolicy dan PrivateEndpointConnections ke cmdlet StorageSyncService.

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan dukungan untuk melakukan operasi untuk Slots yang tidak berada dalam grup sumber daya yang sama dengan Paket Layanan Aplikasi

## <a name="430---june-2020"></a>4.3.0 - Juni 2020
#### <a name="azaccounts"></a>Az.Accounts
* Pengaturan lingkungan penemuan yang didukung secara default dan menambahkan lingkungan melalui 'Add-AzEnvironment'
* Memperbarui rakitan yang dimuat sebelumnya [#12024], [#11976]
* Perakitan Azure.Core yang diperbarui
* Memperbaiki masalah yang dapat menyebabkan 'Koneksi-AzAccount' gagal dalam eksekusi multi-threaded [#11201]

#### <a name="azaks"></a>Az.Aks
* Mengganti penggunaan [API AccessProfile](/rest/api/aks/managedclusters/getaccessprofile) lama dengan panggilan ke [API ListClusterAdmin](/rest/api/aks/managedclusters/listclusteradmincredentials) dan [ListClusterUser](/rest/api/aks/managedclusters/listclusterusercredentials)

#### <a name="azbatch"></a>Az.Batch
* Memperbarui Az.Batch untuk menggunakan versi SDK 'Microsoft.Azure.Management.Batch' ke 11.0.0
* Menambahkan kemampuan untuk mengatur Identitas BatchAccount di cmdlet 'New-AzBatchAccount'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menampilkan kemampuan akun yang didukung.
* Didukung memodifikasi PublicNetworkAccess.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter SimulateEviction ke cmdlet Set-AzVM dan Set-AzVmssVM.
* Menambahkan 'Premium_LRS' ke pelengkap argumen parameter StorageAccountType untuk cmdlet New-AzGalleryImageVersion.
* Menambahkan Substatus ke VMCustomScriptExtension [#11297]
* Menambahkan 'Hapus' ke argumen yang lebih lengkap dari parameter EvictionPolicy untuk cmdlet New-AzVM dan New-AzVMConfig.
* Memperbaiki nama Ekstensi VM baru untuk SAP

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.9.0

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan parameter Identitas Terkelola ke cmdlet 'New-AzEventHubNamespace' dan 'Set-AzEventHubNamespace'

#### <a name="azfunctions"></a>Az.Functions
* Menambahkan dukungan untuk membuat aplikasi fungsi PowerShell 7.0 dan Java 11

#### <a name="azhdinsight"></a>Az.HDInsight
* Host daftar yang didukung dan memulai ulang host tertentu dari klaster HDInsight.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Memperbarui versi SDK ke 1.1.0
* Menambahkan dukungan untuk pengaturan Ekspor dan Identitas Terkelola

#### <a name="azmonitor"></a>Az.Monitor
* Parameter objek input tetap untuk 'Set-AzActivityLogAlert'
* Memperbaiki parameter 'InputObject' untuk 'Set-AzActionGroup' [#10868]

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk parameter AddressPrefixType ke 'Remove-AzExpressRouteCircuitConnectionConfig'
* Menambahkan cmdlet baru untuk Azure FirewallPolicy
    - 'New-AzFirewallPolicyDnsSetting'
    - Dukungan untuk Tujuan FQDN dalam Aturan Jaringan untuk Kebijakan Firewall
* Menambahkan dukungan untuk operasi kumpulan alamat backend
    - 'New-AzLoadBalancerBackendAddressConfig'
    - 'New-AzLoadBalancerBackendAddressPool'
    - 'Set-AzLoadBalancerBackendAddressPool'
    - 'Remove-AzLoadBalancerBackendAddressPool'
    - 'Get-AzLoadBalancerBackendAddressPool'
* Menambahkan validasi nama untuk 'New-AzIpGroup'
* Menambahkan cmdlet baru untuk Azure FirewallPolicy
    - 'New-AzFirewallPolicyThreatIntelWhitelist'
* Diperbarui di bawah perintah untuk fitur: Server dns kustom set /hapus di VirtualWan P2SVpnGateway.
    - Diperbarui New-AzP2sVpnGateway: Menambahkan parameter opsional '-CustomDnsServer' bagi pelanggan untuk menentukan server dns mereka untuk diatur di P2SVpnGateway, yang dapat digunakan oleh klien Point to site.
    - Update-AzP2sVpnGateway: Menambahkan parameter opsional '-CustomDnsServer' bagi pelanggan untuk menentukan server dns mereka untuk diatur di P2SVpnGateway, yang dapat digunakan oleh klien Point to site.
* Diperbarui 'Update-AzVpnGateway'
    - Menambahkan parameter opsional '-BgpPeeringAddress' bagi pelanggan untuk menentukan bgp kustom mereka untuk diatur di VpnGateway.
* Menambahkan cmdlet baru untuk mendukung pengaturan ulang status perutean sumber daya VirtualHub:
    - 'Reset-AzHubRouter'
* Diperbarui di bawah ini hal-hal berdasarkan perubahan kesombongan baru-baru ini untuk Kebijakan Firewall
    - Mengubah nama untuk RuleGroup, RuleCollectionGroup, dan RuleType
    - Menambahkan dukungan untuk Pengumpulan Aturan NAT Kebijakan Firewall untuk mendukung beberapa Pengumpulan Aturan NAT
* [Melanggar Perubahan] Menambahkan parameter wajib 'SourceIpGroup' untuk 'New-AzFirewallPolicyApplicationRule' dan 'New-AzFirewallPolicyNetworkRule'.
* [Melanggar Perubahan] Tetap 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' menjadi wajib.
* [Melanggar Perubahan] Tetap 'New-AzFirewallPolicyApplicationRule', parameter 'SourceAddress' menjadi wajib.
* [Melanggar Perubahan] Parameter wajib yang dihapus: 'TranslatedAddress', 'TranslatedPort' untuk 'New-AzFirewallPolicyNatRuleCollection'.
* Menambahkan cmdlet baru untuk mendukung PrivateLink On Application Gateway
    - 'New-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Get-AzApplicationGatewayPrivateLinkConfiguration'
    - 'New-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Set-AzApplicationGatewayPrivateLinkConfiguration'
    - 'Remove-AzApplicationGatewayPrivateLinkConfiguration'
    - 'New-AzApplicationGatewayPrivateLinkIpConfiguration'
* Menambahkan cmdlet baru untuk hubRouteTables sumber daya anak virtualhub.
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
* Bug tetap PSWorkspace tidak menerapkan IOperationalInsightsWorkspace [#12135]
* Menambahkan 'pergb2018' ke kumpulan parameter nilai yang valid 'Sku' di 'Set-AzOperationalInsightsWorkspace'
* Menambahkan alias 'FunctionParameters' untuk parameter 'FunctionParameter' ke
    - 'New-AzOperationalInsightsSavedSearch'
    - 'Set-AzOperationalInsightsSavedSearch'

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Backup menambahkan dukungan untuk mengambil item MAB.
* Azure Site Recovery mendukung tipe disk 'StandardSSD_LRS'

#### <a name="azresources"></a>Az.Resources
* Menambahkan 'UsageLocation', 'GivenName', 'Surname', 'AccountEnabled', 'MailNickname', 'Mail' di 'PSADUser' [#10526] [#10497]
* Memperbaiki masalah yang '-Mail' tidak berfungsi pada 'Get-AzADUser' [#11981]
* Menambahkan parameter '-ExcludeChangeType' ke 'Get-AzDeploymentApaIfResult' dan 'Get-AzResourceGroupDeploymentWhatIfResult'
* Menambahkan parameter '-WhatIfExcludeChangeType' ke 'New-AzDeployment' dan 'New-AzResourceGroupDeployment'
* Cmdlet 'Test-Az*Deployment' yang diperbarui untuk menampilkan pesan kesalahan yang lebih baik
* Pesan bantuan tetap untuk parameter penyebaran '-Nama' membuat dan What-If cmdlet

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk prinsipal layanan untuk cmdlet Admin set SQL Server Azure Active Directory
* Memperbaiki masalah sinkronisasi di cmdlet Klasifikasi Data.
* Mendukung pencarian pengguna melalui surat di 'Set-AzSqlServerActiveDirectoryAdministrator' [#12192]

#### <a name="azstorage"></a>Az.Storage
* Didukung membuat akun Storage dengan RequireInfrastructureEncryption
    -  'New-AzStorageAccount'
* Memindahkan logika memuat Azure.Core ke Az.Accounts

#### <a name="azwebsites"></a>Az.Websites
* Perlindungan tambahan untuk menghapus webapp yang dibuat jika pemulihan gagal di 'Restore-AzDeletedWebApp'
* Menambahkan 'SourceWebApp.Location' untuk 'New-AzWebApp' dan 'New-AzWebAppSlot'
* Memperbaiki bug yang mencegah perubahan pengaturan Kontainer di 'Set-AzWebApp' dan 'Set-AzWebAppSlot'
* Memperbaiki bug untuk mendapatkan SiteConfig saat -Nama tidak diberikan untuk Get-AzWebApp
* Menambahkan dukungan untuk membuat ASP untuk Aplikasi Linux
* Menambahkan pengecualian untuk kloning di seluruh grup sumber daya

## <a name="420---june-2020"></a>4.2.0 - Juni 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki masalah yang dapat menyebabkan Az melewatkan log di pekerjaan Azure Automation atau PowerShell [#11492]

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Versi perakitan yang diperbarui dari cmdlet bidang data

#### <a name="azapimanagement"></a>Az.ApiManagement
* Versi perakitan yang diperbarui dari cmdlet manajemen layanan

#### <a name="azbilling"></a>Az.Billing
* Cmdlet konsumsi versi perakitan yang diperbarui

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung kontrol PrivateEndpoint dan PublicNetworkAccess.

#### <a name="azdatafactory"></a>Az.DataFactory
* Versi perakitan yang diperbarui dari cmdlet pabrik data V2

#### <a name="azdatashare"></a>Az.DataShare
* Ketersediaan umum modul 'Az.DataShare''

#### <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization
* Ketersediaan umum modul ''Az.DesktopVirtualization''

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* SDK yang ditingkatkan ke 0.21.0
* Menambahkan parameter opsional ke
    - 'New-AzOperationalInsightsSavedSearch'
    - 'Set-AzOperationalInsightsSavedSearch'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Contoh terkoreksi 3 untuk 'Start-AzPolicyComplianceScan'

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Cmdlet PowerBI versi perakitan yang diperbarui

#### <a name="azprivatedns"></a>Az.PrivateDns
* Pemformatan string output verbose yang dikoreksi untuk Remove-AzPrivateDnsRecordSet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk membuat rencana pemulihan untuk replikasi zona ke zona dari input xml.
* Versi perakitan yang diperbarui dari cmdlet SiteRecovery dan Backup

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter Ekor ke cmdlet Get-AzDeploymentScriptLog dan Save-AzDeploymentScriptLog
* Properti Output yang Diformat dan tampilkan di Get-AzDeploymentScript output cmdlet
* Berganti nama -DeploymentScriptInputObject parameter menjadi -DeploymentScriptObject
* Memperbaiki nama file/target yang hilang dalam pesan cmdlet.
* Versi perakitan yang diperbarui dari manajer sumber daya dan cmdlet tag

#### <a name="azsql"></a>Az.Sql
* Menambahkan UsePrivateLinkConnection ke 'New-AzSqlSyncGroup', 'Update-AzSqlSyncGroup', 'New-AzSqlSyncMember' dan 'Update-AzSqlSyncMember'
* Menambahkan SyncMemberAzureDatabaseResourceId ke 'New-AzSqlSyncMember' dan 'Update-AzSqlSyncMember'
* Menambahkan dukungan pencarian pengguna Tamu ke Mengatur cmdlet Admin SQL Server Azure Active Directory

#### <a name="azstorage"></a>Az.Storage
* Versi perakitan yang diperbarui dari cmdlet bidang data

## <a name="410---may-2020"></a>4.1.0 - Mei 2020
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Versi PowerShell yang didukung: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7
* Ketersediaan umum Az.Functions
* Az.ApiManagement, Az.Batch, Az.Compute, Az.KeyVault, Az.Monitor, Az.Network, Az.OperationalInsights, Az.Resources, dan Az.Storage memiliki rilis besar

#### <a name="azaccounts"></a>Az.Accounts
* Diperbarui 'Add-AzEnvironment' dan 'Set-AzEnvironment' untuk menerima parameter 'AzureSynapseAnalyticsEndpointResourceId' dan 'AzureSynapseAnalyticsEndpointSuffix'
* Menambahkan rakitan terkait Azure.Core ke Az.Accounts, platform PowerShell yang didukung mencakup Windows PowerShell 5.1, PowerShell Core 6.2.4, PowerShell 7+

#### <a name="azaks"></a>Az.Aks
* Versi API yang Ditingkatkan ke 2019-10-01
* Didukung untuk membuat AKS menggunakan wadah Windows
* Disediakan cmdlet baru: 'New-AzAksNodePool', 'Update-AzAksNodePool', 'Remove-AzAksNodePool', 'Get-AzAksNodePool', 'Install-AzAksKubectl', 'Get-AzAksVersion'

#### <a name="azapimanagement"></a>Az.ApiManagement
* Parameter 'New-AzApiManagement' dan 'Set-AzApiManagement': [-AssignIdentity] berganti nama menjadi [-SystemAssignedIdentity]
* 'New-AzApiManagement' dan 'Set-AzApiManagement': Parameter baru ditambahkan: [-UserAssignedIdentity <String[]>]
* 'Get-AzApiManagementProperty': berganti nama menjadi 'Get-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'New-AzApiManagementProperty': berganti nama menjadi 'New-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'Set-AzApiManagementProperty': berganti nama menjadi 'Set-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* 'Remove-AzApiManagementProperty': berganti nama menjadi 'Remove-AzApiManagementNamedValue'. Parameter PropertyId berganti nama menjadi NamedValueId.
* Menambahkan cmdlet 'Get-AzApiManagementAuthorizationServerClientSecret' dan 'Get-AzApiManagementAuthorizationServer' tidak akan mengembalikan rahasia klien lagi.
* Menambahkan cmdlet 'Get-AzApiManagementNamedValueSecretValue' baru dan 'Get-AzApiManagementNamedValue' tidak akan mengembalikan nilai rahasia.
* Menambahkan cmdlet 'Get-AzApiManagementOpenIdConnectProviderClientSecret' dan cmdlet 'Get-AzApiManagementOpenIdConnectProvider' tidak akan mengembalikan rahasia klien lagi.
* Menambahkan cmdlet 'Get-AzApiManagementSubscriptionKey' baru dan 'Get-AzApiManagementSubscription' tidak akan mengembalikan kunci langganan lagi.
* Menambahkan cmdlet 'Get-AzApiManagementTenantAccessSecret' dan 'Get-AzApiManagementTenantAccess' tidak akan mengembalikan kunci lagi.
* Menambahkan cmdlet 'Get-AzApiManagementTenantGitAccessSecret' dan 'Get-AzApiManagementTenantGitAccess' tidak akan mengembalikan kunci lagi.

#### <a name="azapplicationinsights"></a>Az.ApplicationInsights
* Parameter Tambahan: 'RetentionInDays' 'PublicNetworkAccessForIngestion' 'PublicNetworkAccessForQuery' untuk 'New-AzApplicationInsights'
* Cmdlet yang dibuat 'Update-AzApplicationInsights'
* Cmdlet yang dibuat untuk Akun Storage Tertaut

#### <a name="azbatch"></a>Az.Batch
* Memperbarui Az.Batch untuk menggunakan SDK 'Microsoft.Azure.Batch' versi 13.0.0 dan 'Microsoft.Azure.Management.Batch' SDK versi 9.0.0.
* Menambahkan kemampuan untuk memilih jenis sertifikat yang ditambahkan menggunakan parameter '-CertificateKind' baru ke 'New-AzBatchCertificate'.
* Menghapus properti 'ApplicationPackages' dari 'PSApplication' yang sebelumnya selalu ''.
  - Paket spesifik di dalam aplikasi sekarang dapat diambil menggunakan 'Get-AzBatchApplicationPackage'. Misalnya: 'Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication'.
* Saat membuat kumpulan menggunakan 'New-AzBatchPool', properti 'VirtualMachineImageId' dari 'PSImageReference' sekarang hanya dapat merujuk ke gambar Galeri Gambar Bersama.
* Saat membuat kumpulan menggunakan 'New-AzBatchPool', kumpulan dapat disediakan tanpa IP publik menggunakan properti 'PublicIPAddressConfiguration' baru dari 'PSNetworkConfiguration'.
  - Properti 'PublicIPs' dari 'PSNetworkConfiguration' telah pindah ke 'PSPublicIPAddressConfiguration' juga. Properti ini hanya dapat ditentukan jika 'IPAddressProvisioningType' adalah 'UserManaged'.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter HostId ke cmdlet 'Update-AzVM'
* Dokumen Bantuan yang Diperbarui untuk cmdlet 'New-AzVMConfig', 'New-AzVmssConfig', 'Update-AzVmss', 'Set-AzVMOperatingSystem' dan 'Set-AzVmssOsProfile'.
* Perubahan mencolok
    - Parameter FilterExpression dihapus dari cmdlet 'Get-AzVMImage'.
    - Parameter AssignIdentity dihapus dari cmdlet 'New-AzVmssConfig', 'New-AzVMConfig' dan 'Update-AzVM'.
    - AutomaticRepairMaxInstanceRepairsPercent dihapus dari cmdlet 'New-AzVmssConfig' dan 'Update-AzVmss'.
    - AvailabilitySetsColocationStatus, VirtualMachinesColocationStatus dan VirtualMachineScaleSetsColocationStatus properties dihapus dari ProximityPlacementGroup.
    - MaxInstanceRepairsPercent property dihapus dari AutomaticRepairsPolicy.
    - Jenis AvailabilitySets, VirtualMachines dan VirtualMachineScaleSets diubah dari `IList<SubResource>` .`IList<SubResourceWithColocationStatus>`
* Deskripsi untuk cmdlet 'Get-AzVM' telah diperbarui untuk menggambarkannya dengan lebih baik.

#### <a name="azdatafactory"></a>Az.DataFactory
* CRUD yang didukung dari properti runtime aliran data di IR Terkelola.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan cmdlet baru untuk pembuatan, pembaruan, retreival, dan penghapusan objek Mesin Aturan Pintu Depan
* Menambahkan cmdlet pembantu untuk konstruksi objek Mesin Aturan Pintu Depan
* Menambahkan Referensi Mesin Aturan ke objek Aturan Perutean Pintu Depan.
* Menambahkan parameter Tautan Pribadi ke objek Backend Pintu Depan

#### <a name="azfunctions"></a>Az.Functions
* Ketersediaan umum modul 'Az.Functions''

#### <a name="azhdinsight"></a>Az.HDInsight
* Enkripsi key disk yang dikelola pelanggan didukung.

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Kebijakan akses tidak lagi default ke prinsipal saat ini

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan cmdlet untuk meminta kueri di hub IoT untuk mengambil informasi menggunakan bahasa seperti SQL.
* Memperbaiki masalah bahwa 'Add-AzIotHubDevice' gagal membuat Perangkat Berkemampuan Edge tanpa perangkat anak [#11597]
* Menambahkan cmdlet untuk menghasilkan token SAS untuk Iot Hub, perangkat, atau modul.
* Menambahkan cmdlet untuk memanggil kueri metrik konfigurasi.
* Kelola penyebaran otomatis IoT Edge dalam skala besar. Cmdlet baru adalah:
    - 'Add-AzIotHubDeployment'
    - 'Get-AzIotHubDeployment'
    - 'Remove-AzIotHubDeployment'
    - 'Set-AzIotHubDeployment'
* Menambahkan cmdlet untuk memanggil kueri metrik penyebaran IoT Edge.
* Menambahkan cmdlet untuk menerapkan konten konfigurasi ke perangkat edge yang ditentukan.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menghapus dua alias: 'New-AzKeyVaultCertificateAdministratorDetails' dan 'New-AzKeyVaultCertificateOrganizationDetails'
* Penghapusan lunak yang diaktifkan secara default saat membuat vault kunci
* Aturan jaringan dapat diatur untuk mengatur aksesibilitas dari lokasi jaringan tertentu saat membuat brankas utama
* Menambahkan dukungan untuk membawa kunci Anda sendiri (BYOK)
    - 'Add-AzKeyVaultKey' mendukung pembuatan kunci pertukaran kunci
    - 'Get-AzKeyVaultKey' mendukung pengunduhan kunci publik dalam format PEM
* Memperbarui bagian 'KeyOps' dari dokumen bantuan 'Add-AzKeyVaultKey'

#### <a name="azmonitor"></a>Az.Monitor
* Bug tetap untuk 'Set-AzDiagnosticSettings', kebijakan retensi tidak akan berlaku untuk semua kategori [#11589]
* Kriteria ketersediaan WebTest yang didukung untuk peringatan metrik V2
    - 'New-AzMetricAlertRuleV2Criteria': opsi untuk membuat kriteria ketersediaan webtest ditambahkan
    - 'Add-AzMetricAlertRuleV2': mendukung kriteria ketersediaan webtest baru
* Menghapus definisi redundan untuk RetentionPolicy di PSLogProfile [#7608]
* Properti berlebihan yang dihapus difined di PSEventData [#11353]
* Berganti nama menjadi 'Get-AzLog' menjadi 'Get-AzActivityLog'

#### <a name="aznetwork"></a>Az.Network
* Menambahkan atribut perubahan putus untuk memberi tahu bahwa perilaku default Zona akan diubah
    - 'New-AzPublicIpAddress'
    - 'New-AzPublicIpPrefix'
    - 'New-AzLoadBalancerFrontendIpConfig'
* Menambahkan dukungan untuk sumber daya tingkat atas baru SecurityPartnerProvider
    - Cmdlet baru menambahkan:
        - New-AzSecurityPartnerProvider
        - Remove-AzSecurityPartnerProvider
        - Get-AzSecurityPartnerProvider
        - Set-AzSecurityPartnerProvider
* Menambahkan 'RequiredZoneNames' di 'PSPrivateLinkResource' dan 'GroupId' di 'PSPrivateEndpointConnection'
* Memperbaiki jenis parameter SuccessThresholdRoundTripTimeMs yang salah untuk New-AzNetworkWatcherConnectionMonitorTestConfigurationObject
* Cmdlet VirtualWan yang diperbarui untuk menetapkan nilai default argumen AllowVnetToVnetTraffic ke True.
    - 'New-AzVirtualWan'
    - 'Update-AzVirtualWan'
* Menambahkan cmdlet baru untuk mendukung grup zona DNS untuk titik akhir pribadi
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
* Kode lama yang diperbarui untuk menerapkan SDK baru yang dibuat
* Cmdlet yang dihapus karena API yang tidak digunakan lagi
    - 'Get-AzOperationalInsightsSavedSearchResult' (alias 'Get-AzOperationalInsightsSavedSearchResults')
    - 'Get-AzOperationalInsightsSearchResult' (alias 'Get-AzOperationalInsightsSearchResults')
    - 'Get-AzOperationalInsightsLinkTarget' (alias 'Get-AzOperationalInsightsLinkTargets')
* Menambahkan parameter untuk 'Set-AzOperationalInsightsWorkspace' dan 'New-AzOperationalInsightsWorkspace'
* Cmdlet yang dibuat untuk Akun Stoarge Tertaut
* Cmdlet yang dibuat untuk Cluster dan Linked Service

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery menambahkan dukungan untuk melindungi mesin virtual grup penempatan kedekatan untuk penyedia Azure ke Azure.
* Azure Site Recovery menambahkan dukungan untuk replikasi zona ke zona.
* Azure Backup Menambahkan dukungan retensi jangka panjang untuk Azure FileShare Recovery Points.
* Azure Backup Menambahkan properti pengecualian disk ke output cmdlet 'Get-AzRecoveryServicesBackupItem'.
* Menambahkan titik akhir pribadi untuk file kredensial Vault untuk layanan pemulihan situs.

#### <a name="azresources"></a>Az.Resources
* Peringatan pesan tambahan tentang penundaan tampilan saat membuat Definisi Peran baru
* Mengubah cmdlet kebijakan menjadi output objek yang diketik dengan kuat
* Menghapus parameter '-TenantLevel' yang digunakan pada cmdlet 'Get-AzResourceLock' [#11335]
* Memperbaiki 'Remove-AzResourceGroup -Id ResourceId'[#9882]
* Menambahkan cmdlet baru untuk mendapatkan template ARM What-If hasil di lingkup grup sumber daya: 'Get-AzDeploymentResourceGroupWhatIfResult'
* Menambahkan cmdlet baru untuk mendapatkan template ARM What-If hasil di lingkup langganan: 'Get-AzDeploymentApaIfResult'
   - Alias: 'Get-AzSubscriptionDeploymentApaIf'
* Overrode parameter '-WhatIf' dan '-Confirm' untuk 'New-AzDeployment' dan 'New-AzResourceGroupDeployment' untuk menggunakan template ARM What-If hasil
* Menambahkan pesan deprekasi untuk parameter 'ApiVersion' di cmdlet penyebaran
* Menambahkan kemampuan untuk menampilkan pesan kesalahan yang ditingkatkan untuk kegagalan penerapan
* Menambahkan korelasiId logging untuk kegagalan penyebaran
* Menambahkan properti 'kesalahan' ke output skrip penerapan
* Diperbarui nuget Microsoft.Azure.Management.ResourceManager ke '3.7.1-preview'
* Menghapus kasus pengujian tertentu sebagai Properti Kesalahan di DeploymentValidateResult telah berubah menjadi selengkapnya dari nuget 3.7.1-preview
* Dibawa GenericResourceExpanded dari SDK ResourceManager 3.7.1-preview
* Menambahkan dukungan tag untuk semua cmdlet Get untuk penyebaran, serta
    - 'New-AzDeployment'
    - 'New-AzManagementGroupDeployment'
    - 'New-AzResourceGroupDeployment'
    - 'New-AzTenantDeployment'

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki bug dalam menambahkan sertifikat menggunakan --SecretIdentifier yang mendapatkan thumbprint sertifikat yang salah

#### <a name="azsql"></a>Az.Sql
* Meningkatkan kinerja:
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
* Menambahkan '-AsJob' untuk mendapatkan /daftar cmdlet akun 'Get-AzStorageAccount'
* Jadikan KeyVersion ke opsional saat memperbarui akun Storage dengan KeyvaultEncryption, untuk mendukung rotasi otomatis tombol
    - 'Set-AzStorageAccount'
* Memperbaiki hapus Azure File Directory gagal dengan pipeline
    - 'Remove-AzStorageDirectory'
* Tetap [#9880]: Ubah definisi nilai Default NetWorkRule untuk menyelaraskan dengan kesombongan.
    - 'update-azstorageAccountNetworkruleSet'
    - 'Get-AzStorageAccountNetworkruleSet'
* Diperbaiki [#11624]: Lewati aturan duplikat saat menambahkan NetworkRules, untuk menghindari kegagalan server
    - 'Add-azStorageAccountNetworkrule'
* Peningkatan Microsoft.Azure.Cosmos.Table SDK ke 1.0.7
* Menambahkan pesan peringatan untuk mengingatkan pengguna untuk mendaftar lagi dengan ContinuationToken saat hanya item bagian yang dikembalikan dalam daftar Item DataLake Gen2,
    - 'Get-AzDataLakeGen2ChildItem'
* Didukung untuk membuat atau memperbarui akun Storage dengan Autentikasi Layanan Domain Direktori Aktif Azure Files
    -  'New-AzStorageAccount'
    -  'Set-AzStorageAccount'
* Didukung ke kunci kerberos baru atau daftar akun Storage
    -  'New-AzStorageAccountKey'
    -  'Get-AzStorageAccountKey'
* Akun failover Storage yang didukung
    - 'Invoke-AzStorageAccountFailover'
* Bantuan terbaru dari 'Get-AzStorageBlobCopyState'
* Bantuan terbaru dari 'Get-AzStorageFileCopyState' dan 'Start-AzStorageBlobCopy'
* Pustaka klien Storage terintegrasi v12 ke Cmdlet Antrian dan File
* Mengubah jenis output dari CloudFile ke AzureStorageFile, output asli akan menjadi properti anak dari output baru
    - 'Get-AzStorageFile'
    - 'Remove-AzStorageFile'
    - 'Get-AzStorageFileContent'
    - 'Set-AzStorageFileContent'
    - 'Start-AzStorageFileCopy'
* Mengubah jenis output dari CloudFileDirectory ke AzureStorageFileDirectory, output asli akan menjadi properti anak dari output baru
    - 'New-AzStorageDirectory'
    - 'Remove-AzStorageDirectory'
* Mengubah jenis output dari CloudFileShare ke AzureStorageFileShare, output asli akan menjadi properti anak dari output baru
    - 'Get-AzStorageShare'
    - 'New-AzStorageShare'
    - 'Remove-AzStorageShare'
* Mengubah jenis output dari FileShareProperties ke AzureStorageFileShare, output asli akan menjadi properti sub-anak dari output baru
    - 'Set-AzStorageShareQuota'

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Memperbaiki nama profil yang salah di 'DisableAzureTrafficManagerEndpoint' output verbose

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki kesalahan ketik pada bantuan 'Update-AzWebAppAccessRestrictionConfig'.

## <a name="380---april-2020"></a>3.8.0 - April 2020
### <a name="highlights-since-the-last-release"></a>Sorotan sejak rilis terakhir
* Versi PowerShell yang didukung Az.Storage: Windows PowerShell 5.1, PowerShell Core 6.2.4+, PowerShell 7

#### <a name="azaccounts"></a>Az.Accounts
* URL survei Azure PowerShell diperbarui di 'Resolve-AzError' [#11507]

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan pemberitahuan perubahan yang melanggar untuk perubahan output cmdlet Azure File di rilis mendatang
* 'Set-AzApiManagementGroup' Dokumentasi yang diperbarui untuk menentukan parameter GroupId

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki tampilan SKU terkait harga ChinaCDN

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Identitas, Enkripsi, UserOwnedStorage yang Didukung

#### <a name="azcompute"></a>Az.Compute
* Ditambahkan cmdlet 'Set-AzVmssOrchestrationServiceState'.
* 'Get-AzVmss' dengan -InstanceView menampilkan negara OrchestrationService.

#### <a name="aziothub"></a>Az.IotHub
* Mengelola konfigurasi kembar perangkat IoT, Cmdlet baru adalah:
    - 'Get-AzIotHubDeviceTwin'
    - 'Update-AzIotHubDeviceTwin'
* Menambahkan cmdlet untuk memanggil metode langsung pada perangkat di Iot Hub.
* Mengelola konfigurasi kembar modul perangkat IoT, Cmdlet baru adalah:
    - 'Get-AziotHubModuletwin'
    - 'update-aziotHubModuletwin'
* Kelola konfigurasi manajemen perangkat otomatis IoT dalam skala besar. Cmdlet baru adalah:
    - 'Add-aziotHubConfiguration'
    - 'Get-AziotHubConfiguration'
    - 'Remove-aziotHubConfiguration'
    - 'Set-aziotHubConfiguration'
* Menambahkan cmdlet untuk memanggil metode modul edge di Iot Hub.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan cmdlet baru 'Update-AzKeyVault' yang dapat memungkinkan perlindungan penghapusan dan pembersihan lunak di lemari besi
* Menambahkan dukungan ke Microsoft.PowerShell.SecretManagement [#11178]
* Memperbaiki kesalahan dalam contoh 'Remove-AzKeyVaultManagedStorageSasDefinition' [#11479]
* Menambahkan dukungan ke titik akhir privat

#### <a name="azmaintenance"></a>Az.Pemeliharaan
* Menerbitkan versi rilis cmdlet Maintenance untuk GA

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
* Cmdlet yang diperbarui untuk mengaktifkan koneksi pada IP pribadi untuk Virtual Network Gateway.
    - 'New-AzVirtualNetworkGateway'
    - 'Set-AzVirtualNetworkGateway'
    - 'New-AzVirtualNetworkGatewayConnection'
    - 'Set-AzVirtualNetworkGatewayConnection'
* Cmdlet yang diperbarui untuk mengaktifkan LocalNetworkGateways dan VpnSites berbasis FQDN
    - 'New-AzLocalNetworkGateway'
    - 'New-AzVpnSiteLink'
* Menambahkan dukungan untuk keluarga alamat IPv6 di ExpressRouteCircuitConnectionConfig (Global Reach)
    - Ditambahkan 'Set-AzExpressRouteCircuitConnectionConfig'
        - memungkinkan pengaturan semua properti yang ada termasuk IPv6CircuitConnectionProperties
    - Diperbarui 'Add-AzExpressRouteCircuitConnectionConfig'
        - Menambahkan parameter opsional lain AddressPrefixType untuk menentukan keluarga alamat awalan alamat
* Cmdlet yang diperbarui untuk mengaktifkan pengaturan Batas Waktu DPD pada Koneksi Gateway Jaringan Virtual.
    - Baru-AzVirtualNetworkGatewayConnection
    - Set-AzVirtualNetworkGatewayConnection

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Menambahkan cmdlet 'Start-AzPolicyComplianceScan' untuk memicu pemindaian kepatuhan kebijakan
* Menambahkan definisi kebijakan, definisi yang ditetapkan, dan versi penugasan ke output 'Get-AzPolicyState'

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Pemformatan kode yang ditingkatkan dan kegunaan contoh 'New-AzServiceFabricCluster'

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet 'Get-AzSqlInstanceOperation' dan 'Stop-AzSqlInstanceOperation'
* Audit yang didukung ke akun penyimpanan di VNet.

#### <a name="azstorage"></a>Az.Storage
* Menambahkan pemberitahuan perubahan yang melanggar untuk perubahan output cmdlet Azure File di rilis mendatang
* Didukung SkuName StandardGZRS baru, StandardRAGZRS saat membuat/memperbarui akun Storage
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
* Modul Az sekarang tersedia dalam pratinjau di Azure Stack Hub. Hal ini memungkinkan kompatibilitas lintas platform dengan Linux dan macOs. Azure Stack Hub sekarang mendukung inti PowerShell dengan modul Az, informasi lebih lanjut [di sini](/azure-stack/operator/powershell-install-az-module)
* Profil dukungan modul AZ 2019-03-01-hybrid:
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
* Perintah tetap relatif sama, dengan perubahan kecil seperti mengubah AzureRM menjadi Az
* Tautan yang diperbarui ke dokumentasi PowerShell untuk Azure Stack Hub dapat ditemukan [di sini](/azure-stack/operator/powershell-install-az-module)

## <a name="370---march-2020"></a>3.7.0 - Maret 2020
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki 'Get-AzTenant'/'Get-AzDefault'/'Set-AzDefault' melempar NullReferenceException saat tidak login [#10292]

#### <a name="azcompute"></a>Az.Compute
* Menambahkan parameter berikut ke cmdlet 'New-AzDiskConfig':
    - DiskIOPSReadOnly, DiskMBpsReadOnly, MaxSharesCount, GalleryImageReference
* Properti Enkripsi yang Diizinkan untuk Menargetkan parameter cmdlet 'New-AzGalleryImageVersion'.
* Memperbaiki masalah tempDisk untuk cmdlet 'Set-AzVmss' -Reimage dan 'Invoke-AzVMReimage'. [#11354]
* Menambahkan dukungan ke cmdlet bawah untuk Ekstensi SAP baru
    - 'Set-AzVMAEMExtension'
    - 'Get-AzVMAEMExtension'
    - 'Remove-AzVMAEMExtension'
    - 'Update-AzVMAEMExtension'
* Memperbaiki kesalahan dalam contoh dokumen bantuan
* Memperlihatkan nilai string yang tepat untuk VM PowerState dalam format tabel.
* 'New-AzVmssConfig': serialisasi tetap properti AutomaticRepairs saat SinglePlacementGroup dinonaktifkan. [#11257]

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.8.0
* Menambahkan parameter opsional ke perintah 'Invoke-AzDataFactoryV2Pipeline' untuk mendukung tayangan ulang

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan deskripsi perubahan yang melanggar untuk 'Export-AzDataLakeStoreItem' dan 'Import-AzDataLakeStoreItem'
* Opsi tambahan pengkodean Byte untuk 'New-AzDataLakeStoreItem', 'Add-AzDAtaLakeStoreItemContent', dan 'Get-AzDAtaLakeStoreItemContent'

#### <a name="azhdinsight"></a>Az.HDInsight
* Didukung menentukan versi TLS minimal yang didukung saat membuat klaster.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola pengaturan terdistribusi per perangkat. Cmdlet baru adalah:
    - 'Get-AziotHubDistributedTracing'
    - 'Set-aziotHubDistributedTracing'

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan atribut perubahan yang melanggar ke 'New-AzKeyVault'

#### <a name="azmonitor"></a>Az.Monitor
* Dokumentasi yang diperbarui untuk 'New-AzScheduledQueryRuleLogMetricTrigger'

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui untuk memungkinkan lintas penyewa VirtualHubVnetConnections
    - 'New-AzVirtualHubVnetConnection'
    - 'Update-AzVirtualHubVnetConnection'
    - 'New-AzVirtualHub'
    - 'Update-AzVirtualHub'
* Menghapus dependensi SQL Management SDK

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Meningkatkan pesan kesalahan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery menambahkan dukungan untuk melakukan perlindungan ulang dan properti vm yang diperbarui untuk Mesin Virtual terenkripsi disk Azure.
* Menambahkan Azure Site Recovery VmwareToAzure properties DR monitoring
* Azure Backup menambahkan dukungan untuk mencoba kembali pembaruan kebijakan untuk item yang gagal.
* Azure Backup Menambahkan dukungan untuk pengaturan pengecualian disk selama pencadangan dan pemulihan.
* Azure Backup Menambahkan Dukungan untuk Memulihkan Beberapa file/folder di AzureFileShare
* Azure Backup Menambahkan dukungan untuk dukungan Resourcegroup yang ditentukan pengguna saat memperbarui Kebijakan IaasVM

#### <a name="azresources"></a>Az.Resources
* Memperbaiki 'Get-AzResource -ResourceGroupName -Name -ExpandProperties -ResourceType' untuk menggunakan apiVersion sumber daya yang sebenarnya alih-alih apiVersion default [#11267]
* Menambahkan korelasiId logging untuk skenario kesalahan
* Dokumentasi kecil berubah menjadi 'Get-AzResourceLock'. Contoh tambahan.
* Kutipan tunggal yang lolos dalam nilai parameter 'Get-AzADUser' [#11317]
* Menambahkan cmdlet baru untuk Deployment Scripts ('Get-AzDeploymentScript', 'Get-AzDeploymentScriptLog', 'Save-AzDeploymentScriptLog', 'Remove-AzDeploymentScript')

#### <a name="azsql"></a>Az.Sql
* Menambahkan parameter sekunder yang dapat dibaca ke 'Invoke-AzSqlDatabaseFailover'
* Menambahkan cmdlet 'Disable-AzSqlServerActiveDirectoryOnlyAuthentication'
* Peringkat sensitivitas tersimpan saat mengklasifikasikan kolom dalam database.

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
* Buka halaman survei Azure PowerShell di 'Kirim Umpan Balik' [#11020]
* Tampilkan URL survei Azure PowerShell di 'Resolve-Error' [#11021]
* Menambahkan versi Az di UserAgent

#### <a name="azapimanagement"></a>Az.ApiManagement
* Menambahkan dukungan untuk mengambil dan mengonfigurasi Domain Kustom di Titik Akhir DeveloperPortal [#11007]
* 'Export-AzApiManagementApi' Menambahkan dukungan untuk mengunduh Api Definition dalam format Json [#9987]
* 'Import-AzApiManagementApi' Menambahkan dukungan untuk mengimpor definisi OpenApi 3.0 dari dokumen Json
* 'New-AzApiManagementIdentityProvider' dan 'Set-AzApiManagementIdentityProvider' Menambahkan dukungan untuk mengonfigurasi 'Signin Tenant' untuk AAD B2C Provider [#9784]

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan referensi ke System.Buffers secara eksplisit di csproj dan psd1.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola perangkat di Iot Hub. Cmdlet baru adalah:
    - 'Add-AzIotHubDevice'
    - 'Get-AzIotHubDevice'
    - 'Remove-AzIotHubDevice'
    - 'Set-AzIotHubDevice'
* Menambahkan dukungan untuk mengelola modul pada perangkat IoT target di Iot Hub. Cmdlet baru adalah:
    - 'Add-aziotHubModule'
    - 'Get-AziotHubModule'
    - 'Remove-aziotHubModule'
    - 'Set-aziotHubModule'
* Menambahkan cmdlet untuk mendapatkan string koneksi perangkat IoT target di Iot Hub.
* Menambahkan cmdlet untuk mendapatkan string koneksi modul pada perangkat IoT target di Iot Hub.
* Menambahkan dukungan untuk mendapatkan/mengatur perangkat induk perangkat IoT. Cmdlet baru adalah:
    - 'Get-AzIotHubDeviceParent'
    - 'Set-AzIotHubDeviceParent'
* Menambahkan dukungan untuk mengelola hubungan orang tua-anak perangkat.

#### <a name="azmonitor"></a>Az.Monitor
* Nilai output tetap untuk 'Get-AzMetricDefinition' [#9714]

#### <a name="aznetwork"></a>Az.Network
* Diperbarui Sql Management SDK.
* Memperbaiki masalah perbedaan penamaan di kelas PrivateLinkServiceConnectionState.
    - Memetakan bidang TindakanRequired ke ActionRequired.
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'

#### <a name="azresources"></a>Az.Resources
* Diperbaiki untuk bug referensi null di 'Get-AzRoleAssignment'
* Sakelar yang ditandai '-Force' dan '-PassThru' opsional di 'Remove-AzADGroup' [#10849]
* Memperbaiki masalah bahwa 'MailNickname' tidak kembali di 'Remove-AzADGroup' [#11167]
* Memperbaiki masalah bahwa operasi pipa 'Remove-AzADGroup' tidak berfungsi [#11171]
* Diperbaiki untuk bug referensi null di GetAzureRoleAssignmentCommand
* Menambahkan atribut perubahan yang melanggar untuk perubahan yang akan datang pada cmdlet kebijakan
* Diperbarui 'Get-AzResourceGroup' untuk melakukan pemfilteran tag grup sumber daya di sisi server
* Cmdlet Tag Diperpanjang untuk menerima -ResourceId
    - Get-AzTag -ResourceId
    - New-AzTag -ResourceId
    - Remove-AzTag -ResourceId
* Menambahkan cmdlet Tag baru
    - Update-AzTag -ResourceId
* Dibawa ScopedDeployment dari SDK 3.3.0

#### <a name="azsql"></a>Az.Sql
* Menambahkan PublicNetworkAccess ke 'New-AzSqlServer' dan 'Set-AzSqlServer'
* Menambahkan dukungan untuk konfigurasi cadangan Retensi Jangka Panjang untuk Database Terkelola
    - Dapatkan/Atur kebijakan LTR pada database terkelola
    - Dapatkan pencadangan LTR berdasarkan database terkelola, instans terkelola, atau berdasarkan lokasi
    - Menghapus cadangan LTR
    - Memulihkan cadangan LTR untuk membuat database terkelola baru
* Menambahkan MinimalTlsVersion ke New-AzSqlServer dan Set-AzSqlServer
* Menambahkan MinimalTlsVersion ke New-AzSqlInstance dan Set-AzSqlInstance
* Bumped SQL versi SDK untuk Az.Network

#### <a name="azstorage"></a>Az.Storage
* Didukung AllowProtectedAppendWrite in ImmutabilityPolicy
    - 'Set-AzRmStorageContainerImmutabilityPolicy'
* Menambahkan pesan peringatan perubahan yang melanggar untuk perubahan tipe AzureStorageTable dalam rilis mendatang
    - 'New-AzStorageTable'
    - 'Get-AzStorageTable'

#### <a name="azwebsites"></a>Az.Websites
* Menambahkan parameter Tag untuk 'New-AzAppServicePlan' dan 'Set-AzAppServicePlan'
* Hentikan eksekusi cmdlet jika pengecualian dilemparkan saat menambahkan domain kustom ke situs web
* Menambahkan dukungan untuk melakukan operasi untuk Layanan Aplikasi yang tidak berada dalam grup sumber daya yang sama dengan Paket Layanan Aplikasi
* Pembatasan akses yang diterapkan ke WebApp/Fungsi di grup sumber daya yang berbeda
* Memperbaiki masalah untuk mengatur nama host kustom untuk WebAppSlots

## <a name="350---february-2020"></a>3.5.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Telemetri sisi klien yang diperbarui.
* Az.IotHub menambahkan cmdlet untuk mendukung pengelolaan perangkat.
* Az.SqlVirtualMachine menambahkan cmdlets for Availability Group Listener.

#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan SubscriptionId, TenantId, dan waktu eksekusi ke dalam data telemetri sisi klien

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki kesalahan ketik di Contoh 1 dalam dokumentasi referensi untuk 'New-AzAutomationSoftwareUpdateConfiguration'

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* SDK yang diperbarui ke 7.0
* Pesan kesalahan yang ditingkatkan saat server merespons badan kosong

#### <a name="azcompute"></a>Az.Compute
* Nilai kosong yang diizinkan untuk ProximityPlacementGroupId selama pembaruan

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan cmdlet untuk mendapatkan definisi aturan terkelola yang dapat digunakan dalam WAF

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan dukungan untuk mengelola perangkat di Iot Hub. Cmdlet baru adalah:
    - 'Add-AzIotHubDevice'
    - 'Get-AzIotHubDevice'
    - 'Remove-AzIotHubDevice'
    - 'Set-AzIotHubDevice'

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki teks duplikat untuk Add-AzKeyVaultKey.md

#### <a name="azmonitor"></a>Az.Monitor
* Deskripsi tetap cmdlet Get-AzLog.
* Parameter baru yang disebut ActionGroupId ditambahkan ke perintah 'New-AzMetricAlertRuleV2'.
    - Pengguna dapat menyediakan ActionGroupId(string) atau ActionGorup(ActivityLogAlertActionGroup).

#### <a name="aznetwork"></a>Az.Network
* Menambahkan satu catatan parameter tambahan untuk parameter '-EnableProxyProtocol' untuk cmdlet 'New-AzPrivateLinkService'.
* Contoh FilterData Tetap di Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Menambahkan contoh Packet Capture untuk menangkap semua paket dalam dan luar dalam Start-AzVirtualNetworkGatewayConnectionPacketCapture.md dan Start-AzVirtualnetworkGatewayPacketCapture.md.
* Kebijakan Azure Firewall yang Didukung di VNet Firewalls
    - Tidak ada cmdlet baru yang ditambahkan. Melonggarkan pembatasan untuk kebijakan firewall pada firewall VNet

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Dukungan untuk Restore-as-files untuk database SQL.

#### <a name="azresources"></a>Az.Resources
* Cmdlet penyebaran templat yang difaktorkan ulang
    - Menambahkan cmdlet baru untuk mengelola penyebaran di grup manajemen: *-AzManagementGroupDeployment
    - Menambahkan cmdlet baru untuk mengelola penyebaran di lingkup penyewa: *-AzTenantDeployment
    - Refactored *-AzDeployment cmdlets untuk bekerja secara khusus di lingkup langganan
    - Dibuat alias *-AzSubscriptionDeployment for *-AzDeployment cmdlets
* Memperbaiki 'Update-AzADApplication' ketika parameter 'AvailableToOtherTenants' tidak diatur
* Dihapus ApplicationObjectWithoutCredentialParameterSet untuk menghindari AmbiguousParameterSetException.
* File bantuan yang diregenerasi

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk pemulihan titik waktu lintas pada waktu yang dikelola.
* Menambahkan dukungan untuk mengubah pembuatan perangkat keras Sql Managed Instance yang ada
* Memperbaiki contoh bantuan 'Update-AzSqlServerVulnerabilityAssessmentSetting': parameter/output properti - EmailAdmins

#### <a name="azsqlvirtualmachine"></a>Az.SqlVirtualMachine
* Menambahkan cmdlet untuk Pendengar Grup Ketersediaan

#### <a name="azstoragesync"></a>Az.StorageSync
* Kumpulan karakter yang didukung diperbarui di 'Invoke-AzStorageSyncCompatibilityCheck'.

## <a name="340---february-2020"></a>3.4.0 - Februari 2020
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Az.CosmosDB versi awal 0.1.0 dirilis
* Dukungan Az.Network ConnectionMonitor V2 ditambahkan

#### <a name="azaccounts"></a>Az.Accounts
* Nonaktifkan penyimpanan otomatis konteks saat AzureRmContext.json tidak tersedia
* Memperbarui referensi ke Azure Powershell Common ke 1.3.5-preview

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Get-AzApiManagementApiSchema** Memperbaiki mendapatkan skema Open-Api yang terkait dengan API   https://github.com/Azure/azure-powershell/issues/10626
* **New-AzApiManagementProduct** _ dan _ *Set-AzApiManagementProduct**
  - Memperbaiki dokumentasi untuk https://github.com/Azure/azure-powershell/issues/10472
* **Set-AzApiManagementApi** Contoh tambahan untuk menunjukkan cara memperbarui ServiceUrl menggunakan cmdlet

#### <a name="azcompute"></a>Az.Compute
* Batasi jumlah status VM hingga 100 untuk menghindari pelambatan saat Get-AzVM -Status dilakukan tanpa nama VM.
* Tambahkan cmdlet Update-AzDiskEncryptionSet
* Tambahkan parameter EncryptionType dan DiskEncryptionSetId ke cmdlet berikut:
    - New-AzDiskUpdateConfig, New-AzSnapshotUpdateConfig
* Tambahkan parameter ColocationStatus ke cmdlet Get-AzProximityPlacementGroup.

#### <a name="azdatafactory"></a>Az.DataFactory
* Perbarui versi ADF .Net SDK ke 4.7.0

#### <a name="azdeploymentmanager"></a>Az.DeploymentManager
* Menambahkan operasi LIST untuk sumber daya
* Menambahkan kemampuan untuk melakukan operasi pada langkah-langkah Pemeriksaan Kesehatan

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki kesalahan dokumen New-AzHDInsightCluster.

#### <a name="azkeyvault"></a>Az.KeyVault
* Tambahkan alias Nama ke atribut VaultName untuk membuat Remove-AzureKeyVault konsisten dengan New-AzureKeyVault.

#### <a name="aznetwork"></a>Az.Network
* Contoh baru ditambahkan ke Set-AzNetworkWatcherConfigFlowLog.md untuk menunjukkan skenario nonaktifkan Traffic Analytics.
* Tambahkan dukungan untuk menetapkan konfigurasi IP manajemen ke Azure Firewall - subnet khusus dan IP Publik yang akan digunakan firewall untuk lalu lintas manajemennya
    - Cmdlet New-AzFirewall diperbarui:
        - Menambahkan parameter -ManagementPublicIpAddress (tidak wajib) yang menerima objek Alamat IP Publik
        - Metode tambahan SetManagementIpConfiguration pada objek firewall - memerlukan subnet dan alamat IP Publik sebagai input - nama subnet harus 'AzureFirewallManagementSubnet'
* Dikoreksi Get-AzNetworkSecurityGroup contoh untuk menampilkan contoh untuk NSG alih-alih antarmuka jaringan.
* Memperbaiki kesalahan ketik dalam perintah New-AzVpnSite yang mencegah penyelesaian id sumber daya menyelesaikan parameter.
* Menambahkan dukungan untuk Confiugration Url dalam Rewrite Rules Action Set di Application Gateway
    - Cmdlet baru menambahkan:
        - New-AzApplicationGatewayRewriteRuleUrlConfiguration
    - Cmdlet diperbarui dengan parameter opsional - Konfigurasi Url
        - New-AzApplicationGatewayRewriteRuleActionSet
* Menambahkan suppport untuk sumber daya NetworkWatcher ConnectionMonitor versi 2

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Mendukung evaluasi kepatuhan sebelum menentukan sumber daya apa yang akan diperbaiki
    - Tambahkan parameter '-ResourceDiscoverMode' ke Start-AzPolicyRemediation
* Tambahkan cmdlet Get-AzPolicyMetadata untuk mendapatkan sumber daya metadata kebijakan
* diperbarui Get-AzPolicyState dan Get-AzPolicyStateSummary untuk API versi 2019-10-01

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk menghapus disk yang direplikasi.
* Azure Backup menambahkan dukungan untuk menambahkan tag saat membuat Vault Layanan Pemulihan.

#### <a name="azresources"></a>Az.Resources
* Jadikan -Scope opsional di cmdlet *-AzPolicyAssignment dengan langganan default ke konteks
* Menambahkan contoh pembuatan ADServicePrincipal dengan kata sandi dan kredensial utama

#### <a name="azsql"></a>Az.Sql
Perbaiki cmdlet New-AzSqlDatabaseSecondary untuk memeriksa keberadaan PartnerDatabaseName alih-alih keberadaan DatabaseName.

#### <a name="azstorage"></a>Az.Storage
* Mendukung atur Keytype Enkripsi Tabel/Antrean di Buat Akun Storage
    - New-AzStorageAccount
* Tampilkan RequestId saat StorageException tidak memiliki ExtendedErrorInformation
* Perbaiki Contoh 6 cmdlet Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Az.Websites
* Set-AzWebapp dan Set-AzWebappSlot mendukung properti AlwaysOn, MinTls, dan FtpsState
* Memperbaiki masalah saat mengatur HttpsOnly bersama dengan mengubah AppservicePlan pada saat yang sama menggunakan Perintah Set-AzWebApp tunggal, sedang mengatur ulang HttpsOnly ke nilai default

## <a name="330---january-2020"></a>3.3.0 - Januari 2020
#### <a name="azaccounts"></a>Az.Accounts
* Diperbarui Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAttestationServiceEndpointResourceId dan AzureAttestationServiceEndpointSuffix

#### <a name="azcdn"></a>Az.Cdn
* Tampilkan detail respons kesalahan dalam cmdlet New-AzCdnEndpoint

#### <a name="azcompute"></a>Az.Compute
* Perbaiki cmdlet Set-AzVMCustomScriptExtension untuk VM dengan disk OD terkelola yang tidak memiliki profil OS.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Nama parameter tetap yang digunakan dengan contoh New-AzContainerGroup

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Menambahkan cmdlet 'Get-AzDataBoxEdgeStorageContainer'
  - Dapatkan Kontainer Storage Edge
* Menambahkan cmdlet 'New-AzDataBoxEdgeStorageContainer'
  - Membuat Kontainer Edge Strorage baru
* Menambahkan cmdlet 'Remove-AzDataBoxEdgeStorageContainer'
  - Menghapus Kontainer Storage Edge
* Menambahkan cmdlet 'Invoke-AzDataBoxEdgeStorageContainer'
  - Meminta tindakan untuk me-refresh data di Edge Storage Container
* Menambahkan cmdlet 'Get-AzDataBoxEdgeStorageAccount'
  - Dapatkan Akun Storage Edge
* Menambahkan cmdlet 'New-AzDataBoxEdgeStorageAccount'
  - Membuat Akun Storage Edge baru
* Menambahkan cmdlet 'Remove-AzDataBoxEdgeStorageAccount'
  - Menghapus Akun Storage Edge
* Panggil cmdlet 'Invoke-AzDataBoxEdgeShare'
  - Meminta tindakan untuk me-refresh data pada berbagi
* Menambahkan cmdlet 'Set-AzDataBoxEdgeStorageAccountCredential'
  - Mengatur kredensial akun penyimpanan az databoxedge

#### <a name="azdatafactory"></a>Az.DataFactory
* Tambahkan properti AutoUpdateETA, LatestVersion, PushedVersion, TaskQueueId dan VersionStatus untuk Get-AzDataFactoryV2IntegrationRuntime cmd
* Memperbarui versi ADF .Net SDK ke 4.6.0
* Tambahkan parameter 'PublicIPs' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan pembuatan IR Azure-SSIS dengan alamat IP publik statis.

#### <a name="azdevtestlabs"></a>Az.DevTestLabs
* Menghapus link yang rusak di Get-AzDtlAllowedVMSizesPolicy.md

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki untuk masalah 10634 : Perbaiki referensi Objek null untuk menghapus eventhubnamespace

#### <a name="azhdinsight"></a>Az.HDInsight
* Perbaiki kesalahan Invoke-AzHDInsightHiveJob.md.

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
* Tingkatkan dependensi Microsoft.Azure.Management.Sql dari 1.36-preview ke 1.37-preview

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Azure Site Recovery mengubah dukungan untuk vms disk terkelola yang dienkripsi saat istirahat dengan kunci terkelola pelanggan untuk penyedia Azure ke Azure.
* Dukungan Azure Site Recovery untuk memasukkan set id enkripsi disk sebagai input opsional untuk mengaktifkan perlindungan untuk Vmware ke Azure.
* Dukungan Azure Site Recovery untuk memasukkan set id enkripsi disk sebagai input opsional di tingkat disk untuk mengaktifkan perlindungan bagi Vmware ke Azure.
* Dukungan Azure Site Recovery untuk memperbarui item yang dilindungi replikasi dengan peta set enkripsi disk untuk HyperV ke Azure.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki kesalahan dalam dokumen bantuan 'Remove-AzTag'.

#### <a name="azsql"></a>Az.Sql
* Perbaiki penilaian kerentanan atur fungsionalitas cmdlet dasar untuk mengerjakan master db untuk database azure dan batasi pada database sistem instans terkelola.
* Memperbaiki kesalahan saat membuat grup failover instans SQL

#### <a name="azsqlvirtualmachine"></a>Az.SqlVirtualMachine
* Tambahkan DR sebagai jenis Lisensi baru yang valid

#### <a name="azstorage"></a>Az.Storage
* Menambahkan pesan peringatan perubahan yang melanggar untuk perubahan Nilai DefaultAction di rilis mendatang
    - Update-AzStorageAccountNetworkRuleSet
* Dukungan Dapatkan waktu sinkronisasi terakhir akun Storage dengan menjalankan get-AzureRMStorageAccount dengan parameter -IncludeGeoReplicationStats
    - Get-AzureRMStorageAccount

## <a name="320---december-2019"></a>3.2.0 - Desember 2019

### <a name="general"></a>Umum
* Perbarui referensi di .psd1 untuk menggunakan jalur relatif untuk semua modul

#### <a name="azaccounts"></a>Az.Accounts
* Atur UserAgent yang benar untuk telemetri sisi klien untuk pratinjau Az 4.0
* Tampilkan pesan kesalahan yang ramah pengguna saat konteks null di pratinjau Az 4.0

#### <a name="azbatch"></a>Az.Batch
* Perbaiki masalah [#10602](https://github.com/Azure/azure-powershell/issues/10602), di mana **New-AzBatchPool** tidak mengirim 'VirtualMachineConfiguration.ContainerConfiguration' atau 'VirtualMachineConfiguration.DataDisks' ke server.

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.5.0

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Menambahkan dukungan pengecualian aturan terkelola WAF
* Tambahkan SocketAddr ke auto-complete

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Penanganan Pengecualian

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki nilai akses kesalahan yang berpotensi tidak diatur
* Managment Sertifikat Kriptografi Kurva Elips
    - Menambahkan dukungan untuk menentukan Kurva untuk Kebijakan Sertifikat

#### <a name="azmonitor"></a>Az.Monitor
* Menambahkan argumen opsional ke perintah Tambahkan diagnostik Pengaturan. Argumen pengalihan yang jika ada menunjukkan bahwa ekspor ke Log Analytics harus ke skema tetap (a.k.a. berdedikasi, tipe data)

#### <a name="aznetwork"></a>Az.Network
* Dukungan untuk IpGroups di Aplikasi AzureFirewall, Nat & Aturan Jaringan.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah di mana penyebaran template gagal membaca parameter template jika namanya bertentangan dengan beberapa nama parameter bawaan.
* Cmdlet kebijakan yang diperbarui untuk menggunakan api baru versi 2019-09-01 yang memperkenalkan dukungan pengelompokan dalam definisi kumpulan kebijakan.

#### <a name="azsql"></a>Az.Sql
* Pembuatan penyimpanan yang ditingkatkan dalam pemberdayaan otomatis Penilaian Kerentanan ke StorageV2

#### <a name="azstorage"></a>Az.Storage
* Dukungan menghasilkan token SAS berbasis Blob /Constainer Idenity dengan Konteks Storage berdasarkan autentikasi Oauth
    - New-AzStorageContainerSASToken
    - New-AzStorageBlobSASToken
* Dukungan mencabut Storage Kunci Delegasi Pengguna Akun, sehingga semua token SAS identitas dicabut
    - Revoke-AzStorageAccountUserDelegationKeys
* Tingkatkan ke Microsoft.Azure.Management. Storage 14.2.0, untuk mendukung API baru versi 2019-06-01.
* Dukungan KuotaGiB (Kuota Berbagi di Gibibye) untuk nilai lebih dari 5120 di bidang Manajemen cmdlet File Share dan menambahkan parameter 'Kuota' alias ke parameter 'QuotaGiB'.
    - New-AzRmStorageShare
    - Update-AzRmStorageShare
* Tambahkan parameter alias 'QuotaGiB' ke parameter 'Kuota'
    - Set-AzStorageShareQuota
* Memperbaiki masalah yang Set-AzStorageContainerAcl dapat membersihkan Kebijakan Akses yang tersimpan
    - Set-AzStorageContainerAcl

## <a name="310---november-2019"></a>3.1.0 - November 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Az.DataBoxEdge 1.0.0 dirilis
* Az.SqlVirtualMachine 1.0.0 dirilis

#### <a name="azcompute"></a>Az.Compute
* Fitur Aplikasi ulang VM
    - Menambahkan parameter Aplikasi ulang ke cmdlet Set-AzVM
* Fitur VM Scale Set AutomaticRepairs:
    - Tambahkan EnableAutomaticRepair, AutomaticRepairGracePeriod, dan AutomaticRepairMaxInstanceRepairsPercent parameter ke cmdlet berikut: New-AzVmssConfig Update-AzVmss
* Dukungan gambar galeri penyewa silang untuk New-AzVM
* Tambahkan 'Spot' ke argumen yang lebih lengkap dari parameter Prioritas di cmdlet New-AzVM, New-AzVMConfig, dan New-AzVmss
* Tambahkan parameter DiskIOPSReadWrite dan DiskMBpsReadWrite ke cmdlet Add-AzVmssDataDisk
* Ubah Parameter SourceImageId dari cmdlet New-AzGalleryImageVersion menjadi opsional
* Tambahkan parameter OSDiskImage dan DataDiskImage ke cmdlet New-AzGalleryImageVersion
* Tambahkan parameter HyperVGeneration ke cmdlet New-AzGalleryImageDefinition
* Tambahkan parameter SkipExtensionsOnOverprovisionedVMs ke cmdlet New-AzVmss, New-AzVmssConfig dan Update-AzVmss

#### <a name="azdataboxedge"></a>Az.DataBoxEdge
* Ditambahkan cmdlet `Get-AzDataBoxEdgeOrder`
    - Dapatkan Pesanan
* Ditambahkan cmdlet `New-AzDataBoxEdgeOrder`
    - Membuat Pesanan Baru
* Ditambahkan cmdlet `Remove-AzDataBoxEdgeOrder`
    - Menghapus Pesanan
* Perubahan cmdlet `New-AzDataBoxEdgeShare`
    - Sekarang membuat Berbagi Lokal
* Ditambahkan cmdlet `Set-AzDataBoxEdgeRole`
    - Sekarang IotRole dapat dipetakan ke Share
* Ditambahkan cmdlet `Invoke-AzDataBoxEdgeDevice`
    - Memanggil pembaruan pemindaian, unduh pembaruan, instal pembaruan di perangkat
* Ditambahkan cmdlet `Get-AzDataBoxEdgeTrigger`
    - Mendapatkan informasi tentang Pemicu
* Ditambahkan cmdlet `New-AzDataBoxEdgeTrigger`
    - Membuat Pemicu baru
* Ditambahkan cmdlet `Remove-AzDataBoxEdgeTrigger`
    - Menghapus Pemicu

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.4.0
* Tambahkan parameter 'ExpressCustomSetup' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan konfigurasi penyiapan dan komponen pihak ke-3 tanpa skrip penyiapan kustom.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui dokumentasi Get-AzDataLakeStoreDeletedItem dan Restore-AzDataLakeStoreDeletedItem

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah 10301: Perbaiki format tanggal Token SAS

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Tambahkan parameter MinimumTlsVersion ke Enable-AzFrontDoorCustomDomainHttps dan New-AzFrontDoorFrontendEndpointObject
* Tambahkan parameter HealthProbeMethod dan EnabledState ke New-AzFrontDoorHealthProbeSettingObject
* Tambahkan cmdlet baru untuk membuat Objec BackendPoolsSettings untuk diteruskan ke pembuatan / pembaruan Pintu Depan
    - New-AzFrontDoorBackendPoolsSettingObject

#### <a name="aznetwork"></a>Az.Network
* Ubah contoh opsi FilterData 'Start-AzVirtualNetworkGatewayConnectionPacketCapture.md' dan 'Start-AzVirtualnetworkGatewayPacketCapture.md'.

#### <a name="azprivatedns"></a>Az.PrivateDns
* Diperbarui PrivateDns .net sdk ke versi 1.0.0

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Pemulihan Situs Azure untuk memilih tipe disk saat mengaktifkan perlindungan.
* Perbaikan bug Pemulihan Situs Azure untuk pengeditan tindakan rencana pemulihan.
* Azure Backup SQL Pulihkan dukungan untuk menerima DBs filestream.

#### <a name="azrediscache"></a>Az.RedisCache
* Menambahkan parameter 'MinimumTlsVersion' di cmdlet 'New-AzRedisCache' dan 'Set-AzRedisCache'. Juga, menambahkan 'MinimumTlsVersion' dalam output cmdlet 'Get-AzRedisCache'.
* Menambahkan validasi pada parameter '-Size' untuk cmdlet 'Set-AzRedisCache' dan 'New-AzRedisCache'

#### <a name="azresources"></a>Az.Resources
- Cmdlet kebijakan yang diperbarui untuk menggunakan api baru versi 2019-06-01 yang memiliki properti EnforcementMode baru dalam penetapan kebijakan.
- Contoh bantuan definisi kebijakan yang diperbarui
- Perbaiki bug Remove-AZADServicePrincipal -ServicePrincipalName, lemparkan referensi null saat nama pokok layanan tidak ditemukan.
- Perbaiki bug New-AZADServicePrincipal, lemparkan referensi null saat penyewa tidak memiliki langganan.
- Ubah New-AzAdServicePrincipal untuk menambahkan kredensial hanya ke aplikasi terkait.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk database ReadReplicaCount.
* Memperbaiki Set-AzSqlDatabase saat redundansi zona tidak ditetapkan

## <a name="300---november-2019"></a>3.0.0 - November 2019
### <a name="general"></a>Umum
* Az.PrivateDns 1.0.0 dirilis

#### <a name="azaccounts"></a>Az.Accounts
* Tambahkan pesan deprekasi untuk alias 'Selesaikan-Kesalahan'.

#### <a name="azadvisor"></a>Az.Advisor
* Menambahkan kategori baru 'Operational Excellence' ke cmdlet Get-AzAdvisorRecommendation.

#### <a name="azbatch"></a>Az.Batch
* Berganti `CoreQuota` `BatchAccountContext` nama menjadi `DedicatedCoreQuota`. Ada juga yang baru `LowPriorityCoreQuota`.
  - Ini berdampak pada **Get-AzBatchAccount**.
* **New-AzBatchTask** `-ResourceFile` parameter sekarang mengambil koleksi `PSResourceFile` objek, yang dapat dibangun menggunakan cmdlet **New-AzBatchResourceFile** baru.
* Cmdlet **New-AzBatchResourceFile** baru untuk membantu membuat `PSResourceFile` objek. Ini dapat dipasok ke **New-AzBatchTask** pada `-ResourceFile` parameter.
  - Ini mendukung dua jenis file sumber daya baru selain cara yang `HttpUrl` ada:
    - `AutoStorageContainerName` file sumber daya berbasis mengunduh seluruh kontainer penyimpanan otomatis ke node Batch.
    - `StorageContainerUrl` file sumber daya berbasis mengunduh kontainer yang ditentukan dalam URL ke node Batch.
* Properti yang `ApplicationPackages` `PSApplication` dihapus dikembalikan oleh **Get-AzBatchApplication**.
  - Paket spesifik di dalam aplikasi sekarang dapat diambil menggunakan **Get-AzBatchApplicationPackage**. Contoh: `Get-AzBatchApplication -AccountName myaccount -ResourceGroupName myresourcegroup -ApplicationId myapplication`.
* Berganti `ApplicationId` nama menjadi `ApplicationName` di **Get-AzBatchApplicationPackage**, **New-AzBatchApplicationPackage**, **Remove-AzBatchApplicationPackage**, **Get-AzBatchApplication**, **New-AzBatchApplication**, **Remove-AzBatchApplication**, dan **Set-AzBatchApplication**.
  - `ApplicationId` Sekarang adalah alias dari `ApplicationName`.
* Menambahkan properti baru `PSWindowsUserConfiguration` ke `PSUserAccount`.
* Berganti `Version` nama menjadi `Name` on `PSApplicationPackage`.
* Berganti `BlobSource` nama menjadi `HttpUrl` on `PSResourceFile`.
* Properti yang dihapus `OSDisk` dari `PSVirtualMachineConfiguration`.
* Dihapus **Set-AzBatchPoolOSVersion**. Operasi ini tidak lagi didukung.
* Dihapus `TargetOSVersion` dari `PSCloudServiceConfiguration`.
* Berganti `CurrentOSVersion` nama menjadi `OSVersion` on `PSCloudServiceConfiguration`.
* Dihapus `DataEgressGiB` dan `DataIngressGiB` dari `PSPoolUsageMetrics`.
* Menghapus **Get-AzBatchNodeAgentSku** dan menggantinya dengan  **Get-AzBatchSupportedImage**.
  - **Get-AzBatchSupportedImage** mengembalikan data yang sama dengan **Get-AzBatchNodeAgentSku** tetapi dalam format yang lebih ramah.
  - Gambar baru yang tidak diverifikasi juga sekarang dikembalikan. Informasi tambahan tentang `Capabilities` dan `BatchSupportEndOfLife` untuk setiap gambar juga disertakan.
* Menambahkan kemampuan untuk me-mount sistem file jarak jauh pada setiap node kumpulan melalui parameter baru `MountConfiguration` **New-AzBatchPool**.
* Sekarang mendukung aturan keamanan jaringan yang memblokir akses jaringan ke kumpulan berdasarkan port sumber lalu lintas. Ini dilakukan melalui `SourcePortRanges` properti pada `PSNetworkSecurityGroupRule`.
* Saat menjalankan kontainer, Batch sekarang mendukung pelaksanaan tugas di direktori kerja kontainer atau di direktori kerja tugas Batch. Ini dikendalikan oleh `WorkingDirectory` properti pada `PSTaskContainerSettings`.
* Menambahkan kemampuan untuk menentukan koleksi IP `PSNetworkConfiguration` publik melalui properti baru `PublicIPs` . Ini menjamin node di Pool akan memiliki IP dari pengguna daftar yang disediakan IP.
* Ketika tidak ditentukan, nilai `WaitForSuccess` default on `PSSTartTask` sekarang `$True` (adalah `$False`).
* Ketika tidak ditentukan, nilai `Scope` default on `PSAutoUserSpecification` sekarang `Pool` (berada `Task` di Windows dan `Pool` di Linux).

#### <a name="azcdn"></a>Az.Cdn
* Memperkenalkan UrlRewriteAction dan CacheKeyQueryStringAction ke RulesEngine.
* Memperbaiki beberapa bug seperti Input 'Selector' yang hilang di cmdlet New-AzDeliveryRuleCondition.

#### <a name="azcompute"></a>Az.Compute
* Fitur Set Enkripsi Disk
    - Cmdlet baru: New-AzDiskEncryptionSetConfig New-AzDiskEncryptionSet Get-AzDiskEncryptionSet Remove-AzDiskEncryptionSet
    - Parameter DiskEncryptionSetId ditambahkan ke cmdlet berikut: Set-AzImageOSDisk Set-AzVMOSDisk Set-AzVmssStorageProfile Add-AzImageDataDisk New-AzVMDataDisk Set-AzVMDataDisk Add-AzVMDataDisk Add-AzVmssDataDisk Add-AzVmssVMDataDisk
    - Parameter DiskEncryptionSetId dan EncryptionType ditambahkan ke cmdlet berikut: New-AzDiskConfig New-AzSnapshotConfig
* Tambahkan parameter PublicIPAddressVersion ke New-AzVmssIPConfig
* Memindahkan FileUris ekstensi skrip kustom dari pengaturan publik ke pengaturan yang dilindungi
* Tambahkan ScaleInPolicy ke cmdlet New-AzVmss, New-AzVmssConfig dan Update-AzVmss
* Perubahan mencolok
    - Parameter UploadSizeInBytes digunakan sebagai pengganti DiskSizeGB untuk New-AzDiskConfig saat CreateOption Upload
    - PublishingProfile.Source.ManagedImage.Id diganti dengan StorageProfile.Source.Id di objek GalleryImageVersion

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.3.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbarui versi ADLS SDK (https://github.com/Azure/azure-data-lake-store-net/blob/preview-alpha/CHANGELOG.md#version-123-alpha), membawa perbaikan berikut
* Hindari melempar pengecualian saat tidak dapat merusak waktu pembuatan sampah atau entri direktori.
* Mengekspos pengaturan per batas waktu permintaan di adlsclient
* Memperbaiki melewati syncflag asli untuk pemulihan badoffset
* Perbaiki EnumerateDirectory untuk mengambil token kelanjutan setelah respons diperiksa
* Memperbaiki Bug Concat

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Memperbaiki kesalahan ketik lain-lain di seluruh modul

#### <a name="azhdinsight"></a>Az.HDInsight
* Memperbaiki bug bahwa pelanggan akan mendapatkan kesalahan 'Bukan string Base-64 yang valid' saat menggunakan Get-AzHDInsightCluster untuk mendapatkan klaster dengan penyimpanan ADLSGen1.
* Tambahkan parameter bernama 'ApplicationId' ke tiga cmdlet Add-AzHDInsightClusterIdentity, New-AzHDInsightClusterConfig dan New-AzHDInsightCluster sehingga pelanggan dapat memberikan id aplikasi utama layanan untuk mengakses Azure Data Lake.
* Mengubah Microsoft.Azure.Management.HDInsight dari 2.1.0 menjadi 5.1.0
* Dihapus lima cmdlet:
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
* Set parameter dihapus('Spark1', 'Spark2') dari Add-AzHDInsightConfigValue.
* Tambahkan contoh ke dokumen bantuan cmdlet Add-AzHDInsightSecurityProfile.
* Mengubah jenis output dari cmdlet berikut:
*  - Mengubah jenis output Get-AzHDInsightProperties dari CapabilitiesResponse ke AzureHDInsightCapabilities.
*  - Mengubah jenis output Remove-AzHDInsightCluster dari ClusterGetResponse menjadi bool.
*  - Mengubah jenis output Set-AzHDInsightGatewaySettings HttpConnectivitySettings menjadi GatewaySettings.
* Menambahkan beberapa kasus uji skenario.
* Hapus beberapa alias: 'Add-AzHDInsightConfigValues', 'Get-AzHDInsightProperties'.

#### <a name="aziothub"></a>Az.IotHub
* Melanggar perubahan:
    - Cmdlet 'Add-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter '__AllParameterSets' untuk cmdlet 'Add-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Get-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter '__AllParameterSets' untuk cmdlet 'Get-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Properti 'OperationsMonitoringProperties' dari jenis 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubProperties' telah dihapus.
    - Properti 'OperationsMonitoringProperties' dari jenis 'Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubInputProperties' telah dihapus.
    - Cmdlet 'New-AzIotHubExportDevice' tidak lagi mendukung alias 'New-AzIotHubExportDevices'.
    - Cmdlet 'New-AzIotHubImportDevice' tidak lagi mendukung alias 'New-AzIotHubImportDevices'.
    - Cmdlet 'Remove-AzIotHubEventHubConsumerGroup' tidak lagi mendukung parameter 'EventHubEndpointName' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter '__AllParameterSets' untuk cmdlet 'Remove-AzIotHubEventHubConsumerGroup' telah dihapus.
    - Cmdlet 'Set-AzIotHub' tidak lagi mendukung parameter 'OperationsMonitoringProperties' dan tidak ada alias yang ditemukan untuk nama parameter asli.
    - Kumpulan parameter 'UpdateOperationsMonitoringProperties' untuk cmdlet 'Set-AzIotHub' telah dihapus.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan Azure Site Recovery untuk mengonfigurasi sumber daya jaringan seperti NSG, IP publik, dan penyeimbang beban internal untuk Azure ke Azure.
* Azure Site Recovery Support untuk menulis ke disk terkelola untuk vMWare ke Azure.
* Azure Site Recovery Support to NIC reduction for vMWare to Azure.
* Azure Site Recovery Support ke jaringan yang dipercepat untuk Azure ke Azure.
* Azure Site Recovery Support to agent auto update for Azure to Azure.
* Azure Site Recovery Support to Standard SSD for Azure to Azure.
* Azure Site Recovery Support to Azure Disk Encryption two pass for Azure to Azure.
* Dukungan Pemulihan Situs Azure untuk melindungi disk yang baru ditambahkan untuk Azure ke Azure.
* Menambahkan fitur SoftDelete untuk VM dan menambahkan tes untuk softdelete

#### <a name="azresources"></a>Az.Resources
* Memperbarui perakitan dependensi Microsoft.Extensions.Caching.Memory dari 1.1.1 hingga 2.2

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
* Tambahkan bidang dan parameter baru untuk fitur Proxy Protocol V2.
    - Menambahkan properti EnableProxyProtocol di PrivateLinkService
    - Menambahkan properti LinkIdentifier di PrivateEndpointConnection
    - Diperbarui New-AzPrivateLinkService untuk menambahkan parameter opsional baru EnableProxyProtocol.
* Memperbaiki deskripsi parameter yang salah dalam dokumentasi referensi 'New-AzApplicationGatewaySku'
* Cmdlet baru untuk mendukung kebijakan firewall azure
* Menambahkan dukungan untuk RouteTables sumber daya anak dari VirtualHub
    - Cmdlet baru menambahkan:
        - Add-AzVirtualHubRoute
        - Add-AzVirtualHubRouteTable
        - Get-AzVirtualHubRouteTable
        - Remove-AzVirtualHubRouteTable
        - Set-AzVirtualHub
* Tambahkan dukungan untuk properti baru Sku dari VirtualHub dan VirtualWANType dari VirtualWan
    - Cmdlet diperbarui dengan parameter opsional:
        - New-AzVirtualHub : parameter ditambahkan Sku
        - Update-AzVirtualHub : parameter ditambahkan Sku
        - New-AzVirtualWan : parameter ditambahkan VirtualWANType
        - Update-AzVirtualWan : parameter ditambahkan VirtualWANType
* Menambahkan dukungan untuk properti EnableInternetSecurity untuk HubVnetConnection, VpnConnection, dan ExpressRouteConnection
    - Cmdlet baru menambahkan:
        - Update-AzureRmVirtualHubVnetConnection
    - Cmdlet diperbarui dengan parameter opsional:
        - New-AzureRmVirtualHubVnetConnection : parameter tambahan EnableInternetSecurity
        - New-AzureRmVpnConnection : parameter tambahan EnableInternetSecurity
        - Update-AzureRmVpnConnection : parameter tambahan EnableInternetSecurity
        - New-AzureRmExpressRouteConnection : parameter tambahan EnableInternetSecurity
        - Set-AzureRmExpressRouteConnection : parameter tambahan EnableInternetSecurity
* Menambahkan dukungan untuk Mengonfigurasi Kebijakan TopLevel WebApplicationFirewall
    - Cmdlet baru menambahkan:
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
* Memperbaiki subnet yang diperlukan dengan nama AzureBastionSubnet di 'PSBastion' dapat menjadi kasus yang tidak sensitif
* Dukungan untuk FQDNs Tujuan dalam Aturan Jaringan dan Menerjemahkan FQDN dalam Aturan NAT untuk Azure Firewall
* Menambahkan dukungan untuk RouteTables sumber daya tingkat atas dari IpGroup
    - Cmdlet baru menambahkan:
        - Baru-AzIpGroup
        - Remove-AzIpGroup
        - Dapatkan-AzIpGroup
        - Atur-AzIpGroup

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Hapus cmdlet Add-AzServiceFabricApplicationCertificate karena skenario ini dicakup oleh Add-AzVmssSecret.

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk memulihkan database yang dijatuhkan pada Instans Terkelola.
* Tidak digunakan lagi dari cmdlet audit kode lama.
* Menghapus alias yang tidak digunakan lagi:
* Get-AzSqlDatabaseIndexRecommendations (gunakan Get-AzSqlDatabaseIndexRecommendation sebagai gantinya)
* Get-AzSqlDatabaseRestorePoints (gunakan Get-AzSqlDatabaseRestorePoint sebagai gantinya)
* Hapus cmdlet Get-AzSqlDatabaseSecureConnectionPolicy
* Hapus alias untuk cmdlet Pengaturan Penilaian Kerentanan yang tidak digunakan lagi
* Deprecate Advanced Threat Detection Pengaturan cmdlets
* Menambahkan cmdlet untuk Menonaktifkan dan mengaktifkan rekomendasi sensitivitas pada kolom dalam database.

#### <a name="azstorage"></a>Az.Storage
* Dukungan aktifkan Berbagi File Besar saat membuat atau memperbarui akun Storage
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Saat menutup/mendapatkan Pegangan file, lewati periksa jalur input adalah direktori File atau File, untuk menghindari kegagalan dengan objek dalam status DeletePending
    -  Get-AzStorageFileHandle
    -  Close-AzStorageFileHandle

## <a name="280---october-2019"></a>2.8.0 - Oktober 2019
### <a name="general"></a>Umum
* Az.HealthcareApis 1.0.0 rilis

#### <a name="azaccounts"></a>Az.Accounts
* Perbarui telemetri dan penulisan ulang url untuk modul yang dihasilkan, perbaiki pengujian unit windows.

#### <a name="azapimanagement"></a>Az.ApiManagement
* **Set-AzApiManagementApi** - Menambahkan dukungan untuk Memperbarui Api ke ApiVersionSet
    - Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/10068

#### <a name="azautomation"></a>Az.Automation
* Tetap New-AzureAutomationSoftwareUpdateConfiguration cmdlet untuk parameter pengaturan reboot Linux.

#### <a name="azbatch"></a>Az.Batch
* **Get-AzBatchNodeAgentSku** sudah tidak digunakan lagi dan akan digantikan oleh **Get-AzBatchSupportImage** di versi 2.0.0.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter Prioritas, EvictionPolicy, dan MaxPrice ke cmdlet New-AzVM dan New-AzVmss
* Memperbaiki pesan peringatan dan dokumen bantuan untuk cmdlet Add-AzVMAdditionalUnattendContent dan Add-AzVMSshPublicKey
* Perbaiki -skipVmBackup pengecualian untuk VM Linux dengan disk terkelola untuk Set-AzVMDiskEncryptionExtension.
* Perbaiki bug dalam pengaturan enkripsi pembaruan di Set-AzVMDiskEncryptionExtension, dua skenario lulus.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan perintah CRUD untuk aliran data ADF V2: Set-AzDataFactoryV2DataFlow, Remove-AzDataFactoryV2DataFlow, dan Get-AzDataFactoryV2DataFlow.
* Menambahkan perintah tindakan untuk sesi debug aliran data ADF V2: Start-AzDataFactoryV2DataFlowDebugSession, Get-AzDataFactoryV2DataFlowDebugSession, Add-AzDataFactoryV2DataFlowDebugSessionPackage, Invoke-AzDataFactoryV2DataFlowDebugSessionCommand dan Stop-AzDataFactoryV2DataFlowDebugSession.
* Memperbarui versi ADF .Net SDK ke 4.2.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbaiki validasi akun sehingga akun dengan '-' dapat dilewati tanpa domain

#### <a name="azhealthcareapis"></a>Az.HealthcareApis
* Memperbarui versi powershell ke 1.0.0
* Memperbarui versi SDK ke 1.0.2
* Perbarui dalam pengujian untuk merujuk ke versi SDK baru
* Memperbarui struktur output dari bersarang ke pipih.

#### <a name="aziothub"></a>Az.IotHub
* Menambahkan sumber perutean baru: DigitalTwinChangeEvents
* Perbaikan bug kecil: Get-AzIothub tidak mengembalikan langgananId

#### <a name="azmonitor"></a>Az.Monitor
* Penerima grup aksi baru ditambahkan untuk grup aksi -ItsmReceiver -VoiceReceiver -ArmRoleReceiver -AzureFunctionReceiver -LogicAppReceiver -AutomationRunbookReceiver -AzureAppPushReceiver
* Gunakan skema peringatan umum yang diaktifkan untuk penerima. Ini tidak berlaku untuk SMS, Azure App push, ITSM dan Voice recievers
* Webhooks sekarang mendukung otentikasi direktori aktif Azure .

#### <a name="aznetwork"></a>Az.Network
* Tambahkan cmdlet baru Get-AzAvailableServiceAlias yang dapat dipanggil untuk mendapatkan alias yang dapat digunakan untuk Kebijakan Titik Akhir Layanan.
* Menambahkan dukungan untuk menambahkan pemilih lalu lintas ke Koneksi Gateway Jaringan Virtual
    - Cmdlet baru menambahkan:
        - New-AzureRmTrafficSelectorPolicy
    - Cmdlet diperbarui dengan parameter opsional -TrafficSelectorPolicies -New-AzureRmVirtualNetworkGatewayConnection -Set-AzureRmVirtualNetworkGatewayConnection
* Menambahkan dukungan untuk protokol ESP dan AH dalam konfigurasi aturan keamanan jaringan
    - Cmdlet yang diperbarui:
        - Tambahkan-AzNetworkSecurityRuleConfig
        - New-AzNetworkSecurityRuleConfig
        - Set-AzNetworkSecurityRuleConfig
* Meningkatkan penanganan pengecualian di cmdlet Cortex
* Generasi Baru dan SKU untuk VirtualNetworkGateways
  - Memperkenalkan Generasi baru untuk VirtualNetworkGateways.
  - Memperkenalkan SKU throughput tinggi baru untuk VirtualNetworkGateways.

#### <a name="azrediscache"></a>Az.RedisCache
* Dokumentasi referensi 'Set-AzRedisCache' yang diperbarui untuk menyertakan nilai yang hilang untuk parameter '-Size'

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk mengatur Administrator Direktori Aktif pada Instans Terkelola

#### <a name="azstorage"></a>Az.Storage
* Tingkatkan Storage Pustaka Klien ke 11.1.0
* Kontainer daftar dengan API pesawat Manajemen, akan mencantumkan dengan NextPageLink
    -  Get-AzRmStorageContainer
* Daftar akun Storage dari langganan, akan daftar dengan NextPageLink
    -  Dapatkan-AkunPenyimpananAz

#### <a name="azstoragesync"></a>Az.StorageSync
* Perbaiki Masalah 9810 di Reset-AzStorageSyncServerCertificate.

#### <a name="azwebsites"></a>Az.Websites
* Set-AzWebApp memperbarui ASP aplikasi gagal

## <a name="270---september-2019"></a>2.7.0 - September 2019
#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbarui deskripsi parameter '-Format' dalam dokumentasi referensi 'Set-AzApiManagementPolicy'
* Menghapus referensi cmdlet usang 'Update-AzApiManagementDeployment' dari dokumentasi referensi. Gunakan 'Set-AzApiManagement' sebagai gantinya.

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki contoh kesalahan ketik dalam dokumentasi referensi untuk 'Register-AzAutomationDscNode'
* Menambahkan klarifikasi tentang pembatasan OS ke Register-AzAutomationDSCNode
* Memperbaiki Start-AzAutomationRunbook cmdlet Null referensi pengecualian untuk opsi -Tunggu.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter UploadSizeInBytes tp New-AzDiskConfig
* Tambahkan parameter Inkremental ke New-AzSnapshotConfig
* Tambahkan fitur mesin virtual prioritas rendah:
    - Parameter MaxPrice, EvictionPolicy, dan Priority ditambahkan ke New-AzVMConfig.
    - Parameter MaxPrice ditambahkan ke cmdlet New-AzVmssConfig, Update-AzVM dan Update-AzVmss.
* Memperbaiki masalah referensi VM untuk cmdlet Get-AzAvailabilitySet saat mencantumkan semua kumpulan ketersediaan dalam langganan.
* Perbaiki pengecualian null untuk Get-AzRemoteDesktopFile.
* Perbaiki VHD Cari metode untuk posisi end-relative.
* Perbaiki masalah UltraSSD untuk New-AzVM dan Update-AzVM.

#### <a name="azdatafactory"></a>Az.DataFactory
* Menambahkan 3 perintah baru untuk ADF V2 - Add-AzDataFactoryV2TriggerSubscription, Remove-AzDataFactoryV2TriggerSubscription, dan Get-AzDataFactoryV2TriggerSubscriptionStatus
* Memperbarui versi ADF .Net SDK ke 4.1.3

#### <a name="azhdinsight"></a>Az.HDInsight
* Memanggil perubahan yang melanggar

#### <a name="aziothub"></a>Az.IotHub
* Tambahkan dukungan untuk meminta failover untuk IotHub ke wilayah pemulihan bencana geo-paired.
* Tambahkan dukungan untuk mengelola pengayaan pesan untuk IotHub. Cmdlet baru adalah:
    - Add-AzIotHubMessageEnrichment
    - Get-AzIotHubMessageEnrichment
    - Remove-AzIotHubMessageEnrichment
    - Set-AzIotHubMessageEnrichment

#### <a name="azmonitor"></a>Az.Monitor
* Menunjuk ke SDK Monitor terbaru, yaitu pratinjau 0.24.1
   - Menambahkan perubahan non-pengereman pada cmdlet Metrik, yaitu pencacahan Unit mendukung beberapa nilai baru. Ini adalah cmdlet baca-saja, sehingga tidak akan ada perubahan dalam input cmdlet.
   - Versi api dari permintaan **ActionGroups** sekarang **2019-06-01**, sebelum **2018-03-01**. Tes skenario telah diperbarui untuk mengakomodasi perubahan ini.
   - Konstruktor untuk kelas **EmailReceiver** dan **WebhookReceiver** menambahkan satu argumen wajib baru, yaitu nilai Boolean yang disebut **useCommonAlertSchema**. Saat ini, nilainya ditetapkan **palsu** untuk menyembunyikan perubahan yang melanggar ini dari cmdlet. **CATATAN**: ini adalah perubahan sementara yang harus divalidasi oleh tim Peringatan.
   - Urutan argumen untuk konstruktor **Sumber** kelas (terkait dengan kelas **ScheduledQueryRuleSource** ) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua tes unit untuk diperbaiki: mereka dikompilasi, tetapi gagal lulus tes.
   - Urutan argumen untuk konstruktor **AlertingAction** kelas (terkait dengan kelas **ScheduledQueryRuleSource** ) berubah dari SDK sebelumnya. Perubahan ini membutuhkan dua tes unit untuk diperbaiki: mereka dikompilasi, tetapi gagal lulus tes.
* Mendukung kriteria Ambang Batas Dinamis untuk peringatan metrik V2
    - New-AzMetricAlertRuleV2Criteria: sekarang creats kriteria ambang dinamis juga
    - Add-AzMetricAlertRuleV2: sekarang terima kriteria ambang batas dinamis juga
* Penyempurnaan cmdlet Aturan Kueri Terjadwal (SQR)
 - Cmdlet akan menerima paramater 'Lokasi' dalam kedua format, baik lokasi (misalnya eastus) atau nama tampilan lokasi (misalnya AS Timur)
 - Ilustrasi parameter 'Diaktifkan' dalam file bantuan dengan benar
 - Menambahkan contoh untuk parameter opsional 'ActionGroup'
 - File bantuan yang ditingkatkan secara keseluruhan
* Memperbaiki bug dalam menentukan jenis cakupan untuk 'Set-AzActionRule'

#### <a name="aznetwork"></a>Az.Network
* Memperbaiki contoh yang salah dalam dokumentasi referensi 'New-AzApplicationGateway'
* Tambahkan catatan di dokumentasi referensi 'Get-AzNetworkWatcherPacketCapture' tentang mengambil semua properti untuk pengambilan paket
* Contoh tetap dalam dokumentasi referensi 'Test-AzNetworkWatcherIPFlow' untuk menghitung NIC dengan benar
* Penguraian pengecualian cloud yang ditingkatkan untuk menampilkan detail tambahan jika ada
* Penguraian pengecualian cloud yang ditingkatkan untuk menangani jenis pengecualian SDK tambahan
* Memperbaiki pemetaan model Aturan Keamanan yang salah
* Menambahkan properti ke antarmuka jaringan untuk fitur ip pribadi
    - Menambahkan properti 'PrivateEndpoint' sebagai jenis PSResourceId ke PSNetworkInterface
    - Menambahkan properti 'PrivateLinkConnectionProperties' sebagai jenis PSIpConfigurationConnectivityInformation to PSNetworkInterfaceIPConfiguration
    - Menambahkan kelas model baru PSIpConfigurationConnectivityInformation
* Menambahkan ApplicationRuleProtocolType baru 'mssql' untuk sumber daya Azure Firewall
* Dukungan MultiLink di Virtual WAN
    - Cmdlet baru
        - New-AzVpnSiteLink
        - New-AzVpnSiteLinkConnection
    - Cmdlet yang diperbarui:
        - New-VpnSite
        - Update-VpnSite
        - New-VpnConnection
        - Update-VpnConnection
* Memperbaiki dokumen untuk beberapa contoh PowerShell untuk menggunakan cmdlet Az, bukan cmdlet AzureRM

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbarui Objek AzureVMpolicy dengan Atribut ProtectedItemsCount
* Pengujian Tambahan untuk kebijakan VM dan Pemulihan Akun Storage Asli

#### <a name="azresources"></a>Az.Resources
* Perbaiki bug di mana New-AzRoleAssignment tidak dapat dipanggil tanpa parameter Scope.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki kesalahan ketik misalnya untuk dokumentasi referensi 'Update-AzServiceFabricReliability'
* Menambahkan cmdlet baru untuk mengelola appliaction dan layanan:
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
* Ditingkatkan Service Fabric SDK ke versi 1.2.0 yang menggunakan penyedia sumber daya kain layanan api-versi 2019-03-01.

#### <a name="azsignalr"></a>Az.Signalr
* Tambahkan Pembaruan, Restart, CheckNameAvailability, GetUsage Cmdlets

#### <a name="azsql"></a>Az.Sql
* Perbarui contoh dalam dokumentasi referensi untuk 'Get-AzSqlElasticPool'
* Menambahkan contoh vCore untuk membuat kumpulan elastis (New-AzSqlElasticPool).
* Hapus validasi EmailAddresses dan periksa bahwa EmailAdmins tidak salah jika EmailAddresses kosong di Set-AzSqlServerAdvancedThreatProtectionPolicy dan Set-AzSqlDatabaseAdvancedThreatProtectionPolicy
* Penghapusan pengaturan audit server /database yang diaktifkan ketika beberapa pengaturan diagnostik yang memungkinkan kategori audit ada.
* Memperbaiki validasi alamat email di beberapa cmdlet Sql Vulnerability Assessment (Update-AzSqlDatabaseVulnerabilityAssessmentSetting, Update-AzSqlServerVulnerabilityAssessmentSetting, Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting dan Update-AzSqlInstanceVulnerabilityAssessmentSetting).

#### <a name="azstorage"></a>Az.Storage
* Contoh terbaru dalam dokumentasi referensi untuk 'Get-AzStorageAccountKey'
* Dalam upload/Downalod Azure File,support perserve properti File SMB sumber (File Attributtes, File Creation Time, File Last Write Time) di file tujuan
    -  Set-AzStorageFileContent
    -  Get-AzStorageFileContent
* Perbaiki gumpalan blok Upload dengan properti/metadate gagal pada kontainer diaktifkan ImmutabilityPolicy.
    -  Set-AzStorageBlobContent
* Mendukung mengelola berbagi Azure File dengan API bidang Manajemen
    -  New-AzRmStorageShare
    -  Get-AzRmStorageShare
    -  Update-AzRmStorageShare
    -  Remove-AzRmStorageShare

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki masalah saat Tag webapp dihapus saat memigrasikan App ke ASP baru di mana Tag webapp dihapus saat memigrasikan App ke ASP baru
* Memperbaiki Publish-AzureWebapp untuk bekerja di Linux dan windows
* Perbarui contoh dalam dokumentasi referensi 'Get-AzWebAppPublishingProfile'

## <a name="260---august-2019"></a>2.6.0 - Agustus 2019
#### <a name="general"></a>Umum
* Memperbaiki kesalahan ketik lain-lain di berbagai modul

#### <a name="azaccounts"></a>Az.Accounts
* Mendukung MSI yang ditetapkan pengguna di Azure Functiosn Authentication (#9479)

#### <a name="azaks"></a>Az.Aks
* Memperbaiki masalah dengan output untuk 'Get-AzAks'
    * Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/9847

#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/9351
    - Perbarui versi .net nuget, yang tidak memberlakukan pembatasan pada productId, apiId, groupId dan userId
* **Get-AzApiManagementProduct** - Menambahkan dukungan untuk query produk menggunakan Api.
  https://github.com/Azure/azure-powershell/issues/9482
* **New-AzApiManagementApiRevision** - Perbaiki masalah di mana ApiRevisionDescription tidak ditetapkan saat membuat revisi api baru https://github.com/Azure/azure-powershell/issues/9752
* Memperbaiki kesalahan ketik dalam model 'PsApiManagementOAuth2AuthrozationServer' ke 'PsApiManagementOAuth2AuthorizationServer'

#### <a name="azbatch"></a>Az.Batch
* Memperbaiki kesalahan ketik dalam pesan bantuan dan dokumentasi untuk memanfaatkan Windows

#### <a name="azcdn"></a>Az.Cdn
* Memperbaiki kesalahan ketik di pembantu konversi modul CDN

#### <a name="azcompute"></a>Az.Compute
* Tambahkan VmssId ke cmdlet New-AzVMConfig
* Tambahkan TerminateScheduledEvents dan TerminateScheduledEventNotBeforeTimeoutInMinutes parameter untuk New-AzVmssConfig dan Update-AzVmss
* Menambahkan properti HyperVGeneration ke objek gambar VM
* Menambahkan fitur Host dan HostGroup
    - Cmdlet baru: New-AzHostGroup New-AzHost Get-AzHostGroup Get-AzHost Remove-AzHostGroup Remove-AzHost
    - Parameter HostId ditambahkan ke New-AzVMConfig dan New-AzVM
* Perbarui contoh dalam dokumentasi 'Invoke-AzVMRunCommand' untuk menggunakan nama parameter yang benar
* Perbarui deskripsi '-VolumeType' di dokumentasi referensi 'Set-AzVMDiskEncryptionExtension' dan 'Set-AzVmssDiskEncryptionExtension'

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbaiki kesalahan ketik untuk memanfaatkan 'Windows' dalam dokumentasi 'New-AzDataFactoryEncryptValue'
* Memperbarui versi ADF .Net SDK ke 4.1.2
* Tambahkan parameter 'DataProxyIntegrationRuntimeName', 'DataProxyStagingLinkedServiceName' dan 'DataProxyStagingPath' untuk cmd 'Set-AzureRmDataFactoryV2IntegrationRuntime' untuk mengaktifkan pengaturan Self-Hosted Integration Runtime sebagai proxy untuk SSIS Integration Runtime
* Memperbarui PSTriggerRun untuk menampilkan pipeline, pesan, dan properti yang dipicu, dan PSActivityRun untuk menampilkan jenis aktivitas

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbaiki menggantung Get-DataLakeStoreDeletedItem untuk setiap kesalahan atau pengecualian jarak jauh.

#### <a name="azeventhub"></a>Az.EventHub
* Memperbaiki masalah #9658 : Typo VirtualNteworkRule parameter dalam Set-AzEventHubNetworkRuleSet
* Memperbaiki masalah # 9558: Set-AzEventHubNamespace menggunakan PATCH bukan PUT
* menambahkan parameter EnableKafka ke cmdlet Set-AzEventHubNamespace
* Memperbaiki masalah #9786: tidak dapat membuat aturan dengan hak Hanya Mendengarkan

#### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* Kesalahan ketik dokumentasi tetap di mana 'Azure' adalah semua huruf kecil

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam dokumentasi bantuan

#### <a name="aznetwork"></a>Az.Network
* New-AzPrivateLinkServiceIpConfig diperbarui
    - Usang parameter 'PublicIpAddress' karena ini tidak pernah digunakan di sisi server.
    - Menambahkan satu parameter opsional 'Primary' yang menunjukkan konfigurasi ip saat ini adalah yang utama atau tidak.
* Peningkatan penanganan pengecualian kesalahan permintaan dari SDK -Memperbaiki masalah yang sebelumnya pengecualian SDK tidak ditangani dengan benar yang menghasilkan detail kesalahan utama yang tidak ditampilkan
* Logika validasi yang disesuaikan untuk Awalan IP Ipv6 untuk memeriksa panjang awalan IPv6 yang benar.
* Diperbarui Get-AzVirtualNetworkSubnetConfig: Menambahkan parameter yang diatur untuk mendapatkan dengan id sumber daya subnet.
* Deskripsi terbaru parameter Lokasi untuk AzNetworkServiceTag

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Dokumentasi terbaru untuk 'New-AzOperationalInsightsLinuxSyslogDataSource'
    - Contoh tambahan
    - Deskripsi yang diperbarui untuk parameter '-Nama'
* Menambahkan contoh untuk New-AzOperationalInsightsWindowsEventDataSource
* Mengubah deskripsi parameter -Nama untuk New-AzOperationalInsightsWindowsEventDataSource

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbarui 'Get-AzRecoveryServicesBackupJobDetail.md'

#### <a name="azresources"></a>Az.Resources
* Menambahkan dukungan untuk api baru versi 2019-05-10 untuk Microsoft.Resource
    - Tambahkan dukungan untuk 'copy.count = 0' untuk variabel, sumber daya, dan properti
    - Sumber daya dengan 'condition = false' atau 'copy.count = 0' akan dihapus dalam mode lengkap
* Menambahkan contoh menetapkan kebijakan di tingkat langganan untuk membantu dokumen

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaiki untuk masalah #9658 : Typo VirtualNetworkRule parameter dalam Set-AzServiceBusNetworkRuleSet
* Memperbaiki masalah #9786: tidak dapat membuat aturan dengan hak Hanya Mendengarkan
* Menambahkan perintah baru 'Test-AzServiceBusNameAvailability' untuk memeriksa ketersediaan nama untuk antrean dan topik

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki tambahkan bug cmdlet tipe node:
    - NullReferenceException bug ketika grup sumber daya memiliki vmss lain yang tidak terkait dengan cluster kain layanan. Memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8681
    - Perbaiki bug di mana cmdlet gagal jika virtualNetwork berada di grup sumber daya yang berbeda dari klaster. memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/8407
    - Menonaktifkan cmdlet Add-AzServiceFabricApplicationCertificate

#### <a name="azsql"></a>Az.Sql
* Perbarui dokumentasi cmdlet Audit lama.

#### <a name="azstorage"></a>Az.Storage
* Perbarui bantuan untuk Get/Close-AzStorageFileHandle, dengan menambahkan lebih banyak skenario ke contoh cmdlet dan memperbarui deskripsi parameter
* Mendukung StandardBlobTier dalam mengunggah blob dan menyalin blob
    -  Set-AzStorageBlobContent
    -  Start-AzStorageBlobCopy
* Mendukung Rehydrate Priority dalam blob salinan
    -  Start-AzStorageBlobCopy

#### <a name="azwebsites"></a>Az.Websites
* Tambahkan klarifikasi seputar parameter -AppSettings di Set-AzWebApp dan Set-AzWebAppSlot

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
* Tambahkan properti yang hilang (ComputerName, OsName, OsVersion, dan HyperVGeneration) objek tampilan instans VM.

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbaiki kesalahan ketik dalam parameter Remove-AzContainerRegistryReplication untuk Replikasi
    - Informasi lebih lanjut di sini https://github.com/Azure/azure-powershell/issues/9633

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 4.1.0
* Memperbaiki kesalahan ketik dalam dokumentasi untuk 'Get-AzDataFactoryV2PipelineRun'

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmmdlet baru ditambahkan untuk menghasilkan token SAS: New-AzEventHubAuthorizationRuleSASToken
* menambahkan pesan verifikasi dan kesalahan untuk hak authorizationrules jika hanya 'Kelola' yang ditetapkan

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan untuk menentukan KeySize untuk Kebijakan Sertifikat

#### <a name="azlogicapp"></a>Az.LogicApp
* Perbaiki untuk Get-AzIntegrationAccountMap untuk mencantumkan semua jenis peta
    - Menambahkan parameter MapType baru untuk pemfilteran

#### <a name="azmanagedservices"></a>Az.ManagedServices
* Menambahkan dukungan untuk API versi 2019-06-01 (GA)

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk titik akhir pribadi dan layanan tautan pribadi
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
        - Menambahkan parameter opsional -PrivateEndpointNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan pada titik akhir privat di subnet ini.
        - Menambahkan parameter opsional -PrivateLinkServiceNetworkPoliciesFlag yang mengonfigurasi apakah akan menerapkan kebijakan jaringan pada layanan tautan pribadi di subnet ini.
* Parameter cmdlet AzPrivateLinkService 'ServiceName' diganti namanya menjadi 'Nama' dengan alias 'ServiceName' untuk kompatibilitas ke belakang
* Aktifkan protokol ICMP untuk konfigurasi aturan keamanan jaringan
    - Cmdlet yang diperbarui
        - Tambahkan-AzNetworkSecurityRuleConfig
        - New-AzNetworkSecurityRuleConfig
        - Set-AzNetworkSecurityRuleConfig
* Tambahkan ConnectionProtocolType (Ikev1/Ikev2) sebagai parameter yang dapat dikonfigurasi untuk New-AzVirtualNetworkGatewayConnection
* Tambahkan PrivateIpAddressVersion in LoadBalancerFrontendIpConfiguration
    - Cmdlet yang diperbarui:
        - New-AzLoadBalancerFrontendIpConfig
        - Add-AzLoadBalancerFrontendIpConfig
        - Set-AzLoadBalancerFrontendIpConfig
* Application Gateway New-AzApplicationGatewayProbeConfig pembaruan perintah untuk mendukung port kustom di Probe
    - Diperbarui New-AzApplicationGatewayProbeConfig: Menambahkan port parameter opsional yang digunakan untuk menyelidiki server backend. Parameter ini berlaku untuk SKU Standard_V2 dan WAF_V2.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Versi default yang diperbarui untuk pencarian tersimpan menjadi 1.
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
* Panggilan layanan yang diperbarui untuk kontainer Tidak Terdaftar untuk Berbagi File Azure
* Perbarui 'Set-AzRecoveryServicesAsrAlertSetting.md'

#### <a name="azresources"></a>Az.Resources
- Hapus cmdlet yang hilang yang dirujuk dalam dokumentasi 'New-AzResourceGroupDeployment'
- Cmdlet kebijakan yang diperbarui untuk menggunakan api baru versi 2019-01-01

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmmdlet baru ditambahkan untuk menghasilkan token SAS: New-AzServiceBusAuthorizationRuleSASToken
* menambahkan pesan verifikasi dan kesalahan untuk hak authorizationrules jika hanya 'Kelola' yang ditetapkan

#### <a name="azsql"></a>Az.Sql
* Memperbaiki contoh yang hilang untuk cmdlet Set-AzSqlDatabaseSecondary
* Memperbaiki pemindaian berulang Penilaian Kerentanan yang ditetapkan tanpa memberikan alamat email apa pun
* Perbaiki kesalahan ketik kecil dalam pesan warining.

#### <a name="azstorage"></a>Az.Storage
* Perbarui contoh dalam dokumentasi referensi untuk 'Get-AzStorageAccount' untuk menggunakan nama parameter yang benar

#### <a name="azstoragesync"></a>Az.StorageSync
* Menambahkan cmdlet Invoke-AzStorageSyncChangeDetection.
* Perbaiki Masalah 9551 untuk menghormati TierFilesOlderThanDays

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug di mana beberapa properti SiteConfig tidak dikembalikan oleh Get-AzWebApp dan Set-AzWebApp
* Menambahkan parameter Lokasi baru ke Get-AzDeletedWebApp dan Restore-AzDeletedWebApp
* Memperbaiki bug dengan kloning slot aplikasi web menggunakan New-AzWebApp -IncludeSourceWebAppSlots

## <a name="240---july-2019"></a>2.4.0 - Juli 2019
#### <a name="azaccounts"></a>Az.Accounts
* Menambahkan dukungan untuk cmdlet profil
* Menambahkan dukungan untuk lingkungan dan bidang data dalam cmdlet yang dihasilkan
* Perbaiki bug di mana titik akhir yang salah digunakan dalam beberapa kasus untuk cmdlet bidang data di Windows PowerShell

#### <a name="azadvisor"></a>Az.Advisor
* Rilis GA dari Az.Advisor
* Modul ini sekarang disertakan sebagai bagian dari modul roll-up.`Az`

#### <a name="azapimanagement"></a>Az.ApiManagement
* Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/8671
    - **Get-AzApiManagementSubscription**
        - Menambahkan dukungan untuk kueri langganan oleh Pengguna dan Produk
        - Menambahkan dukungan untuk kueri menggunakan Scope '/', '/apis', '/apis/echo-api'
* Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/9307 dan https://github.com/Azure/azure-powershell/issues/8432
    - **Import-AzApiManagementApi**
        - Menambahkan dukungan untuk menentukan 'ApiVersion' dan 'ApiVersionSetId' saat mengimpor Apis

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug cmdlet Set-AzAutomationConnectionFieldValue untuk menangani nilai string.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter HyperVGeneration ke New-AzImageConfig

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui output aktivitas get berjalan, menjalankan pipeline, dan mendapatkan pemicu berjalan cmdlet ADF untuk mendukung pipa Select-Object.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbaiki kesalahan ketik dalam dokumentasi 'New-AzEventGridSubscription'

#### <a name="aziothub"></a>Az.IotHub
* Tambahkan dukungan untuk meregenerasi kunci kebijakan otorisasi.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan 'RoutingPreference' ke tag ip publik
* Meningkatkan contoh untuk dokumentasi referensi 'Get-AzNetworkServiceTag'

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi null di Get-AzPolicyState
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/9446

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Model sumber data CustomLog tetap dikembalikan dalam Get-AzOperationalInsightsDataSource

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Perbaiki untuk perintah get-policy untuk IaaSVMs

#### <a name="azresources"></a>Az.Resources
   - Memperbaiki teks bantuan untuk parameter Get-AzPolicyState -Top
   - Tambahkan dukungan paging sisi klien untuk Get-AzPolicyAlias
   - Tambahkan parameter baru untuk Set-AzPolicyAssignment, -PolicyParameters dan -PolicyParametersObject
   - Beberapa pembaruan doc dan contoh untuk cmdlet Kebijakan

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaiki masalah # 4938 - New-AzureRmServiceBusQueue mengembalikan BadRequest saat mengatur MaxSizeInMegabytes

#### <a name="azsql"></a>Az.Sql
* Menambahkan cmdlet Instance Failover Group dari rilis pratinjau ke rilis publik
* Mendukung Azure SQL Server\Database Auditing dengan cmdlet baru.
    - Set-AzSqlServerAudit
    - Get-AzSqlServerAudit
    - Remove-AzSqlServerAudit
    - Set-AzSqlDatabaseAudit
    - Get-AzSqlDatabaseAudit
    - Remove-AzSqlDatabaseAudit
* Menghapus batasan email dari setelan Penilaian Kerentanan

#### <a name="azstorage"></a>Az.Storage
* Ubah 2 parameter '-IndexDocument' dan '-ErrorDocument404Path' dari yang diperlukan menjadi opsional dalam cmdlet:
    -  Enable-AzStorageStaticWebsite
* Memperbarui bantuan Get-AzStorageBlobContent dengan menambahkan contoh
* Tampilkan informasi kesalahan lainnya saat cmdlet gagal dengan StorageException
* Mendukung membuat atau memperbarui akun Storage dengan Azure Files AAD DS Authentication
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Mendukung daftar atau menutup gagang file dari berbagi file, direktori file, atau file
    - Get-AzStorageFileHandle
    - Close-AzStorageFileHandle

#### <a name="azstoragesync"></a>Az.StorageSync
* Modul ini sekarang disertakan sebagai bagian dari modul roll-up.`Az`

## <a name="232---june-2019"></a>2.3.2 - Juni 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbaiki bug dengan URL yang salah digunakan dalam beberapa kasus untuk panggilan Fungsi
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/8983
* Memperbaiki Masalah dengan alias dari AzureRM ke cmdlet Az
  - Set-AzureRmVMBootDiagnostics -> Set-AzVMBootDiagnostic
  - Export-AzureRMLogAnalyticThrottledRequests -> Export-AzLogAnalyticThrottledRequest

#### <a name="azcompute"></a>Az.Compute
* New-AzVm dan New-AzVmss kumpulan parameter sederhana sekarang menerima parameter 'ProximityPlacementGroup'.
* Memperbaiki kesalahan ketik dalam dokumentasi referensi 'New-AzVM'

#### <a name="azdns"></a>Az.Dns
* Memperbaiki kesalahan ketik dalam contoh bantuan 'Set-AzDnsZone'.

#### <a name="azeventgrid"></a>Az.EventGrid
* Diperbarui untuk menggunakan versi API 2019-06-01.
* Cmdlet baru:
    - New-AzureRmEventGridDomain
        - Membuat Domain Azure Event Grid baru.
    - Get-AzureRmEventGridDomain
        - Mendapatkan detail Domain Grid Peristiwa, atau mendapatkan daftar semua Domain Grid Peristiwa di langganan Azure saat ini.
    - Remove-AzureRmEventGridDomain
        - Menghapus Domain Azure Event Grid.
    - New-AzureRmEventGridDomainKey
        - Meregenerasi kunci akses bersama untuk Domain Grid Peristiwa Azure.
    - Get-AzureRmEventGridDomainKey
        - Mendapatkan kunci akses bersama yang digunakan untuk memublikasikan acara ke Domain Grid Peristiwa.
    - New-AzureRmeventGridDomainTopic:
        - Membuat Topik Domain Azure Event Grid baru.
    - Get-AzureRmEventGridDomainTopic
        - Mendapatkan detail Topik Domain Grid Peristiwa, atau mendapatkan daftar semua Topik Domain Grid Peristiwa di bawah Domain Grid Peristiwa tertentu di Azure saat ini
    - Remove-AzureRmeventGridDomainTopic:
        - Menghapus Topik Domain Azure Event Grid yang sudah ada.
* Cmdlet yang diperbarui:
    - New-AzureRmEventGridSubscription/Update-AzureRmEventGridSubscription:
        - Tambahkan parameter wajib baru untuk mendukung perpipaan untuk Domain Grid Peristiwa baru dan Topik Domain Grid Peristiwa untuk memungkinkan pembuatan langganan acara baru di bawah sumber daya ini.
        - Tambahkan parameter wajib baru untuk menentukan nama Domain Grid Peristiwa baru dan/atau nama Topik Domain Grid Peristiwa untuk memungkinkan pembuatan langganan acara baru di bawah sumber daya ini.
        - Tambahkan kumpulan Parameter baru untuk domain dan topik domain untuk memungkinkan penggunaan kembali parameter yang ada (misalnya, EndPointType, SubjectBeginsWith, dll).
        - Tambahkan parameter opsional baru untuk menentukan:
            - Tanggal kedaluwarsa langganan acara,
            - Parameter pemfilteran tingkat lanjut.
        - Tambahkan enum baru untuk servicebusqueue sebagai tujuan.
        - Melarang penggunaan opsi 'All' in -IncludedEventType dan ganti dengan
    - Get-AzEventGridTopic, Get-AzEventGridDomain, Get-AzEventGridDomainTopic, Get-AzEventGridSubscription:
        - Tambahkan parameter opsional baru (Top, ODataQuery dan NextLink) untuk mendukung hasil pagination dan pemfilteran.
    - Remove-AzureRmEventGridSubscription
        - Tambahkan parameter wajib baru untuk mendukung perpipaan untuk Domain Grid Peristiwa dan Topik Domain Grid Peristiwa untuk memungkinkan menghapus langganan acara yang ada di bawah sumber daya ini.
        - Tambahkan parameter wajib baru untuk menentukan nama Domain Grid Peristiwa dan/atau nama Topik Domain Grid Peristiwa untuk memungkinkan menghapus langganan acara yang ada di bawah sumber daya ini.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* New-AzFrontDoorWafMatchConditionObject
    - Menambahkan transformasi dukungan dan nilai lengkap otomatis operator baru (RegEx)
* New-AzFrontDoorWafManagedRuleObject
    - Menambahkan nilai lengkap otomatis baru

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk Sumber Daya Gateway Jaringan Virtual
    - Cmdlet baru
        - Get-AzVirtualNetworkGatewayVpnClientConnectionHealth
* Tambahkan AvailablePrivateEndpointType
    - Cmdlet baru
        - Get-AzAvailablePrivateEndpointType
* Tambahkan Layanan PrivatePrivateLink
    - Cmdlet baru
        - Get-AzPrivateLinkService
        - New-AzPrivateLinkService
        - Remove-AzPrivateLinkService
        - New-AzPrivateLinkServiceIpConfig
        - Set-AzPrivateEndpointConnection
* Tambahkan Titik Temu Pribadi
    - Cmdlet baru
        - Get-AzPrivateEndpoint
        - New-AzPrivateEndpoint
        - Remove-AzPrivateEndpoint
        - New-AzPrivateLinkServiceConnection
* Diperbarui di bawah perintah untuk fitur: UseLocalAzureIpAddress flag on VpnConnection
    - Diperbarui New-AzVpnConnection: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
    - Set-AzVpnConnection yang Diperbarui: Menambahkan parameter opsional -UseLocalAzureIpAddress untuk menunjukkan bahwa alamat ip azure lokal harus digunakan sebagai alamat sumber saat memulai koneksi.
* Menambahkan bidang readonly PeeredConnections di ExpressRoute peering.
* Menambahkan bidang readonly GlobalReachEnabled di ExpressRoute.
* Menambahkan atribut perubahan yang melanggar untuk memanggil penghentian bidang AllowGlobalReach dalam model ExpressRouteCircuit
* Memperbaiki Masalah 8756 Kesalahan menggunakan TargetListenerID dengan AzApplicationGatewayRedirectConfiguration cmdlets
* Memperbaiki bug di New-AzApplicationGatewayPathRuleConfig yang mencegah penulisan ulang ruleset ditetapkan.
* Tampilan tetap VirtualNetworkTaps di NetworkInterfaceIpConfiguration
* Fixed Cortex Dapatkan cmdlet untuk daftar semua bagian
* Pembuatan referensi VirtualHub tetap untuk ExpressRouteGateways, VpnGateway
* Menambahkan dukungan untuk Availability Zone di AzureFirewall dan NatGateway
* Ditambahkan cmdlet Get-AzNetworkServiceTag
* Menambahkan dukungan untuk beberapa alamat IP publik untuk Azure Firewall
    - Cmdlet New-AzFirewall diperbarui:
        - Menambahkan parameter -PublicIpAddress yang menerima satu atau lebih objek Alamat IP Publik
        - Menambahkan parameter -VirtualNetwork yang menerima objek Jaringan Virtual
        - Metode tambahan AddPublicIpAddress dan RemovePublicIpAddress pada objek firewall - ini menerima objek Alamat IP Publik sebagai input
        - Parameter yang tidak digunakan lagi -PublicIpName dan -VirtualNetworkName
* Perintah yang diperbarui di bawah ini untuk fitur: Atur opsi otentikasi AAD VpnClient ke sumber daya gateway jaringan Virtual.
    - New-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi otentikasi vpnClient AAD di Gateway.
    - Diperbarui Set-AzVirtualNetworkGateway: Menambahkan parameter opsional AadTenantUri,AadAudienceId,AadIssuerUri untuk mengatur opsi otentikasi AAD VpnClient di Gateway.
    - Set-AzVirtualNetworkGateway yang diperbarui: Menambahkan parameter switch opsional RemoveAadAuthentication untuk menghapus opsi autentikasi AAD VpnClient dari Gateway.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Aktifkan tingkat harga **pergb2018** dalam perintah 'New-AzureRmOperationalInsightsWorkspace'

#### <a name="azresources"></a>Az.Resources
* Dukungan untuk opsi Ekspor Templat tambahan
    - Tambahkan parameter '-SkipResourceNameParameterization' ke Export-AzResourceGroup
    - Tambahkan parameter '-SkipAllParameterization' ke Export-AzResourceGroup
    - Tambahkan parameter '-Resource' ke Export-AzResourceGroup untuk pemfilteran sumber daya yang diekspor

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Perbaiki tambahkan sertifikat ByExistingKeyVault mendapatkan cap jempol yang salah dalam beberapa kasus

#### <a name="azsql"></a>Az.Sql
* Memperbaiki akhiran titik akhir penyimpanan Perlindungan Ancaman Tingkat Lanjut
* Memperbaiki Keamanan Data Tingkat Lanjut memungkinkan penggantian kebijakan Perlindungan Ancaman Tingkat Lanjut
* Cmdlet baru untuk Management.Sql untuk memungkinkan pelanggan menambahkan kunci TDE dan mengatur pelindung TDE untuk instans terkelola
   - Add-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceKeyVaultKey
   - Remove-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceTransparentDataEncryptionProtector
   - Set-AzSqlInstanceTransparentDataEncryptionProtector

#### <a name="azstorage"></a>Az.Storage
* Mendukung Kind FileStorage dan SkuName Premium_ZRS saat membuat akun Storage
    - New-AzStorageAccount
* Deskripsi yang diklarifikasi tentang cmdlet immutability blob
    -  Remove-AzRmStorageContainerImmutabilityPolicy

#### <a name="azwebsites"></a>Az.Websites
* Mengoptimalkan Get-AzWebAppCertificate untuk memfilter berdasarkan grup sumber daya di server, bukan klien
* Menambahkan parameter switch -UseDisasterRecovery ke Get-AzWebAppSnapshot

## <a name="220---june-2019"></a>2.2.0 - Juni 2019
#### <a name="azcdn"></a>Az.Cdn
* Cmdlet yang diperbarui untuk mendukung fitur rulesEngine berdasarkan API versi 2019-04-15.

#### <a name="azcompute"></a>Az.Compute
* Menambahkan `NoWait` parameter yang memulai operasi dan segera kembali, sebelum operasi selesai.
    - Cmdlet yang diperbarui: Export-AzLogAnalyticRequestRateByInterval Export-AzLogAnalyticThrottledRequest Remove-AzVM Remove-AzVMAccessExtension Remove-AzVMAEMExtension Remove-AzVMChefExtension Remove-AzVMCustomScriptExtension Remove-AzVMDiagnosticsExtension Remove-AzVMDiskEncryptionExtension Remove-AzVMDscExtension Remove-AzVMSqlServerExtension Restart-AzVM Set-AzVM Set-AzVMAccessExtension Set-AzVMADDomainExtension Set-AzVMAEMExtension Set-AzVMBginfoExtension Set-AzVMChefExtension Set-AzVMCustomScriptExtension Set-AzVMDiagnosticsExtension Set-AzVMDscExtension Set-AzVMExtension Start-AzVM Stop-AzVM Update-AzVM

#### <a name="azeventhub"></a>Az.EventHub
* Perbaiki untuk #9231 - Get-AzEventHubNamespace tidak mengembalikan tag
* Perbaiki untuk #9230 - Get-AzEventHubNamespace mengembalikan ResourceGroup alih-alih ResourceGroupName

#### <a name="aznetwork"></a>Az.Network
* Perbarui ResourceId dan InputObject untuk Nat Gateway
    - Menambahkan alias untuk ResourceId dan InputObject

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Memperbaiki masalah referensi Null di Get-AzPolicyEvent

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Retensi minimum kebijakan IAASVM dalam beberapa hari berubah menjadi 7 dari 1

#### <a name="azservicebus"></a>Az.ServiceBus
* Perbaiki masalah #9182 - Get-AzServiceBusNamespace mengembalikan ResourceGroup alih-alih ResourceGroupName

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Memperbaiki kesalahan ketik dalam pesan kesalahan untuk 'Update-AzServiceFabricReliability'
* Memperbaiki karakter yang hilang di cmdlines Service Fabric

#### <a name="azsql"></a>Az.Sql
* Tambahkan Parameter DnsZonePartner untuk cmdlet New-AzureSqlInstance untuk mendukung AutoDr untuk Instans Terkelola.
* Menonaktifkan cmdlet Get-AzSqlDatabaseSecureConnectionPolicy
* Ganti nama cmdlet Deteksi Ancaman menjadi Perlindungan Ancaman Tingkat Lanjut
* New-AzSqlInstance -StorageSizeInGB dan -LicenseType sekarang opsional.

#### <a name="azwebsites"></a>Az.Websites
* memperbaiki masalah saat menggunakan Set-AzWebApp dan Set-AzWebAppSlot dengan properti -WebApp menghapus tag

## <a name="210---may-2019"></a>2.1.0 - Mei 2019
#### <a name="azapimanagement"></a>Az.ApiManagement
* Membuat Cmdlet baru untuk mengelola diagnostik di Lingkup global dan API
    - **Get-AzApiManagementDiagnostic** - Dapatkan diagnostik yang dikonfigurasi lingkup global atau api
    - **New-AzApiManagementDiagnostic** - Buat diagnostik baru di lingkup global atau api Scope
    - **New-AzApiManagementHttpMessageDiagnostic** - Buat pengaturan diagnostik untuk Header mana yang akan di-log dan ukuran Body Bytes
    - **New-AzApiManagementPipelineDiagnosticSetting** - Buat pengaturan Diagnostik untuk pesan HTTP masuk/keluar ke Gateway.
    - **New-AzApiManagementSamplingSetting** - Buat Pengaturan Sampling untuk permintaan/respons untuk diagnostik
    - **Remove-AzApiManagementDiagnostic** - Menghapus entitas diagnostik di lingkup global atau api
    - **Set-AzApiManagementDiagnostic** - Memperbarui Entitas diagnostik di lingkup global atau api
* Membuat Cmdlet baru untuk mengelola Cache di layanan ApiManagement
    - **Get-AzApiManagementCache** - Dapatkan detail Cache yang ditentukan oleh pengidentifikasi atau semua cache
    - **New-AzApiManagementCache** - Buat Cache atau Cache 'default' baru di 'wilayah' biru tertentu
    - **Remove-AzApiManagementCache** - Hapus cache
    - **Update-AzApiManagementCache** - Memperbarui cache
* Membuat Cmdlet baru untuk mengelola Skema API
    - **New-AzApiManagementSchema** - Buat Skema baru untuk API
    - **Get-AzApiManagementSchema** - Dapatkan skema yang dikonfigurasi di API
    - **Remove-AzApiManagementSchema** - Hapus skema yang dikonfigurasi dalam API
    - **Set-AzApiManagementSchema** - Memperbarui skema yang dikonfigurasi dalam API
* Membuat Cmdlet baru untuk menghasilkan Token Pengguna.
    - **New-AzApiManagementUserToken** - Hasilkan Token Pengguna baru yang berlaku selama 8 jam secara default. Token untuk pengguna 'GIT' dapat dibuat menggunakan cmdlet ini./
* Membuat cmdlet baru untuk mengambil Status Jaringan
    - **Get-AzApiManagementNetworkStatus** - Dapatkan konektivitas status Jaringan sumber daya yang bergantung pada layanan API Management. Ini berguna saat menerapkan layanan ApiManagement ke Jaringan Virtual dan memvalidasi apakah ada dependensi yang rusak.
* Memperbarui cmdlet **New-AzApiManagement** untuk mengelola layanan ApiManagement
    - Menambahkan dukungan untuk SKU 'Konsumsi' baru
    - Menambahkan dukungan untuk mengaktifkan bendera 'EnableClientCertificate' untuk SKU 'Konsumsi'
    - Cmdlet baru **New-AzApiManagementSslSetting** memungkinkan konfigurasi pengaturan 'TLS /SSL' pada pengaturan 'Backend' dan 'Frontend'. Ini juga dapat digunakan untuk mengkonfigurasi 'Cipher' seperti '3DES' dan 'ServerProtocols' seperti 'Http2' pada 'Frontend' layanan ApiManagement.
    - Menambahkan dukungan untuk mengonfigurasi nama host 'DeveloperPortal' pada layanan ApiManagement.
* Cmdlet yang diperbarui **Get-AzApiManagementSsoToken** untuk mengambil objek 'PsApiManagement' sebagai input
* Memperbarui cmdlet untuk menampilkan Pesan Kesalahan sebaris
     > PS D:\github\azure-powershell> Set-AzApiManagementPolicy -Context -PolicyFilePath C:\wrongpolicy.xml -ApiId httpbin Set-AzApiManagementPolicy : Kode Kesalahan: Validasi Pesan Kesalahan: Satu atau beberapa bidang berisi nilai yang salah: Detail Kesalahan: [Code=ValidationError, Message=Error in element 'log-to-eventhub' di baris 3, kolom 10: Logger tidak ditemukan, Target=log-to-eventhub]
* Diperbarui cmdlet **Export-AzApiManagementApi** untuk mengekspor API dalam format 'OpenApi 3.0'
* Diperbarui cmdlet **Import-AzApiManagementApi**
    - Untuk mengimpor Api dari spesifikasi dokumen 'OpenApi 3.0'
    - Untuk menimpa properti 'PsApiManagementSchema' yang ditentukan dalam dokumen apa pun ('Swagger', 'Wadl', 'Wsdl', 'OpenApi').
    - Untuk mengganti properti 'ServiceUrl' yang ditentukan dalam dokumen apa pun.
* Cmdlet diperbarui **Get-AzApiManagementPolicy** untuk mengembalikan kebijakan dalam 'format' Non-Xml lolos menggunakan 'rawxml'
* Diperbarui cmdlet **Set-AzApiManagementPolicy** untuk menerima kebijakan dalam Non-Xml lolos 'format' menggunakan 'rawxml' dan Xml lolos menggunakan 'xml'
* Diperbarui cmdlet **New-AzApiManagementApi**
    - Untuk mengonfigurasi API dengan server otorisasi 'OpenId'.
    - Untuk membuat API dalam 'ApiVersionSet'
    - Untuk mengkloning API menggunakan 'SourceApiId' dan 'SourceApiRevision'.
    - Kemampuan untuk mengonfigurasi 'SubscriptionRequired' di lingkup Api.
* Diperbarui cmdlet **Set-AzApiManagementApi**
    - Untuk mengonfigurasi API dengan server otorisasi 'OpenId'.
    - Untuk memperbarui API menjadi 'ApiVersionSet'
    - Kemampuan untuk mengonfigurasi 'SubscriptionRequired' di lingkup Api.
* Cmdlet diperbarui **New-AzApiManagementRevision**
    - Untuk mengkloning (salin tag, produk, operasi, dan kebijakan) revisi yang ada menggunakan 'SourceApiRevision'. Revisi baru mengasumsikan 'ApiId' dari induknya.
    - Untuk menyediakan 'ApiRevisionDescription'
    - Untuk menimpa 'ServiceUrl' saat mengkloning API.
* Cmdlet **diperbarui New-AzApiManagementIdentityProvider**
    - Untuk mengonfigurasi 'AAD' atau 'AADB2C' dengan 'Otoritas'
    - Untuk menyiapkan 'SignupPolicy', 'SigninPolicy', 'ProfileEditingPolicy' dan 'PasswordResetPolicy'
* Cmdlet **diperbarui New-AzApiManagementSubscription**
    - Untuk memperhitungkan Subskripmodel baru menggunakan 'Scope' dan 'UserId'
    - Untuk memperhitungkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Tambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Diperbarui cmdlet **Set-AzApiManagementSubscription**
    - Untuk memperhitungkan Subskripmodel baru menggunakan 'Scope' dan 'UserId'
    - Untuk memperhitungkan model langganan lama menggunakan 'ProductId' dan 'UserId'
    - Tambahkan dukungan untuk mengaktifkan 'AllowTracing' di tingkat langganan.
* Diperbarui cmdlet berikut untuk menerima 'ResourceId' sebagai input
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
* Diperbarui Get-AzAutomationJobOutputRecord untuk menangani nilai json dan rekaman teks.
    - Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/7977
    - Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/8600
* Perubahan perilaku bagi Start-AzAutomationDscCompilationJob untuk memulai pekerjaan alih-alih menunggu penyelesaiannya.
    * Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/8347
* Perbaiki untuk Get-AzAutomationDscNode saat menggunakan -Name mengembalikan semua node. Sekarang mengembalikan node yang cocok saja.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter ProtectFromScaleIn dan ProtectFromScaleSetAction ke cmdlet Update-AzVmssVM.
* New-AzVM parameter wimple yang ditetapkan sekarang menggunakan secara default lokasi yang tersedia jika 'AS Timur' tidak didukung

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbarui sdk ADLS untuk menggunakan httpclient, integrasikan pengujian dataplane dengan azure framework

#### <a name="azmonitor"></a>Az.Monitor
* Memperbaiki nama parameter yang salah dalam contoh bantuan

#### <a name="aznetwork"></a>Az.Network
* Tambahkan bendera DisableBgpRoutePropagation ke output Tabel Rute Efektif
    - Cmdlet yang diperbarui:
        - Get-AzEffectiveRouteTable
* Memperbaiki dasbor ganda dalam dokumentasi New-AzApplicationGatewayTrustedRootCertificate

#### <a name="azresources"></a>Az.Resources
* Menambahkan Get-AzureRmDenyAssignment cmdlet baru untuk mengambil tugas penolakan

#### <a name="azsql"></a>Az.Sql
* Ganti nama cmdlet Advanced Threat Protection menjadi Advanced Data Security dan aktifkan Penilaian Kerentanan secara default

## <a name="200---may-2019"></a>2.0.0 - Mei 2019
#### <a name="azaccounts"></a>Az.Accounts
* Memperbarui Pustaka Autentikasi untuk memperbaiki masalah ADFS dengan nama pengguna/kata sandi yang diautentikasi

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Hanya menampilkan penafian Bing untuk Layanan Pencarian Bing.
* Tingkatkan kesalahan saat membuat akun gagal.

#### <a name="azcompute"></a>Az.Compute
* Fitur grup penempatan kedekatan.
    - Cmdlet baru berikut ditambahkan: New-AzProximityPlacementGroup Get-AzProximityPlacementGroup Remove-AzProximityPlacementGroup
    - Parameter baru, ProximityPlacementGroupId, ditambahkan ke cmdlet berikut: New-AzAvailabilitySet New-AzVMConfig New-AzVmssConfig
* Parameter StorageAccountType ditambahkan ke New-AzGalleryImageVersion.
* TargetRegion New-AzGalleryImageVersion dapat berisi StorageAccountType.
* Parameter switch SkipShutdown ditambahkan ke Stop-AzVM dan Stop-AzVmss
* Perubahan mencolok
    - Set-AzVMBootDiagnostics diubah menjadi Set-AzVMBootDiagnostic.
    - Export-AzLogAnalyticThrottledRequests diubah menjadi Export-AzLogAnalyticThrottledRequests.

#### <a name="azdeploymentmanager"></a>Az.DeploymentManager
* Rilis cmdlet Azure Deployment Manager pertama yang tersedia secara umum

#### <a name="azdns"></a>Az.Dns
* Delegasi Server Nama DNS Otomatis
    - Buat cmdlet zona DNS menerima nama zona induk sebagai parameter opsional tambahan.
    - Menambahkan catatan NS di zona induk untuk zona anak yang baru dibuat.

#### <a name="azfrontdoor"></a>Az.FrontDoor
* Rilis Pertama yang Tersedia Secara Umum dari cmdlet Azure FrontDoor
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
* Menambahkan cmdlet baru Set-AzHDInsightGatewayCredential untuk menggantikan Grant-AzHDInsightHttpServicesAccess
* Perbarui cmdlet Get-AzHDInsightJobOutput untuk membedakan peran pembaca dan peran operator hdinsight:
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
    - [Informasi lebih](/rest/api/monitor/scheduledqueryrules) lanjut tentang SQR API
    - Az.Monitor.md yang diperbarui untuk menyertakan cmdlet untuk aturan peringatan berbasis metrik GenV2 (non klasik)

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan untuk Nat Gateway Resource
    - Cmdlet baru
        - New-AzNatGateway
        - Get-AzNatGateway
        - Set-AzNatGateway
        - Remove-AzNatGateway
   - Cmdlet yang diperbarui
        - New-AzureVirtualNetworkSubnetConfigCommand
        - Add-AzureVirtualNetworkSubnetConfigCommand
* Diperbarui di bawah perintah untuk fitur: Set/hapus rute kustom di Brooklyn Gateway.
    - Diperbarui New-AzVirtualNetworkGateway: Menambahkan parameter opsional -CustomRoute untuk mengatur awalan alamat sebagai rute kustom untuk diatur di Gateway.
    - Set-AzVirtualNetworkGateway yang diperbarui: Menambahkan parameter opsional -CustomRoute untuk mengatur awalan alamat sebagai rute kustom yang akan diatur di Gateway.

#### <a name="azpolicyinsights"></a>Az.PolicyInsights
* Dukungan untuk menanyakan detail evaluasi kebijakan.
    - Tambahkan parameter '-Expand' ke Get-AzPolicyState. Dukung '-Perluas Evaluasi KebijakanDetails'.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Dukungan untuk langganan Silang Azure ke pemulihan situs Azure.
* Menandai perubahan melanggar yang akan datang untuk Pemulihan Situs Azure.
* Memperbaiki paket tindakan akhir rencana pemulihan Pemulihan Situs Azure.
* Perbaiki untuk pemetaan jaringan Pembaruan Pemulihan Situs Azure untuk Azure ke Azure.
* Perbaiki untuk arah perlindungan pembaruan Pemulihan Situs Azure untuk Azure ke Azure untuk disk terkelola.
* Perbaikan kecil lainnya.

#### <a name="azrelay"></a>Az.Relay
* Memperbaiki kesalahan ketik dalam pesan yang menghadap pelanggan

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan cmdlet baru untuk NetworkRuleSet of Namespace

#### <a name="azstorage"></a>Az.Storage
* Tingkatkan ke Storage Client Library 10.0.1 (namespace semua objek dari SDK ini berubah dari 'Microsoft.WindowsAzure.Storage. *' ke 'Microsoft.Azure. Storage.*')
* Tingkatkan ke Microsoft.Azure.Management. Storage 11.0.0, untuk mendukung API baru versi 2019-04-01.
* Jenis akun Storage default di Buat perubahan akun Storage dari 'Storage' menjadi 'StorageV2'
    - New-AzStorageAccount
* Ubah Sku.Name output cmdlet akun Storage untuk diselaraskan dengan input SkuName dengan menambahkan '-', seperti perubahan 'StandardLRS' menjadi 'Standard_LRS'
    - New-AzStorageAccount
    - Dapatkan-AkunPenyimpananAz
    - Set-AzStorageAccount

#### <a name="azwebsites"></a>Az.Websites
* Properti 'Kind' sekarang akan diatur untuk objek PSSite yang dikembalikan oleh Get-AzWebApp
* Get-AzWebApp*Metrik dan Get-AzAppServicePlanMetrics ditandai tidak digunakan lagi

## <a name="180---april-2019"></a>1.8.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan `Az` umum modul
* Untuk informasi lebih lanjut tentang `Az` modul, silakan kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan Lokasi, ResourceGroup, dan ResourceName selengkapnya: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan wildcard untuk Mendapatkan cmdlet untuk Az.Compute dan Az.Network
* Menambahkan otentikasi interaktif dan nama pengguna / kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Kumpulan Akun Integrasi dan Konfigurasi Batch

#### <a name="azaccounts"></a>Az.Accounts
* Perbarui Uninstall-AzureRm untuk menghapus modul dengan benar di Mac

#### <a name="azbatch"></a>Az.Batch
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azcdn"></a>Az.Cdn
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah dengan instalasi AEM jika id sumber daya disk memiliki kelompok sumber daya huruf kecil di id sumber daya
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.
* Memperbaiki dokumentasi untuk wildcard

#### <a name="azdatafactory"></a>Az.DataFactory
* Tambahkan SsisProperties jika NodeCount tidak null untuk runtime integrasi terkelola.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azeventgrid"></a>Az.EventGrid
* Memperbarui teks bantuan untuk titik akhir untuk menunjukkan bahwa sumber daya harus dibuat sebelum menggunakan cmdlet langganan buat/perbarui peristiwa.

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan cmdlet baru untuk NetworkRuleSet of Namespace

#### <a name="azhdinsight"></a>Az.HDInsight
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="aziothub"></a>Az.IotHub
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azkeyvault"></a>Az.KeyVault
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.
* Memperbaiki dokumentasi untuk wildcard

#### <a name="azmachinelearning"></a>Az.MachineLearning
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azmedia"></a>Az.Media
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azmonitor"></a>Az.Monitor
  * Cmdlet baru untuk aturan peringatan berbasis metrik GenV2(non klasik)
      - New-AzMetricAlertRuleV2DimensionSelection
      - New-AzMetricAlertRuleV2Criteria
      - Remove-AzMetricAlertRuleV2
      - Get-AzMetricAlertRuleV2
      - Add-AzMetricAlertRuleV2
  * SDK Monitor yang diperbarui ke pratinjau versi 0.22.0

#### <a name="aznetwork"></a>Az.Network
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.
* Memperbaiki dokumentasi untuk wildcard

#### <a name="aznotificationhubs"></a>Az.NotificationHubs
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azpowerbiembedded"></a>Az.PowerBIEmbedded
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.
* Format tabel yang diperbarui untuk SQL di azure VM
* Menambahkan metode alternatif untuk mengambil lokasi di AzureFileShare
* Update ScheduleRunDays in SchedulePolicy object sesuai dengan timezone

#### <a name="azrediscache"></a>Az.RedisCache
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.

#### <a name="azresources"></a>Az.Resources
* Memperbaiki dokumentasi untuk wildcard

#### <a name="azsql"></a>Az.Sql
* Mengganti dependensi pada Monitor SDK dengan kode umum
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.
* Proses yang disempurnakan dari klasifikasi beberapa kolom.
* Sertakan properti sku (nama sku, keluarga, kapasitas) sebagai respons dari Get-AzSqlServerServiceObjective dan format sebagai tabel secara default.
* Kemampuan untuk Get-AzSqlServerServiceObjective berdasarkan lokasi tanpa memerlukan server yang sudah ada sebelumnya di wilayah tersebut.
* Dukungan untuk parameter zona waktu di Instans Terkelola.
* Memperbaiki dokumentasi untuk wildcard

#### <a name="azwebsites"></a>Az.Websites
* memperbaiki Set-AzWebApp dan Set-AzWebAppSlot untuk tidak menghapus tag pada eksekusi
* Cmdlet yang diperbarui dengan kata benda jamak ke nama jamak tunggal, dan usang.
* Memperbarui SDK WebSites.
* Menghapus properti AdminSiteName dari PSAppServicePlan.

## <a name="170---april-2019"></a>1.7.0 - April 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan `Az` umum modul
* Untuk informasi lebih lanjut tentang `Az` modul, silakan kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan Lokasi, ResourceGroup, dan ResourceName selengkapnya: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan wildcard untuk Mendapatkan cmdlet untuk Az.Compute dan Az.Network
* Menambahkan otentikasi interaktif dan nama pengguna / kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Kumpulan Akun Integrasi dan Konfigurasi Batch

#### <a name="azaccounts"></a>Az.Accounts
* Diperbarui Add-AzEnvironment dan Set-AzEnvironment untuk menerima parameter AzureAnalysisServicesEndpointResourceId

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Menggunakan ServiceClient di cmdlets dataplane dan menghapus logika otentikasi asli
* Membuat Add-AzureASAccount pembungkus Connect-AzAccount untuk menghindari perubahan yang melanggar

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki bug cmdlet New-AzAutomationSoftwareUpdateConfiguration untuk Inklusi. Sekarang parameter IncludedKbNumber dan IncludedPackageNameMask harus berfungsi.
* Perbaikan bug untuk grup dinamis manajemen pembaruan otomatisasi azure

#### <a name="azcompute"></a>Az.Compute
* Tambahkan parameter HyperVGeneration ke New-AzDiskConfig dan New-AzSnapshotConfig
* Izinkan pembuatan VM dengan gambar dapur dari penyewa lain.

#### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbaiki masalah dalam parameter -Command New-AzContainerGroup yang menambahkan argumen kosong trailing

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 3.0.2
* Diperbarui Set-AzDataFactoryV2 cmdlet dengan parameter tambahan untuk pengaturan terkait RepoConfiguration.

#### <a name="azresources"></a>Az.Resources
* Meningkatkan penanganan penyedia untuk parameter 'Get-AzResource' saat menyediakan parameter '-ResourceId' atau '-ResourceGroupName', '-Name' dan '-ResourceType'
* Meningkatkan penanganan kesalahan untuk 'Test-AzDeployment' dan 'Test-AzResourceGroupDeployment'
    - Menangani kesalahan yang dilemparkan di luar validasi penerapan dan sertakan dalam output perintah sebagai gantinya
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/6856
* Tambahkan parameter switch '-IgnoreDynamicParameters' ke kumpulan cmdlet penyebaran untuk melewati prompt dalam skenario skrip dan pekerjaan
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/6856

#### <a name="azsql"></a>Az.Sql
* Mendukung Klasifikasi Data Database.

#### <a name="azstorage"></a>Az.Storage
* Laporkan kesalahan detail saat membuat konteks Storage dengan parameter -UseConnectedAccount, tetapi tanpa login akun Azure
    - New-AzStorageContext
* Mendukung Kelola Properti Layanan Blob dari akun Storage tertentu dengan API bidang Manajemen
    - Update-AzStorageBlobServiceProperty
    - Get-AzStorageBlobServiceProperty
    - Enable-AzStorageBlobDeleteRetentionPolicy
    - Disable-AzStorageBlobDeleteRetentionPolicy
* -AsJob dukungan untuk Blob dan file upload dan download cmdlets
    - Get-AzStorageBlobContent
    - Set-AzStorageBlobContent
    - Get-AzStorageFileContent
    - Set-AzStorageFileContent

## <a name="160---march-2019"></a>1.6.0 - Maret 2019
### <a name="highlights-since-the-last-major-release"></a>Sorotan sejak rilis besar terakhir
* Ketersediaan `Az` umum modul
* Untuk informasi lebih lanjut tentang `Az` modul, silakan kunjungi yang berikut: https://aka.ms/azps-announce
* Menambahkan Lokasi, ResourceGroup, dan ResourceName selengkapnya: https://azure.microsoft.com/blog/completers-in-azure-powershell/
* Menambahkan dukungan wildcard untuk Mendapatkan cmdlet untuk Az.Compute dan Az.Network
* Menambahkan otentikasi interaktif dan nama pengguna / kata sandi hanya untuk Windows PowerShell 5.1
* Menambahkan dukungan untuk runbook Python 2 di Az.Automation
* Az.LogicApp: Cmdlet baru untuk Kumpulan Akun Integrasi dan Konfigurasi Batch

#### <a name="azautomation"></a>Az.Automation
* Perubahan manajemen pembaruan otomatisasi Azure untuk mendukung fitur baru berikut:
    * Pengelompokan dinamis
    * Skrip Pra-Posting
    * Pengaturan Reboot

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah dengan resolusi jalur di Get-AzVmBootDiagnosticsData
* Perbarui pustaka klien Compute ke 25.0.0.

#### <a name="azkeyvault"></a>Az.KeyVault
* Menambahkan dukungan wildcard ke cmdlet KeyVault

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan Threat Intelligence untuk Azure Firewall
* Tambahkan Sumber daya tingkat atas Kebijakan Gateway Aplikasi dan Aturan Kustom

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan SnapshotRetentionInDays dalam kebijakan Azure VM untuk mendukung Instant RP
* Menambahkan dukungan pipa untuk kontainer yang tidak terdaftar

#### <a name="azresources"></a>Az.Resources
* Perbarui dukungan wildcard untuk Get-AzResource dan Get-AzResourceGroup
* Memperbarui kredensial yang digunakan saat melakukan panggilan umum ke ARM

#### <a name="azsql"></a>Az.Sql
* mengubah param cmdlet Deteksi Ancaman (ExcludeDetectionType) dari DetectionType ke string[] untuk menjadikannya bukti masa depan ketika DetectionTypes baru ditambahkan dan untuk mendukung pelengkapan otomatis juga.

#### <a name="azstorage"></a>Az.Storage
* Mendukung Kebijakan Kelola Get/Set/Remove Management di akun Storage
    - Atur-AzStorageAccountManagementPolicy
    - Get-AzStorageAccountManagementPolicy
    - Hapus-AzStorageAccountManagementPolicy
    - Tambahkan-AzstorageAccountManagementPolicyaction
    - Baru-AzStorageAccountManagementPolicyFilter
    - Baru-AzStorageAccountManagementPolicyRule

#### <a name="azwebsites"></a>Az.Websites
* Perbaiki bug template ARM yang merusak kloning semua slot menggunakan 'New-AzWebApp -IncludeSourceWebAppSlots'

## <a name="150---march-2019"></a>1.5.0 - Maret 2019
#### <a name="azaccounts"></a>Az.Accounts
* Tambahkan perintah 'Register-AzModule' untuk mendukung cmdlet yang dihasilkan AutoRest
* Perbarui contoh untuk Connect-AzAccount

#### <a name="azautomation"></a>Az.Automation
* Memperbaiki masalah saat mengaktifkan kembali jadwal bulanan tertentu di beberapa cmdlet Azure Automation
* Perbaiki Get-AzAutomationDscNode kembali hanya atas 20 node. Sekarang mengembalikan semua node

#### <a name="azcdn"></a>Az.Cdn
* Menambahkan cmdlet Powershell baru untuk Aktifkan/Nonaktifkan Domain Kustom Https dan usangkan yang lama

#### <a name="azcompute"></a>Az.Compute
* Menambahkan dukungan wildcard ke Dapatkan cmdlet

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 3.0.1

#### <a name="azlogicapp"></a>Az.LogicApp
* Memperbaiki untuk ListWorkflows hanya mengambil halaman pertama hasil

#### <a name="aznetwork"></a>Az.Network
* Menambahkan dukungan wildcard ke cmdlet Jaringan

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Menambahkan Sql server di dukungan Azure VM
* Pembaruan SDK
* Check-in VMappContainer yang dihapus Get-ProtectableItem
* Menambahkan Nama dan Nama Server sebagai parameter untuk Get-ProtectableItem

#### <a name="azresources"></a>Az.Resources
* Menambahkan `-TemplateObject` parameter ke cmdlet penyebaran
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/2933
* Memperbaiki masalah saat menyalurkan hasil `Get-AzResource` ke `Set-AzResource`
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/8240
* Memperbaiki masalah dengan perubahan tipe data JSON saat berjalan `Set-AzResource`
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/7930

#### <a name="azsql"></a>Az.Sql
* Memperbarui AuditingEndpointsCommunicator.
    - Memperbaiki perilaku kasus tepi saat membuat pengaturan diagnostik baru.

#### <a name="azstorage"></a>Az.Storage
* Mendukung Kind BlockBlobStorage saat membuat akun Storage - New-AzStorageAccount

## <a name="140---february-2019"></a>1.4.0 - Februari 2019
#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Cmdlet AddAzureASAccount yang tidak digunakan lagi

#### <a name="azautomation"></a>Az.Automation
* Perbarui bantuan untuk Import-AzAutomationDscNodeConfiguration
* Menambahkan validasi nama konfigurasi ke cmdlet Import-AzAutomationDscConfiguration
* Penanganan kesalahan yang ditingkatkan untuk cmdlet Import-AzAutomationDscConfiguration

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Menambahkan CustomSubdomainName sebagai parameter opsional baru untuk New-AzCognitiveServicesAccount yang digunakan untuk menentukan subdomain untuk sumber daya.

#### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah dengan kumpulan parameter ID
* Perbarui Get-AzVMExtension untuk mencantumkan semua ekstensi yang diinstal jika parameter Nama tidak disediakan
* Menambahkan parameter Tag dan ResourceId ke cmdlet Update-AzImage
* Get-AzVmssVM tanpa ID instans dan dengan InstanceView dapat mencantumkan VMSS VMSS VMS dengan tampilan instans.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan cmdlet untuk item ADL yang dihapus menghitung dan memulihkan

#### <a name="azeventhub"></a>Az.EventHub
* Menambahkan properti boolean baru SkipEmptyArchives untuk Melewatkan Arsip Kosong di kelas CaptureDescription eventhub

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbaiki penandaan pada Set-AzKeyVaultSecret

#### <a name="azlogicapp"></a>Az.LogicApp
* Tambahkan sku Dasar untuk Akun Integrasi
* Tambahkan XSLT 2.0, XSLT 3.0 dan Tipe Peta Cair
* Cmdlet baru untuk Kumpulan Akun Integrasi
    - Get-AzIntegrationAccountAssembly
    - New-AzIntegrationAccountAssembly
    - Remove-AzIntegrationAccountAssembly
    - Set-AzIntegrationAccountAssembly
* Cmdlet baru untuk Konfigurasi Batch Akun Integrasi
    - Get-AzIntegrationAccountBatchConfiguration
    - New-AzIntegrationAccountBatchConfiguration
    - Remove-AzIntegrationAccountBatchConfiguration
    - Set-AzIntegrationAccountBatchConfiguration
* Memperbarui Logic App SDK ke versi 4.1.0

#### <a name="azmonitor"></a>Az.Monitor
* Perbarui bantuan untuk Get-AzMetric

#### <a name="aznetwork"></a>Az.Network
* Perbarui contoh bantuan untuk Add-AzApplicationGatewayCustomError

#### <a name="azoperationalinsights"></a>Az.OperationalInsights
* Dukungan tambahan untuk sumber data New dan Get ApplicationInsights.
    - Menambahkan jenis 'ApplicationInsights' baru untuk mendukung Dapatkan spesifik dan Dapatkan semua sumber data ApplicationInsights untuk ruang kerja tertentu.
    - Menambahkan cmdlet New-AzOperationalInsightsApplicationInsightsDataSource untuk membuat sumber data dengan memberikan parameter sumber daya Application-Insights: Id langganan, resourceGroupName, dan nama.

#### <a name="azresources"></a>Az.Resources
* Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/8166
* Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/8235
* Perbaiki untuk masalah https://github.com/Azure/azure-powershell/issues/6219
* Memperbaiki bug mencegah pembuatan KeyCredentials berulang

#### <a name="azsql"></a>Az.Sql
* Menambahkan dukungan untuk tingkat SQL DB Hyperscale
* Memperbaiki bug di mana pemulihan bisa gagal karena mengatur properti yang tidak perlu dalam permintaan pemulihan

#### <a name="azwebsites"></a>Az.Websites
* Contoh yang benar dalam Get-AzWebAppSlotMetrics

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
* Memperbaiki penandaan untuk grup sumber daya
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/8166
* Memperbaiki masalah di mana `Get-AzureRmRoleAssignment` tidak menghormati -ErrorAction
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/8235

#### <a name="azsql"></a>Az.Sql
* Add Get/Set AzSqlDatabaseBackupShortTermRetentionPolicy
* Memperbaiki masalah jika tidak masuk ke akun Azure akan mengakibatkan pengecualian nullref saat mengeksekusi cmdlet SQL
* Menetapkan pengecualian null ref dalam Get-AzSqlCapability

## <a name="121---january-2019"></a>1.2.1 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Rilis dengan versi Otentikasi yang benar

#### <a name="azanalysisservices"></a>Az.AnalysisServices
* Rilis dengan dependensi Autentikasi yang diperbarui

#### <a name="azrecoveryservices"></a>Az.RecoveryServices
* Rilis dengan dependensi Autentikasi yang diperbarui

## <a name="120---january-2019"></a>1.2.0 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Tambahkan otentikasi interaktif dan nama pengguna/kata sandi hanya untuk Windows PowerShell 5.1
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
* Tambahkan cmdlet Invoke-AzVMReimage
* Tambahkan parameter TempDisk ke Set-AzVmss
* Memperbaiki pesan peringatan New-AzVM

#### <a name="azcontainerregistry"></a>Az.ContainerRegistry
* Memperbarui URL bantuan online yang salah

#### <a name="azdatafactory"></a>Az.DataFactory
* Memperbarui versi ADF .Net SDK ke 3.0.0

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Memperbaiki masalah dengan titik akhir ADLS saat menggunakan MSI
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/7462
* Memperbarui URL bantuan online yang salah

#### <a name="aziothub"></a>Az.IotHub
* Tambahkan format Encoding ke cmdlet Add-IotHubRoutingEndpoint.

#### <a name="azkeyvault"></a>Az.KeyVault
* Memperbarui URL bantuan online yang salah

#### <a name="aznetwork"></a>Az.Network
* Memperbarui URL bantuan online yang salah

#### <a name="azresources"></a>Az.Resources
* Memperbaiki contoh yang salah dalam dokumentasi referensi 'New-AzADAppCredential' dan 'New-AzADSpCredential'
* Memperbaiki masalah di mana jalur untuk parameter '-TemplateFile' tidak diselesaikan sebelum menjalankan cmdlet penyebaran grup sumber daya
* Az.Resources: Dokumentasi yang benar untuk nilai default New-AzureRmPolicyDefinition -Mode
* Az.Resources: Perbaiki masalah https://github.com/Azure/azure-powershell/issues/7522
* Az.Resources: Perbaiki masalah https://github.com/Azure/azure-powershell/issues/5747
* Memperbaiki masalah pemformatan dengan objek 'PSResourceGroupDeployment'
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/2123

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Rollback ketika sertifikat ditambahkan ke model VMSS tetapi pengecualian dilemparkan ini adalah untuk memperbaiki bug: https://github.com/Azure/service-fabric-issues/issues/932
* Memperbaiki beberapa pesan kesalahan.
* Perbaiki buat klaster dengan templat ARM default untuk New-AzServiceFabriCluster yang tidak berfungsi dengan migrasi ke Az.
* Perbaiki tambahkan sertifikat klaster/aplikasi untuk hanya menambahkan ke Kumpulan Skala VM yang sesuai dengan klaster dengan memeriksa id klaster di ekstensi.

#### <a name="azsignalr"></a>Az.Signalr
* Memperbarui URL bantuan online yang salah

#### <a name="azsql"></a>Az.Sql
* Memperbarui URL bantuan online yang salah
* Deskripsi parameter yang diperbarui untuk parameter LicenseType dengan kemungkinan nilai
* Perbaiki untuk memperbarui identitas instans terkelola yang tidak berfungsi saat merupakan satu-satunya properti yang diperbarui
* Dukungan untuk kolusi kustom pada instans terkelola

#### <a name="azstorage"></a>Az.Storage
* Memperbarui URL bantuan online yang salah
* Berikan pesan kesalahan detail saat mendapatkan/mengatur Logging/Metrik klasik di Akun Premium Storage, karena Akun Premium Storage bukan supoort logging/metric klasik.
    - Dapatkan/Set-AzStorageServiceLoggingProperty
    - Dapatkan/Set-AzStorageServiceMetricsProperty

#### <a name="aztrafficmanager"></a>Az.TrafficManager
* Memperbarui URL bantuan online yang salah

#### <a name="azwebsites"></a>Az.Websites
* Memperbarui URL bantuan online yang salah
* Memperbaiki 'New-AzWebAppSSLBinding' untuk mengunggah sertifikat ke resourcegroup + lokasi yang benar jika aplikasi dihosting di ASE.
* Memperbaiki 'New-AzWebAppSSLBinding' untuk tidak menimpa tag untuk mengikat sertifikat SSL ke aplikasi

## <a name="110---january-2019"></a>1.1.0 - Januari 2019
#### <a name="azaccounts"></a>Az.Accounts
* Tambahkan Cakupan 'Lokal' ke Enable-AzureRmAlias

#### <a name="azcompute"></a>Az.Compute
* Nama sekarang opsional dalam parameter ID yang ditetapkan untuk Restart/Start/Stop/Remove/Set-AzVM dan Save-AzVMImage
* Memperbarui deskripsi ID dalam file bantuan
* Memperbaiki masalah kompatibilitas ke belakang dengan modul Az.Accounts

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbarui dataplane versi SDK ke 1.1.14 untuk perbaikan SDK.
    - Memperbaiki penanganan acesstime negatif dan waktu modifikasi untuk getfilestatus dan liststatus, Perbaiki token pembatalan async

#### <a name="azeventgrid"></a>Az.EventGrid
* Diperbarui untuk menggunakan versi API 2019-01-01.
* Perbarui cmdlet berikut untuk mendukung skenario baru dalam versi API 2019-01-01
    - New-AzureRmEventGridSubscription: Tambahkan parameter opsional baru untuk menentukan:
        - Acara Time-To-Live,
        - Jumlah maksimum upaya pengiriman untuk acara,
        - Titik akhir huruf mati.
    - Update-AzureRmEventGridSubscription: Tambahkan parameter opsional baru untuk menentukan:
        - Acara Time-To-Live,
        - Jumlah maksimum upaya pengiriman untuk acara,
        - Titik akhir huruf mati.
* Tambahkan nilai enum baru (yaitu, storageQueue dan hybridConnection) untuk opsi EndpointType dalam cmdlet New-AzureRmEventGridSubscription dan Update-AzureRmEventGridSubscription.
* Tampilkan pesan peringatan jika membuat atau memperbarui langganan acara diharapkan memerlukan tindakan manual dari pengguna.

#### <a name="aziothub"></a>Az.IotHub
* Diperbarui ke sdk IotHub versi terbaru

#### <a name="azlogicapp"></a>Az.LogicApp
* Get-AzLogicApp mencantumkan semua tanpa Nama yang ditentukan

#### <a name="azresources"></a>Az.Resources
* Memperbaiki masalah kumpulan parameter saat menyediakan parameter '-ODataQuery' dan '-ResourceId' untuk 'Get-AzResource'
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/7875
* Memperbaiki penanganan parameter -Custom di New/Set-AzPolicyDefinition
* Memperbaiki kesalahan ketik dalam dokumentasi New-AzDeployment
* Membuat parameter '-MailNickname' wajib untuk 'New-AzADUser'
    - Informasi lebih lanjut di sini: https://github.com/Azure/azure-powershell/issues/8220

#### <a name="azsignalr"></a>Az.Signalr
* Memperbaiki masalah kompatibilitas ke belakang dengan modul Az.Accounts

#### <a name="azsql"></a>Az.Sql
* Mengonversi dependensi klien manajemen Storage ke implementasi SDK umum.

#### <a name="azstorage"></a>Az.Storage
* Atur konteks StorageAccountName of Storage sebagai Nama Akun Storage yang sebenarnya, saat dibuat dengan Sas Token, OAuth, atau Anonymous
    - New-AzStorageContext
* Buat Sas Token of Blob Snapshot Object dengan parameter '-FullUri', perbaiki Uri yang dikembalikan menjadi sanpshot Uri
    - New-AzStorageBlobSASToken

#### <a name="azwebsites"></a>Az.Websites
* Memperbaiki bug pengurai tanggal di 'Get-AzDeletedWebApp'
* Memperbaiki masalah kompatibilitas ke belakang dengan modul Az.Accounts

## <a name="100---december-2018"></a>1.0.0 - Desember 2018
### <a name="general"></a>Umum

- Ketersediaan Umum Modul Az
- Bantuan online untuk setiap modul
- Untuk detail lebih lanjut dan peta jalan, lihat [halaman Az Announcement](https://aka.ms/azps-announce)
- Lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk informasi tentang migrasi dari AzureRM

### <a name="azaccounts"></a>Az.Accounts
- Diubah dari Az.Profile
- Memperbaiki format tabel untuk jenis profil dan konteks

### <a name="azapimanagement"></a>Az.ApiManagement
- Perbaikan untuk #7002
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azbatch"></a>Az.Batch
- Menambahkan kemampuan untuk melihat versi Agen Node Azure Batch apa yang berjalan pada masing-masing VM di kumpulan, melalui properti baru `NodeAgentInformation` pada `PSComputeNode`.
- Default `Caching` untuk `PSDataDisk` sekarang `ReadWrite` bukan `None`.
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azbilling"></a>Az.Billing
- Menggabungkan cmdlet Penagihan, Konsumsi, dan PenggunaanAggregates, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azcognitivservices"></a>Az.CognitivServices
- Tambahkan completers untuk SkuName dan Typem yang tersedia pada operasi New-AzureRmCognitiveServicesAccount
- Dihapus GetSkusWithAccountParamSetName parameter set dari Get-AzCognitiveServicesAccountSkus

### <a name="azcontainerinstance"></a>Az.ContainerInstance
- Menambahkan dukungan ManagedIdentity

### <a name="azdatalakeanalytics"></a>Az.DataLakeAnalytics
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azdatalakestore"></a>Az.DataLakeStore
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azmonitor"></a>Az.Monitor
- Berganti nama menjadi Az.Insights menjadi Az.Monitor dan perubahan kecil lainnya, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide) untuk detailnya

### <a name="azkeyvault"></a>Az.KeyVault
- Menghapus properti 'PurgeDisabled' yang tidak digunakan lagi dari jenis output

### <a name="azmachinelearning"></a>Az.MachineLearning
- Cmdlet yang disertakan dari modul Az.MachineLearningCompute

### <a name="azmedia"></a>Az.Media
- Hapus alias tag yang tidak digunakan lagi dari New-AzMediaService

### <a name="aznetwork"></a>Az.Network
Menambahkan dukungan untuk mengonfigurasi RewriteRuleSets di Application Gateway
    - Cmdlet baru menambahkan:
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
        - New-AzureRmApplicationGatewayUrlPathMapConfig Menambahkan Dukungan KeyVault ke Gateway Aplikasi menggunakan Identitas.
    - Cmdlet diperbarui dengan parameter optonal -KeyVaultSecretId, -KeyVaultSecret
        - Add-AzApplicationGatewaySslCertificate
        - New-AzApplicationGatewaySslCertificate
        - Set-AzApplicationGatewaySslCertificate
    - New-AzApplicationGateway cmdlet diperbarui dengan parameter opsional -UserAssignedIdentity
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azoperationalinsights"></a>Az.OperationalInsights
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azprofile"></a>Az.Profil
- Mengubah nama modul menjadi Az.Accounts

### <a name="azrecoveryservices"></a>Az.RecoveryServices
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azresources"></a>Az.Resources
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azservicefabric"></a>Az.ServiceFabric
- Mendukung sertifikat specfying dengan nama umum dan cap jempol
- Mnor melanggar perubahan, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azsignalr"></a>Az.SIgnalr
- Ketersediaan Umum untuk cmdlet PowerShell untuk SIgnalR

### <a name="azsql"></a>Az.Sql
- Menambahkan jenis deteksi Data_Exfiltration dan Unsafe_Action baru ke cmdlet Deteksi Ancaman
- Contoh dokumentasi yang diperbarui untuk cmdlet Sql Auditing
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azstorage"></a>Az.Storage
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

### <a name="azwebsites"></a>Az.Websites
- Perubahan kecil yang melanggar, lihat [Panduan Migrasi](https://aka.ms/azps-migration-guide)  untuk detailnya

## <a name="070---december-2018"></a>0.7.0 - Desember 2018

### <a name="general"></a>Umum

* Perubahan kecil untuk transisi AzureRM ke Az mendatang

### <a name="azcompute"></a>Az.Compute

* Tambahkan dukungan untuk Gambar UltraSSD dan Galeri dalam set param sederhana untuk `New-AzVm(ss)` cmdlet.

### <a name="azdatalakestore"></a>Az.DataLakeStore

* Memperbaiki garis miring trailing dari domain akun adls

### <a name="azfrontdoor"></a>Az.FrontDoor

* Memperbaiki beberapa tautan yang rusak
    - Dalam artikel New-AzureRmFrontDoor dan Set-AzureRmFrontDoor, perbaiki tautan ke artikel cmdlet New-AzureRmFrontDoorHealthProbeSettingObject.
    - Dalam artikel New-AzureRmFrontDoorManagedRuleObject, perbaiki tautan ke artikel cmdlet New-AzureRmFrontDoorRuleGroupOverrideObject.

### <a name="azrecoveryservices"></a>Az.RecoveryServices

* Menambahkan validasi sisi klien untuk operasi pemulihan Azure File Share.
* Penyimpanan buatanAccountName dan storageAccountResourceGroupName opsional untuk pemulihan af.

### <a name="azresources"></a>Az.Resources

* Perbaiki untuk https://github.com/Azure/azure-powershell/issues/7679
    - Perbarui Get-AzureRmRoleAssignment untuk menggunakan cakupan langganan jika disediakan saat meminta administrator klasik.

### <a name="azsql"></a>Az.Sql

* Perubahan kecil untuk transisi AzureRM ke Az mendatang
* Memperbaiki masalah dengan menggunakan Get-AzureRmSqlDatabaseVulnerabilityAssessment dengan inti DotNet
* Dokumentasi pesan bantuan yang dimodifikasi terkait dengan cmdlet Audit SQL.

### <a name="azstorage"></a>Az.Storage

* Tambahkan -EnableHierarchicalNamespace ke New-AzureRmStorageAccount
* Memperbaiki masalah bahwa cmdlet Copy File tidak dapat menggunakan kembali konteks sumber di tujuan saat tidak memasukkan -DestContext
    - Start-AzureStorageFileCopy
* Mendukung konfigurasi Situs Web Statis
    - Enable-AzureStorageStaticWebsite
    - Disable-AzureStorageStaticWebsite

### <a name="azwebsites"></a>Az.Websites

* Set-AzureRmWebApp dan Set-AzureRmWebAppSlot
    - Parameter baru (-AzureStoragePath) ditambahkan untuk menentukan jalur Azure Storage yang akan dipasang di aplikasi kontainer Windows dan Linux. Gunakan output cmdlet baru New-AzureRmWebAppAzureStoragePath sebagai parameter untuk mengatur jalur Azure Storage.

## <a name="061---november-2018"></a>0.6.1 - November 2018

### <a name="azapimanagement"></a>Az.ApiManagement
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azautomation"></a>Az.Automation
* Cmdlet Azure Automation berbasis swagger
* Cmdlet Manajemen Pembaruan Tambahan
* Menambahkan cmdlet Kontrol Sumber
* Ditambahkan cmdlet Remove-AzureRmAutomationHybridWorkerGroup
* Memperbaiki perintah DSC Register Node

### <a name="azcompute"></a>Az.Compute
* Memperbaiki masalah identitas untuk identitas yang ditetapkan Sistem
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azcontainerinstance"></a>Az.ContainerInstance
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azmarketplaceordering"></a>Az.MarketplaceOrdering
* memperbarui deskripsi contoh untuk cmdlet marketplace

### <a name="aznetwork"></a>Az.Network
* Added cmdlet New-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayCustomError, Get-AzureRmApplicationGatewayCustomError, Set-AzureRmApplicationGatewayCustomError, Remove-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayHttpListenerCustomError, Get-AzureRmApplicationGatewayhttpListenerCustomError, Set-AzureRmApplicationGatewayHttpListenerCustomError, Remove-AzureRmApplicationGatewayHttpListenerCustomError
* Menambahkan ICMP kembali ke Protokol Jaringan AzureFirewall yang didukung
* Perbarui cmdlet Test-AzureRmNetworkWatcherConnectivity, tambahkan validasi pada id tujuan, alamat, dan port.
* Memperbaiki masalah dengan penggunaan memori di peta VirtualNetwork

### <a name="azrecoveryservicesbackup"></a>Az.RecoveryServices.Backup
* Perbaiki untuk memodifikasi kebijakan untuk berbagi file yang dilindungi.
* Mengubah zona waktu kebijakan menjadi huruf besar.

### <a name="azrecoveryservicessiterecovery"></a>Az.RecoveryServices.SiteRecovery
* Contoh yang dikoreksi dalam New-AzureRmRecoveryServicesAsrProtectableItem
* Memperbarui dependensi untuk masalah pemetaan tipe

### <a name="azrelay"></a>Az.Relay
* Menambahkan Parameter -KeyValue opsional ke cmdlet New-AzureRmRelayKey, yang memungkinkan pengguna untuk menyediakan KeyValue.

### <a name="azresources"></a>Az.Resources
* Memperbarui dokumentasi bantuan untuk parameter terkait identitas sumber daya di `New-AzureRmPolicyAssignment` dan `Set-AzureRmPolicyAssignment`
* Menambahkan contoh untuk New-AzureRmPolicyDefinition yang menggunakan -Metadata
* Perbaiki untuk memungkinkan pelestarian kasus di tombol Tag di NetStandard: #7678 #7703

### <a name="azservicefabric"></a>Az.ServiceFabric
* Menambahkan pesan penghentian untuk perubahan yang akan datang

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
* Mengaktifkan manajemen Kebijakan Audit Diperpanjang pada server atau database.
    - Parameter baru (PredicateExpression) ditambahkan untuk mengaktifkan pemfilteran log audit.
    - Cmdlet dimodifikasi untuk menggunakan klien SQL, bukan klien Legacy.
    - Set-AzureRmSqlServerauditing.
    - Get-AzureRmSqlServerauditing.
    - Set-AzureRmSqlDatabaseauditing.
    - Get-AzureRmSqlDatabaseauditing.
* Memperbaiki masalah dengan menggunakan Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings dengan kumpulan parameter nama akun penyimpanan

## <a name="050---november-2018"></a>0.5.0 - November 2018
#### <a name="general"></a>Umum
* Menambahkan Resource Completers ke banyak cmdlet inti - ini alloow Anda untuk tab melalui nama sumber daya yang ada ketika memohon cmdlet interaktif

#### <a name="azprofile"></a>Az.Profil
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime
* Ganti nama param TenantId in cmdlet Connect-AzAccount ke Tenant dan tambahkan alias untuk TenantId
* Deskripsi TenantId yang diperbarui untuk Connect-AzAccount
* Memperbaiki pesan kesalahan untuk login yang gagal saat menyediakan domain penyewa
    - https://github.com/Azure/azure-powershell/issues/6936
* Memperbaiki masalah dengan nama konteks yang berbenturan untuk akun tanpa langganan di penyewa
    - https://github.com/Azure/azure-powershell/issues/7453
* Memperbaiki masalah dengan titik akhir DataLake saat menggunakan MSI
    - https://github.com/Azure/azure-powershell/issues/7462
* Memperbaiki masalah di mana 'Disconnect-AzAccount' akan melempar jika tidak terhubung
    - https://github.com/Azure/azure-powershell/issues/7167

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Tambahkan operasi Get-AzCognitiveServicesAccountSkus.

#### <a name="azcompute"></a>Az.Compute
* Tambahkan cmdlet Add-AzVmssVMDataDisk dan Remove-AzVmssVMDataDisk
* Get-AzVMImage menunjukkan AutomaticOSUpgradeProperties
* Fixed SetAzVMChefExtension -BootstrapOptions dan -JsonAttribute option values tidak diatur dalam format json.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Perbarui paket DataLake ke 1.1.10.
* Tambahkan Konkurensi default ke operasi multithreaded.

#### <a name="azinsights"></a>Az.Insights
* Memperbaiki masalah #7267 (Area Skala Otomatis)
    - Masalah dengan membuat aturan skala otomatis baru tidak mengatur parameter pencacahan dengan benar (akan selalu mengaturnya ke nilai default).
* Masalah tetap #7513 [Insights] Set-AzDiagnosticSetting memerlukan spesifikasi eksplisit kategori selama pembuatan pengaturan
    - Sekarang cmdlet tidak memerlukan indikasi eksplisit dari kategori untuk memungkinkan selama pembuatan, yaitu bekerja seperti yang didokumentasikan.

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
* Perbaiki untuk https://github.com/Azure/azure-powershell/issues/7402
    - Izinkan daftar sumber daya menggunakan parameter '-ResourceId' untuk 'Get-AzResource'

#### <a name="azservicebus"></a>Az.ServiceBus
* Menambahkan properti baca-saja MigrationState ke PSServiceBusMigrationConfigurationAttributes yang akan membantu mengetahui status Migrasi.

#### <a name="azservicefabric"></a>Az.ServiceFabric
* Perbaiki tambahkan sertifikat ke Linux Vmss.
* Perbaiki 'Add-AzServiceFabricClusterCertificate'
    - Menggunakan cap jempol yang benar dari sertifikat baru (Azure/service-fabric-issues#932).
    - Tampilkan pengecualian dengan benar (Azure/service-fabric-issues#1054).
* Perbaiki 'Update-AzServiceFabricDurability' untuk memperbarui konfigurasi klaster sebelum memulai operasi Vmss CreateOrUpdate.

## <a name="040---october-2018"></a>0.4.0 - Oktober 2018
#### <a name="azprofile"></a>Az.Profil
* Memperbaiki masalah dengan Get-AzSubscription di CloudShell
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azcompute"></a>Az.Compute
* Menambahkan ukuran baru ke daftar ukuran VM yang memungkinkan jaringan yang dipercepat akan diaktifkan saat menggunakan param sederhana yang ditetapkan untuk 'New-AzVm'
* Menambahkan lebih lengkap argumen ResourceName ke semua cmdlet.

#### <a name="azdatalakestore"></a>Az.DataLakeStore
* Menambahkan dukungan untuk Aturan Jaringan Virtual
    - Get-AzDataLakeStoreVirtualNetworkRule: Mendapatkan atau Mencantumkan aturan jaringan virtual Azure Data Lake Store.
    - Add-AzDataLakeStoreVirtualNetworkRule: Menambahkan aturan jaringan virtual ke akun Data Lake Store yang ditentukan.
    - Set-AzDataLakeStoreVirtualNetworkRule: Memodifikasi aturan jaringan virtual yang ditentukan di akun Data Lake Store yang ditentukan.
    - Remove-AzDataLakeStoreVirtualNetworkRule: Menghapus aturan jaringan virtual Azure Data Lake Store.

#### <a name="aznetwork"></a>Az.Network
* Perbarui cmdlet Test-AzNetworkWatcherConnectivity, berikan nilai protokol ke backend.
* Menambahkan lebih lengkap argumen ResourceName ke semua cmdlet.

#### <a name="azresources"></a>Az.Resources
* Perbaiki isssue di mana Get-AzRoleDefinition memberikan pengecualian yang tidak dapat dipahami (ketika profil default tidak memiliki langganan di dalamnya dan tidak ada ruang lingkup yang ditentukan) dengan menambahkan pengecualian yang berarti dalam skenario. Juga atur param default yang diatur ke 'RoleDefinitionNameParameterSet'.

## <a name="030---october-2018"></a>0.3.0 - Oktober 2018
#### <a name="azurestorage"></a>Azure.Storage
* Memperbaiki Salin Blob/File tidak akan menyalin metadata saat tujuan memiliki masalah metadata
    - Start-AzureStorageBlobCopy
    - Start-AzureStorageFileCopy
* Dukungan mendapatkan penggunaan sumber daya Storage dari lokasi tertentu, dan menambahkan pesan peringatan untuk mendapatkan penggunaan sumber daya Storage global sudah usang.
    - Get-AzStorageUsage

#### <a name="azcognitiveservices"></a>Az.CognitiveServices
* Mendukung Get-AzCognitiveServicesAccountSkus tanpa akun yang sudah ada.

#### <a name="azcompute"></a>Az.Compute
* Perbaiki Get-AzVM -ResourceGroupName `<rg>` untuk mengembalikan lebih dari 50 hasil jika diperlukan
* Menambahkan contoh 'SimpleParameterSet' ke New-AzVmss bantuan cmdlet.
* Memperbaiki kesalahan ketik dalam pesan kemajuan Enkripsi Disk Azure

#### <a name="azdatafactoryv2"></a>Az.DataFactoryV2
* Memperbarui versi ADF .Net SDK ke 2.3.0.

#### <a name="aznetwork"></a>Az.Network
* Menambahkan fungsionalitas NetworkProfile. cmdlet baru ditambahkan
    - Get-AzNetworkProfile
    - New-AzNetworkProfile
    - Remove-AzNetworkProfile
    - Set-AzNetworkProfile
    - New-AzContainerNicConfig
    - New-AzContainerNicConfigIpConfig
* Menambahkan tautan asosiasi layanan di Model Subnet
* Menambahkan cmdlet New-AzVirtualNetworkTap, Get-AzVirtualNetworkTap, Set-AzVirtualNetworkTap, Remove-AzVirtualNetworkTap
* Menambahkan cmdlet Set-AzNEtworkInterfaceTapConfig, Get-AzNEtworkInterfaceTapConfig, Remove-AzNEtworkInterfaceTapConfig

#### <a name="azrediscache"></a>Az.RedisCache
* Izinkan string apa pun sebagai parameter Ukuran ke depan. Tambahkan P5 di popup PSArgumentCompleter

#### <a name="azresources"></a>Az.Resources
* Menambahkan parameter -Mode yang hilang ke Set-AzPolicyDefinition
* Memperbaiki bug commandlet Get-AzProviderOperation untuk operasi dengan Asal yang berisi Pengguna

#### <a name="azsql"></a>Az.Sql
* Memperbaiki masalah di mana beberapa cmdlet cadangan tidak akan mengenali langganan azure saat ini

#### <a name="azwebsites"></a>Az.Websites
* Cmdlet baru Get-AzWebAppContainerContinuousDeploymentUrl - Mendapatkan URL Webhook Penyebaran Berkelanjutan Kontainer
* Cmdlet baru New-AzWebAppContainerPSSession dan Enter-WebAppContainerPSSession - Memulai sesi jarak jauh PowerShell ke dalam aplikasi kontainer windows

## <a name="020---september-2018"></a>0.2.0 - September 2018
 Rilis Awal
