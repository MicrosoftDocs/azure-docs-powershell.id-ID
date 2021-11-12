---
title: Azure PowerShell Log Perubahan | Microsoft Docs
description: Ini adalah riwayat perubahan yang dibuat untuk Azure PowerShell dalam rilis terbaru.
ms.devlang: powershell
ms.topic: conceptual
ms.workload: ''
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 0969a235e46b2a44a197968300f6eb22e733c03e
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429351"
---
# <a name="release-notes"></a>Catatan rilis

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Ini adalah daftar perubahan yang dibuat untuk Azure PowerShell dalam rilis ini.

---
## <a name="6130---november-2018"></a>6.13.0 - November 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Memperbarui dependensi untuk masalah pemetaan tipe

#### <a name="azurermautomation"></a>AzureRM.Automation
* Cmdlet Otomatisasi Azure berbasis Swagger
* Cmdlet Manajemen Pembaruan tambahan
* Cmdlet Kontrol Sumber Ditambahkan
* Cmdlet Remove-AzureRmAutomationHybridWorkerGroup tambahan
* Memperbaiki perintah Node Register DSC

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki masalah identitas untuk Identitas SystemAssigned
* Memperbarui dependensi untuk masalah pemetaan tipe

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Memperbarui dependensi untuk masalah pemetaan tipe

#### <a name="azurermmarketplaceordering"></a>AzureRM.MarketplaceOrdering
* perbarui deskripsi contoh untuk cmdlet marketplace

#### <a name="azurermnetwork"></a>AzureRM.Network
* Ditambahkan cmdlet New-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayCustomError, Get-AzureRmApplicationGatewayCustomError, Set-AzureRmApplicationGatewayCustomError, Remove-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayhttpListenerCustomError, Get-AzureRmApplicationGatewayhttpListenerCustomError, Set-AzureRmApplicationGatewayHttpListenerCustomError, Remove-AzureRmApplicationGatewayHttpListenerCustomError
* Menambahkan icMP kembali ke AzureFirewall Network Protocols yang didukung
* Perbarui cmdlet Test-AzureRmNetworkWatcherConnectivity, tambahkan validasi pada id tujuan, alamat dan port.
* Memperbaiki masalah penggunaan memori di Peta jaringan Virtual

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Perbaikan untuk mengubah kebijakan untuk berbagi file yang diproteksi.
* Zona waktu kebijakan yang dikonversi menjadi huruf besar.

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Contoh yang diperbaiki dalam New-AzureRmRecoveryServicesAsrProtectableItem
* Memperbarui dependensi untuk masalah pemetaan tipe

#### <a name="azurermrelay"></a>AzureRM.Relay
* Added optional Parameter -KeyValue to New-AzureRmRelayKey cmdlet, which enables user to provide KeyValue.

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbarui dokumentasi bantuan untuk parameter terkait identitas sumber daya `New-AzureRmPolicyAssignment` di dan `Set-AzureRmPolicyAssignment`
* Menambahkan contoh untuk New-AzureRmPolicyDefinition yang menggunakan -Metadata
* Perbaikan untuk memungkinkan mempertahankan huruf dalam tombol Tag di NetStandard: #7678 #7703

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Tambahkan pesan penghentian untuk perubahan yang akan datang

#### <a name="azurermsql"></a>AzureRM.Sql
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

## <a name="6120---november-2018"></a>6.12.0 - November 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime
* Ganti nama Id Tenant di cmdlet Connect-AzureRmAccount ke Tenant dan tambahkan alias untuk TenantId
* Deskripsi TenantId yang diperbarui untuk Connect-AzureRmAccount
* Pesan kesalahan perbaikan gagal masuk saat menyediakan domain penyewa
    - https://github.com/Azure/azure-powershell/issues/6936
* Perbaiki masalah terkait nama konteks yang bentrok untuk akun tanpa langganan dalam penyewa
    - https://github.com/Azure/azure-powershell/issues/7453
* Memperbaiki masalah titik akhir DataLake saat menggunakan MSI
    - https://github.com/Azure/azure-powershell/issues/7462
* Memperbaiki masalah ketika 'Disconnect-AzureRmAccount' akan muncul jika tidak tersambung
    - https://github.com/Azure/azure-powershell/issues/7167

#### <a name="azurermautomation"></a>AzureRM.Automation
* Nama file dll cmdlet yang diganti namanya Microsoft.Azure.Commands.Automation.dll

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Menambahkan Get-AzureRmCognitiveServicesAccountSkus operasi.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Menambahkan Add-AzureRmVmssVMDataDisk dan Remove-AzureRmVmssVMDataDisk cmdlets
* Get-AzureRmVMImage memperlihatkan AutomaticOSUpgradeProperties
* Memperbaiki nilai opsi SetAzureRmVMChefExtension -BootstrapOptions dan -JsonAttribute tidak diatur dalam format json.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Perbarui paket DataLake ke 1.1.10.
* Tambahkan Konkurensi default ke operasi multithreaded.

#### <a name="azurerminsights"></a>AzureRM. Insights
* Memperbaiki masalah #7267 (area Skala Otomatis)
    - Masalah dengan pembuatan aturan skala otomatis baru yang tidak mengatur parameter yang dienumerasi dengan benar (akan selalu mengaturnya ke nilai default).
* Memperbaiki masalah #7513 [Insights] Set-AzureRMDiagnosticSetting memerlukan spesifikasi kategori eksplisit selama pembuatan pengaturan
    - Sekarang cmdlet tidak mengharuskan indikasi kategori eksplisit untuk mengaktifkan selama pembuatan, misalnya saat kategori itu berfungsi sebagaimana didokumentasikan

#### <a name="azurermnetwork"></a>AzureRM.Network
* Changed PeeringType to be a mandatory parameter for the following cmdlets:-
    - Get-AzureRmExpressRouteCircuitRouteTable
    - Get-AzureRmExpressRouteCircuitARPTable
    - Get-AzureRmExpressRouteCircuitRouteTableSummary
    - Get-AzureRMExpressRouteCrossConnectionArpTable
    - Get-AzureRMExpressRouteCrossConnectionRouteTable
    - Get-AzureRMExpressRouteCrossConnectionRouteTableSummary

#### <a name="azurermpolicyinsights"></a>AzureRM.PolicyInsights
* Cmdlet perbaikan kebijakan yang ditambahkan

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Dukungan tambahan untuk berbagi file Azure dalam layanan pemulihan.

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbaikan untuk https://github.com/Azure/azure-powershell/issues/7402
    - Perbolehkan daftar sumber daya menggunakan parameter '-ResourceId' untuk 'Get-AzureRmResource'

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Added MigrationState read-only property to PSServiceBusMigrationConfigurationAttributes which will help to know the Migration state.

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Perbaiki penambahan sertifikat untuk Vms Linux.
* Memperbaiki 'Add-AzureRmServiceFabricClusterCertificate'
    - Menggunakan thumbprint yang benar dari sertifikat baru (Azure/service-fabric-issues#932).
    - Display exception correctly (Azure/service-fabric-issues#1054).
* Perbaiki 'Update-AzureRmServiceFabricDurability' untuk memperbarui konfigurasi kluster sebelum memulai operasi Vmss CreateOrUpdate.

## <a name="6110---october-2018"></a>6.11.0 - Oktober 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbaiki masalah terkait Get-AzureRmSubscription di CloudShell
* Memperbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azurermbackup"></a>AzureRM.Backup
* Cmdlet Azure Backup yang sudah tidak berlaku.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Ukuran baru yang ditambahkan pada daftar ukuran VM yang diizinkan ketika jaringan yang dipercepat akan diaktifkan ketika menggunakan kumpulan param sederhana untuk 'New-AzureRmVm'
* Penambahan selesai argumen ResourceName ke semua cmdlet.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Menambahkan dukungan untuk Aturan Jaringan Virtual
    - Get-AzureRmDataLakeStoreVirtualNetworkRule: Mendapatkan atau Mencantumkan aturan jaringan virtual Azure Data Lake Store.
    - Add-AzureRmDataLakeStoreVirtualNetworkRule: Menambahkan aturan jaringan virtual ke akun Data Lake Store yang ditentukan.
    - Set-AzureRmDataLakeStoreVirtualNetworkRule: Mengubah aturan jaringan virtual tertentu di akun Data Lake Store yang ditentukan.
    - Remove-AzureRmDataLakeStoreVirtualNetworkRule: Menghapus aturan jaringan virtual Azure Data Lake Store.

#### <a name="azurermnetwork"></a>AzureRM.Network
* Perbarui cmdlet Test-AzureRmNetworkWatcherConnectivity, berikan nilai protokol ke backend.
* Penambahan selesai argumen ResourceName ke semua cmdlet.

#### <a name="azurermresources"></a>AzureRM.Resources
* Fix isssue where Get-AzureRMRoleDefinition throws an unintelligible exception (when the default profile has no subscription in it and no scope is specified) by adding a meaningful exception in the scenario. Juga setel param default ke 'RoleDefinitionNameParameterSet'.

## <a name="6100---october-2018"></a>6.10.0 - Oktober 2018
#### <a name="azurestorage"></a>Azure. Storage
* Perbaiki Salin Blob/File tidak akan menyalin metadata ketika tujuan memiliki masalah metadata
    - Start-AzureStorageBlobCopy
    - Start-AzureStorageFileCopy

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Dukungan Get-AzureRmCognitiveServicesAccountSkus tanpa akun yang sudah ada.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Perbaiki Get-AzureRmVM -ResourceGroupName `<rg>` untuk mengembalikan lebih dari 50 hasil jika diperlukan
* Menambahkan contoh 'SimpleParameterSet' untuk New-AzureRmVmss cmdlet.
* Memperbaiki kesalahan ketik dalam pesan kemajuan Enkripsi Disk Azure

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui versi .Net SDK ADF ke 2.3.0.

#### <a name="azurermnetwork"></a>AzureRM.Network
* Fungsionalitas NetworkProfile yang ditambahkan. cmdlet baru ditambahkan
    - Get-AzureRMNetworkProfile
    - New-AzureRMNetworkProfile
    - Remove-AzureRMNetworkProfile
    - Set-AzureRMNetworkProfile
    - New-AzureRMContainerNicConfig
    - New-AzureRmContainerNicConfigIpConfig
* Tautan asosiasi layanan yang ditambahkan pada Model Subnet
* Ditambahkan cmdlet Baru-AzureRmVirtualNetworkTap, Get-AzureRmVirtualNetworkTap, Set-AzureRmRmVirtualNetworkTap, Remove-AzureRmVirtualNetworkTap
* Ditambahkan cmdlet Set-AzureRmNEtworkInterfaceTapConfig, Get-AzureRmNEtworkInterfaceTapConfig, Remove-AzureRmNEtworkInterfaceTapConfig

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Perbolehkan string apa pun sebagai parameter Ukuran ke depan. Tambahkan P5 di popup PSA argumentmentCompleter

#### <a name="azurermresources"></a>AzureRM.Resources
* Menambahkan parameter -Mode hilang ke Set-AzureRmPolicyDefinition
* Memperbaiki Get-AzureRmProviderOperation commandlet untuk operasi dengan Origin yang berisi Pengguna

#### <a name="azurermsql"></a>AzureRM.Sql
* Memperbaiki masalah ketika beberapa cmdlet cadangan tidak mengenali langganan Azure saat ini

#### <a name="azurermstorage"></a>AzureRM. Storage
* Dukungan mendapatkan Storage sumber daya penggunaan lokasi tertentu, dan menambahkan pesan peringatan agar penggunaan sumber daya global Storage sudah tidak t fungsi.
    - Get-AzureRmStorageUsage

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Perintah Cmdlet Get-AzureRMWebAppContainerContinuousDeploymentUrl - Mendapatkan URL Container Continuous Deployment Webhook
* Cmdlet Baru New-AzureRMWebAppContainerPSSession dan Enter-WebAppContainerPSSession - Memulai sesi jarak jauh PowerShell ke aplikasi wadah windows

## <a name="690---september-2018"></a>6.9.0 - September 2018
#### <a name="general"></a>Umum
* AzureRM.SignalR ditambahkan ke modul rollup AzureRM

#### <a name="azurermprofile"></a>AzureRM.Profile
* Perubahan minor untuk kode umum penyimpanan
* File bantuan yang diperbarui untuk menyertakan tipe parameter penuh.
* Changed -ServicePrincipal to non-mandatory in the ServicePrincipalCertificateWithSubscriptionId parameter set

#### <a name="azurestorage"></a>Azure. Storage
* Dukungan membuat Storage Konteks Dengan OAuth.
    - New-AzureStorageContext

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Ditambahkan Standard_Microsoft dalam sku harga Cdn.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memindahkan dependensi pada Keyvault Storage pada dependensi umum
* Tambahkan dukungan untuk ukuran mesin virutal lainnya ke cmdlet AEM
* Menambahkan parameter PublicIPPrefix ke New-AzureRmVmssIpConfig
* Menambahkan parameter ResourceId Invoke-AzureRmVMRunCommand cmdelt
* Tambahkan Invoke-AzureRmVmssVMRunCommand cmdlet

#### <a name="azurermdns"></a>AzureRM.Dns
* Menambahkan dukungan untuk catatan alias selama pembuatan catatan dns

#### <a name="azurerminsights"></a>AzureRM. Insights
* Memperbaiki masalah #6833 dan #7102 (Area Pengaturan diagnostik)
    - Masalah dengan nama default, misalnya 'layanan', selama pembuatan dan pencatatan/pencatatan pengaturan diagnostik
    - Masalah saat membuat pengaturan diagnostik dengan kategori
* Menambahkan pesan penghentian untuk parameter tinggi waktu metrik
    - Parameter timegrains masih diterima (ini adalah perubahan yang tidak memutus,) tapi diabaikan dalam backend karena hanya PT1M yang valid

#### <a name="azurermnetwork"></a>AzureRM.Network
* Perubahan pada cmdlet LoadBalancer
  - LoadBalancerInboundNatPoolConfig: parameter tambahan IdleTimeoutInMinutes, EnableFloatingIp dan EnableTcpReset
  - LoadBalancerInboundNatRuleConfig: parameter tambahan EnableTcpReset
  - LoadBalancerRuleConfig: parameter tambahan EnableTcpReset
  - LoadBalancerProbeConfig: menambahkan dukungan untuk nilai "Https" untuk Protokol parameter
* Menambahkan perintah baru untuk subresource OutboundRule LoadBalancer baru
  - Add-AzureRmLoadBalancerOutboundRuleConfig
  - Get-AzureRmLoadBalancerOutboundRuleConfig
  - New-AzureRmLoadBalancerOutboundRuleConfig
  - Set-AzureRmLoadBalancerOutboundRuleConfig
  - Remove-AzureRmLoadBalancerOutboundRuleConfig
* Menambahkan properti HostedWorkloads baru untuk PSNetworkInterface
* Menambahkan cmdlet baru untuk fitur: Azure Firewall melalui ARM
  - Ditambahkan Get-AzureRmFirewall
  - Ditambahkan Set-AzureRmFirewall
  - Ditambahkan New-AzureRmFirewall
  - Ditambahkan Remove-AzureRmFirewall
  - Ditambahkan New-AzureRmFirewallApplicationRuleCollection
  - Ditambahkan New-AzureRmFirewallApplicationRule
  - Ditambahkan New-AzureRmFirewallNatRuleCollection
  - Ditambahkan New-AzureRmFirewallNatRule
  - Ditambahkan New-AzureRmFirewallNetworkRuleCollection
  - Ditambahkan New-AzureRmFirewallNetworkRule
* Menambahkan dukungan untuk sertifikat Akar Tepercaya dan konfigurasi Skala Otomatis di Gateway Aplikasi
  - Cmdlet Baru ditambahkan:
      - Add-AzureRmApplicationGatewayTrustedRootCertificate
      - Get-AzureRmApplicationGatewayTrustedRootCertificate
      - New-AzureRmApplicationGatewayTrustedRootCertificate
      - Remove-AzureRmApplicationGatewayTrustedRootCertificate
      - Set-AzureRmApplicationGatewayTrustedRootCertificate
      - Get-AzureRmApplicationGatewayAutoscaleConfiguration
      - New-AzureRmApplicationGatewayAutoscaleConfiguration
      - Remove-AzureRmApplicationGatewayAutoscaleConfiguration
      - Set-AzureRmApplicationGatewayAutoscaleConfiguration
  - Cmdlet diperbarui dengan parameter optonal -TrustedRootCertificate
      - New-AzureRmApplicationGateway
      - Set-AzureRmApplicationGateway
      - New-AzureRmApplicationGatewayBackendHttpSetting
      - Set-AzureRmApplicationGatewayBackendHttpSetting
  - Cmdlet diperbarui dengan parameter optonal -AutoscaleConfiguration
      - New-AzureRmApplicationGateway
      - Set-AzureRmApplicationGateway
* Tambahkan cmdlet untuk titik akhir antarmuka Get-AzureInterfaceEndpoint
* Menambahkan dukungan untuk beberapa prefiks alamat dalam subnet. Cmdlet yang diperbarui:
  - New-AzureRmVirtualNetworkSubnetConfig
  - Set-AzureRmVirtualNetworkSubnetConfig
  - Add-AzureRmVirtualNetworkSubnetConfig
  - Get-AzureRmVirtualNetworkSubnetConfig
  - Add-AzureRmApplicationGatewayAuthenticationCertificate
  - Add-AzureRmApplicationGatewayFrontendIPConfig
  - New-AzureRmApplicationGatewayFrontendIPConfig
  - Set-AzureRmApplicationGatewayFrontendIPConfig
  - Add-AzureRmApplicationGatewayIPConfiguration
  - New-AzureRmApplicationGatewayIPConfiguration
  - Set-AzureRmApplicationGatewayIPConfiguration
  - Add-AzureRmNetworkInterfaceIpConfig
  - New-AzureRmNetworkInterfaceIpConfig - Set-AzureRmNetworkInterfaceIpConfig
  - New-AzureRmVirtualNetworkGatewayIpConfig
  - Add-AzureRmVirtualNetworkGatewayIpConfig
  - Set-AzureRmLoadBalancerFrontendIpConfig
  - Add-AzureRmLoadBalancerFrontendIpConfig
  - New-AzureRmLoadBalancerFrontendIpConfig
  - New-AzureRmNetworkInterface
* Menambahkan cmdlet untuk delegasi subnet.
  - New-AzureRmDelegation: Membuat delegasi baru, yang bisa ditambahkan ke subnet
  - Remove-AzureRmDelegation: Membawa subnet dan menghapus nama delegasi yang disediakan dari subnet itu
  - Add-AzureRmDelegation: Diperlukan dalam subnet dan menambahkan nama layanan yang disediakan sebagai delegasi ke subnet itu
  - Get-AzureRmDelegation
  - Get-AzureRmAvailableServiceDelegations

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Dukungan untuk disk terkelola

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Memperbarui Insights dependensi.

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbarui New-AzureRmResourceGroupDeployment dengan parameter baru RollbackAction
    - Tambahkan dukungan untuk OnErrorDeployment dengan parameter baru.
* Mendukung identitas terkelola mengenai penetapan kebijakan.
* Parameter dengan nilai default tidak lagi dikualkan saat menetapkan kebijakan dengan 'New-AzureRmPolicyAssignment'
* Menambahkan cmdlet Get-AzureRmPolicyAlias cmdlet baru untuk mengambil alias kebijakan

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Memperbaiki masalah #7161

#### <a name="azurermsignalr"></a>AzureRM.Signalr
* Memperbarui nama SKU menjadi Free_F1 dan Standard_S1
* Tambahkan bidang versi ke objek PSSignalRResource dan string koneksi ke objek PSSignalRKeys.

#### <a name="azurermstorage"></a>AzureRM. Storage
* Mendukung Kebijakan Keterbacaan di AzureRm. Storage
    - Remove-AzureRmStorageAccountNetworkRule
    - Get-AzureRmStorageContainer
    - Update-AzureRmStorageContainer
    - New-AzureRmStorageContainer
    - Remove-AzureRmStorageContainer
    - Add-AzureRmStorageContainerLegalHold
    - Remove-AzureRmStorageContainerLegalHold
    - Set-AzureRmStorageContainerImmutabilityPolicy
    - Get-AzureRmStorageContainerImmutabilityPolicy
    - Remove-AzureRmStorageContainerImmutabilityPolicy
    - Lock-AzureRmStorageContainerImmutabilityPolicy

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Menambahkan dua cmdlet baru: Get-AzureRmDeletedWebApp dan Restore-AzureRmDeletedWebApp
* New-AzureRmAppServicePlan -HyperV ditambahkan untuk membuat paket layanan aplikasi dengan wadah windows
* New-AzureRmWebApp/ New-AzureRmWebAppSlot/ Set-AzureRmWebApp/ Set-AzureRmWebAppSlot - Parameter baru (–ContainerRegistryUser string -ContainerRegistryPassword secureString -EnableContainerContinuousDeployment) ditambahkan untuk membuat dan mengelola aplikasi windows container

## <a name="681---august-2018"></a>6.8.1 - Agustus 2018
#### <a name="general"></a>Umum
* Memperbaiki masalah grup sumber daya default yang tidak diatur.
* Pembaruan himpunan runtime umum

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Memperbaiki masalah grup sumber daya default yang tidak diatur.
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6603
    - Import-AzureRmApiManagementApi cmdlet *-AzureRmApiManagementCertificate kini menangani Jalur relatif
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6879
    - CertificateInformation adalah properti settable yang memungkinkan cmdlet Set-AzureRmApiManagement bekerja. Diperbaiki dengan memutakhirkan ke nuget 4.0.4-preview
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6853
    - Memperbaiki filter Odata untuk Cari menurut Nama pada Produk
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6814
    - Memperbaiki filter Odata untuk Cari menurut Nama di Api
* Menambahkan dukungan untuk logger AzureMonitor


#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki masalah target yang hilang dalam output kesalahan.
* Memperbaiki masalah dengan tipe akun penyimpanan untuk VM dengan disk terkelola
* Memperbaiki masalah grup sumber daya default yang tidak diatur.
* Memperbaiki cmdlet Ekstensi AEM untuk lingkungan lain, misalnya Azure China

#### <a name="azurermnetwork"></a>AzureRM.Network
* Presentasi output cmdlet default yang diubah ke tampilan tabel

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Perbaiki kegagalan dalam Update-AzureRmPowerBIEmbeddedCapacity saat mencoba menskalakan kapasitas yang dijeda


#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah pembuatan aplikasi yang dikelola dari MarketPlace.

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Masalah tetap
    - https://github.com/Azure/azure-powershell/issues/5058
    - https://github.com/Azure/azure-powershell/issues/5055
    - https://github.com/Azure/azure-powershell/issues/6891

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Menambahkan Dukungan untuk metode perutean MultiValue
    - Parameter baru 'MaxReturn' untuk perutean MultiValue
* Menambahkan Dukungan untuk metode perutean subnet
    - Dukungan untuk rentang alamat IP (subnet) di titik akhir
* Menambahkan Dukungan untuk Header Kustom dalam profil
* Dukungan tambahan untuk rentang kode status yang diharapkan dalam profil
* Menambahkan Dukungan untuk Header Kustom di titik akhir

## <a name="680---august-2018"></a>6.8.0 - Agustus 2018
#### <a name="general"></a>Umum
* Memperbaiki masalah grup sumber daya default yang tidak diatur.

#### <a name="azurermprofile"></a>AzureRM.Profile
* Properti kedaluwarsa yang ditambahkan ke token yang dikembalikan selama Connect-AzureRmAccount

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki masalah target yang hilang dalam output kesalahan.
* Memperbaiki masalah dengan tipe akun penyimpanan untuk VM dengan disk terkelola
* Memperbaiki cmdlet Ekstensi AEM untuk lingkungan lain, misalnya Azure China

#### <a name="azurermiothub"></a>AzureRM.IotHub
* Memperbaiki contoh untuk New-AzureRmIotHubExportDevices dan New-AzureRmIotHubImportDevices

#### <a name="azurermnetwork"></a>AzureRM.Network
* Representasi model default yang diubah menjadi tampilan tabel

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Perbaiki kegagalan dalam Update-AzureRmPowerBIEmbeddedCapacity saat mencoba menskalakan kapasitas yang dijeda

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah pembuatan aplikasi yang dikelola dari MarketPlace.

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Perbaikan masalah
    - https://github.com/Azure/azure-powershell/issues/5058
    - https://github.com/Azure/azure-powershell/issues/5055
    - https://github.com/Azure/azure-powershell/issues/6891

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Dukungan untuk metode perutean MultiValue
    - Parameter baru 'MaxReturn' untuk perutean MultiValue
* Dukungan untuk metode perutean subnet
    - Dukungan untuk rentang alamat IP (subnet) di titik akhir
* Dukungan untuk Header Kustom dalam profil
* Dukungan untuk Rentang kode status yang diharapkan dalam profil
* Dukungan untuk Header Kustom di titik akhir

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Memperbaiki masalah grup sumber daya default yang diatur secara tidak benar.

## <a name="670---august-2018"></a>6.7.0 - Agustus 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Diperbarui ke versi terbaru Azure ClientRuntime.
* Menambahkan id pengguna ke nama konteks default untuk menghindari konteks yang bentrok
    - https://github.com/Azure/azure-powershell/issues/6489
* Memperbaiki masalah Clear-AzureRmContext masalah yang menyebabkan pemilihan konteks #6398
* Aktifkan domain penyewa yang akan diteruskan ke parameter '-TenantId' untuk 'Koneksi-AzureRmAccount'
    - https://github.com/Azure/azure-powershell/issues/3974
    - https://github.com/Azure/azure-powershell/issues/6709

#### <a name="azurestorage"></a>Azure. Storage
* Hapus batasan 5TB untuk kuota Berbagi File Azure
* Set-AzureStorageShareQuota

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azureanalysisservices"></a>Azure.AnalysisServices
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermapplicationinsights"></a>AzureRM.ApplicationInsights
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermautomation"></a>AzureRM.Automation
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermbackup"></a>AzureRM.Backup
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermbatch"></a>AzureRM.Batch
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermbilling"></a>AzureRM.Billing
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Diperbarui ke versi terbaru Azure ClientRuntime.
* Menambahkan parameterPolpolPolicy ke New-AzureRmVmssConfig
* Gunakan lokasi default di diskFileParameterSet dari New-AzureRmVm jika tidak ada Lokasi yang ditentukan.
* Memperbaiki deskripsi parameter di Save-AzureRmVMImage
* Memperbaiki Get-AzureRmVMDiskEncryptionStatus cmdlet untuk skenario terkait singlepass tertentu

#### <a name="azurermconsumption"></a>AzureRM.Consumption
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermcontainerregistry"></a>AzureRM.ContainerRegistry
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermdatafactories"></a>AzureRM.DataFactories
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Memperbaiki penelusuran kesalahan saat DebugPreference diatur dari baris perintah powershell
* Contoh pembaruan untuk Set-AzureRmDataLakeStoreItemAcl
* Diperbarui ke versi terbaru Azure ClientRuntime.
* Contoh pembaruan untuk Set-AzureRmDataLakeStoreItemAclEntry

#### <a name="azurermdevtestlabs"></a>AzureRM.DevTestLabs
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermdns"></a>AzureRM.Dns
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermhdinsight"></a>AzureRM.HDInsight
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurerminsights"></a>AzureRM. Insights
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermiothub"></a>AzureRM.IotHub
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermlogicapp"></a>AzureRM.LogicApp
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermmachinelearning"></a>AzureRM.MachineLearning
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermmachinelearningcompute"></a>AzureRM.MachineLearningCompute
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermmarketplaceordering"></a>AzureRM.MarketplaceOrdering
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermmedia"></a>AzureRM.Media
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermnetwork"></a>AzureRM.Network
* Contoh yang ditambahkan untuk Set-AzureRmLocalNetworkGateway
* Menambahkan contoh dan deskripsi untuk Add-AzureRmVirtualNetworkGatewayIpConfig, Get-AzureRmVirtualNetworkGatewayConnectionSharedKey dan New-AzureRmVirtualNetworkGatewayConnection
* Contoh yang ditambahkan untuk Remove-AzureRmVirtualNetworkGatewayIpConfig dan Reset-AzureRmVirtualNetworkGateway
* Contoh yang ditambahkan untuk Reset-AzureRmVirtualNetworkGatewayConnectionSharedKey
* Contoh yang ditambahkan untuk Set-AzureRmVirtualNetworkGatewayConnectionSharedKey
* Contoh yang ditambahkan untuk Set-AzureRmVirtualNetworkGatewayConnection
* Cmdlet yang dibuat ulang untuk ApplicationSecurityGroup, RouteTable, dan Usage menggunakan generator kode terbaru
* Pesan kesalahan menjelaskan Get-AzureRmVirtualNetworkSubnetConfig ketika berusaha mendapatkan subnet yang tidak keluar

#### <a name="azurermnotificationhubs"></a>AzureRM.NotificationHubs
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermpolicyinsights"></a>AzureRM.PolicyInsights
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermrecoveryservices"></a>AzureRM.RecoveryServices
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Filter kebijakan yang ditambahkan Get-AzureRmRecoveryServicesBackItem cmdlet. Perintah mengembalikan daftar item cadangan yang diproteksi oleh id kebijakan yang diberikan.
* Memperbarui Microsoft.Azure.Management.RecoveryServices.Backup ke versi 3.0.0-preview.
* Diperbarui ke versi terbaru Azure ClientRuntime.
* Menambahkan parameter TargetResourceGroupName ke Restore-AzureRmRecoveryServicesBackupItem. Grup sumber daya tempat disk terkelola dipulihkan. Berlaku untuk pencadangan VM dengan disk terkelola.

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermrelay"></a>AzureRM.Relay
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermresources"></a>AzureRM.Resources
* Penyebaran templat dukungan di lingkup langganan. Tambahkan Cmdlet baru:
    - New-AzureRmDeployment
    - Get-AzureRmDeployment
    - Test-AzureRmDeployment
    - Remove-AzureRmDeployment
    - Stop-AzureRmDeployment
    - Save-AzureRmDeploymentTemplate
    - Get-AzureRmDeploymentOperation
* Memperbaiki masalah ketika kesalahan terjadi saat meneruskan konteks ke Set-AzureRmResource
    - https://github.com/Azure/azure-powershell/issues/5705
* Memperbaiki contoh di New-AzureRmResourceGroupDeployment
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermscheduler"></a>AzureRM.Scheduler
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermsql"></a>AzureRM.Sql
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermstorage"></a>AzureRM. Storage
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermstreamanalytics"></a>AzureRM.StreamAnalytics
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermtags"></a>AzureRM.Tags
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermusageaggregates"></a>AzureRM.UsageAggregates
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Diperbarui ke versi terbaru Azure ClientRuntime.

## <a name="660---july-2018"></a>6.6.0 - Juli 2018
#### <a name="general"></a>Umum
* Memperbarui semua file bantuan agar menyertakan tipe parameter penuh dan tipe input/output yang benar.

#### <a name="azurermprofile"></a>AzureRM.Profile
* Updated Common.Strategy library to be able to validate that the current config for a resource is compatible with the target resource.
* Menambahkan tipe ps1xml ke Common. Storage

#### <a name="azurestorage"></a>Azure. Storage
* Dukungan tambahan untuk mendapatkan Storage Konteks dari DefaultProfile
* Menambahkan Ps1XmlAttribute ke properti tipe output cmdlet.

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6370
    - Memperbaiki bug dalam Automaotomatis untuk menerjemahkan PsApiManagementApi ke ApiContract
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6515
    - Perbaikan bug dalam File.Simpan agar tidak kelebihan beban dengan Tipe Pengodean
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6560
    - Dimutakhirkan ke versi 4.0.3 Nuget yang memperbaiki pengecualian pola di apiId

#### <a name="azurermcompute"></a>AzureRM.Compute
* Perbaiki masalah dengan membuat vm menggunakan DiskFileParameterSet New-AzureRmVm gagal karena penggantian nama tipe akun penyimpanan PremiumLRS.
* Cmdlet Fix Invoke-AzureRmVMRunCommand
* Perbarui Get-AzureRmAvailabilitySet mengaktifkan daftar semua kumpulan ketersediaan dalam langganan.  (Parameter ResouceGroupName kini opsional.)
* Perbarui SimpleParameterSet dari 'New-AzureRmVm' untuk mengaktifkan Jaringan yang Dipercepat pada vm yang memenuhi syarat.
* Perbarui New-AzureRmVmss parameter sederhana yang diatur ke gagal membuat vmss ketika pengguna LB yang ditentukan sudah ada.
* Contoh pembaruan untuk New-AzureRmDisk
* Tambahkan contoh untuk 'New-AzureRmVM'
* Deskripsi pembaruan untuk Set-AzureRmVMOSDisk
* Perbarui Contoh 1 untuk Set-AzureRmVMBginfoExtension memperbaiki ejaan dan prefiks.

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui versi .Net SDK ADF ke 1.1.0.
* Mendukung berbagi runtime integrasi yang dihosting sendiri di seluruh faktor data.
     - Tambahkan parameter baru -SharedIntegrationRuntimeResourceId ke Set-AzureRmDataFactoryV2IntegrationRuntime cmdlet.
     - Tambahkan parameter opsional baru -LinkedDataFactoryName Remove-AzureRmDataFactoryV2IntegrationRuntime cmdlet.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Memperbarui versi DataPlane SDK (Microsoft.Azure.DataLake.Store) ke 1.1.9

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Pemipaan yang diperbarui untuk InputObject dan ResourceId dalam cmdlet hapus

#### <a name="azurerminsights"></a>AzureRM. Insights
* Memperbaiki pemformatan OutputType dalam file bantuan
* Menggunakan Microsoft.Azure.Management.Monitor SDK 0.19.1-preview

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbaiki masalah pemipaan Set-AzureRmKeyVaultAccessPolicy

#### <a name="azurermnetwork"></a>AzureRM.Network
* Contoh yang ditambahkan untuk cmdlet LoadBalancerInboundNatPoolConfig.

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbaiki masalah saat menyediakan nama tag dan nilai untuk 'Get-AzureRmResource'
    - https://github.com/Azure/azure-powershell/issues/6765
* Memperbaiki skenario pemipaan dengan 'Set-AzureRmResource'

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Pemipaan yang diperbarui untuk InputObject dan ResourceId dalam cmdlet hapus
* memperbaiki beberapa masalah
    - https://github.com/Azure/azure-powershell/issues/3780
    - https://github.com/Azure/azure-powershell/issues/4340

#### <a name="azurermsql"></a>AzureRM.Sql
* Menambahkan dukungan Server Advanced Threat Protection dengan cmdlet berikut:
    - Enable-AzureRmSqlServerAdvancedThreatProtection; Disable-AzureRmSqlServerAdvancedThreatProtection; Get-AzureRmSqlServerAdvancedThreatProtectionPolicy
* Menambahkan dukungan Penilaian Kerentanan dengan cmdlet berikut:
    - Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings; Get-AzureRmSqlDatabaseVulnerabilityAssessmentSettings; Clear-AzureRmSqlDatabaseVulnerabilityAssessmentSettings
    - Set-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline; Get-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline; Clear-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline
    - Convert-AzureRmSqlDatabaseVulnerabilityAssessmentScan; Get-AzureRmSqlDatabaseVulnerabilityAssessmentScanRecord; Start-AzureRmSqlDatabaseVulnerabilityAssessmentScan
* Contoh tetap dalam Remove-AzureRmSqlServerFirewallRule
* Memperbaiki penanganan waktu tanggal secara tidak benar untuk budaya dasar non-AS Get-AzureSqlSyncGroupLog

#### <a name="azurermstorage"></a>AzureRM. Storage
* Menambahkan Ps1XmlAttribute ke properti tipe output cmdlet
* Memperlihatkan output cmdlet StorageAccount dalam tampilan tabel
    - Get-AzureRmStorageAccount
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount

#### <a name="azurermtags"></a>AzureRM.Tags
* Menghapus pernyataan yang salah dari bantuan cmdlet Tag
    - https://github.com/Azure/azure-powershell/issues/3878

## <a name="650---july-2018"></a>6.5.0 - Juli 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbarui bantuan untuk 'Get-AzureRmContextAutosaveSetting'

#### <a name="azurestorage"></a>Azure. Storage
* Dukungan Upload Blob atau File dengan token Sas tulis saja
* Set-AzureStorageBlobContent
* Set-AzureStorageFileContent

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Tambahkan properti yang diperlukan ResourceGroupName ke AS.

#### <a name="azurermautomation"></a>AzureRM.Automation
* Perbarui bantuan dan tambahkan contoh untuk 'New-AzureRMAutomationSchedule'

#### <a name="azurermcompute"></a>AzureRM.Compute
* Tambahkan -Parameter tag ke Update/New-AzureRmAvailabilitySet
* Tambahkan contoh untuk 'Add-AzureRmVmssExtension'
* Tambahkan contoh untuk 'Remove-AzureRmVmssExtension'
* Bantuan pembaruan untuk 'Set-AzureRmVMAccessExtension'
* Update SimpleParameterSet for New-AzureRmVmss to set SinglePlacementGroup to false by default and add switch parameter 'SinglePlacementGroup' that enables the user to create the VMSS in a single placement group.

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Menambahkan properti bacaonly 'PendingReplicationOperationsCount' ke kelas PSEventHubDRConfigurationAttributes, yang memberikan jumlah operasi replikasi tertunda saat replikasi sedang berlangsung

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbarui pesan kesalahan untuk Set-AzureRmKeyVaultAccessPolicy

#### <a name="azurermlogicapp"></a>AzureRM.LogicApp
* Memperbaiki kesalahan "kumpulan parameter tidak dapat diatasi" dalam New-AzureRmLogicApp

#### <a name="azurermnetwork"></a>AzureRM.Network
* Aktifkan peering di seluruh Jaringan Virtual di beberapa Penyewa untuk Set/Add-AzureRmVirtualNetworkPeering
* Diperbarui di bawah cmdlet untuk Application Gateway
    - New-AzureRmApplicationGateway : Bendera EnableFIPS ditambahkan dan dukungan Zona
    - New-AzureRmApplicationGatewaySku : Menambahkan sku baru Standard_v2 dan WAF_v2
    - Set-AzureRmApplicationGatewaySku : Menambahkan sku baru Standard_v2 dan WAF_v2
* Cmdlet RouteTable regenerasi dengan versi generator terbaru

#### <a name="azurermrelay"></a>AzureRM.Relay
* Memperbaiki masalah nama parameter dalam file yang diperbarui

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbarui cmdlet Roleassignment dan roledefinition:
    - Remove extra roledefinition calls done as part of paging.
* Cmdlet Fix Get-AzureRmRoleAssignment
    - Fix -ExpandPrincipalGroups fungsionalitas parameter perintah
* Memperbaiki masalah terkait 'Get-AzureRmResource' yang parameter '-ResourceType' peka huruf besar kecil

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan parameter teratas dan lewati ke cmdlet daftar
* Ditambahkan Standar Premium cmdlet migrasi NameSpace:
    - Start-AzureRmServiceBusMigration
    - Get-AzureRmServiceBusMigration
    - Complete-AzureRmServiceBusMigration
    - Stop-AzureRmServiceBusMigration
    - Remove-AzureRmServiceBusMigration
* Menambahkan properti readonly 'PendingReplicationOperationsCount' ke KELAS PSServiceBusDRConfigurationAttributes, yang memberikan jumlah operasi replikasi yang tertunda saat replikasi sedang berlangsung

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Contoh pembaruan untuk 'New-AzureRmServiceFabricCluster'

#### <a name="azurermsql"></a>AzureRM.Sql
* Menambahkan Cmdlet baru untuk Manajemen.Sql untuk memungkinkan pelanggan menambahkan Sertifikat TDE ke contoh Sql Server atau Instans Terkelola
    - Add-AzureRmSqlServerTransparentDataEncryptionCertificate
    - Add-AzureRmSqlManagedInstanceTransparentDataEncryptionCertificate

#### <a name="azurermwebsites"></a>AzureRM.Websites
* `Set-AzureRmWebApp -AssignIdentity` dan  `Set-AzureRmWebAppSlot -AssignIdentity` saat diatur ke false sekarang akan menghapus properti Identitas dari objek situs. Menghapus tag pratinjau juga.
* `Get-AzureRmWebAppMetrics`, `Get-AzureRmAppServicePlanMetrics` contoh yang diperbarui
* `Set-AzureRmWebApp -PhpVersion` mendukung sebagai versi php yang valid

## <a name="640---july-2018"></a>6.4.0 - Juli 2018
#### <a name="general"></a>Umum
* Memperbaiki pemformatan OutputType dalam file bantuan untuk sebagian besar modul

#### <a name="azurermprofile"></a>AzureRM.Profile
* Atribut Ps1Xml ditambahkan ke tipe output dasar

#### <a name="azurermcompute"></a>AzureRM.Compute
* Fitur Tag IP untuk VMSS
    - Cmdlet 'New-AzureRmVmssIpTagConfig' ditambahkan
    - Parameter IpTag ditambahkan ke New-AzureRmVmssIpConfig
* Fitur Auto OS Rollback untuk VMSS
    - Parameter DisableAutoRollback ditambahkan ke New-AzureRmVmssConfig dan Update-AzureRmVmss
* Fitur Os Upgrade History untuk Vms
    - Parameter sakelar OSUpgradeHistory ditambahkan ke Get-AzureRmVmss

#### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Tambahkan dukungan untuk ACL Katalog melalui perintah berikut:
    - Get-AzureRmDataLakeAnalyticsCatalogItemAclEntry
    - Set-AzureRmDataLakeAnalyticsCatalogItemAclEntry
    - Remove-AzureRmDataLakeAnalyticsCatalogItemAclEntry

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Tambahkan dukungan pembatalan dan pelacakan kemajuan untuk Set-AzureRmDataLakeStoreItemAclEntry, Remove-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAcl
* Tambahkan dukungan pembatalan untuk Export-AzureRmDataLakeStoreChildItemProperties
* Memperbaiki cara membilas pesan debug untuk cmdlet yang melakukan operasi rekursif
* Memperbaiki lokasi uji cmdlet DataLake

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Menambahkan parameter Opsional MaxCount ke cmdlet List Operations Get-AzureRmEventHub dan Get-AzureRmEventHubConsumerGroup
* Memperbaiki masalah dalam cmdlet New-AzureRmEventHub cmdlet yang setidaknya memerlukan satu parameter saat membuat New EventHub. Kumpulan Parameter Default yang disediakan.
* Added optional Parameter -KeyValue to New-AzureRmEventHubKey cmdlet, which enables user to provide KeyValue.

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbaiki masalah ketika semua sumber daya dikembalikan oleh Get-AzureRmKeyVault -Tag

#### <a name="azurermnetwork"></a>AzureRM.Network
* Mengekspos Sku baru untuk Zone-Redundant VirtualNetworkGateway
* Perintah baru yang ditambahkan untuk fitur: API Mitra ExpressRoute melalui ARM
    - Ditambahkan Get-AzureRmExpressRouteCrossConnection
    - Ditambahkan Set-AzureRmExpressRouteCrossConnection
    - Ditambahkan Add-AzureRmExpressRouteCrossConnectionPeering
    - Ditambahkan Get-AzureRmExpressRouteCrossConnectionPeering
    - Ditambahkan Remove-AzureRmExpressRouteCrossConnectionPeering
    - Ditambahkan Get-AzureRMExpressRouteCrossConnectionArpTable
    - Ditambahkan Get-AzureRMExpressRouteCrossConnectionRouteTable
    - Ditambahkan Get-AzureRMExpressRouteCrossConnectionRouteTableSummary

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Ditambahkan Get-AzureRmRecoveryServicesBackupStatus cmdlet. Cmdlet ini akan menggunakan ID VM dan memeriksa apakah VM dilindungi oleh beberapa vault dalam langganan. Jika terdapat vault seperti itu, cmdlet akan menampilkan detail vault.

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbarui Get-AzureRmPolicyAssignment cmdlet:
    - Tambahkan dukungan untuk pencatatan nilai -Lingkup di tingkat grup manajemen
    - Tambahkan dukungan untuk mengambil penetapan individual dengan nilai -Lingkup di tingkat grup manajemen
    - Tambahkan -Efektif dan -Semua sakelar ke parameter kontrol
* Cmdlet Update Get/New/Remove/Set-AzureRmPolicyDefinition
    - Menambahkan parameter -ManagementGroupName untuk menerapkan operasi ke grup manajemen tertentu
    - Menambahkan parameter -SubscriptionId untuk menerapkan operasi ke langganan tertentu
* Cmdlet Update Get/New/Remove/Set-AzureRmPolicySetDefinition
    - Menambahkan parameter -ManagementGroupName untuk menerapkan operasi ke grup manajemen tertentu
    - Menambahkan parameter -SubscriptionId untuk menerapkan operasi ke langganan tertentu
* Tambahkan dukungan referensi rahasia KeyVault dalam parameter saat menggunakan 'TemplateParameterObject' di 'New-AzureRmResourceGroupDeployment'
* Memperbaiki masalah parameter '-EndDate' yang diabaikan untuk 'New-AzureRmADAppCredential'
    - https://github.com/Azure/azure-powershell/issues/6505
* Memperbaiki masalah ketika 'Add-AzureRmADGroupMember' menggunakan URL yang salah untuk membuat permintaan
    - https://github.com/Azure/azure-powershell/issues/6485

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Added optional Parameter -KeyValue to New-AzureRmServiceBusKey cmdlet, which enables user to provide KeyValue.

#### <a name="azurermsql"></a>AzureRM.Sql
* Poin pemulihan User-Defined untuk SQLDW dalam New-AzureRmSqlDatabaseRestorePoint bantuan
* Dokumentasi parameter -ComputeGeneration yang diperbarui dalam beberapa cmdlet

## <a name="630---june-2018"></a>6.3.0 - Juni 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Pesan kesalahan yang diperbarui untuk Enable-AzureRmContextAutoSave
* Membuat konteks untuk setiap langganan ketika menjalankan 'Koneksi-AzureRmAccount' tanpa konteks sebelumnya

#### <a name="azurestorage"></a>Azure. Storage
* Menambahkan informasi tambahan tentang parameter -Permissions dalam file bantuan.

#### <a name="azurermcompute"></a>AzureRM.Compute
* 'Get-AzureRmVmDiskEncryptionStatus' memperbaiki masalah yang diamati untuk VM tanpa disk data
* Perbarui versi pustaka klien Hitung untuk memperbaiki cmdlet berikut
    - Grant-AzureRmDiskAccess
    - Grant-AzureRmSnapshotAccess
    - Save-AzureRmVMImage
* Perbaikan cmdlets berikut agar memperlihatkan 'ID operasi' dan 'status operasi' dengan benar:
    - Start-AzureRmVM
    - Stop-AzureRmVM
    - Restart-AzureRmVM
    - Set-AzureRmVM
    - Remove-AzuerRmVM
    - Set-AzureRmVmss
    - Start-AzureRmVmssRollingOSUpgrade
    - Stop-AzureRmVmssRollingUpgrade
    - Start-AzureRmVmss
    - Restart-AzureRmVmss
    - Stop-AzureRmVmss
    - Remove-AzureRmVmss
    - ConvertTo-AzureRmVMManagedDisk
    - Revoke-AzureRmSnapshotAccess
    - Remove-AzureRmSnapshot
    - Revoke-AzureRmDiskAccess
    - Remove-AzureRmDisk
    - Remove-AzureRmContainerService
    - Remove-AzureRmAvailabilitySet

#### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Hapus kondisi validasi ValidateNotNullOrEmpty untuk SubjectBeginsWith/SubjectEndsWith dalam cmdlet Update-AzureRmEventGridSubscription untuk memungkinkan pengubahan parameter ini menjadi string kosong jika diperlukan.

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbaiki masalah ketika tidak ada Tag yang dikembalikan Get-AzureRmKeyVault -Tag dijalankan

#### <a name="azurermpolicyinsights"></a>AzureRM.PolicyInsights
* Cmdlet kebijakan Insights rilis publik
    - Menggunakan API versi 2018-04-04
    - Tambahkan PolicyDefinitionReferenceId ke hasil Get-AzureRmPolicyStateSummary

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Menambahkan parameter -Vault ke cmdlet RecoveryServices.Backup. Ketika lolos, hal ini akan menimpa Set-AzureRmRecoveryServicesContext cmdlet.

#### <a name="azurermsql"></a>AzureRM.Sql
* Contoh yang diperbarui di file bantuan untuk Get-AzureRmSqlDatabaseExpanded

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Memperbarui file bantuan untuk Add-AzureRmTrafficManagerEndpointConfig

#### <a name="azurermwebsites"></a>AzureRM.Websites
* 'Set-AzureRmWebApp' diperbarui untuk tidak menimpa AppSettings saat menggunakan -AssignIdentity
* 'New-AzureRmWebAppSlot' diperbarui untuk mengikuti AppServicePlan sebagai parameter opsional

## <a name="621---june-2018"></a>6.2.1 - Juni 2018
### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Model PSWorkspace yang diperbarui untuk memungkinkan Jaringan menggunakan tipe sebagai parameter

## <a name="620---june-2018"></a>6.2.0 - Juni 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbaiki masalah versi 10.0.3 Newtonsoft.Json tidak dimuat pada impor modul

#### <a name="azurermcompute"></a>AzureRM.Compute
* Fitur VMSS VM Update
    - Menambahkan cmdlet 'Update-AzureRmVmssVM' dan 'New-AzureRmVMDataDisk'
    - Tambahkan parameter VirtualMachineScaleSetVM ke cmdlet 'Add-AzureRmVMDataDisk' untuk mendukung penambahan disk data ke VM Vmss.

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui versi ADF .Net SDK ke 0.8.0-preview yang berisi perubahan berikut:
    - Ditambahkan Konfigurasi operasi penyimpanan pabrik
    - Pembaruan QuickBooks LinkedService untuk mengekspos properti consumerKey dan consumerSecret
    - Diperbarui Beberapa tipe model dari SecretBase menjadi Object
    - Pemicu Kejadian Blob yang ditambahkan

### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbarui dokumentasi dengan output contoh

### <a name="azurermnetwork"></a>AzureRM.Network
* Mengaktifkan parameter Analitik Lalu Lintas pada cmdlet Pengawas Jaringan

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbaiki masalah terkait properti 'Properti' dari objek 'PSResource' yang dikembalikan dari 'Get-AzureRmResource'

#### <a name="azurermscheduler"></a>AzureRM.Scheduler
* Memperbaiki masalah terkait pembaruan ServiceBusQueueJob tidak mengatur nilai Auth baru

### <a name="azurermsql"></a>AzureRM.Sql
* Memperbarui cmdlet berikut dengan parameter LicenseType opsional
    - New-AzureRmSqlDatabase; Set-AzureRmSqlDatabase
    - New-AzureRmSqlElasticPool; Set-AzureRmSqlElasticPool
    - New-AzureRmSqlDatabaseCopy
    - New-AzureRmSqlDatabaseSecondary
    - Restore-AzureRmSqlDatabase

#### <a name="azurermwebsites"></a>AzureRM.Websites
* 'New-AzureRMWebApp' diperbarui untuk menggunakan algoritma umum dari pustaka Strategi.

## <a name="610---may-2018"></a>6.1.0 - Mei 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbaiki masalah ketika menjalankan 'Clear-AzureRmContext' akan mempertahankan konteks kosong dengan nama konteks default sebelumnya, yang mencegah pengguna membuat konteks baru dengan nama lama

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Mengaktifkan operasi alkuit/diseserta gateway pada AS.

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Menambahkan dukungan untuk ApiVersions, ApiReleases dan ApiRevisions
* Penambahan dukungan untuk ServiceFabric Backend
* Dukungan tambahan untuk Application Insights Logger
* Dukungan yang ditambahkan untuk mengenali sku 'Dasar' sebagai sku layanan Manajemen Api yang valid
* Menambahkan dukungan untuk menginstal Sertifikat yang dikeluarkan oleh CA privat sebagai Akar atau CA
* Menambahkan dukungan untuk menerima sertifikat SSL kustom melalui KeyVault dan Beberapa nama host proksi
* Dukungan tambahan untuk identitas MSI
* Dukungan tambahan untuk menerima Kebijakan melalui URL NOTE: Cmdlets berikut akan tidak berlaku lagi dalam rilis mendatang
   - Import-AzureRmApiManagementHostnameCertificate
   - New-AzureRmApiManagementHostnameConfiguration
   - Set-AzureRmApiManagementHostnames
   - Update-AzureRmApiManagementDeployment

#### <a name="azurermbatch"></a>AzureRM.Batch
* Perintah cmdlet baru Get-AzureBatchPoolNodeCounts
* Perintah cmdlet baru Start-AzureBatchComputeNodeServiceLogUpload

#### <a name="azurermconsumption"></a>AzureRM.Consumption
* Menambahkan parameter baru Perluas, Grup Sumber Daya, InstanceName, InstanceId, Tag, dan Atas di atas cmdlet Get-AzureRmConsumptionUsageDetail

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Contoh perbaikan untuk Export-AzureRmDataLakeStoreChildItemProperties
* Memperbaiki pengecualian parameter null untuk kasus Reurse dalam Set-AzureRmDataLakeStoreItemAclEntry
* Memperbaiki file bantuan untuk Set-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAcl, Remove-AzureRmDataLakeStoreItemAclEntry

#### <a name="azurermnetwork"></a>AzureRM.Network
* Membenturkan versi SDK Jaringan dari 18.0.0-preview ke 19.0.0-preview
* Cmdlet yang ditambahkan untuk membuat konfigurasi protokol
    - New-AzureRmNetworkWatcherProtocolConfiguration
* Cmdlet ditambahkan untuk menambahkan koneksi sirkuit baru ke sirkuit rute ekspres yang ada.
    - Add-AzureRmExpressRouteCircuitConnectionConfig
* Cmdlet tambahan untuk menghapus koneksi sirkuit dari sirkuit rute ekspres yang ada.
    - Remove-AzureRmExpressRouteCircuitConnectionConfig
* Cmdlet yang ditambahkan untuk mengambil koneksi sirkuit
    - Get-AzureRmExpressRouteCircuitConnectionConfig

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Memperbaiki penggunaan autentikasi server dengan sertifikat yang dihasilkan (Masalah #5998)

#### <a name="azurermsql"></a>AzureRM.Sql
* Update Auditing cmdlets to allow removing AuditActions or AuditActionGroups
* Memperbaiki masalah Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy ketika mengatur kebijakan penyimpanan fleksibel baru yang perintahnya akan gagal dengan 'Konfigurasi kebijakan penyimpanan jangka panjang dengan penyimpanan dan kebijakan layanan pemulihan Azure tidak lagi didukung. Silakan kirim permintaan dengan kebijakan penyimpanan fleksibel yang baru.'
* Perbarui semua cmdlet terkait Pembuatan/Pembaruan Database/ElastisPool Azure Untuk menggunakan API Database baru, yang mendukung properti Sku untuk skala dan properti terkait tier.
* Cmdlet yang diperbarui termasuk:
    - New-AzureRmSqlDatabase; Set-AzureRmSqlDatabase
    - New-AzureRmSqlElasticPool; Set-AzureRmSqlElasticPool
    - New-AzureRmSqlDatabaseCopy
    - New-AzureRmSqlDatabaseSecondary
    - Restore-AzureRmSqlDatabase

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Perbarui parameter untuk 'Get-AzureRmTrafficManagerProfile' sehingga parameter -ResourceGroupName diperlukan saat menggunakan parameter -Name.
