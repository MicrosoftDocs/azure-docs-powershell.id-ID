---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: D614B509-82DD-42FB-B975-D72CD3355E3E
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesbackupprotectionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesBackupProtectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesBackupProtectionPolicy.md
ms.openlocfilehash: 2e82248b0d708d11564bd5472bdd232d1b223543
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145647994"
---
# Set-AzRecoveryServicesBackupProtectionPolicy

## SYNOPSIS
Memodifikasi kebijakan perlindungan Pencadangan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/set-azrecoveryservicesbackupprotectionpolicy) untuk informasi terbaru.

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
Cmdlet **Set-AzRecoveryServicesBackupProtectionPolicy** memodifikasi kebijakan perlindungan Azure Backup yang ada.
Anda dapat mengubah jadwal Pencadangan dan komponen kebijakan penyimpanan.
Setiap perubahan yang Anda buat memengaruhi pencadangan dan penyimpanan item yang terkait dengan kebijakan.
Atur konteks vault dengan menggunakan cmdlet Set-AzRecoveryServicesVaultContext sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Mengubah kebijakan perlindungan Cadangan
```powershell
$SchPol = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
$SchPol.ScheduleRunTimes.Clear()
$Time = Get-Date
$Time1 = Get-Date -Year $Time.Year -Month $Time.Month -Day $Time.Day -Hour $Time.Hour -Minute 0 -Second 0 -Millisecond 0
$Time1 = $Time1.ToUniversalTime()
$SchPol.ScheduleRunTimes.Add($Time1)
$SchPol.ScheduleRunFrequency.Clear
$SchPol.ScheduleRunDays.Add("Monday")
$SchPol.ScheduleRunFrequency="Weekly"
$RetPol = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM" 
$RetPol.IsDailyScheduleEnabled=$false
$RetPol.DailySchedule.DurationCountInDays = 0
$RetPol.IsWeeklyScheduleEnabled=$true 
$RetPol.WeeklySchedule.DaysOfTheWeek.Add("Monday")
$RetPol.WeeklySchedule.DurationCountInWeeks = 365
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "azurefiles" -Name "azurefilesvault"
$Pol= Get-AzRecoveryServicesBackupProtectionPolicy -Name "TestPolicy" -VaultId $vault.ID
$Pol.SnapshotRetentionInDays=5
Set-AzRecoveryServicesBackupProtectionPolicy -Policy $Pol -SchedulePolicy $SchPol -RetentionPolicy $RetPol
```

Berikut adalah deskripsi tingkat tinggi dari langkah-langkah yang harus diikuti untuk memodifikasi kebijakan perlindungan: 
1.  Dapatkan SchedulePolicyObject dasar dan RetentionPolicyObject dasar. Simpan dalam beberapa variabel.
2.  Atur parameter objek kebijakan jadwal dan penyimpanan yang berbeda sesuai kebutuhan Anda. Misalnya- Dalam contoh skrip di atas, kami mencoba menetapkan kebijakan perlindungan mingguan. Oleh karena itu, kami mengubah frekuensi jadwal menjadi "Mingguan" dan juga memperbarui durasi jadwal. Dalam objek kebijakan retensi, kami memperbarui durasi retensi mingguan dan mengatur bendera "jadwal mingguan diaktifkan" yang benar. Jika Anda ingin menetapkan kebijakan Harian, atur bendera "jadwal harian diaktifkan" ke true dan tetapkan nilai yang sesuai untuk parameter objek lainnya.
3.  Dapatkan kebijakan perlindungan cadangan yang ingin Anda ubah dan simpan dalam variabel. Dalam contoh di atas, kami mengambil kebijakan cadangan dengan nama "TestPolicy" yang ingin kami ubah.
4.  Ubah kebijakan perlindungan cadangan yang diambil pada langkah 3 menggunakan objek kebijakan jadwal yang dimodifikasi dan objek kebijakan penyimpanan.

### Contoh 2: Mengubah kebijakan fileshare Azure untuk beberapa cadangan per hari
```powershell
$schedulePolicy = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
$retentionPolicy = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
$timeZone = Get-TimeZone
$schedulePolicy.ScheduleRunTimeZone = $timeZone.Id
$startTime = Get-Date -Date "2021-12-22T06:00:00.00+00:00"
$schedulePolicy.ScheduleWindowStartTime = $startTime.ToUniversalTime()
$schedulePolicy.ScheduleInterval = 6
$schedulePolicy.ScheduleWindowDuration = 14
$retentionPolicy.DailySchedule.DurationCountInDays = 6
$policy = Get-AzRecoveryServicesBackupProtectionPolicy -Name "TestPolicy" -VaultId $vault.ID
Set-AzRecoveryServicesBackupProtectionPolicy -Policy $policy -VaultId $vault.ID -SchedulePolicy $schedulePolicy -RetentionPolicy $retentionPolicy
```

Berikut adalah deskripsi tingkat tinggi dari langkah-langkah yang harus diikuti untuk memodifikasi kebijakan fileshare untuk beberapa cadangan per hari: 
1.  Dapatkan SchedulePolicyObject dasar per jam dan retensi per jam dasarPolicyObject. Simpan dalam beberapa variabel.
2.  Atur parameter objek kebijakan jadwal dan penyimpanan yang berbeda sesuai kebutuhan Anda. Misalnya- Dalam contoh skrip di atas, kami mencoba mengatur $timeZone di mana kami ingin menjalankan jadwal, kami mengatur waktu mulai jadwal Per Jam, mengatur interval per jam (dalam jam), setelah itu cadangan akan diambil pada hari yang sama, durasi (dalam jam) di mana jadwal akan berjalan. Selanjutnya kami memodifikasi pengaturan retensi untuk titik pemulihan harian.
3.  Dapatkan kebijakan perlindungan cadangan yang ingin Anda ubah dan simpan dalam variabel. Dalam contoh di atas, kami mengambil kebijakan cadangan dengan nama "TestPolicy" yang ingin kami ubah.
4.  Ubah kebijakan perlindungan cadangan yang diambil pada langkah 3 menggunakan objek kebijakan jadwal yang dimodifikasi dan objek kebijakan penyimpanan.

## PARAMETERS

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

### -FixForInconsistentItems
Beralih Parameter yang menunjukkan apakah akan mencoba kembali Pembaruan Kebijakan untuk item yang gagal atau tidak.

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
Menentukan kebijakan perlindungan Cadangan yang diubah cmdlet ini.
Untuk mendapatkan objek **BackupProtectionPolicy** , gunakan cmdlet Get-AzRecoveryServicesBackupProtectionPolicy.

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
Untuk mendapatkan objek **SchedulePolicy** , gunakan objek Get-AzRecoveryServicesBackupSchedulePolicyObject.

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

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PolicyBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesBackupProtectionPolicy](./Get-AzRecoveryServicesBackupProtectionPolicy.md)

[Get-AzRecoveryServicesBackupRetentionPolicyObject](./Get-AzRecoveryServicesBackupRetentionPolicyObject.md)

[Baru-AzRecoveryServicesBackupProtectionPolicy](./New-AzRecoveryServicesBackupProtectionPolicy.md)

[Remove-AzRecoveryServicesBackupProtectionPolicy](./Remove-AzRecoveryServicesBackupProtectionPolicy.md)


