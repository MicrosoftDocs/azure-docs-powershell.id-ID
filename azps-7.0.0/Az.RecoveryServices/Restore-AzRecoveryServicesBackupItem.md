---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: F49FA524-28BC-464F-BD0A-F898E99C83D8
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/restore-azrecoveryservicesbackupitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Restore-AzRecoveryServicesBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Restore-AzRecoveryServicesBackupItem.md
ms.openlocfilehash: e988c1ee3548a36cbf580acb5bb7702411ff2526
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136536944"
---
# Restore-AzRecoveryServicesBackupItem

## SYNOPSIS

Memulihkan data dan konfigurasi untuk item Cadangan ke titik pemulihan yang ditentukan. Parameter yang diperlukan bervariasi dengan tipe item cadangan.
Perintah yang sama digunakan untuk memulihkan mesin Azure Virtual, database yang berjalan dalam komputer Azure Virtual dan berbagi file Azure juga.

## SYNTAX

### AzureVMManagedDiskParameterSet (Default)
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 [-StorageAccountName] <String> [-StorageAccountResourceGroupName] <String> [-TargetResourceGroupName] <String>
 [-RestoreOnlyOSDisk] [-RestoreDiskList <String[]>] [-DiskEncryptionSetId <String>] [-RestoreToSecondaryRegion]
 [-TargetZoneNumber <Int32>] [-RehydratePriority <String>] [-UseSystemAssignedIdentity]
 [-UserAssignedIdentityId <String>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [-RehydrateDuration <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureVMParameterSet
```
Restore-AzRecoveryServicesBackupItem [-VaultLocation <String>] [-RecoveryPoint] <RecoveryPointBase>
 [-StorageAccountName] <String> [-StorageAccountResourceGroupName] <String> [-RestoreOnlyOSDisk]
 [-RestoreDiskList <String[]>] [-DiskEncryptionSetId <String>] [-RestoreToSecondaryRegion]
 [-TargetZoneNumber <Int32>] [-RehydratePriority <String>] [-VaultId <String>]
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

Cmdlet **Restore-AzRecoveryServicesBackupItem** memulihkan data dan konfigurasi untuk item Azure Backup ke titik pemulihan yang ditentukan.

**Untuk pencadangan Azure VM**

Anda dapat mencadangkan mesin virtual Azure dan memulihkan disk (terkelola maupun tidak dikelola) menggunakan perintah ini. Operasi pemulihan tidak memulihkan mesin virtual penuh.
Jika merupakan vm disk terkelola, grup Sumber Daya target harus ditentukan tempat disk yang dipulihkan disimpan. Saat grup sumber daya target ditentukan, jika snapshot ada dalam grup sumber daya yang ditentukan dalam kebijakan cadangan, operasi pemulihan akan instan dan disk dibuat dari snapshot lokal dan disimpan dalam grup sumber daya target. Ada juga opsi untuk memulihkannya sebagai disk tak terkelola tapi ini akan memanfaatkan data yang ada di penyimpanan layanan pemulihan Azure sehingga akan jauh lebih lambat. Konfigurasi VM dan templat penyebaran yang dapat digunakan untuk membuat VM dari disk yang dipulihkan akan diunduh ke akun penyimpanan yang ditentukan.
Jika ini adalah VM disk yang tidak dikelola, snapshot ada dalam akun penyimpanan asli disk dan/atau dalam vault layanan pemulihan. Jika pengguna memberikan opsi untuk menggunakan Akun penyimpanan asli untuk memulihkan, pemulihan instan dapat disediakan. Jika tidak, data diambil dari disk dan vault layanan Pemulihan Azure dibuat dalam akun penyimpanan tertentu bersama dengan konfigurasi VM dan templat penyebaran.

> [!IMPORTANT]
> Secara default, pencadangan Azure VM mencadangkan semua disk. Anda dapat secara selektif mencadangkan disk yang relevan menggunakan parameter exclusionList atau InclusionList selama Enable-Backup. Opsi untuk memulihkan disk secara selektif hanya tersedia jika disk telah secara selektif mencadangkannya.

Silakan merujuk ke kumpulan parameter dan teks parameter yang berbeda untuk informasi selengkapnya.

> [!NOTE]
> Jika parameter -VaultId digunakan, parameter -VaultLocation juga harus digunakan.

**Untuk cadangan berbagi File Azure**

Anda bisa memulihkan seluruh file yang dibagikan atau file/beberapa file/folder tertentu di berbagi. Anda bisa memulihkan ke lokasi asli atau ke lokasi alternatif.

**Untuk Beban Kerja Azure**

Anda bisa memulihkan SQL DB dalam VM Azure

## EXAMPLES

### Contoh 1: Memulihkan disk dari disk yang dicadangkan Azure VM dari titik pemulihan tertentu

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

Perintah pertama mendapatkan vault Layanan Pemulihan dan menyimpannya $vault variabel.
Perintah kedua mendapatkan item Cadangan tipe AzureVM, nama "V2VM", dan menyimpannya di $BackupItem variabel.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam $StartDate variabel.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam $EndDate baru.
Perintah kelima mendapatkan daftar poin pemulihan untuk item cadangan tertentu yang difilter oleh tim $StartDate $EndDate.
Perintah terakhir memulihkan semua disk ke Target_RG grup Sumber Daya target, lalu menyediakan informasi konfigurasi VM dan templat penyebaran di DestAccount akun penyimpanan di grup sumber daya DestRG.

### Contoh 2: Memulihkan disk tertentu dari disk yang dikelola yang dicadangkan Azure VM dari titik pemulihan tertentu

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

Perintah pertama mendapatkan vault Layanan Pemulihan dan menyimpannya $vault variabel.
Perintah kedua mendapatkan item Cadangan tipe AzureVM, nama "V2VM", dan menyimpannya di $BackupItem variabel.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam $StartDate variabel.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam $EndDate baru.
Perintah kelima mendapatkan daftar poin pemulihan untuk item cadangan tertentu yang difilter oleh tim $StartDate $EndDate.
Perintah keenam menyimpan daftar disk yang akan dipulihkan dalam variabel restoreDiskLUN.
Perintah terakhir memulihkan disk tertentu, dari LUN yang ditentukan, ke grup Sumber Daya target Target_RG, lalu menyediakan informasi konfigurasi VM dan templat penyebaran dalam DestAccount akun penyimpanan di grup sumber daya DestRG.

### Contoh 3: Memulihkan disk dari VM yang dikelola sebagai Disk tak terkelola

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

Perintah pertama mendapatkan vault RecoveryServices dan menyimpannya dalam $vault baru.
Perintah kedua mendapatkan item Cadangan lalu menyimpannya dalam variabel $BackupItem Cadangkan.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam $StartDate variabel.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam $EndDate baru.
Perintah kelima mendapatkan daftar poin pemulihan untuk item cadangan tertentu yang difilter oleh tim $StartDate $EndDate.
Perintah keenam memulihkan disk sebagai disk yang tidak manajemen.

### Contoh 4: Pulihkan VM yang tidak manajemen sebagai Disk tak terageage menggunakan akun penyimpanan asli

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

Perintah pertama mendapatkan vault RecoveryServices dan menyimpannya dalam $vault baru.
Perintah kedua mendapatkan item Cadangan lalu menyimpannya dalam variabel $BackupItem Cadangkan.
Perintah ketiga mendapatkan tanggal dari tujuh hari sebelumnya, lalu menyimpannya dalam $StartDate variabel.
Perintah keempat mendapatkan tanggal saat ini, lalu menyimpannya dalam $EndDate baru.
Perintah kelima mendapatkan daftar poin pemulihan untuk item cadangan tertentu yang difilter oleh tim $StartDate $EndDate.
Perintah keenam memulihkan disk sebagai disk yang tidak dikelola ke akun penyimpanan aslinya

### Contoh 5: Pulihkan Beberapa file dari item AzureFileShare

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

Perintah pertama mendapatkan vault Layanan Pemulihan dan menyimpannya $vault variabel.
Perintah kedua mendapatkan item Cadangan bernama fileshareitem lalu menyimpannya di $BackupItem baru.
Perintah ketiga mendapatkan daftar poin pemulihan untuk item cadangan tertentu.
Perintah keempat menentukan file mana yang akan dipulihkan dan disimpan dalam $files baru.
Perintah terakhir memulihkan file tertentu ke lokasi aslinya.

### Contoh 6: Pulihkan SQL DB dalam Azure VM ke vm target lainnya untuk poin pemulihan penuh yang berbeda

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

### Contoh 7: Pulihkan SQL DB dalam Azure VM ke vm target lainnya untuk titik pemulihan log

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

### Contoh 8: Pemulihan Rehydrate untuk IaasVM dari titik pemulihan yang diarsipkan

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $item = Get-AzRecoveryServicesBackupItem -BackupManagementType AzureVM -WorkloadType AzureVM -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -StartDate (Get-Date).AddDays(-29).ToUniversalTime() -EndDate (Get-Date).AddDays(0).ToUniversalTime() -VaultId $vault.ID -Item $item[3] -Tier VaultArchive
PS C:\> $restoreJob = Restore-AzRecoveryServicesBackupItem -RecoveryPoint $rp[0] -RehydratePriority "Standard" -RehydrateDuration "13" -TargetResourceGroupName "Target_RG" -StorageAccountName "DestAccount" -StorageAccountResourceGroupName "DestRG" -RestoreDiskList $restoreDiskLUNs -VaultId $vault.ID -VaultLocation $vault.Location
```

Di sini, kami memfilter titik-titik pemulihan yang ada dalam tier VaultArchive dan memicu pemulihan dengan prioritas rehydration dan durasi rehydration.

## PARAMETERS

### -DefaultProfile

Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

DES ID untuk mengenkripsi disk yang dipulihkan.

```yaml
Type: System.String
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultipleSourceFilePath
Digunakan untuk Beberapa file dipulihkan dari berbagi file. Jalur item yang akan dipulihkan dalam berbagi file.

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
Untuk mendapatkan objek **AzureRmRecoveryServicesBackupRecoveryPoint,** gunakan cmdlet **Get-AzRecoveryServicesBackupRecoveryPoint.**

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet, AzureFileShareParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RehydrateDuration

Durasi dalam hari di mana untuk menjaga titik pemulihan yang diarsipkan diarsir ulang. Nilai dapat berkisar dari 10 hingga 30 hari, nilai default adalah 15 hari.

```yaml
Type: System.String
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged, AzureWorkloadParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RehydratePriority

Prioritas rehydrasi untuk titik pemulihan yang diarsipkan sembari memicu pemulihan. Nilai yang dapat diterima adalah Standar, Tinggi.

```yaml
Type: System.String
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged, AzureWorkloadParameterSet
Aliases:
Accepted values: Standard, High

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResolveConflict

Dalam kasus item yang dipulihkan juga ada di tujuan, gunakan ini untuk menunjukkan apakah akan menimpa atau tidak.
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
Use this switch to specify to restore as managed disks.

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
Gunakan sakelar ini untuk menentukan untuk memulihkan sebagai disk tidakage

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
Menentukan disk mana yang akan dipulihkan vm yang dicadangkan

```yaml
Type: System.String[]
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreOnlyOSDisk
Gunakan sakelar ini untuk memulihkan disk OS yang dicadangkan saja

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreToSecirisanRegion

Gunakan sakelar ini untuk memicu pemulihan Wilayah silang ke kawasan sekunder.

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

Menentukan nama target akun Storage langganan Anda.
Sebagai bagian dari proses pemulihan, cmdlet ini menyimpan disk dan informasi konfigurasi di akun Storage Anda.

```yaml
Type: System.String
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountResourceGroupName

Menentukan nama grup sumber daya yang berisi akun Storage target dalam langganan Anda.
Sebagai bagian dari proses pemulihan, cmdlet ini menyimpan disk dan informasi konfigurasi di akun Storage Anda.

```yaml
Type: System.String
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet, AzureVMRestoreManagedAsUnmanaged, AzureVMUnManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetFileShareName

Berbagi File tempat file bersama harus dipulihkan.

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

Folder tempat berbagi file harus dipulihkan dalam TargetFileShareName. Jika konten yang dicadangkan akan dipulihkan ke folder akar, beri nilai folder target sebagai string kosong.

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
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMRestoreUnmanagedAsManaged
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetStorageAccountName

Akun penyimpanan tempat file bersama harus dipulihkan.

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

### -TargetZoneNumber

Nomor zona ketersediaan target tempat disk yang dipulihkan disematkan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: AzureVMManagedDiskParameterSet, AzureVMParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseOriginalStorageAccount

Gunakan sakelar ini jika disk dari titik pemulihan harus dipulihkan ke akun penyimpanan aslinya.

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
Id Identitas yangSigned UserAssigned untuk memicu pemulihan berbasis MSI dengan UserAssigned Identity

```yaml
Type: System.String
Parameter Sets: AzureVMManagedDiskParameterSet
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
Parameter Sets: AzureVMManagedDiskParameterSet
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

### -Konfirmasi

Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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
