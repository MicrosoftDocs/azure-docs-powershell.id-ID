---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/undo-azrecoveryservicesbackupitemdeletion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Undo-AzRecoveryServicesBackupItemDeletion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Undo-AzRecoveryServicesBackupItemDeletion.md
ms.openlocfilehash: 939181d62191f3dcd84b368592c242018d7db459
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145977565"
---
# Undo-AzRecoveryServicesBackupItemDeletion

## SYNOPSIS
Jika item cadangan dihapus dan ada dalam status dihapus sementara, perintah ini membawa item kembali ke status di mana data disimpan selamanya

## SYNTAX

```
Undo-AzRecoveryServicesBackupItemDeletion [-Item] <ItemBase> [-Force] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Undo-AzRecoveryServicesBackupItemDeletion mengembalikan item yang dihapus sementara ke status di mana perlindungan dihentikan tetapi data disimpan selamanya.

## EXAMPLES

### Contoh 1
```powershell
$Cont = Get-AzRecoveryServicesBackupContainer -ContainerType AzureVM
$PI = Get-AzRecoveryServicesBackupItem -Container $Cont[0] -WorkloadType AzureVM
Disable-AzRecoveryServicesBackupProtection -Item $PI[0] -RemoveRecoveryPoints
$PI = Get-AzRecoveryServicesBackupItem -Container $Cont[0] -WorkloadType AzureVM | Where-Object {$_.DeleteState -eq "ToBeDeleted"}
Undo-AzRecoveryServicesBackupItemDeletion -Item $PI[0]
```

Perintah pertama mendapatkan array kontainer cadangan, lalu menyimpannya di array $Cont.
Perintah kedua mendapatkan item Backup yang sesuai dengan item kontainer pertama, lalu menyimpannya dalam variabel $PI.
Perintah ketiga menonaktifkan perlindungan Pencadangan untuk item di $PI\[0\] dan menempatkan item dalam status dihapus sementara.
Perintah keempat mendapatkan item yang dalam status dihapus sementara.
Perintah terakhir membawa VM yang dihapus sementara ke status di mana perlindungan dihentikan tetapi data dipertahankan selamanya.

### Contoh 2

Merehidrasi Item yang dihapus sementara. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Undo-AzRecoveryServicesBackupItemDeletion -Item $PI[0] -VaultId $vault.ID
```

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

### -Force
Paksa menonaktifkan perlindungan pencadangan (mencegah dialog konfirmasi).
Parameter ini bersifat opsional.

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

### -Item
Menentukan item cadangan tempat cmdlet ini mengembalikan penghapusan.
Untuk mendapatkan AzureRmRecoveryServicesBackupItem, gunakan cmdlet Get-AzRecoveryServicesBackupItem.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.JobBase

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesBackupContainer]()

[Get-AzRecoveryServicesBackupItem]()

