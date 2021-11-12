---
title: Panduan migrasi untuk Az 2.0.0
description: Panduan migrasi ini berisi daftar perubahan yang telah dibuat untuk Azure PowerShell di rilis Az versi 2.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: f051d42346741307f518451deafb62f4e8d4f530
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429489"
---
# <a name="migration-guide-for-az-200"></a>Panduan Migrasi untuk Az 2.0.0

Dokumen ini menjelaskan perubahan antara versi 1.0.0 dan 2.0.0 az

## <a name="table-of-contents"></a>Daftar Isi
- [Perubahan pecah modul](#module-breaking-changes)
  - [Az.Compute](#azcompute)
  - [Az.HDInsight](#azhdinsight)
  - [Az.Storage](#azstorage)

## <a name="module-breaking-changes"></a>Perubahan pecah modul

### <a name="azcompute"></a>Az.Compute

- Menghapus `Managed` Parameter dari dan cmdlet agar dapat `New-AzAvailabilitySet` `Update-AzAvailabilitySet` menggunakan ```Sku = Aligned```

  #### <a name="before"></a>Sebelum

  ```powershell
  Update-AzAvailabilitySet -Managed
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Update-AzAvailabilitySet -Sku Aligned
  ```
- Untuk konsistensi, `Image` parameter yang dihapus dari kumpulan parameter 'ByName' dan 'ByResourceId' dalam `Update-AzImage`

  #### <a name="before"></a>Sebelum

  Perhatikan bahwa kode di bawah ini adalah fungsional, tapi kata-kata yang diteruskan di ImageName tidak digunakan, jadi menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Update-AzImage -ResourceGroupName $Rg -ImageName $Name -Image $Image -Tag $tags

  Update-AzImage -ResourceId $Id -Image $Image -Tag $tags
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Update-AzImage -ResourceGroupName $Rg -ImageName $Name -Tag $tags

  Update-AzImage -ResourceId $Id -Tag $tags
  ```

- Untuk konsistensi, `Name` parameter yang dihapus dari kumpulan parameter 'ByObject' dan 'ByResourceId' di `Restart-AzVM`

  #### <a name="before"></a>Sebelum

  Perhatikan bahwa kode di bawah ini adalah fungsional, tapi Nama yang diteruskan tidak digunakan, jadi menghapus parameter ini tidak memiliki dampak fungsional.
  ```powershell
  Restart-AzVM -InputObject $VM -Name $Name

  Restart-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Restart-AzVM -InputObject $VM

  Restart-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, `Name` parameter yang dihapus dari kumpulan parameter 'ByObject' dan 'ByResourceId' di `Start-AzVM`

  #### <a name="before"></a>Sebelum

  Perhatikan bahwa kode di bawah ini adalah fungsional, tapi Nama yang diteruskan tidak digunakan, jadi menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Start-AzVM -InputObject $VM -Name $Name

  Start-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Start-AzVM -InputObject $VM

  Start-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, `Name` parameter yang dihapus dari kumpulan parameter 'ByObject' dan 'ByResourceId' di `Stop-AzVM`

  #### <a name="before"></a>Sebelum

  Perhatikan bahwa kode di bawah ini adalah fungsional, tapi Nama yang diteruskan tidak digunakan, jadi menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Stop-AzVM -InputObject $VM -Name $Name

  Stop-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Stop-AzVM -InputObject $VM

  Stop-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, `Name` parameter yang dihapus dari kumpulan parameter 'ByObject' dan 'ByResourceId' di `Remove-AzVM`

  #### <a name="before"></a>Sebelum

  Perhatikan bahwa kode di bawah ini adalah fungsional, tapi Nama yang diteruskan tidak digunakan, jadi menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Remove-AzVM -InputObject $VM -Name $Name

  Remove-AzVM -ResourceId $Id -Name $Name
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Remove-AzVM -InputObject $VM

  Remove-AzVM -ResourceId $Id
  ```

- Untuk konsistensi, `Name` parameter yang dihapus dari kumpulan parameter 'ByObject' dan 'ByResourceId' di `Set-AzVM`

  #### <a name="before"></a>Sebelum

  Perhatikan bahwa kode di bawah ini adalah fungsional, tapi Nama yang diteruskan tidak digunakan, jadi menghapus parameter ini tidak memiliki dampak fungsional.

  ```powershell
  Set-AzVM -InputObject $VM -Name $Name ...

  Set-AzVM -ResourceId $Id -Name $Name ...
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Set-AzVM -InputObject $VM ...

  Set-AzVM -ResourceId $Id ...
  ```

- Untuk konsistensi, `Name` parameter yang dihapus dari kumpulan parameter 'ByObject' dan 'ByResourceId' di `Save-AzVMImage`

  #### <a name="before"></a>Sebelum
  Perhatikan bahwa kode di bawah ini adalah fungsional, tapi Nama yang diteruskan tidak digunakan, jadi menghapus parameter ini tidak memiliki dampak fungsional.
  ```powershell
  Save-AzVMImage -InputObject $VM -Name $Name ...

  Save-AzVMImage -ResourceId $Id -Name $Name ...
  ```
  #### <a name="after"></a>Setelah
  ```powershell
  Save-AzVMImage -InputObject $VM ...

  Save-AzVMImage -ResourceId $Id ...
  ```

- Properti ProtectionPolicy ditambahkan untuk menyecap `ProtectFromScaleIn` properti di `PSVirtualMachineScaleSetVM`

  #### <a name="before"></a>Sebelum

  ```powershell
  $vmss = Get-AzVMssVM ...
  $vmss.ProtectFromScaleIn = $true

  $vmss = Update-AzVMssVM ...
  $vmss.ProtectFromScaleIn = $true

  $vmss = Remove-AzVMssVMDataDisk ...
  $vmss.ProtectFromScaleIn = $true
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  $vmss = Get-AzVMssVM ...
  $vmss.ProtectionPolicy.ProtectFromScaleIn = $true

  $vmss = Update-AzVMssVM ...
  $vmss.ProtectionPolicy.ProtectFromScaleIn = $true

  $vmss = Remove-AzVMssVMDataDisk ...
  $vmss.ProtectionPolicy.ProtectFromScaleIn = $true

  ```

- Properti ```EncryptionSettingsCollection``` yang Ditambahkan untuk menyertakan properti `EncryptionSettings` di `PSDisk`

  #### <a name="before"></a>Sebelum

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

  #### <a name="after"></a>Setelah

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

- Properti ```EncryptionSettingsCollection``` yang Ditambahkan untuk menyertakan properti `EncryptionSettings` di `PSSnapshot`

  #### <a name="before"></a>Sebelum

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

  #### <a name="after"></a>Setelah

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

- Properti `VirtualMachineProfile` yang dihapus dari `PSVirtualMachineScaleSet`

  #### <a name="before"></a>Sebelum

  ```powershell
  $vmss = New-AzVMSSConfig ...
  $vmss.VirtualMachineProfile.AdditionalCapabilities.UltraSSDEnabled = $true
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  $vmss = New-AzVMSSConfig ...
  $vmss.AdditionalCapabilities.UltraSSDEnabled = $true
  ```

- Cmdlet `Set-AzVMBootDiagnostic` removed alias to `Set-AzVMBootDiagnostics`

  #### <a name="before"></a>Sebelum

  Menggunakan alias yang sudah tidak berlaku

  ```powershell
  Set-AzVMBootDiagnostics
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Set-AzVMBootDIagnostic
  ```

- Cmdlet `Export-AzLogAnalyticThrottledRequest` removed alias to `Export-AzLogAnalyticThrottledRequests`

  #### <a name="before"></a>Sebelum

  Menggunakan alias yang sudah tidak digunakan

  ```powershell
  Export-AzLogAnalyticThrottledRequests
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Export-AzLogAnalyticThrottledRequest
  ```

### <a name="azhdinsight"></a>Az.HDInsight

- Menghapus `Grant-AzHDInsightHttpServicesAccess` `Revoke-AzHDInsightHttpServicesAccess` cmdlet. Ini tidak lagi diperlukan karena akses HTTP selalu diaktifkan pada semua kluster HDInsight.
- Menambahkan `Set-AzHDInsightGatewayCredential`  cmdlet baru. Gunakan cmdlet ini untuk mengubah nama pengguna dan kata sandi HTTP gateway (menggantikan `Grant-AzHDInsightHttpServicesAccess` ).
- Memperbarui `Get-AzHDInsightJobOutput` cmdlet untuk mendukung akses berbasis peran granular ke kunci penyimpanan.
    - Pengguna dengan peran Operator Kluster HDInsight, Kontributor, atau Pemilik tidak akan terpengaruh.
    - Pengguna dengan peran Pembaca saja harus menentukan `DefaultStorageAccountKey` parameter secara eksplisit.

Untuk informasi selengkapnya tentang perubahan akses berbasis peran ini, [lihat aka.ms/hdi-config-update](/azure/hdinsight/hdinsight-migrate-granular-access-cluster-configurations)

  #### <a name="before"></a>Sebelum

  ```powershell
  Grant-AzHDInsightHttpServicesAccess -ClusterName $cluster -HttpCredential $credential
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Set-AzHDInsightGatewayCredential -ClusterName $cluster -HttpCredential $credential
  ```

###  <a name="users-with-only-reader-role-for-cmdlet-get-azhdinsightjoboutput"></a>Pengguna dengan peran Pembaca saja untuk perintah cmdlet Get-AzHDInsightJobOutput

  ####  <a name="before"></a>Sebelum

  ```powershell
  Get-AzHDInsightJobOutput  -ClusterName $clusterName -JobId $jobId
  ```

  #### <a name="after"></a>Setelah

  ```powershell
  Get-AzHDInsightJobOutput  -ClusterName $clusterName -JobId $jobId -DefaultStorageAccountKey $storageAccountKey
  ```

### <a name="azstorage"></a>Az.Storage

- Ruang nama untuk tipe yang dikembalikan dari Blob, Antrean, dan cmdlet File telah mengubah ruang namanya `Microsoft.WindowsAzure.Storage` dari menjadi `Microsoft.Azure.Storage` .  Meskipun hal ini tidak secara teknis merupakan perubahan yang sedang terjadi menurut kebijakan perubahan yang sedang berjalan, namun mungkin memerlukan beberapa perubahan dalam kode yang menggunakan metode dari Storage .Net SDK untuk berinteraksi dengan objek yang dikembalikan dari cmdlets ini.

  #### <a name="example-1--add-a-message-to-a-queue-change-cloudqueuemessage-object-namespace"></a>Contoh 1: Menambahkan pesan ke Antrean (mengubah ruang nama objek CloudQueueMessage)

  Sebelum:

  ```powershell
  $queue = Get-AzStorageQueue –Name $queueName –Context $ctx
  $queueMessage = New-Object -TypeName "Microsoft.WindowsAzure.Storage.Queue.CloudQueueMessage,$($queue.CloudQueue.GetType().Assembly.FullName)" -ArgumentList "This is message 1"
  $queue.CloudQueue.AddMessageAsync($QueueMessage)
  ```

  Setelah:

  ```powershell
  $queue = Get-AzStorageQueue –Name $queueName –Context $ctx
  $queueMessage = New-Object -TypeName "Microsoft.Azure.Storage.Queue.CloudQueueMessage,$($queue.CloudQueue.GetType().Assembly.FullName)"  -ArgumentList "This is message 1"
  $queue.CloudQueue.AddMessageAsync($QueueMessage)
  ```

  #### <a name="example-2--fetch-blobfile-attributes-with-accesscondition-change-accesscondition-object-namespace"></a>Contoh 2: Ambil Atribut Blob/File dengan AccessCondition (mengubah ruang nama objek AccessCondition)

  Sebelum:

  ```powershell
  $accessCondition= New-Object Microsoft.WindowsAzure.Storage.AccessCondition

  $blob = Get-AzureStorageBlob -Container $containerName -Blob $blobName
  $blob.ICloudBlob.FetchAttributes($accessCondition)

  $file = Get-AzureStorageFile -ShareName $shareName -Path $filepath
  $file.FetchAttributes($accessCondition)
  ```

  Setelah:

  ```powershell
  $accessCondition= New-Object Microsoft.Azure.Storage.AccessCondition

  $blob = Get-AzureStorageBlob -Container $containerName -Blob $blobName
  $blob.ICloudBlob.FetchAttributes($accessCondition)

  $file = Get-AzureStorageFile -ShareName $shareName -Path $filepath
  $file.FetchAttributes($accessCondition)
  ```

- Meskipun bukan perubahan yang sedang berlangsung secara teknis, Anda akan menyadari perbedaan output dalam properti Sku.Name dari akun Storage yang dihasilkan `New/Get/Set-AzStorageAccount` dari perubahan adalah sebagai berikut. (Setelah perubahan, output dan SkuName input diratakan.)
  - "StandardLRS" -> "Standard_LRS";
  - "StandardGRS" -> "Standard_GRS";
  - "StandardRAGRS" -> "Standard_RAGRS";
  - "StandardZRS" -> "Standard_ZRS";
  - "PremiumLRS" -> "Premium_LRS";

- Perilaku layanan default saat membuat akun penyimpanan tanpa menentukan Jenis telah berubah.  Pada versi sebelumnya, ketika akun penyimpanan dibuat tanpa ditentukan, Jenis akun Storage digunakan, di versi `Kind` `Storage` baru adalah nilai `StorageV2` `Kind` default. Jika Anda perlu membuat akun V1 Storage dengan Kind 'Storage', tambahkan parameter '-Kind Storage'

  #### <a name="example--create-a-storage-account-default-kind-change"></a>Contoh : Membuat Akun penyimpanan (Perubahan Jenis Default)

  Sebelum:

  ```powershell
  PS c:\> New-AzStorageAccount -ResourceGroupName groupname -Name accountname -SkuName Standard_LRS -Location "westus"

  StorageAccountName ResourceGroupName Location SkuName     Kind      AccessTier CreationTime          ProvisioningState EnableHttpsTrafficOnly
  ------------------ ----------------- -------- -------     ----      ---------- ------------          ----------------- ----------------------
  accountname        groupname         westus   StandardLRS Storage   Hot        4/17/2018 10:34:32 AM Succeeded         False
  ```

  Setelah:

  ```powershell
  PS c:\> New-AzStorageAccount -ResourceGroupName groupname -Name accountname -SkuName Standard_LRS -Location "westus"

  StorageAccountName ResourceGroupName Location SkuName      Kind      AccessTier CreationTime          ProvisioningState EnableHttpsTrafficOnly
  ------------------ ----------------- -------- -------      ----      ----------  ------------          ----------------- ----------------------
  accountname        groupname         westus   Standard_LRS StorageV2 Hot        4/17/2018 10:34:32 AM Succeeded         False
  ```