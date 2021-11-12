---
external help file: Microsoft.Azure.Commands.RecoveryServices.Backup.dll-Help.xml
Module Name: AzureRM.RecoveryServices.Backup
ms.assetid: C2A7F37B-5713-4430-B83F-C6745692396D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.recoveryservices.backup/new-azurermrecoveryservicesbackupprotectionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/New-AzureRmRecoveryServicesBackupProtectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/New-AzureRmRecoveryServicesBackupProtectionPolicy.md
ms.openlocfilehash: e9834236a72a68f64cc9b19d6576e56102f96b13
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420772"
---
# New-AzureRmRecoveryServicesBackupProtectionPolicy

## SYNOPSIS
Membuat kebijakan perlindungan Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmRecoveryServicesBackupProtectionPolicy [-Name] <String> [-WorkloadType] <WorkloadType>
 [[-BackupManagementType] <BackupManagementType>] [[-RetentionPolicy] <RetentionPolicyBase>]
 [[-SchedulePolicy] <SchedulePolicyBase>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmRecoveryServicesBackupProtectionPolicy** membuat kebijakan proteksi Cadangan di vault.
Kebijakan proteksi berkaitan dengan setidaknya satu kebijakan penyimpanan.
Kebijakan penyimpanan menentukan berapa lama titik pemulihan akan disimpan dengan Azure Backup.

Anda bisa menggunakan cmdlet Get-AzureRmRecoveryServicesBackupRetentionPolicyObject cmdlet untuk mendapatkan kebijakan penyimpanan default.
Dan Anda bisa menggunakan cmdlet Get-AzureRmRecoveryServicesBackupSchedulePolicyObject cmdlet untuk mendapatkan kebijakan jadwal default.
Objek **SchedulePolicy** **dan RetentionPolicy** digunakan sebagai input ke cmdlet **New-AzureRmRecoveryServicesBackupProtectionPolicy.**

Mengatur konteks vault menggunakan cmdlet Set-AzureRmRecoveryServicesVaultContext sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Membuat kebijakan proteksi Cadangan
```
PS C:\> $SchPol = Get-AzureRmRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
PS C:\> $SchPol.ScheduleRunTimes.Clear()
PS C:\> $Dt = Get-Date
PS C:\> $SchPol.ScheduleRunTimes.Add($Dt.ToUniversalTime())
PS C:\> $RetPol = Get-AzureRmRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM" 
PS C:\> $RetPol.DailySchedule.DurationCountInDays = 365
PS C:\> New-AzureRmRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $RetPol -SchedulePolicy $SchPol
```

Perintah pertama mendapatkan dasar **SchedulePolicyObject**, lalu menyimpannya di $SchPol variabel.

Perintah kedua menghapus semua waktu jalankan terjadwal dari kebijakan jadwal di $SchPol.

Perintah ketiga menggunakan cmdlet Get-Date cmdlet untuk mendapatkan tanggal dan waktu saat ini.

Perintah keempat menambahkan tanggal dan waktu saat ini $Dt waktu berjalan sebagai waktu berjalan yang dijadwalkan ke kebijakan jadwal.

Perintah kelima mendapatkan objek **RetentionPolicy** basis, lalu menyimpannya dalam $RetPol penyimpanan.

Perintah keenam mengatur kebijakan durasi penyimpanan ke 365 hari.

Perintah terakhir membuat objek **BackupProtectionPolicy** berdasarkan kebijakan jadwal dan penyimpanan yang dibuat oleh perintah sebelumnya.

## PARAMETERS

### -BackupManagementType
Menentukan tipe manajemen Pencadangan.
Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM 
- AzureSQLDatabase

```yaml
Type: BackupManagementType
Parameter Sets: (All)
Aliases: 
Accepted values: AzureVM, MARS, SCDPM, AzureBackupServer, AzureSQL

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama kebijakan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionPolicy
Menentukan objek **RetentionPolicy** dasar.
Anda bisa menggunakan cmdlet Get-AzureRmRecoveryServicesBackupRetentionPolicyObject untuk mendapatkan objek **RetentionPolicy.**

```yaml
Type: RetentionPolicyBase
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SchedulePolicy
Menentukan objek **schedulePolicy** dasar.
Anda bisa menggunakan cmdlet Get-AzureRmRecoveryServicesBackupSchedulePolicyObject untuk mendapatkan **objek SchedulePolicy.**

```yaml
Type: SchedulePolicyBase
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkloadType
Menentukan tipe beban kerja.
Nilai yang dapat diterima untuk parameter ini adalah:

- AzureVM 
- AzureSQLDatabase

```yaml
Type: WorkloadType
Parameter Sets: (All)
Aliases: 
Accepted values: AzureVM, AzureSQLDatabase

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PolicyBase

## CATATAN

## RELATED LINKS

[Enable-AzureRmRecoveryServicesBackupProtection](./Enable-AzureRmRecoveryServicesBackupProtection.md)

[Get-AzureRmRecoveryServicesBackupProtectionPolicy](./Get-AzureRmRecoveryServicesBackupProtectionPolicy.md)

[Get-AzureRmRecoveryServicesBackupRetentionPolicyObject](./Get-AzureRmRecoveryServicesBackupRetentionPolicyObject.md)

[Get-AzureRmRecoveryServicesBackupSchedulePolicyObject](./Get-AzureRmRecoveryServicesBackupSchedulePolicyObject.md)

[Remove-AzureRmRecoveryServicesBackupProtectionPolicy](./Remove-AzureRmRecoveryServicesBackupProtectionPolicy.md)

[Set-AzureRmRecoveryServicesBackupProtectionPolicy](./Set-AzureRmRecoveryServicesBackupProtectionPolicy.md)


