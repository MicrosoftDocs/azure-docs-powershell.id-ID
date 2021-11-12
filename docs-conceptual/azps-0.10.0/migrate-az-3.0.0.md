---
title: Panduan migrasi untuk Az 3.0.0
description: Panduan migrasi ini berisi daftar perubahan terbaru yang dibuat untuk Azure PowerShell rilis Az versi 3.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/04/2019
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 641804fc0931d29f082ef7057f610beb75d7550a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421101"
---
# <a name="migration-guide-for-az-300"></a>Panduan Migrasi untuk Az 3.0.0

Dokumen ini menjelaskan perubahan antara versi 2.0.0 dan 3.0.0 az

<!-- TOC -->

- [Panduan Migrasi untuk Az 3.0.0](#migration-guide-for-az-300)
  - [Kumpulan](#batch)
    - [`Get-AzBatchNodeAgentSku`](#get-azbatchnodeagentsku)
    - [Inkompatibilitas dengan versi dari sebelumnya `Az.Resources`](#previous-version-incompatibility-with-azresources-module)
  - [Hitung](#compute)
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
  - [Sumber daya](#resources)
    - [Inkompatibilitas dengan versi dari sebelumnya `Az.Batch`](#previous-version-incompatibility-with-azbatch-module)
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


## <a name="batch"></a>Kumpulan

### `Get-AzBatchNodeAgentSku`
- Dihapus `Get-AzBatchNodeAgentSku` dan diganti dengan  `Get-AzBatchSupportedImage` .
- `Get-AzBatchSupportedImage` mengembalikan data yang sama dengan `Get-AzBatchNodeAgentSku` namun dalam format yang lebih mudah di dikenal.
- Gambar baru yang tidak diverifikasi kini juga dikembalikan. Informasi tambahan tentang `Capabilities` dan untuk setiap gambar juga `BatchSupportEndOfLife` disertakan.

#### <a name="before"></a>Sebelum
```powershell
$Context = Get-AzBatchAccountKeys -AccountName "ContosoBatchAccount"
Get-AzBatchNodeAgentSku -BatchContext $Context
```

#### <a name="after"></a>Setelah
```powershell
$Context = Get-AzBatchAccountKey -AccountName "ContosoBatchAccount"
Get-AzBatchSupportedImage -BatchContext $Context
```
### <a name="previous-version-incompatibility-with-azresources-module"></a>Inkompatibilitas Versi Sebelumnya dengan Modul Az.Resources
Versi 2.0.1 modul 'Az.Batch' tidak kompatibel dengan versi yang lebih lama (versi 1.7.0 atau yang lebih lama) modul 'Az.Resources'.  Hal ini akan mengakibatkan tidak dapat mengimpor modul 'Az.Resources' versi 1.7.0 ketika versi 2.0.1 modul 'Az.Batch' diimpor.  Untuk memperbaiki masalah ini, cukup perbarui modul 'Az.Resources' ke versi 1.7.1 atau yang lebih besar, atau cukup instal modul 'Az' versi terbaru.

## <a name="compute"></a>Hitung

### `New-AzDiskConfig`
`UploadSizeInBytes`parameter ini digunakan dan bukan `DiskSizeGB` `New-AzDiskConfig` ketika CreateOption tidak Upload

#### <a name="before"></a>Sebelum
```powershell
$diskconfig = New-AzDiskConfig -Location 'Central US' -DiskSizeGB 1023 -SkuName Standard_LRS -OsType Windows -CreateOption Upload -DiskIOPSReadWrite 500 -DiskMBpsReadWrite 8
```

#### <a name="after"></a>Setelah
```powershell
$diskconfig = New-AzDiskConfig -Location 'Central US' -UploadSizeInBytes 1023 * 1024 * 1024 * 1024 -SkuName Standard_LRS -OsType Windows -CreateOption Upload -DiskIOPSReadWrite 500 -DiskMBpsReadWrite 8
```

## <a name="hdinsight"></a>HDInsight

### `Get-AzHDInsightJobOutput`
- Memperbarui `Get-AzHDInsightJobOutput` cmdlet untuk mendukung akses berbasis peran granular ke kunci penyimpanan.
- Pengguna dengan peran Operator Kluster HDInsight, Kontributor, atau Pemilik tidak akan terpengaruh.
- Pengguna dengan peran Pembaca saja harus menentukan `DefaultStorageAccountKey` parameter secara eksplisit.

#### <a name="before"></a>Sebelum
```powershell
Get-AzHDInsightJobOutput  -ClusterName $clusterName -JobId $jobId
```

#### <a name="after"></a>Setelah
```powershell
Get-AzHDInsightJobOutput -ClusterName $clusterName -JobId $jobId -DefaultStorageAccountKey $storageAccountKey
```

### `Add-AzHDInsightConfigValues`
Cmdlet `Add-AzHDInsightConfigValue` removed alias to `Add-AzHDInsightConfigValues` .

#### <a name="before"></a>Sebelum
Menggunakan alias yang sudah tidak berlaku
```powershell
Add-AzHDInsightConfigValues
```

#### <a name="after"></a>Setelah
```powershell
Add-AzHDInsightConfigValue
```


### `Disable-AzHDInsightMonitoring`
Menambahkan `Disable-AzHDInsightMonitoring` cmdlet baru. Gunakan cmdlet ini untuk menonaktifkan pemantauan dalam kluster HDInsight (replaces `Disable-AzHDInsightOperationsManagementSuite` and `Disable-AzHDInsightOMS` ).

#### <a name="before"></a>Sebelum
```powershell
Disable-AzHDInsightOMS -Name testcluster
```
```powershell
Disable-AzHDInsightOperationsManagementSuite -Name testcluster
```

#### <a name="after"></a>Setelah
```powershell
Disable-AzHDInsightMonitoring -Name testcluster
```


### `Enable-AzHDInsightMonitoring`
Menambahkan `Enable-AzHDInsightMonitoring` cmdlet baru. Gunakan cmdlet ini untuk mengaktifkan pemantauan dalam kluster HDInsight (replaces `Enable-AzHDInsightOperationsManagementSuite` and `Enable-AzHDInsightOMS` ).

#### <a name="before"></a>Sebelum
```powershell
Enable-AzHDInsightOMS Enable-AzHDInsightMonitoring -Name testcluster -WorkspaceId 1d364e89-bb71-4503-aa3d-a23535aea7bd -PrimaryKey <key for workspace 1d364e89-bb71-4503-aa3d-a23535aea7bd>
```
```powershell
Enable-AzHDInsightOperationsManagementSuite Enable-AzHDInsightMonitoring -Name testcluster -WorkspaceId 1d364e89-bb71-4503-aa3d-a23535aea7bd -PrimaryKey <key for workspace 1d364e89-bb71-4503-aa3d-a23535aea7bd>
```

#### <a name="after"></a>Setelah
```powershell
Enable-AzHDInsightMonitoring Enable-AzHDInsightMonitoring -Name testcluster -WorkspaceId 1d364e89-bb71-4503-aa3d-a23535aea7bd -PrimaryKey <key for workspace 1d364e89-bb71-4503-aa3d-a23535aea7bd>
```

### `Get-AzHDInsightMonitoring`
Menambahkan `Get-AzHDInsightMonitoring` cmdlet baru. Gunakan cmdlet ini untuk mendapatkan status penginstalan pemantauan di kluster Azure HDInsight (ganti `Get-AzHDInsightOperationsManagementSuite` dan `Get-AzHDInsightOMS` ).

#### <a name="before"></a>Sebelum
```powershell
Get-AzHDInsightOMS -Name testcluster
```
```powershell
Get-AzHDInsightOperationsManagementSuite -Name testcluster
```

#### <a name="after"></a>Setelah
```powershell
Get-AzHDInsightMonitoring -Name testcluster
```

### `Get-AzHDInsightProperty`
Cmdlet `Get-HDInsightProperty` removed alias to `Get-AzHDInsightProperties` .

#### <a name="before"></a>Sebelum
Menggunakan alias yang sudah tidak berlaku
```powershell
Get-AzHDInsightProperties -Location "East US 2"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzHDInsightProperty -Location "East US 2"
```

### `Grant-AzHDInsightRdpServicesAccess`
Menghapus `Grant-AzHDInsightRdpServicesAccess` `Revoke-AzHDInsightRdpServicesAccess` cmdlet. Hal ini tidak perlu lagi dilakukan karena kluster Windows tipe OS tidak didukung. Silakan buat kluster menggunakan tipe Linux OS sebagai gantinya.

### `Remove-AzHDInsightCluster`
Tipe output berubah `Remove-AzHDInsightCluster` dari `Microsoft.Azure.Management.HDInsight.Models.ClusterGetResponse` menjadi `bool` .

#### <a name="before"></a>Sebelum
```powershell
$cluster = Remove-AzHDInsightCluster -ClusterName "your-hadoop-001"
```

#### <a name="after"></a>Setelah
```powershell
Remove-AzHDInsightCluster -ClusterName "your-hadoop-001" -PassThru
True
```

### `Revoke-AzHDInsightRdpServicesAccess`
Cmdlet sudah tidak berlaku. Tidak ada penggantinya.

### `Set-AzHDInsightGatewayCredential`
Tipe output berubah `Set-AzHDInsightGatewayCredential` dari `HttpConnectivitySettings` menjadi `AzureHDInsightGatewaySettings` .



## <a name="iothub"></a>IotHub

### `New-AzIotHubImportDevices`
Alias ini dihapus, silakan gunakan sebagai `New-AzIotHubImportDevice` gantinya.

#### <a name="before"></a>Sebelum
```powershell
New-AzIotHubImportDevices -ResourceGroupName "myresourcegroup" -Name "myiothub" -InputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -OutputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D"
```

#### <a name="after"></a>Setelah
```powershell
New-AzIotHubImportDevice -ResourceGroupName "myresourcegroup" -Name "myiothub" -InputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -OutputBlobContainerUri "https://mystorageaccount.blob.core.windows.net/?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D"
```

### `New-AzIotHubExportDevices`
Alias ini dihapus, silakan gunakan sebagai `New-AzIotHubExportDevice` gantinya.

#### <a name="before"></a>Sebelum
```powershell
New-AzIotHubExportDevices -ResourceGroupName "myresourcegroup" -Name "myiothub" -ExportBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -ExcludeKeys
```

#### <a name="after"></a>Setelah
```powershell
New-AzIotHubExportDevice -ResourceGroupName "myresourcegroup" -Name "myiothub" -ExportBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -ExcludeKeys
```

### `Add-AzIotHubEventHubConsumerGroup`
Parameter akan ditolak tanpa diganti karena IotHub hanya hadir dengan satu `EventHubEndPointName` endpoint("events") bawaan yang dapat menangani pesan sistem dan perangkat.

#### <a name="before"></a>Sebelum
```powershell
Add-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName "myconsumergroup" -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Setelah
```powershell
Add-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName "myconsumergroup"
```

### `Get-AzIotHubEventHubConsumerGroup`
Parameter akan ditolak tanpa diganti karena IotHub hanya hadir dengan satu `EventHubEndPointName` endpoint("events") bawaan yang dapat menangani pesan sistem dan perangkat.

#### <a name="before"></a>Sebelum
```powershell
Get-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub"
```

### `Remove-AzIotHubEventHubConsumerGroup`
Parameter akan ditolak tanpa diganti karena IotHub hanya hadir dengan satu `EventHubEndPointName` endpoint("events") bawaan yang dapat menangani pesan sistem dan perangkat.

#### <a name="before"></a>Sebelum
```powershell
Remove-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName myconsumergroup -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Setelah
```powershell
Remove-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName myconsumergroup
```

### `Set-AzIotHub`
Parameter tidak akan digantikan karena IotHub tidak lagi menggunakan titik akhir `OperationsMonitoringProperties` bawaan("operationsMonitoringEvents").



## <a name="recoveryservices"></a>RecoveryServices

### `Edit-AzRecoveryServicesAsrRecoveryPlan`
`ASRRecoveryPlanGroup.ReplicationProtectedItems`, `ASRRecoveryPlanGroup.StartGroupActions` dan dihapus dari `ASRRecoveryPlanGroup.EndGroupActions` output.

### `Get-AzRecoveryServicesAsrRecoveryPlan`
`ASRRecoveryPlanGroup.ReplicationProtectedItems`, `ASRRecoveryPlanGroup.StartGroupActions` dan dihapus dari `ASRRecoveryPlanGroup.EndGroupActions` output.

### `New-AzRecoveryServicesAsrReplicationProtectedItem`
Parameter IncludeDiskId diubah untuk mendukung penulisan langsung pada disk terkelola di Azure Site Recovery.

#### <a name="before"></a>Sebelum
```powershell
$job = New-AzRecoveryServicesAsrReplicationProtectedItem -RecoveryAzureStorageAccountId $recoveryAzureStorageAccountId -IncludeDiskId $includeDiskId -VMwareToAzure -Account $fabric.FabricSpecificDetails.RunAsAccounts[0] -RecoveryResourceGroupId $RecoveryResourceGroupId -RecoveryAzureNetworkId $RecoveryAzureNetworkId -name $name -ProcessServer $fabric.FabricSpecificDetails.ProcessServers[0] -ProtectableItem $protectableItem -ProtectionContainerMapping $pcm -RecoveryAzureSubnetName $RecoveryAzureSubnetName -RecoveryVmName $RecoveryVmName -LogStorageAccountId $LogStorageAccountId
```

#### <a name="after"></a>Setelah
```powershell
$disk1 = New-AzRecoveryServicesAsrInMageAzureV2DiskInput -DiskId $diskId -LogStorageAccountId $logStorageAccountId -DiskType $diskType
$disk2 = New-AzRecoveryServicesAsrInMageAzureV2DiskInput -DiskId $diskId2 -LogStorageAccountId $logStorageAccountId -DiskType $diskType2
$job = New-AzRecoveryServicesAsrReplicationProtectedItem -VMwareToAzure -Account $fabric.FabricSpecificDetails.RunAsAccounts[0] -RecoveryResourceGroupId $RecoveryResourceGroupId -RecoveryAzureNetworkId $RecoveryAzureNetworkId -name $name -ProcessServer $fabric.FabricSpecificDetails.ProcessServers[0] -ProtectableItem $protectableItem -ProtectionContainerMapping $pcm -RecoveryAzureSubnetName $RecoveryAzureSubnetName -RecoveryVmName $RecoveryVmName -LogStorageAccountId $LogStorageAccountId -InMageAzureV2DiskInput $disk1,$disk2
```

## <a name="resources"></a>Sumber daya

### <a name="previous-version-incompatibility-with-azbatch-module"></a>Inkompatibilitas Versi Sebelumnya dengan Modul Az.Batch
Versi 1.7.1 modul 'Az.Resources' tidak kompatibel dengan versi yang lebih lama (versi 1.1.2 atau yang lebih lama) modul 'Az.Batch'.  Hal ini akan mengakibatkan tidak dapat mengimpor versi 1.1.2 modul 'Az.Batch' ketika modul 'Az.Resources' versi 1.7.1 diimpor.  Untuk memperbaiki masalah ini, perbarui modul 'Az.Batch' ke versi 2.0.1 atau yang lebih besar, atau cukup instal modul 'Az' versi terbaru.

## <a name="servicefabric"></a>ServiceFabric

### `Add-ServiceFabricApplicationCertificate`
Dihapus `Add-ServiceFabricApplicationCertificate` karena skenario ini dibahas oleh `Add-AzVmssSecret` .

#### <a name="before"></a>Sebelum
```powershell
Add-AzServiceFabricApplicationCertificate -ResourceGroupName "Group1" -Name "Contoso01SFCluster" -SecretIdentifier "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion"
```

#### <a name="after"></a>Setelah
```powershell
$Vault = Get-AzKeyVault -VaultName "ContosoVault"
$CertConfig = New-AzVmssVaultCertificateConfig -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion" -CertificateStore "Certificates"
$VMSS = New-AzVmssConfig
Add-AzVmssSecret -VirtualMachineScaleSet $VMSS -SourceVaultId $Vault.ResourceId -VaultCertificate $CertConfig
```


## <a name="sql"></a>Sql

### `Get-AzSqlDatabaseSecureConnectionPolicy`
Perhatikan bahwa koneksi aman sudah tidak berlaku dan maka perintah dihapus. Silakan gunakan SQL database blade di portal Azure untuk menampilkan string koneksi

### `Get-AzSqlDatabaseIndexRecommendations`
`Get-AzSqlDatabaseIndexRecommendations` alias dihapus. Gunakan `Get-AzSqlDatabaseIndexRecommendation` sebagai gantinya.

### `Get-AzSqlDatabaseRestorePoints`
`Get-AzSqlDatabaseRestorePoints` alias dihapus. Gunakan `Get-AzSqlDatabaseRestorePoint` sebagai gantinya.

### `Get-AzSqlDatabaseAuditing`
- Cmdlet `Get-AzSqlDatabaseAudit` menggantikan cmdlet ini.
- Tipe output berubah dari tipe yang sudah ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseAuditingSettingsModel', menghapus properti `AuditState` dan `StorageAccountName` . dan `StorageAccountSubscriptionId` .  Skrip dapat mengambil informasi akun penyimpanan dari properti `StorageAccountResourceId` baru.

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
- Tipe output berubah dari tipe yang sudah ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'bool'

#### <a name="before"></a>Sebelum
```powershell
Set-AzSqlDatabaseAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22" -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Set-AzSqlDatabaseAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage"
```

### `Get-AzSqlServerAuditing`
- Cmdlet `Get-AzSqlServerAudit` menggantikan cmdlet ini.
- Tipe output berubah dari tipe yang sudah ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'Microsoft.Azure.Commands.Sql.Auditing.Model.ServerAuditingSettingsModel'.  Properti `AuditState` , , dan `StorageAccountName` `StorageAccountSubscriptionId` dihapus.  Skrip yang menggunakan `StorageAccountName` dan properti dapat mengambil informasi ini dari properti `StorageAccountSubscriptionId` `StorageAccountResourceId` baru.

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
- Tipe output berubah dari tipe yang sudah ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'bool'

#### <a name="before"></a>Sebelum
```powershell
Set-AzSqlServerAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22"
```

#### <a name="after"></a>Setelah
```powershell
PS C:\> Set-AzSqlServerAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage"
```

### `Get-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Get-AzSqlServerAdvancedThreatProtectionSettings` digantikan oleh `Get-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Get-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Clear-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Clear-AzSqlServerAdvancedThreatProtectionSettings` digantikan oleh `Clear-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Update-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Update-AzSqlServerAdvancedThreatProtectionSettings` digantikan oleh `Update-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Update-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Setelah
```powershell
Update-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Get-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Get-AzSqlDatabaseAdvancedThreatProtectionSettings` digantikan oleh `Get-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Get-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

### `Update-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Update-AzSqlDatabaseAdvancedThreatProtectionSettings` is repleaced by `Update-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Setelah
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Clear-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Clear-AzSqlDatabaseAdvancedThreatProtectionSettings` is repleaced by `Clear-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

### `Update-AzSqlDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlDatabaseVulnerabilityAssessmentSettings` is repleaced by `Update-AzSqlDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
Cmdlet `Get-AzSqlDatabaseVulnerabilityAssessmentSettings` is repleaced by `Get-AzSqlDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Get-AzSqlDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzSqlDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlDatabaseVulnerabilityAssessmentSettings` is repleaced by `Clear-AzSqlDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Clear-AzSqlDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` is repleaced by `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
Cmdlet `Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` is repleaced by `Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` is repleaced by `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Update-AzSqlInstanceVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlInstanceVulnerabilityAssessmentSettings` is repleaced by `Update-AzSqlInstanceVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
Cmdlet `Get-AzSqlInstanceVulnerabilityAssessmentSettings` is repleaced by `Get-AzSqlInstanceVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Get-AzSqlInstanceVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzSqlInstanceVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlInstanceVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlInstanceVulnerabilityAssessmentSettings` is repleaced by `Clear-AzSqlInstanceVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Clear-AzSqlInstanceVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlInstanceVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Update-AzSqlServerVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlServerVulnerabilityAssessmentSettings` is repleaced by `Update-AzSqlServerVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
Cmdlet `Get-AzSqlServerVulnerabilityAssessmentSettings` is repleaced by `Get-AzSqlServerVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Get-AzSqlServerVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Get-AzSqlServerVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Clear-AzSqlServerVulnerabilityAssessmentSettings`
Cmdlet `Clear-AzSqlServerVulnerabilityAssessmentSettings` is repleaced by `Clear-AzSqlServerVulnerabilityAssessmentSetting`

#### <a name="before"></a>Sebelum
```powershell
Clear-AzSqlServerVulnerabilityAssessmentSettings `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlDatabaseVulnerabilityAssessmentSetting `
    -ResourceGroupName "ResourceGroup01" `
    -ServerName "Server01" `
    -DatabaseName "Database01"
```

### `Get-AzSqlServerAdvancedThreatProtectionPolicy`
Cmdlet `Get-AzSqlServerAdvancedThreatProtectionPolicy` dihapus dan tidak ada cmdlet yangpleaced

### `Get-AzSqlServerThreatDetectionPolicy`
Cmdlet `Get-AzSqlServerThreatDetectionPolicy` is repleaced by `Get-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
Cmdlet `Remove-AzSqlServerThreatDetectionPolicy` is repleaced by `Clear-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Remove-AzSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Set-AzSqlServerThreatDetectionPolicy`
Cmdlet `Set-AzSqlServerThreatDetectionPolicy` is repleaced by `Update-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Set-AzSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Setelah
```powershell
Update-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Get-AzSqlDatabaseThreatDetectionPolicy`
Cmdlet `Get-AzSqlDatabaseThreatDetectionPolicy` is repleaced by `Get-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelum
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

#### <a name="after"></a>Setelah
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
Cmdlet `Set-AzSqlDatabaseThreatDetectionPolicy` is repleaced by `Update-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Set-AzSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Setelah
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Remove-AzSqlDatabaseThreatDetectionPolicy`
Cmdlet `Remove-AzSqlDatabaseThreatDetectionPolicy` is repleaced by `Clear-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelum
```powershell
Remove-AzSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Setelah
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```
