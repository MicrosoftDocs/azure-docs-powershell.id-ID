---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: E247C6DF-B53D-487E-AAA2-551FCBFD77E7
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupschedulepolicyobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupSchedulePolicyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupSchedulePolicyObject.md
ms.openlocfilehash: 8d37e4d9d0afa18b037985d3a02d261771e18e53
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143117441"
---
# Get-AzRecoveryServicesBackupSchedulePolicyObject

## SYNOPSIS
Mendapatkan objek kebijakan jadwal dasar.

## SYNTAX

```
Get-AzRecoveryServicesBackupSchedulePolicyObject [-WorkloadType] <WorkloadType>
 [[-BackupManagementType] <BackupManagementType>] [-DefaultProfile <IAzureContextContainer>]
 [[-ScheduleRunFrequency] <ScheduleRunType>] [[-PolicySubType] <PSPolicyType>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRecoveryServicesBackupSchedulePolicyObject** mendapatkan basis **AzureRMRecoveryServicesSchedulePolicyObject**.
Obyek ini tidak tetap ada dalam sistem.
Ini adalah objek sementara yang dapat Anda manipulasi dan gunakan dengan cmdlet New-AzRecoveryServicesBackupProtectionPolicy untuk membuat kebijakan perlindungan cadangan baru.

## EXAMPLES

### Contoh 1: Mengatur frekuensi jadwal ke mingguan
```powershell
$RetPol = Get-AzRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM" 
$SchPol = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
$SchPol.ScheduleRunFrequency = "Weekly"
New-AzRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $RetPol -SchedulePolicy $SchPol
```

Perintah pertama mendapatkan objek kebijakan penyimpanan, lalu menyimpannya dalam variabel $RetPol.
Perintah kedua mendapatkan objek kebijakan jadwal, lalu menyimpannya dalam variabel $SchPol.
Perintah ketiga mengubah frekuensi kebijakan jadwal menjadi mingguan.
Perintah terakhir membuat kebijakan proteksi cadangan dengan jadwal yang diperbarui.

### Contoh 2: Atur waktu pencadangan
```powershell
$SchPol = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
$SchPol.ScheduleRunTimes.RemoveAll()
$DT = Get-Date
$SchPol.ScheduleRunTimes.Add($DT.ToUniversalTime())
New-AzRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $RetPol -SchedulePolicy $SchPol
```

Perintah pertama mendapatkan objek kebijakan jadwal, lalu menyimpannya dalam variabel $SchPol.
Perintah kedua menghapus semua waktu jalankan terjadwal dari $SchPol.
Perintah ketiga mendapatkan tanggal dan waktu saat ini, lalu menyimpannya dalam variabel $DT.
Perintah keempat menggantikan waktu jalankan terjadwal dengan waktu saat ini.
Anda hanya dapat mencadangkan AzureVM sekali per hari, jadi untuk mengatur ulang waktu pencadangan, Anda harus mengganti jadwal asli.
Perintah terakhir membuat kebijakan proteksi cadangan menggunakan jadwal baru.

### Contoh 3: Dapatkan jadwal per jam untuk kebijakan filehare
```powershell
$schedulePolicy = Get-AzRecoveryServicesBackupSchedulePolicyObject -WorkloadType AzureFiles -BackupManagementType AzureStorage -ScheduleRunFrequency Hourly
$timeZone = Get-TimeZone
$schedulePolicy.ScheduleRunTimeZone = $timeZone.Id
$startTime = Get-Date -Date "2021-12-22T06:00:00.00+00:00"
$schedulePolicy.ScheduleWindowStartTime = $startTime.ToUniversalTime()
$schedulePolicy.ScheduleInterval = 6
$schedulePolicy.ScheduleWindowDuration = 14
```

Perintah pertama mendapatkan **SchedulePolicyObject** basis jam, lalu menyimpannya dalam variabel $schedulePolicy.
Perintah kedua dan ketiga mengambil zona waktu dan memperbarui zona waktu dalam $schedulePolicy.
Perintah keempat dan kelima menginisialisasi waktu mulai jendela jadwal dan memperbarui $schedulePolicy. Harap diperhatikan bahwa waktu mulai harus berada di UTC meskipun zona waktunya tidak UTC. Perintah keenam dan ketujuh memperbarui interval (dalam jam) setelah itu cadangan akan diambil pada hari yang sama, durasi (dalam jam) yang jadwalnya akan berjalan.

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
Position: 1
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

### -PolicySubType
Jenis kebijakan jadwal yang akan disambungkan: Standar, Ditingkatkan

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.PSPolicyType
Parameter Sets: (All)
Aliases:
Accepted values: Standard, Enhanced

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleRunFrequency
Jadwalkan frekuensi jalankan untuk jadwal kebijakan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ScheduleRunType
Parameter Sets: (All)
Aliases:
Accepted values: Daily, Hourly, Weekly

Required: False
Position: 2
Default value: None
Accept pipeline input: False
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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SchedulePolicyBase

## NOTES

## RELATED LINKS

[New-AzRecoveryServicesBackupProtectionPolicy](./New-AzRecoveryServicesBackupProtectionPolicy.md)

[Set-AzRecoveryServicesBackupProtectionPolicy](./Set-AzRecoveryServicesBackupProtectionPolicy.md)


