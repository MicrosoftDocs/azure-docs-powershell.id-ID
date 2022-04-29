---
description: Panduan migrasi ini berisi daftar perubahan berisiko yang dibuat untuk Azure PowerShell dalam rilis Az versi 2.0.
ms.custom: devx-track-azurepowershell
ms.date: 04/05/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Panduan migrasi untuk Az 2.0.0
ms.openlocfilehash: 486fe274403aced359287461182f6ac8246e72d1
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144294271"
---
# <a name="migration-guide-for-az-200"></a>Panduan Migrasi untuk Az 2.0.0

Dokumen ini menjelaskan perubahan antara Az versi 1.0.0 dan 2.0.0

## <a name="table-of-contents"></a>Daftar Isi
- [Perubahan modul yang dapat menyebabkan gangguan](#module-breaking-changes)
  - [Az.Compute](#azcompute)
  - [Az.HDInsight](#azhdinsight)
  - [Az.Storage](#azstorage)

## <a name="module-breaking-changes"></a>Perubahan modul yang dapat menyebabkan gangguan

### <a name="azcompute"></a>Az.Compute

- Menghapus parameter `Managed` dari cmdlet `New-AzAvailabilitySet` dan `Update-AzAvailabilitySet` yang mendukung penggunaan ```Sku = Aligned```

  #### <a name="before"></a>Sebelumnya

  ```powershell
  Update-AzAvailabilitySet -Managed
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Update-AzAvailabilitySet -Sku Aligned
  ```
- Untuk konsistensi, menghapus parameter `Image` dari set parameter 'ByName' dan 'ByResourceId' di `Update-AzImage`

  #### <a name="before"></a>Sebelumnya

  Perhatikan bahwa kode di bawah ini bersifat fungsional, tetapi ImageName yang diteruskan tidak digunakan, sehingga menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Update-AzImage -ResourceGroupName $Rg -ImageName $Name -Image $Image -Tag $tags

  Update-AzImage -ResourceId $Id -Image $Image -Tag $tags
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Update-AzImage -ResourceGroupName $Rg -ImageName $Name -Tag $tags

  Update-AzImage -ResourceId $Id -Tag $tags
  ```

- Untuk konsistensi, menghapus parameter `Name` dari set parameter 'ByObject' dan 'ByResourceId' di `Restart-AzVM`

  #### <a name="before"></a>Sebelumnya

  Perhatikan bahwa kode di bawah ini bersifat fungsional, tetapi Nama yang diteruskan tidak digunakan, sehingga menghapus parameter ini tidak memiliki dampak fungsional.
  ```powershell
  Restart-AzVM -InputObject $VM -Name $Name

  Restart-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Restart-AzVM -InputObject $VM

  Restart-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, menghapus parameter `Name` dari set parameter 'ByObject' dan 'ByResourceId' di `Start-AzVM`

  #### <a name="before"></a>Sebelumnya

  Perhatikan bahwa kode di bawah ini bersifat fungsional, tetapi Nama yang diteruskan tidak digunakan, sehingga menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Start-AzVM -InputObject $VM -Name $Name

  Start-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Start-AzVM -InputObject $VM

  Start-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, menghapus parameter `Name` dari set parameter 'ByObject' dan 'ByResourceId' di `Stop-AzVM`

  #### <a name="before"></a>Sebelumnya

  Perhatikan bahwa kode di bawah ini bersifat fungsional, tetapi Nama yang diteruskan tidak digunakan, sehingga menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Stop-AzVM -InputObject $VM -Name $Name

  Stop-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Stop-AzVM -InputObject $VM

  Stop-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, menghapus parameter `Name` dari set parameter 'ByObject' dan 'ByResourceId' di `Remove-AzVM`

  #### <a name="before"></a>Sebelumnya

  Perhatikan bahwa kode di bawah ini bersifat fungsional, tetapi Nama yang diteruskan tidak digunakan, sehingga menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Remove-AzVM -InputObject $VM -Name $Name

  Remove-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Remove-AzVM -InputObject $VM

  Remove-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, menghapus parameter `Name` dari set parameter 'ByObject' dan 'ByResourceId' di `Set-AzVM`

  #### <a name="before"></a>Sebelumnya

  Perhatikan bahwa kode di bawah ini bersifat fungsional, tetapi Nama yang diteruskan tidak digunakan, sehingga menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Set-AzVM -InputObject $VM -Name $Name ...

  Set-AzVM -ResourceId $Id -Name $Name ...
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Set-AzVM -InputObject $VM ...

  Set-AzVM -ResourceId $Id ...
  ```

- Untuk konsistensi, menghapus parameter `Name` dari set parameter 'ByObject' dan 'ByResourceId' di `Save-AzVMImage`

  #### <a name="before"></a>Sebelumnya
  Perhatikan bahwa kode di bawah ini bersifat fungsional, tetapi Nama yang diteruskan tidak digunakan, sehingga menghapus parameter ini tidak memiliki dampak fungsional.
  ```powershell
  Save-AzVMImage -InputObject $VM -Name $Name ...

  Save-AzVMImage -ResourceId $Id -Name $Name ...
  ```
  #### <a name="after"></a>Sesudahnya
  ```powershell
  Save-AzVMImage -InputObject $VM ...

  Save-AzVMImage -ResourceId $Id ...
  ```

- Menambahkan properti ProtectionPolicy untuk merangkum properti `ProtectFromScaleIn` di `PSVirtualMachineScaleSetVM`

  #### <a name="before"></a>Sebelumnya

  ```powershell
  $vmss = Get-AzVMssVM ...
  $vmss.ProtectFromScaleIn = $true

  $vmss = Update-AzVMssVM ...
  $vmss.ProtectFromScaleIn = $true

  $vmss = Remove-AzVMssVMDataDisk ...
  $vmss.ProtectFromScaleIn = $true
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  $vmss = Get-AzVMssVM ...
  $vmss.ProtectionPolicy.ProtectFromScaleIn = $true

  $vmss = Update-AzVMssVM ...
  $vmss.ProtectionPolicy.ProtectFromScaleIn = $true

  $vmss = Remove-AzVMssVMDataDisk ...
  $vmss.ProtectionPolicy.ProtectFromScaleIn = $true

  ```

- Menambahkan Properti ```EncryptionSettingsCollection``` untuk menyertakan properti `EncryptionSettings` di `PSDisk`

  #### <a name="before"></a>Sebelumnya

  ```powershell
  $disk = New-AzDisk ... | Set-AzDiskDiskEncrytionKey ...
  $disk.EncryptionSettings

  $disk = New-AzDisk ... | Set-AzDiskKeyEncrytionKey ...
  $disk.EncryptionSettings

  $update = New-AzDiskUpdateConfig | Set-AzDiskUpdateDiskEncryptionKey ...
  $update.EncryptionSettings

  $update = New-AzDiskUpdateConfig | Set-AzDiskUpdateKeyEncryptionKey ...
  $update.EncryptionSettings
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  $disk = New-AzDisk ... | Set-AzDiskDiskEncrytionKey ...
  $disk.EncryptionSettingsCollection.EncryptionSettings

  $disk = New-AzDisk ... | Set-AzDiskKeyEncrytionKey ...
  $disk.EncryptionSettingsCollection.EncryptionSettings

  $update = New-AzDiskUpdateConfig | Set-AzDiskUpdateDiskEncryptionKey ...
  $update.EncryptionSettingsCollection.EncryptionSettings

  $update = New-AzDiskUpdateConfig | Set-AzDiskUpdateKeyEncryptionKey ...
  $update.EncryptionSettingsCollection.EncryptionSettings
  ```

- Menambahkan Properti ```EncryptionSettingsCollection``` untuk menyertakan properti `EncryptionSettings` di `PSSnapshot`

  #### <a name="before"></a>Sebelumnya

  ```powershell
  $snap = New-AzSnapshotConfig ... | Set-AzSnapshotDiskEncryptionKey ...
  $snap.EncryptionSettings

  $snap = New-AzSnapshotConfig ... | Set-AzSnapshotKeyEncryptionKey ...
  $snap.EncryptionSettings

  $update = New-AzSnapshotUpdateConfig ... | Set-AzSnapshotUpdateDiskEncryptionKey ...
  $update.EncryptionSettings

  $update = New-AzSnapshotUpdateConfig ... | Set-AzSnapshotUpdateKeyEncryptionKey ...
  $update.EncryptionSettings
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  $snap = New-AzSnapshotConfig ... | Set-AzSnapshotDiskEncryptionKey ...
  $snap.EncryptionSettingsCollection.EncryptionSettings

  $snap = New-AzSnapshotConfig ... | Set-AzSnapshotKeyEncryptionKey ...
  $snap.EncryptionSettingsCollection.EncryptionSettings

  $update = New-AzSnapshotUpdateConfig ... | Set-AzSnapshotUpdateDiskEncryptionKey ...
  $update.EncryptionSettingsCollection.EncryptionSettings

  $update = New-AzSnapshotUpdateConfig ... | Set-AzSnapshotUpdateKeyEncryptionKey ...
  $update.EncryptionSettingsCollection.EncryptionSettings
  ```

- Menghapus properti `VirtualMachineProfile` dari `PSVirtualMachineScaleSet`

  #### <a name="before"></a>Sebelumnya

  ```powershell
  $vmss = New-AzVMSSConfig ...
  $vmss.VirtualMachineProfile.AdditionalCapabilities.UltraSSDEnabled = $true
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  $vmss = New-AzVMSSConfig ...
  $vmss.AdditionalCapabilities.UltraSSDEnabled = $true
  ```

- Cmdlet `Set-AzVMBootDiagnostic` menghapus alias ke `Set-AzVMBootDiagnostics`

  #### <a name="before"></a>Sebelumnya

  Menggunakan alias yang tidak digunakan lagi

  ```powershell
  Set-AzVMBootDiagnostics
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Set-AzVMBootDIagnostic
  ```

- Cmdlet `Export-AzLogAnalyticThrottledRequest` menghapus alias ke `Export-AzLogAnalyticThrottledRequests`

  #### <a name="before"></a>Sebelumnya

  Menggunakan alias yang tidak digunakan lagi

  ```powershell
  Export-AzLogAnalyticThrottledRequests
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Export-AzLogAnalyticThrottledRequest
  ```

### <a name="azhdinsight"></a>Az.HDInsight

- Menghapus cmdlet `Grant-AzHDInsightHttpServicesAccess` dan `Revoke-AzHDInsightHttpServicesAccess`. Hal ini tidak lagi diperlukan karena akses HTTP selalu diaktifkan di semua kluster HDInsight.
- Menambahkan cmdlet `Set-AzHDInsightGatewayCredential` baru. Gunakan cmdlet ini untuk mengubah nama pengguna dan kata sandi HTTP gateway (menggantikan `Grant-AzHDInsightHttpServicesAccess`).
- Memperbarui cmdlet `Get-AzHDInsightJobOutput` untuk mendukung akses berbasis peran granular ke kunci penyimpanan.
    - Pengguna dengan peran Operator Kluster HDInsight, Kontributor, atau Pemilik tidak akan terpengaruh.
    - Pengguna hanya dengan peran Pembaca perlu menentukan parameter `DefaultStorageAccountKey` secara eksplisit.

Untuk informasi selengkapnya tentang perubahan akses berbasis peran ini, lihat [aka.ms/hdi-config-update](/azure/hdinsight/hdinsight-migrate-granular-access-cluster-configurations)

  #### <a name="before"></a>Sebelumnya

  ```powershell
  Grant-AzHDInsightHttpServicesAccess -ClusterName $cluster -HttpCredential $credential
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Set-AzHDInsightGatewayCredential -ClusterName $cluster -HttpCredential $credential
  ```

###  <a name="users-with-only-reader-role-for-cmdlet-get-azhdinsightjoboutput"></a>Pengguna hanya dengan peran Pembaca untuk cmdlet Get-AzHDInsightJobOutput

  ####  <a name="before"></a>Sebelumnya

  ```powershell
  Get-AzHDInsightJobOutput  -ClusterName $clusterName -JobId $jobId
  ```

  #### <a name="after"></a>Sesudahnya

  ```powershell
  Get-AzHDInsightJobOutput  -ClusterName $clusterName -JobId $jobId -DefaultStorageAccountKey $storageAccountKey
  ```

### <a name="azstorage"></a>Az.Storage

- Namespace layanan untuk jenis yang dikembalikan dari cmdlet Blob, Antrean, dan File telah mengubah namespace layanan mereka dari `Microsoft.WindowsAzure.Storage` menjadi `Microsoft.Azure.Storage`.  Meskipun hal ini secara teknis bukan perubahan pemecahan sesuai dengan kebijakan perubahan pemecahan, hal ini memerlukan beberapa perubahan dalam kode yang menggunakan metode dari Storage .Net SDK untuk berinteraksi dengan objek yang dikembalikan dari cmdlet ini.

  #### <a name="example-1--add-a-message-to-a-queue-change-cloudqueuemessage-object-namespace"></a>Contoh 1: Menambahkan pesan ke Antrean (mengubah namespace layanan objek CloudQueueMessage)

  Sebelumnya:

  ```powershell
  $queue = Get-AzStorageQueue –Name $queueName –Context $ctx
  $queueMessage = New-Object -TypeName "Microsoft.WindowsAzure.Storage.Queue.CloudQueueMessage,$($queue.CloudQueue.GetType().Assembly.FullName)" -ArgumentList "This is message 1"
  $queue.CloudQueue.AddMessageAsync($QueueMessage)
  ```

  Setelahnya:

  ```powershell
  $queue = Get-AzStorageQueue –Name $queueName –Context $ctx
  $queueMessage = New-Object -TypeName "Microsoft.Azure.Storage.Queue.CloudQueueMessage,$($queue.CloudQueue.GetType().Assembly.FullName)"  -ArgumentList "This is message 1"
  $queue.CloudQueue.AddMessageAsync($QueueMessage)
  ```

  #### <a name="example-2--fetch-blobfile-attributes-with-accesscondition-change-accesscondition-object-namespace"></a>Contoh 2: Mengambil Atribut Blob/File dengan AccessCondition (mengubah namespace layanan objek AccessCondition)

  Sebelumnya:

  ```powershell
  $accessCondition= New-Object Microsoft.WindowsAzure.Storage.AccessCondition

  $blob = Get-AzureStorageBlob -Container $containerName -Blob $blobName
  $blob.ICloudBlob.FetchAttributes($accessCondition)

  $file = Get-AzureStorageFile -ShareName $shareName -Path $filepath
  $file.FetchAttributes($accessCondition)
  ```

  Setelahnya:

  ```powershell
  $accessCondition= New-Object Microsoft.Azure.Storage.AccessCondition

  $blob = Get-AzureStorageBlob -Container $containerName -Blob $blobName
  $blob.ICloudBlob.FetchAttributes($accessCondition)

  $file = Get-AzureStorageFile -ShareName $shareName -Path $filepath
  $file.FetchAttributes($accessCondition)
  ```

- Meskipun secara teknis bukan perubahan pemecahan, Anda akan menyadari perbedaan output di properti Sku.Name dari Akun Penyimpanan yang dikembalikan dari perubahan `New/Get/Set-AzStorageAccount` adalah sebagai berikut. (Setelah perubahan, SkuName output dan input disejajarkan.)
  - "StandardLRS" -> "Standard_LRS";
  - "StandardGRS" -> "Standard_GRS";
  - "StandardRAGRS" -> "Standard_RAGRS";
  - "StandardZRS" -> "Standard_ZRS";
  - "PremiumLRS" -> "Premium_LRS";

- Perilaku layanan default saat membuat akun penyimpanan tanpa menentukan Jenis telah berubah.  Pada versi sebelumnya, saat akun penyimpanan dibuat tanpa penentuan `Kind`, Jenis Akun penyimpanan `Storage` digunakan, pada versi baru `StorageV2` adalah nilai default `Kind`. Jika Anda perlu membuat Akun penyimpanan V1 dengan Jenis 'Storage', tambahkan parameter '-Kind Storage'

  #### <a name="example--create-a-storage-account-default-kind-change"></a>Contoh: Membuat Akun penyimpanan (perubahan Jenis Default)

  Sebelumnya:

  ```powershell
  PS c:\> New-AzStorageAccount -ResourceGroupName groupname -Name accountname -SkuName Standard_LRS -Location "westus"

  StorageAccountName ResourceGroupName Location SkuName     Kind      AccessTier CreationTime          ProvisioningState EnableHttpsTrafficOnly
  ------------------ ----------------- -------- -------     ----      ---------- ------------          ----------------- ----------------------
  accountname        groupname         westus   StandardLRS Storage   Hot        4/17/2018 10:34:32 AM Succeeded         False
  ```

  Setelahnya:

  ```powershell
  PS c:\> New-AzStorageAccount -ResourceGroupName groupname -Name accountname -SkuName Standard_LRS -Location "westus"

  StorageAccountName ResourceGroupName Location SkuName      Kind      AccessTier CreationTime          ProvisioningState EnableHttpsTrafficOnly
  ------------------ ----------------- -------- -------      ----      ----------  ------------          ----------------- ----------------------
  accountname        groupname         westus   Standard_LRS StorageV2 Hot        4/17/2018 10:34:32 AM Succeeded         False
  ```
