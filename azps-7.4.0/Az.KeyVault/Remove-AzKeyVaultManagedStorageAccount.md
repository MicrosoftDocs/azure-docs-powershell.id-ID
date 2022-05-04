---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/remove-azkeyvaultmanagedstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultManagedStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultManagedStorageAccount.md
ms.openlocfilehash: 9a06f56ef7ef05437db9ccf78d84815a0f18e61b
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144687968"
---
# Remove-AzKeyVaultManagedStorageAccount

## SYNOPSIS
Menghapus Akun Azure Storage terkelola Key Vault dan semua definisi SAS terkait.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/remove-azkeyvaultmanagedstorageaccount) untuk informasi terbaru.

## SYNTAX

### ByDefinitionName (Default)
```
Remove-AzKeyVaultManagedStorageAccount [-VaultName] <String> [-AccountName] <String> [-InRemovedState] [-Force]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Remove-AzKeyVaultManagedStorageAccount [-InputObject] <PSKeyVaultManagedStorageAccountIdentityItem>
 [-InRemovedState] [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Memisahkan Akun Azure Storage dari Key Vault. Ini tidak menghapus Akun Azure Storage tetapi menghapus kunci akun agar tidak dikelola oleh Azure Key Vault. Semua definisi SAS Key Vault terkelola Storage Key Vault terkait juga dihapus.

## EXAMPLES

### Contoh 1: Hapus Akun Azure Storage terkelola Key Vault dan semua definisi SAS terkait.
```powershell
Remove-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount' -PassThru
```

```output
Id                  : https://myvault.vault.azure.net:443/storage/mystorageaccount
Vault Name          : myvault
AccountName         : mystorageaccount
Account Resource Id : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx/resourceGroups/myrg/providers/Microsoft.St
                      orage/storageAccounts/mystorageaccount
Enabled             : True
Created             : 4/25/2018 1:50:32 AM
Updated             : 4/25/2018 1:50:32 AM
Tags                :
```

Memisahkan akun Azure Storage 'mystorageaccount' dari Key Vault 'myvault' dan menghentikan Key Vault mengelola kuncinya. Akun 'mystorageaccount' tidak akan dihapus. Semua definisi SAS Storage terkelola Key Vault yang terkait dengan akun ini akan dihapus.

### Contoh 2: Hapus Akun Azure Storage terkelola Key Vault dan semua definisi SAS terkait tanpa konfirmasi pengguna.
```powershell
Remove-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount' -PassThru -Force
```

```output
Id                  : https://myvault.vault.azure.net:443/storage/mystorageaccount
Vault Name          : myvault
AccountName         : mystorageaccount
Account Resource Id : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx/resourceGroups/myrg/providers/Microsoft.St
                      orage/storageAccounts/mystorageaccount
Enabled             : True
Created             : 4/25/2018 1:50:32 AM
Updated             : 4/25/2018 1:50:32 AM
Tags                :
```

Memisahkan akun Azure Storage 'mystorageaccount' dari Key Vault 'myvault' dan menghentikan Key Vault mengelola kuncinya. Akun 'mystorageaccount' tidak akan dihapus. Semua definisi SAS Storage terkelola Key Vault yang terkait dengan akun ini akan dihapus.

### Contoh 3: Hapus secara permanen (hapus menyeluruh) Akun Azure Storage terkelola Key Vault dan semua definisi SAS terkait dari vault yang mendukung penghapusan sementara.
```powershell
Remove-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount'
Get-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount' -InRemovedState
Remove-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount' -InRemovedState
```

Contoh mengasumsikan bahwa penghapusan sementara diaktifkan untuk vault ini. Verifikasi apakah itu masalahnya dengan memeriksa properti vault, atau atribut RecoveryLevel dari entitas di vault.
Cmdlet pertama memisahkan akun Azure Storage 'mystorageaccount' dari Key Vault 'myvault' dan menghentikan Key Vault mengelola kuncinya. Akun 'mystorageaccount' tidak akan dihapus. Semua definisi SAS Storage terkelola Key Vault yang terkait dengan akun ini akan dihapus.
Cmdlet kedua memverifikasi bahwa akun penyimpanan dalam status dihapus, tetapi dapat dipulihkan. Mencapai status ini mungkin memerlukan waktu, harap izinkan ~30s sebelum mencoba.
Cmdlet ketiga secara permanen menghapus akun penyimpanan - pemulihan tidak akan lagi dimungkinkan.

## PARAMETERS

### -AccountName
Key Vault nama akun penyimpanan terkelola. Cmdlet membangun FQDN dari nama akun penyimpanan terkelola dari nama brankas, lingkungan yang saat ini dipilih, dan nama akun penyimpanan terkelola.

```yaml
Type: System.String
Parameter Sets: ByDefinitionName
Aliases: StorageAccountName, Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Jangan meminta konfirmasi.

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

### -InputObject
Objek ManagedStorageAccount.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InRemovedState
Hapus akun penyimpanan terkelola yang dihapus sebelumnya secara permanen.

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
Cmdlet tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, cmdlet mengembalikan akun penyimpanan terkelola yang dihapus.

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

### -VaultName
Nama vault.
Cmdlet membangun FQDN vault berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: ByDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVaultManagedStorageAccount

## NOTES

## RELATED LINKS

[Cmdlet PowerShell Azure Key Vault](/powershell/module/az.keyvault/)
