---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 707A3E57-AF46-44B3-A491-89554900EF03
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupjobdetail
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupJobDetail.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupJobDetail.md
ms.openlocfilehash: 9655499578b97e3502fbbe264c8115352d004a53
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140050934"
---
# Get-AzRecoveryServicesBackupJobDetail

## SYNOPSIS

Mendapatkan detail untuk pekerjaan Pencadangan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupjobdetail) untuk informasi terkini.

## SYNTAX

### JobFilterSet (Default)
```
Get-AzRecoveryServicesBackupJobDetail [-Job] <JobBase> [-UseSecondaryRegion] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### IdFilterSet
```
Get-AzRecoveryServicesBackupJobDetail [-JobId] <String> [-UseSecondaryRegion] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesBackupJobDetail** mendapatkan detail pekerjaan Azure Backup untuk pekerjaan tertentu.
Mengatur konteks vault menggunakan parameter -VaultId.

Peringatan: Alias **Get-AzRecoveryServicesBackupJobDetails** akan dihapus di rilis perubahan yang akan datang.

## EXAMPLES

### Contoh 1: Mendapatkan detail pekerjaan Cadangan untuk pekerjaan yang gagal

```powershell
PS C:\> $vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
PS C:\> $Jobs = Get-AzRecoveryServicesBackupJob -Status Failed -VaultId $vault.ID
PS C:\> $JobDetails = Get-AzRecoveryServicesBackupJobDetail -Job $Jobs[0] -VaultId $vault.ID
PS C:\> $JobDetails.ErrorDetails
```

Perintah pertama mengambil vault yang relevan. Perintah kedua mendapatkan larik pekerjaan yang gagal dalam vault, lalu menyimpannya di $Jobs larik.
Perintah ketiga mendapatkan detail pekerjaan untuk pekerjaan pertama yang gagal di $Jobs, lalu menyimpannya di $JobDetails lain.
Perintah terakhir menampilkan detail kesalahan untuk pekerjaan yang gagal.

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

### -Job

Menentukan pekerjaan yang akan didaekan.
Untuk mendapatkan objek **BackupJob** , gunakan cmdlet **Get-AzRecoveryServicesBackupJob** .

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase
Parameter Sets: JobFilterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId

Menentukan ID pekerjaan Pencadangan.
ID adalah properti JobId dari objek **Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase** .

```yaml
Type: System.String
Parameter Sets: IdFilterSet
Aliases:

Required: True
Position: 2
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesBackupJob](./Get-AzRecoveryServicesBackupJob.md)
