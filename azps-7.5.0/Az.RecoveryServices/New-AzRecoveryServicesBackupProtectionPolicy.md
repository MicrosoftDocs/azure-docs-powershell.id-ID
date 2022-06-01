---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: C2A7F37B-5713-4430-B83F-C6745692396D
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/new-azrecoveryservicesbackupprotectionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesBackupProtectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesBackupProtectionPolicy.md
ms.openlocfilehash: 3690c4d46a9df47aa2d8791e8b87d71e8cce7c0e
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145979365"
---
# Baru-AzRecoveryServicesBackupProtectionPolicy

## SYNOPSIS
Membuat kebijakan perlindungan Pencadangan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/new-azrecoveryservicesbackupprotectionpolicy) untuk informasi terbaru.

## SYNTAX

```
New-AzRecoveryServicesBackupProtectionPolicy [-Name] <String> [-WorkloadType] <WorkloadType>
 [[-BackupManagementType] <BackupManagementType>] [[-RetentionPolicy] <RetentionPolicyBase>]
 [[-SchedulePolicy] <SchedulePolicyBase>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRecoveryServicesBackupProtectionPolicy** membuat kebijakan perlindungan Cadangan dalam vault.
Kebijakan perlindungan dikaitkan dengan setidaknya satu kebijakan penyimpanan.
Kebijakan retensi menentukan berapa lama titik pemulihan disimpan dengan Azure Backup.
Anda dapat menggunakan cmdlet Get-AzRecoveryServicesBackupRetentionPolicyObject untuk mendapatkan kebijakan penyimpanan default.
Dan Anda dapat menggunakan cmdlet Get-AzRecoveryServicesBackupSchedulePolicyObject untuk mendapatkan kebijakan jadwal default.
Objek **SchedulePolicy** dan **RetentionPolicy** digunakan sebagai input ke cmdlet **New-AzRecoveryServicesBackupProtectionPolicy** .
Atur konteks vault dengan menggunakan cmdlet Set-AzRecoveryServicesVaultContext sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Membuat kebijakan perlindungan Pencadangan
```powershell
$SchPol = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM"
$SchPol.ScheduleRunTimes.Clear()
$Dt = Get-Date
$SchPol.ScheduleRunTimes.Add($Dt.ToUniversalTime())
$RetPol = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM"
$RetPol.DailySchedule.DurationCountInDays = 365
New-AzRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $RetPol -SchedulePolicy $SchPol
```

Perintah pertama mendapatkan **SchedulePolicyObject** dasar, lalu menyimpannya dalam variabel $SchPol.
Perintah kedua menghapus semua durasi terjadwal dari kebijakan jadwal di $SchPol.
Perintah ketiga menggunakan cmdlet Get-Date untuk mendapatkan tanggal dan waktu saat ini.
Perintah keempat menambahkan tanggal dan waktu saat ini dalam $Dt sebagai durasi terjadwal ke kebijakan jadwal.
Perintah kelima mendapatkan objek **RetentionPolicy** dasar, lalu menyimpannya dalam variabel $RetPol.
Perintah keenam menetapkan kebijakan durasi retensi menjadi 365 hari.
Perintah akhir membuat objek **BackupProtectionPolicy** berdasarkan jadwal dan kebijakan retensi yang dibuat oleh perintah sebelumnya.

### Contoh 2: Membuat kebijakan fileshare untuk beberapa cadangan per hari
```powershell
$schedulePolicy = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
$timeZone = Get-TimeZone
$schedulePolicy.ScheduleRunTimeZone = $timeZone.Id
$startTime = Get-Date -Date "2021-12-22T06:00:00.00+00:00"
$schedulePolicy.ScheduleWindowStartTime = $startTime.ToUniversalTime()
$schedulePolicy.ScheduleInterval = 6
$schedulePolicy.ScheduleWindowDuration = 14
$retentionPolicy = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
$retentionPolicy.DailySchedule.DurationCountInDays = 10
New-AzRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $retentionPolicy -SchedulePolicy $schedulePolicy
```

Perintah pertama mendapatkan **SchedulePolicyObject** dasar per jam, lalu menyimpannya dalam variabel $schedulePolicy.
Perintah kedua dan ketiga mengambil zona waktu dan memperbarui zona waktu dalam $schedulePolicy.
Perintah keempat dan kelima menginisialisasi waktu mulai jendela jadwal dan memperbarui $schedulePolicy. Harap dicatat bahwa waktu mulai harus dalam UTC meskipun zona waktu bukan UTC.
Perintah keenam dan ketujuh memperbarui interval (dalam jam) setelah itu cadangan akan diambil pada hari yang sama, durasi (dalam jam) yang jadwalnya akan berjalan.
Perintah kedelapan mendapatkan objek **RetentionPolicy** dasar per jam, lalu menyimpannya dalam variabel $retentionPolicy.
Perintah kesembilan menetapkan kebijakan durasi retensi menjadi 10 hari.
Perintah akhir membuat objek **BackupProtectionPolicy** berdasarkan jadwal dan kebijakan retensi yang dibuat oleh perintah sebelumnya.

### Contoh: 3

Membuat kebijakan perlindungan Pencadangan. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
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

### -Name
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
Anda dapat menggunakan cmdlet Get-AzRecoveryServicesBackupRetentionPolicyObject untuk mendapatkan objek **RetentionPolicy** .

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
Menentukan objek **SchedulePolicy** dasar.
Anda dapat menggunakan cmdlet Get-AzRecoveryServicesBackupSchedulePolicyObject untuk mendapatkan objek **SchedulePolicy** .

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
Jenis beban kerja sumber daya. Nilai yang dapat diterima untuk parameter ini adalah:
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.WorkloadType

### System.Nullable'1[[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType, Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.Models, Version=1.0.0.0, Culture=netral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RetentionPolicyBase

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SchedulePolicyBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PolicyBase

## NOTES

## RELATED LINKS

[Enable-AzRecoveryServicesBackupProtection](./Enable-AzRecoveryServicesBackupProtection.md)

[Get-AzRecoveryServicesBackupProtectionPolicy](./Get-AzRecoveryServicesBackupProtectionPolicy.md)

[Get-AzRecoveryServicesBackupRetentionPolicyObject](./Get-AzRecoveryServicesBackupRetentionPolicyObject.md)

[Get-AzRecoveryServicesBackupSchedulePolicyObject](./Get-AzRecoveryServicesBackupSchedulePolicyObject.md)

[Remove-AzRecoveryServicesBackupProtectionPolicy](./Remove-AzRecoveryServicesBackupProtectionPolicy.md)

[Set-AzRecoveryServicesBackupProtectionPolicy](./Set-AzRecoveryServicesBackupProtectionPolicy.md)


