---
title: Log Perubahan Azure PowerShell | Microsoft Docs
description: Ini adalah sejarah perubahan yang dibuat untuk Azure PowerShell dalam rilis terbaru.
ms.devlang: powershell
ms.topic: conceptual
ms.workload: ''
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 0969a235e46b2a44a197968300f6eb22e733c03e
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
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
* Perbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Memperbarui dependensi untuk masalah pemetaan jenis

#### <a name="azurermautomation"></a>AzureRM.Automation
* Cmdlet Azure Automation berbasis Swagger
* Menambahkan cmdlet Manajemen Pembaruan
* Menambahkan cmdlet Kontrol Sumber
* Menambahkan cmdlet Hapus-AzureRmAutomationHybridWorkerGroup
* Memperbaiki perintah Node Register DSC

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki masalah identitas untuk identitas SystemAssigned
* Memperbarui dependensi untuk masalah pemetaan jenis

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Memperbarui dependensi untuk masalah pemetaan jenis

#### <a name="azurermmarketplaceordering"></a>AzureRM.MarketplaceOrdering
* memperbarui deskripsi contoh untuk cmdlet marketplace

#### <a name="azurermnetwork"></a>AzureRM.Network
* Menambahkan cmdlet New-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayCustomError, Get-AzureRmApplicationGatewayCustomError, Set-AzureRmApplicationGatewayCustomError, Remove-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayHttpListenerCustomError, Get-AzureRmApplicationGatewayHttpListenerCustomError, Set-AzureRmApplicationGatewayHttpListenerCustomError, Remove-AzureRmApplicationGatewayHttpListenerCustomError
* Menambahkan ICMP kembali ke Protokol Jaringan AzureFirewall yang didukung
* Perbarui cmdlet Test-AzureRmNetworkWatcherConnectivity, tambahkan validasi pada id tujuan, alamat, dan port.
* Memperbaiki masalah penggunaan memori di peta VirtualNetwork

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Perbaiki guna mengubah kebijakan untuk berbagi file yang dilindungi.
* Zona waktu kebijakan diubah menjadi huruf besar.

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Memperbaiki contoh di New-AzureRmRecoveryServicesAsrProtectableItem
* Memperbarui dependensi untuk masalah pemetaan jenis

#### <a name="azurermrelay"></a>AzureRM.Relay
* Menambahkan Parameter opsional -KeyValue ke cmdlet New-AzureRmRelayKey, yang memungkinkan pengguna untuk menyediakan KeyValue.

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbarui dokumentasi bantuan untuk parameter terkait identitas sumber daya di `New-AzureRmPolicyAssignment` dan `Set-AzureRmPolicyAssignment`
* Menambahkan contoh untuk New-AzureRmPolicyDefinition yang menggunakan -Metadata
* Perbaiki untuk memungkinkan pelestarian kasus di kunci Tag pada NetStandard: #7678 #7703

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Menambahkan pesan penghentian untuk perubahan yang berisiko selanjutnya

#### <a name="azurermsql"></a>AzureRM.Sql
* Menambahkan cmdlet baru untuk operasi CRUD pada Instans Terkeola Azure Sql Database dan Azure Sql Managed Database
    - Get-AzureRmSqlInstance
    - New-AzureRmSqlInstance
    - Set-AzureRmSqlInstance
    - Remove-AzureRmSqlInstance
    - Get-AzureRmSqlInstanceDatabase
    - New-AzureRmSqlInstanceDatabase
    - Restore-AzureRmSqlInstanceDatabase
    - Remove-AzureRmSqlInstanceDatabase
* Mengaktifkan manajemen Kebijakan Audit yang Diperpanjang di server atau database.
    - Parameter baru (PredicateExpression) ditambahkan untuk mengaktifkan pemfilteran log audit.
    - Cmdlet dimodifikasi untuk menggunakan klien SQL, bukan klien Warisan.
    - Set-AzureRmSqlServerAuditing.
    - Get-AzureRmSqlServerAuditing.
    - Set-AzureRmSqlDatabaseAuditing.
    - Get-AzureRmSqlDatabaseAuditing.
* Memperbaiki masalah menggunakan Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings dengan kumpulan parameter nama akun penyimpanan

## <a name="6120---november-2018"></a>6.12.0 - November 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Perbarui kode umum untuk menggunakan versi terbaru ClientRuntime
* Ganti nama param TenantId di cmdlet Connect-AzureRmAccount ke Penyewa dan tambahkan alias untuk TenantId
* Deskripsi TenantId yang diperbarui untuk Connect-AzureRmAccount
* Memperbaiki pesan kesalahan untuk login yang gagal saat menyediakan domain penyewa
    - https://github.com/Azure/azure-powershell/issues/6936
* Memperbaiki masalah dengan nama konteks yang berbenturan untuk akun tanpa langganan di penyewa
    - https://github.com/Azure/azure-powershell/issues/7453
* Memperbaiki masalah dengan titik akhir DataLake saat menggunakan MSI
    - https://github.com/Azure/azure-powershell/issues/7462
* Memperbaiki masalah di mana 'Disconnect-AzureRmAccount' akan dibuang jika tidak tersambung
    - https://github.com/Azure/azure-powershell/issues/7167

#### <a name="azurermautomation"></a>AzureRM.Automation
* Mengganti nama file cmdlet DLL menjadi Microsoft.Azure.Commands.Automation.dll

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Tambahkan operasi Get-AzureRmCognitiveServicesAccountSkus.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Tambahkan cmdlet Add-AzureRmVmssVMDataDisk dan Remove-AzureRmVmssVMDataDisk
* Get-AzureRmVMImage menunjukkan AutomaticOSUpgradeProperties
* Memperbaiki nilai opsi SetAzureRmVMChefExtension -BootstrapOptions dan -JsonAttribute tidak diatur dalam format json.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Perbarui paket DataLake ke 1.1.10.
* Tambahkan Konkurensi default ke operasi multialur.

#### <a name="azurerminsights"></a>AzureRM.Insights
* Memperbaiki masalah #7267 (Area skala otomatis)
    - Masalah terkait pembuatan aturan skala otomatis baru yang tidak mengatur parameter yang disebutkan dengan benar (akan selalu mengaturnya ke nilai default).
* Memperbaiki masalah #7513 [Insight] Set-AzureRMDiagnosticSetting memerlukan spesifikasi kategori eksplisit selama pembuatan pengaturan
    - Sekarang cmdlet tidak memerlukan indikasi eksplisit kategori untuk diaktifkan selama pembuatan, yaitu berfungsi seperti yang didokumentasikan

#### <a name="azurermnetwork"></a>AzureRM.Network
* Mengubah PeeringType menjadi parameter wajib untuk cmdlet berikut:-
    - Get-AzureRmExpressRouteCircuitRouteTable
    - Get-AzureRmExpressRouteCircuitARPTable
    - Get-AzureRmExpressRouteCircuitRouteTableSummary
    - Get-AzureRMExpressRouteCrossConnectionArpTable
    - Get-AzureRMExpressRouteCrossConnectionRouteTable
    - Get-AzureRMExpressRouteCrossConnectionRouteTableSummary

#### <a name="azurermpolicyinsights"></a>AzureRM.PolicyInsights
* Menambahkan cmdlet remediasi kebijakan

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Menambahkan dukungan untuk berbagi file azure dalam layanan pemulihan.

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbaikan untuk https://github.com/Azure/azure-powershell/issues/7402
    - Izinkan daftar sumber daya menggunakan parameter '-ResourceId' untuk 'Get-AzureRmResource'

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan properti baca-saja MigrationState ke PSServiceBusMigrationConfigurationAttributes yang akan membantu mengetahui status Migrasi.

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Perbaiki tindakan tambahkan sertifikat ke Linux Vmss.
* Memperbaiki 'Add-AzureRmServiceFabricClusterCertificate'
    - Menggunakan thumbprint yang benar dari sertifikat baru (Azure/service-fabric-issues#932).
    - Tampilkan pengecualian dengan benar (Azure/service-fabric-issues#1054).
* Perbaiki 'Update-AzureRmServiceFabricDurability' untuk memperbarui konfigurasi kluster sebelum memulai operasi Vmss CreateOrUpdate.

## <a name="6110---october-2018"></a>6.11.0 - Oktober 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbaiki masalah dengan Get-AzureRmSubscription di CloudShell
* Perbarui kode umum untuk menggunakan versi terbaru ClientRuntime

#### <a name="azurermbackup"></a>AzureRM.Backup
* Cmdlet Azure Backup yang tidak digunakan lagi.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Menambahkan ukuran baru ke daftar ukuran VM yang dimungkinkan untuk jaringan yang dipercepat yang akan diaktifkan saat menggunakan parameter sederhana yang disetel untuk 'New-AzureRmVm'
* Menambahkan pelengkap argumen ResourceName ke semua cmdlet.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Menambahkan dukungan untuk Aturan Virtual Network
    - Get-AzureRmDataLakeStoreVirtualNetworkRule: Mendapat atau Mencantumkan aturan jaringan virtual Azure Data Lake Store.
    - Add-AzureRmDataLakeStoreVirtualNetworkRule: Menambahkan aturan jaringan virtual ke akun Data Lake Store yang ditentukan.
    - Set-AzureRmDataLakeStoreVirtualNetworkRule: Memodifikasi aturan jaringan virtual yang ditentukan di akun Data Lake Store yang ditentukan.
    - Remove-AzureRmDataLakeStoreVirtualNetworkRule: Menghapus aturan jaringan virtual Azure Data Lake Store.

#### <a name="azurermnetwork"></a>AzureRM.Network
* Perbarui cmdlet Test-AzureRmNetworkWatcherConnectivity, berikan nilai protokol ke backend.
* Menambahkan pelengkap argumen ResourceName ke semua cmdlet.

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbaiki masalah ketika Get-AzureRMRoleDefinition memberikan pengecualian yang tidak dapat dipahami (ketika profil default tidak memiliki langganan di dalamnya dan tidak ada cakupan yang ditentukan) dengan menambahkan pengecualian yang berarti dalam skenario. Atur juga param default ke 'RoleDefinitionNameParameterSet'.

## <a name="6100---october-2018"></a>6.10.0 - Oktober 2018
#### <a name="azurestorage"></a>Azure.Storage
* Memperbaiki tindakan Salin Blob/File tidak akan menyalin metadata saat tujuan mengalami masalah metadata
    - Start-AzureStorageBlobCopy
    - Start-AzureStorageFileCopy

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Dukung Get-AzureRmCognitiveServicesAccountSkus tanpa akun yang ada.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki Get-AzureRmVM -ResourceGroupName `<rg>` untuk mengembalikan lebih dari 50 hasil jika diperlukan
* Tambahkan contoh 'SimpleParameterSet' ke bantuan cmdlet New-AzureRmVmss.
* Memperbaiki kesalahan ketik di pesan kemajuan Azure Disk Encryption

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui versi ADF .Net SDK ke 2.3.0.

#### <a name="azurermnetwork"></a>AzureRM.Network
* Menambahkan fungsionalitas NetworkProfile. cmdlet baru ditambahkan
    - Get-AzureRMNetworkProfile
    - New-AzureRMNetworkProfile
    - Remove-AzureRMNetworkProfile
    - Set-AzureRMNetworkProfile
    - New-AzureRMContainerNicConfig
    - New-AzureRmContainerNicConfigIpConfig
* Menambahkan tautan asosiasi layanan pada Model Subnet
* Menambahkan cmdlet New-AzureRmVirtualNetworkTap, Get-AzureRmVirtualNetworkTap, Set-AzureRmVirtualNetworkTap, Remove-AzureRmVirtualNetworkTap
* Menambahkan cmdlet Set-AzureRmNEtworkInterfaceTapConfig, Get-AzureRmNEtworkInterfaceTapConfig, Remove-AzureRmNEtworkInterfaceTapConfig

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Izinkan string apa pun sebagai parameter Ukuran selanjutnya. Menambahkan P5 di popup PSArgumentCompleter

#### <a name="azurermresources"></a>AzureRM.Resources
* Tambahkan parameter -Mode yang hilang ke Set-AzureRmPolicyDefinition
* Perbaiki bug commandlet Get-AzureRmProviderOperation untuk operasi Asal yang berisi Pengguna

#### <a name="azurermsql"></a>AzureRM.Sql
* Memperbaiki masalah ketika beberapa cmdlet cadangan tidak mengenali langganan azure saat ini

#### <a name="azurermstorage"></a>AzureRM.Storage
* Dukungan mendapatkan penggunaan sumber daya Penyimpanan dari lokasi tertentu, dan menambahkan pesan peringatan untuk mendapatkan penggunaan sumber daya Penyimpanan global yang sudah kedaluwarsa.
    - Get-AzureRmStorageUsage

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Cmdlet Baru Get-AzureRMWebAppContainerContinuousDeploymentUrl - Mendapatkan URL Webhook Penyebaran Berkelanjutan Kontainer
* Cmdlet Baru New-AzureRMWebAppContainerPSSession dan Enter-WebAppContainerPSSession - Memulai sesi jarak jauh PowerShell ke dalam aplikasi kontainer windows

## <a name="690---september-2018"></a>6.9.0 - September 2018
#### <a name="general"></a>Umum
* AzureRM.SignalR ditambahkan ke modul rollup AzureRM

#### <a name="azurermprofile"></a>AzureRM.Profile
* Perubahan kecil pada kode umum penyimpanan
* File bantuan yang diperbarui untuk menyertakan jenis parameter lengkap.
* Mengubah -ServicePrincipal menjadi tidak wajib dalam set parameter ServicePrincipalCertificateWithSubscriptionId

#### <a name="azurestorage"></a>Azure.Storage
* Dukung buat Konteks Penyimpanan dengan OAuth.
    - New-AzureStorageContext

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Menambahkan Standard_Microsoft dalam harga Cdn sku.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memindahkan dependensi pada Keyvault dan Penyimpanan ke dependensi umum
* Menambahkan dukungan untuk ukuran mesin virutal lainnya ke cmdlet AEM
* Menambahkan parameter PublicIPPrefix ke New-AzureRmVmssIpConfig
* Menambahkan parameter ResourceId ke Invoke-AzureRmVMRunCommand cmdelt
* Menambahkan cmdlet Invoke-AzureRmVmssVMRunCommand

#### <a name="azurermdns"></a>AzureRM.Dns
* Menambahkan dukungan untuk catatan alias selama pembuatan catatan dns

#### <a name="azurerminsights"></a>AzureRM.Insights
* Memperbaiki masalah #6833 dan #7102 (area Pengaturan Diagnostik)
    - Masalah terkait nama default, yaitu 'layanan', selama pembuatan dan daftar/mendapatkan pengaturan diagnostik
    - Masalah saat membuat pengaturan diagnostik dengan kategori
* Menambahkan pesan penghentian untuk parameter butir waktu metrik
    - Parameter timegrains masih diterima (ini adalah perubahan yang tidak berisiko,) tetapi diabaikan di backend karena hanya PT1M yang valid

#### <a name="azurermnetwork"></a>AzureRM.Network
* Perubahan pada cmdlet LoadBalancer
  - LoadBalancerInboundNatPoolConfig: menambahkan parameter IdleTimeoutInMinutes, EnableFloatingIp dan EnableTcpReset
  - LoadBalancerInboundNatRuleConfig: menambahkan parameter EnableTcpReset
  - LoadBalancerRuleConfig: menambahkan parameter EnableTcpReset
  - LoadBalancerProbeConfig: menambahkan dukungan nilai "Https" untuk parameter Protokol
* Menambahkan perintah baru untuk OutboundRule subsumber daya LoadBalancer baru
  - Add-AzureRmLoadBalancerOutboundRuleConfig
  - Get-AzureRmLoadBalancerOutboundRuleConfig
  - New-AzureRmLoadBalancerOutboundRuleConfig
  - Set-AzureRmLoadBalancerOutboundRuleConfig
  - Remove-AzureRmLoadBalancerOutboundRuleConfig
* Menambahkan properti HostedWorkloads baru untuk PSNetworkInterface
* Menambahkan cmdlet baru untuk fitur: Azure Firewall melalui ARM
  - Menambahkan Get-AzureRmFirewall
  - Menambahkan Set-AzureRmFirewall
  - Menambahkan New-AzureRmFirewall
  - Menambahkan Remove-AzureRmFirewall
  - Menambahkan New-AzureRmFirewallApplicationRuleCollection
  - Menambahkan New-AzureRmFirewallApplicationRule
  - Menambahkan New-AzureRmFirewallNatRuleCollection
  - Menambahkan New-AzureRmFirewallNatRule
  - Menambahkan New-AzureRmFirewallNetworkRuleCollection
  - Menambahkan New-AzureRmFirewallNetworkRule
* Menambahkan dukungan untuk sertifikat Akar Tepercaya dan konfigurasi Skala Otomatis di Application Gateway
  - Cmdlet baru menambahkan:
      - Add-AzureRmApplicationGatewayTrustedRootCertificate
      - Get-AzureRmApplicationGatewayTrustedRootCertificate
      - New-AzureRmApplicationGatewayTrustedRootCertificate
      - Remove-AzureRmApplicationGatewayTrustedRootCertificate
      - Set-AzureRmApplicationGatewayTrustedRootCertificate
      - Get-AzureRmApplicationGatewayAutoscaleConfiguration
      - New-AzureRmApplicationGatewayAutoscaleConfiguration
      - Remove-AzureRmApplicationGatewayAutoscaleConfiguration
      - Set-AzureRmApplicationGatewayAutoscaleConfiguration
  - Cmdlet diperbarui dengan parameter opsional-TrustedRootCertificate
      - New-AzureRmApplicationGateway
      - Set-AzureRmApplicationGateway
      - New-AzureRmApplicationGatewayBackendHttpSetting
      - Set-AzureRmApplicationGatewayBackendHttpSetting
  - Cmdlet diperbarui dengan parameter opsional-AutoscaleConfiguration
      - New-AzureRmApplicationGateway
      - Set-AzureRmApplicationGateway
* Menambahkan cmdlet untuk Get-AzureInterfaceEndpoint Titik Akhir Antarmuka
* Menambahkan dukungan untuk beberapa awalan alamat dalam subnet. Cmdlet yang diperbarui:
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
  - New-AzureRmNetworkInterfaceIpConfig  - Set-AzureRmNetworkInterfaceIpConfig
  - New-AzureRmVirtualNetworkGatewayIpConfig
  - Add-AzureRmVirtualNetworkGatewayIpConfig
  - Set-AzureRmLoadBalancerFrontendIpConfig
  - Add-AzureRmLoadBalancerFrontendIpConfig
  - New-AzureRmLoadBalancerFrontendIpConfig
  - New-AzureRmNetworkInterface
* Menambahkan cmdlet untuk delegasi subnet.
  - New-AzureRmDelegation: Membuat delegasi baru, yang dapat ditambahkan ke subnet
  - Remove-AzureRmDelegation: Mengambil subnet dan menghapus nama delegasi yang disediakan dari subnet tersebut
  - Add-AzureRmDelegation: Mengambil subnet dan menambahkan nama layanan yang disediakan sebagai delegasi ke subnet tersebut
  - Get-AzureRmDelegation
  - Get-AzureRmAvailableServiceDelegations

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Dukungan untuk disk Terkelola yang terkelola

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Dependensi Insight yang diperbarui.

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbarui New-AzureRmResourceGroupDeployment dengan parameter baru RollbackAction
    - Tambahkan dukungan untuk OnErrorDeployment dengan parameter baru.
* Mendukung identitas terkelola pada penetapan kebijakan.
* Parameter dengan nilai default tidak lagi dibutuhkan saat menetapkan kebijakan dengan 'New-AzureRmPolicyAssignment'
* Menambahkan cmdlet baru Get-AzureRmPolicyAlias untuk mengambil alias kebijakan

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Memperbaiki masalah #7161

#### <a name="azurermsignalr"></a>AzureRM.SignalR
* Memperbarui nama SKU ke Free_F1 dan Standard_S1
* Tambahkan bidang versi ke objek PSSignalRResource dan string koneksi ke objek PSSignalRKeys.

#### <a name="azurermstorage"></a>AzureRM.Storage
* Mendukung Kebijakan Ketetapan di AzureRm.Storage
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
* Switch HyperV- New-AzureRmAppServicePlan ditambahkan untuk membuat paket layanan aplikasi dengan kontainer windows
* New-AzureRmWebApp/ New-AzureRmWebAppSlot/ Set-AzureRmWebApp/ Set-AzureRmWebAppSlot - Parameter baru (–string ContainerRegistryUser -ContainerRegistryPassword secureString -EnableContainerContinuousDeployment) ditambahkan untuk membuat dan mengelola aplikasi kontainer windows

## <a name="681---august-2018"></a>6.8.1 - Agustus 2018
#### <a name="general"></a>Umum
* Memperbaiki masalah dengan grup sumber daya default yang tidak diatur.
* Rakitan runtime umum yang diperbarui

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Memperbaiki masalah dengan grup sumber daya default yang tidak diatur.
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6603
    - Cmdlet Import-AzureRmApiManagementApi dan *-AzureRmApiManagementCertificate sekarang menangani Jalur relatif
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6879
    - CertificateInformation adalah properti yang dapat diatur yang memungkinkan cmdlet Set-AzureRmApiManagement untuk properti kerja. Diperbaiki dengan meningkatkan ke nuget 4.0.4-preview
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6853
    - Memperbaiki filter Odata untuk Pencarian berdasarkan Nama pada Produk
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6814
    - Memperbaiki filter Odata untuk Pencarian berdasarkan Nama di Api
* Menambahkan dukungan untuk pencatat AzureMonitor


#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki masalah yang targetnya tidak ada dalam output kesalahan.
* Memperbaiki masalah jenis akun penyimpanan untuk mesin virtual dengan disk terkelola
* Memperbaiki masalah dengan grup sumber daya default yang tidak diatur.
* Memperbaiki cmdlet Ekstensi AEM untuk lingkungan lain, misalnya Azure Tiongkok

#### <a name="azurermnetwork"></a>AzureRM.Network
* Mengubah presentasi output cmdlet default menjadi tampilan tabel

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Memperbaiki kegagalan dalam Perbarui-AzureRmPowerBIEmbeddedCapacity saat mencoba menskalakan kapasitas yang dijeda


#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah saat membuat aplikasi terkelola dari MarketPlace.

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Memperbaiki masalah
    - https://github.com/Azure/azure-powershell/issues/5058
    - https://github.com/Azure/azure-powershell/issues/5055
    - https://github.com/Azure/azure-powershell/issues/6891

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Menambahkan Dukungan untuk metode perutean MultiValue
    - Parameter baru 'MaxReturn' untuk perutean MultiValue
* Menambahkan Dukungan untuk metode perutean Subnet
    - Dukungan untuk rentang alamat IP (subnet) di titik akhir
* Menambahkan Dukungan untuk Header Kustom di profil
* Menambahkan Dukungan untuk rentang kode status yang diharapkan di profil
* Menambahkan Dukungan untuk Header Kustom di titik akhir

## <a name="680---august-2018"></a>6.8.0 - Agustus 2018
#### <a name="general"></a>Umum
* Memperbaiki masalah dengan grup sumber daya default yang tidak diatur.

#### <a name="azurermprofile"></a>AzureRM.Profile
* Menambahkan properti kedaluwarsa ke token yang dikembalikan selama Connect-AzureRmAccount

#### <a name="azurermcompute"></a>AzureRM.Compute
* Memperbaiki masalah yang targetnya tidak ada dalam output kesalahan.
* Memperbaiki masalah jenis akun penyimpanan untuk mesin virtual dengan disk terkelola
* Memperbaiki cmdlet Ekstensi AEM untuk lingkungan lain, misalnya Azure Tiongkok

#### <a name="azurermiothub"></a>AzureRM.IotHub
* Memperbaiki contoh untuk New-AzureRmIotHubExportDevices dan New-AzureRmIotHubImportDevices

#### <a name="azurermnetwork"></a>AzureRM.Network
* Mengubah representasi model default menjadi tampilan-tabel

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Memperbaiki kegagalan dalam Perbarui-AzureRmPowerBIEmbeddedCapacity saat mencoba menskalakan kapasitas yang dijeda

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah saat membuat aplikasi terkelola dari MarketPlace.

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Memperbaiki masalah
    - https://github.com/Azure/azure-powershell/issues/5058
    - https://github.com/Azure/azure-powershell/issues/5055
    - https://github.com/Azure/azure-powershell/issues/6891

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Dukungan untuk metode perutean MultiValue
    - Parameter baru 'MaxReturn' untuk perutean MultiValue
* Dukungan untuk metode perutean Subnet
    - Dukungan untuk rentang alamat IP (subnet) di titik akhir
* Dukungan untuk Header Kustom di profil
* Dukungan untuk rentang kode status yang Diperkirakan di profil
* Dukungan untuk Header Kustom di titik akhir

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Memperbaiki masalah grup sumber daya default yang salah diatur.

## <a name="670---august-2018"></a>6.7.0 - Agustus 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Diperbarui ke versi terbaru Azure ClientRuntime.
* Menambahkan id pengguna ke nama konteks default untuk menghindari bentrokan konteks
    - https://github.com/Azure/azure-powershell/issues/6489
* Memperbaiki masalah dengan Clear-AzureRmContext yang menyebabkan masalah dengan memilih konteks #6398
* Aktifkan domain penyewa untuk diteruskan ke parameter '-TenantId' untuk 'Connect-AzureRmAccount'
    - https://github.com/Azure/azure-powershell/issues/3974
    - https://github.com/Azure/azure-powershell/issues/6709

#### <a name="azurestorage"></a>Azure.Storage
* Menghapus batasan 5TB untuk kuota Berbagi File Azure
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
* Tambahkan parameter EvictionPolicy ke New-AzureRmVmssConfig
* Gunakan lokasi default di DiskFileParameterSet New-AzureRmVm jika tidak ada Lokasi yang ditentukan.
* Memperbaiki deskripsi parameter di Save-AzureRmVMImage
* Memperbaiki cmdlet Get-AzureRmVMDiskEncryptionStatus untuk skenario terkait singlepass tertentu

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
* Memperbarui contoh untuk Set-AzureRmDataLakeStoreItemAcl
* Diperbarui ke versi terbaru Azure ClientRuntime.
* Memperbarui contoh untuk Set-AzureRmDataLakeStoreItemAclEntry

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

#### <a name="azurerminsights"></a>AzureRM.Insights
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
* Menambahkan contoh untuk Set-AzureRmLocalNetworkGateway
* Menambahkan contoh dan deskripsi untuk Add-AzureRmVirtualNetworkGatewayIpConfig, Get-AzureRmVirtualNetworkGatewayConnectionSharedKey and New-AzureRmVirtualNetworkGatewayConnection
* Menambahkan contoh untuk Remove-AzureRmVirtualNetworkGatewayIpConfig dan Reset-AzureRmVirtualNetworkGateway
* Menambahkan contoh untuk Reset-AzureRmVirtualNetworkGatewayConnectionSharedKey
* Menambahkan contoh untuk Set-AzureRmVirtualNetworkGatewayConnectionSharedKey
* Menambahkan contoh untuk Set-AzureRmVirtualNetworkGatewayConnection
* Cmdlet yang dibuat ulang untuk ApplicationSecurityGroup, RouteTable, dan Penggunaan memakai generator kode terbaru
* Pesan kesalahan yang diklarifikasi untuk Get-AzureRmVirtualNetworkSubnetConfig saat berupaya mendapatkan subnet yang tidak keluar

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
* Menambahkan filter kebijakan ke cmdlet Get-AzureRmRecoveryServicesBackItem. Perintah mengembalikan daftar item cadangan yang dilindungi oleh id kebijakan yang diberikan.
* Memperbarui Microsoft.Azure.Management.RecoveryServices.Backup ke versi 3.0.0-pratinjau.
* Diperbarui ke versi terbaru Azure ClientRuntime.
* Menambahkan parameter TargetResourceGroupName ke Restore-AzureRmRecoveryServicesBackupItem. Grup sumber daya tempat disk terkelola dipulihkan. Berlaku untuk pencadangan VM dengan disk terkelola.

#### <a name="azurermrecoveryservicessiterecovery"></a>AzureRM.RecoveryServices.SiteRecovery
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermrelay"></a>AzureRM.Relay
* Diperbarui ke versi terbaru Azure ClientRuntime.

#### <a name="azurermresources"></a>AzureRM.Resources
* Mendukung penyebaran templat pada cakupan langganan. Tambahkan Cmdlet baru:
    - New-AzureRmDeployment
    - Get-AzureRmDeployment
    - Test-AzureRmDeployment
    - Remove-AzureRmDeployment
    - Stop-AzureRmDeployment
    - Save-AzureRmDeploymentTemplate
    - Get-AzureRmDeploymentOperation
* Memperbaiki masalah di mana kesalahan muncul saat meneruskan konteks ke Set-AzureRmResource
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

#### <a name="azurermstorage"></a>AzureRM.Storage
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
* Memperbarui semua file bantuan untuk menyertakan jenis parameter lengkap dan jenis input/output yang benar.

#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbarui pustaka Common.Strategy agar dapat memvalidasi bahwa saat ini konfigurasi untuk sumber daya kompatibel dengan sumber daya target.
* Menambahkan jenis ps1xml ke Common.Storage

#### <a name="azurestorage"></a>Azure.Storage
* Menambahkan dukungan untuk mendapatkan Konteks Penyimpanan dari DefaultProfile
* Menambahkan Ps1XmlAttribute ke properti jenis output cmdlet.

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6370
    - Memperbaiki bug di Automapper untuk menerjemahkan PsApiManagementApi ke ApiContract
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6515
    - Memperbaiki bug di File.Save agar tidak kelebihan beban dengan Jenis Pengodean
* Memperbaiki masalah https://github.com/Azure/azure-powershell/issues/6560
    - Ditingkatkan ke versi Nuget 4.0.3 yang dapat memperbaiki pengecualian pola pada apiId

#### <a name="azurermcompute"></a>AzureRM.Compute
* Perbaiki masalah dengan membuat vm menggunakan DiskFileParameterSet di New-AzureRmVm gagal karena penggantian nama jenis akun penyimpanan PremiumLRS.
* Memperbaiki cmdlet Invoke-AzureRmVMRunCommand
* Perbarui Get-AzureRmAvailabilitySet untuk mengaktifkan daftar semua set ketersediaan dalam langganan.  (Parameter ResouceGroupName sekarang opsional.)
* Perbarui SimpleParameterSet 'New-AzureRmVm' untuk mengaktifkan Jaringan yagn Dipercepat pada vm yang memenuhi syarat.
* Perbarui parameter sederhana New-AzureRmVmss yang disetel untuk menggagalkan pembuatan vmss ketika LB yang ditentukan pengguna sudah ada.
* Memperbarui contoh untuk New-AzureRmDisk
* Menambahkan contoh untuk 'New-AzureRmVM'
* Memperbarui deskripsi untuk Set-AzureRmVMOSDisk
* Perbarui Contoh 1 untuk Set-AzureRmVMBginfoExtension guna memperbaiki ejaan dan awalan.

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui versi SDK ADF .Net ke 1.1.0.
* Mendukung berbagi runtime integrasi yang dihost sendiri ke seluruh pabrik data.
     - Tambahkan parameter baru -SharedIntegrationRuntimeResourceId ke cmdlet Set-AzureRmDataFactoryV2IntegrationRuntime.
     - Tambahkan parameter opsional baru -LinkedDataFactoryName ke cmdlet Remove-AzureRmDataFactoryV2IntegrationRuntime.

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Memperbarui SDK DataPlane (Microsoft.Azure.DataLake.Store) ke versi 1.1.9

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Penyaluran yang diperbarui untuk InputObject dan ResourceId dalam menghapus cmdlet

#### <a name="azurerminsights"></a>AzureRM.Insights
* Memperbaiki pemformatan OutputType dalam file bantuan
* Menggunakan SDK Microsoft.Azure.Management.Monitor 0.19.1-pratinjau

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbaiki masalah penyaluran di Set-AzureRmKeyVaultAccessPolicy

#### <a name="azurermnetwork"></a>AzureRM.Network
* Menambahkan contoh untuk cmdlet LoadBalancerInboundNatPoolConfig.

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah saat memberikan nama dan nilai tag untuk 'Get-AzureRmResource'
    - https://github.com/Azure/azure-powershell/issues/6765
* Perbaiki skenario penyaluran dengan 'Set-AzureRmResource'

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Penyaluran yang diperbarui untuk InputObject dan ResourceId dalam menghapus cmdlet
* memperbaiki beberapa masalah
    - https://github.com/Azure/azure-powershell/issues/3780
    - https://github.com/Azure/azure-powershell/issues/4340

#### <a name="azurermsql"></a>AzureRM.Sql
* Menambahkan dukungan Perlindungan Ancaman Tingkat Lanjut Server dengan cmdlet berikut:
    - Enable-AzureRmSqlServerAdvancedThreatProtection; Disable-AzureRmSqlServerAdvancedThreatProtection; Get-AzureRmSqlServerAdvancedThreatProtectionPolicy
* Menambahkan dukungan Penilaian Kerentanan dengan cmdlet berikut:
    - Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings; Get-AzureRmSqlDatabaseVulnerabilityAssessmentSettings; Clear-AzureRmSqlDatabaseVulnerabilityAssessmentSettings
    - Set-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline; Get-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline; Clear-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline
    - Convert-AzureRmSqlDatabaseVulnerabilityAssessmentScan; Get-AzureRmSqlDatabaseVulnerabilityAssessmentScanRecord; Start-AzureRmSqlDatabaseVulnerabilityAssessmentScan
* Contoh tetap dalam Remove-AzureRmSqlServerFirewallRule
* Memperbaiki penanganan tanggalwaktu secara tidak benar untuk budaya dasar non-us di Get-AzureSqlSyncGroupLog

#### <a name="azurermstorage"></a>AzureRM.Storage
* Tambahkan Ps1XmlAttribute ke properti jenis output cmdlet
* Menampilkan output cmdlet StorageAccount dalam tampilan tabel
    - Get-AzureRmStorageAccount
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount

#### <a name="azurermtags"></a>AzureRM.Tags
* Menghapus pernyataan yang salah dari bantuan cmdlet Tag
    - https://github.com/Azure/azure-powershell/issues/3878

## <a name="650---july-2018"></a>6.5.0 - Juli 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Bantuan yang diperbarui untuk 'Get-AzureRmContextAutosaveSetting'

#### <a name="azurestorage"></a>Azure.Storage
* Mendukung Unggah Blob atau File dengan hanya menulis token Sas
* Set-AzureStorageBlobContent
* Set-AzureStorageFileContent

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Tambahkan properti yang diperlukan ResourceGroupName ke AS.

#### <a name="azurermautomation"></a>AzureRM.Automation
* Memperbarui bantuan dan menambahkan contoh untuk 'New-AzureRMAutomationSchedule'

#### <a name="azurermcompute"></a>AzureRM.Compute
* Menambahkan parameter -Tag ke Update/New-AzureRmAvailabilitySet
* Menambahkan contoh untuk 'Add-AzureRmVmssExtension'
* Menambahkan contoh untuk 'Remove-AzureRmVmssExtension'
* Memperbarui bantuan untuk 'Set-AzureRmVMAccessExtension'
* Perbarui SimpleParameterSet untuk New-AzureRmVmss guna mengatur SinglePlacementGroup ke false secara default dan tambahkan parameter switch 'SinglePlacementGroup' yang memungkinkan pengguna membuat VMSS dalam satu grup penempatan.

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Menambahkan properti readonly 'PendingReplicationOperationsCount' ke kelas PSEventHubDRConfigurationAttributes, yang memberikan jumlah operasi replikasi yang tertunda saat replikasi sedang berlangsung

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbarui pesan kesalahan untuk Set-AzureRmKeyVaultAccessPolicy

#### <a name="azurermlogicapp"></a>AzureRM.LogicApp
* Memperbaiki kesalahan "set parameter tidak dapat diselesaikan" di New-AzureRmLogicApp

#### <a name="azurermnetwork"></a>AzureRM.Network
* Mengaktifkan peering pada seluruh Jaringan Virtual di beberapa Penyewa untuk Set/Add-AzureRmVirtualNetworkPeering
* Memperbarui cmdlet di bawah ini untuk Application Gateway
    - New-AzureRmApplicationGateway : Menambahkan bendera EnableFIPS dan dukungan Zona
    - New-AzureRmApplicationGatewaySku : Menambahkan sku baru Standard_v2 dan WAF_v2
    - Set-AzureRmApplicationGatewaySku : Menambahkan sku baru Standard_v2 dan WAF_v2
* Cmdlet RouteTable yang diregenerasi dengan versi generator terbaru

#### <a name="azurermrelay"></a>AzureRM.Relay
* File penurunan harga yang diperbarui, perbaiki masalah nama parameter dalam contoh

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbarui cmdlet Roleassignment dan roledefinition:
    - Hapus panggilan roledefinition tambahan yang dilakukan sebagai bagian dari penomoran.
* Memperbaiki cmdlet Get-AzureRmRoleAssignment
    - Memperbaiki fungsionalitas parameter perintah-ExpandPrincipalGroups
* Memperbaiki masalah dengan 'Get-AzureRmResource' di mana parameter '-ResourceType' peka huruf besar/kecil

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Menambahkan parameter atas dan melewatkannya ke daftar cmdlet
* Menambahkan Standar ke cmdlet migrasi NameSpace Premium :
    - Start-AzureRmServiceBusMigration
    - Get-AzureRmServiceBusMigration
    - Complete-AzureRmServiceBusMigration
    - Stop-AzureRmServiceBusMigration
    - Remove-AzureRmServiceBusMigration
* Menambahkan properti readonly 'PendingReplicationOperationsCount' ke kelas PSServiceBusDRConfigurationAttributes, yang menimbulkan jumlah operasi replikasi tertunda saat replikasi sedang berlangsung

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Contoh pembaruan untuk 'New-AzureRmServiceFabricCluster'

#### <a name="azurermsql"></a>AzureRM.Sql
* Menambahkan Cmdlet baru untuk Management.Sql guna memungkinkan pelanggan menambahkan Sertifikat TDE ke instans SQLServer atau Instans Terkelola
    - Add-AzureRmSqlServerTransparentDataEncryptionCertificate
    - Add-AzureRmSqlManagedInstanceTransparentDataEncryptionCertificate

#### <a name="azurermwebsites"></a>AzureRM.Websites
* `Set-AzureRmWebApp -AssignIdentity` dan  `Set-AzureRmWebAppSlot -AssignIdentity` ketika diatur ke false sekarang akan menghapus properti Identitas dari objek situs. Menghapus tag pratinjau juga.
* contoh `Get-AzureRmWebAppMetrics`,`Get-AzureRmAppServicePlanMetrics` diperbarui
* `Set-AzureRmWebApp -PhpVersion` mendukung off sebagai versi php yang valid

## <a name="640---july-2018"></a>6.4.0 - Juli 2018
#### <a name="general"></a>Umum
* Memperbaiki pemformatan OutputType dalam file bantuan untuk sebagian besar modul

#### <a name="azurermprofile"></a>AzureRM.Profile
* Atribut Ps1Xml ditambahkan ke jenis output dasar

#### <a name="azurermcompute"></a>AzureRM.Compute
* Fitur Tag IP untuk VMSS
    - Cmdlet 'New-AzureRmVmssIpTagConfig' ditambahkan
    - Parameter IpTag ditambahkan ke New-AzureRmVmssIpConfig
* Fitur Rollback OS Otomatis untuk VMSS
    - Parameter DisableAutoRollback ditambahkan ke New-AzureRmVmssConfig dan Update-AzureRmVmss
* Fitur Riwayat Peningkatan OS untuk Vmss
    - Parameter switch OSUpgradeHistory ditambahkan ke Get-AzureRmVmss

#### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Tambahkan dukungan untuk ACL Katalog melalui perintah berikut:
    - Get-AzureRmDataLakeAnalyticsCatalogItemAclEntry
    - Set-AzureRmDataLakeAnalyticsCatalogItemAclEntry
    - Remove-AzureRmDataLakeAnalyticsCatalogItemAclEntry

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Tambahkan dukungan pembatalan dan pelacakan kemajuan untuk Set-AzureRmDataLakeStoreItemAclEntry, Remove-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAcl
* Menambahkan dukungan pembatalan untuk Export-AzureRmDataLakeStoreChildItemProperties
* Memperbaiki penghapusan pesan debug untuk cmdlet yang melakukan operasi rekursif
* Memperbaiki lokasi pengujian cmdlet DataLake

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Menambahkan parameter MaxCount Opsional ke cmdlet Operasi Daftar Get-AzureRmEventHub dan Get-AzureRmEventHubConsumerGroup
* Memperbaiki masalah di cmdlet New-AzureRmEventHub di mana setidaknya memerlukan satu parameter saat membuat EventHub Baru. Set Parameter Default yang Disediakan.
* Menambahkan Parameter opsional -KeyValue ke cmdlet New-AzureRmEventHubKey, yang memungkinkan pengguna untuk menyediakan KeyValue.

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbaiki masalah ketika semua sumber daya dikembalikan oleh Get-AzureRmKeyVault -Tag

#### <a name="azurermnetwork"></a>AzureRM.Network
* Mengekspos Sku baru untuk Zone-Redundant VirtualNetworkGateways
* Menambahkan perintah baru untuk fitur: API Mitra ExpressRoute melalui ARM
    - Menambahkan Get-AzureRmExpressRouteCrossConnection
    - Menambahkan Set-AzureRmExpressRouteCrossConnection
    - Menambahkan Add-AzureRmExpressRouteCrossConnectionPeering
    - Menambahkan Get-AzureRmExpressRouteCrossConnectionPeering
    - Menambahkan Remove-AzureRmExpressRouteCrossConnectionPeering
    - Menambahkan Get-AzureRMExpressRouteCrossConnectionArpTable
    - Menambahkan Get-AzureRMExpressRouteCrossConnectionRouteTable
    - Menambahkan Get-AzureRMExpressRouteCrossConnectionRouteTableSummary

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Menambahkan cmdlet Get-AzureRmRecoveryServicesBackupStatus. Cmdlet ini mengambil ID mesin virtual dan memeriksa apakah VM tersebut dilindungi oleh beberapa brankas dalam langganan. Jika ada brankas seperti itu, cmdlet mengeluarkan detail vault.

#### <a name="azurermresources"></a>AzureRM.Resources
* Perbarui cmdlet Get-AzureRmPolicyAssignment:
    - Menambahkan dukungan untuk mencantumkan nilai -Cakupan di tingkat grup manajemen
    - Menambahkan dukungan untuk mengambil tugas individual dengan nilai -Cakupan di tingkat grup manajemen
    - Tambahkan switch-Efektif dan -Semua ke parameter kontrol
* Memperbarui cmdlet Get/New/Remove/Set-AzureRmPolicyDefinition
    - Tambahkan parameter -ManagementGroupName untuk menerapkan operasi ke grup manajemen tertentu
    - Tambahkan parameter -SubscriptionId untuk menerapkan operasi ke langganan tertentu
* Memperbarui cmdlet Get/New/Remove/Set-AzureRmPolicySetDefinition
    - Tambahkan parameter -ManagementGroupName untuk menerapkan operasi ke grup manajemen tertentu
    - Tambahkan parameter -SubscriptionId untuk menerapkan operasi ke langganan tertentu
* Tambahkan dukungan referensi rahasia KeyVault dalam parameter saat menggunakan 'TemplateParameterObject' di 'New-AzureRmResourceGroupDeployment'
* Memperbaiki masalah ketika parameter '-EndDate' diabaikan untuk 'New-AzureRmADAppCredential'
    - https://github.com/Azure/azure-powershell/issues/6505
* Memperbaiki masalah ketika 'Add-AzureRmADGroupMember' menggunakan URL yang salah untuk membuat permintaan
    - https://github.com/Azure/azure-powershell/issues/6485

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Tambahkan Parameter opsional -KeyValue ke cmdlet New-AzureRmServiceBusKey, yang memungkinkan pengguna untuk menyediakan KeyValue.

#### <a name="azurermsql"></a>AzureRM.Sql
* Mengklarifikasi Titik Pemulihan yang Ditentukan Pengguna untuk SQLDW dalam bantuan New-AzureRmSqlDatabaseRestorePoint
* Dokumentasi terbaru parameter -ComputeGeneration dalam beberapa cmdlet

## <a name="630---june-2018"></a>6.3.0 - Juni 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Pesan kesalahan yang diperbarui untuk Enable-AzureRmContextAutoSave
* Membuat konteks untuk setiap langganan saat menjalankan 'Connect-AzureRmAccount' tanpa konteks sebelumnya

#### <a name="azurestorage"></a>Azure.Storage
* Menambahkan informasi tambahan tentang parameter -Izin dalam file bantuan.

#### <a name="azurermcompute"></a>AzureRM.Compute
* 'Get-AzureRmVmDiskEncryptionStatus' memperbaiki masalah yang diamati untuk VM tanpa disk data
* Perbarui versi pustaka klien Compute untuk memperbaiki cmdlet berikut
    - Grant-AzureRmDiskAccess
    - Grant-AzureRmSnapshotAccess
    - Save-AzureRmVMImage
* Perbaiki cmdlet berikut untuk menampilkan 'ID operasi' dan 'status operasi' dengan benar:
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
* Memperbaiki masalah ketika tidak ada Tag yang dikembalikan saat Get-AzureRmKeyVault -Tag dijalankan

#### <a name="azurermpolicyinsights"></a>AzureRM.PolicyInsights
* Rilis publik cmdlet Insight Kebijakan
    - Gunakan versi API 04-04-2018
    - Menambahkan PolicyDefinitionReferenceId ke hasil Get-AzureRmPolicyStateSummary

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Menambahkan parameter -Vault ke cmdlet RecoveryServices.Backup. Ketika diteruskan, ini akan menimpa cmdlet Set-AzureRmRecoveryServicesContext.

#### <a name="azurermsql"></a>AzureRM.Sql
* Contoh yang diperbarui dalam file bantuan untuk Get-AzureRmSqlDatabaseExpanded

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Memperbarui file bantuan untuk Add-AzureRmTrafficManagerEndpointConfig

#### <a name="azurermwebsites"></a>AzureRM.Websites
* 'Set-AzureRmWebApp' diperbarui agar tidak menimpa AppSettings saat menggunakan -AssignIdentity
* 'New-AzureRmWebAppSlot' diperbarui agar menghormati AppServicePlan sebagai parameter opsional

## <a name="621---june-2018"></a>6.2.1 - Juni 2018
### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Model PSWorkspace yang diperbarui untuk memungkinkan Jaringan menggunakan jenis sebagai parameter

## <a name="620---june-2018"></a>6.2.0 - Juni 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Perbaiki masalah di mana versi 10.0.3 Newtonsoft.Json tidak dimuat pada impor modul

#### <a name="azurermcompute"></a>AzureRM.Compute
* Fitur Pembaruan mesin virtual VMSS
    - Menambahkan cmdlet 'Update-AzureRmVmssVM' dan 'New-AzureRmVMDataDisk'
    - Tambahkan parameter VirtualMachineScaleSetVM ke cmdlet 'Add-AzureRmVMDataDisk' untuk mendukung penambahan disk data ke VMSS.

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Memperbarui versi SDK ADF .Net ke 0.8.0-pratinjau yang berisi perubahan berikut:
    - Menambahkan Konfigurasi operasi repositori pabrik
    - Memperbarui LinkedService QuickBooks untuk mengekspos properti consumerKey dan consumerSecret
    - Memperbarui Beberapa jenis model dari SecretBase ke Object
    - Menambahkan pemicu Peristiwa Blob

### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Memperbarui dokumentasi dengan contoh output

### <a name="azurermnetwork"></a>AzureRM.Network
* Mengaktifkan parameter Traffic Analytics pada cmdlet Network Watcher

#### <a name="azurermresources"></a>AzureRM.Resources
* Memperbaiki masalah terkait properti 'Properties' dari objek 'PSResource' yang dikembalikan dari 'Get-AzureRmResource'

#### <a name="azurermscheduler"></a>AzureRM.Scheduler
* Memperbaiki masalah dengan memperbarui ServiceBusQueueJob tidak menyetel nilai Auth baru

### <a name="azurermsql"></a>AzureRM.Sql
* Memperbarui cmdlet berikut dengan parameter LicenseType opsional
    - New-AzureRmSqlDatabase-AzureRmSqlDatabase; Set-AzureRmSqlDatabase
    - New-AzureRmSqlElasticPool; Set-AzureRmSqlElasticPool
    - New-AzureRmSqlDatabaseCopy
    - New-AzureRmSqlDatabaseSecondary
    - Restore-AzureRmSqlDatabase

#### <a name="azurermwebsites"></a>AzureRM.Websites
* 'New-AzureRMWebApp' diperbarui untuk menggunakan algoritma umum dari pustaka Strategi.

## <a name="610---may-2018"></a>6.1.0 - Mei 2018
#### <a name="azurermprofile"></a>AzureRM.Profile
* Memperbaiki masalah saat menjalankan 'Clear-AzureRmContext' akan menyimpan konteks kosong dengan nama konteks default sebelumnya, yang mencegah pengguna membuat konteks baru dengan nama lama

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Aktifkan operasi pengaitan/pemisahan Gateway di AS.

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Menambahkan dukungan untuk ApiVersions, ApiReleases dan ApiRevisions
* Menambahkan dukungan untuk Backend ServiceFabric
* Menambahkan dukungan untuk Pencatat Application Insights
* Menambahkan dukungan untuk mengenali sku 'Basic' sebagai sku layanan API Management yang valid
* Menambahkan dukungan untuk menginstal Sertifikat yang dikeluarkan oleh CA privat sebagai Root atau CA
* Menambahkan dukungan untuk menerima sertifikat SSL Kustom melalui KeyVault dan Beberapa nama host proksi
* Menambahkan dukungan untuk identitas MSI
* Menambahkan dukungan untuk menerima Kebijakan melalui CATATAN Url: Cmdlet berikut akan dihentikan di rilis mendatang
   - Import-AzureRmApiManagementHostnameCertificate
   - New-AzureRmApiManagementHostnameConfiguration
   - Set-AzureRmApiManagementHostnames
   - Update-AzureRmApiManagementDeployment

#### <a name="azurermbatch"></a>AzureRM.Batch
* Merilis cmdlet baru Get-AzureBatchPoolNodeCounts
* Merilis cmdlet baru Start-AzureBatchComputeNodeServiceLogUpload

#### <a name="azurermconsumption"></a>AzureRM.Consumption
* Menambahkan parameter baru seperti Perluas, ResourceGroup, InstanceName, InstanceId, Tag, dan Top di Cmdlet Get-AzureRmConsumptionUsageDetail

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Memperbaiki contoh untuk Export-AzureRmDataLakeStoreChildItemProperties
* Memperbaiki pengecualian parameter null untuk kasus Recurse di Set-AzureRmDataLakeStoreItemAclEntry
* Perbaiki file bantuan untuk Set-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAcl, Remove-AzureRmDataLakeStoreItemAclEntry

#### <a name="azurermnetwork"></a>AzureRM.Network
* Tingkatkan versi SDK Jaringan dari 18.0.0-pratinjau ke 19.0.0-pratinjau
* Menambahkan cmdlet untuk membuat konfigurasi protokol
    - New-AzureRmNetworkWatcherProtocolConfiguration
* Menambahkan cmdlet untuk menambahkan koneksi sirkuit baru ke sirkuit rute ekspres yang ada.
    - Add-AzureRmExpressRouteCircuitConnectionConfig
* Menambahkan cmdlet untuk menghapus koneksi sirkuit dari sirkuit rute ekspres yang ada.
    - Remove-AzureRmExpressRouteCircuitConnectionConfig
* Menambahkan cmdlet untuk mengambil koneksi sirkuit
    - Get-AzureRmExpressRouteCircuitConnectionConfig

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Memperbaiki penggunaan autentikasi server dengan sertifikat yang dihasilkan (Masalah #5998)

#### <a name="azurermsql"></a>AzureRM.Sql
* Memperbarui cmdlet Audit untuk memungkinkan penghapusan AuditActions atau AuditActionGroups
* Memperbaiki masalah dengan Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy saat menetapkan kebijakan retensi fleksibel baru di mana perintah akan gagal dengan 'Konfigurasikan kebijakan retensi jangka panjang dengan brankas dan kebijakan layanan pemulihan azure tidak lagi didukung. Silakan kirim permintaan dengan kebijakan retensi fleksibel yang baru'.
* Perbarui semua cmdlet terkait Azure Sql Database/ElasticPool Creation/Update untuk menggunakan API Database baru, yang mendukung properti Sku untuk properti terkait skala dan tingkat.
* Cmdlet yang diperbarui termasuk:
    - New-AzureRmSqlDatabase-AzureRmSqlDatabase; Set-AzureRmSqlDatabase
    - New-AzureRmSqlElasticPool; Set-AzureRmSqlElasticPool
    - New-AzureRmSqlDatabaseCopy
    - New-AzureRmSqlDatabaseSecondary
    - Restore-AzureRmSqlDatabase

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Perbarui parameter untuk 'Get-AzureRmTrafficManagerProfile' sehingga parameter -ResourceGroupName diperlukan saat menggunakan parameter -Name.
