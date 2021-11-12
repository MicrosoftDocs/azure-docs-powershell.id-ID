---
external help file: Microsoft.Azure.Commands.RecoveryServices.Backup.dll-Help.xml
Module Name: AzureRM.RecoveryServices.Backup
ms.assetid: DEB3D7B5-D974-472B-B8B4-9A19CA6AECCC
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Get-AzureRmRecoveryServicesBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Get-AzureRmRecoveryServicesBackupItem.md
ms.openlocfilehash: 03da361f8dd68d345782568dc243d4438cad1d77
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421437"
---
# Get-AzureRmRecoveryServicesBackupItem

## SYNOPSIS
Mendapatkan item dari wadah dalam Cadangkan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetItemsForContainer (Default)
```
Get-AzureRmRecoveryServicesBackupItem [-Container] <ContainerBase> [[-Name] <String>]
 [[-ProtectionStatus] <ItemProtectionStatus>] [[-ProtectionState] <ItemProtectionState>]
 [-WorkloadType] <WorkloadType> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetItemsForVault
```
Get-AzureRmRecoveryServicesBackupItem [-BackupManagementType] <BackupManagementType> [[-Name] <String>]
 [[-ProtectionStatus] <ItemProtectionStatus>] [[-ProtectionState] <ItemProtectionState>]
 [-WorkloadType] <WorkloadType> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmRecoveryServicesBackupItem** mendapatkan item dalam wadah atau nilai di Azure Backup dan status proteksi item.

Wadah yang terdaftar di vault Layanan Pemulihan Azure dapat memiliki satu atau beberapa item yang dapat diproteksi.
Untuk mesin virtual Azure, hanya ada satu item cadangan dalam wadah mesin virtual.

Mengatur konteks vault menggunakan cmdlet Set-AzureRmRecoveryServicesVaultContext cmdlet sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan item dari wadah Cadangan
```
PS C:\>$Container = Get-AzureRmRecoveryServicesBackupContainer -ContainerType AzureVM -Status Registered -Name "V2VM"
PS C:\> $BackupItem = Get-AzureRmRecoveryServicesBackupItem -Container $Container -WorkloadType AzureVM
```

Perintah pertama mendapatkan wadah tipe AzureVM, lalu menyimpannya di $Container variabel.

Perintah kedua mendapatkan item Cadangan bernama V2VM dalam $Container, lalu menyimpannya di $BackupItem cadangan.

## PARAMETERS

### -BackupManagementType
Menentukan tipe manajemen Pencadangan.
Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM 
- MARS 
- SCDPM 
- AzureBackupServer AzureSQL

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType
Parameter Sets: GetItemsForVault
Aliases: 
Accepted values: AzureVM, MARS, SCDPM, AzureBackupServer, AzureSQL

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Container
Menentukan objek wadah tempat cmdlet ini mendapatkan item cadangan.
Untuk mendapatkan **AzureRmRecoveryServicesBackupContainer,** gunakan cmdlet Get-AzureRmRecoveryServicesBackupContainer cmdlet.

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

### -Nama
Menentukan nama wadah.

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

### -ProtectionState
Menentukan status proteksi.
Nilai yang dapat diterima untuk parameter ini adalah:

- IRPending.
Sinkronisasi awal belum dimulai dan belum ada titik pemulihan. 
- Diproteksi.
Proteksi sedang berlangsung. 
- ProtectionError.
Terdapat kesalahan proteksi.
- ProtectionStopped.
Proteksi dinonaktifkan.

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
Menentukan status proteksi keseluruhan item dalam wadah.
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

### -WorkloadType
Menentukan tipe beban kerja. Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM 
- AzureSQLDatabase

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.WorkloadType
Parameter Sets: (All)
Aliases: 
Accepted values: AzureVM, AzureSQLDatabase

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase

### System.Collections.Generic.IList'1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase]

## CATATAN

## RELATED LINKS

[Backup-AzureRmRecoveryServicesBackupItem](./Backup-AzureRmRecoveryServicesBackupItem.md)

[Disable-AzureRmRecoveryServicesBackupProtection](./Disable-AzureRmRecoveryServicesBackupProtection.md)

[Get-AzureRmRecoveryServicesBackupRecoveryPoint](./Get-AzureRmRecoveryServicesBackupRecoveryPoint.md)

[Restore-AzureRmRecoveryServicesBackupItem](./Restore-AzureRmRecoveryServicesBackupItem.md)


