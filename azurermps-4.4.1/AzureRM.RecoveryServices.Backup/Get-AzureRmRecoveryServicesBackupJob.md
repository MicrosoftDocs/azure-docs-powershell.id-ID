---
external help file: Microsoft.Azure.Commands.RecoveryServices.Backup.dll-Help.xml
Module Name: AzureRM.RecoveryServices.Backup
ms.assetid: 12F8A120-7282-4844-90E0-1C3393336E8A
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Get-AzureRmRecoveryServicesBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Get-AzureRmRecoveryServicesBackupJob.md
ms.openlocfilehash: 3fb6b89f5708c951731c45e0d32e0f7a379cf754
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421432"
---
# Get-AzureRmRecoveryServicesBackupJob

## SYNOPSIS
Mendapatkan pekerjaan Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmRecoveryServicesBackupJob [[-Status] <JobStatus>] [[-Operation] <JobOperation>] [[-From] <DateTime>]
 [[-To] <DateTime>] [[-JobId] <String>] [[-Job] <JobBase>] [-BackupManagementType <BackupManagementType>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmRecoveryServicesBackupJob** mendapatkan pekerjaan Azure Backup untuk vault tertentu.

Mengatur konteks vault menggunakan cmdlet Set-AzureRmRecoveryServicesVaultContext cmdlet sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan semua pekerjaan dalam proses
```
PS C:\>$Joblist = Get-AzureRMRecoveryservicesBackupJob -Status Inprogress
PS C:\> $Joblist[0]
WorkloadName     Operation            Status               StartTime                 EndTime                                             
------------     ---------            ------               ---------                 -------                                             
V2VM             Backup               InProgress           4/23/2016 5:00:30 PM      1/1/2001 12:00:00
```

Perintah pertama mendapatkan status pekerjaan dalam proses sebagai array, lalu menyimpannya dalam $Joblist kolom.

Perintah kedua menampilkan item pertama dalam $Joblist array.

### Contoh 2: Mendapatkan semua pekerjaan yang gagal dalam 7 hari terakhir
```
PS C:\>Get-AzureRmRecoveryServicesBackupJob -From (Get-Date).AddDays(-7).ToUniversalTime() -Status Failed
```

Perintah ini gagal dari minggu lalu dalam penyimpanan.
Parameter *Dari* menentukan waktu tujuh hari sebelumnya yang ditentukan dalam UTC.
Perintah tidak menentukan nilai untuk parameter *To.*
Oleh karena itu, menggunakan nilai default waktu saat ini.

### Contoh 3: Mendapatkan pekerjaan dalam proses dan menunggu penyelesaian
```
PS C:\> 
$Jobs = Get-AzureRmRecoveryServicesBackupJob -Status InProgress
$Job = $Jobs[0]
    while ( $Job.Status -ne Completed )
    {
       Write-Host "Waiting for completion..."
       Start-Sleep -Seconds 10
       $job = Get-AzureRmBackAzureRmRecoveryServicesBackupJob  -Job $Job
    }
    Write-Host "Done!"
    Waiting for completion... 
    Waiting for completion... 
    Waiting for completion... 
    Done!
```

Skrip ini menjajaki pekerjaan pertama yang saat ini sedang berlangsung hingga pekerjaan selesai.

## PARAMETERS

### -BackupManagementType
Menentukan tipe manajemen Pencadangan.
Saat ini, hanya AzureVM yang didukung.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType]
Parameter Sets: (All)
Aliases: 
Accepted values: AzureVM, MARS, SCDPM, AzureBackupServer, AzureSQL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dari
Menentukan mulai, sebagai objek **DateTime,** rentang waktu untuk pekerjaan yang cmdlet ini dapatkan.
Untuk mendapatkan objek **DateTime,** gunakan cmdlet Get-Date.
Untuk informasi selengkapnya tentang **objek DateTime,** ketik `Get-Help Get-Date` .
Gunakan format UTC untuk tanggal.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Menentukan nama Pekerjaan pencadangan untuk mendapatkan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang akan dapatkan cmdlet ini.
ID adalah properti InstanceId dari objek **AzureRmRecoveryServicesBackupJob.**
Untuk mendapatkan objek **AzureRmRecoveryServicesBackupJob,** gunakan Get-AzureRmRecoveryServicesBackupJob.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operasi
Menentukan operasi pekerjaan yang akan dilakukan cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:

- Pencadangan
- ConfigureBackup
- DeleteBackupData
- Daftar
- Pulihkan
- Buka Proteksi
- Pisahkan pendaftaran

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobOperation]
Parameter Sets: (All)
Aliases: 
Accepted values: Backup, Restore, ConfigureBackup, DisableBackup, DeleteBackupData

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Menentukan status pekerjaan yang cmdlet ini dapatkan.
Nilai yang dapat diterima untuk parameter ini adalah:

- InProgress
- Gagal
- Dibatalkan
- Membatalkan
- Selesai
- CompletedWithWarnings

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobStatus]
Parameter Sets: (All)
Aliases: 
Accepted values: InProgress, Cancelling, Cancelled, Completed, CompletedWithWarnings, Failed

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ke
Menentukan akhir, sebagai objek **DateTime,** rentang waktu untuk pekerjaan yang cmdlet ini dapatkan.
Nilai default adalah waktu sistem saat ini.
Jika Anda menentukan parameter ini, Anda juga harus menentukan parameter *From.*
Gunakan format UTC untuk tanggal.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### System.Collections.Generic.IList'1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase]

## CATATAN

## RELATED LINKS

[Get-AzureRmRecoveryServicesBackupJobDetails](./Get-AzureRmRecoveryServicesBackupJobDetails.md)

[Stop-AzureRmRecoveryServicesBackupJob](./Stop-AzureRmRecoveryServicesBackupJob.md)

[Wait-AzureRmRecoveryServicesBackupJob](./Wait-AzureRmRecoveryServicesBackupJob.md)


