---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 44C5AF58-ADC1-4BC6-9771-3FD8F0480106
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/stop-azurermbackupjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Stop-AzureRmBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Stop-AzureRmBackupJob.md
ms.openlocfilehash: d219f49bd3fa4660048bdf5108ca660344e2bc48
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423518"
---
# Stop-AzureRmBackupJob

## SYNOPSIS
Membatalkan pekerjaan Pencadangan yang sudah ada.

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
Gunakan parameter ini untuk menghentikan pekerjaan yang membutuhkan waktu terlalu lama dan memblokir aktivitas lain.

Anda bisa membatalkan hanya tipe pekerjaan berikut ini: 

- Pencadangan
- Pulihkan

## EXAMPLES

### Contoh 1: Menghentikan pekerjaan cadangan menggunakan ID pekerjaan
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03" 
PS C:\> $Job = Get-AzureRmBackupJob -Vault $Vault -Operation Backup
PS C:\> Stop-AzureRmBackupJob -Vault $Vault -JobID $Job.InstanceId
```

Perintah pertama mengambil vault bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault.**
Perintah menyimpan objek tersebut dalam $Vault variabel.

Perintah kedua mendapatkan pekerjaan pencadangan dari vault di $Vault menggunakan cmdlet **Get-AzureRmBackupJob.**
Perintah menyimpan pekerjaan di $Job berbeda.
Dalam contoh ini, hanya ada satu operasi pencadangan di vault yang ditentukan.

Perintah terakhir menghentikan pekerjaan yang memiliki ID yang ditentukan.

### Contoh 2: Menghentikan semua operasi Pemulihan
```
PS C:\>Get-AzureRmBackupJob -Vault $Vault -Operation Restore | Stop-AzureRmBackupJob
```

Perintah ini akan mendapatkan semua operasi pemulihan di vault $Vault, lalu meneruskannya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini menghentikan setiap pekerjaan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Job
Menentukan pekerjaan yang dibatalkan cmdlet ini.
Untuk mendapatkan objek **AzureRmBackupJob,** gunakan cmdlet Get-AzureRmBackupJob cmdlet.

```yaml
Type: AzureRMBackupJob
Parameter Sets: JobFiltersSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobID
Menentukan pekerjaan yang dibatalkan cmdlet ini.
Untuk mendapatkan objek **AzureRmBackupJob,** gunakan cmdlet Get-AzureRmBackupJob cmdlet.

```yaml
Type: String
Parameter Sets: IdFiltersSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan vault Cadangan di mana cmdlet ini membatalkan pekerjaan.
Untuk mendapatkan objek **AzureRmBackupVault,** gunakan cmdlet Get-AzureRmBackupVault cmdlet.

```yaml
Type: AzureRMBackupVault
Parameter Sets: IdFiltersSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### AzureRmBackupJob

## OUTPUTS

### Tidak ada

## CATATAN

## RELATED LINKS

[Get-AzureRmBackupJob](./Get-AzureRmBackupJob.md)

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Wait-AzureRmBackupJob](./Wait-AzureRmBackupJob.md)


