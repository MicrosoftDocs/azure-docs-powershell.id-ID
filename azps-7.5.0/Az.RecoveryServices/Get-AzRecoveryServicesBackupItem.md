---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: DEB3D7B5-D974-472B-B8B4-9A19CA6AECCC
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupItem.md
ms.openlocfilehash: 466a9af7ac6f977f41564b50fda8e9a3995c3643
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144208787"
---
# Get-AzRecoveryServicesBackupItem

## SYNOPSIS

Mendapatkan item dari kontainer di Backup.

## SYNTAX

### GetItemsForContainer (Default)
```
Get-AzRecoveryServicesBackupItem [-Container] <ContainerBase> [[-Name] <String>]
 [[-ProtectionStatus] <ItemProtectionStatus>] [[-ProtectionState] <ItemProtectionState>]
 [-WorkloadType] <WorkloadType> [[-DeleteState] <ItemDeleteState>] [-FriendlyName <String>] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-UseSecondaryRegion] [<CommonParameters>]
```

### GetItemsForVault
```
Get-AzRecoveryServicesBackupItem [-BackupManagementType] <BackupManagementType> [[-Name] <String>]
 [[-ProtectionStatus] <ItemProtectionStatus>] [[-ProtectionState] <ItemProtectionState>]
 [-WorkloadType] <WorkloadType> [[-DeleteState] <ItemDeleteState>] [-FriendlyName <String>] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-UseSecondaryRegion] [<CommonParameters>]
```

### GetItemsForPolicy
```
Get-AzRecoveryServicesBackupItem [-Policy] <PolicyBase> [[-Name] <String>]
 [[-ProtectionStatus] <ItemProtectionStatus>] [[-ProtectionState] <ItemProtectionState>]
 [[-DeleteState] <ItemDeleteState>] [-FriendlyName <String>] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-UseSecondaryRegion] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesBackupItem** mendapatkan daftar item yang dilindungi dalam kontainer dan status perlindungan item.
Kontainer yang didaftarkan ke vault Azure Recovery Services dapat memiliki satu atau beberapa item yang dapat dilindungi.
Untuk komputer virtual Azure, hanya boleh ada satu item cadangan dalam kontainer komputer virtual.
Atur konteks vault dengan menggunakan parameter -VaultId.

## EXAMPLES

### Contoh 1: Mendapatkan item dari kontainer Backup

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$Container = Get-AzRecoveryServicesBackupContainer -ContainerType AzureVM -Status Registered -FriendlyName "V2VM" -VaultId $vault.ID
$BackupItem = Get-AzRecoveryServicesBackupItem -Container $Container -WorkloadType AzureVM -VaultId $vault.ID
```

Perintah pertama mendapatkan kontainer jenis AzureVM, lalu menyimpannya dalam variabel $Container.
Perintah kedua mendapatkan item Cadangan bernama V2VM di $Container, lalu menyimpannya dalam variabel $BackupItem.

### Contoh 2: Mendapatkan Item Berbagi File Azure dari FriendlyName

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$Container = Get-AzRecoveryServicesBackupContainer -ContainerType AzureStorage -Status Registered -FriendlyName "StorageAccount1" -VaultId $vault.ID
$BackupItem = Get-AzRecoveryServicesBackupItem -Container $Container -WorkloadType AzureFiles -VaultId $vault.ID -FriendlyName "FileShareName"
```

Perintah pertama mendapatkan kontainer jenis AzureStorage, lalu menyimpannya dalam variabel $Container.
Perintah kedua mendapatkan item Cadangan yang friendlyName-nya cocok dengan nilai yang diteruskan dalam Parameter FriendlyName, lalu menyimpannya dalam variabel $BackupItem.
Menggunakan parameter FriendlyName dapat menghasilkan lebih dari satu Azure File Share. Dalam kasus seperti itu, jalankan cmdlet dengan meneruskan nilai untuk parameter -Name sebagai properti Nama yang dikembalikan dalam kumpulan hasil $BackupItem.

## PARAMETERS

### -BackupManagementType

Kelas sumber daya yang dilindungi. Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM
- MAB
- AzureStorage
- AzureWorkload

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType
Parameter Sets: GetItemsForVault
Aliases:
Accepted values: AzureVM, MAB, AzureStorage, AzureWorkload

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kontainer

Menentukan objek kontainer tempat cmdlet ini mendapatkan item cadangan.
Untuk mendapatkan **AzureRmRecoveryServicesBackupContainer**, gunakan cmdlet **Get-AzRecoveryServicesBackupContainer** .

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerBase
Parameter Sets: GetItemsForContainer
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -DeleteState
Menentukan deletestate item Nilai yang dapat diterima untuk parameter ini adalah:

- ToBeDeleted
- Tidak Dihapus

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemDeleteState
Parameter Sets: (All)
Aliases:
Accepted values: ToBeDeleted, NotDeleted

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
FriendlyName dari item yang dicadangkan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Menentukan nama item cadangan. Untuk berbagi file, tentukan ID unik berbagi file yang dilindungi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kebijakan

Objek kebijakan perlindungan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PolicyBase
Parameter Sets: GetItemsForPolicy
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionState

Menentukan status perlindungan.
Nilai yang dapat diterima untuk parameter ini adalah:

- IRPending.
Sinkronisasi awal belum dimulai dan belum ada titik pemulihan.
- Dilindungi.
Perlindungan sedang berlangsung.
- ProtectionError.
Ada kesalahan perlindungan.
- Perlindungan Dihentikan.
Perlindungan dinonaktifkan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemProtectionState
Parameter Sets: (All)
Aliases:
Accepted values: IRPending, ProtectionError, Protected, ProtectionStopped

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionStatus

Menentukan status perlindungan keseluruhan item dalam kontainer.
Nilai yang dapat diterima untuk parameter ini adalah:

- Sehat
- Tidak sehat

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemProtectionStatus
Parameter Sets: (All)
Aliases:
Accepted values: Healthy, Unhealthy

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSecondaryRegion
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

### -WorkloadType

Jenis beban kerja sumber daya. Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM
- AzureFiles
- MSSQL
- FileFolder
- SAPHanaDatabase

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.WorkloadType
Parameter Sets: GetItemsForContainer, GetItemsForVault
Aliases:
Accepted values: AzureVM, AzureFiles, MSSQL, FileFolder, SAPHanaDatabase

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase

## NOTES

## RELATED LINKS

[Backup-AzRecoveryServicesBackupItem](./Backup-AzRecoveryServicesBackupItem.md)

[Disable-AzRecoveryServicesBackupProtection](./Disable-AzRecoveryServicesBackupProtection.md)

[Get-AzRecoveryServicesBackupRecoveryPoint](./Get-AzRecoveryServicesBackupRecoveryPoint.md)

[Restore-AzRecoveryServicesBackupItem](./Restore-AzRecoveryServicesBackupItem.md)
