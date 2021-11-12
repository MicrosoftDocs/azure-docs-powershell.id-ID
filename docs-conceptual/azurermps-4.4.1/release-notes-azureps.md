---
title: Azure PowerShell Log Perubahan | Microsoft Docs
description: Ini adalah riwayat perubahan yang dibuat untuk Azure PowerShell dalam rilis terbaru.
ms.devlang: powershell
ms.topic: conceptual
ms.workload: ''
ms.date: 07/26/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: fca8b618a2b04d10df51a34942125435a403ca56
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421093"
---
# <a name="release-notes"></a>Catatan rilis

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Ini adalah daftar perubahan yang dibuat untuk Azure PowerShell dalam rilis ini.

## <a name="20170925---version-440"></a>2017.09.25 - Versi 4.4.0
* AnalysisServices
  * Menambahkan commandlet dataplane baru untuk memungkinkan sinkronisasi database dari instans baca-tulis ke instans baca-saja
    - Menyertakan file bantuan untuk commandlet
    - Uji dalam memori yang ditambahkan dan uji skenario (hanya secara langsung)
  * Memperbaiki bug di Add-AzureAsAccount commandlet
* Otomatisasi
  * Memperbaiki dokumen bantuan untuk cmdlet yang diperbaiki dalam rilis sebelumnya.
  * Menambahkan 4 cmdlet baru untuk mendukung peluncuran bertahap konfigurasi node DSC.
    - Start-AzureRmAutomationDscNodeConfigurationDeployment
    - Stop-AzureRmAutomationDscNodeConfigurationDeployment
    - Get-AzureRmAutomationDscNodeConfigurationDeployment
    - Get-AzureRmAutomationDscNodeConfigurationDeploymentSchedule
* CognitiveServices
  * Terintegrasi dengan SDK Manajemen Layanan Kognitif versi 2.0.0.
  * Get-AzureRmCognitiveServicesAccount kini dapat mendukung paging dengan benar.
* Hitung
  * Fitur Jalankan Perintah:
    - Cmdlet baru: 'Invoke-AzureRmVMRunCommand' menjalankan perintah pada VM
    - Cmdlet baru: 'Get-AzureRmVMRunCommandDocument' memperlihatkan dokumen perintah jalankan yang tersedia
  * Menambahkan parameter 'StorageAccountType' ke Set-AzureRmDataDisk
  * Dukungan Zona Ketersediaan untuk mesin virtual, kumpulan skala VM, dan disk
    - Paramter baru: 'Zona' ditambahkan ke New-AzureRmVM, New-AzureRmVMConfig, New-AzureRmVmssConfig, New-AzureRmDiskConfig
  * Fitur pemutakhiran rangkaian skala VM:
    - Cmdlet baru: 'Start-AzureRmVmssRollingOSUpgrade' invokes OS meluncurkan pemutakhiran skala VM
    - Cmdlet baru: 'Set-AzureRmVmssRollingUpgradePolicy' mengatur kebijakan pemutakhiran untuk pemutakhiran berkelanjutan dalam skala VM.
    - Cmdlet baru: 'Stop-AzureRmVmssRollingUpgrade' membatalkan pemutakhiran berkelanjutan dalam kumpulan skala VM
    - Cmdlet baru: 'Get-AzureRmVmssRollingUpgrade' memperlihatkan status pemutakhiran berkelanjutan dengan skala VM.
  * Parameter sakelar AssignIdentity diperkenalkan untuk identitas yang ditetapkan sistem.
    - Parameter baru: 'AssignIdentity' ditambahkan ke New-AzureRmVMConfig, New-AzureRmVmssConfig dan Update-AzureRmVM
  * Fitur enkripsi disk Vmss:
    - Cmdlet baru: 'Set-AzureRmVmssDiskEncryptionExtension' memungkinkan enkripsi disk pada kumpulan skala VM
    - Cmdlet baru: 'Disable-AzureRmVmssDiskEncryption' menonaktifkan enkripsi disk pada kumpulan skala VM
    - Cmdlet baru: 'Get-AzureRmVmssDiskEncryptionStatus' memperlihatkan status enkripsi disk dari kumpulan skala VM
    - Cmdelt baru: 'Get-AzureRmVmssVMDiskEncryptionStatus' memperlihatkan status enkripsi disk VM dalam kumpulan skala VM
* ContainerInstance
  * Menambahkan cmdlet PowerShell untuk Azure Container Instance
    - New-AzureRmContainerGroup
    - Get-AzureRmContainerGroup
    - Remove-AzureRmContainerGroup
    - Get-AzureRmContainerInstanceLog
* Insights
  * Perintah cmdlet Disable-AzureRmActivityLogAlert
    - Cmdlet baru untuk menonaktifkan pemberitahuan log aktivitas yang sudah ada.
    - Jika diperlukan, Tag juga dapat diatur dengan cmdlet ini.
  * Perintah cmdlet Enable-AzureRmActivityLogAlert
    - Cmdlet baru untuk mengaktifkan pemberitahuan log aktivitas yang sudah ada.
    - Jika diperlukan, Tag juga dapat diatur dengan cmdlet ini.
  * Perintah cmdlet Get-AzureRmActivityLogAlert
    - Cmdlet baru untuk mengambil satu atau beberapa pemberitahuan log aktivitas.
    - Pemberitahuan bisa diambil berdasarkan nama, grup sumber daya, atau langganan.
  * Perintah cmdlet New-AzureRmActionGroup
    - Cmdlet baru untuk membuat objek ActionGroup dalam memori (tidak ada permintaan yang dilibatkan.)
  * Perintah cmdlet New-AzureRmActivityLogAlertCondition
    - Cmdlet baru untuk membuat objek kondisi daun peringatan log aktivitas dalam memori (tidak ada permintaan yang dilibatkan.)
  * Perintah cmdlet Set-AzureRmActivityLogAlert
    - Cmdlet baru untuk membuat atau memperbarui pemberitahuan log aktivitas.
  * Perintah cmdlet Remove-AzureRmActivityLogAlert
    - Cmdlet baru untuk menghapus satu pemberitahuan log aktivitas.
  * Perintah cmdlet Set-AzureRmActionGroup
    - Cmdlet baru untuk membuat grup tindakan baru atau memperbarui yang sudah ada.
  * Perintah cmdlet Get-AzureRmActionGroup
    - Cmdlet baru untuk mengambil satu atau beberapa grup tindakan.
    - Grup tindakan dapat diambil menurut nama, grup sumber daya, atau langganan.
  * Perintah cmdlet Remove-AzureRmActionGroup
    - Cmdlet baru untuk menghapus satu grup tindakan.
  * Perintah cmdlet New-AzureRmActionGroupReceiver
    - Cmdlet baru untuk membuat penerima grup tindakan baru dalam memori.
* KeyVault
  * Cmdlet baru/diperbarui untuk mendukung penghapusan sementara untuk sertifikat KeyVault
    * Get-AzureKeyVaultCertificate
    * Remove-AzureKeyVaultCertificate
    * Undo-AzureKeyVaultCertificateRemoval
* Jaringan
  * Menambahkan dukungan untuk layanan titik akhir ke Subnet Jaringan Virtual
    - Updated Add-AzureRmVirtualSubnetConfig: Added optional parameter -ServiceEndpoint
    - Updated New-AzureRmVirtualSubnetConfig: Added optional parameter -ServiceEndpoint
    - Updated Set-AzureRmVirtualSubnetConfig: Added optional parameter -ServiceEndpoint
  * Cmdlet yang ditambahkan ke layanan titik akhir daftar yang tersedia di lokasi
    - Get-AzureRmVirtualNetworkAvailableEndpointService
  * Menambahkan kemampuan untuk mengonfigurasi autentikasi P2S berbasis radius eksternal ke commandlet berikut
    - New-AzureVirtualNetworkGateway
    - Set-AzureVirtualNetworkGateway
    - Set-AzureRmVirtualNetworkGatewayVpnClientConfig
  * Cmdlet tambahan untuk memungkinkan generasi VpnProfiles untuk radius eksternal berbasis P2S
    - New-AzureRmVpnClientConfiguration
    - Get-AzureRmVpnClientConfiguration
  * Menambahkan dukungan untuk parameter SKU ke Alamat IP Publik dan Penyeimbang Muat
    - Updated New-AzureRMLoadBalancer: Added optional parameter -Sku
    - Updated New-AzureRMPublicIpAddress: Added optional parameter -Sku
  * Menambahkan dukungan untuk DisableOutboundSNAT untuk Memuat Aturan Penyeimbang
    - Updated New-AzureRMLoadBalancerRuleConfig: Added optional parameter DisableOutboundSNAT
    - Updated Add-AzureRMLoadBalancerRuleConfig: Added optional parameter DisableOutboundSNAT
    - Updated Set-AzureRMLoadBalancerRuleConfig: Added optional parameter DisableOutboundSNAT
  * Menambahkan dukungan untuk IkeV2 P2S
    - Diperbarui New-AzureRmVirtualNetworkGateway: Added optional parameter -VpnClientProtocol, defaults to [ "SSTP", "IkeV2" ]
    - Updated Set-AzureRmVirtualNetworkGateway: Added optional parameter -VpnClientProtocol
  * Menambahkan dukungan untuk aturan MultiNilai di Aturan Keamanan Jaringan dan Aturan Keamanan Jaringan Efektif
    - Updated Add-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix parameters to accept a list of strings
    - Updated New-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix parameter to accept a list of strings
    - Updated Set-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix parameter to accept a list of strings
    - Diperbarui Add-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix parameter untuk menerima daftar string
    - Diperbarui New-AzureRmNetworkSecurityGroup : Parameter Updated SecurityRules untuk menerima parameter SourcePortRange, DestinationPortRange, SourceAddressPrefix yang merupakan daftar string dalam objek PSSecurityRule
    - Pembaruan Get-AzureRmEffectiveNetworkSecurityGroup: Added parameter TagMap
    - Updated Get-AzureRmEffectiveNetworkSecurityGroup: Updated returned PSEffectiveSecurityRule object with SourcePortRange, DestinationPortRange, SourceAddressPrefix parameters which are list of strings.
  * Dukungan tambahan untuk proteksi DDoS untuk jaringan virtual
    - Diperbarui Baru-AzureRmVirtualNetwork: Menambahkan parameter sakelar EnableDDoSProtection dan EnableVmProtection
    - Properti yang ditambahkan EnableDDoSProtection dan EnableVmProtection di PSVirtualNetwork object
  * Menambahkan dukungan untuk Penyeimbang Muat Internal yang Sangat Tersedia
    - Updated Add-AzureRmLoadBalancerRuleConfig: Added All as an acceptable value for Protocol parameter
    - Updated New-AzureRmLoadBalancerRuleConfig: Added All as an acceptable value for Protocol parameter
    - Updated Set-AzureRmLoadBalancerRuleConfig: Added All as an acceptable value for Protocol parameter
  * Menambahkan dukungan untuk Grup Keamanan Aplikasi
    - Ditambahkan New-AzureRmApplicationSecurityGroup
    - Ditambahkan Get-AzureRmApplicationSecurityGroup
    - Ditambahkan Remove-AzureRmApplicationSecurityGroup
    - Updated New-AzureRmNetworkInterface: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated New-AzureRmNetworkInterfaceIpConfig: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated Add-AzureRmNetworkInterfaceIpConfig: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated Set-AzureRmNetworkInterfaceIpConfig: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated New-AzureRmNetworkSecurityRuleConfig: Added optional parameters SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, and DestinationApplicationSecurityGroupId
    - Updated Add-AzureRmNetworkSecurityRuleConfig: Added optional parameters SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, and DestinationApplicationSecurityGroupId
    - Updated Set-AzureRmNetworkSecurityRuleConfig: Added optional parameters SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, and DestinationApplicationSecurityGroupId
  * Menambahkan perintah baru untuk VpnDeviceConfiguration Scripts
    - Get-AzureRmVirtualNetworkGatewaySupportedVpnDevices
    - Get-AzureRmVirtualNetworkGatewayConnectionVpnDeviceConfigScript
* Profil
  * Start-Job Dukungan untuk cmdlet AzureRm.
    * Semua azureRmCmdlets menambahkan parameter -AzureRmContext, yang dapat menerima konteks (output cmdlet Konteks).
      - Pola umum untuk pekerjaan dengan persistensi konteks DINONAKTIFKAN: `Start-Job {param ($context) New-AzureRmVM -AzureRmContext $context [... other parameters]} -ArgumentList (Get-AzureRmContext)`
      - Pola umum untuk pekerjaan dengan persistensi konteks DIAKTIFKAN:`Start-Job {New-AzureRmVM [... other parameters]}`
  * Persist sign in information across sessions, new cmdlets:
    - Enable-AzureRmContextAutosave - Mengaktifkan kredensial persistensi di seluruh sesi.
    - Disable-AzureRmContextAutosave - Menonaktifkan ke persistensi kredensial di seluruh sesi.
  * Mengelola informasi konteks, cmd baru
    - Select-AzureRmContext - Pilih konteks aktif bernama.
    - Rename-AzureRmContext - Mengganti nama konteks yang sensitif untuk referensi yang mudah.
    - Remove-AzureRmContext - Menghapus konteks yang sudah ada.
    - Remove-AzureRmAccount - Hapus semua kredensial, langganan, dan penyewa yang terkait dengan akun.
  * Mengelola informasi konteks, perubahan cmdlet:
    - Lingkup Ditambahkan = (| CurrentUser) ke semua cmdlet yang mengubah kredensial
    - Get-AzureRmContext - Parameter ListAvailable ditambahkan untuk mencantumkan semua konteks yang disimpan
* Sumber daya
  * Add PolicySetDefinition cmdlets
    - New-AzureRmPolicySetDefinition cmdlet untuk membuat definisi kumpulan kebijakan
    - Get-AzureRmPolicySetDefinition cmdlet to list all policy set definitions or to get a specific policy set definition
    - Remove-AzureRmPolicySetDefinition cmdlet untuk menghapus definisi kumpulan kebijakan
    - Set-AzureRmPolicySetDefinition cmdlet untuk memperbarui definisi kumpulan kebijakan yang sudah ada
  * Menambahkan parameter -PolicySetDefinition, -Sku dan -NotScope ke New-AzureRmPolicyAssignment Set-AzureRmPolicyAssignment cmdlets
  * Tambahkan dukungan untuk url kebijakan pass in ke New-AzureRmPolicyDefinition dan Set-AzureRmPolicyDefinition cmdlet
  * Menambahkan parameter -Mode New-AzureRmPolicyDefinition cmdlet
  * Tambahkan Dukungan untuk penghapusan penetapan peran menggunakan objek PSRoleAssignment
    - Pengguna sekarang bisa menggunakan PSRoleassignmnet inputobject dengan Remove-AzureRMRoleAssignment commandlet untuk menghapus penetapan peran.
  * Tambahkan cmdlet ManagedApplication
    - New-AzureRmManagedApplication cmdlet untuk membuat aplikasi terkelola
    - Get-AzureRmManagedApplication cmdlet to list all managed applications under a subscription or to get a specific managed application
    - Remove-AzureRmManagedApplication cmdlet untuk menghapus aplikasi terkelola
    - Set-AzureRmManagedApplication cmdlet untuk memperbarui aplikasi terkelola yang sudah ada
  * Add ManagedApplicationDefinition cmdlets
    - New-AzureRmManagedApplicationDefinition cmdlet untuk membuat definisi aplikasi terkelola menggunakan uri file zip atau menggunakan file json mainTemplate dan createUiDefinition
    - Get-AzureRmManagedApplicationDefinition cmdlet to list all managed application definitions under a resource group or to get a specific managed application definition
    - Remove-AzureRmManagedApplicationDefinition cmdlet untuk menghapus definisi aplikasi terkelola
    - Set-AzureRmManagedApplicationDefinition cmdlet untuk memperbarui definisi aplikasi terkelola yang sudah ada
* Sql
  * Menambahkan dukungan untuk Aturan Jaringan Virtual
    - Menambahkan Get-AzureRmSqlServerVirtualNetworkRule cmdlet yang mendapatkan aturan jaringan virtual dengan nama aturan tertentu atau daftar aturan jaringan virtual dalam server Azure Sql.
    - Menambahkan Set-AzureRmSqlServerVirtualNetworkRule cmdlet yang mengubah jaringan virtual yang menjadi poin aturan.
    - Menambahkan Remove-AzureRmSqlServerVirtualNetworkRule cmdlet yang menghapus aturan jaringan virtual untuk server Azure Sql.
    - Menambahkan New-AzureRmSqlServerVirtualNetworkRule cmdlet yang membuat aturan jaringan virtual baru untuk server Azure Sql.
* Situs Web
  * Tambahkan PremiumV2 Tier untuk Paket Layanan Aplikasi
* Azure. Storage
  * Mutakhirkan ke Azure Storage Client Library 8.4.0 dan Azure Storage DataMovement Library 0.6.1
  * Tambahkan Dukungan PremiumPageBlobTier di Upload dan Salin API Blob
    - Set-AzureStorageBlobContent
    - Start-AzureStorageBlobCopy
  * Memperbaiki Format Output Konsol AzureStorageContainer, AzureStorageBlob, AzureStorageQueue, AzureStorageTable
    - Get-AzureStorageContainer
    - Get-AzureStorageBlob
    - Get-AzureStorageQueue
    - Get-AzureStorageTable

## <a name="20170810---version-431"></a>2017.08.10 - Versi 4.3.1
  * Pembaruan untuk memperbaiki masalah penandatanganan perakitan

## <a name="20170807---version-430"></a>2017.08.07 - Versi 4.3.0
* AnalysisServices
  * Memperbaiki bug di Set-AzureRmAnalysisServciesServer
    - Ketika admin tidak diberikan, admin akan dihapus.
  * Added BackupBlobContainerUri in New-AzureRmAnalysisServicesServer and Set-AzureRmAnalysisServicesServer
    - Aktifkan untuk mengatur/menonaktifkan wadah blob cadangan untuk pencadangan/pemulihan Azure Analysis Services Server
  * Pencarian Sku yang diperbarui di New-AzureRmAnalysisServicesServer lalu Set-AzureRmAnalysisServicesServer
    - Mengubah Sku dengan kode keras menjadi pencarian dinamis.
  * Add-AzureAnalysisServicesAccount untuk mendukung masuk dengan Prinsipal Layanan
* Otomatisasi
  * Membuat perubahan pada cmdlet AutomationDSC* untuk menarik lebih dari 100 rekaman
  * Mengatasi masalah aliran Verbose yang berhenti berfungsi setelah memanggil beberapa cmdlet Otomatisasi (misalnya Get-AzureRmAutomationVariable, Get-AzureRmAutomationJob).
  * Dukungan untuk pembuatan versi NodeConfiguration yang ditambahkan di StartAzureAutomationDscCompilationJob dan ImportAzureAutomationDscNodeConfiguration
  * Perbaikan bug untuk masalah yang sudah ada - Memperbaiki masalah alias adalah #3775 dan alias dan dukungan runOn untuk Rekan Kerja Hibrid.
* Hitung
  * Set-AzureRmVMAEMExtension: Menambahkan dukungan untuk disk Premium ukuran disk baru
  * Set-AzureRmVMAEMExtension: Menambahkan dukungan untuk seri M
  * Menambahkan parameter ForceUpdateTag ke Add-AzureRmVmssExtension
  * Menambahkan parameter Primer New-AzureRmVmssIpConfig
  * Tambahkan parameter EnableAcceleratedNetworking ke Add-AzureRmVmssNetworkInterfaceConfig
  * Menambahkan InstanceId ke Set-AzureRmVmss
  * Mengekspos MaintenanceRedeployStatus pada Get-AzureRmVM output -Status
  * Mengekspos Batasan dan Kapabilitas ke format tabel Get-AzureRmComputeResourceSku
* DataLakeStore
  * Perbaikan untuk masalah: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
  * menambahkan properti ResourceGroup ke NamespaceAttributes
    - 'Grup Sumber Daya' Mendapatkan nama grup sumber daya ruang nama berada di
  * cmdlet yang diperbarui dengan Parameterets untuk Namespace dan EventHub untuk operasi AuthorizationRule
    - New-AzureRmEventHubAuthorizationRule - Menambahkan AuthorizationRule baru ke NameSpace atau EventHub yang sudah ada.
    - Get-AzureRmEventHubAuthorizationRule - Mendapatkan AuthorizationRule / Daftar AuthorizationRules untuk NameSpace atau EventHub yang sudah ada.
    - Set-AzureRmEventHubAuthorizationRule - Memperbarui properti AuthorizationRule dari EventHub NameSpace yang sudah ada.
    - Remove-AzureRmEventHubAuthorizationRule - Menghapus AuthorizationRule yang sudah ada dari NameSpace atau EventHub yang ada.
    - New-AzureRmEventHubKey - Menghasilkan Kunci Utama/Sekunder baru untuk AuthorizationRule dari NameSpace atau EventHub yang sudah ada.
    - Get-AzureRmEventHubKey - Mendapatkan Kunci Utama/Sekunder untuk AuthorizationRule dari NameSpace atau EventHub yang sudah ada.
* Jaringan
    * Menambahkan dukungan IPv6 dan parameter opsional baru -PeerAddressType
      * New-AzureRmExpressRouteCircuitPeeringConfig:
      * Set-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. Parameter opsional baru ditambahkan
      * Remove-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. Parameter opsional baru ditambahkan
    * Parameter yang ditandai -BesEnabled sebagai sudah tak t fungsi
      - Add-AzureRmApplicationGatewayBackendHttpSettings
      - New-AzureRmApplicationGatewayBackendHttpSettings
      - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profil
    * Pengumpulan data telah diaktifkan secara default. Data penggunaan dikumpulkan oleh Microsoft untuk meningkatkan pengalaman pengguna. Data bersifat anonim dan tidak menyertakan nilai argumen baris perintah.
      - Menggunakan cmdlet Disable-AzureRmDataCollection untuk menonaktifkan fitur
      - Gunakan cmdlet Enable-AzureRmDataCollection untuk mengaktifkan fitur ini
* Sumber daya
    * Tambahkan Dukungan untuk validasi lingkup untuk command command roledefinition dan roleassignment berikut sebelum mengirim permintaan ke ARM
      - Get-AzureRMRoleAssignment
      - New-AzureRMRoleAssignment
      - Remove-AzureRMRoleAssignment
      - Get-AzureRMRoleDefinition
      - New-AzureRMRoleDefinition
      - Remove-AzureRMRoleDefinition
      - Set-AzureRMRoleDefinition
* ServiceBus
  * Ditambahkan di bawah commandlet baru untuk AuthorizationRules untuk NameSpace, Queue, dan Topic. menurut parameter yang mengatur aturan otorisasi orperasi berperfomed.
    - New-AzureRmServiceBusAuthorizationRule - Menambahkan AuthorizationRule baru ke ServiceBus NameSpace/Queue/Topic yang sudah ada.
    - Get-AzureRmServiceBusAuthorizationRule - Mendapatkan AuthorizationRule / Daftar AturanOtorisasi untuk ServiceBus NameSpace/Queue/Topic yang sudah ada.
    - Set-AzureRmServiceBusAuthorizationRule - Memperbarui properti AuthorizationRule of Servicebus NameSpace/Queue/Topic yang sudah ada.
    - New-AzureRmServiceBusKey - Menghasilkan Kunci Primer/Sekunder baru untuk AuthorizationRule dari ServiceBus NameSpace/Queue/Topic yang baru.
    - Get-AzureRmServiceBusKey - Mendapatkan kunci utama/sekunder untuk AuthorizationRule dari ServiceBus NameSpace/Queue/Topic yang sudah ada.
    - Remove-AzureRmServiceBusNamespaceAuthorizationRule - Menghapus AuthorizationRule of ServiceBus NameSpace/Queue/Topic yang sudah ada.
  * Properti Grup Sumber Daya ditambahkan ke NamespceAttributes

* Sql
    * Memperbarui Set-AzureRmSqlServerTransparentDataEncryptionProtector untuk menampilkan peringatan dan meminta konfirmasi jika Tipe Enkripsi sudah diatur ke AzureKeyVault
    * Menambahkan cmdlet baru yang diperbarui untuk pengaturan Pengauditan
      - Get-AzureRmSqlDatabaseAuditing cmdlet yang mendapatkan pengaturan audit database Azure SQL.
      - Get-AzureRmSqlServerAuditing cmdlet yang mendapatkan pengaturan pengauditan dari server SQL Azure.
      - Set-AzureRmSqlDatabaseAuditing cmdlet yang mengubah pengaturan audit untuk database Azure SQL.
      - Set-AzureRmSqlServerAuditing cmdlet yang mengubah pengaturan audit server Azure SQL.
    * Penghentian cmdlet kebijakan Pengauditan yang sudah ada
      - Get-AzureRmSqlDatabaseAuditingPolicy
      - Get-AzureRmSqlServerAuditingPolicy
      - Set-AzureRmSqlDatabaseAuditingPolicy
      - Set-AzureRmSqlServerAuditingPolicy
      - Use-AzureRmSqlServerAuditingPolicy
      - Remove-AzureRmSqlDatabaseAuditing
      - Remove-AzureRmSqlServerAuditing
    * File skema penguraian Update-AzureRmSqlSyncGroup sekarang peka huruf besar/besar/besar.
* Storage
    * Menambahkan dukungan NeworkRule ke cmdlet akun penyimpanan mode sumber daya
      - New-AzureRmStorageAccount
      - Set-AzureRmStorageAccount
      - Get-AzureRmStorageAccountNetworkRuleSet
      - Update-AzureRmStorageAccountNetworkRuleSet
      - Add-AzureRmStorageAccountNetworkRule
      - Remove-AzureRmStorageAccountNetworkRule

## <a name="20170717---version-421"></a>2017.07.17 - Versi 4.2.1
* Hitung
  - Memperbaiki masalah dengan cmdlet pembuatan dan pembaruan VM Disk dan VM Disk, (tautan[ <https://github.com/azure/azure-powershell/issues/4309> ]
    - New-AzureRmDisk
    - New-AzureRmSnapshot
    - Update-AzureRmDisk
    - Update-AzureRmSnapshot
* Profil
  - Memperbaiki masalah dengan autentikasi pengguna non interaktif di RDFE (link→ <https://github.com/Azure/azure-powershell/issues/4299> ]

* ServiceManagement
  - Memperbaiki masalah dengan autentikasi pengguna yang tidak interaktif (tautan] <https://github.com/Azure/azure-powershell/issues/4299> ]

## <a name="2017711---version-420"></a>2017.7.11 - Versi 4.2.0
* AnalysisServices
    * Tambahkan API dataplane baru
        - API yang diperkenalkan untuk mengambil log server AS, Export-AzureAnalysisServicesInstanceLog
* Otomatisasi
    * Mengatur nilai Zona Waktu dengan benar untuk jadwal Mingguan dan Bulanan untuk New-AzureRmAutomationSchedule
        - Informasi selengkapnya dapat ditemukan dalam masalah ini: https://github.com/Azure/azure-powershell/issues/3043
* AzureBatch
    - Menambahkan cmdlet Get-AzureBatchJobPreparationAndReleaseTaskStatus baru.
    - Rentang byte yang ditambahkan dimulai dan Get-AzureBatchNodeFileContent parameter tambahan.
* CognitiveServices
    * Terintegrasi dengan SDK Manajemen Layanan Kognitif versi 1.0.0.
    * Memperbaiki bug pemeriksaan panjang nama akun.
* Hitung
    * Storage tipe akun untuk Disk gambar:
        - Parameter 'StorageAccountType' ditambahkan ke Set-AzureRmImageOsDisk lalu Add-AzureRmImageDataDisk
    * Fitur PrivateIP dan PublicIP dalam Konfigurasi Ip Vmss:
        - 'PrivateIPAddressVersion', 'PublicIPAddressConfigurationName', 'PublicIPAddressConfigurationIdleTimeoutInMinutes', 'DnsSetting' nama ditambahkan ke New-AzureRmVmssIpConfig
        - Parameter 'PrivateIPAddressVersion' untuk menentukan IPv4 atau IPv6 ditambahkan ke New-AzureRmVmssIpConfig
    * Fitur Pemeliharaan Kinerja:
        - Parameter sakelar 'PerformMaintenance' ditambahkan ke Mulai Ulang-AzureRmVM.
        - Get-AzureRmVM -Status memperlihatkan informasi pemeliharaan kinerja vm
    * Fitur Identitas Mesin Virtual:
        - Parameter 'IdentityType' ditambahkan ke New-AzureRmVMConfig dan UpdateAzureRmVM
        - Get-AzureRmVM memperlihatkan informasi identitas vm
    * Fitur Identitas Vmss:
        - Parameter 'IdentityType' ditambahkan ke New-AzureRmVmssConfig
        - Get-AzureRmVmss memperlihatkan informasi identitas vms yang diberikan
    * Fitur Diagnostik Vmss Boot:
        - Cmdlet baru untuk mengatur diagnostik boot objek Vmss: Set-AzureRmVmssBootDiagnostics
        - Parameter 'BootDiagnostic' ditambahkan ke New-AzureRmVmssConfig
    * Fitur Vmss LicenseType:
        - Parameter 'LicenseType' ditambahkan ke New-AzureRmVmssConfig
    * Dukungan RecoveryPolicyMode:
        - Paramter 'RecoveryPolicyMode' ditambahkan ke New-AzureRmVmssConfig
    * Fitur Hitung Sku Sumber Daya:
        - Daftar cmdlet baru 'Get-AzureRmComputeResourceSku' semuanya menghitung sku sumber daya
* DataFactories
    * New-AzureRmDataFactoryGatewayKey
    * Memperkenalkan fitur kunci gateway auth dengan menambahkan New-AzureRmDataFactoryGatewayAuthKey dan Get-AzureRmDataFactoryGatewayAuthKey
* DataLakeAnalytics
    * Tambahkan dukungan untuk Compute Policy CRUD melalui perintah berikut:
        - New-AzureRMDataLakeAnalyticsComputePolicy
        - Get-AzureRMDataLakeAnalyticsComputePolicy
        - Remove-AzureRMDataLakeAnalyticsComputePolicy
        - Update-AzureRMDataLakeAnalyticsComputePolicy
    * Tambahkan dukungan untuk metadata hubungan pekerjaan untuk bantuan dengan pekerjaan berulang dan alur kerja. Perintah berikut ini diperbarui atau ditambahkan:
        - Submit-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJobRecurrence
        - Get-AzureRMDataLakeAnalyticsJobPipeline
    * Memperbarui audiens token untuk pekerjaan dan API katalog agar menggunakan audiens khusus Danau Data dan bukan audiens Sumber Daya Azure.
* DataLakeStore
    * Dukungan tambahan untuk rotasi tombol KeyVault terkelola pengguna dalam cmdlet Set-AzureRMDataLakeStoreAccount baru
    * Menambahkan pembaruan umur pakai secara otomatis untuk memicu `enableKeyVault` panggilan ketika KeyVault terkelola pengguna ditambahkan atau tombol diputar.
    * Memperbarui audiens token untuk pekerjaan dan API katalog agar menggunakan audiens khusus Danau Data dan bukan audiens Sumber Daya Azure.
    * Perbaikan bug yang membatasi ukuran file yang dibuat/ditambahkan menggunakan cmdlet berikut:
        - New-AzureRmDataLakeStoreItem
        - Add-AzureRmDataLakeStoreItemContent
* Dns
    * Memperbaiki bug dalam skenario pemipaan untuk Get-AzureRmDnsZone
        - Informasi selengkapnya bisa ditemukan di sini: https://github.com/Azure/azure-powershell/issues/4203
* HDInsight
    * Menambahkan dukungan untuk mengaktifkan / menonaktifkan Operations Management Suite(OMS)
    * Cmdlet baru
        - Enable-AzureRmHDInsightOperationsManagementSuite
        - Disable-AzureRmHDInsightOperationsManagementSuite
        - Get-AzureRmHDInsightOperationsManagementSuite
    * Menambahkan parameter baru untuk mengatur konfigurasi kustom Grafik Add-AzureRmHDInsightConfigValues
        - Parameter SparkDefaults dan SparkThriftConf untuk Spark 1.6
        - Parameter Spark2Defaults dan Spark2ThriftConf untuk Spark 2.0
* Insights
    * Masalah #4215 (permintaan perubahan) menghapus batas 15 hari dalam jendela waktu untuk Get-AzureRmLog cmdlet. Juga perubahan minor pada nama uji satuan.
    * Masalah #3957 diperbaiki untuk Get-AzureRmLog
        - Masalah #1: Backend mengembalikan rekaman di halaman masing-masing 200 catatan, yang ditautkan oleh token lanjutan ke halaman berikutnya. Pelanggan melihat cmdlet yang hanya mengembalikan 200 rekaman ketika mereka tahu ada lebih banyak. Ini terjadi terlepas dari nilai yang mereka tetapkan untuk MaxEvents, kecuali nilai kurang dari 200.
        - Masalah #2: Dokumentasi berisi data yang tidak benar tentang cmdlet ini, misalnya: timewindow default adalah 1 jam.
        - Perbaikan #1: Cmdlet sekarang mengikuti token berkelanjutan yang dikembalikan oleh backend hingga mencapai MaxEvents atau akhir set.<br>Nilai default untuk MaxEvents adalah 1000 dan maksimumnya adalah 100000. Nilai apa pun untuk MaxEvents yang kurang dari 1 diabaikan dan default digunakan sebagai gantinya. Nilai dan perilaku ini tidak berubah, sekarang nilai dan perilaku tersebut didokumentasikan dengan benar.<br>Alias untuk MaxEvents telah ditambahkan -MaxRecords- karena nama cmdlet tidak berbicara tentang kejadian lagi, tapi hanya tentang Log.
        - Perbaikan #2: Dokumentasi berisi informasi yang benar dan lebih mendetail: alias baru, jendela waktu yang benar, nilai default, minimum, dan maksimum yang benar.
* KeyVault
    * Hapus alamat email dari kueri direktori ketika -UserPrincipalName ditentukan pada cmdlet Set-AzureRMKeyVaultAccessPolicy Remove-AzureRMKeyVaultAccessPolicy.
      - Kedua Cmdlet kini memiliki parameter -EmailAddress yang dapat digunakan sebagai ganti parameter -UserPrincipalName ketika membuat kueri untuk alamat email yang sesuai.  Jika terdapat lebih dari satu alamat email yang cocok dalam direktori, Cmdlet akan gagal.
* Jaringan
    * New-AzureRmIpsecPolicy: SALifeTimeSeconds dan SADataSizeKilobytes tidak lagi parameter wajib
        - SALifeTimeSeconds default hingga 27000 detik
        - SADataSizeKilobytes default ke 102400000 KB
    * Menambahkan dukungan untuk konfigurasi perangkat cipher kustom menggunakan kebijakan ssl dan mencantumkan semua api opsi ssl di Gateway Aplikasi
        - Menambahkan parameter opsional -PolicyType, -PolicyName, -MinProtocolVersion, -Ciphersuite
            - Add-AzureRmApplicationGatewaySslPolicy
            - New-AzureRmApplicationGatewaySslPolicy
            - Set-AzureRmApplicationGatewaySslPolicy
        - Ditambahkan Get-AzureRmApplicationGatewayAvailableSslOptions (Alias: List-AzureRmApplicationGatewayAvailableSslOptions)
        - Ditambahkan Get-AzureRmApplicationGatewaySslPredefinedPolicy (Alias: List-AzureRmApplicationGatewaySsslPredefinedPolicy)
    * Menambahkan dukungan pengalihan di Gateway Aplikasi
        - Ditambahkan Add-AzureRmApplicationGatewayRedirectConfiguration
        - Ditambahkan Get-AzureRmApplicationGatewayRedirectConfiguration
        - Ditambahkan New-AzureRmApplicationGatewayRedirectConfiguration
        - Ditambahkan Remove-AzureRmApplicationGatewayRedirectConfiguration
        - Ditambahkan Set-AzureRmApplicationGatewayRedirectConfiguration
        - Menambahkan parameter opsional -RedirectConfiguration
            - Add-AzureRmApplicationGatewayRequestRoutingRule
            - New-AzureRmApplicationGatewayRequestRoutingRule
            - Set-AzureRmApplicationGatewayRequestRoutingRule
        - Added optional parameter -DefaultRedirectConfiguration
            - Add-AzureRmApplicationGatewayUrlPathMapConfig
            - New-AzureRmApplicationGatewayUrlPathMapConfig
            - Set-AzureRmApplicationGatewayUrlPathMapConfig
        - Menambahkan parameter opsional -RedirectConfiguration
            - Add-AzureRmApplicationGatewayPathRuleConfig
            - New-AzureRmApplicationGatewayPathRuleConfig
            - Set-AzureRmApplicationGatewayPathRuleConfig
        - Menambahkan parameter opsional -RedirectConfigurations
            - New-AzureRmApplicationGateway
            - Set-AzureRmApplicationGateway
    * Dukungan tambahan untuk situs web Azure di Gateway Aplikasi
        - Ditambahkan New-AzureRmApplicationGatewayProbeHealthResponseMatch
        - Menambahkan parameter opsional -PickHostNameFromBackendHttpSettings, -MinServers, -Match
            - Add-AzureRmApplicationGatewayProbeConfig
            - New-AzureRmApplicationGatewayProbeConfig
            - Set-AzureRmApplicationGatewayProbeConfig
        - Menambahkan parameter opsional -PickHostNameFromBackendAddress, -AffinityCohostingeName, -OptionalEnabled, -Path
            - Add-AzureRmApplicationGatewayBackendHttpSettings
            - New-AzureRmApplicationGatewayBackendHttpSettings
            - Set-AzureRmApplicationGatewayBackendHttpSettings
    * Perbarui Get-AzureRmPublicIPaddress untuk mendapatkan sumber daya alamat publik yang dibuat melalui Vm Scale Set
    * Cmdlet yang ditambahkan untuk mendapatkan penggunaan jaringan virtual saat ini
        - Get-AzureRmVirtualNetworkUsageList
* Profil
    * Memperbaiki kesalahan saat menggunakan Import-AzureRmContext atau Save-AzureRmContext
        - Informasi selengkapnya dapat ditemukan dalam masalah ini: https://github.com/Azure/azure-powershell/issues/3954
* RecoveryServices.SiteRecovery
    * Memperkenalkan modul baru untuk operasi Pemulihan Situs Azure.
        - Semua cmdlet dimulai dengan AzureRmRecoveryServicesAsr*
* Sql
    * Menambahkan Cmdlet PowerShell Sinkronisasi Data ke AzureRM.Sql
    * Cmdlet AzureRmSqlServer yang diperbarui untuk menggunakan versi API REST baru yang menghindari waktu habis saat membuat server.
    * Cmdlet pemutakhiran server yang tidak berlaku karena versi server lama (2.0) tidak ada lagi.
    * Add new optional switch paramter "AssignIdentity" to New-AzureRmSqlServer and Set-AzureRmSqlServer cmdlets to support provisioning of a resource identity for the SQL server resource
    * Parameter ResourceGroupName sekarang opsional untuk Get-AzureRmSqlServer
        - Informasi selengkapnya dapat ditemukan dalam masalah berikut: https://github.com/Azure/azure-powershell/issues/635
* ServiceManagement untuk ExpressRoute:
    * Cmdlet New-AzureBgpPeering diperbarui untuk menambahkan opsi baru berikut ini:
        - PeerAddressType : Nilai "IPv4" atau "IPv6" dapat ditentukan untuk membuat Peering BGP tipe keluarga alamat terkait
    * Cmdlet Set-AzureBgpPeering diperbarui untuk menambahkan opsi baru berikut ini:
        - PeerAddressType : Nilai "IPv4" atau "IPv6" dapat ditentukan untuk memperbarui Peering BGP dari tipe keluarga alamat terkait
    * Cmdlet Remove-AzureBgpPeering diperbarui untuk menambahkan opsi baru berikut ini:
        - PeerAddressType : Nilai "IPv4", "IPv6" atau Semua dapat ditentukan untuk menghapus Peering BGP dari jenis keluarga alamat terkait atau semuanya

## <a name="20170607---version-410"></a>2017.06.07 - Versi 4.1.0
* AnalysisServices
    * SKU baru ditambahkan: B1, B2, S0
    * Menskalakan dukungan naik/turun yang ditambahkan
* CognitiveServices
    * Perbarui tampilan mendetail perjanjian lisensi saat membuat sumber daya Layanan Kognitif
* Hitung
    * Memperbaiki Test-AzureRmVMAEMExtension untuk mesin virtual dengan beberapa disk terkelola
    * Updated Set-AzureRmVMAEMExtension: Add caching information for Premium managed disks
    * Add-AzureRmVhd: Batas ukuran vhd ditingkatkan hingga 4TB.
    * Stop-AzureRmVM: Menjelaskan dokumentasi untuk parameter STayProvisioned
    * New-AzureRmDiskUpdateConfig
      * Parameter yang sudah tidak berlaku CreateOption, StorageAccountId, ImageReference, SourceUri, SourceResourceId
    * Set-AzureRmDiskUpdateImageReference: Cmdlet yang tidak berlaku
    * New-AzureRmSnapshotUpdateConfig
      * Parameter yang sudah tidak berlaku CreateOption, StorageAccountId, ImageReference, SourceUri, SourceResourceId
    * Set-AzureRmSnapshotUpdateImageReference: Deprecated Cmdlet
* DataLakeStore
    * Enable-AzureRmDataLakeStoreKeyVault (Enable-AdlStoreKeyVault)
      * Mengaktifkan enkripsi terkelola KeyVault untuk DataLake Store
* DevTestLabs
    * Perbarui cmdlet untuk bekerja dengan versi API DevTest Labs terbaru dan diperbarui.
* IotHub
    * Menambahkan dukungan Perutean untuk cmdlet IoTHub
* KeyVault
  * Cmdlet Baru untuk mendukung KeyVault Managed Storage Account Keys
    * Get-AzureKeyVaultManagedStorageAccount
    * Add-AzureKeyVaultManagedStorageAccount
    * Remove-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccountKey
    * Get-AzureKeyVaultManagedStorageSasDefinition
    * Set-AzureKeyVaultManagedStorageSasDefinition
    * Remove-AzureKeyVaultManagedStorageSasDefinition
* Jaringan
    * Get-AzureRmNetworkUsage: Cmdlet baru untuk memperlihatkan detail penggunaan dan kapasitas jaringan
    * Menambahkan opsi GatewaySku untuk VirtualNetworkGateway
        * VpnGw1, VpnGw2, VpnGw3 adalah Sku baru yang ditambahkan untuk gateway Vpn
    * Set-AzureRmNetworkWatcherConfigFlowLog
      * Contoh bantuan tetap
* NotificationHubs
    * Cmdlet Transparent Update to NotificationHubs untuk API baru
* Profil
    * Resolve-AzureRmError
      * Cmdlet baru untuk memperlihatkan detail kesalahan dan pengecualian yang diberikan oleh cmdlet, termasuk data permintaan/respons server
    * Send-Feedback
      * Mengaktifkan umpan balik pengiriman tanpa masuk
    * Get-AzureRmSubscription
      * Memperbaiki bug dalam piutang langganan CSP
* Sumber daya
    * Memperbaiki masalah Get-AzureRMRoleAssignment mengakibatkan Permintaan Buruk jika jumlah penetapan peran lebih besar dari 1000
        * Pengguna kini dapat Get-AzureRMRoleAssignment meskipun penetapan peran yang akan dikembalikan lebih besar dari 1000
* Sql
    * Restore-AzureRmSqlDatabase: Contoh dokumentasi pembaruan
* Storage
    * Tambahkan dukungan pengaturan AssignIdentity ke cmdlet akun penyimpanan mode sumber daya
        * New-AzureRmStorageAccount
        * Set-AzureRmStorageAccount
    * Tambahkan Dukungan Kunci Pelanggan ke cmdlet akun penyimpanan mode sumber daya
        * Set-AzureRmStorageAccount
        * New-AzureRmStorageAccountEncryptionKeySource
* TrafficManager

    * Pengaturan Monitor Baru 'MonitorIntervalInSeconds', 'MonitorTimeoutInSeconds', 'MonitorToleratedNumberOfFailures'
    * Protokol Monitor Baru 'TCP'
* ServiceManagement
    * Add-AzureVhd: Batas ukuran vhd ditingkatkan menjadi 4TB.
    * New-AzureBGPPeering: Support LegacyMode
* Azure. Storage
    * Bantuan pembaruan untuk parameter yang menerima karakter wildcard dan memperbarui tipe StorageContext

## <a name="20170523---version-402"></a>2017.05.23 - Versi 4.0.2
* Profil
    * Add-AzureRmAccount
      * Menambahkan `-EnvironmentName` alis parameter untuk kompatibilitas mundur dengan versi 2.x dari AzureRM.profile

## <a name="20170512---version-401"></a>2017.05.12 - Versi 4.0.1
 * Memperbaiki masalah terkait New-AzureStorageContext dalam skenario offline: https://github.com/Azure/azure-powershell/issues/3939

## <a name="20170510---version-400"></a>2017.05.10 - Versi 4.0.0


* Rilis ini berisi perubahan yang tidak dapat dilakukan. Silakan lihat [panduan migrasi untuk](https://aka.ms/azps-migration-guide) detail perubahan dan dampaknya pada skrip yang sudah ada.
* ApiManagement
  - Menambahkan dukungan untuk mengonfigurasi grup eksternal di New-AzureRmApiManagementGroup.
* Tagihan
  - Perintah Cmdlet Get-AzureRmBillingPeriod
    + cmdlet untuk mendapatkan periode tagihan Azure dari langganan.
  - Perbarui cmdlet Get-AzureRmBillingInvoice
  - properti baru BillingPeriodNames
  - output dalam tampilan daftar
* Hitung
  - Cmdlet Set-AzureRmVMAEMExtension dan Test-AzureRmVMAEMExtension diperbarui untuk mendukung Premium yang dikelola
  - Pengaturan enkripsi cadangan untuk VM IaaS dan pulihkan saat gagal
  - Opsi ChefServiceInterval diganti namanya menjadi ChefDaemonInterval sekarang. Lama akan tetap berfungsi.
  - Menghapus properti DataDiskNames dan NetworkInterfaceIDs duplikat dari objek PS VM.
  - Buat parameter DataDiskName dan NetworkInterfaceIDs opsional di Remove-AzureRmVMDataDisk dan Remove-AzureRmVMNetworkInterface.
  - Perbaiki masalah pemipaan cmdlet Get ketika cmdlet Get mengembalikan objek daftar.
  - Cmdlet yang berkonflik dengan cmdlet RDFE telah diganti namanya. Lihat masalah https://github.com/Azure/azure-powershell/issues/2917 untuk detail selengkapnya
    + `New-AzureVMSqlServerAutoBackupConfig` telah diganti namanya menjadi `New-AzureRmVMSqlServerAutoBackupConfig`
    + `New-AzureVMSqlServerAutoPatchingConfig` telah diganti namanya menjadi `New-AzureRmVMSqlServerAutoPatchingConfig`
    + `New-AzureVMSqlServerKeyVaultCredentialConfig` telah diganti namanya menjadi `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Konsumsi
  - Perintah Cmdlet Get-AzureRmConsumptionUsageDetail
    + cmdlet untuk mendapatkan detail penggunaan langganan.
* ContainerRegistry
  - Menambahkan cmdlet PowerShell untuk Azure Container Registry
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - Tambahkan dukungan untuk daftar dan dapatkan paket katalog
  - Tambahkan dukungan untuk mencantumkan item katalog berikut ini dari pemahaman yang lebih mendalam:
    + Tabel
    + TVF
    + Tampilan
    + Statistik
* DataLakeStore
  - Untuk `Import-AzureRMDataLakeStoreItem` dan melacak pembuatan log telah dinonaktifkan secara default untuk meningkatkan `Export-AzureRMDataLakeStoreItem` kinerja. Jika pembuatan log jejak diinginkan, silakan gunakan `-DiagnosticLogLevel` parameter `-DiagnosticLogPath` dan
  - Memperbaiki bug yang terkadang menyebabkan PowerShell mengalami crash saat mengunggah banyak file kecil ke ADLS.
* EventHub
  - Perbaikan bug:
    + Perbaikan untuk Set-AzureRmEventHubNamespace cmdlet baru - 'Tier' tidak dapat null, dan seharusnya 'SkuName'
    + Set-AzureRmEventHub - Perbaiki kesalahan 'Referensi objek tidak diatur ke contoh objek' saat memperbarui EventHub
* Insights
  - Add-AzureRm*AlertRule
    + Mengembalikan objek tunggal: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + Outputnya sekarang dienumerasi, bukan dianggap sebuah objek tunggal. Tipenya tidak berubah, namun masih merupakan daftar.
  - Remove-AzureRmAlertRule
    + Kode status mengikuti kode status yang dikembalikan oleh permintaan, sebelum Selalu ok.
  - Add-AzureRmAutoscaleSetting
    + Mengembalikan sekarang sebuah objek (bukan daftar seperti sebelumnya) yang berisi statusCode, requestId, dan sumber daya yang baru dibuat/diperbarui.
    + Kode status mengikuti status yang dikembalikan oleh permintaan, sebelum selalu Ok.
  - New-AzureRmAutoscaleRule
    + Parameter ScaleActionType telah diperpanjang, dan menerima nilai berikut ini sekarang: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + StatusKode dalam output mengikuti statusKode yang dikembalikan oleh permintaan. Sebelum selalu ok.
  - Get-AzureRMLogProfile
    + Outputnya sekarang dienumerasi. Sebelum dianggap sebuah objek. Tipe output tetap merupakan daftar seperti sebelumnya.
  - Remove-AzureRmLogProfile
    + Parameter PassThru telah diterapkan.
  - API Metrik
    + SDK sekarang mengambil metrik dari MDM.
  - Get-AzureRmMetricDefinition
    + Outputnya masih daftar, tapi struktur daftarnya berubah.
  - Get-AzureRmMetric
    + Panggilan telah berubah. Ini adalah sintaks baru: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailOutput]
    + Outputnya adalah daftar, dan struktur elemennya telah berubah.
* KeyVault
  - Menambahkan dukungan pencadangan/pemulihan untuk rahasia KeyVault
    + Rahasia bisa dicadangkan dan dipulihkan, mencocokkan fungsionalitas yang saat ini didukung untuk Tombol

  - Cmdlet cadangan untuk Kunci dan Rahasia kini menerima objek terkait sebagai parameter input
    + Penelepon mungkin operasi pengambilan dan pencadangan berantai: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - Cmdlet cadangan kini mendukung pengalih -Force untuk menimpa file yang sudah ada
    + Perhatikan bahwa mencoba menimpa file yang sudah ada tidak akan muncul lagi, dan sebagai gantinya akan meminta pengguna untuk memilih cara melanjutkan.
* LogicApp
  - Parameter baru untuk cmdlet pemulihan bencana Interchange Control Number:
    + Opsional -Parameter AgreementType ("X12", atau "Edifact") untuk menentukan angka kontrol yang relevan
* MachineLearning
  - Menggunakan versi baru Azure Machine Learning .Net SDK dan menambahkan cmdlet baru
    + Add-AzureRmMlWebServiceRegionalProperty
  - Perbaikan kata-kata minor dalam teks bantuan.
* Jaringan
  - Cmdlet Test-AzureRmNetworkWatcherConnectivity tambahan
    + Mengembalikan informasi konektivitas untuk VM sumber yang ditentukan dan tujuan
    + Jika konektivitas antara sumber dan tujuan tidak dapat dibuat, cmdlet akan mengembalikan detail tentang masalah tersebut
* Profil
  - Menambahkan cmdlet 'Kirim-Umpan Balik': memungkinkan pengguna untuk memulai serangkaian perintah yang mengirimkan umpan balik ke Azure PowerShell tim terkait.
  - Alias berikut ini telah dihapus karena berkonflik dengan nama cmdlet yang ada dalam modul Azure:
    + `Enable-AzureDataCollection` (didukung oleh `Enable-AzureRmDataCollection` )
    + `Disable-AzureDataCollection` (didukung oleh `Disable-AzureRmDataCollection` )
* Relay
  - Menambahkan cmdlet untuk Azure Relay yang memungkinkan pengguna membuat dan mengelola semua sumber daya Azure Relay.
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* Sumber daya
  - Mendukung penyebaran lintas sumber daya grup untuk New-AzureRmResourceGroupDeployment
    + Pengguna kini dapat menggunakan penyebaran bertumpuk untuk menyebarkan ke grup sumber daya yang berbeda.
* ServiceBus

  - Perbaikan Bug: Nilai properti objek ServiceBus Queue diatur ke null, objek digunakan sebagai parameter input Set-AzureRmServiceBusQueue cmdlet untuk memperbarui Queue.
    - Properti yang terpengaruh adalah LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount, dan MessageCount
* ServiceFabric

  - Added cmdlets for service fabric
    + Add-AzureRmServiceFabricApplicationCertificate Tambahkan sertifikat yang akan digunakan sebagai sertifikat aplikasi
    + Add-AzureRmServiceFabricClientCertificate Tambahkan nama umum atau thumbprint ke pengaturan kluster untuk autentikasi klien
    + Add-AzureRmServiceFabricClusterCertificate Menambahkan sertifikat kluster sekunder ke kluster untuk diluncurkan pada sertifikat yang sudah ada
    + Add-AzureRmServiceFabricNodes Menambahkan node/VM tipe node tertentu ke kluster
    + Add-AzureRmServiceFabricNodeType Menambahkan tipe/VM simpul ke kluster yang sudah ada
    + Get-AzureRmServiceFabricCluster Dapatkan detail sumber daya kluster
    + New-AzureRmServiceFabricCluster Membuat kluster ServiceFabric baru. Perintah ini memiliki banyak kelebihan beban untuk menutupi berbagai skenario
    + Remove-AzureRmServiceFabricClientCertificate Menghapus sertifikat klien agar tidak digunakan untuk mengakses kluster
    + Remove-AzureRmServiceFabricClusterCertificate Menghapus sertifikat kluster agar tidak digunakan untuk keamanan kluster
    + Remove-AzureRmServiceFabricNodes Menghapus node dari tipe node tertentu dari kluster
    + Remove-AzureRmServiceFabricNodeType Menghapus tipe node dari kluster
    + Remove-AzureRmServiceFabricSettings Menghapus satu atau beberapa pengaturan ServiceFabric dari kluster
    + Set-AzureRmServiceFabricSettings Menambahkan atau memperbarui satu atau beberapa pengaturan ServiceFabric kluster
    + Set-AzureRmServiceFabricUpgradeType Mengubah tipe pemutakhiran ServiceFabric kluster
    + Update-AzureRmServiceFabricDurability Mengubah tingkat durability kluster
    + Update-AzureRmServiceFabricReliability Mengubah tingkat keandalan kluster
* Sql
  - Menambahkan parameter -SampleName ke New-AzureRmSqlDatabase
  - Pembaruan untuk cmdlet Grup Failover
  - Menghapus parameter 'Tag'
  - Hapus parameter 'PartnerResourceGroupName' dan 'PartnerServerName' Remove-AzureRmSqlDatabaseFailoverGroup cmdlet
  - Tambahkan parameter 'GracePeriodWithDataLossHours' ke cmdlet New- dan Set-, yang nantinya akan menggantikan 'GracePeriodWithDataLossHour'
  - Dokumentasi telah dikuak dan diperbarui
  - Mengubah pemformatan objek yang dikembalikan dan memperbaiki beberapa bug ketika bidang tidak selalu diisi
  - Menambahkan properti 'DatabaseNames' dan 'PartnerLocation' ke objek Grup Failover
  - Memperbaiki bug yang menyebabkan Cmdlet Switch- segera kembali dan bukan menunggu operasi selesai
  - Memperbaiki bug luapan bilangan bulat ketika nilai masa tenggang tinggi digunakan
  - Sesuaikan masa tenggang minimal 1 jam jika yang lebih rendah diberikan
  - Hapus "Usage_Anomaly" dari nilai yang diterima untuk parameter "ExcludedDetectionType" cmdlet Set-AzureRmSqlDatabaseThreatDetectionPolicy cmdlet Set-AzureRmSqlServerThreatDetectionPolicy cmdlet.
* Storage
  - Memutakhirkan SRP SDK ke 6.3.0
  - Baru/Set-AzureRmStorageAccount:Menambahkan parameter baru untuk mendukung EnableHttpsTrafficOnly
  - New/Set/Get-AzureRmStorageAccount: Returned Storage Account berisi atribut baru EnableHttpsTrafficOnly
* Azure. Storage
  - Mutakhirkan ke Azure Storage Client Library 8.1.1 dan Azure Storage DataMovement Library 0.5.1
  - Menambahkan cmdlet baru untuk mendukung fitur Salinan Penambahan blob
