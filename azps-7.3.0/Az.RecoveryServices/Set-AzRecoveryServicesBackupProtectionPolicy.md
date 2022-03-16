---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: D614B509-82DD-42FB-B975-D72CD3355E3E
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesbackupprotectionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesBackupProtectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesBackupProtectionPolicy.md
ms.openlocfilehash: 0f38644bf8ae3db9a4720cb6e8774b213e695855
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140204695"
---
# Set-AzRecoveryServicesBackupProtectionPolicy

## SYNOPSIS
Mengubah kebijakan Proteksi cadangan.

## SYNTAX

### ModifyPolicyParamSet
```
Set-AzRecoveryServicesBackupProtectionPolicy [-Policy] <PolicyBase> [[-RetentionPolicy] <RetentionPolicyBase>]
 [[-SchedulePolicy] <SchedulePolicyBase>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FixPolicyParamSet
```
Set-AzRecoveryServicesBackupProtectionPolicy [-Policy] <PolicyBase> [-FixForInconsistentItems]
 [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzRecoveryServicesBackupProtectionPolicy** mengubah kebijakan perlindungan Azure Backup yang sudah ada.
Anda bisa memodifikasi komponen kebijakan penyimpanan dan jadwal cadangan.
Setiap perubahan yang Anda buat mempengaruhi pencadangan dan penyimpanan item yang terkait dengan kebijakan tersebut.
Mengatur konteks vault menggunakan cmdlet Set-AzRecoveryServicesVaultContext cmdlet sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Mengubah kebijakan proteksi Cadangan
```
PS C:\> $SchPol = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
PS C:\> $SchPol.ScheduleRunTimes.Clear()
PS C:\> $Time = Get-Date
PS C:\> $Time1 = Get-Date -Year $Time.Year -Month $Time.Month -Day $Time.Day -Hour $Time.Hour -Minute 0 -Second 0 -Millisecond 0
PS C:\> $Time1 = $Time1.ToUniversalTime()
PS C:\> $SchPol.ScheduleRunTimes.Add($Time1)
PS C:\> $SchPol.ScheduleRunFrequency.Clear
PS C:\> $SchPol.ScheduleRunDays.Add("Monday")
PS C:\> $SchPol.ScheduleRunFrequency="Weekly"
PS C:\> $RetPol = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM" 
PS C:\> $RetPol.IsDailyScheduleEnabled=$false
PS C:\> $RetPol.DailySchedule.DurationCountInDays = 0
PS C:\> $RetPol.IsWeeklyScheduleEnabled=$true 
PS C:\> $RetPol.WeeklySchedule.DaysOfTheWeek.Add("Monday")
PS C:\> $RetPol.WeeklySchedule.DurationCountInWeeks = 365
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "azurefiles" -Name "azurefilesvault"
PS C:\> $Pol= Get-AzRecoveryServicesBackupProtectionPolicy -Name "TestPolicy" -VaultId $vault.ID
PS C:\> $Pol.SnapshotRetentionInDays=5
PS C:\> Set-AzRecoveryServicesBackupProtectionPolicy -Policy $Pol -SchedulePolicy $SchPol -RetentionPolicy $RetPol
```

Berikut adalah deskripsi tingkat tinggi tentang langkah-langkah yang akan diikuti untuk mengubah kebijakan proteksi: 
1.  Dapatkan dasar SchedulePolicyObject dan basis RetentionPolicyObject. Simpan nilai dalam variabel tertentu.
2.  Set the different parameters of schedule and retention policy object as per your requirement. Misalnya, dalam contoh skrip di atas, kami mencoba menetapkan kebijakan perlindungan mingguan. Karenanya, kami mengubah frekuensi jadwal menjadi "Mingguan" dan juga memperbarui waktu berjalan jadwal. Dalam objek kebijakan penyimpanan, kami memperbarui durasi penyimpanan mingguan dan menyetel bendera "jadwal mingguan diaktifkan" yang benar. Jika Anda ingin menetapkan kebijakan Harian, setel bendera "jadwal harian diaktifkan" ke benar dan menetapkan nilai yang tepat untuk parameter objek lainnya.
3.  Dapatkan kebijakan proteksi cadangan yang ingin Anda ubah dan simpan dalam variabel. Dalam contoh di atas, kami mengambil kebijakan cadangan dengan nama "TestPolicy" yang ingin kami ubah.
4.  Ubah kebijakan proteksi cadangan yang diambil di langkah 3 menggunakan objek kebijakan jadwal yang diubah dan objek kebijakan penyimpanan.

### Contoh 2: Ubah kebijakan berbagi file Azure untuk beberapa cadangan per hari
```powershell
PS C:\> $schedulePolicy = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
PS C:\> $retentionPolicy = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
PS C:\> $timeZone = Get-TimeZone
PS C:\> $schedulePolicy.ScheduleRunTimeZone = $timeZone.Id
PS C:\> $startTime = Get-Date -Date "2021-12-22T06:00:00.00+00:00"
PS C:\> $schedulePolicy.ScheduleWindowStartTime = $startTime.ToUniversalTime()
PS C:\> $schedulePolicy.ScheduleInterval = 6
PS C:\> $schedulePolicy.ScheduleWindowDuration = 14
PS C:\> $retentionPolicy.DailySchedule.DurationCountInDays = 6
PS C:\> $policy = Get-AzRecoveryServicesBackupProtectionPolicy -Name "TestPolicy" -VaultId $vault.ID
PS C:\> Set-AzRecoveryServicesBackupProtectionPolicy -Policy $policy -VaultId $vault.ID -SchedulePolicy $schedulePolicy -RetentionPolicy $retentionPolicy
```

Berikut adalah deskripsi tingkat tinggi dari langkah-langkah yang akan diikuti untuk mengubah kebijakan berbagi file untuk beberapa cadangan per hari: 
1.  Dapatkan base hourly SchedulePolicyObject dan base hourly RetentionPolicyObject. Simpan nilai dalam variabel tertentu.
2.  Set the different parameters of schedule and retention policy object as per your requirement. Misalnya- Dalam skrip contoh di atas, kami mencoba mengatur $timeZone di mana kami ingin menjalankan jadwal, kami mengatur waktu mulai jadwal Per jam, mengatur interval per jam (dalam jam), setelah itu cadangan akan dicoba lagi pada hari yang sama, durasi (dalam jam) di mana jadwal akan dijalankan. Berikutnya kami mengubah pengaturan penyimpanan untuk poin pemulihan harian.
3.  Dapatkan kebijakan proteksi cadangan yang ingin Anda ubah dan simpan dalam variabel. Dalam contoh di atas, kami mengambil kebijakan cadangan dengan nama "TestPolicy" yang ingin kami ubah.
4.  Ubah kebijakan proteksi cadangan yang diambil di langkah 3 menggunakan objek kebijakan jadwal yang diubah dan objek kebijakan penyimpanan.

## PARAMETERS

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

### -FixForInconsistentItems
Ubah Parameter yang menunjukkan apakah Anda perlu mencoba kembali Pembaruan Kebijakan untuk item yang gagal.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FixPolicyParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kebijakan
Menentukan kebijakan Proteksi cadangan yang ditentukan cmdlet ini.
Untuk mendapatkan objek **BackupProtectionPolicy** , gunakan cmdlet Get-AzRecoveryServicesBackupProtectionPolicy baru.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PolicyBase
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RetentionPolicy
Menentukan kebijakan penyimpanan dasar.
Untuk mendapatkan objek **RetentionPolicy** , gunakan cmdlet Get-AzRecoveryServicesBackupRetentionPolicyObject.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RetentionPolicyBase
Parameter Sets: ModifyPolicyParamSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SchedulePolicy
Menentukan objek kebijakan jadwal dasar.
Untuk mendapatkan objek **SchedulePolicy** , gunakan Get-AzRecoveryServicesBackupSchedulePolicyObject Anda.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SchedulePolicyBase
Parameter Sets: ModifyPolicyParamSet
Aliases:

Required: False
Position: 3
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

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PolicyBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesBackupProtectionPolicy](./Get-AzRecoveryServicesBackupProtectionPolicy.md)

[Get-AzRecoveryServicesBackupRetentionPolicyObject](./Get-AzRecoveryServicesBackupRetentionPolicyObject.md)

[New-AzRecoveryServicesBackupProtectionPolicy](./New-AzRecoveryServicesBackupProtectionPolicy.md)

[Remove-AzRecoveryServicesBackupProtectionPolicy](./Remove-AzRecoveryServicesBackupProtectionPolicy.md)


