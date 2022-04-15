---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: A10DC2A2-A732-416F-9C68-6533C143AE8F
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/unregister-azrecoveryservicesbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Unregister-AzRecoveryServicesBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Unregister-AzRecoveryServicesBackupContainer.md
ms.openlocfilehash: 6d5608ea647b709c0ed51dad1250f69b37d5c154
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142254517"
---
# Unregister-AzRecoveryServicesBackupContainer

## SYNOPSIS
Membatalkan pendaftaran server Windows atau wadah lain dari kubah.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/unregister-azrecoveryservicesbackupcontainer) untuk informasi terbaru.

## SYNTAX

```
Unregister-AzRecoveryServicesBackupContainer [-Container] <ContainerBase> [-PassThru] [-Force]
 [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Unregister-AzRecoveryServicesBackupContainer** membatalkan pendaftaran server Windows atau kontainer Cadangan lainnya dari kubah.
Cmdlet ini menghapus referensi ke wadah dari kubah.
Sebelum dapat membatalkan pendaftaran wadah, Anda harus menghapus semua data yang diproteksi yang terkait dengan wadah tersebut.
Mengatur konteks kubah menggunakan cmdlet Set-AzRecoveryServicesVaultContext sebelum Anda menggunakan cmdlet saat ini.

## EXAMPLES

### Contoh 1: Batalkan pendaftaran Server Windows dari kubah
```powershell
PS C:\>$Cont = Get-AzRecoveryServicesBackupContainer -ContainerType "Windows" -BackupManagementType MAB -Name "server01.contoso.com"
PS C:\> Unregister-AzRecoveryServicesBackupContainer -Container $Cont
```

Perintah pertama mendapatkan wadah Windows bernama server01.contoso.com yang terdaftar dalam kubah, lalu menyimpannya dalam variabel $Cont.
Perintah kedua membatalkan pendaftaran Server Windows yang ditentukan dari kubah Azure Backup.

### Contoh 2

Membatalkan pendaftaran server Windows atau wadah lain dari kubah. (autogenerasi)

```powershell
<!-- Aladdin Generated Example --> 
Unregister-AzRecoveryServicesBackupContainer -Container $Cont -VaultId $vault.ID
```

## PARAMETERS

### -Kontainer
Menentukan objek Kontainer Cadangan untuk membatalkan pendaftaran.
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

### -Paksa
Memaksa penampung tidak terdaftar (mencegah dialog konfirmasi). Parameter ini bersifat opsional.

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
Mengembalikan wadah yang akan dihapus.

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
ARM ID dari Vault Layanan Pemulihan.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. 

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ContainerBase

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesBackupContainer](./Get-AzRecoveryServicesBackupContainer.md)


