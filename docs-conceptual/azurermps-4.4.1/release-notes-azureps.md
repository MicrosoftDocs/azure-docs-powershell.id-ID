---
title: Log Perubahan Azure PowerShell | Microsoft Docs
description: Ini adalah sejarah perubahan yang dibuat untuk Azure PowerShell dalam rilis terbaru.
ms.devlang: powershell
ms.topic: conceptual
ms.workload: ''
ms.date: 07/26/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: fca8b618a2b04d10df51a34942125435a403ca56
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
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
    - Menambahkan pengujian dalam memori dan tes skenario (hanya secara langsung)
  * Memperbaiki bug di commandlet Add-AzureAsAccount
* Automation
  * Memperbaiki dokumen bantuan untuk cmdlet yang diperbaiki pada rilis sebelumnya.
  * Menambahkan 4 cmdlet baru untuk mendukung peluncuran bertahap konfigurasi node DSC.
    - Start-AzureRmAutomationDscNodeConfigurationDeployment
    - Stop-AzureRmAutomationDscNodeConfigurationDeployment
    - Get-AzureRmAutomationDscNodeConfigurationDeployment
    - Get-AzureRmAutomationDscNodeConfigurationDeploymentSchedule
* CognitiveServices
  * Integrasikan denganSDK Manajemen Cognitive Services versi 2.0.0.
  * Get-AzureRmCognitiveServicesAccount sekarang dapat mendukung penomoran dengan benar.
* Compute
  * Jalankan fitur Perintah:
    - Cmdlet baru: 'Invoke-AzureRmVMRunCommand' memanggil perintah jalankan pada VM
    - Cmdlet baru: 'Get-AzureRmVMRunCommandDocument' menampilkan dokumen perintah jalankan yang tersedia
  * Menambahkan parameter 'StorageAccountType' ke Set-AzureRmDataDisk
  * Dukungan Availability Zone untuk mesin virtual, set skala VM, dan disk
    - Paramter baru: 'Zone' ditambahkan ke New-AzureRmVM, New-AzureRmVMConfig, New-AzureRmVmssConfig, New-AzureRmDiskConfig
  * Fitur peningkatan bergulir set skala VM:
    - Cmdlet baru: 'Start-AzureRmVmssRollingOSUpgrade' memanggil peningkatan rolling OS dari set skala VM
    - Cmdlet baru: 'Set-AzureRmVmssRollingUpgradePolicy' menetapkan kebijakan peningkatan untuk peningkatan rolling set skala VM.
    - Cmdlet baru: 'Stop-AzureRmVmssRollingUpgrade' membatalkan peningkatan rolling set skala VM
    - Cmdlet baru: 'Get-AzureRmVmssRollingUpgrade' menunjukkan status peningkatan rolling set skala VM.
  * Parameter switch AssignIdentity diperkenalkan untuk identitas yang ditetapkan sistem.
    - Parameter baru: 'AssignIdentity' ditambahkan ke New-AzureRmVMConfig, New-AzureRmVmssConfig, dan Update-AzureRmVM
  * Fitur enkripsi disk Vmss:
    - Cmdlet baru: 'Set-AzureRmVmssDiskEncryptionExtension' memungkinkan enkripsi disk pada set skala VM
    - Cmdlet baru: 'Disable-AzureRmVmssDiskEncryption' menonaktifkan enkripsi disk pada set skala VM
    - Cmdlet baru: 'Get-AzureRmVmssDiskEncryptionStatus' menunjukkan status enkripsi disk set skala VM
    - Cmdelt baru: 'Get-AzureRmVmssVMDiskEncryptionStatus' menunjukkan status enkripsi disk VM dalam set skala VM
* ContainerInstance
  * Menambahkan cmdlet PowerShell untuk Instans Kontainer Azure
    - New-AzureRmContainerGroup
    - Get-AzureRmContainerGroup
    - Remove-AzureRmContainerGroup
    - Get-AzureRmContainerInstanceLog
* Wawasan
  * Cmdlet baru Disable-AzureRmActivityLogAlert
    - Cmdlet baru untuk menonaktifkan peringatan log aktivitas yang ada.
    - Secara opsional Tag diatur dengan cmdlet ini juga.
  * Cmdlet baru Enable-AzureRmActivityLogAlert
    - Cmdlet baru untuk mengaktifkan peringatan log aktivitas yang ada.
    - Secara opsional Tag diatur dengan cmdlet ini juga.
  * Cmdlet baru Get-AzureRmActivityLogAlert
    - Cmdlet baru untuk mengambil satu atau beberapa peringatan log aktivitas.
    - Peringatan dapat diambil berdasarkan nama, grup sumber daya, atau langganan.
  * Cmdlet baru New-AzureRmActionGroup
    - Cmdlet baru untuk membuat objek ActionGroup di memori (tidak ada permintaan yang terlibat.)
  * Cmdlet baru New-AzureRmActivityLogAlertCondition
    - Cmdlet baru untuk membuat objek kondisi daun peringatan log aktivitas dalam memori (tidak ada permintaan yang terlibat.)
  * Cmdlet baru Set-AzureRmActivityLogAlert
    - Cmdlet baru untuk membuat atau memperbarui peringatan log aktivitas.
  * Cmdlet baru Remove-AzureRmActivityLogAlert
    - Cmdlet baru untuk menghapus satu peringatan log aktivitas.
  * Cmdlet baru Set-AzureRmActionGroup
    - Cmdlet baru untuk membuat grup tindakan baru atau memperbarui yang sudah ada.
  * Cmdlet baru Get-AzureRmActionGroup
    - Cmdlet baru untuk mengambil satu atau beberapa grup tindakan.
    - Grup tindakan dapat diambil berdasarkan nama, grup sumber daya, atau langganan.
  * Cmdlet baru Remove-AzureRmActionGroup
    - Cmdlet baru untuk menghapus satu grup aksi.
  * Cmdlet baru New-AzureRmActionGroupReceiver
    - Cmdlet baru untuk membuat penerima grup tindakan baru dalam memori.
* Az.KeyVault
  * Cmdlet baru/diperbarui guna mendukung penghapusan sementara untuk sertifikat KeyVault
    * Get-AzureKeyVaultCertificate
    * Remove-AzureKeyVaultCertificate
    * Undo-AzureKeyVaultCertificateRemoval
* Jaringan
  * Menambahkan dukungan untuk layanan titik akhir ke Subnet Virtual Network
    - Memperbarui Add-AzureRmVirtualSubnetConfig: Menambahkan parameter opsional -ServiceEndpoint
    - Memperbarui New-AzureRmVirtualSubnetConfig: Menambahkan parameter opsional -ServiceEndpoint
    - Memperbarui Set-AzureRmVirtualSubnetConfig: Menambahkan parameter opsional -ServiceEndpoint
  * Menambahkan cmdlet ke daftar layanan titik akhir yang tersedia di lokasi
    - Get-AzureRmVirtualNetworkAvailableEndpointService
  * Menambahkan kemampuan untuk mengonfigurasi autentikasi P2S berbasis radius eksternal ke commandlet berikut
    - New-AzureVirtualNetworkGateway
    - Set-AzureVirtualNetworkGateway
    - Set-AzureRmVirtualNetworkGatewayVpnClientConfig
  * Menambahkan cmdlet guna memungkinkan pembuatan VpnProfiles untuk P2S berbasis radius eksternal
    - New-AzureRmVpnClientConfiguration
    - Get-AzureRmVpnClientConfiguration
  * Menambahkan dukungan untuk parameter SKU ke Alamat IP Publik dan Penyeimbang Beban
    - Memperbarui New-AzureRMLoadBalancer: Menambahkan parameter opsional -Sku
    - Memperbarui New-AzureRMPublicIpAddress: Menambahkan parameter opsional -Sku
  * Menambahkan dukungan untuk DisableOutboundSNAT ke Aturan Penyeimbang Beban
    - Memperbarui New-AzureRMLoadBalancerRuleConfig: Menambahkan parameter opsional DisableOutboundSNAT
    - Memperbarui Add-AzureRMLoadBalancerRuleConfig: Menambahkan parameter opsional DisableOutboundSNAT
    - Memperbarui Set-AzureRMLoadBalancerRuleConfig: Menambahkan parameter opsional DisableOutboundSNAT
  * Menambahkan dukungan untuk IkeV2 P2S
    - Memperbarui New-AzureRmVirtualNetworkGateway: Menambahkan parameter opsional -VpnClientProtocol, default ke [ "SSTP", "IkeV2" ]
    - Memperbarui Set-AzureRmVirtualNetworkGateway: Menambahkan parameter opsional -VpnClientProtocol
  * Menambahkan dukungan untuk aturan MultiValued dalam Aturan Keamanan Jaringan dan Aturan Keamanan Jaringan yang Efektif
    - Memperbarui Add-AzureRmNetworkSecurityRuleConfig: Memperbarui parameter SourcePortRange, DestinationPortRange, SourceAddressPrefix untuk menerima daftar string
    - Memperbarui New-AzureRmNetworkSecurityRuleConfig: Memperbarui parameter SourcePortRange, DestinationPortRange, SourceAddressPrefix untuk menerima daftar string
    - Memperbarui Set-AzureRmNetworkSecurityRuleConfig: Memperbarui parameter SourcePortRange, DestinationPortRange, SourceAddressPrefix untuk menerima daftar string
    - Memperbarui Add-AzureRmNetworkSecurityRuleConfig: Memperbarui parameter SourcePortRange, DestinationPortRange, SourceAddressPrefix untuk menerima daftar string
    - Memperbarui New-AzureRmNetworkSecurityGroup: Memperbarui parameter SecurityRules untuk menerima parameter SourcePortRange, DestinationPortRange, SourceAddressPrefix yang merupakan daftar string di objek PSSecurityRule
    - Memperbarui Get-AzureRmEffectiveNetworkSecurityGroup: Menambahkan parameter TagMap
    - Memperbarui Get-AzureRmEffectiveNetworkSecurityGroup: Memperbarui objek PSEffectiveSecurityRule dengan parameter SourcePortRange, DestinationPortRange, SourceAddressPrefix yang merupakan daftar string.
  * Menambahkan dukungan untuk perlindungan DDoS untuk jaringan virtual
    - Memperbarui New-AzureRmVirtualNetwork: Menambahkan parameter switch EnableDDoSProtection dan EnableVmProtection
    - Menambahkan properti EnableDDoSProtection dan EnableVmProtection di objek PSVirtualNetwork
  * Menambahkan dukungan untuk Penyeimbang Beban Internal yang Sangat Tersedia
    - Memperbarui Add-AzureRmLoadBalancerRuleConfig: Menambahkan Semua sebagai nilai yang dapat diterima oleh parameter Protokol
    - Memperbarui New-AzureRmLoadBalancerRuleConfig: Menambahkan Semua sebagai nilai yang dapat diterima oleh parameter Protokol
    - Memperbarui Set-AzureRmLoadBalancerRuleConfig: Menambahkan Semua sebagai nilai yang dapat diterima oleh parameter Protokol
  * Menambahkan dukungan untuk Grup Keamanan Aplikasi
    - Menambahkan New-AzureRmApplicationSecurityGroup
    - Menambahkan Get-AzureRmApplicationSecurityGroup
    - Menambahkan Remove-AzureRmApplicationSecurityGroup
    - Memperbarui New-AzureRmNetworkInterface: Menambahkan parameter opsional ApplicationSecurityGroup dan ApplicationSecurityGroupId
    - Memperbarui New-AzureRmNetworkInterfaceIpConfig: Menambahkan parameter opsional ApplicationSecurityGroup dan ApplicationSecurityGroupId
    - Memperbarui Add-AzureRmNetworkInterfaceIpConfig: Menambahkan parameter opsional ApplicationSecurityGroup dan ApplicationSecurityGroupId
    - Memperbarui Set-AzureRmNetworkInterfaceIpConfig: Menambahkan parameter opsional ApplicationSecurityGroup dan ApplicationSecurityGroupId
    - Memperbarui New-AzureRmNetworkSecurityRuleConfig: Menambahkan parameter opsional SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, dan DestinationApplicationSecurityGroupId
    - Memperbarui Add-AzureRmNetworkSecurityRuleConfig: Menambahkan parameter opsional SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, dan DestinationApplicationSecurityGroupId
    - Memperbarui Set-AzureRmNetworkSecurityRuleConfig: Menambahkan parameter opsional SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, dan DestinationApplicationSecurityGroupId
  * Menambahkan perintah baru untuk Skrip VpnDeviceConfiguration
    - Get-AzureRmVirtualNetworkGatewaySupportedVpnDevices
    - Get-AzureRmVirtualNetworkGatewayConnectionVpnDeviceConfigScript
* Profil
  * Start-Job Support untuk cmdlet AzureRm.
    * Semua AzureRmCmdlets menambahkan parameter -AzureRmContext, yang dapat menerima konteks (output dari cmdlet Konteks).
      - Pola umum untuk pekerjaan dengan persistensi konteks DINONAKTIFKAN: `Start-Job {param ($context) New-AzureRmVM -AzureRmContext $context [... other parameters]} -ArgumentList (Get-AzureRmContext)`
      - Pola umum untuk pekerjaan dengan persistensi konteks DIAKIFKAN:`Start-Job {New-AzureRmVM [... other parameters]}`
  * Pertahankan informasi masuk di seluruh sesi, cmdlet baru:
    - Enable-AzureRmContextAutosave - Mengaktifkan persistensi info masuk di seluruh sesi.
    - Disable-AzureRmContextAutosave - Menonaktifkan persistensi info masuk di seluruh sesi.
  * Mengelola informasi konteks, cmdet baru
    - Select-AzureRmContext - Memilih konteks bernama aktif.
    - Rename-AzureRmContext - Mengganti nama konteks yang jelas untuk referensi yang mudah.
    - Remove-AzureRmContext - Menghapus konteks yang ada.
    - Remove-AzureRmAccount - Menghapus semua info masuk, langganan, dan penyewa yang terkait dengan akun.
  * Mengelola informasi konteks, perubahan cmdlet:
    - Menambahkan Cakupan = (Proses | CurrentUser) ke semua cmdlet yang mengubah info masuk
    - Get-AzureRmContext - Menambahkan parameter ListAvailable ke daftar semua konteks yang disimpan
* Sumber
  * Menambahkan cmdlet PolicySetDefinition
    - Cmdlet New-AzureRmPolicySetDefinition untuk membuat definisi set kebijakan
    - Cmdlet Get-AzureRmPolicySetDefinition untuk mencantumkan semua definisi yang ditetapkan kebijakan atau untuk mendapatkan definisi set kebijakan tertentu
    - Cmdlet Remove-AzureRmPolicySetDefinition untuk menghapus definisi set kebijakan
    - Cmdlet Set-AzureRmPolicySetDefinition untuk memperbarui definisi set kebijakan yang ada
  * Tambahkan parameter -PolicySetDefinition, -Sku dan -NotScope ke cmdlet New-AzureRmPolicyAssignment dan Set-AzureRmPolicyAssignment
  * Menambahkan dukungan untuk meneruskan url kebijakan ke cmdlet New-AzureRmPolicyDefinition dan Set-AzureRmPolicyDefinition
  * Tambahkan parameter -Mode ke cmdlet New-AzureRmPolicyDefinition
  * Tambahkan Dukungan untuk penghapusan roleassignment menggunakan objek PSRoleAssignment
    - Pengguna sekarang dapat menggunakan PSRoleassignmnet inputobject dengan commandlet Remove-AzureRMRoleAssignment untuk menghapus roleassignment.
  * Menambahkan cmdlet ManagedApplication
    - Cmdlet New-AzureRmManagedApplication untuk membuat aplikasi terkelola
    - Cmdlet Get-AzureRmManagedApplication untuk mencantumkan semua aplikasi terkelola di bawah langganan atau untuk mendapatkan aplikasi terkelola tertentu
    - Cmdlet Remove-AzureRmManagedApplication untuk menghapus aplikasi terkelola
    - Cmdlet Set-AzureRmManagedApplication untuk memperbarui aplikasi terkelola yang sudah ada
  * Menambahkan cmdlet ManagedApplicationDefinition
    - Cmdlet New-AzureRmManagedApplicationDefinition untuk membuat definisi aplikasi terkelola menggunakan file zip uri atau menggunakan file json mainTemplate dan createUiDefinition
    - Cmdlet Get-AzureRmManagedApplicationDefinition untuk mencantumkan semua definisi aplikasi terkelola di bawah grup sumber daya atau untuk mendapatkan definisi aplikasi terkelola tertentu
    - Cmdlet Remove-AzureRmManagedApplicationDefinition untuk menghapus definisi aplikasi terkelola
    - Cmdlet Set-AzureRmManagedApplicationDefinition untuk memperbarui definisi aplikasi terkelola yang ada
* Sql
  * Menambahkan dukungan untuk Aturan Virtual Network
    - Menambahkan cmdlet Get-AzureRmSqlServerVirtualNetworkRule yang mendapatkan aturan jaringan virtual dengan nama aturan tertentu atau daftar aturan jaringan virtual di server Azure Sql.
    - Menambahkan cmdlet Set-AzureRmSqlServerVirtualNetworkRule yang mengubah jaringan virtual yang ditunjukkan oleh aturan.
    - Menambahkan cmdlet Remove-AzureRmSqlServerVirtualNetworkRule yang menghapus aturan jaringan virtual untuk server Azure Sql.
    - Menambahkan cmdlet New-AzureRmSqlServerVirtualNetworkRule yang membuat aturan jaringan virtual baru untuk server Azure Sql.
* Website
  * Menambahkan Tingkat PremiumV2 untuk Paket App Service
* Azure.Storage
  * Tingkatkan ke Pustaka Klien Azure Storage 8.4.0 dan Pustaka DataMovement Azure Storage 0.6.1
  * Tambahkan Dukungan PremiumPageBlobTier di Unggah dan Salin Blob API
    - Set-AzureStorageBlobContent
    - Start-AzureStorageBlobCopy
  * Menyempurnakan Format Output Konsol AzureStorageContainer, AzureStorageBlob, AzureStorageQueue, AzureStorageTable
    - Get-AzureStorageContainer
    - Get-AzureStorageBlob
    - Get-AzureStorageQueue
    - Get-AzureStorageTable

## <a name="20170810---version-431"></a>2017.08.10 - Versi 4.3.1
  * Melakukan pembaruan untuk memperbaiki masalah penandatanganan perakitan

## <a name="20170807---version-430"></a>2017.08.07 - Versi 4.3.0
* AnalysisServices
  * Memperbaiki bug di Set-AzureRmAnalysisServciesServer
    - Ketika admin tidak disediakan, admin akan dihapus.
  * Menambahkan BackupBlobContainerUri di New-AzureRmAnalysisServicesServer dan Set-AzureRmAnalysisServicesServer
    - Aktifkan guna mengatur/menonaktifkan kontainer blob cadangan untuk mencadangkan/memulihkan Server Azure Analysis Services
  * Memperbarui pencarian Sku di New-AzureRmAnalysisServicesServer dan Set-AzureRmAnalysisServicesServer
    - Mengubah Sku berkode keras menjadi pencarian dinamis.
  * Add-AzureAnalysisServicesAccount untuk mendukung masuk dengan Perwakilan Layanan
* Automation
  * Membuat perubahan pada cmdlet AutomationDSC* untuk menarik lebih dari 100 rekaman
  * Mengatasi masalah di mana aliran Verbose berhenti berfungsi setelah memanggil beberapa cmdlet Automation (misalnya Get-AzureRmAutomationVariable, Get-AzureRmAutomationJob).
  * Dukungan untuk versi NodeConfiguration Build ditambahkan di StartAzureAutomationDscCompilationJob dan ImportAzureAutomationDscNodeConfiguration
  * Perbaikan bug untuk masalah yang ada - Memperbaiki masalah alias #3775 dan alias runOn serta dukungan untuk HybridWorkers.
* Compute
  * Set-AzureRmVMAEMExtension: Menambahkan dukungan untuk ukuran Disk Premium baru
  * Set-AzureRmVMAEMExtension: Menambahkan dukungan untuk seri M
  * Menambahkan parameter ForceUpdateTag ke Add-AzureRmVmssExtension
  * Menambahkan parameter Primer ke New-AzureRmVmssIpConfig
  * Menambahkan parameter EnableAcceleratedNetworking ke Add-AzureRmVmssNetworkInterfaceConfig
  * Menambahkan InstanceId ke Set-AzureRmVmss
  * Mengekspos MaintenanceRedeployStatus ke Get-AzureRmVM -Output status
  * Mengekspos Pembatasan dan Kemampuan ke format tabel Get-AzureRmComputeResourceSku
* DataLakeStore
  * Memperbaiki masalah: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
  * menambahkan properti ResourceGroup ke NamespaceAttributes
    - 'ResourceGroup' Mendapatkan nama grup sumber daya tempat Namespace berada
  * cmdlet yang diperbarui dengan Parametersets untuk Namespace dan EventHub untuk pengoperasian AuthorizationRule
    - New-AzureRmEventHubAuthorizationRule - Menambahkan AuthorizationRule baru ke NameSpace atau EventHub yang ada.
    - Get-AzureRmEventHubAuthorizationRule - Mendapat AuthorizationRule/Daftar AuthorizationRules untuk NameSpace atau EventHub yang ada.
    - Set-AzureRmEventHubAuthorizationRule - Memperbarui properti AuthorizationRule dari EventHub NameSpace yang ada.
    - Remove-AzureRmEventHubAuthorizationRule - Menghapus AuthorizationRule yang ada dari NameSpace atau EventHub yang ada.
    - New-AzureRmEventHubKey - Menghasilkan Kunci Primer/Sekunder baru untuk AuthorizationRule dari NameSpace atau EventHub yang ada.
    - Get-AzureRmEventHubKey - Mendapat Kunci Primer/Sekunder untuk AuthorizationRule dari NameSpace atau EventHub yang ada.
* Jaringan
    * Menambahkan dukungan IPv6 dan parameter opsional baru -PeerAddressType
      * New-AzureRmExpressRouteCircuitPeeringConfig:
      * Set-AzureRmExpressRouteCircuitPeeringConfig: Menambahkan dukungan IPv6. Parameter opsional baru ditambahkan
      * Remove-AzureRmExpressRouteCircuitPeeringConfig: Menambahkan dukungan IPv6. Parameter opsional baru ditambahkan
    * Parameter yang ditandai -ProbeEnabled sebagai tidak digunakan
      - Tambahkan-AzureRmApplicationGatewayBackendHttpSettings
      - New-AzureRmApplicationGatewayBackendHttpSettings
      - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profil
    * Pengumpulan data telah diaktifkan secara default. Data penggunaan dikumpulkan oleh Microsoft untuk meningkatkan pengalaman pengguna. Data bersifat anonim dan tidak menyertakan nilai argumen baris perintah.
      - Gunakan cmdlet Disable-AzureRmDataCollection untuk menonaktifkan fitur
      - Gunakan cmdlet Enable-AzureRmDataCollection untuk mengaktifkan fitur ini
* Sumber
    * Tambahkan Dukungan validasi cakupan untuk definisi peran dan perintah penetapan peran berikut sebelum mengirim permintaan ke ARM
      - Get-AzureRMRoleAssignment
      - New-AzureRMRoleAssignment
      - Remove-AzureRMRoleAssignment
      - Get-AzureRMRoleDefinition
      - New-AzureRMRoleDefinition
      - Remove-AzureRMRoleDefinition
      - Set-AzureRMRoleDefinition
* ServiceBus
  * Tambahkan commandlet baru di bawah ini untuk AuthorizationRules NameSpace, Queue dan Topic. sesuai dengan set parameter, operasi aturan otorisasi dilakukan.
    - New-AzureRmServiceBusAuthorizationRule - Menambahkan AuthorizationRule baru ke ServiceBus NameSpace/Antrean/Topik yang ada.
    - Get-AzureRmServiceBusAuthorizationRule - Mendapat AuthorizationRule/Daftar AuthorizationRules untuk ServiceBus NameSpace/Antrean/Topik yang ada.
    - Set-AzureRmServiceBusAuthorizationRule - Memperbarui properti AuthorizationRule Servicebus NameSpace/Antrean/Topik yang ada.
    - New-AzureRmServiceBusKey - Menghasilkan Kunci Primer/Sekunder baru untuk AuthorizationRule ServiceBus NameSpace/Antrean/Topik yang ada.
    - Get-AzureRmServiceBusKey - Mendapat Kunci Primer/Sekunder untuk AuthorizationRule NameSpace/Antrean/Topik yang ada.
    - Remove-AzureRmServiceBusNamespaceAuthorizationRule - Menghapus AuthorizationRule ServiceBus NameSpace/Antrean/Topik yang ada.
  * Menambahkan properti Grup Sumber Daya ke NamespceAttributes

* Sql
    * Memperbarui Set-AzureRmSqlServerTransparentDataEncryptionProtector untuk menampilkan peringatan dan memerlukan konfirmasi jika jenis Pelindung Enkripsi sedang diatur ke AzureKeyVault
    * Menambahkan cmdlet baru yang diperbarui untuk pengaturan Audit
      - Cmdlet Get-AzureRmSqlDatabaseAuditing yang mendapatkan pengaturan audit database Azure SQL.
      - Cmdlet Get-AzureRmSqlServerAuditing yang mendapatkan pengaturan audit server Azure SQL.
      - Cmdlet Set-AzureRmSqlDatabaseAuditing yang mengubah pengaturan audit untuk database Azure SQL.
      - Cmdlet Set-AzureRmSqlServerAuditing yang mengubah pengaturan audit server Azure SQL.
    * Menghentikan cmdlet kebijakan Audit yang ada
      - Get-AzureRmSqlDatabaseAuditingPolicy
      - Get-AzureRmSqlServerAuditingPolicy
      - Set-AzureRmSqlDatabaseAuditingPolicy
      - Set-AzureRmSqlServerAuditingPolicy
      - Use-AzureRmSqlServerAuditingPolicy
      - Remove-AzureRmSqlDatabaseAuditing
      - Remove-AzureRmSqlServerAuditing
    * Penguraian file skema untuk Update-AzureRmSqlSyncGroup sekarang tidak peka huruf besar-kecil.
* Penyimpanan
    * Menambahkan dukungan NeworkRule ke cmdlet akun penyimpanan mode sumber daya
      - New-AzureRmStorageAccount
      - Set-AzureRmStorageAccount
      - Get-AzureRmStorageAccountNetworkRuleSet
      - Update-AzureRmStorageAccountNetworkRuleSet
      - Add-AzureRmStorageAccountNetworkRule
      - Remove-AzureRmStorageAccountNetworkRule

## <a name="20170717---version-421"></a>2017.07.17 - Versi 4.2.1
* Compute
  - Memperbaiki masalah terkait VM DIsk dan snapshot VM Disk membuat dan memperbarui cmdlet, (link)[<https://github.com/azure/azure-powershell/issues/4309>]
    - New-AzureRmDisk
    - New-AzureRmSnapshot
    - Update-AzureRmDisk
    - Update-AzureRmSnapshot
* Profil
  - Memperbaiki masalah terkait autentikasi pengguna non-interaktif di RDFE (link)[<https://github.com/Azure/azure-powershell/issues/4299>]

* ServiceManagement
  - Memperbaiki masalah terkait autentikasi pengguna non-interaktif (link)[<https://github.com/Azure/azure-powershell/issues/4299>]

## <a name="2017711---version-420"></a>2017.7.11 - Versi 4.2.0
* AnalysisServices
    * Menambahkan API dataplane baru
        - Memperkenalkan API untuk mengambil log server AS, Export-AzureAnalysisServicesInstanceLog
* Automation
    * Mengatur nilai TimeZone dengan benar untuk jadwal Mingguan dan Bulanan untuk New-AzureRmAutomationSchedule
        - Informasi lebih lanjut dapat ditemukan dalam edisi ini: https://github.com/Azure/azure-powershell/issues/3043
* AzureBatch
    - Menambahkan cmdlet Get-AzureBatchJobPreparationAndReleaseTaskStatus baru.
    - Menambahkan rentang byte awal dan akhir ke parameter Get-AzureBatchNodeFileContent.
* CognitiveServices
    * Integrasikan dengan SDK Manajemen Cognitive Services versi 1.0.0.
    * Perbaiki bug pemeriksaan panjang nama akun.
* Compute
    * Jenis akun penyimpanan mendukung disk Gambar:
        - Parameter 'StorageAccountType' ditambahkan ke Set-AzureRmImageOsDisk dan Add-AzureRmImageDataDisk
    * Fitur PrivateIP dan PublicIP dalam Konfigurasi Ip Vmss:
        - 'PrivateIPAddressVersion', 'PublicIPAddressConfigurationName', 'PublicIPAddressConfigurationIdleTimeoutInMinutes', nama 'DnsSetting' ditambahkan ke New-AzureRmVmssIpConfig
        - Parameter 'PrivateIPAddressVersion' untuk menentukan IPv4 atau IPv6 ditambahkan ke New-AzureRmVmssIpConfig
    * Fitur Pemeliharaan Performa:
        - Parameter switch 'PerformMaintenance' ditambahkan ke Restart-AzureRmVM.
        - Get-AzureRmVM -Status menunjukkan informasi pemeliharaan performa VM yang diberikan
    * Fitur Identitas Mesin Virtual:
        - Parameter 'IdentityType' ditambahkan ke New-AzureRmVMConfig dan UpdateAzureRmVM
        - Get-AzureRmVM menunjukkan informasi identitas VM yang diberikan
    * Fitur Identitas Vmss:
        - Parameter 'IdentityType' ditambahkan ke New-AzureRmVmssConfig
        - Get-AzureRmVmss menunjukkan informasi identitas Vmss yang diberikan
    * Fitur Diagnostik Boot Vmss:
        - Cmdlet baru untuk emngatur diagnostik boot objek Vmss: Set-AzureRmVmssBootDiagnostics
        - Parameter 'BootDiagnostic' ditambahkan ke New-AzureRmVmssConfig
    * Fitur LicenseType Vmss:
        - Parameter 'LicenseType' ditambahkan ke New-AzureRmVmssConfig
    * Dukungan RecoveryPolicyMode:
        - Parameter 'RecoveryPolicyMode' ditambahkan ke New-AzureRmVmssConfig
    * Fitur Sku Sumber Daya Komputasi:
        - Cmdlet baru 'Get-AzureRmComputeResourceSku' mencantumkan semua sku sumber daya komputasi
* DataFactories
    * Menghentikan New-AzureRmDataFactoryGatewayKey
    * Memperkenalkan fitur kunci autentikasi gateway dengan menambahkan New-AzureRmDataFactoryGatewayAuthKey dan Get-AzureRmDataFactoryGatewayAuthKey
* DataLakeAnalytics
    * Tambahkan dukungan untuk CRUD Kebijakan Komputasi melalui perintah berikut:
        - New-AzureRMDataLakeAnalyticsComputePolicy
        - Get-AzureRMDataLakeAnalyticsComputePolicy
        - Remove-AzureRMDataLakeAnalyticsComputePolicy
        - Update-AzureRMDataLakeAnalyticsComputePolicy
    * Tambahkan dukungan untuk metadata hubungan pekerjaan guna membantu pekerjaan berulang dan alur pekerjaan. Perintah berikut diperbarui atau ditambahkan:
        - Submit-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJobRecurrence
        - Get-AzureRMDataLakeAnalyticsJobPipeline
    * Memperbarui audiens token untuk API pekerjaan dan katalog guna menggunakan audiens spesifik Data Lake yang benar, bukan audiens Azure Resource.
* DataLakeStore
    * Menambahkan dukungan untuk rotasi tombol KeyVault yang dikelola pengguna di cmdlet Set-AzureRMDataLakeStoreAccount
    * Menambahkan pembaruan kualitas hidup untuk secara otomatis memicu panggilan `enableKeyVault` saat KeyVault yang dikelola pengguna ditambahkan atau saat kunci diputar.
    * Memperbarui audiens token untuk API pekerjaan dan katalog guna menggunakan audiens spesifik Data Lake yang benar, bukan audiens Azure Resource.
    * Memperbaiki bug yang membatasi ukuran file yang dibuat/ditambahkan menggunakan cmdlet berikut:
        - New-AzureRmDataLakeStoreItem
        - Add-AzureRmDataLakeStoreItemContent
* Dns
    * Perbaiki bug dalam skenario penyaluran untuk Get-AzureRmDnsZone
        - Informasi selengkapnya dapat ditemukan di sini: https://github.com/Azure/azure-powershell/issues/4203
* HDInsight
    * Menambahkan dukungan untuk mengaktifkan/menonaktifkan Rangkaian Manajemen Operasi (OMS)
    * Cmdlet baru
        - Enable-AzureRmHDInsightOperationsManagementSuite
        - Disable-AzureRmHDInsightOperationsManagementSuite
        - Get-AzureRmHDInsightOperationsManagementSuite
    * Menambahkan parameter baru untuk mengatur konfigurasi kustom Spark ke Add-AzureRmHDInsightConfigValues
        - Parameter SparkDefaults dan SparkThriftConf untuk Spark 1.6
        - Parameter Spark2Defaults dan Spark2ThriftConf untuk Spark 2.0
* Wawasan
    * Masalah #4215 (perubahan permintaan) menghapus batas 15 hari di jendela waktu untuk cmdlet Get-AzureRmLog. Juga perubahan kecil pada nama pengujian unit.
    * Masalah #3957 diperbaiki untuk Get-AzureRmLog
        - Masalah #1: Backend mengembalikan catatan di halaman masing-masing 200 catatan, ditautkan oleh token kelanjutan ke halaman berikutnya. Pelanggan melihat cmdlet hanya mengembalikan 200 catatan padahal mereka tahu ada lebih banyak lagi. Ini terjadi terlepas dari nilai yang mereka tetapkan untuk MaxEvents, kecuali nilai itu kurang dari 200.
        - Masalah # 2: Dokumentasi berisi data yang salah tentang cmdlet ini, misalnya: timewindow default adalah 1 jam.
        - Perbaiki # 1: Cmdlet sekarang mengikuti token kelanjutan yang dikembalikan oleh backend hingga mencapai MaxEvents atau akhir set.<br>Nilai default untuk MaxEvents adalah 1000 dan maksimumnya adalah 100.000. Nilai apa pun untuk MaxEvents yang kurang dari 1 diabaikan dan nilai default digunakan sebagai gantinya. Nilai dan perilaku ini tidak berubah, nilai tersebut sekarang didokumentasikan dengan benar.<br>Alias untuk MaxEvents telah ditambahkan-MaxRecords- karena nama cmdlet tidak berbicara tentang peristiwa lagi, tetapi hanya tentang Log.
        - Perbaiki # 2: Dokumentasi berisi informasi yang benar dan lebih rinci: alias baru, jendela waktu yang benar, default yang benar, nilai minimum, dan nilai maksimum.
* Az.KeyVault
    * Hapus alamat email dari kueri direktori saat -UserPrincipalName ditentukan ke cmdlet Set-AzureRMKeyVaultAccessPolicy dan Remove-AzureRMKeyVaultAccessPolicy.
      - Kedua Cmdlet sekarang memiliki parameter -EmailAddress yang dapat digunakan, bukan parameter -UserPrincipalName ketika permintaan alamat email sudah sesuai.  Jika ada lebih dari satu alamat email yang cocok di direktori maka Cmdlet akan gagal.
* Jaringan
    * New-AzureRmIpsecPolicy: SALifeTimeSeconds dan SADataSizeKilobytes tidak lagi menjadi parameter wajib
        - SALifeTimeSeconds default hingga 27.000 detik
        - SADataSizeKilobytes default hingga 10.2400.000 KB
    * Menambahkan dukungan untuk konfigurasi suite cipher kustom menggunakan kebijakan ssl dan mencantumkan semua api opsi ssl di Application Gateway
        - Menambahkan parameter opsional -PolicyType, -PolicyName, -MinProtocolVersion, -Ciphersuite
            - Add-AzureRmApplicationGatewaySslPolicy
            - New-AzureRmApplicationGatewaySslPolicy
            - Set-AzureRmApplicationGatewaySslPolicy
        - Menambahkan Get-AzureRmApplicationGatewayAvailableSslOptions (Alias: List-AzureRmApplicationGatewayAvailableSslOptions)
        - Menambahkan Get-AzureRmApplicationGatewaySslPredefinedPolicy (Alias: List-AzureRmApplicationGatewaySslPredefinedPolicy)
    * Menambahkan dukungan pengalihan di Application Gateway
        - Menambahkan Add-AzureRmApplicationGatewayRedirectConfiguration
        - Menambahkan Get-AzureRmApplicationGatewayRedirectConfiguration
        - Menambahkan New-AzureRmApplicationGatewayRedirectConfiguration
        - Menambahkan Remove-AzureRmApplicationGatewayRedirectConfiguration
        - Menambahkan Set-AzureRmApplicationGatewayRedirectConfiguration
        - Menambahkan parameter opsional -RedirectConfiguration
            - Add-AzureRmApplicationGatewayRequestRoutingRule
            - New-AzureRmApplicationGatewayRequestRoutingRule
            - Set-AzureRmApplicationGatewayRequestRoutingRule
        - Menambahkan parameter opsional -DefaultRedirectConfiguration
            - Add-AzureRmApplicationGatewayUrlPathMapConfig
            - New-AzureRmApplicationGatewayUrlPathMapConfig
            - Set-AzureRmApplicationGatewayUrlPathMapConfig
        - Menambahkan parameter opsional -RedirectConfiguration
            - Add-AzureRmApplicationGatewayPathRuleConfig
            - New-AzureRmApplicationGatewayPathRuleConfig
            - Set-AzureRmApplicationGatewayPathRuleConfig
        - Menambahkan parameter opsional -RedirectConfiguration
            - New-AzureRmApplicationGateway
            - Set-AzureRmApplicationGateway
    * Menambahkan dukungan untuk situs azure di Application Gateway
        - Menambahkan New-AzureRmApplicationGatewayProbeHealthResponseMatch
        - Menambahkan parameter opsional -PickHostNameFromBackendHttpSettings, -MinServers, -Match
            - Add-AzureRmApplicationGatewayProbeConfig
            - New-AzureRmApplicationGatewayProbeConfig
            - Set-AzureRmApplicationGatewayProbeConfig
        - Menambahkan parameter opsional -PickHostNameFromBackendAddress, -AffinityCookieName, -ProbeEnabled, -Path
            - Tambahkan-AzureRmApplicationGatewayBackendHttpSettings
            - New-AzureRmApplicationGatewayBackendHttpSettings
            - Set-AzureRmApplicationGatewayBackendHttpSettings
    * Memperbarui Get-AzureRmPublicIPaddress untuk mengambil sumber daya publicipaddress yang dibuat melalui Set Skala VM
    * Menambahkan cmdlet untuk mendapatkan penggunaan jaringan virtual saat ini
        - Get-AzureRmVirtualNetworkUsageList
* Profil
    * Memperbaiki kesalahan saat menggunakan Import-AzureRmContext atau Save-AzureRmContext
        - Informasi lebih lanjut dapat ditemukan di edisi ini: https://github.com/Azure/azure-powershell/issues/3954
* RecoveryServices.SiteRecovery
    * Memperkenalkan modul baru untuk operasi Azure Site Recovery.
        - Semua cmdlet dimulai dengan AzureRmRecoveryServicesAsr*
* Sql
    * Menambahkan Cmdlet PowerShell Sinkronisasi Data ke AzureRM.Sql
    * Memperbarui cmdlet AzureRmSqlServer untuk menggunakan versi REST API baru yang menghindari batas waktu saat membuat server.
    * Cmdlet peningkatan server yang tidak digunakan lagi karena versi server lama (2.0) tidak ada lagi.
    * Menambahkan parameter switch opsional baru "AssignIdentity" ke cmdlet New-AzureRmSqlServer dan Set-AzureRmSqlServer untuk mendukung penyediaan identitas sumber daya untuk sumber daya server SQL
    * Parameter ResourceGroupName sekarang bersifat opsional untuk Get-AzureRmSqlServer
        - Informasi lebih lanjut dapat ditemukan dalam edisi ini: https://github.com/Azure/azure-powershell/issues/635
* ServiceManagement   untuk ExpressRoute:
    * Memperbarui cmdlet New-AzureBgpPeering untuk menambahkan opsi baru berikut:
        - PeerAddressType : Nilai "IPv4" atau "IPv6" dapat ditentukan untuk membuat Peering BGP dari jenis keluarga alamat yang sesuai
    * Perbarui cmdlet Set-AzureBgpPeering untuk menambahkan opsi baru berikut:
        - PeerAddressType : Nilai "IPv4" atau "IPv6" dapat ditentukan untuk memperbarui Peering BGP dari jenis keluarga alamat yang sesuai
    * Perbarui cmdlet Remove-AzureBgpPeering untuk menambahkan opsi baru berikut ini:
        - PeerAddressType : Nilai "IPv4", "IPv6" atau Semua dapat ditentukan untuk menghapus BGP Peering dari tipe keluarga alamat yang sesuai atau semuanya

## <a name="20170607---version-410"></a>2017.06.07 - Versi 4.1.0
* AnalysisServices
    * SKU baru ditambahkan: B1, B2, S0
    * Dukungan skala atas/bawah ditambahkan
* CognitiveServices
    * Memperbarui tampilan terperinci dari perjanjian lisensi saat membuat sumber daya Cognitive Services
* Compute
    * Memperbaiki Test-AzureRmVMAEMExtension untuk komputer virtual dengan beberapa disk terkelola
    * Memperbarui Set-AzureRmVMAEMExtension: Menambahkan informasi caching untuk disk terkelola Premium
    * Add-AzureRmVhd: Batas ukuran pada vhd ditingkatkan menjadi 4TB.
    * Stop-AzureRmVM: Memperjelas dokumentasi untuk parameter STayProvisioned
    * New-AzureRmDiskUpdateConfig
      * Parameter yang tidak digunakan lagi adalah CreateOption, StorageAccountId, ImageReference, SourceUri, SourceResourceId
    * Set-AzureRmDiskUpdateImageReference: Cmdlet yang tidakdigunakan lagi
    * New-AzureRmSnapshotUpdateConfig
      * Parameter yang tidak digunakan lagi adalah CreateOption, StorageAccountId, ImageReference, SourceUri, SourceResourceId
    * Set-AzureRmSnapshotUpdateImageReference: Cmdlet yang tidak digunakan lagi
* DataLakeStore
    * Enable-AzureRmDataLakeStoreKeyVault (Enable-AdlStoreKeyVault)
      * Mengaktifkan enkripsi terkelola KeyVault untuk Penyimpanan DataLake
* DevTestLab
    * Perbarui cmdlet agar berfungsi dengan versi API DevTest Labs saat ini maupun yang diperbarui.
* IotHub
    * Menambahkan dukungan Perutean untuk cmdlet IoTHub
* Az.KeyVault
  * Cmdlet Baru untuk mendukung Kunci Akun Penyimpanan yang Dikelola oleh KeyVault
    * Get-AzureKeyVaultManagedStorageAccount
    * Add-AzureKeyVaultManagedStorageAccount
    * Remove-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccountKey
    * Get-AzureKeyVaultManagedStorageSasDefinition
    * Set-AzureKeyVaultManagedStorageSasDefinition
    * Remove-AzureKeyVaultManagedStorageSasDefinition
* Jaringan
    * Get-AzureRmNetworkUsage: Cmdlet baru untuk menampilkan detail penggunaan dan kapasitas jaringan
    * Menambahkan opsi GatewaySku baru untuk VirtualNetworkGateways
        * VpnGw1, VpnGw2, VpnGw3 adalah Sku baru yang ditambahkan untuk gateway Vpn
    * Set-AzureRmNetworkWatcherConfigFlowLog
      * Memperbaiki contoh bantuan
* NotificationHubs
    * Pembaruan Transparan ke cmdlet NotificationHubs untuk API baru
* Profil
    * Resolve-AzureRmError
      * Cmdlet baru untuk menampilkan detail kesalahan dan pengecualian yang dilemparkan oleh cmdlet, termasuk permintaan/data respons server
    * Kirim-Tanggapan
      * Mengaktifkan pengiriman tanggapan tanpa masuk
    * Get-AzureRmSubscription
      * Memperbaiki bug dalam menerima langganan CSP
* Sumber
    * Memperbaiki masalah di mana Get-AzureRMRoleAssignment akan menghasilkan Permintaan Buruk jika jumlah roleassignments lebih dari 1.000
        * Pengguna sekarang dapat menggunakan Get-AzureRMRoleAssignment bahkan jika penugasan peran yang akan dikembalikan lebih besar dari 1.000
* Sql
    * Restore-AzureRmSqlDatabase: Memperbarui contoh dokumentasi
* Penyimpanan
    * Menambahkan dukungan pengaturan AssignIdentity ke cmdlet akun penyimpanan mode sumber daya
        * New-AzureRmStorageAccount
        * Set-AzureRmStorageAccount
    * Menambahkan Dukungan Kunci Pelanggan ke cmdlet akun penyimpanan mode sumber daya
        * Set-AzureRmStorageAccount
        * New-AzureRmStorageAccountEncryptionKeySource
* TrafficManager

    * Pengaturan Monitor Baru 'MonitorIntervalInSeconds', 'MonitorTimeoutInSeconds', 'MonitorToleratedNumberOfFailures'
    * Protokol Monitor Baru 'TCP'
* ServiceManagement
    * Add-AzureVhd: Batas ukuran pada vhd ditingkatkan hingga 4TB.
    * New-AzureBGPPeering: Mendukung LegacyMode
* Azure.Storage
    * Memperbarui bantuan untuk parameter yang menerima karakter wildcard dan memperbarui jenis StorageContext

## <a name="20170523---version-402"></a>2017.05.23 - Versi 4.0.2
* Profil
    * Add-AzureRmAccount
      * Menambahkan alias parameter `-EnvironmentName` untuk kompatibilitas mundur dengan versi 2.x AzureRM.profile

## <a name="20170512---version-401"></a>2017.05.12 - Versi 4.0.1
 * Memperbaiki masalah terkait New-AzureStorageContext dalam skenario offline: https://github.com/Azure/azure-powershell/issues/3939

## <a name="20170510---version-400"></a>2017.05.10 - Versi 4.0.0


* Rilis ini berisi perubahan yang berisiko. Silakan lihat [panduan migrasi](https://aka.ms/azps-migration-guide) untuk detail perubahan dan dampaknya pada skrip yang ada.
* ApiManagement
  - Menambahkan dukungan untuk mengonfigurasi grup eksternal di New-AzureRmApiManagementGroup.
* Billing
  - Cmdlet Baru Get-AzureRmBillingPeriod
    + cmdlet untuk mengambil periode penagihan Azure dari langganan.
  - Memperbarui Cmdlet Get-AzureRmBillingInvoice
  - properti baru BillingPeriodNames
  - output dalam tampilan daftar
* Compute
  - Memperbarui cmdlet Set-AzureRmVMAEMExtension dan Test-AzureRmVMAEMExtension untuk mendukung disk terkelola Premium
  - Mencadangkan pengaturan enkripsi untuk IaaS VM dan memulihkannya jika gagal
  - Sekarang Opsi ChefServiceInterval diganti namanya menjadi ChefDaemonInterval. Namun, yang lama akan terus bekerja.
  - Hapus properti DataDiskNames dan NetworkInterfaceIDs yang diduplikasi dari objek VM PS.
  - Jadikan parameter DataDiskNames dan NetworkInterfaceIDs opsional di masing-masing Remove-AzureRmVMDataDisk dan Remove-AzureRmVMNetworkInterface.
  - Perbaiki masalah penyaluran cmdlet Get saat cmdlet Get mengembalikan objek daftar.
  - Cmdlet yang bertentangan dengan cmdlet RDFE telah diganti namanya. Lihat https://github.com/Azure/azure-powershell/issues/2917 untuk detail selengkapnya.
    + `New-AzureVMSqlServerAutoBackupConfig` telah diubah namanya menjadi `New-AzureRmVMSqlServerAutoBackupConfig`
    + `New-AzureVMSqlServerAutoPatchingConfig` telah diubah namanya menjadi `New-AzureRmVMSqlServerAutoPatchingConfig`
    + `New-AzureVMSqlServerKeyVaultCredentialConfig` telah diubah namanya menjadi `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Consumption
  - Cmdlet Baru Get-AzureRmConsumptionUsageDetail
    + cmdlet untuk mengambil detail penggunaan langganan.
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
  - Menambahkan dukungan untuk get dan daftar paket katalog
  - Tambahkan dukungan untuk mencantumkan item katalog berikut dari elemen induk yang lebih dalam:
    + Tabel
    + TVF
    + Tampilan
    + Statistik
* DataLakeStore
  - Untuk melacak pengelogan `Import-AzureRMDataLakeStoreItem` dan `Export-AzureRMDataLakeStoreItem` telah dinonaktifkan secara default untuk meningkatkan performa. Jika pengelogan pelacakan diinginkan, silakan gunakan parameter `-DiagnosticLogLevel` dan `-DiagnosticLogPath`
  - Memperbaiki bug yang terkadang menyebabkan PowerShell macet saat mengunggah banyak file kecil ke ADLS.
* EventHub
  - Perbaikan bug:
    + Memperbaiki kesalahan cmdlet Set-AzureRmEventHubNamespace - 'Tier' tidak bisa null, di mana seharusnya 'SkuName'
    + Set-AzureRmEventHub - Memperbaiki kesalahan 'Referensi objek tidak diatur ke instans objek' saat memperbarui EventHub
* Wawasan
  - Add-AzureRm*AlertRule
    + Mengembalikan satu objek: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + Output sekarang dihitung, bukan dianggap sebagai objek tunggal. Jenisnya tidak berubah, masih daftar.
  - Remove-AzureRmAlertRule
    + StatusCode mengikuti kode status yang dikembalikan oleh permintaan, sebelum selalu Oke.
  - Add-AzureRmAutoscaleSetting
    + Sekarang mengembalikan satu objek (bukan daftar seperti sebelumnya) yang berisi statusCode, requestId, dan sumber daya yang baru dibuat/diperbarui.
    + Kode status mengikuti status yang dikembalikan oleh permintaan, sebelum selalu Oke.
  - New-AzureRmAutoscaleRule
    + Parameter ScaleActionType telah diperpanjang, sekarang parameter tersebut menerima nilai-nilai berikut: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + StatusCode dalam output mengikuti statusCode yang dikembalikan oleh permintaan. Sebelum parameter tersebut selalu Oke.
  - Get-AzureRMLogProfile
    + Output sekarang dihitung. Sebelumnya dianggap sebagai objek tunggal. Jenis output tetap menjadi daftar seperti sebelumnya.
  - Remove-AzureRmLogProfile
    + Parameter PassThru telah diimplementasikan.
  - API Metrik
    + SDK sekarang mengambil metrik dari MDM.
  - Get-AzureRmMetricDefinition
    + Outputnya masih berupa daftar, tetapi struktur daftar berubah.
  - Get-AzureRmMetric
    + Panggilan telah berubah. Ini adalah sintaks baru: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]
    + Outputnya berupa daftar, dan struktur elemennya telah berubah.
* Az.KeyVault
  - Menambahkan dukungan pencadangan/pemulihan untuk rahasia KeyVault
    + Rahasia dapat dicadangkan dan dipulihkan, cocok dengan fungsionalitas yang saat ini didukung untuk Keys

  - Cmdlet cadangan untuk Kunci dan Rahasia sekarang menerima objek yang sesuai sebagai parameter input
    + Penelepon dapat merangkai operasi pengambilan dan pencadangan: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - Cmdlet cadangan sekarang mendukung -switch Force untuk menimpa file yang sudah ada
    + Perhatikan bahwa upaya untuk menimpa file yang ada tidak akan lagi dibuang, dan sebagai gantinya akan meminta pengguna untuk memilih cara melanjutkan.
* LogicApp
  - Parameter baru untuk cmdlet pemulihan bencana Nomor Kontrol Interchange:
    + Parameter -AgreementType opsional ("X12", atau "Edifact") untuk menentukan nomor kontrol yang relevan
* MachineLearning
  - Menggunakan versi baru SDK .Net Azure Machine Learning dan menambahkan cmdlet baru
    + Add-AzureRmMlWebServiceRegionalProperty
  - Perbaikan kata-kata minor dalam teks bantuan.
* Jaringan
  - Menambahkan cmdlet Test-AzureRmNetworkWatcherConnectivity
    + Mengembalikan informasi konektivitas untuk VM sumber dan tujuan tertentu
    + Jika konektivitas antara sumber dan tujuan tidak dapat dibuat, cmdlet mengembalikan detail tentang masalah tersebut
* Profil
  - Menambahkan cmdlet 'Kirim-Tanggapan': memungkinkan pengguna untuk memulai serangkaian petunjuk yang mengirimkan tanggapan ke tim Azure PowerShell.
  - Alias berikut telah dihapus karena bertentangan dengan nama cmdlet yang ada di modul Azure:
    + `Enable-AzureDataCollection` (didukung oleh `Enable-AzureRmDataCollection`)
    + `Disable-AzureDataCollection` (didukung oleh `Disable-AzureRmDataCollection`)
* Relay
  - Menambahkan cmdlet untuk Azure Relay yang memungkinkan pengguna untuk membuat dan mengelola semua sumber daya Azure Relay.
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
* Sumber
  - Mendukung penyebaran lintas sumber daya grup untuk New-AzureRmResourceGroupDeployment
    + Pengguna sekarang dapat menggunakan penyebaran berlapis untuk disebarkan ke grup sumber daya yang berbeda.
* ServiceBus

  - Perbaikan Bug: Nilai properti objek Antrean ServiceBus ditetapkan ke null, objek digunakan sebagai parameter input di cmdlet Set-AzureRmServiceBusQueue untuk memperbarui Antrean.
    - Properti yang terpengaruh adalah LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount dan MessageCount
* ServiceFabric

  - Menambahkan cmdlet untuk fabric layanan
    + Add-AzureRmServiceFabricApplicationCertificate       Menambahkan sertifikat yang akan digunakan sebagai sertifikat aplikasi
    + Add-AzureRmServiceFabricClientCertificate       Menambahkan nama umum atau thumbprint ke pengaturan kluster untuk autentikasi klien
    + Add-AzureRmServiceFabricClusterCertificate       Menambahkan sertifikat kluster sekunder ke kluster untuk menggulirkan sertifikat yang ada
    + Add-AzureRmServiceFabricNodes       Menaambahkan node/VM dari jenis node tertentu ke kluster
    + Add-AzureRmServiceFabricNodeType       Menambahkan jenis node/VM ke kluster yang ada
    + Get-AzureRmServiceFabricCluster       Mendapatkan detail sumber daya kluster
    + New-AzureRmServiceFabricCluster Membuat kluster ServiceFabric baru. Perintah ini memiliki banyak kelebihan beban untuk mencakup berbagai skenario
    + Remove-AzureRmServiceFabricClientCertificate       Menghapus sertifikat klien agar tidak digunakan untuk mengakses kluster
    + Remove-AzureRmServiceFabricClusterCertificate       Menghapus sertifikat kluster agar tidak digunakan untuk keamanan kluster
    + Remove-AzureRmServiceFabricNodes       Menghapus node dari jenis node tertentu dari kluster
    + Remove-AzureRmServiceFabricNodeType       Menghapus tipe node dari sebuah cluster
    + Remove-AzureRmServiceFabricSettings       Menghapus satu atau beberapa pengaturan ServiceFabric dari kluster
    + Set-AzureRmServiceFabricSettings       Menambahkan atau memperbarui satu atau lebih pengaturan ServiceFabric dari sebuah kluster
    + Set-AzureRmServiceFabricUpgradeType       Mengubah jenis peningkatan ServiceFabric dari kluster
    + Update-AzureRmServiceFabricDurability       Mengubah tingkat durabilitas kluster
    + Update-AzureRmServiceFabricReliability       Mengubah tingkat keandalan kluster
* Sql
  - Menambahkan -parameter SampleName ke New-AzureRmSqlDatabase
  - Memperbarui ke cmdlet Grup Failover
  - Hapus parameter 'Tag'
  - Menghapus parameter 'PartnerResourceGroupName' dan 'PartnerServerName' dari cmdlet Remove-AzureRmSqlDatabaseFailoverGroup
  - Menambahkan parameter 'GracePeriodWithDataLossHours' ke cmdlet New- dan Set-, yang pada akhirnya akan menggantikan 'GracePeriodWithDataLossHour'
  - Dokumentasi telah disempurnakan dan diperbarui
  - Mengubah pemformatan objek yang dikembalikan dan memperbaiki beberapa bug di mana bidang tidak selalu diisi
  - Menambahkan properti 'DatabaseNames' dan 'PartnerLocation' ke objek Failover Grup Failover
  - Memperbaiki bug yang menyebabkan cmdlet Switch-segera kembali daripada menunggu operasi selesai
  - Memperbaiki bug luapan bilangan bulat saat nilai masa tenggang tinggi digunakan
  - Menyesuaikan masa tenggang hingga minimal 1 jam jika yang lebih rendah disediakan
  - Menghapus "Usage_Anomaly" dari nilai yang diterima untuk parameter "ExcludedDetectionType" dari cmdlet Set-AzureRmSqlDatabaseThreatDetectionPolicy dan cmdlet Set-AzureRmSqlServerThreatDetectionPolicy.
* Penyimpanan
  - Meningkatkan SDK SRP ke versi 6.3.0
  - New/Set-AzureRmStorageAccount:Menambahkan parameter baru untuk mendukung EnableHttpsTrafficOnly
  - New/Set/Get-AzureRmStorageAccount: Mengembalikan Akun Storage yang berisi atribut baru EnableHttpsTrafficOnly
* Azure.Storage
  - Meningkatkan ke Pustaka Klien Azure Storage 8.1.1 dan Pustaka DataMovement Azure Storage 0.5.1
  - Menambahkan cmdlet baru untuk mendukung fitur Salinan Inkremental blob
