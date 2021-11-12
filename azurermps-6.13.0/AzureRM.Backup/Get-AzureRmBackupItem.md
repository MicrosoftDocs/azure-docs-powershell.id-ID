---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 8A638FB1-F530-4E28-BAAE-5382671092C4
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupItem.md
ms.openlocfilehash: f0380a518353c3bc462a8a7b58012871359569a0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428450"
---
# Get-AzureRmBackupItem

## SYNOPSIS
Mendapatkan item di bawah wadah dalam Cadangkan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupItem [-ProtectionStatus <String>] [-Status <String>] [-Type <String>]
 [-Container] <AzureRMBackupContainer> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupItem** mendapatkan item dalam wadah di Azure Backup dan status proteksi item.
Mengaktifkan item untuk proteksi menggunakan cmdlet Enable-AzureRmBackupProtection.
Wadah yang terdaftar di vault Cadangan dapat memiliki satu atau beberapa item yang dapat diproteksi.
Untuk mesin virtual Azure, hanya ada satu item dalam wadah mesin virtual.

## EXAMPLES

### Contoh 1: Mendapatkan item dalam wadah
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> $Container = Get-AzureRmBackupContainer -Vault $Vault -Type AzureVM -Name "DPMSERVER.CONTOSO.COM"
PS C:\> Get-AzureRmBackupItem -Container $Container
Name                    ProtectionStatus       DataSourceStatus       RecoveryPointsCount    ProtectionPolicyName
----                    ----------------       ----------------       -------------------    --------------------
co03-vm                 NotProtected                                  0
```

Perintah pertama mendapatkan vault bernama Vault03 menggunakan cmdlet Get-AzureRmBackupVault baru.
Perintah menyimpan objek tersebut dalam $Vault variabel.
Perintah kedua mendapatkan wadah dengan nama yang ditentukan dalam penyimpanan pada $Vault menggunakan cmdlet **Get-AzureRmBackupContainer.**
Perintah menyimpan objek tersebut dalam $Container variabel.
Perintah terakhir mendapatkan item cadangan dalam wadah dalam $Container.

### Contoh 2: Menampilkan semua properti untuk sebuah item
```
PS C:\>Get-AzureRmBackupItem -Container $Container | Select-Object -Property *
Name                 : co03-vm
DataSourceStatus     : 
ProtectionStatus     : NotProtected
Type                 : AzureVM
ProtectionPolicyName : 
ProtectionPolicyId   : 
RecoveryPointsCount  : 0
ItemName             : iaasvmcontainer;co03-vm;co03-vm
ContainerType        : AzureVM
ContainerUniqueName  : iaasvmcontainer;co03-vm;co03-vm
ResourceGroupName    : resourcegroup02
ResourceName         : vault03
Location             : southeastasia
```

Perintah ini mendapatkan item cadangan dalam wadah $Container, lalu meneruskannya ke cmdlet Select-Object.
Cmdlet tersebut mengembalikan semua properti item cadangan.
Untuk informasi selengkapnya, ketik `Get-Help Select-Object` .

## PARAMETERS

### -Container
Menentukan objek wadah di mana cmdlet ini mendapatkan item cadangan.
Untuk mendapatkan **AzureRmBackupContainer,** gunakan cmdlet Get-AzureRmBackupContainer cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupContainer
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -ProtectionStatus
Menentukan status proteksi keseluruhan item dalam wadah.
Nilai yang dapat diterima untuk parameter ini adalah:
- Diproteksi 
- Melindungi  
- NotProtected

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Protected, Protecting, NotProtected

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Menentukan status cadangan untuk sebuah item.
Nilai yang dapat diterima untuk parameter ini adalah: IRPending, Protected, ProtectionError, dan ProtectionStopped.
Jika parameter *ProtectionStatus* memiliki nilai Protected, Anda dapat menggunakan nilai parameter *Status* untuk memfilter item.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: IRPending, ProtectionStopped, ProtectionError, Protected

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe item yang akan didaurkan cmdlet ini.
Saat ini, satu-satunya nilai yang didukung adalah AzureVM.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: AzureVM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupContainer
Parameter: Container (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupItem

## CATATAN

## RELATED LINKS

[Backup-AzureRmBackupItem](./Backup-AzureRmBackupItem.md)

[Disable-AzureRmBackupProtection](./Disable-AzureRmBackupProtection.md)

[Enable-AzureRmBackupProtection](./Enable-AzureRmBackupProtection.md)

[Get-AzureRmBackupContainer](./Get-AzureRmBackupContainer.md)

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Restore-AzureRmBackupItem](./Restore-AzureRmBackupItem.md)


