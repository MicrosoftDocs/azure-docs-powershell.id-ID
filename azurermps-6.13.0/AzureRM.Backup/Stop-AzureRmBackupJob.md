---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 44C5AF58-ADC1-4BC6-9771-3FD8F0480106
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/stop-azurermbackupjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Stop-AzureRmBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Stop-AzureRmBackupJob.md
ms.openlocfilehash: 800b5c6e04e0842113db7fb3494815bcd97ebfb9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142100772"
---
# Stop-AzureRmBackupJob

## SYNOPSIS
Membatalkan tugas Pencadangan yang sudah ada.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### IdFiltersSet
```
Stop-AzureRmBackupJob -Vault <AzureRMBackupVault> -JobID <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### JobFiltersSet
```
Stop-AzureRmBackupJob -Job <AzureRMBackupJob> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureRmBackupJob** membatalkan pekerjaan Azure Backup yang sudah ada.
Gunakan parameter ini untuk menghentikan pekerjaan yang memakan waktu terlalu lama dan memblokir aktivitas lainnya.
Anda hanya dapat membatalkan jenis pekerjaan berikut: 
- Cadangan
- Mengembalikan

## EXAMPLES

### Contoh 1: Menghentikan pekerjaan pencadangan dengan menggunakan ID pekerjaan
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03" 
PS C:\> $Job = Get-AzureRmBackupJob -Vault $Vault -Operation Backup
PS C:\> Stop-AzureRmBackupJob -Vault $Vault -JobID $Job.InstanceId
```

Perintah pertama mendapatkan kubah bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault** .
Perintah menyimpan objek tersebut dalam variabel $Vault.
Perintah kedua mendapatkan pekerjaan cadangan dari kubah di $Vault menggunakan cmdlet **Get-AzureRmBackupJob** .
Perintah menyimpan pekerjaan dalam variabel $Job.
Dalam contoh ini, hanya ada satu operasi pencadangan dalam kubah yang ditentukan.
Perintah terakhir menghentikan pekerjaan yang memiliki ID yang ditentukan.

### Contoh 2: Hentikan semua operasi Pemulihan
```
PS C:\>Get-AzureRmBackupJob -Vault $Vault -Operation Restore | Stop-AzureRmBackupJob
```

Perintah ini mendapatkan semua operasi pemulihan dalam kubah di $Vault, lalu meneruskannya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini menghentikan setiap pekerjaan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Job
Menentukan pekerjaan yang cmdlet ini batalkan.
Untuk mendapatkan objek **AzureRmBackupJob** , gunakan cmdlet Get-AzureRmBackupJob.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob
Parameter Sets: JobFiltersSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobID
Menentukan pekerjaan yang cmdlet ini batalkan.
Untuk mendapatkan objek **AzureRmBackupJob** , gunakan cmdlet Get-AzureRmBackupJob.

```yaml
Type: System.String
Parameter Sets: IdFiltersSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan kubah Cadangan tempat cmdlet ini membatalkan pekerjaan.
Untuk mendapatkan objek **AzureRmBackupVault** , gunakan cmdlet Get-AzureRmBackupVault.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter Sets: IdFiltersSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob
Parameter: Job (ByValue)

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzureRmBackupJob](./Get-AzureRmBackupJob.md)

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Tunggu-AzureRmBackupJob](./Wait-AzureRmBackupJob.md)


