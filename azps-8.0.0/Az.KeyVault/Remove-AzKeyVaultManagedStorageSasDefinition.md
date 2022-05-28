---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/remove-azkeyvaultmanagedstoragesasdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultManagedStorageSasDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultManagedStorageSasDefinition.md
ms.openlocfilehash: 891b864c37135873c70ef0e4aeffc85a437511d5
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145506430"
---
# Remove-AzKeyVaultManagedStorageSasDefinition

## SYNOPSIS
Menghapus definisi SAS Azure Storage terkelola Key Vault.

## SYNTAX

### ByDefinitionName (Default)
```
Remove-AzKeyVaultManagedStorageSasDefinition [-VaultName] <String> [-AccountName] <String> [-Name] <String>
 [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Remove-AzKeyVaultManagedStorageSasDefinition [-InputObject] <PSKeyVaultManagedStorageSasDefinitionIdentityItem>
 [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus definisi SAS Azure Storage terkelola Key Vault. Ini juga menghapus rahasia yang digunakan untuk mendapatkan token SAS sesuai definisi SAS ini.

## EXAMPLES

### Contoh 1: Hapus definisi SAS Azure Storage terkelola Key Vault.
```powershell
Remove-AzKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount' -Name 'mysasdef' -PassThru
```

```output
Id          : https://myvault.vault.azure.net:443/storage/mystorageaccount/sas/mysasdef
Vault Name  : myvault
AccountName : mystorageaccount
Name        : mysasdef
Enabled     : True
Created     : 5/24/2018 9:11:08 PM
Updated     : 5/24/2018 9:11:08 PM
Tags        :
```

Menghapus definisi KEY VAULT terkelola Storage SAS 'mysasdef' yang terkait dengan akun 'mystorageaccount' di vault 'myvault'.

### Contoh 2: Hapus definisi SAS Azure Storage terkelola Key Vault tanpa konfirmasi pengguna.
```powershell
Remove-AzKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount' -Name 'mysasdef' -PassThru -Force
```

```output
Id          : https://myvault.vault.azure.net:443/storage/mystorageaccount/sas/mysasdef
Vault Name  : myvault
AccountName : mystorageaccount
Name        : mysasdef
Enabled     : True
Created     : 5/24/2018 9:11:08 PM
Updated     : 5/24/2018 9:11:08 PM
Tags        :
```

Menghapus definisi KEY VAULT terkelola Storage SAS 'mysasdef' yang terkait dengan akun 'mystorageaccount' di vault 'myvault'.

## PARAMETERS

### -AccountName
Nama akun penyimpanan.
Cmdlet membangun FQDN dari nama akun penyimpanan terkelola dari nama vault, lingkungan yang saat ini dipilih dan nama akun penyimpanan.

```yaml
Type: System.String
Parameter Sets: ByDefinitionName
Aliases: StorageAccountName

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
Objek ManagedStorageSasDefinition.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageSasDefinitionIdentityItem
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Storage nama definisi sas.
Cmdlet membangun FQDN dari definisi sas penyimpanan dari nama vault, lingkungan yang saat ini dipilih, nama akun penyimpanan, dan nama definisi sas.

```yaml
Type: System.String
Parameter Sets: ByDefinitionName
Aliases: SasDefinitionName

Required: True
Position: 2
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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageSasDefinitionIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVaultManagedStorageSasDefinition

## NOTES

## RELATED LINKS

[Get-AzKeyVaultManagedStorageSasDefinition](./Get-AzKeyVaultManagedStorageSasDefinition.md)

[Set-AzKeyVaultManagedStorageSasDefinition](./Set-AzKeyVaultManagedStorageSasDefinition.md)

[Undo-AzKeyVaultManagedStorageSasDefinitionRemoval](./Undo-AzKeyVaultManagedStorageSasDefinitionRemoval.md)