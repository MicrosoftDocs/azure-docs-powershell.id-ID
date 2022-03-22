---
title: Panduan migrasi untuk Az 3.0.0
description: Panduan migrasi ini berisi daftar perubahan yang melanggar yang dibuat untuk Azure PowerShell dalam rilis Az versi 3.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: a727bed348d5c0a4fccd9e74b2fa6b641b109f67
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429471"
---
# <a name="migration-guide-for-az-300"></a>Panduan Migrasi untuk Az 3.0.0

Dokumen ini menjelaskan perubahan antara Az versi 2.0.0 dan 3.0.0

<!-- TOC -->

- [Panduan Migrasi untuk Az 3.0.0](#migration-guide-for-az-300)
  - [Batch](#batch)
    - [`Get-AzBatchNodeAgentSku`](#get-azbatchnodeagentsku)
    - [Ketidakcocokan dengan versi `Az.Resources` sebelumnya](#previous-version-incompatibility-with-azresources-module)
  - [Compute](#compute)
    - [`New-AzDiskConfig`](#new-azdiskconfig)
  - [HDInsight](#hdinsight)
    - [`Get-AzHDInsightJobOutput`](#get-azhdinsightjoboutput)
    - [`Add-AzHDInsightConfigValues`](#add-azhdinsightconfigvalues)
    - [`Disable-AzHDInsightMonitoring`](#disable-azhdinsightmonitoring)
    - [`Enable-AzHDInsightMonitoring`](#enable-azhdinsightmonitoring)
    - [`Get-AzHDInsightMonitoring`](#get-azhdinsightmonitoring)
    - [`Get-AzHDInsightProperty`](#get-azhdinsightproperty)
    - [`Grant-AzHDInsightRdpServicesAccess`](#grant-azhdinsightrdpservicesaccess)
    - [`Remove-AzHDInsightCluster`](#remove-azhdinsightcluster)
    - [`Revoke-AzHDInsightRdpServicesAccess`](#revoke-azhdinsightrdpservicesaccess)
    - [`Set-AzHDInsightGatewayCredential`](#set-azhdinsightgatewaycredential)
  - [IotHub](#iothub)
    - [`New-AzIotHubImportDevices`](#new-aziothubimportdevices)
    - [`New-AzIotHubExportDevices`](#new-aziothubexportdevices)
    - [`Add-AzIotHubEventHubConsumerGroup`](#add-aziothubeventhubconsumergroup)
    - [`Get-AzIotHubEventHubConsumerGroup`](#get-aziothubeventhubconsumergroup)
    - [`Remove-AzIotHubEventHubConsumerGroup`](#remove-aziothubeventhubconsumergroup)
    - [`Set-AzIotHub`](#set-aziothub)
  - [RecoveryServices](#recoveryservices)
    - [`Edit-AzRecoveryServicesAsrRecoveryPlan`](#edit-azrecoveryservicesasrrecoveryplan)
    - [`Get-AzRecoveryServicesAsrRecoveryPlan`](#get-azrecoveryservicesasrrecoveryplan)
    - [`New-AzRecoveryServicesAsrReplicationProtectedItem`](#new-azrecoveryservicesasrreplicationprotecteditem)
  - [Sumber](#resources)
    - [Ketidakcocokan dengan versi `Az.Batch` sebelumnya](#previous-version-incompatibility-with-azbatch-module)
  - [ServiceFabric](#servicefabric)
    - [`Add-ServiceFabricApplicationCertificate`](#add-servicefabricapplicationcertificate)
  - [Sql](#sql)
    - [`Get-AzSqlDatabaseSecureConnectionPolicy`](#get-azsqldatabasesecureconnectionpolicy)
    - [`Get-AzSqlDatabaseIndexRecommendations`](#get-azsqldatabaseindexrecommendations)
    - [`Get-AzSqlDatabaseRestorePoints`](#get-azsqldatabaserestorepoints)
    - [`Get-AzSqlDatabaseAuditing`](#get-azsqldatabaseauditing)
    - [`Set-AzSqlDatabaseAuditing`](#set-azsqldatabaseauditing)
    - [`Get-AzSqlServerAuditing`](#get-azsqlserverauditing)
    - [`Set-AzSqlServerAuditing`](#set-azsqlserverauditing)
    - [`Get-AzSqlServerAdvancedThreatProtectionSettings`](#get-azsqlserveradvancedthreatprotectionsettings)
    - [`Clear-AzSqlServerAdvancedThreatProtectionSettings`](#clear-azsqlserveradvancedthreatprotectionsettings)
    - [`Update-AzSqlServerAdvancedThreatProtectionSettings`](#update-azsqlserveradvancedthreatprotectionsettings)
    - [`Get-AzSqlDatabaseAdvancedThreatProtectionSettings`](#get-azsqldatabaseadvancedthreatprotectionsettings)
    - [`Update-AzSqlDatabaseAdvancedThreatProtectionSettings`](#update-azsqldatabaseadvancedthreatprotectionsettings)
    - [`Clear-AzSqlDatabaseAdvancedThreatProtectionSettings`](#clear-azsqldatabaseadvancedthreatprotectionsettings)
    - [`Update-AzSqlDatabaseVulnerabilityAssessmentSettings`](#update-azsqldatabasevulnerabilityassessmentsettings)
    - [`Get-AzSqlDatabaseVulnerabilityAssessmentSettings`](#get-azsqldatabasevulnerabilityassessmentsettings)
    - [`Clear-AzSqlDatabaseVulnerabilityAssessmentSettings`](#clear-azsqldatabasevulnerabilityassessmentsettings)
    - [`Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`](#update-azsqlinstancedatabasevulnerabilityassessmentsettings)
    - [`Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`](#get-azsqlinstancedatabasevulnerabilityassessmentsettings)
    - [`Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`](#clear-azsqlinstancedatabasevulnerabilityassessmentsettings)
    - [`Update-AzSqlInstanceVulnerabilityAssessmentSettings`](#update-azsqlinstancevulnerabilityassessmentsettings)
    - [`Get-AzSqlInstanceVulnerabilityAssessmentSettings`](#get-azsqlinstancevulnerabilityassessmentsettings)
    - [`Clear-AzSqlInstanceVulnerabilityAssessmentSettings`](#clear-azsqlinstancevulnerabilityassessmentsettings)
    - [`Update-AzSqlServerVulnerabilityAssessmentSettings`](#update-azsqlservervulnerabilityassessmentsettings)
    - [`Get-AzSqlServerVulnerabilityAssessmentSettings`](#get-azsqlservervulnerabilityassessmentsettings)
    - [`Clear-AzSqlServerVulnerabilityAssessmentSettings`](#clear-azsqlservervulnerabilityassessmentsettings)
    - [`Get-AzSqlServerAdvancedThreatProtectionPolicy`](#get-azsqlserveradvancedthreatprotectionpolicy)
    - [`Get-AzSqlServerThreatDetectionPolicy`](#get-azsqlserverthreatdetectionpolicy)
    - [`Remove-AzSqlServerThreatDetectionPolicy`](#remove-azsqlserverthreatdetectionpolicy)
    - [`Set-AzSqlServerThreatDetectionPolicy`](#set-azsqlserverthreatdetectionpolicy)
    - [`Get-AzSqlDatabaseThreatDetectionPolicy`](#get-azsqldatabasethreatdetectionpolicy)
    - [`Set-AzSqlDatabaseThreatDetectionPolicy`](#set-azsqldatabasethreatdetectionpolicy)
    - [`Remove-AzSqlDatabaseThreatDetectionPolicy`](#remove-azsqldatabasethreatdetectionpolicy)

<!-- /TOC -->


## <a name="batch"></a>Batch

### `Get-AzBatchNodeAgentSku`
- Menghapus `Get-AzBatchNodeAgentSku` dan menggantinya dengan `Get-AzBatchSupportedImage`.
- `Get-AzBatchSupportedImage` mengembalikan data yang sama dengan `Get-AzBatchNodeAgentSku` tetapi dalam format yang lebih ramah.
- Citra baru yang tidak diverifikasi kini juga dikembalikan. Informasi tambahan tentang `Capabilities` dan `BatchSupportEndOfLife` untuk setiap citra juga disertakan.

#### <a name="before"></a>Sebelumnya
```powershell
$Context = Get-AzBatchAccountKeys -AccountName "ContosoBatchAccount"
Get-AzBatchNodeAgentSku -BatchContext $Context
```

#### <a name="after"></a>Sesudahnya
```powershell
$Context = Get-AzBatchAccountKey -AccountName "ContosoBatchAccount"
Get-AzBatchSupportedImage -BatchContext $Context
```
### <a name="previous-version-incompatibility-with-azresources-module"></a>Ketidakcocokan Versi sebelumnya dengan modul Az.Resources
Versi 2.0.1 modul ‘Az.Batch’ tidak cocok dengan versi sebelumnya (versi 1.7.0 atau lebih lama) dari modul ‘Az.Resources’.  Hal ini akan mengakibatkan ketidakmampuan untuk mengimpor versi 1.7.0 modul ‘Az.Resources’ jika versi 2.0.1 modul ‘Az.Batch’ diimpor.  Untuk memperbaiki masalah ini, cukup perbarui modul ‘Az.Resources’ ke versi 1.7.1 atau yang lebih tinggi, atau cukup pasang versi modul ‘Az’ terbaru.

## <a name="compute"></a>Compute

### `New-AzDiskConfig`
Parameter `UploadSizeInBytes` digunakan bukan `DiskSizeGB` untuk `New-AzDiskConfig` ketika CreateOption Diunggah

#### <a name="before"></a>Sebelumnya
```powershell
$diskconfig = New-AzDiskConfig -Location 'Central US' -DiskSizeGB 1023 -SkuName Standard_LRS -OsType Windows -CreateOption Upload -DiskIOPSReadWrite 500 -DiskMBpsReadWrite 8
```

#### <a name="after"></a>Sesudahnya
```powershell
$diskconfig = New-AzDiskConfig -Location 'Central US' -UploadSizeInBytes 1023 * 1024 * 1024 * 1024 -SkuName Standard_LRS -OsType Windows -CreateOption Upload -DiskIOPSReadWrite 500 -DiskMBpsReadWrite 8
```

## <a name="hdinsight"></a>HDInsight

### `Get-AzHDInsightJobOutput`
- Memperbarui cmdlet `Get-AzHDInsightJobOutput` untuk mendukung akses berbasis peran granular ke kunci penyimpanan.
- Pengguna dengan peran Operator Kluster HDInsight, Kontributor, atau Pemilik tidak akan terpengaruh.
- Pengguna hanya dengan peran Pembaca perlu menentukan parameter `DefaultStorageAccountKey` secara eksplisit.

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzHDInsightJobOutput  -ClusterName $clusterName -JobId $jobId
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzHDInsightJobOutput -ClusterName $clusterName -JobId $jobId -DefaultStorageAccountKey $storageAccountKey
```

### `Add-AzHDInsightConfigValues`
Cmdlet `Add-AzHDInsightConfigValue` menghapus alias ke `Add-AzHDInsightConfigValues`.

#### <a name="before"></a>Sebelumnya
Menggunakan alias yang tidak digunakan lagi
```powershell
Add-AzHDInsightConfigValues
```

#### <a name="after"></a>Sesudahnya
```powershell
Add-AzHDInsightConfigValue
```


### `Disable-AzHDInsightMonitoring`
Menambahkan cmdlet `Disable-AzHDInsightMonitoring` baru. Gunakan cmdlet ini untuk menonaktifkan pemantauan di kluster HDInsight (mengganti `Disable-AzHDInsightOperationsManagementSuite` dan `Disable-AzHDInsightOMS`).

#### <a name="before"></a>Sebelumnya
```powershell
Disable-AzHDInsightOMS -Name testcluster
```
```powershell
Disable-AzHDInsightOperationsManagementSuite -Name testcluster
```

#### <a name="after"></a>Sesudahnya
```powershell
Disable-AzHDInsightMonitoring -Name testcluster
```


### `Enable-AzHDInsightMonitoring`
Menambahkan cmdlet `Enable-AzHDInsightMonitoring` baru. Gunakan cmdlet ini untuk mengaktifkan pemantauan di kluster HDInsight (mengganti `Enable-AzHDInsightOperationsManagementSuite` dan `Enable-AzHDInsightOMS`).

#### <a name="before"></a>Sebelumnya
```powershell
Enable-AzHDInsightOMS Enable-AzHDInsightMonitoring -Name testcluster -WorkspaceId 1d364e89-bb71-4503-aa3d-a23535aea7bd -PrimaryKey <key for workspace 1d364e89-bb71-4503-aa3d-a23535aea7bd>
```
```powershell
Enable-AzHDInsightOperationsManagementSuite Enable-AzHDInsightMonitoring -Name testcluster -WorkspaceId 1d364e89-bb71-4503-aa3d-a23535aea7bd -PrimaryKey <key for workspace 1d364e89-bb71-4503-aa3d-a23535aea7bd>
```

#### <a name="after"></a>Sesudahnya
```powershell
Enable-AzHDInsightMonitoring Enable-AzHDInsightMonitoring -Name testcluster -WorkspaceId 1d364e89-bb71-4503-aa3d-a23535aea7bd -PrimaryKey <key for workspace 1d364e89-bb71-4503-aa3d-a23535aea7bd>
```

### `Get-AzHDInsightMonitoring`
Menambahkan cmdlet `Get-AzHDInsightMonitoring` baru. Gunakan cmdlet ini untuk mendapatkan status penginstalan pemantauan di kluster Azure HDInsight (mengganti `Get-AzHDInsightOperationsManagementSuite` dan `Get-AzHDInsightOMS`).

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzHDInsightOMS -Name testcluster
```
```powershell
Get-AzHDInsightOperationsManagementSuite -Name testcluster
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzHDInsightMonitoring -Name testcluster
```

### `Get-AzHDInsightProperty`
Cmdlet `Get-HDInsightProperty` menghapus alias ke `Get-AzHDInsightProperties`.

#### <a name="before"></a>Sebelumnya
Menggunakan alias yang tidak digunakan lagi
```powershell
Get-AzHDInsightProperties -Location "East US 2"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzHDInsightProperty -Location "East US 2"
```

### `Grant-AzHDInsightRdpServicesAccess`
Menghapus cmdlet `Grant-AzHDInsightRdpServicesAccess` dan `Revoke-AzHDInsightRdpServicesAccess`. Cmdlet ini tidak lagi diperlukan karena kluster yang menggunakan jenis OS Windows tidak didukung. Silakan buat kluster menggunakan jenis OS Linux sebagai gantinya.

### `Remove-AzHDInsightCluster`
Jenis output `Remove-AzHDInsightCluster` berubah dari `Microsoft.Azure.Management.HDInsight.Models.ClusterGetResponse` menjadi `bool`.

#### <a name="before"></a>Sebelumnya
```powershell
$cluster = Remove-AzHDInsightCluster -ClusterName "your-hadoop-001"
```

#### <a name="after"></a>Sesudahnya
```powershell
Remove-AzHDInsightCluster -ClusterName "your-hadoop-001" -PassThru
True
```

### `Revoke-AzHDInsightRdpServicesAccess`
Cmdlet tidak digunakan lagi. Tidak ada pengganti untuk cmdlet ini.

### `Set-AzHDInsightGatewayCredential`
Jenis output `Set-AzHDInsightGatewayCredential` berubah dari `HttpConnectivitySettings` menjadi `AzureHDInsightGatewaySettings`.



## <a name="iothub"></a>IotHub

### `New-AzIotHubImportDevices`
Alias ini dihapus, silakan gunakan `New-AzIotHubImportDevice` sebagai gantinya.

#### <a name="before"></a>Sebelumnya
```powershell
New-AzIotHubImportDevices -ResourceGroupName "myresourcegroup" -Name "myiothub" -InputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -OutputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D"
```

#### <a name="after"></a>Sesudahnya
```powershell
New-AzIotHubImportDevice -ResourceGroupName "myresourcegroup" -Name "myiothub" -InputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -OutputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D"
```

### `New-AzIotHubExportDevices`
Alias ini dihapus, silakan gunakan `New-AzIotHubExportDevice` sebagai gantinya.

#### <a name="before"></a>Sebelumnya
```powershell
New-AzIotHubExportDevices -ResourceGroupName "myresourcegroup" -Name "myiothub" -ExportBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -ExcludeKeys
```

#### <a name="after"></a>Sesudahnya
```powershell
New-AzIotHubExportDevice -ResourceGroupName "myresourcegroup" -Name "myiothub" -ExportBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -ExcludeKeys
```

### `Add-AzIotHubEventHubConsumerGroup`
Parameter `EventHubEndPointName` tidak digunakan lagi tanpa perlu diganti karena IotHub dilengkapi dengan hanya satu titik akhir bawaan ("peristiwa") yang dapat menangani sistem dan pesan peranti.

#### <a name="before"></a>Sebelumnya
```powershell
Add-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName "myconsumergroup" -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Sesudahnya
```powershell
Add-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName "myconsumergroup"
```

### `Get-AzIotHubEventHubConsumerGroup`
Parameter `EventHubEndPointName` tidak digunakan lagi tanpa perlu diganti karena IotHub dilengkapi dengan hanya satu titik akhir bawaan ("peristiwa") yang dapat menangani sistem dan pesan peranti.

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub"
```

### `Remove-AzIotHubEventHubConsumerGroup`
Parameter `EventHubEndPointName` tidak digunakan lagi tanpa perlu diganti karena IotHub dilengkapi dengan hanya satu titik akhir bawaan ("peristiwa") yang dapat menangani sistem dan pesan peranti.

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName myconsumergroup -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Sesudahnya
```powershell
Remove-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName myconsumergroup
```

### `Set-AzIotHub`
Parameter `OperationsMonitoringProperties` tidak digunakan lagi tanpa diganti karena IotHub tidak lagi menggunakan titik akhir bawaan ("operationsMonitoringEvents").



## <a name="recoveryservices"></a>RecoveryServices

### `Edit-AzRecoveryServicesAsrRecoveryPlan`
`ASRRecoveryPlanGroup.ReplicationProtectedItems`, `ASRRecoveryPlanGroup.StartGroupActions`, dan `ASRRecoveryPlanGroup.EndGroupActions` dihapus dari output.

### `Get-AzRecoveryServicesAsrRecoveryPlan`
`ASRRecoveryPlanGroup.ReplicationProtectedItems`, `ASRRecoveryPlanGroup.StartGroupActions`, dan `ASRRecoveryPlanGroup.EndGroupActions` dihapus dari output.

### `New-AzRecoveryServicesAsrReplicationProtectedItem`
Parameter IncludeDiskId diubah untuk mendukung penulisan langsung ke disk terkelola di Azure Site Recovery.

#### <a name="before"></a>Sebelumnya
```powershell
$job = New-AzRecoveryServicesAsrReplicationProtectedItem -RecoveryAzureStorageAccountId $recoveryAzureStorageAccountId -IncludeDiskId $includeDiskId -VMwareToAzure -Account $fabric.FabricSpecificDetails.RunAsAccounts[0] -RecoveryResourceGroupId $RecoveryResourceGroupId -RecoveryAzureNetworkId $RecoveryAzureNetworkId -name $name -ProcessServer $fabric.FabricSpecificDetails.ProcessServers[0] -ProtectableItem $protectableItem -ProtectionContainerMapping $pcm -RecoveryAzureSubnetName $RecoveryAzureSubnetName -RecoveryVmName $RecoveryVmName -LogStorageAccountId $LogStorageAccountId
```

#### <a name="after"></a>Sesudahnya
```powershell
$disk1 = New-AzRecoveryServicesAsrInMageAzureV2DiskInput -DiskId $diskId -LogStorageAccountId $logStorageAccountId -DiskType $diskType
$disk2 = New-AzRecoveryServicesAsrInMageAzureV2DiskInput -DiskId $diskId2 -LogStorageAccountId $logStorageAccountId -DiskType $diskType2
$job = New-AzRecoveryServicesAsrReplicationProtectedItem -VMwareToAzure -Account $fabric.FabricSpecificDetails.RunAsAccounts[0] -RecoveryResourceGroupId $RecoveryResourceGroupId -RecoveryAzureNetworkId $RecoveryAzureNetworkId -name $name -ProcessServer $fabric.FabricSpecificDetails.ProcessServers[0] -ProtectableItem $protectableItem -ProtectionContainerMapping $pcm -RecoveryAzureSubnetName $RecoveryAzureSubnetName -RecoveryVmName $RecoveryVmName -LogStorageAccountId $LogStorageAccountId -InMageAzureV2DiskInput $disk1,$disk2
```

## <a name="resources"></a>Sumber

### <a name="previous-version-incompatibility-with-azbatch-module"></a>Ketidakcocokan Versi sebelumnya dengan modul Az.Batch
Versi 1.7.1 modul ‘Az.Resources’ tidak cocok dengan versi sebelumnya (versi 1.1.2 atau lebih lama) dari modul ‘Az.Batch’.  Hal ini akan mengakibatkan ketidakmampuan untuk mengimpor versi 1.1.2 modul ‘Az.Batch’ jika versi 1.7.1 modul ‘Az.Resources’ diimpor.  Untuk memperbaiki masalah ini, perbarui modul ‘Az.Batch’ ke versi 2.0.1 atau yang lebih tinggi, atau cukup pasang versi modul ‘Az’ terbaru.

## <a name="servicefabric"></a>ServiceFabric

### `Add-ServiceFabricApplicationCertificate`
Menghapus `Add-ServiceFabricApplicationCertificate` karena skenario ini dicakup dengan `Add-AzVmssSecret`.

#### <a name="before"></a>Sebelumnya
```powershell
Add-AzServiceFabricApplicationCertificate -ResourceGroupName "Group1" -Name "Contoso01SFCluster" -SecretIdentifier "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion"
```

#### <a name="after"></a>Sesudahnya
```powershell
$Vault = Get-AzKeyVault -VaultName "ContosoVault"
$CertConfig = New-AzVmssVaultCertificateConfig -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion" -CertificateStore "Certificates"
$VMSS = New-AzVmssConfig
Add-AzVmssSecret -VirtualMachineScaleSet $VMSS -SourceVaultId $Vault.ResourceId -VaultCertificate $CertConfig
```


## <a name="sql"></a>Sql

### `Get-AzSqlDatabaseSecureConnectionPolicy`
Perhatikan bahwa koneksi yang aman tidak digunakan lagi dan sehingga perintah dihapus. Silakan gunakan bilah database SQL di portal Microsoft Azure untuk menampilkan string koneksi

### `Get-AzSqlDatabaseIndexRecommendations`
Alias `Get-AzSqlDatabaseIndexRecommendations` dihapus. Gunakan `Get-AzSqlDatabaseIndexRecommendation` sebagai gantinya.

### `Get-AzSqlDatabaseRestorePoints`
Alias `Get-AzSqlDatabaseRestorePoints` dihapus. Gunakan `Get-AzSqlDatabaseRestorePoint` sebagai gantinya.

### `Get-AzSqlDatabaseAuditing`
- Cmdlet `Get-AzSqlDatabaseAudit` menggantikan cmdlet ini.
- Jenis output berubah dari jenis :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' yang ada menjadi jenis :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseAuditingSettingsModel' baru, yang menghapus properti `AuditState` dan `StorageAccountName`. dan `StorageAccountSubscriptionId`.  Skrip dapat mengambil informasi akun penyimpanan dari properti `StorageAccountResourceId` baru.

#### <a name="before"></a>Sebelumnya
```powershell
PS C:\> Get-AzSqlDatabaseAuditing -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01"
DatabaseName                 : database01
AuditAction                  : {}
AuditActionGroup             : {SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP, FAILED_DATABASE_AUTHENTICATION_GROUP,
                                BATCH_COMPLETED_GROUP, ...}
ResourceGroupName            : resourcegroup01
ServerName                   : server01
AuditState                   : Enabled
StorageAccountName           : mystorage
StorageKeyType               : Primary
RetentionInDays              : 0
StorageAccountSubscriptionId : 7fe3301d-31d3-4668-af5e-211a890ba6e3
PredicateExpression          : statement <> 'select 1'
```

#### <a name="after"></a>Sesudahnya
```powershell
PS C:\> Get-AzSqlDatabaseAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01"
ServerName                          : server01
DatabaseName                        : database01
AuditAction                         : {}
ResourceGroupName                   : resourcegroup01
AuditActionGroup                    : {SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP, FAILED_DATABASE_AUTHENTICATION_GROUP,
                                       BATCH_COMPLETED_GROUP, ...}
PredicateExpression                 : statement <> 'select 1'
BlobStorageTargetState              : Enabled
StorageAccountResourceId            : /subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage
StorageKeyType                      : Primary
RetentionInDays                     : 0
EventHubTargetState                 : Enabled
EventHubName                        : eventHubName
EventHubAuthorizationRuleResourceId : EventHubAuthorizationRuleResourceId
LogAnalyticsTargetState             : Enabled
WorkspaceResourceId                 : "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2"
```

### `Set-AzSqlDatabaseAuditing`
- Cmdlet `Set-AzSqlDatabaseAudit` menggantikan cmdlet ini.
- Jenis output berubah dari jenis :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' yang ada menjadi jenis :'bool' baru

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzSqlDatabaseAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22" -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Set-AzSqlDatabaseAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage"
```

### `Get-AzSqlServerAuditing`
- Cmdlet `Get-AzSqlServerAudit` menggantikan cmdlet ini.
- Jenis output berubah dari jenis :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' yang ada menjadi jenis :'Microsoft.Azure.Commands.Sql.Auditing.Model.ServerAuditingSettingsModel' baru.  Properti `AuditState`, `StorageAccountName`, dan `StorageAccountSubscriptionId` dihapus.  Skrip yang menggunakan properti `StorageAccountName` dan `StorageAccountSubscriptionId` dapat mengambil informasi ini dari properti `StorageAccountResourceId` baru.

#### <a name="before"></a>Sebelumnya
```powershell
PS C:\> Get-AzSqlServerAuditing -ResourceGroupName "resourcegroup01" -ServerName "server01"
AuditActionGroup             : {SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP, FAILED_DATABASE_AUTHENTICATION_GROUP, BATCH_COMPLETED_GROUP, ...}
ResourceGroupName            : resourcegroup01
ServerName                   : server01
AuditState                   : Enabled
StorageAccountName           : mystorage
StorageKeyType               : Primary
RetentionInDays              : 0
StorageAccountSubscriptionId : 7fe3301d-31d3-4668-af5e-211a890ba6e3
PredicateExpression          : statement <> 'select 1'
```

#### <a name="after"></a>Sesudahnya
```powershell
PS C:\> Get-AzSqlServerAudit -ResourceGroupName "resourcegroup01" -ServerName "server01"
ServerName                          : server01
ResourceGroupName                   : resourcegroup01
AuditActionGroup                    : {SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP, FAILED_DATABASE_AUTHENTICATION_GROUP, BATCH_COMPLETED_GROUP, ...}
PredicateExpression                 : statement <> 'select 1'
BlobStorageTargetState              : Enabled
StorageAccountResourceId            : /subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage
StorageKeyType                      : Primary
RetentionInDays                     : 0
EventHubTargetState                 : Enabled
EventHubName                        : eventHubName
EventHubAuthorizationRuleResourceId : EventHubAuthorizationRuleResourceId
LogAnalyticsTargetState             : Enabled
WorkspaceResourceId                 : "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2"
```

### `Set-AzSqlServerAuditing`
- Cmdlet `Set-AzSqlServerAudit` menggantikan cmdlet ini.
- Jenis output berubah dari jenis :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' yang ada menjadi jenis :'bool' baru

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzSqlServerAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22"
```

#### <a name="after"></a>Sesudahnya
```powershell
PS C:\> Set-AzSqlServerAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage"
```

### `Get-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Get-AzSqlServerAdvancedThreatProtectionSettings` diganti dengan `Get-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Clear-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Clear-AzSqlServerAdvancedThreatProtectionSettings` diganti dengan `Clear-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Update-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Update-AzSqlServerAdvancedThreatProtectionSettings` diganti dengan `Update-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Get-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Get-AzSqlDatabaseAdvancedThreatProtectionSettings` diganti dengan `Get-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

### `Update-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Update-AzSqlDatabaseAdvancedThreatProtectionSettings` diganti dengan `Update-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Clear-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Clear-AzSqlDatabaseAdvancedThreatProtectionSettings` diganti dengan `Clear-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

### `Update-AzSqlDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlDatabaseVulnerabilityAssessmentSettings` diganti dengan `Update-AzSqlDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01"`
    -ServerName "Server01"`
    -DatabaseName "Database01" `
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01"`
    -ServerName "Server01"`
    -DatabaseName "Database01" `
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```


### `Get-AzSqlDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Get-AzSqlDatabaseVulnerabilityAssessmentSettings` diganti dengan `Get-AzSqlDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlDatabaseVulnerabilityAssessmentSettings` diganti dengan `Clear-AzSqlDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` diganti dengan `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -InstanceName "ManagedInstance01" `
    -DatabaseName "Database01" `
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -InstanceName "ManagedInstance01" `
    -DatabaseName "Database01" `
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```

### `Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` diganti dengan `Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` diganti dengan `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Update-AzSqlInstanceVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlInstanceVulnerabilityAssessmentSettings` diganti dengan `Update-AzSqlInstanceVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlInstanceVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -InstanceName "ManagedInstance01" `
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlInstanceVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -InstanceName "ManagedInstance01" `
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```

### `Get-AzSqlInstanceVulnerabilityAssessmentSettings`
Cmdlet `Get-AzSqlInstanceVulnerabilityAssessmentSettings` diganti dengan `Get-AzSqlInstanceVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlInstanceVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlInstanceVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlInstanceVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlInstanceVulnerabilityAssessmentSettings` diganti dengan `Clear-AzSqlInstanceVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlInstanceVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlInstanceVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Update-AzSqlServerVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlServerVulnerabilityAssessmentSettings` diganti dengan `Update-AzSqlServerVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlServerVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01"`
    -ServerName "Server01"`
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlServerVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01"`
    -ServerName "Server01"`
    -StorageAccountName "mystorage" `
    -ScanResultsContainerName "vulnerability-assessment" `
    -RecurringScansInterval Weekly `
    -EmailSubscriptionAdmins $true `
    -NotificationEmail @("mail1@mail.com" , "mail2@mail.com")
```

### `Get-AzSqlServerVulnerabilityAssessmentSettings`
Cmdlet `Get-AzSqlServerVulnerabilityAssessmentSettings` diganti dengan `Get-AzSqlServerVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlServerVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlServerVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlServerVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlServerVulnerabilityAssessmentSettings` diganti dengan `Clear-AzSqlServerVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlServerVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Get-AzSqlServerAdvancedThreatProtectionPolicy`
Cmdlet `Get-AzSqlServerAdvancedThreatProtectionPolicy` dihapus dan tidak ada cmdlet yang menggantikannya

### `Get-AzSqlServerThreatDetectionPolicy`
Cmdlet `Get-AzSqlServerThreatDetectionPolicy` diganti dengan `Get-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
PS C:\> Get-AzSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
ResourceGroupName            : ResourceGroup11
ServerName                   : Server01
ThreatDetectionState         : Enabled
NotificationRecipientsEmails : admin@myCompany.com
StorageAccountName           : mystorage
EmailAdmins                  : True
ExcludedDetectionTypes       : {}
RetentionInDays              : 0
```

#### <a name="after"></a>Sesudahnya
```powershell
PS C:\> Get-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
ResourceGroupName            : ResourceGroup11
ServerName                   : Server01
ThreatDetectionState         : Enabled
NotificationRecipientsEmails : admin@myCompany.com
StorageAccountName           : mystorage
EmailAdmins                  : True
ExcludedDetectionTypes       : {}
RetentionInDays              : 0
```

### `Remove-AzSqlServerThreatDetectionPolicy`
Cmdlet `Remove-AzSqlServerThreatDetectionPolicy` diganti dengan `Clear-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Set-AzSqlServerThreatDetectionPolicy`
Cmdlet `Set-AzSqlServerThreatDetectionPolicy` diganti dengan `Update-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Get-AzSqlDatabaseThreatDetectionPolicy`
Cmdlet `Get-AzSqlDatabaseThreatDetectionPolicy` diganti dengan `Get-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
PS C:\> Get-AzSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName   "Database01"
DatabaseName                 : Database01
ResourceGroupName            : ResourceGroup11
ServerName                   : Server01
ThreatDetectionState         : Enabled
NotificationRecipientsEmails : admin@myCompany.com
StorageAccountName           : mystorage
EmailAdmins                  : True
ExcludedDetectionTypes       : {}
RetentionInDays              : 0
```

#### <a name="after"></a>Sesudahnya
```powershell
PS C:\> Get-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"   -DatabaseName "Database01"
DatabaseName                 : Database01
ResourceGroupName            : ResourceGroup11
ServerName                   : Server01
ThreatDetectionState         : Enabled
NotificationRecipientsEmails : admin@myCompany.com
StorageAccountName           : mystorage
EmailAdmins                  : True
ExcludedDetectionTypes       : {}
RetentionInDays              : 0
```

### `Set-AzSqlDatabaseThreatDetectionPolicy`
Cmdlet `Set-AzSqlDatabaseThreatDetectionPolicy` diganti dengan `Update-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Remove-AzSqlDatabaseThreatDetectionPolicy`
Cmdlet `Remove-AzSqlDatabaseThreatDetectionPolicy` diganti dengan `Clear-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```
