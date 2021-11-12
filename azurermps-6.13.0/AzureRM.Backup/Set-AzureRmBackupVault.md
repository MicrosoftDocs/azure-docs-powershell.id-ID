---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: D57C32D1-EB4F-495E-A11B-3B4066E8C552
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/set-azurermbackupvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Set-AzureRmBackupVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Set-AzureRmBackupVault.md
ms.openlocfilehash: edb119484d397241b786ff9476b688e150ed3c6d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422195"
---
# Set-AzureRmBackupVault

## SYNOPSIS
Mengubah tipe penyimpanan vault Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmBackupVault [[-Storage] <AzureBackupVaultStorageType>] [-Vault] <AzureRMBackupVault>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmBackupVault** mengubah tipe penyimpanan vault Azure Backup.
Anda tidak dapat mengubah properti vault yang lain.

## EXAMPLES

### Contoh 1: Mengubah penyimpanan untuk vault yang sudah ada
```
PS C:\>Get-AzureRmBackupVault -Name "Vault03" | Set-AzureRmBackupVault -Storage LocallyRedundant
```

Perintah ini mendapatkan penyimpanan Azure Backup bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault.**
Perintah itu meneruskan vault itu ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini mengubah tipe penyimpanan menjadi LocallyRedundant.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Storage
Menentukan tipe penyimpanan untuk data cadangan.
Nilai yang dapat diterima untuk parameter ini adalah: LocallyRedundant dan GeoRedundant.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureBackupVaultStorageType
Parameter Sets: (All)
Aliases:
Accepted values: GeoRedundant, LocallyRedundant

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan vault Cadangan yang telah dimodifikasi cmdlet ini.
Untuk mendapatkan objek **AzureRmBackupVault,** gunakan cmdlet Get-AzureRmBackupVault cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter: Vault (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault

## CATATAN
* Saat Anda mendaftarkan server atau mesin virtual pertama untuk vault, tipe penyimpanan dikunci. Selanjutnya, Anda tidak dapat mengubah tipe penyimpanan.

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[New-AzureRmBackupVault](./New-AzureRmBackupVault.md)

[Remove-AzureRmBackupVault](./Remove-AzureRmBackupVault.md)


