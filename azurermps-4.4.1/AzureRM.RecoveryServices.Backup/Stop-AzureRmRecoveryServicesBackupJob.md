---
external help file: Microsoft.Azure.Commands.RecoveryServices.Backup.dll-Help.xml
Module Name: AzureRM.RecoveryServices.Backup
ms.assetid: A8FDC5A3-F309-49B3-B417-8E0A1535BAF4
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Stop-AzureRmRecoveryServicesBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Stop-AzureRmRecoveryServicesBackupJob.md
ms.openlocfilehash: 63d90aa5f98f6710702a70e9609c7625626e34c4
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422719"
---
# Stop-AzureRmRecoveryServicesBackupJob

## SYNOPSIS
Membatalkan pekerjaan yang sedang berjalan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### JobFilterSet (Default)
```
Stop-AzureRmRecoveryServicesBackupJob [-Job] <JobBase> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### IdFilterSet
```
Stop-AzureRmRecoveryServicesBackupJob [-JobId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureRmRecoveryServicesBackupJob** membatalkan pekerjaan Azure Backup yang sudah ada.
Gunakan cmdlet ini untuk menghentikan pekerjaan yang membutuhkan waktu terlalu lama dan memblokir aktivitas lain.

Anda hanya bisa membatalkan tipe pekerjaan Cadangkan dan Pulihkan.

Mengatur konteks vault menggunakan cmdlet Set-AzureRmRecoveryServicesVaultContext sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Menghentikan pekerjaan pencadangan
```
PS C:\>$Job = Get-AzureRmRecoveryServicesBackupJob -Operation Backup
PS C:\> Stop-AzureRmRecoveryServicesBackupJob -JobID $Job.InstanceId
```

Perintah pertama mendapatkan pekerjaan cadangan, lalu menyimpan pekerjaan di $Job tersebut.

Perintah terakhir menghentikan pekerjaan dengan menentukan ID Contoh pekerjaan cadangan di $Job.

## PARAMETERS

### -Job
Menentukan pekerjaan yang dibatalkan cmdlet ini.
Untuk mendapatkan objek **BackupJob,** gunakan cmdlet Get-AzureRmRecoveryServicesBackupJob.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase
Parameter Sets: JobFilterSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang akan dibatalkan.
ID adalah properti InstanceId dari objek **BackupJob.**
Untuk mendapatkan objek **BackupJob,** gunakan Get-AzureRmRecoveryServicesBackupJob.

```yaml
Type: System.String
Parameter Sets: IdFilterSet
Aliases: 

Required: True
Position: 2
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

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## CATATAN

## RELATED LINKS

[Get-AzureRmRecoveryServicesBackupJob](./Get-AzureRmRecoveryServicesBackupJob.md)

[Wait-AzureRmRecoveryServicesBackupJob](./Wait-AzureRmRecoveryServicesBackupJob.md)


