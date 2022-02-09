---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: C2A7F37B-5713-4430-B83F-C6745692396D
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/new-azrecoveryservicesbackupprotectionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesBackupProtectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesBackupProtectionPolicy.md
ms.openlocfilehash: 825e36f6723e9d89f4c8efc4431e8fb51e56909a
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138302028"
---
# New-AzRecoveryServicesBackupProtectionPolicy

## SYNOPSIS
Membuat kebijakan perlindungan Cadangan.

## SYNTAX

```
New-AzRecoveryServicesBackupProtectionPolicy [-Name] <String> [-WorkloadType] <WorkloadType>
 [[-BackupManagementType] <BackupManagementType>] [[-RetentionPolicy] <RetentionPolicyBase>]
 [[-SchedulePolicy] <SchedulePolicyBase>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRecoveryServicesBackupProtectionPolicy** membuat kebijakan proteksi Cadangan di vault.
Kebijakan proteksi berkaitan dengan setidaknya satu kebijakan penyimpanan.
Kebijakan penyimpanan menentukan berapa lama titik pemulihan akan disimpan dengan Azure Backup.
Anda bisa menggunakan cmdlet Get-AzRecoveryServicesBackupRetentionPolicyObject cmdlet untuk mendapatkan kebijakan penyimpanan default.
Dan Anda bisa menggunakan cmdlet Get-AzRecoveryServicesBackupSchedulePolicyObject cmdlet untuk mendapatkan kebijakan jadwal default.
Objek **SchedulePolicy** **dan RetentionPolicy** digunakan sebagai input ke cmdlet **New-AzRecoveryServicesBackupProtectionPolicy** .
Mengatur konteks vault menggunakan cmdlet Set-AzRecoveryServicesVaultContext cmdlet sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Membuat kebijakan proteksi Cadangan
```powershell
PS C:\> $SchPol = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
PS C:\> $SchPol.ScheduleRunTimes.Clear()
PS C:\> $Dt = Get-Date
PS C:\> $SchPol.ScheduleRunTimes.Add($Dt.ToUniversalTime())
PS C:\> $RetPol = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM" 
PS C:\> $RetPol.DailySchedule.DurationCountInDays = 365
PS C:\> New-AzRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $RetPol -SchedulePolicy $SchPol
```

Perintah pertama mendapatkan **schedulePolicyObject** dasar, lalu menyimpannya dalam $SchPol variabel.
Perintah kedua menghapus semua waktu jalankan terjadwal dari kebijakan jadwal di $SchPol.
Perintah ketiga menggunakan cmdlet Get-Date cmdlet untuk mendapatkan tanggal dan waktu saat ini.
Perintah keempat menambahkan tanggal dan waktu saat ini $Dt waktu sebagaimana waktu berjalan yang dijadwalkan ke kebijakan jadwal.
Perintah kelima mendapatkan objek **RetentionPolicy** basis, lalu menyimpannya dalam $RetPol penyimpanan.
Perintah keenam mengatur kebijakan durasi penyimpanan ke 365 hari.
Perintah terakhir membuat objek **BackupProtectionPolicy** berdasarkan kebijakan jadwal dan penyimpanan yang dibuat oleh perintah sebelumnya.

### Contoh 2: Membuat kebijakan berbagi file untuk beberapa cadangan per hari
```powershell
PS C:\> $schedulePolicy = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
PS C:\> $timeZone = Get-TimeZone
PS C:\> $schedulePolicy.ScheduleRunTimeZone = $timeZone.Id
PS C:\> $startTime = Get-Date -Date "2021-12-22T06:00:00.00+00:00"
PS C:\> $schedulePolicy.ScheduleWindowStartTime = $startTime.ToUniversalTime()
PS C:\> $schedulePolicy.ScheduleInterval = 6
PS C:\> $schedulePolicy.ScheduleWindowDuration = 14
PS C:\> $retentionPolicy = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
PS C:\> $retentionPolicy.DailySchedule.DurationCountInDays = 10
PS C:\> New-AzRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $retentionPolicy -SchedulePolicy $schedulePolicy
```

Perintah pertama mendapatkan **schedulePolicyObject basis jam**, lalu menyimpannya dalam $schedulePolicy variabel.
Perintah kedua dan ketiga mengambil zona waktu dan memperbarui zona waktu dalam $schedulePolicy.
Perintah keempat dan kelima memulai waktu mulai jendela jadwal dan memperbarui $schedulePolicy. Harap diperhatikan bahwa waktu mulai harus dalam UTC meskipun zona waktu tidak UTC. Perintah keenam dan ketujuh memperbarui interval (dalam jam) setelah itu cadangan akan dibuat ulang di hari yang sama, durasi (dalam jam) di mana jadwal akan dijalankan.
Perintah kedelapan mendapatkan objek **RetentionPolicy** basis per jam, lalu menyimpannya dalam $retentionPolicy per jam.
Perintah kesembilan mengatur kebijakan durasi penyimpanan ke 10 hari.
Perintah terakhir membuat objek **BackupProtectionPolicy** berdasarkan kebijakan jadwal dan penyimpanan yang dibuat oleh perintah sebelumnya.

### Contoh 3

Membuat kebijakan perlindungan Cadangan. (otomatisgenerated)

```powershell <!-- Aladdin Generated Example --> 
New-AzRecoveryServicesBackupProtectionPolicy -Name 'NewPolicy' -RetentionPolicy $RetPol -SchedulePolicy $SchPol -VaultId $vault.ID -WorkloadType AzureVM
```

## PARAMETERS

### -BackupManagementType
Kelas sumber daya yang dilindungi. Nilai yang dapat diterima untuk parameter ini adalah:
- AzureVM 
- AzureStorage
- AzureWorkload

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType]
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, AzureStorage, AzureWorkload

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Nama
Menentukan nama kebijakan.

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

### -RetentionPolicy
Menentukan objek **RetentionPolicy** dasar.
Anda bisa menggunakan cmdlet Get-AzRecoveryServicesBackupRetentionPolicyObject untuk mendapatkan **objek RetentionPolicy** .

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RetentionPolicyBase
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
Anda bisa menggunakan cmdlet Get-AzRecoveryServicesBackupSchedulePolicyObject untuk mendapatkan objek **SchedulePolicy** .

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SchedulePolicyBase
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Tipe beban kerja sumber daya. Nilai yang dapat diterima untuk parameter ini adalah:
- AzureVM 
- AzureFiles
- MSSQL

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.WorkloadType
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, AzureFiles, MSSQL

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.WorkloadType

### System.Nullable'1[[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType, Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.Models, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RetentionPolicyBase

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SchedulePolicyBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PolicyBase

## CATATAN

## RELATED LINKS

[Enable-AzRecoveryServicesBackupProtection](./Enable-AzRecoveryServicesBackupProtection.md)

[Get-AzRecoveryServicesBackupProtectionPolicy](./Get-AzRecoveryServicesBackupProtectionPolicy.md)

[Get-AzRecoveryServicesBackupRetentionPolicyObject](./Get-AzRecoveryServicesBackupRetentionPolicyObject.md)

[Get-AzRecoveryServicesBackupSchedulePolicyObject](./Get-AzRecoveryServicesBackupSchedulePolicyObject.md)

[Remove-AzRecoveryServicesBackupProtectionPolicy](./Remove-AzRecoveryServicesBackupProtectionPolicy.md)

[Set-AzRecoveryServicesBackupProtectionPolicy](./Set-AzRecoveryServicesBackupProtectionPolicy.md)


