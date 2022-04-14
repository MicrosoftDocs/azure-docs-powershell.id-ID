---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 8A638FB1-F530-4E28-BAAE-5382671092C4
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupItem.md
ms.openlocfilehash: f0380a518353c3bc462a8a7b58012871359569a0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141845006"
---
# Get-AzureRmBackupItem

## SYNOPSIS
Mendapatkan item di bawah wadah di Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupItem [-ProtectionStatus <String>] [-Status <String>] [-Type <String>]
 [-Container] <AzureRMBackupContainer> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupItem** mendapatkan item dalam wadah dalam Azure Backup dan status proteksi item.
Aktifkan item untuk perlindungan dengan menggunakan cmdlet Enable-AzureRmBackupProtection.
Wadah yang didaftarkan ke kubah Cadangan dapat memiliki satu atau beberapa item yang dapat diproteksi.
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

Perintah pertama mendapatkan kubah bernama Vault03 dengan menggunakan cmdlet Get-AzureRmBackupVault.
Perintah menyimpan objek tersebut dalam variabel $Vault.
Perintah kedua mendapatkan wadah yang memiliki nama yang ditentukan dalam kubah di $Vault menggunakan cmdlet **Get-AzureRmBackupContainer** .
Perintah menyimpan objek tersebut dalam variabel $Container.
Perintah akhir mendapatkan item cadangan dalam wadah dalam $Container.

### Contoh 2: Menampilkan semua properti untuk item
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

Perintah ini mendapatkan item cadangan dalam wadah dalam $Container, lalu meneruskannya ke cmdlet Select-Object.
Cmdlet tersebut mengembalikan semua properti item cadangan.
Untuk informasi selengkapnya, ketik .`Get-Help Select-Object`

## PARAMETERS

### -Kontainer
Menentukan objek kontainer di mana cmdlet ini mendapatkan item cadangan.
Untuk mendapatkan **AzureRmBackupContainer**, gunakan cmdlet Get-AzureRmBackupContainer.

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

### -ProtectionStatus
Menentukan status proteksi keseluruhan item dalam wadah.
Nilai yang dapat diterima untuk parameter ini adalah:
- Dilindungi 
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
Menentukan status cadangan untuk suatu item.
Nilai yang dapat diterima untuk parameter ini adalah: IRPending, Protected, ProtectionError, dan ProtectionStopped.
Jika parameter *ProtectionStatus* memiliki nilai Terproteksi, Anda dapat menggunakan nilai parameter *Status* untuk memfilter item.

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
Menentukan tipe item yang didapat cmdlet ini.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupContainer
Parameter: Kontainer (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupItem

## CATATAN

## RELATED LINKS

[Backup-AzureRmBackupItem](./Backup-AzureRmBackupItem.md)

[Menonaktifkan-AzureRmBackupProtection](./Disable-AzureRmBackupProtection.md)

[Aktifkan-AzureRmBackupProtection](./Enable-AzureRmBackupProtection.md)

[Get-AzureRmBackupContainer](./Get-AzureRmBackupContainer.md)

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Pulihkan-AzureRmBackupItem](./Restore-AzureRmBackupItem.md)


