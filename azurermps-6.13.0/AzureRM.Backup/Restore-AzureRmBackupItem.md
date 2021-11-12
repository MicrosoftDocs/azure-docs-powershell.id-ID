---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 856B76FC-88ED-4A29-9DC6-C482398D702E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/restore-azurermbackupitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Restore-AzureRmBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Restore-AzureRmBackupItem.md
ms.openlocfilehash: 3bbddc217bd33e303b998bfb816c9c0c65e96ce6
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425484"
---
# Restore-AzureRmBackupItem

## SYNOPSIS
Memulihkan data dan konfigurasi untuk item Cadangan ke titik pemulihan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Restore-AzureRmBackupItem [-StorageAccountName] <String> [-RecoveryPoint] <AzureRMBackupRecoveryPoint>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzureRmBackupItem** memulihkan data dan konfigurasi untuk item Azure Backup ke titik pemulihan yang ditentukan.
Cmdlet ini memulai pemulihan dari vault Cadangan ke akun Anda.
Operasi pemulihan tidak memulihkan mesin virtual penuh.
Alat ini memulihkan data disk dan informasi konfigurasi.
Setelah operasi pemulihan selesai, Anda harus membuat mesin virtual dan memulainya.

## EXAMPLES

### Contoh 1: Pulihkan mesin virtual ke titik pemulihan
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> $Container = Get-AzureRmBackupContainer -Vault $Vault -Type AzureVM -Name "DPMSERVER.CONTOSO.COM"
PS C:\> $BackupItem = Get-AzureRmBackupItem -Container $Container
PS C:\> $RecoveryPoint = Get-AzureRmBackupRecoveryPoint -Item $BackupItem 
PS C:\> Restore-AzureRmBackupItem -StorageAccountName "DestinationAccount" -RecoveryPoint $RecoveryPoint 
WorkloadName    Operation       Status          StartTime              EndTime
------------    ---------       ------          ---------              -------
co03-vm         Restore         InProgress      26-Aug-15 1:14:01 PM   01-Jan-01 12:00:00 AM
```

Perintah pertama mendapatkan vault bernama Vault03 menggunakan cmdlet Get-AzureRmBackupVault baru.
Perintah menyimpan objek tersebut dalam $Vault variabel.
Perintah kedua mendapatkan wadah dengan nama yang ditentukan dalam penyimpanan pada $Vault menggunakan cmdlet **Get-AzureRmBackupContainer.**
Perintah menyimpan objek tersebut dalam $Container variabel.
Perintah ketiga mendapatkan item cadangan dalam wadah pada $Container dengan menggunakan cmdlet **Get-AzureRmBackupItem.**
Perintah menyimpan objek tersebut dalam $BackupItem variabel.
Perintah keempat mendapatkan poin pemulihan untuk item dalam $BackupItem.
Perintah menyimpan objek tersebut dalam $RecoveryPoint variabel.
Perintah terakhir memulihkan titik pemulihan dalam $RecoveryPoint akun bernama DestinationAccount.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -RecoveryPoint
Menentukan titik pemulihan untuk memulihkan mesin virtual.
Untuk mendapatkan **AzureRmBackupRecoveryPoint,** gunakan cmdlet Get-AzureRmBackupRecoveryPoint cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupRecoveryPoint
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama akun penyimpanan target dalam langganan Anda.
Sebagai bagian dari proses pemulihan, cmdlet ini menyimpan disk dan informasi konfigurasi di akun penyimpanan ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupRecoveryPoint
Parameter: RecoveryPoint (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob

## CATATAN

## RELATED LINKS

[Backup-AzureRmBackupItem](./Backup-AzureRmBackupItem.md)

[Get-AzureRmBackupItem](./Get-AzureRmBackupItem.md)

[Get-AzureRmBackupRecoveryPoint](./Get-AzureRmBackupRecoveryPoint.md)


