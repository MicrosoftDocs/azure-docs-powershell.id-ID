---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 9882F1A5-6FFB-4DAF-8ED5-B14596BC939D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupvaultcredentials
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupVaultCredentials.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupVaultCredentials.md
ms.openlocfilehash: f35c728bfdea4da74780382aea06fb1c6458290366ead99174cdbf05de8f9919
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415423"
---
# Get-AzureRmBackupVaultCredentials

## SYNOPSIS
Mengunduh file kredensial vault untuk Vault cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupVaultCredentials [-TargetLocation] <String> [-Vault] <AzureRMBackupVault>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupVaultCredentials** mengunduh file kredensial vault untuk penyimpanan Azure Backup.
Pencadangan menggunakan file kredensial vault untuk menyambungkan server ke penyimpanan Cadangan Azure dan mendaftarkannya.
Anda harus mendaftarkan server sebelum Pencadangan dapat mengirim data cadangan ke vault.

## EXAMPLES

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

### -TargetLocation
Menentukan jalur tujuan tempat cmdlet ini menyimpan file kredensial penyimpanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan vault Cadangan tempat cmdlet ini mendapatkan file kredensial penyimpanan.
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

### System.String
Cmdlet ini mengembalikan nama file kredensial vault.

## CATATAN

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)


