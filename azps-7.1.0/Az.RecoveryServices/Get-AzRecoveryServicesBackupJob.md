---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 12F8A120-7282-4844-90E0-1C3393336E8A
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupJob.md
ms.openlocfilehash: 80288a04409d5cba981b066746825e428be8d17c
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136747199"
---
# Get-AzRecoveryServicesBackupJob

## SYNOPSIS

Mendapatkan pekerjaan Cadangan.

## SYNTAX

```
Get-AzRecoveryServicesBackupJob [[-Status] <JobStatus>] [[-Operation] <JobOperation>] [[-From] <DateTime>]
 [[-To] <DateTime>] [[-JobId] <String>] [[-Job] <JobBase>] [-BackupManagementType <BackupManagementType>]
 [-UseSecondaryRegion] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesBackupJob** mendapatkan pekerjaan Azure Backup untuk vault tertentu.
Mengatur konteks vault menggunakan parameter -VaultId.

## EXAMPLES

### Contoh 1: Mendapatkan semua pekerjaan dalam proses

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $Joblist = Get-AzRecoveryServicesBackupJob -Status InProgress -VaultId $vault.ID
PS C:\> $Joblist[0]

WorkloadName     Operation            Status               StartTime                 EndTime
------------     ---------            ------               ---------                 -------
V2VM             Backup               InProgress           4/23/2016 5:00:30 PM      1/1/2001 12:00:00
```

Perintah pertama mendapatkan status pekerjaan dalam proses sebagai array, lalu menyimpannya dalam $Joblist baru.
Perintah kedua menampilkan item pertama dalam $Joblist array.

### Contoh 2: Mendapatkan semua pekerjaan yang gagal dalam 7 hari terakhir

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> Get-AzRecoveryServicesBackupJob -From (Get-Date).AddDays(-7).ToUniversalTime() -Status Failed -VaultId $vault.ID
```

Perintah ini gagal dari minggu lalu dalam penyimpanan.
Parameter *Dari* menentukan waktu tujuh hari sebelumnya yang ditentukan dalam UTC.
Perintah tidak menentukan nilai untuk parameter *To.*
Oleh karena itu, menggunakan nilai default waktu saat ini.

### Contoh 3: Mendapatkan pekerjaan dalam proses dan menunggu penyelesaian

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$Jobs = Get-AzRecoveryServicesBackupJob -Status InProgress -VaultId $vault.ID
$Job = $Jobs[0]
While ( $Job.Status -ne Completed ) {
    Write-Host -Object "Waiting for completion..."
    Start-Sleep -Seconds 10
    $Job = Get-AzRecoveryServicesBackupJob -Job $Job -VaultId $vault.ID
}
Write-Host -Object "Done!"

Waiting for completion... 
Waiting for completion... 
Waiting for completion... 
Done!
```

Skrip ini menjajaki pekerjaan pertama yang saat ini sedang berlangsung hingga pekerjaan selesai.

Catatan: Anda dapat menggunakan cmdlet **Wait-AzRecoveryServicesBackupJob** untuk menunggu pekerjaan Azure Backup selesai, bukan Mengulang sementara.

### Contoh 4: Mendapatkan semua pekerjaan AzureVM dalam 2 hari terakhir yang berhasil diselesaikan

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$Jobs = Get-AzRecoveryServicesBackupJob  -VaultId $vault.ID  -Status Completed -From (Get-Date).AddDays(-2).ToUniversalTime() -BackupManagementType AzureVM
```

Cmdlet pertama mengambil objek vault. Cmdlet kedua menyimpan semua pekerjaan AzureVM di vault tertentu yang selesai dalam 2 hari terakhir $jobs. Ubah nilai parameter BackupManagementType menjadi MAB untuk mengambil pekerjaan agen MAB.

## PARAMETERS

### -BackupManagementType

Kelas sumber daya yang dilindungi. Saat ini nilai yang didukung untuk cmdlet ini adalah AzureVM, AzureStorage, AzureWorkload, MAB.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType]
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, AzureStorage, AzureWorkload, MAB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Dari

Menentukan mulai, sebagai objek **DateTime,** rentang waktu untuk pekerjaan yang cmdlet ini dapatkan.
Untuk mendapatkan **objek DateTime,** gunakan cmdlet **Get-Date.**
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

Menentukan pekerjaan yang akan didaekan.

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
ID adalah properti JobId dari objek **Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase.**

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
- DisableBackup
- Pulihkan
- BackupDataMove

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobOperation]
Parameter Sets: (All)
Aliases:
Accepted values: Backup, Restore, ConfigureBackup, DisableBackup, DeleteBackupData, BackupDataMove, UpdateCustomerManagedKey

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
Jika Anda menentukan parameter ini, Anda juga harus menentukan parameter **-From.**
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesBackupJobDetail](./Get-AzRecoveryServicesBackupJobDetail.md)

[Stop-AzRecoveryServicesBackupJob](./Stop-AzRecoveryServicesBackupJob.md)

[Wait-AzRecoveryServicesBackupJob](./Wait-AzRecoveryServicesBackupJob.md)
