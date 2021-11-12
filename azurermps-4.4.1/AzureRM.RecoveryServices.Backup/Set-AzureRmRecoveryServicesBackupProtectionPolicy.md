---
external help file: Microsoft.Azure.Commands.RecoveryServices.Backup.dll-Help.xml
Module Name: AzureRM.RecoveryServices.Backup
ms.assetid: D614B509-82DD-42FB-B975-D72CD3355E3E
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Set-AzureRmRecoveryServicesBackupProtectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.Backup/Commands.RecoveryServices.Backup/help/Set-AzureRmRecoveryServicesBackupProtectionPolicy.md
ms.openlocfilehash: f17ce0a23c2b91cd00f2a12bb2451c4e235169ce
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422724"
---
# Set-AzureRmRecoveryServicesBackupProtectionPolicy

## SYNOPSIS
Mengubah kebijakan Proteksi cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmRecoveryServicesBackupProtectionPolicy [-Policy] <PolicyBase>
 [[-RetentionPolicy] <RetentionPolicyBase>] [[-SchedulePolicy] <SchedulePolicyBase>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmBackupProtectionPolicy** mengubah kebijakan proteksi Azure Backup yang sudah ada.
Anda bisa memodifikasi komponen kebijakan penyimpanan dan jadwal cadangan.

Setiap perubahan yang Anda buat mempengaruhi pencadangan dan penyimpanan item yang terkait dengan kebijakan tersebut.

Mengatur konteks vault menggunakan cmdlet Set-AzureRmRecoveryServicesVaultContext cmdlet sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Mengubah kebijakan proteksi Cadangan
```
PS C:\>$SchPol = Get-AzureRmRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
PS C:\> $SchPol.ScheduleRunTimes.RemoveAll()
PS C:\> $DT = Get-Date
PS C:\> $SchPol.ScheduleRunTimes.Add($DT.ToUniversalTime())
PS C:\> $RetPol = Get-AzureRmRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM" 
PS C:\> $RetPol.DailySchedule.DurationCountInDays = 365
PS C:\> $Pol = Get-AzureRmRecoveryServicesBackupProtectionPolicy -Name "NewPolicy"
PS C:\> Set-AzureRmRecoveryServicesBackupProtectionPolicy -Policy $Pol -SchedulePolicy $SchPol -RetentionPolicy $RetPol
```

Perintah pertama mendapatkan objek SchedulePolicy dasar, lalu menyimpannya dalam $SchPol variabel.

Perintah kedua menghapus semua waktu jalankan terjadwal dari kebijakan jadwal di $SchPol.

Perintah ketiga menggunakan cmdlet Get-Date cmdlet untuk mendapatkan tanggal dan waktu saat ini, lalu menyimpannya dalam $DT variabel.

Perintah keempat menambahkan tanggal dan waktu dalam $DT waktu berjalan sesuai jadwal untuk kebijakan jadwal.

Perintah kelima mendapatkan objek kebijakan penyimpanan dasar, lalu menyimpannya di $RetPol penyimpanan.

Perintah keenam mengatur durasi penyimpanan ke 365 hari.

Perintah ketujuh mendapatkan kebijakan Proteksi cadangan bernama NewPolicy, lalu menyimpannya dalam $Pol baru.

Perintah final mengubah kebijakan proteksi Pencadangan di $Pol menggunakan kebijakan jadwal di $SchPol dan kebijakan penyimpanan di $RetPol.

## PARAMETERS

### -Kebijakan
Menentukan kebijakan Proteksi cadangan yang ditentukan cmdlet ini.
Untuk mendapatkan objek **BackupProtectionPolicy,** gunakan cmdlet Get-AzureRmRecoveryServicesBackupProtectionPolicy.

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
Untuk mendapatkan objek **RetentionPolicy,** gunakan cmdlet Get-AzureRmRecoveryServicesBackupRetentionPolicyObject.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RetentionPolicyBase
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SchedulePolicy
Menentukan objek kebijakan jadwal dasar.
Untuk mendapatkan objek **SchedulePolicy,** gunakan Get-AzureRmRecoveryServicesBackupSchedulePolicyObject Anda.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SchedulePolicyBase
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### PolicyBase
Parameter 'Policy' menerima nilai tipe 'PolicyBase' dari saluran

## OUTPUTS

### System.Collections.Generic.List'1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase]

## CATATAN

## RELATED LINKS

[Get-AzureRmRecoveryServicesBackupProtectionPolicy](./Get-AzureRmRecoveryServicesBackupProtectionPolicy.md)

[Get-AzureRmRecoveryServicesBackupRetentionPolicyObject](./Get-AzureRmRecoveryServicesBackupRetentionPolicyObject.md)

[New-AzureRmRecoveryServicesBackupProtectionPolicy](./New-AzureRmRecoveryServicesBackupProtectionPolicy.md)

[Remove-AzureRmRecoveryServicesBackupProtectionPolicy](./Remove-AzureRmRecoveryServicesBackupProtectionPolicy.md)


