---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: DD150A2C-27D5-4119-9B43-FAB82F9F7D5B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/enable-azurermbackupprotection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Enable-AzureRmBackupProtection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Enable-AzureRmBackupProtection.md
ms.openlocfilehash: c66eda488b0b7876317b02db279202a88bbcc3d7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141780364"
---
# Enable-AzureRmBackupProtection

## SYNOPSIS
Mengaitkan item dengan kebijakan proteksi Azure Backup.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Enable-AzureRmBackupProtection -Policy <AzureRMBackupProtectionPolicy>
 [-Item] <AzureRMBackupContainerContextObject> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzureRmBackupProtection** mengaitkan item dengan kebijakan proteksi Azure Backup.
Untuk mengaktifkan kebijakan proteksi, Anda harus terlebih dahulu memiliki item cadangan yang sudah ada dan kebijakan yang sudah ada.
Keduanya harus memiliki kubah Cadangan yang sama.
Jadwal cadangan melakukan salinan awal penuh untuk item dan salinan tambahan untuk cadangan berikutnya.

## EXAMPLES

### Contoh 1: Aktifkan proteksi di mesin virtual Azure
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> $Policy = Get-AzureRmBackupProtectionPolicy -Vault $Vault -Name "DefaultPolicy"
PS C:\> Get-AzureRmBackupContainer -Vault $Vault -Type AzureVM -Status Registered | Get-AzureRmBackupItem | Enable-AzureRmBackupProtection -Policy $Policy
WorkloadName    Operation        Status          StartTime              EndTime
------------    ---------        ------          ---------              -------
co03-vm         ConfigureBackup  Completed       26-Aug-15 12:19:49 PM  26-Aug-15 12:19:54 PM
```

Perintah pertama mendapatkan kubah bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault** .
Perintah menyimpan objek tersebut dalam variabel $Vault.
Perintah kedua mendapatkan kebijakan Proteksi cadangan bernama DefaultPolicy untuk kubah di $Vault.
Perintah menyimpan objek tersebut dalam variabel $Policy.
Perintah akhir menggunakan operator saluran untuk meneruskan nilai dari satu cmdlet ke cmdlet berikutnya.
Ini mendapatkan wadah, dengan menggunakan cmdlet Get-AzureRmBackupContainer.
Perintah mendapatkan item cadangan dari wadah tersebut menggunakan cmdlet Get-AzureRmBackupItem.
Cmdlet saat ini memungkinkan kebijakan yang disimpan di $Policy untuk item yang dilewati perintah ke cmdlet tersebut.

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

### -Item
Menentukan item Cadangan di mana cmdlet ini mengaktifkan proteksi.
Untuk mendapatkan **AzureRmBackupItem**, gunakan cmdlet Get-AzureRmBackupItem.

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
Menentukan kebijakan proteksi yang terkait dengan cmdlet ini dengan item.
Untuk mendapatkan objek **AzureRmBackupProtectionPolicy** , gunakan cmdlet Get-AzureRmBackupProtectionPolicy.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupContainerContextObject
Parameter: Item (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob

## CATATAN

## RELATED LINKS

[Backup-AzureRmBackupItem](./Backup-AzureRmBackupItem.md)

[Get-AzureRmBackupItem](./Get-AzureRmBackupItem.md)

[Get-AzureRmBackupProtectionPolicy](./Get-AzureRmBackupProtectionPolicy.md)


