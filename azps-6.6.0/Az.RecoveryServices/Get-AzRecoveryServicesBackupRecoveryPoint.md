---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 838026E4-F001-434C-86F0-B2A838E93A9C
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecoverypoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryPoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryPoint.md
ms.openlocfilehash: 658dc09d58b74fab4988047f9f154963f85ad396
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140279257"
---
# Get-AzRecoveryServicesBackupRecoveryPoint

## SYNOPSIS

Dapatkan poin pemulihan untuk item yang dicadangkan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecoverypoint) untuk informasi terkini.

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

Cmdlet **Get-AzRecoveryServicesBackupRecoveryPoint** mendapatkan titik pemulihan untuk item Azure Backup yang dicadangkan.
Setelah item dicadangkan, objek **AzureRmRecoveryServicesBackupRecoveryPoint** memiliki satu atau beberapa titik pemulihan.
Mengatur konteks vault menggunakan parameter -VaultId.

## EXAMPLES

### Contoh 1: Dapatkan poin pemulihan dari minggu lalu untuk sebuah item

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $startDate = (Get-Date).AddDays(-7)
PS C:\> $endDate = Get-Date
PS C:\> $container = Get-AzRecoveryServicesBackupContainer -ContainerType AzureVM -Status Registered -Name "V2VM" -VaultId $vault.ID
PS C:\> $backupItem = Get-AzRecoveryServicesBackupItem -ContainerType AzureVM -WorkloadType AzureVM -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -Item $backupItem -StartDate $startdate.ToUniversalTime() -EndDate $enddate.ToUniversalTime() -VaultId $vault.ID
```

Perintah pertama mendapatkan objek vault berdasarkan vaultName. Perintah kedua mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam $startDate variabel.
Perintah ketiga mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $endDate.
Perintah keempat mendapatkan wadah cadangan AzureVM, dan menyimpannya dalam $Container baru. Perintah kelima mendapatkan item cadangan berdasarkan beban kerjaType, VaultId lalu menyimpannya dalam $backupItem baru.
Perintah terakhir mendapatkan array poin pemulihan untuk item di $BackupItem, lalu menyimpannya dalam variabel $rp pemulihan.

### Contoh 2: Dapatkan poin pemulihan yang siap dipindahkan ke VaultArchive

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $startDate = (Get-Date).AddDays(-7).ToUniversalTime()
PS C:\> $endDate = Get-Date.ToUniversalTime()
PS C:\> $item = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -StartDate $startDate -EndDate $endDate -VaultId $vault.ID -Item $item[3] 
-IsReadyForMove $true -TargetTier VaultArchive
```

Perintah pertama mendapatkan objek vault berdasarkan vaultName. Perintah kedua mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam $startDate variabel.
Perintah ketiga mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $endDate.
Perintah keempat mendapatkan item cadangan berdasarkan backupManagementType dan workloadType, vaultId lalu menyimpannya di $item baru.
Perintah terakhir mendapatkan array poin pemulihan untuk item dalam $backupItem yang siap untuk dipindahkan ke tingkatan VaultArchive lalu menyimpannya dalam $rp baru.

### Contoh 3: Dapatkan poin pemulihan di tier tertentu

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $startDate = (Get-Date).AddDays(-7).ToUniversalTime()
PS C:\> $endDate = Get-Date.ToUniversalTime()
PS C:\> $item = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -VaultId $vault.ID
PS C:\> $rp = Get-AzRecoveryServicesBackupRecoveryPoint -StartDate $startDate -EndDate $endDate -VaultId $vault.ID -Item $item[3] 
-Tier VaultStandard
```

Perintah pertama mendapatkan objek vault berdasarkan vaultName. Perintah kedua mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam $startDate variabel.
Perintah ketiga mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $endDate.
Perintah keempat mendapatkan item cadangan berdasarkan backupManagementType dan workloadType, vaultId lalu menyimpannya di $item baru.
Perintah terakhir mendapatkan array poin pemulihan untuk item dalam $backupItem yang siap untuk dipindahkan ke tingkatan VaultArchive lalu menyimpannya dalam $rp baru. 

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

### -EndDate

Menentukan akhir dari rentang tanggal.

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

Memfilter Titik Pemulihan berdasarkan tingkat apakah RP Siap untuk dipindahkan ke tingkat target. Gunakan ini bersama dengan parameter tier target.

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

Menentukan item di mana cmdlet ini mendapatkan poin pemulihan.
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

Tingkat target untuk memeriksa tingkat kesiapan pemindahan titik pemulihan. Saat ini hanya nilai yang valid adalah 'VaultArchive'.

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

### -Tier

Filter titik pemulihan berdasarkan nilai tingkatan.

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

### -UseSecirisanryRegion
Filter dari Wilayah Sekunder untuk Pemulihan Lintas Wilayah

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesBackupContainer](./Get-AzRecoveryServicesBackupContainer.md)

[Get-AzRecoveryServicesBackupItem](./Get-AzRecoveryServicesBackupItem.md)
