---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: DD150A2C-27D5-4119-9B43-FAB82F9F7D5B
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Enable-AzureRmBackupProtection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Enable-AzureRmBackupProtection.md
ms.openlocfilehash: c479869cb150633ca926542552fab2aa7dc80b90
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426876"
---
# Enable-AzureRmBackupProtection

## SYNOPSIS
Mengaitkan item dengan kebijakan proteksi Cadangan Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Enable-AzureRmBackupProtection -Policy <AzureRMBackupProtectionPolicy>
 [-Item] <AzureRMBackupContainerContextObject> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzureRmBackupProtection** mengaitkan item dengan kebijakan proteksi Azure Backup.
Untuk mengaktifkan kebijakan proteksi, Anda harus terlebih dahulu memiliki item cadangan dan kebijakan yang sudah ada.
Keduanya harus berada di vault Cadangan yang sama.
Jadwal pencadangan melakukan salinan awal penuh untuk item dan salinan tambahan untuk cadangan berikutnya.

## EXAMPLES

### Contoh 1: Mengaktifkan perlindungan di komputer virtual Azure
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> $Policy = Get-AzureRmBackupProtectionPolicy -Vault $Vault -Name "DefaultPolicy"
PS C:\> Get-AzureRmBackupContainer -Vault $Vault -Type AzureVM -Status Registered | Get-AzureRmBackupItem | Enable-AzureRmBackupProtection -Policy $Policy
WorkloadName    Operation        Status          StartTime              EndTime
------------    ---------        ------          ---------              -------
co03-vm         ConfigureBackup  Completed       26-Aug-15 12:19:49 PM  26-Aug-15 12:19:54 PM
```

Perintah pertama mengambil vault bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault.**
Perintah menyimpan objek tersebut dalam $Vault variabel.

Perintah kedua mendapatkan kebijakan Proteksi cadangan yang bernama DefaultPolicy untuk penyimpanan di $Vault.
Perintah menyimpan objek tersebut dalam $Policy variabel.

Perintah final menggunakan operator pipeline untuk meneruskan nilai dari satu cmdlet ke cmdlet berikutnya.
Perintah ini mendapatkan wadah, dengan menggunakan Get-AzureRmBackupContainer cmdlet.
Perintah akan mendapatkan item cadangan dari wadah tersebut menggunakan cmdlet Get-AzureRmBackupItem.
Cmdlet saat ini mengaktifkan kebijakan yang disimpan $Policy untuk item yang dilewati perintah ke cmdlet tersebut.

## PARAMETERS

### -Item
Menentukan item Cadangan yang memungkinkan proteksi oleh cmdlet ini.
Untuk mendapatkan **AzureRmBackupItem,** gunakan cmdlet Get-AzureRmBackupItem cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupContainerContextObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Kebijakan
Menentukan kebijakan proteksi bahwa cmdlet ini terkait dengan item.
Untuk mendapatkan objek **AzureRmBackupProtectionPolicy,** gunakan cmdlet Get-AzureRmBackupProtectionPolicy baru.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupProtectionPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

### AzureRmBackupItem

## OUTPUTS

### AzureRmBackupJob

## CATATAN

## RELATED LINKS

[Backup-AzureRmBackupItem](./Backup-AzureRmBackupItem.md)

[Get-AzureRmBackupItem](./Get-AzureRmBackupItem.md)

[Get-AzureRmBackupProtectionPolicy](./Get-AzureRmBackupProtectionPolicy.md)


