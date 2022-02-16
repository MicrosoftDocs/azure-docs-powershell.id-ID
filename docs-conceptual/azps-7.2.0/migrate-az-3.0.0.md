---
description: Panduan migrasi ini berisi daftar perubahan melanggar yang dibuat untuk Azure PowerShell dalam rilis Az versi 3.0.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Panduan migrasi untuk Az 3.0.0
ms.openlocfilehash: 9bae55c0fb0d438bd03e58b0d8cd0e0e10816d0e
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855873"
---
# <a name="migration-guide-for-az-300"></a>Panduan Migrasi untuk Az 3.0.0

Dokumen ini menjelaskan perubahan antara az versi 2.0.0 dan 3.0.0

<!-- TOC -->

- [Panduan Migrasi untuk Az 3.0.0](#migration-guide-for-az-300)
  - [Batch](#batch)
    - [`Get-AzBatchNodeAgentSku`](#get-azbatchnodeagentsku)
    - [Ketidakcocokan dengan versi sebelumnya dari `Az.Resources`](#previous-version-incompatibility-with-azresources-module)
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
  - [Layanan Pemulihan](#recoveryservices)
    - [`Edit-AzRecoveryServicesAsrRecoveryPlan`](#edit-azrecoveryservicesasrrecoveryplan)
    - [`Get-AzRecoveryServicesAsrRecoveryPlan`](#get-azrecoveryservicesasrrecoveryplan)
    - [`New-AzRecoveryServicesAsrReplicationProtectedItem`](#new-azrecoveryservicesasrreplicationprotecteditem)
  - [Sumber](#resources)
    - [Ketidakcocokan dengan versi sebelumnya dari `Az.Batch`](#previous-version-incompatibility-with-azbatch-module)
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
- Dihapus `Get-AzBatchNodeAgentSku` dan diganti dengan  `Get-AzBatchSupportedImage`.
- `Get-AzBatchSupportedImage` mengembalikan data yang sama seperti `Get-AzBatchNodeAgentSku` tetapi dalam format yang lebih ramah.
- Gambar baru yang tidak diverifikasi juga sekarang dikembalikan. Informasi tambahan tentang `Capabilities` dan `BatchSupportEndOfLife` untuk setiap gambar juga disertakan.

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
### <a name="previous-version-incompatibility-with-azresources-module"></a>Ketidakcocokan Versi Sebelumnya dengan Modul Az.Resources
Versi 2.0.1 dari modul 'Az.Batch' tidak kompatibel dengan versi sebelumnya (versi 1.7.0 atau versi lebih lama) dari modul 'Az.Resources'.  Hal ini akan mengakibatkan tidak dapat mengimpor versi 1.7.0 dari modul 'Az.Resources' ketika versi 2.0.1 dari modul 'Az.Batch' diimpor.  Untuk memperbaiki masalah ini, cukup perbarui modul 'Az.Resources' ke versi 1.7.1 atau lebih besar, atau cukup instal versi terbaru modul 'Az'.

## <a name="compute"></a>Compute

### `New-AzDiskConfig`
`UploadSizeInBytes`parameter digunakan sebagai pengganti `DiskSizeGB` `New-AzDiskConfig` ketika CreateOption Upload

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
- `Get-AzHDInsightJobOutput` Memperbarui cmdlet untuk mendukung akses berbasis peran granular ke kunci penyimpanan.
- Pengguna dengan peran Operator Kluster HDInsight, Kontributor, atau Pemilik tidak akan terpengaruh.
- Pengguna dengan hanya peran Reader perlu menentukan `DefaultStorageAccountKey` parameter secara eksplisit.

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzHDInsightJobOutput  -ClusterName $clusterName -JobId $jobId
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzHDInsightJobOutput -ClusterName $clusterName -JobId $jobId -DefaultStorageAccountKey $storageAccountKey
```

### `Add-AzHDInsightConfigValues`
Cmdlet `Add-AzHDInsightConfigValue` dihapus alias ke `Add-AzHDInsightConfigValues`.

#### <a name="before"></a>Sebelumnya
Menggunakan alias usang
```powershell
Add-AzHDInsightConfigValues
```

#### <a name="after"></a>Sesudahnya
```powershell
Add-AzHDInsightConfigValue
```


### `Disable-AzHDInsightMonitoring`
Menambahkan cmdlet baru `Disable-AzHDInsightMonitoring` . Gunakan cmdlet ini untuk menonaktifkan pemantauan dalam klaster HDInsight (menggantikan `Disable-AzHDInsightOperationsManagementSuite` dan `Disable-AzHDInsightOMS`).

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
Menambahkan cmdlet baru `Enable-AzHDInsightMonitoring` . Gunakan cmdlet ini untuk mengaktifkan pemantauan dalam klaster HDInsight (menggantikan `Enable-AzHDInsightOperationsManagementSuite` dan `Enable-AzHDInsightOMS`).

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
Menambahkan cmdlet baru `Get-AzHDInsightMonitoring` . Gunakan cmdlet ini untuk mendapatkan status instalasi pemantauan di klaster Azure HDInsight (menggantikan `Get-AzHDInsightOperationsManagementSuite` dan `Get-AzHDInsightOMS`).

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
Cmdlet `Get-HDInsightProperty` dihapus alias ke `Get-AzHDInsightProperties`.

#### <a name="before"></a>Sebelumnya
Menggunakan alias usang
```powershell
Get-AzHDInsightProperties -Location "East US 2"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzHDInsightProperty -Location "East US 2"
```

### `Grant-AzHDInsightRdpServicesAccess`
`Grant-AzHDInsightRdpServicesAccess` Menghapus dan `Revoke-AzHDInsightRdpServicesAccess` cmdlets. Ini tidak lagi diperlukan karena cluster yang menggunakan jenis OS Windows tidak didukung. Silakan buat cluster menggunakan tipe OS Linux sebagai gantinya.

### `Remove-AzHDInsightCluster`
Jenis `Remove-AzHDInsightCluster` output berubah dari `Microsoft.Azure.Management.HDInsight.Models.ClusterGetResponse` ke `bool`.

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
Cmdlet tidak digunakan lagi. Tidak ada pengganti untuk itu.

### `Set-AzHDInsightGatewayCredential`
Jenis `Set-AzHDInsightGatewayCredential` output berubah dari `HttpConnectivitySettings` ke `AzureHDInsightGatewaySettings`.



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
Parameter `EventHubEndPointName` tidak digunakan lagi tanpa diganti karena IotHub hanya dilengkapi dengan satu titik akhir bawaan ("peristiwa") yang dapat menangani pesan sistem dan perangkat.

#### <a name="before"></a>Sebelumnya
```powershell
Add-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName "myconsumergroup" -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Sesudahnya
```powershell
Add-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName "myconsumergroup"
```

### `Get-AzIotHubEventHubConsumerGroup`
Parameter `EventHubEndPointName` tidak digunakan lagi tanpa diganti karena IotHub hanya dilengkapi dengan satu titik akhir bawaan ("peristiwa") yang dapat menangani pesan sistem dan perangkat.

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub"
```

### `Remove-AzIotHubEventHubConsumerGroup`
Parameter `EventHubEndPointName` tidak digunakan lagi tanpa diganti karena IotHub hanya dilengkapi dengan satu titik akhir bawaan ("peristiwa") yang dapat menangani pesan sistem dan perangkat.

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName myconsumergroup -EventHubEndpointName "/EventHubEndpointName"
```

#### <a name="after"></a>Sesudahnya
```powershell
Remove-AzIotHubEventHubConsumerGroup -ResourceGroupName "myresourcegroup" -Name "myiothub" -EventHubConsumerGroupName myconsumergroup
```

### `Set-AzIotHub`
Parameter `OperationsMonitoringProperties` tidak digunakan lagi tanpa diganti karena IotHub tidak lagi menggunakan titik akhir bawaan("operationsMonitoringEvents").



## <a name="recoveryservices"></a>Layanan Pemulihan

### `Edit-AzRecoveryServicesAsrRecoveryPlan`
`ASRRecoveryPlanGroup.ReplicationProtectedItems`, `ASRRecoveryPlanGroup.StartGroupActions` dan `ASRRecoveryPlanGroup.EndGroupActions` dihapus dari output.

### `Get-AzRecoveryServicesAsrRecoveryPlan`
`ASRRecoveryPlanGroup.ReplicationProtectedItems`, `ASRRecoveryPlanGroup.StartGroupActions` dan `ASRRecoveryPlanGroup.EndGroupActions` dihapus dari output.

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

### <a name="previous-version-incompatibility-with-azbatch-module"></a>Ketidakcocokan Versi Sebelumnya dengan Modul Az.Batch
Versi 1.7.1 dari modul 'Az.Resources' tidak kompatibel dengan versi sebelumnya (versi 1.1.2 atau versi lebih lama) dari modul 'Az.Batch'.  Hal ini akan mengakibatkan tidak dapat mengimpor versi 1.1.2 dari modul 'Az.Batch' ketika versi 1.7.1 dari modul 'Az.Resources' diimpor.  Untuk memperbaiki masalah ini, perbarui modul 'Az.Batch' ke versi 2.0.1 atau lebih besar, atau cukup instal versi terbaru modul 'Az'.

## <a name="servicefabric"></a>ServiceFabric

### `Add-ServiceFabricApplicationCertificate`
Dihapus `Add-ServiceFabricApplicationCertificate` karena skenario ini dicakup oleh `Add-AzVmssSecret`.

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
Perhatikan bahwa koneksi aman tidak digunakan lagi sehingga perintah dihapus. Silakan gunakan bilah database SQL di portal Microsoft Azure untuk melihat string koneksi

### `Get-AzSqlDatabaseIndexRecommendations`
`Get-AzSqlDatabaseIndexRecommendations` alias dihapus. Gunakan `Get-AzSqlDatabaseIndexRecommendation` sebagai gantinya.

### `Get-AzSqlDatabaseRestorePoints`
`Get-AzSqlDatabaseRestorePoints` alias dihapus. Gunakan `Get-AzSqlDatabaseRestorePoint` sebagai gantinya.

### `Get-AzSqlDatabaseAuditing`
- Cmdlet `Get-AzSqlDatabaseAudit` menggantikan cmdlet ini.
- Jenis output berubah dari tipe yang ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseAuditingSettingsModel', menghapus properti `AuditState` dan `StorageAccountName`. dan `StorageAccountSubscriptionId`.  Skrip dapat mengambil informasi akun penyimpanan dari properti baru `StorageAccountResourceId` .

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
- Jenis output berubah dari tipe yang ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'bool'

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
- Jenis output berubah dari tipe yang ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'Microsoft.Azure.Commands.Sql.Auditing.Model.ServerAuditingSettingsModel'.  Properti `AuditState`, `StorageAccountName`, dan `StorageAccountSubscriptionId` dihapus.  Skrip yang menggunakan `StorageAccountName` dan `StorageAccountSubscriptionId` proeprties dapat mengambil informasi ini dari properti baru `StorageAccountResourceId` .

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
- Jenis output berubah dari tipe yang ada :'Microsoft.Azure.Commands.Sql.Auditing.Model.DatabaseBlobAuditingSettingsModel' ke tipe baru :'bool'

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzSqlServerAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22"
```

#### <a name="after"></a>Sesudahnya
```powershell
PS C:\> Set-AzSqlServerAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage"
```

### `Get-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Get-AzSqlServerAdvancedThreatProtectionSettings` digantikan oleh `Get-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Clear-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Clear-AzSqlServerAdvancedThreatProtectionSettings` digantikan oleh `Clear-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Update-AzSqlServerAdvancedThreatProtectionSettings`
Cmdlet `Update-AzSqlServerAdvancedThreatProtectionSettings` digantikan oleh `Update-AzSqlServerAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlServerAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Get-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Get-AzSqlDatabaseAdvancedThreatProtectionSettings` digantikan oleh `Get-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Get-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

### `Update-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Update-AzSqlDatabaseAdvancedThreatProtectionSettings` adalah repleaced oleh `Update-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Clear-AzSqlDatabaseAdvancedThreatProtectionSettings`
Cmdlet `Clear-AzSqlDatabaseAdvancedThreatProtectionSettings` adalah repleaced oleh `Clear-AzSqlDatabaseAdvancedThreatProtectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSettings -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

### `Update-AzSqlDatabaseVulnerabilityAssessmentSettings`
Cmdlet `Update-AzSqlDatabaseVulnerabilityAssessmentSettings` adalah repleaced oleh `Update-AzSqlDatabaseVulnerabilityAssessmentSetting`

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
Cmdlet `Get-AzSqlDatabaseVulnerabilityAssessmentSettings` adalah repleaced oleh `Get-AzSqlDatabaseVulnerabilityAssessmentSetting`

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
Cmdlet `Clear-AzSqlDatabaseVulnerabilityAssessmentSettings` adalah repleaced oleh `Clear-AzSqlDatabaseVulnerabilityAssessmentSetting`

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
Cmdlet `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` adalah repleaced oleh `Update-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

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
Cmdlet `Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` adalah repleaced oleh `Get-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

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
Cmdlet `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSettings` adalah repleaced oleh `Clear-AzSqlInstanceDatabaseVulnerabilityAssessmentSetting`

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
Cmdlet `Update-AzSqlInstanceVulnerabilityAssessmentSettings` adalah repleaced oleh `Update-AzSqlInstanceVulnerabilityAssessmentSetting`

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
Cmdlet `Get-AzSqlInstanceVulnerabilityAssessmentSettings` adalah repleaced oleh `Get-AzSqlInstanceVulnerabilityAssessmentSetting`

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
Cmdlet `Clear-AzSqlInstanceVulnerabilityAssessmentSettings` adalah repleaced oleh `Clear-AzSqlInstanceVulnerabilityAssessmentSetting`

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
Cmdlet `Update-AzSqlServerVulnerabilityAssessmentSettings` adalah repleaced oleh `Update-AzSqlServerVulnerabilityAssessmentSetting`

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
Cmdlet `Get-AzSqlServerVulnerabilityAssessmentSettings` adalah repleaced oleh `Get-AzSqlServerVulnerabilityAssessmentSetting`

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
Cmdlet `Clear-AzSqlServerVulnerabilityAssessmentSettings` adalah repleaced oleh `Clear-AzSqlServerVulnerabilityAssessmentSetting`

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
Cmdlet `Get-AzSqlServerAdvancedThreatProtectionPolicy` dihapus dan tidak ada cmdlet yang penuh dengannya

### `Get-AzSqlServerThreatDetectionPolicy`
Cmdlet `Get-AzSqlServerThreatDetectionPolicy` adalah repleaced oleh `Get-AzSqlServerThreatDetectionSetting`

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
Cmdlet `Remove-AzSqlServerThreatDetectionPolicy` adalah repleaced oleh `Clear-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

### `Set-AzSqlServerThreatDetectionPolicy`
Cmdlet `Set-AzSqlServerThreatDetectionPolicy` adalah repleaced oleh `Update-AzSqlServerThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlServerAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Get-AzSqlDatabaseThreatDetectionPolicy`
Cmdlet `Get-AzSqlDatabaseThreatDetectionPolicy` adalah repleaced oleh `Get-AzSqlDatabaseThreatDetectionSetting`

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
Cmdlet `Set-AzSqlDatabaseThreatDetectionPolicy` adalah repleaced oleh `Update-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

#### <a name="after"></a>Sesudahnya
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

### `Remove-AzSqlDatabaseThreatDetectionPolicy`
Cmdlet `Remove-AzSqlDatabaseThreatDetectionPolicy` adalah repleaced oleh `Clear-AzSqlDatabaseThreatDetectionSetting`

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

#### <a name="after"></a>Sesudahnya
```powershell
Clear-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```
