---
external help file: Microsoft.Azure.Commands.RecoveryServices.Backup.dll-Help.xml
Module Name: AzureRM.RecoveryServices.Backup
ms.assetid: E247C6DF-B53D-487E-AAA2-551FCBFD77E7
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.recoveryservices.backup/get-azurermrecoveryservicesbackupschedulepolicyobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices/Commands.RecoveryServices.Backup/help/Get-AzureRmRecoveryServicesBackupSchedulePolicyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices/Commands.RecoveryServices.Backup/help/Get-AzureRmRecoveryServicesBackupSchedulePolicyObject.md
ms.openlocfilehash: cc65ea2b2f050eb356d5be22c935aebb131f5cfe
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142855414"
---
# Get-AzureRmRecoveryServicesBackupSchedulePolicyObject

## SYNOPSIS
Mendapatkan objek kebijakan jadwal dasar.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmRecoveryServicesBackupSchedulePolicyObject [-WorkloadType] <WorkloadType>
 [[-BackupManagementType] <BackupManagementType>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmRecoveryServicesBackupSchedulePolicyObject** mendapatkan basis **AzureRMRecoveryServicesSchedulePolicyObject**.
Obyek ini tidak tetap ada dalam sistem.
Ini adalah objek sementara yang dapat Anda manipulasi dan gunakan dengan cmdlet New-AzureRmRecoveryServicesBackupProtectionPolicy untuk membuat kebijakan perlindungan cadangan baru.

## EXAMPLES

### Contoh 1: Mengatur frekuensi jadwal ke mingguan
```
PS C:\>$RetPol = Get-AzureRmRecoveryServicesBackupRetentionPolicyObject -WorkloadType "AzureVM" 
PS C:\> $SchPol = Get-AzureRmRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
PS C:\> $SchPol.ScheduleRunFrequency = "Weekly"
PS C:\> New-AzureRmRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $RetPol -SchedulePolicy $SchPol
```

Perintah pertama mendapatkan objek kebijakan penyimpanan, lalu menyimpannya dalam variabel $RetPol.
Perintah kedua mendapatkan objek kebijakan jadwal, lalu menyimpannya dalam variabel $SchPol.
Perintah ketiga mengubah frekuensi kebijakan jadwal menjadi mingguan.
Perintah terakhir membuat kebijakan proteksi cadangan dengan jadwal yang diperbarui.

### Contoh 2: Atur waktu pencadangan
```
PS C:\>$SchPol = Get-AzureRmRecoveryServicesBackupSchedulePolicyObject -WorkloadType "AzureVM" 
PS C:\> $SchPol.ScheduleRunTimes.RemoveAll()
PS C:\> $DT = Get-Date
PS C:\> $SchPol.ScheduleRunTimes.Add($DT.ToUniversalTime())
PS C:\> New-AzureRmRecoveryServicesBackupProtectionPolicy -Name "NewPolicy" -WorkloadType AzureVM -RetentionPolicy $RetPol -SchedulePolicy $SchPol
```

Perintah pertama mendapatkan objek kebijakan jadwal, lalu menyimpannya dalam variabel $SchPol.
Perintah kedua menghapus semua waktu jalankan terjadwal dari $SchPol.
Perintah ketiga mendapatkan tanggal dan waktu saat ini, lalu menyimpannya dalam variabel $DT.
Perintah keempat menggantikan waktu jalankan terjadwal dengan waktu saat ini.
Anda hanya dapat mencadangkan AzureVM sekali per hari, jadi untuk mengatur ulang waktu pencadangan, Anda harus mengganti jadwal asli.
Perintah terakhir membuat kebijakan proteksi cadangan menggunakan jadwal baru.

## PARAMETERS

### -BackupManagementType
Menentukan tipe manajemen Pencadangan.
Nilai yang dapat diterima untuk parameter ini adalah:
- AzureVM 
- AzureSQLDatabase
- AzureStorage

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.BackupManagementType]
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, MARS, SCDPM, AzureBackupServer, AzureSQL, AzureStorage

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -WorkloadType
Menentukan tipe beban kerja.
Nilai yang dapat diterima untuk parameter ini adalah:
- AzureVM 
- AzureSQLDatabase
- AzureFiles

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.WorkloadType
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM, AzureSQLDatabase, AzureFiles

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.SchedulePolicyBase

## NOTES

## RELATED LINKS

[New-AzureRmRecoveryServicesBackupProtectionPolicy](./New-AzureRmRecoveryServicesBackupProtectionPolicy.md)

[Set-AzureRmRecoveryServicesBackupProtectionPolicy](./Set-AzureRmRecoveryServicesBackupProtectionPolicy.md)


