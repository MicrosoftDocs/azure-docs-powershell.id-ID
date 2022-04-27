---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 12F8A120-7282-4844-90E0-1C3393336E8A
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupJob.md
ms.openlocfilehash: 3e32beb03184c6415fda91991c0021b62c984b8b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144208754"
---
# Get-AzRecoveryServicesBackupJob

## SYNOPSIS

Mendapatkan pekerjaan Pencadangan.

## SYNTAX

```
Get-AzRecoveryServicesBackupJob [[-Status] <JobStatus>] [[-Operation] <JobOperation>] [[-From] <DateTime>]
 [[-To] <DateTime>] [[-JobId] <String>] [[-Job] <JobBase>] [-BackupManagementType <BackupManagementType>]
 [-UseSecondaryRegion] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesBackupJob** mendapatkan pekerjaan Azure Backup untuk vault tertentu.
Atur konteks vault dengan menggunakan parameter -VaultId.

## EXAMPLES

### Contoh 1: Mendapatkan semua pekerjaan yang sedang berlangsung

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$Joblist = Get-AzRecoveryServicesBackupJob -Status InProgress -VaultId $vault.ID
$Joblist[0]
```

```output
WorkloadName     Operation            Status               StartTime                 EndTime
------------     ---------            ------               ---------                 -------
V2VM             Backup               InProgress           4/23/2016 5:00:30 PM      1/1/2001 12:00:00
```

Perintah pertama mendapatkan status pekerjaan yang sedang berlangsung sebagai array, lalu menyimpannya dalam variabel $Joblist.
Perintah kedua menampilkan item pertama dalam array $Joblist.

### Contoh 2: Dapatkan semua pekerjaan yang gagal dalam 7 hari terakhir

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
Get-AzRecoveryServicesBackupJob -From (Get-Date).AddDays(-7).ToUniversalTime() -Status Failed -VaultId $vault.ID
```

Perintah ini mendapatkan pekerjaan yang gagal dari minggu lalu di brankas.
Parameter *Dari* menentukan waktu tujuh hari di masa lalu yang ditentukan dalam UTC.
Perintah tidak menentukan nilai untuk parameter *Kepada* .
Oleh karena itu, ia menggunakan nilai default dari waktu saat ini.

### Contoh 3: Dapatkan pekerjaan yang sedang berlangsung dan tunggu penyelesaian

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
```

```output
Waiting for completion... 
Waiting for completion... 
Waiting for completion... 
Done!
```

Skrip ini melakukan polling pekerjaan pertama yang saat ini sedang berlangsung hingga pekerjaan selesai.

Catatan: Anda dapat menggunakan cmdlet **Wait-AzRecoveryServicesBackupJob** untuk menunggu pekerjaan Azure Backup selesai alih-alih Perulangan Sementara.

### Contoh 4: Dapatkan semua pekerjaan AzureVM dalam 2 hari terakhir yang berhasil diselesaikan

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$Jobs = Get-AzRecoveryServicesBackupJob  -VaultId $vault.ID  -Status Completed -From (Get-Date).AddDays(-2).ToUniversalTime() -BackupManagementType AzureVM
```

Cmdlet pertama mengambil objek vault. Cmdlet kedua menyimpan semua pekerjaan AzureVM di vault tertentu yang selesai dalam 2 hari terakhir untuk $jobs. Ubah nilai parameter BackupManagementType menjadi MAB untuk mengambil pekerjaan agen MAB.

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

### -Dari

Menentukan awal, sebagai objek **DateTime** , dari rentang waktu untuk pekerjaan yang didapatkan cmdlet ini.
Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** .
Untuk informasi selengkapnya tentang objek **DateTime** , ketik `Get-Help Get-Date`.
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

### -Pekerjaan

Menentukan pekerjaan yang akan didapatkan.

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

Menentukan ID pekerjaan yang didapatkan cmdlet ini.
ID adalah properti JobId dari objek **Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase** .

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

Menentukan operasi pekerjaan yang didapat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:

- Cadangan
- KonfigurasikanBackup
- DeleteBackupData
- NonaktifkanCadangkan
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

Menentukan status pekerjaan yang didapat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:

- SedangBerlangsung
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

Menentukan akhir, sebagai objek **DateTime** , dari rentang waktu untuk pekerjaan yang didapat cmdlet ini.
Nilai default adalah waktu sistem saat ini.
Jika Anda menentukan parameter ini, Anda juga harus menentukan parameter **-From** .
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesBackupJobDetail](./Get-AzRecoveryServicesBackupJobDetail.md)

[Stop-AzRecoveryServicesBackupJob](./Stop-AzRecoveryServicesBackupJob.md)

[Wait-AzRecoveryServicesBackupJob](./Wait-AzRecoveryServicesBackupJob.md)
