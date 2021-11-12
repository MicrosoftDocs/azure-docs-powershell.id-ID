---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 6778E018-B6CC-468A-823E-3DA047EA6B52
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackuprecoverypoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupRecoveryPoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupRecoveryPoint.md
ms.openlocfilehash: f82abc45a9b78093c13764ab0eb28f2593c7fabb
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426334"
---
# Get-AzureRmBackupRecoveryPoint

## SYNOPSIS
Dapatkan poin pemulihan untuk item yang dicadangkan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupRecoveryPoint [[-RecoveryPointId] <String>] [-Item] <AzureRMBackupItem>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupRecoveryPoint** mendapatkan poin pemulihan untuk item Cadangan Azure yang dicadangkan.
Setelah item dicadangkan, Cadangkan menyimpan satu atau beberapa poin pemulihan.

## EXAMPLES

### Contoh 1: Dapatkan poin pemulihan untuk sebuah item
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> $Container = Get-AzureRmBackupContainer -Vault $Vault -Type AzureVM -Name "DPMSERVER.CONTOSO.COM"
PS C:\> $BackupItem = Get-AzureRmBackupItem -Container $Container
PS C:\> Get-AzureRmBackupRecoveryPoint -Item $BackupItem
RecoveryPointId    RecoveryPointType  RecoveryPointTime      ContainerName
---------------    -----------------  -----------------      -------------
15273496567119     AppConsistent      26-Aug-15 12:27:38 PM  iaasvmcontainer;conto02-vm;conto0...
```

Perintah pertama mendapatkan vault bernama Vault03 menggunakan cmdlet Get-AzureRmBackupVault baru.
Perintah menyimpan objek tersebut dalam $Vault variabel.
Perintah kedua mendapatkan wadah dengan nama yang ditentukan dalam penyimpanan pada $Vault menggunakan cmdlet **Get-AzureRmBackupContainer.**
Perintah menyimpan objek tersebut dalam $Container variabel.
Perintah ketiga mendapatkan item cadangan dalam wadah pada $Container dengan menggunakan cmdlet **Get-AzureRmBackupItem.**
Perintah menyimpan objek tersebut dalam $BackupItem variabel.
Perintah terakhir mendapatkan poin pemulihan untuk item tersebut dalam $BackupItem.

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

### -Item
Menentukan item di mana cmdlet ini mendapatkan poin pemulihan.
Untuk mendapatkan **AzureRmBackupItem,** gunakan cmdlet Get-AzureRmBackupItem cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupItem
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPointId
Menentukan ID titik pemulihan yang akan didaurkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupItem
Parameter: Item (MenurutNilai)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupRecoveryPoint

## CATATAN

## RELATED LINKS

[Get-AzureRmBackupContainer](./Get-AzureRmBackupContainer.md)

[Get-AzureRmBackupItem](./Get-AzureRmBackupItem.md)

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)


