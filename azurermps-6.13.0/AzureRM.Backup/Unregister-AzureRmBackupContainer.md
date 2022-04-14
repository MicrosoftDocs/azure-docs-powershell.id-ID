---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 922BEA08-6619-4D4C-86EC-58279C9E1D93
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/unregister-azurermbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Unregister-AzureRmBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Unregister-AzureRmBackupContainer.md
ms.openlocfilehash: 8c90137e142086d7ea7c0bcc34321b3f38a12d95
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142065934"
---
# Unregister-AzureRmBackupContainer

## SYNOPSIS
Membatalkan pendaftaran wadah dari kubah Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Unregister-AzureRmBackupContainer [-Force] [-Container] <AzureRMBackupContainer>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Unregister-AzureRmBackupContainer** membatalkan pendaftaran Windows Server atau mesin virtual Azure dari kubah Azure Backup.
Cmdlet ini menghapus referensi ke wadah dari kubah Cadangan.
Sebelum dapat membatalkan pendaftaran wadah, Anda harus menghapus semua data yang diproteksi yang terkait dengan wadah tersebut.

## EXAMPLES

### Contoh 1: Batalkan pendaftaran server Windows
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> $Container = Get-AzureRmBackupContainer -Vault $Vault -Type Windows -Name "server01.contoso.com"
PS C:\> Unregister-AzureRmBackupContainer -Container $Container[0]
Unregister Server
This operation will delete all data in the backup vault that is associated with the server. Are you sure you want to unregister the server? 
[] Yes  [] No  [?] Help (default is "No"): Yes
```

Perintah pertama mendapatkan kubah bernama Vault03 dengan menggunakan cmdlet Get-AzureRmBackupVault.
Perintah menyimpan objek tersebut dalam variabel $Vault.
Perintah kedua mendapatkan wadah yang memiliki nama yang ditentukan dalam kubah di $Vault menggunakan cmdlet Get-AzureRmBackupContainer.
Perintah menyimpan objek tersebut dalam variabel $Container.
Perintah terakhir membatalkan pendaftaran Server Windows yang ditentukan dari kubah Azure Backup.

### Contoh 2: Batalkan pendaftaran server Windows tanpa konfirmasi
```
PS C:\>Unregister-AzureRmBackupContainer -Container $Container[0] -Force
```

Perintah ini membatalkan pendaftaran Server Windows yang ditentukan dari kubah Azure Backup, sama seperti dalam contoh pertama.
Perintah ini menentukan parameter *Paksa* .
Oleh karena itu, perintah tidak meminta konfirmasi kepada Anda.

## PARAMETERS

### -Kontainer
Menentukan Windows Server atau mesin virtual Azure yang tidak terdaftar cmdlet ini.
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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.
Parameter ini hanya relevan untuk objek **AzureBackupContainer** tipe Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupContainer
Parameter: Kontainer (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob

## CATATAN
* Tidak

## RELATED LINKS

[Get-AzureRmBackupContainer](./Get-AzureRmBackupContainer.md)

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Daftarkan-AzureRmBackupContainer](./Register-AzureRmBackupContainer.md)


