---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: F49FA524-28BC-464F-BD0A-F898E99C83D8
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/restore-azrecoveryservicesbackupitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Restore-AzRecoveryServicesBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Restore-AzRecoveryServicesBackupItem.md
ms.openlocfilehash: 8be59662976d26c12d4781f7d536b9abff8bcb34
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144223799"
---
# Restore-AzRecoveryServicesBackupItem

## SYNOPSIS

Memulihkan data dan konfigurasi untuk item Cadangan ke titik pemulihan yang ditentukan. Parameter yang diperlukan bervariasi menurut jenis item cadangan.
Perintah yang sama digunakan untuk memulihkan komputer Virtual Azure, database yang berjalan dalam komputer Virtual Azure dan berbagi file Azure juga.

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

**Untuk pencadangan Azure VM**

Anda dapat mencadangkan komputer virtual Azure dan memulihkan disk (baik terkelola maupun tidak terkelola) menggunakan perintah ini. Operasi pemulihan tidak memulihkan komputer virtual penuh.
Jika ini adalah VM disk terkelola, grup Sumber Daya target harus ditentukan di mana disk yang dipulihkan disimpan. Ketika grup sumber daya target ditentukan, jika rekam jepret ada dalam grup sumber daya yang ditentukan dalam kebijakan pencadangan, operasi pemulihan akan instan dan disk dibuat dari rekam jepret lokal dan disimpan dalam grup sumber daya target. Ada juga opsi untuk memulihkannya sebagai disk yang tidak dikelola tetapi ini akan memanfaatkan data yang ada di vault layanan pemulihan Azure dan karenanya akan jauh lebih lambat. Konfigurasi VM dan templat penyebaran yang dapat digunakan untuk membuat VM dari disk yang dipulihkan akan diunduh ke akun penyimpanan yang ditentukan.
Jika ini adalah VM disk yang tidak dikelola, rekam jepret ada di akun penyimpanan asli disk dan/atau di vault layanan pemulihan. Jika pengguna memberikan opsi untuk menggunakan Akun penyimpanan asli untuk memulihkan, pemulihan instan dapat disediakan. Jika tidak, data diambil dari vault dan disk layanan Azure Recovery dibuat di akun penyimpanan tertentu bersama dengan konfigurasi VM dan templat penyebaran.

> [!IMPORTANT]
> Secara default, cadangan Azure VM mencadangkan semua disk. Anda dapat secara selektif mencadangkan disk yang relevan menggunakan parameter exclusionList atau InclusionList selama Enable-Backup. Opsi untuk memulihkan disk secara selektif hanya tersedia jika satu disk telah secara selektif mencadangkannya.

Silakan lihat berbagai kemungkinan set parameter dan teks parameter untuk informasi lebih lanjut.

> [!NOTE]
> Jika parameter -VaultId digunakan maka parameter -VaultLocation juga harus digunakan.

**Untuk pencadangan berbagi File Azure**

Anda dapat memulihkan seluruh berbagi file atau file/beberapa file/folder tertentu pada berbagi. Anda dapat memulihkan ke lokasi asli atau ke lokasi alternatif.

**Untuk Beban Kerja Azure**

Anda dapat memulihkan SQL DB dalam Azure VM

## EXAMPLES

### Contoh 1: Memulihkan disk Azure VM Disk terkelola yang dicadangkan dari titik pemulihan tertentu

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
$StartDate = (Get-Date).AddDays(-7)
$EndDate = Get-Date
$RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
$RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -TargetResourceGroupName "Target_RG" -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -VaultId $vault.ID -VaultLocation $vault.Location
```

```output
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan vault Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan jenis AzureVM, dari nama "V2VM", dan menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah terakhir memulihkan semua disk ke grup Sumber Daya target Target_RG, lalu menyediakan informasi konfigurasi VM dan templat penyebaran di akun penyimpanan DestAccount di grup sumber daya DestRG.

### Contoh 2: Memulihkan AzureVM Terkelola dari titik pemulihan tertentu ke lokasi asli/alternatif 

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
$StartDate = (Get-Date).AddDays(-7)
$EndDate = Get-Date
$RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
$AlternateLocationRestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -TargetResourceGroupName "Target_RG" -StorageAccountName "DestStorageAccount" -StorageAccountResourceGroupName "DestStorageAccRG" -TargetVMName "TagetVirtualMachineName" -TargetVNetName "Target_VNet" -TargetVNetResourceGroup "" -TargetSubnetName "subnetName" -VaultId $vault.ID -VaultLocation $vault.Location 
$OriginalLocationRestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -StorageAccountName "DestStorageAccount" -StorageAccountResourceGroupName "DestStorageAccRG" -VaultId $vault.ID -VaultLocation $vault.Location 
```

```output
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan vault Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan jenis AzureVM, dari nama "V2VM", dan menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam memicu Alternate Location Restore (ALR) untuk membuat VM baru di grup sumber daya Target_RG sesuai input yang ditentukan oleh parameter TargetVMName, TargetVNetName, TargetVNetResourceGroup, TargetSubnetName. Secara bergantian, jika pengguna ingin melakukan pemulihan di tempat ke VM yang awalnya dicadangkan di lokasi asli, itu dapat dilakukan dengan perintah terakhir. **Hindari** menggunakan parameter TargetResourceGroupName, RestoreAsUnmanagedDisks, TargetVMName, TargetVNetName, TargetVNetResourceGroup, TargetSubnetName untuk melakukan Original Location Restore (OLR).

### Contoh 3: Memulihkan disk yang ditentukan dari Disk terkelola yang dicadangkan Azure VM dari titik pemulihan tertentu

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
$StartDate = (Get-Date).AddDays(-7)
$EndDate = Get-Date
$RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
$restoreDiskLUNs = ("0", "1")
$RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -TargetResourceGroupName "Target_RG" -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -RestoreDiskList $restoreDiskLUNs -VaultId $vault.ID -VaultLocation $vault.Location
```

```output
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan vault Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Cadangan jenis AzureVM, dari nama "V2VM", dan menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam menyimpan daftar disk yang akan dipulihkan dalam variabel restoreDiskLUN.
Perintah terakhir memulihkan disk yang diberikan, dari LUN yang ditentukan, ke grup Sumber Daya target Target_RG, lalu menyediakan informasi konfigurasi VM dan templat penyebaran di akun penyimpanan DestAccount di grup sumber daya DestRG.

### Contoh 4: Memulihkan disk VM terkelola sebagai Disk tidak terkelola

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -Name "V2VM" -VaultId $vault.ID
$StartDate = (Get-Date).AddDays(-7)
$EndDate = Get-Date
$RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem[0] -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
$RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -RestoreAsUnmanagedDisks -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -VaultId $vault.ID -VaultLocation $vault.Location
```

```output
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan vault RecoveryServices dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Backup lalu menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam memulihkan disk sebagai disk yang tidak dikelola.

### Contoh 5: Memulihkan VM yang tidak dikelola sebagai Disk yang tidak dikelola menggunakan akun penyimpanan asli

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureVM -WorkloadType AzureVM -Name "UnManagedVM" -VaultId $vault.ID
$StartDate = (Get-Date).AddDays(-7)
$EndDate = Get-Date
$RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem[0] -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
$RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -UseOriginalStorageAccount -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -VaultId $vault.ID -VaultLocation $vault.Location
```

```output
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    V2VM            Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan vault RecoveryServices dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Backup lalu menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam variabel $StartDate.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam variabel $EndDate.
Perintah kelima mendapatkan daftar titik pemulihan untuk item cadangan tertentu yang difilter menurut $StartDate dan $EndDate.
Perintah keenam memulihkan disk sebagai disk yang tidak dikelola ke akun penyimpanan aslinya

### Contoh 6: Memulihkan Beberapa file item AzureFileShare

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureStorage -WorkloadType AzureVM -VaultId $vault.ID -Name "fileshareitem"
$RP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -VaultId $vault.ID
$files = ("file1.txt", "file2.txt")
$RestoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $RP[0] -MultipleSourceFilePath $files -SourceFileType File -ResolveConflict Overwrite -VaultId $vault.ID -VaultLocation $vault.Location
```

```output
    WorkloadName    Operation       Status          StartTime              EndTime
    ------------    ---------       ------          ---------              -------
    fileshareitem   Restore         InProgress      26-Apr-16 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan vault Layanan Pemulihan dan menyimpannya dalam variabel $vault.
Perintah kedua mendapatkan item Backup bernama fileshareitem dan kemudian menyimpannya dalam variabel $BackupItem.
Perintah ketiga mendapatkan daftar titik pemulihan untuk item cadangan tertentu.
Perintah keempat menentukan file mana yang akan dipulihkan dan menyimpannya dalam variabel $files.
Perintah terakhir memulihkan file yang ditentukan ke lokasi aslinya.

### Contoh 7: Memulihkan SQL DB dalam Azure VM ke VM target lain untuk titik pemulihan penuh yang berbeda

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureWorkload -WorkloadType MSSQL -VaultId $vault.ID -Name "MSSQLSERVER;model"
$StartDate = (Get-Date).AddDays(-7)
$EndDate = Get-Date
$FullRP = Get-AzRecoveryServicesBackupRecoveryPoint -Item $BackupItem -StartDate $StartDate.ToUniversalTime() -EndDate $EndDate.ToUniversalTime() -VaultId $vault.ID
$TargetInstance = Get-AzRecoveryServicesBackupProtectableItem -WorkloadType MSSQL -ItemType SQLInstance -Name "<SQLInstance Name>" -ServerName "<SQL VM name>" -VaultId $vault.ID
$AnotherInstanceWithFullConfig = Get-AzRecoveryServicesBackupWorkloadRecoveryConfig -RecoveryPoint $FullRP -TargetItem $TargetInstance -AlternateWorkloadRestore -VaultId $vault.ID
Restore-AzRecoveryServicesBackupItem -WLRecoveryConfig $AnotherInstanceWithLogConfig -VaultId $vault.ID
```

```output
    WorkloadName       Operation        Status            StartTime                 EndTime          JobID
    ------------       ---------        ------            ---------                 -------          -----
    MSSQLSERVER/m...   Restore          InProgress        3/17/2019 10:02:45 AM                      3274xg2b-e4fg-5952-89b4-8cb566gc1748
```

### Contoh 8: Memulihkan SQL DB dalam Azure VM ke VM target lain untuk titik pemulihan log

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$BackupItem = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureWorkload -WorkloadType MSSQL -VaultId $vault.ID -Name "MSSQLSERVER;model"
$PointInTime = Get-Date -Date "2019-03-20 01:00:00Z"
$TargetInstance = Get-AzRecoveryServicesBackupProtectableItem -WorkloadType MSSQL -ItemType SQLInstance -Name "<SQLInstance Name>" -ServerName "<SQL VM name>" -VaultId $vault.ID
$AnotherInstanceWithLogConfig = Get-AzRecoveryServicesBackupWorkloadRecoveryConfig -PointInTime $PointInTime -Item $BackupItem -AlternateWorkloadRestore -VaultId $vault.ID
Restore-AzRecoveryServicesBackupItem -WLRecoveryConfig $AnotherInstanceWithLogConfig -VaultId $vault.ID
```

```output
    WorkloadName     Operation      Status           StartTime                 EndTime           JobID
    ------------     ---------      ------           ---------                 -------           -----
    MSSQLSERVER/m... Restore        InProgress       3/17/2019 10:02:45 AM                       3274xg2b-e4fg-5952-89b4-8cb566gc1748
```

### Contoh 9: Pemulihan Rehidrasi untuk IaasVM dari titik pemulihan yang diarsipkan

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$item = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureVM -WorkloadType AzureVM -VaultId $vault.ID
$rp = Get-AzRecoveryServicesBackupRecoveryPoint -StartDate (Get-Date).AddDays(-29).ToUniversalTime() -EndDate (Get-Date).AddDays(0).ToUniversalTime() -VaultId $vault.ID -Item $item[3] -Tier VaultArchive
$restoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $rp[0] -RehydratePriority "Standard" -RehydrateDuration "13" -TargetResourceGroupName "Target_RG" -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -RestoreDiskList $restoreDiskLUNs -VaultId $vault.ID -VaultLocation $vault.Location
```

Di sini kami memfilter titik pemulihan yang ada di tingkat VaultArchive dan memicu pemulihan dengan prioritas rehidrasi dan durasi rehidrasi.

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
Digunakan untuk Pemulihan beberapa file dari berbagi file. Jalur item yang akan dipulihkan dalam berbagi file.

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
Untuk mendapatkan objek **AzureRmRecoveryServicesBackupRecoveryPoint** , gunakan cmdlet **Get-AzRecoveryServicesBackupRecoveryPoint** .

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

Durasi dalam hari untuk menjaga titik pemulihan yang diarsipkan direhidrasi. Nilai dapat berkisar dari 10 hingga 30 hari, nilai default adalah 15 hari.

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

Prioritas rehidrasi untuk titik pemulihan yang diarsipkan saat memicu pemulihan. Nilai yang dapat diterima adalah Standar, Tinggi.

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

- Timpa
- Lewati

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
Gunakan sakelar ini untuk menentukan untuk memulihkan sebagai disk yang tidak terkelola

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

Gunakan sakelar ini untuk memicu pemulihan Lintas wilayah ke wilayah sekunder.

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

Menentukan nama akun Storage target di langganan Anda.
Sebagai bagian dari proses pemulihan, cmdlet ini menyimpan disk dan informasi konfigurasi di akun Storage ini.

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

Menentukan nama grup sumber daya yang berisi akun Storage target di langganan Anda.
Sebagai bagian dari proses pemulihan, cmdlet ini menyimpan disk dan informasi konfigurasi di akun Storage ini.

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

Folder tempat berbagi file harus dipulihkan dalam TargetFileShareName. Jika konten yang dicadangkan akan dipulihkan ke folder akar, berikan nilai folder target sebagai string kosong.

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
Nama subnet tempat VM target harus dibuat, dalam kasus pemulihan Lokasi Alternatif ke VM baru

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
Nama VM tempat data harus dipulihkan, dalam kasus pemulihan Lokasi Alternatif ke VM baru

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
Nama VNet tempat VM target harus dibuat, dalam kasus pemulihan Lokasi Alternatif ke VM baru

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
Nama grup sumber daya yang berisi VNet target, dalam kasus pemulihan Lokasi Alternatif ke VM baru

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
Id Identitas UserAssigned untuk memicu pemulihan berbasis MSI dengan UserAssigned Identity

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
Gunakan switch ini untuk memicu pemulihan berbasis MSI dengan SystemAssigned Identity

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

ID ARM dari Vault Layanan Pemulihan.

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

### -Confirm

Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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

Menunjukkan yang akan terjadi jika cmdlet dijalankan. 

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## NOTES

## RELATED LINKS

[Backup-AzRecoveryServicesBackupItem](./Backup-AzRecoveryServicesBackupItem.md)

[Get-AzRecoveryServicesBackupItem](./Get-AzRecoveryServicesBackupItem.md)

[Get-AzRecoveryServicesBackupRecoveryPoint](./Get-AzRecoveryServicesBackupRecoveryPoint.md)
