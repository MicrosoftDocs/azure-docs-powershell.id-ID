---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: F49FA524-28BC-464F-BD0A-F898E99C83D8
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/restore-azrecoveryservicesbackupitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Restore-AzRecoveryServicesBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Restore-AzRecoveryServicesBackupItem.md
ms.openlocfilehash: b3d93fca1d20ffa75868878356e270998743394c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142288663"
---
# Restore-AzRecoveryServicesBackupItem

## SYNOPSIS

Memulihkan data dan konfigurasi untuk item Cadangan ke titik pemulihan yang ditentukan. Parameter yang diperlukan bervariasi dengan tipe item cadangan.
Perintah yang sama digunakan untuk memulihkan mesin Azure Virtual, database yang berjalan di dalam mesin Azure Virtual dan berbagi file Azure juga.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/restore-azrecoveryservicesbackupitem) untuk informasi terbaru.

## SYNTAX

### AzureManagedVMReplaceExistingParameterSet (Default)
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 [-StorageAccountName] <String> [-StorageAccountResourceGroupName] <String> [-RestoreOnlyOSDisk]
 [-RestoreDiskList <String[]>] [-DiskEncryptionSetId <String>] [-RestoreToSecondaryRegion]
 [-TargetZoneNumber <Int32>] [-RehydratePriority <String>] [-UseSystemAssignedIdentity]
 [-UserAssignedIdentityId <String>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [-RehydrateDuration <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureManagedVMCreateNewParameterSet
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 [-StorageAccountName] <String> [-StorageAccountResourceGroupName] <String> [-TargetResourceGroupName] <String>
 [-RestoreOnlyOSDisk] [-RestoreDiskList <String[]>] [-DiskEncryptionSetId <String>] [-RestoreToSecondaryRegion]
 [-TargetZoneNumber <Int32>] [-RehydratePriority <String>] [-UseSystemAssignedIdentity]
 [-UserAssignedIdentityId <String>] [-TargetVMName <String>] [-TargetVNetName <String>]
 [-TargetVNetResourceGroup <String>] [-TargetSubnetName <String>] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-RehydrateDuration <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AzureFileShareParameterSet
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 -ResolveConflict <RestoreFSResolveConflictOption> [-SourceFilePath <String>]
 [-SourceFileType <SourceFileType>] [-TargetStorageAccountName <String>] [-TargetFileShareName <String>]
 [-TargetFolder <String>] [-MultipleSourceFilePath <String[]>] [-RestoreToSecondaryRegion] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureVMRestoreManagedAsUnmanaged
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 [-StorageAccountName] <String> [-StorageAccountResourceGroupName] <String> [-RestoreOnlyOSDisk]
 [-RestoreDiskList <String[]>] [-RestoreAsUnmanagedDisks] [-RestoreToSecondaryRegion]
 [-RehydratePriority <String>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [-RehydrateDuration <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureVMUnManagedDiskParameterSet
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 [-StorageAccountName] <String> [-StorageAccountResourceGroupName] <String> [-UseOriginalStorageAccount]
 [-RestoreOnlyOSDisk] [-RestoreDiskList <String[]>] [-RestoreToSecondaryRegion] [-RehydratePriority <String>]
 [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [-RehydrateDuration <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AzureVMRestoreUnmanagedAsManaged
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 [-StorageAccountName] <String> [-StorageAccountResourceGroupName] <String> [-TargetResourceGroupName] <String>
 [-UseOriginalStorageAccount] [-RestoreOnlyOSDisk] [-RestoreDiskList <String[]>] [-RestoreToSecondaryRegion]
 [-RestoreAsManagedDisk] [-RehydratePriority <String>] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-RehydrateDuration <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AzureWorkloadParameterSet
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-WLRecoveryConfig] <RecoveryConfigBase>
 [-RestoreToSecondaryRegion] [-RehydratePriority <String>] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-RehydrateDuration <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Restore-AzRecoveryServicesBackupItem** memulihkan data dan konfigurasi untuk item Azure Backup ke titik pemulihan tertentu.

**Untuk cadangan Azure VM**

Anda dapat mencadangkan mesin virtual Azure dan memulihkan disk (baik yang dikelola maupun tidak dikelola) menggunakan perintah ini. Operasi pemulihan tidak memulihkan mesin maya penuh.
Jika ini adalah VM disk terkelola, grup Sumber Daya target harus ditentukan di mana disk yang dipulihkan disimpan. Ketika grup sumber daya target ditentukan, jika snapshot ada dalam grup sumber daya yang ditentukan dalam kebijakan cadangan, operasi pemulihan akan instan dan disk dibuat dari snapshot lokal dan disimpan dalam grup sumber daya target. Ada juga opsi untuk memulihkannya sebagai disk yang tidak dikelola tetapi ini akan memanfaatkan data yang ada di kubah layanan pemulihan Azure dan karenanya akan jauh lebih lambat. Konfigurasi VM dan templat penyebaran yang dapat digunakan untuk membuat VM dari disk yang dipulihkan akan diunduh ke akun penyimpanan tertentu.
Jika ini adalah VM disk yang tidak dikelola, snapshot hadir di akun penyimpanan asli disk dan/atau dalam kubah layanan pemulihan. Jika pengguna memberikan opsi untuk menggunakan Akun penyimpanan asli untuk memulihkan, pemulihan instan dapat disediakan. Jika tidak, data diperoleh dari brankas dan disk layanan Pemulihan Azure dibuat di akun penyimpanan tertentu bersama dengan konfigurasi VM dan templat penyebaran.

> [!IMPORTANT]
> Secara default, cadangan Azure VM mencadangkan semua disk. Anda dapat mencadangkan disk yang relevan secara selektif menggunakan parameter exclusionList atau InclusionList selama Enable-Backup. Opsi untuk memulihkan disk secara selektif hanya tersedia jika disk telah dicadangkan secara selektif.

Silakan merujuk ke kumpulan parameter dan teks parameter yang berbeda untuk informasi selengkapnya.

> [!NOTE]
> Jika parameter -VaultId digunakan maka -VaultLocation parameter harus digunakan juga.

**Untuk cadangan berbagi File Azure**

Anda dapat memulihkan seluruh berbagi file atau file/beberapa file/folder tertentu pada berbagi. Anda bisa memulihkan ke lokasi asli atau ke lokasi alternatif.

**Untuk Beban Kerja Azure**

Anda dapat memulihkan SQL DB dalam Azure VM

## EXAMPLES

### Contoh 1: Memulihkan disk disk yang dicadangkan Disk terkelola Azure VM dari titik pemulihan tertentu

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
PS C:\> $StartDate = (Get-Date).AddDays(-7)
PS C:\> $EndDate = Get-Date
PS C:\> $RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
PS C:\> $RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -TargetResourceGroupName "Target_RG" -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -VaultId $vault.ID -VaultLocation $vault.Location
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan kubah Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan tipe AzureVM, nama "V2VM", dan menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah terakhir memulihkan semua disk ke grup sumber daya target Target_RG, lalu menyediakan informasi konfigurasi VM dan templat penyebaran di akun penyimpanan DestAccount dalam grup sumber daya DestRG.

### Contoh 2: Memulihkan AzureVM yang Dikelola dari titik pemulihan tertentu ke lokasi asli/alternatif 

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
PS C:\> $StartDate = (Get-Date).AddDays(-7)
PS C:\> $EndDate = Get-Date
PS C:\> $RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
PS C:\> $AlternateLocationRestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -TargetResourceGroupName "Target_RG" -StorageAccountName "DestStorageAccount" -StorageAccountResourceGroupName "DestStorageAccRG" -TargetVMName "TagetVirtualMachineName" -TargetVNetName "Target_VNet" -TargetVNetResourceGroup "" -TargetSubnetName "subnetName" -VaultId $vault.ID -VaultLocation $vault.Location 
PS C:\> $OriginalLocationRestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -StorageAccountName "DestStorageAccount" -StorageAccountResourceGroupName "DestStorageAccRG" -VaultId $vault.ID -VaultLocation $vault.Location 

    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan kubah Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan tipe AzureVM, nama "V2VM", dan menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam memicu Pemulihan Lokasi Alternatif (ALR) untuk membuat VM baru dalam grup sumber daya Target_RG sesuai input yang ditentukan oleh parameter TargetVMName, TargetVNetName, TargetVNetResourceGroup, TargetSubnetName. Alternatifnya, jika pengguna ingin melakukan pemulihan di tempat ke VM yang awalnya dicadangkan di lokasi asli, itu bisa dilakukan dengan perintah terakhir. Harap **hindari** penggunaan parameter TargetResourceGroupName, RestoreAsUnmanagedDisks, TargetVMName, TargetVNetName, TargetVNetResourceGroup, TargetSubnetName untuk menjalankan OLR.

### Contoh 3: Memulihkan disk yang ditentukan dari disk tercadangkan Azure VM dari titik pemulihan tertentu

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
PS C:\> $StartDate = (Get-Date).AddDays(-7)
PS C:\> $EndDate = Get-Date
PS C:\> $RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
PS C:\> $restoreDiskLUNs = ("0", "1")
PS C:\> $RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -TargetResourceGroupName "Target_RG" -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -RestoreDiskList $restoreDiskLUNs -VaultId $vault.ID -VaultLocation $vault.Location
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan kubah Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan tipe AzureVM, nama "V2VM", dan menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam menyimpan daftar disk yang akan dipulihkan dalam variabel restoreDiskLUN.
Perintah terakhir memulihkan disk tertentu, dari LUN yang ditentukan, ke grup sumber daya target Target_RG, lalu menyediakan informasi konfigurasi VM dan templat penyebaran di akun penyimpanan DestAccount dalam grup sumber daya DestRG.

### Contoh 4: Memulihkan disk VM terkelola sebagai Disk yang tidak terkelola

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
PS C:\> $StartDate = (Get-Date).AddDays(-7)
PS C:\> $EndDate = Get-Date
PS C:\> $RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem[0] -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
PS C:\> $RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -RestoreAsUnmanagedDisks -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -VaultId $vault.ID -VaultLocation $vault.Location
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan kubah RecoveryServices dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan lalu menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam memulihkan diska sebagai disk yang tidak dikelola.

### Contoh 5: Memulihkan VM yang tidak dikelola sebagai Disk yang tidak dikelola menggunakan akun penyimpanan asli

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureVM -WorkloadType AzureVM -Name "UnManagedVM" -VaultId $vault.ID
PS C:\> $StartDate = (Get-Date).AddDays(-7)
PS C:\> $EndDate = Get-Date
PS C:\> $RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem[0] -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
PS C:\> $RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -UseOriginalStorageAccount -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -VaultId $vault.ID -VaultLocation $vault.Location
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan kubah RecoveryServices dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan lalu menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam memulihkan disk sebagai disk yang tidak dikelola ke akun penyimpanan aslinya

### Contoh 6: Memulihkan Beberapa file item AzureFileShare

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureStorage -WorkloadType AzureVM -VaultId $vault.ID -Name "fileshareitem"
PS C:\> $RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -VaultId $vault.ID
PS C:\> $files = ("file1.txt", "file2.txt")
PS C:\> $RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -MultipleSourceFilePath $files -SourceFileType File -ResolveConflict Overwrite -VaultId $vault.ID -VaultLocation $vault.Location
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    fileshareitem   Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan kubah Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan bernama fileshareitem lalu menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan daftar titik pemulihan untuk item cadangan tertentu.
Perintah keempat menentukan file mana yang akan dipulihkan dan disimpan dalam variabel $files.
Perintah terakhir memulihkan file yang ditentukan ke lokasi aslinya.

### Contoh 7: Memulihkan SQL DB dalam Azure VM ke VM target lain untuk titik pemulihan penuh yang berbeda

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureWorkload -WorkloadType MSSQL -VaultId $vault.ID -Name "MSSQLSERVER;model"
PS C:\> $StartDate = (Get-Date).AddDays(-7)
PS C:\> $EndDate = Get-Date
PS C:\> $FullRP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
PS C:\> $TargetInstance = Get-AzRecoveryServicesBackupProtectableItem -WorkloadType MSSQL -ItemType SQLInstance -Name "<SQLInstance Name>" -ServerName "<SQL VM name>" -VaultId $vault.ID
PS C:\> $AnotherInstanceWithFullConfig = Get-AzRecoveryServicesBackupWorkloadRecoveryConfig -RecoveryPoint $FullRP -TargetItem $TargetInstance -AlternateWorkloadRestore -VaultId $vault.ID
PS C:\> Restore-AzRecoveryServicesBackupItem -WLRecoveryConfig $AnotherInstanceWithLogConfig -VaultId $vault.ID
    WorkloadName       Operation        Status            StartTime                 EndTime          JobID
    ------------       ---------        ------            ---------                 -------          -----
    MSSQLSERVER/m...   Restore          InProgress        3/17/2019 10:02:45 AM                      3274xg2b-e4fg-5952-89b4-8cb566gc1748
```

### Contoh 8: Memulihkan SQL DB dalam Azure VM ke VM target lain untuk titik pemulihan log

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureWorkload -WorkloadType MSSQL -VaultId $vault.ID -Name "MSSQLSERVER;model"
PS C:\> $PointInTime = Get-Date -Date "2019-03-20 01:00:00Z"
PS C:\> $TargetInstance = Get-AzRecoveryServicesBackupProtectableItem -WorkloadType MSSQL -ItemType SQLInstance -Name "<SQLInstance Name>" -ServerName "<SQL VM name>" -VaultId $vault.ID
PS C:\> $AnotherInstanceWithLogConfig = Get-AzRecoveryServicesBackupWorkloadRecoveryConfig -PointInTime $PointInTime -Item $BackupItem -AlternateWorkloadRestore -VaultId $vault.ID
PS C:\> Restore-AzRecoveryServicesBackupItem -WLRecoveryConfig $AnotherInstanceWithLogConfig -VaultId $vault.ID
    WorkloadName     Operation      Status           StartTime                 EndTime           JobID
    ------------     ---------      ------           ---------                 -------           -----
    MSSQLSERVER/m... Restore        InProgress       3/17/2019 10:02:45 AM                       3274xg2b-e4fg-5952-89b4-8cb566gc1748
```

### Contoh 9: Pemulihan Rehidrat untuk IaasVM dari titik pemulihan yang diarsipkan

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $item = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureVM -WorkloadType AzureVM -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -StartDate (Get-Date).AddDays(-29).ToUniversalTime() -EndDate (Get-Date).AddDays(0).ToUniversalTime() -VaultId $vault.ID -Item $item[3] -Tier VaultArchive
PS C:\> $restoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $rp[0] -RehydratePriority "Standard" -RehydrateDuration "13" -TargetResourceGroupName "Target_RG" -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -RestoreDiskList $restoreDiskLUNs -VaultId $vault.ID -VaultLocation $vault.Location
```

Di sini kami memfilter titik pemulihan yang ada dalam tingkat VaultArchive dan memicu pemulihan dengan prioritas rehidrasi dan durasi rehidrasi.

## PARAMETERS

### -DefaultProfile

Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskEncryptionSetId

ID DES untuk mengenkripsi disk yang dipulihkan.

```yaml
Type: System.String
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultipleSourceFilePath
Digunakan untuk Pemulihan beberapa file dari berbagi file. Jalur item yang akan dipulihkan di dalam berbagi file.

```yaml
Type: System.String[]
Parameter Sets: AzureFileShareParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPoint

Menentukan titik pemulihan untuk memulihkan item cadangan.
Untuk mendapatkan cmdlet **AzureRmRecoveryServicesBackupRecoveryPoint** , gunakan cmdlet **Get-AzRecoveryServicesBackupRecoveryPoint** .

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureFileShareParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureManagedVMCreateNewParameterSet, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RehydrateDuration

Durasi dalam hari untuk mempertahankan titik pemulihan yang diarsipkan direhidrasi. Nilai dapat berkisar dari 10 hingga 30 hari, nilai default adalah 15 hari.

```yaml
Type: System.String
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureManagedVMCreateNewParameterSet, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged, AzureWorkloadParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RehydratePriority

Prioritas rehidrasi untuk titik pemulihan yang diarsipkan selagi memicu pemulihan. Nilai yang dapat diterima adalah Standar, Tinggi.

```yaml
Type: System.String
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureManagedVMCreateNewParameterSet, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged, AzureWorkloadParameterSet
Aliases:
Accepted values: Standard, High

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResolveConflict

Jika item yang dipulihkan juga ada di tujuan, gunakan ini untuk menunjukkan apakah akan menimpa atau tidak.
Nilai yang dapat diterima untuk parameter ini adalah:

- Menimpa
- Melewatkan

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RestoreFSResolveConflictOption
Parameter Sets: AzureFileShareParameterSet
Aliases:
Accepted values: Overwrite, Skip

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreAsManagedDisk
Gunakan sakelar ini untuk menentukan untuk memulihkan sebagai disk terkelola.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreAsUnmanagedDisks
Gunakan sakelar ini untuk menentukan untuk memulihkan sebagai disk yang tidak dikelola

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureVMRestoreManagedAsUnmanaged
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreDiskList
Tentukan disk mana yang akan dipulihkan dari VM yang dicadangkan

```yaml
Type: System.String[]
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureManagedVMCreateNewParameterSet, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreOnlyOSDisk
Gunakan sakelar ini untuk memulihkan hanya disk OS dari VM yang dicadangkan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureManagedVMCreateNewParameterSet, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreToSecondaryRegion

Gunakan sakelar ini untuk memicu pemulihan Kawasan silang ke kawasan sekunder.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceFilePath

Digunakan untuk pemulihan item tertentu dari berbagi file. Jalur item yang akan dipulihkan dalam berbagi file.

```yaml
Type: System.String
Parameter Sets: AzureFileShareParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceFileType

Digunakan untuk pemulihan item tertentu dari berbagi file. Tipe item yang akan dipulihkan dalam berbagi file.
Nilai yang dapat diterima untuk parameter ini adalah:

- File
- Direktori

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SourceFileType]
Parameter Sets: AzureFileShareParameterSet
Aliases:
Accepted values: File, Directory

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName

Menentukan nama akun Storage target dalam langganan Anda.
Sebagai bagian dari proses pemulihan, cmdlet ini menyimpan disk dan informasi konfigurasi dalam akun Storage ini.

```yaml
Type: System.String
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureManagedVMCreateNewParameterSet, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountResourceGroupName

Menentukan nama grup sumber daya yang berisi akun Storage target dalam langganan Anda.
Sebagai bagian dari proses pemulihan, cmdlet ini menyimpan disk dan informasi konfigurasi dalam akun Storage ini.

```yaml
Type: System.String
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureManagedVMCreateNewParameterSet, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetFileShareName

Berbagi File tempat berbagi file harus dipulihkan.

```yaml
Type: System.String
Parameter Sets: AzureFileShareParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetFolder

Folder tempat berbagi file harus dipulihkan ke dalam TargetFileShareName. Jika konten yang dicadangkan akan dipulihkan ke folder akar, berikan nilai folder target sebagai string kosong.

```yaml
Type: System.String
Parameter Sets: AzureFileShareParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceGroupName

Grup sumber daya tempat disk terkelola dipulihkan. Berlaku untuk pencadangan VM dengan disk terkelola

```yaml
Type: System.String
Parameter Sets: AzureManagedVMCreateNewParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetStorageAccountName

Akun penyimpanan tempat berbagi file harus dipulihkan.

```yaml
Type: System.String
Parameter Sets: AzureFileShareParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetSubnetName
Nama subnet tempat VM target harus dibuat, dalam kasus Pemulihan Lokasi Alternatif ke VM baru

```yaml
Type: System.String
Parameter Sets: AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetVMName
Nama VM tempat data harus dipulihkan, dalam kasus Pemulihan Lokasi Alternatif ke VM baru

```yaml
Type: System.String
Parameter Sets: AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetVNetName
Nama VNet tempat VM target harus dibuat, dalam kasus Pemulihan Lokasi Alternatif ke VM baru

```yaml
Type: System.String
Parameter Sets: AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetVNetResourceGroup
Nama grup sumber daya yang berisi target VNet, dalam kasus Pemulihan Lokasi Alternatif ke VM baru

```yaml
Type: System.String
Parameter Sets: AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetZoneNumber

Nomor zona ketersediaan target tempat disk yang dipulihkan disematkan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseOriginalStorageAccount

Gunakan sakelar ini jika disk dari titik pemulihan akan dipulihkan ke akun penyimpanan aslinya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureVMUnManagedDiskParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentityId
UserAssigned Identity Id untuk memicu pemulihan berbasis MSI dengan UserAssigned Identity

```yaml
Type: System.String
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSystemAssignedIdentity
Gunakan sakelar ini untuk memicu pemulihan berbasis MSI dengan SystemAssigned Identity

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureManagedVMReplaceExistingParameterSet, AzureManagedVMCreateNewParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultId

ARM ID dari Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VaultLocation

Lokasi Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WLRecoveryConfig

Konfigurasi pemulihan

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryConfigBase
Parameter Sets: AzureWorkloadParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi

Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. 

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## CATATAN

## RELATED LINKS

[Backup-AzRecoveryServicesBackupItem](./Backup-AzRecoveryServicesBackupItem.md)

[Get-AzRecoveryServicesBackupItem](./Get-AzRecoveryServicesBackupItem.md)

[Get-AzRecoveryServicesBackupRecoveryPoint](./Get-AzRecoveryServicesBackupRecoveryPoint.md)
