---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: A10DC2A2-A732-416F-9C68-6533C143AE8F
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/unregister-azrecoveryservicesbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Unregister-AzRecoveryServicesBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Unregister-AzRecoveryServicesBackupContainer.md
ms.openlocfilehash: 09b5707f659a7cfa6395b23aa979292993afc80f
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145979330"
---
# Unregister-AzRecoveryServicesBackupContainer

## SYNOPSIS
Membatalkan pendaftaran Windows Server atau kontainer lain dari vault.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/unregister-azrecoveryservicesbackupcontainer) untuk informasi terbaru.

## SYNTAX

```
Unregister-AzRecoveryServicesBackupContainer [-Container] <ContainerBase> [-PassThru] [-Force]
 [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Unregister-AzRecoveryServicesBackupContainer** membatalkan pendaftaran server Windows atau kontainer Cadangan lainnya dari vault.
Cmdlet ini menghapus referensi ke kontainer dari vault.
Sebelum dapat membatalkan pendaftaran kontainer, Anda harus menghapus data yang dilindungi yang terkait dengan kontainer tersebut.
Atur konteks vault dengan menggunakan cmdlet Set-AzRecoveryServicesVaultContext sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Membatalkan pendaftaran server Windows dari vault
```powershell
$Cont = Get-AzRecoveryServicesBackupContainer -ContainerType "Windows" -BackupManagementType MAB -Name "server01.contoso.com"
Unregister-AzRecoveryServicesBackupContainer -Container $Cont
```

Perintah pertama mendapatkan kontainer Windows bernama server01.contoso.com yang terdaftar di vault, lalu menyimpannya dalam variabel $Cont.
Perintah kedua membatalkan pendaftaran server Windows yang ditentukan dari vault Azure Backup.

### Contoh 2

Membatalkan pendaftaran Windows Server atau kontainer lain dari vault. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Unregister-AzRecoveryServicesBackupContainer -Container $Cont -VaultId $vault.ID
```

## PARAMETERS

### -Kontainer
Menentukan objek kontainer Cadangan untuk membatalkan pendaftaran.
Untuk mendapatkan objek **BackupContainer** , gunakan cmdlet Get-AzRecoveryServicesBackupContainer.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerBase
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Paksa membatalkan pendaftaran kontainer (mencegah dialog konfirmasi). Parameter ini bersifat opsional.

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

### -PassThru
Mengembalikan kontainer yang akan dihapus.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerBase

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesBackupContainer](./Get-AzRecoveryServicesBackupContainer.md)


