---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 838026E4-F001-434C-86F0-B2A838E93A9C
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecoverypoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryPoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryPoint.md
ms.openlocfilehash: 658dc09d58b74fab4988047f9f154963f85ad396
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142318019"
---
# Get-AzRecoveryServicesBackupRecoveryPoint

## SYNOPSIS

Mendapatkan titik pemulihan untuk item yang dicadangkan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecoverypoint) untuk informasi terbaru.

## SYNTAX

### NoFilterParameterSet (Default)
```
Get-AzRecoveryServicesBackupRecoveryPoint [-Item] <ItemBase> [-UseSecondaryRegion] [-Tier <RecoveryPointTier>]
 [-IsReadyForMove <Boolean>] [-TargetTier <RecoveryPointTier>] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DateTimeFilter
```
Get-AzRecoveryServicesBackupRecoveryPoint [[-StartDate] <DateTime>] [[-EndDate] <DateTime>] [-Item] <ItemBase>
 [-UseSecondaryRegion] [-Tier <RecoveryPointTier>] [-IsReadyForMove <Boolean>]
 [-TargetTier <RecoveryPointTier>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### RecoveryPointId
```
Get-AzRecoveryServicesBackupRecoveryPoint [-Item] <ItemBase> [-RecoveryPointId] <String>
 [[-KeyFileDownloadLocation] <String>] [-UseSecondaryRegion] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesBackupRecoveryPoint** mendapatkan poin pemulihan untuk item Azure Backup yang dicadangkan.
Setelah item dicadangkan, objek **AzureRmRecoveryServicesBackupRecoveryPoint** memiliki satu atau beberapa titik pemulihan.
Mengatur konteks kubah menggunakan parameter -VaultId.

## EXAMPLES

### Contoh 1: Dapatkan poin pemulihan dari minggu lalu untuk item

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $startDate = (Get-Date).AddDays(-7)
PS C:\> $endDate = Get-Date
PS C:\> $container = Get-AzRecoveryServicesBackupContainer -ContainerType AzureVM -Status Registered -Name "V2VM" -VaultId $vault.ID
PS C:\> $backupItem = Get-AzRecoveryServicesBackupItem -ContainerType AzureVM -WorkloadType AzureVM -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -Item $backupItem -StartDate $startdate.ToUniversalTime() -EndDate $enddate.ToUniversalTime() -VaultId $vault.ID
```

Perintah pertama mendapatkan objek kubah berdasarkan vaultName. Perintah kedua mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam variabel $startDate.
Perintah ketiga mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $endDate.
Perintah keempat mendapatkan wadah cadangan AzureVM, dan menyimpannya dalam variabel $Container. Perintah kelima mendapatkan item cadangan berdasarkan workloadType, vaultId lalu menyimpannya dalam variabel $backupItem.
Perintah terakhir mendapatkan array titik pemulihan untuk item dalam $BackupItem, lalu menyimpannya dalam variabel $rp.

### Contoh 2: Dapatkan titik pemulihan yang siap dipindahkan ke VaultArchive

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $startDate = (Get-Date).AddDays(-7).ToUniversalTime()
PS C:\> $endDate = Get-Date.ToUniversalTime()
PS C:\> $item = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -StartDate $startDate -EndDate $endDate -VaultId $vault.ID -Item $item[3] 
-IsReadyForMove $true -TargetTier VaultArchive
```

Perintah pertama mendapatkan objek kubah berdasarkan vaultName. Perintah kedua mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam variabel $startDate.
Perintah ketiga mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $endDate.
Perintah keempat mendapatkan item cadangan berdasarkan backupManagementType dan workloadType, vaultId lalu menyimpannya dalam variabel $item.
Perintah terakhir mendapatkan array titik pemulihan untuk item dalam $backupItem yang siap dipindahkan ke tingkat VaultArchive lalu menyimpannya dalam variabel $rp.

### Contoh 3: Dapatkan poin pemulihan di tingkat tertentu

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $startDate = (Get-Date).AddDays(-7).ToUniversalTime()
PS C:\> $endDate = Get-Date.ToUniversalTime()
PS C:\> $item = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -StartDate $startDate -EndDate $endDate -VaultId $vault.ID -Item $item[3] 
-Tier VaultStandard
```

Perintah pertama mendapatkan objek kubah berdasarkan vaultName. Perintah kedua mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam variabel $startDate.
Perintah ketiga mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $endDate.
Perintah keempat mendapatkan item cadangan berdasarkan backupManagementType dan workloadType, vaultId lalu menyimpannya dalam variabel $item.
Perintah terakhir mendapatkan array titik pemulihan untuk item dalam $backupItem yang siap dipindahkan ke tingkat VaultArchive lalu menyimpannya dalam variabel $rp. 

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

### -EndDate

Menentukan akhir rentang tanggal.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: DateTimeFilter
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadyForMove

Memfilter Titik Pemulihan berdasarkan apakah RP Siap untuk berpindah ke tingkat target. Gunakan ini bersama dengan parameter tingkat target.

```yaml
Type: System.Boolean
Parameter Sets: NoFilterParameterSet, DateTimeFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Item

Menentukan item di mana cmdlet ini mendapatkan titik pemulihan.
Untuk mendapatkan objek **AzureRmRecoveryServicesBackupItem** , gunakan cmdlet **Get-AzRecoveryServicesBackupItem** .

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyFileDownloadLocation

Menentukan lokasi untuk mengunduh file input untuk memulihkan kunci KeyVault untuk mesin virtual terenkripsi.

```yaml
Type: System.String
Parameter Sets: RecoveryPointId
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPointId

Menentukan ID titik pemulihan.

```yaml
Type: System.String
Parameter Sets: RecoveryPointId
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartDate

Menentukan awal rentang tanggal.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: DateTimeFilter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetTier

Tingkat target untuk memeriksa kesiapan pemindahan titik pemulihan. Saat ini hanya nilai yang valid adalah 'VaultArchive'.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointTier
Parameter Sets: NoFilterParameterSet, DateTimeFilter
Aliases:
Accepted values: VaultArchive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tingkat

Memfilter titik pemulihan berdasarkan nilai tingkat.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointTier
Parameter Sets: NoFilterParameterSet, DateTimeFilter
Aliases:
Accepted values: VaultStandard, Snapshot, VaultArchive, VaultStandardRehydrated, SnapshotAndVaultStandard, SnapshotAndVaultArchive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSecondaryRegion
Filter dari Kawasan Sekunder untuk Pemulihan Lintas Kawasan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesBackupContainer](./Get-AzRecoveryServicesBackupContainer.md)

[Get-AzRecoveryServicesBackupItem](./Get-AzRecoveryServicesBackupItem.md)
