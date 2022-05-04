---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/undo-azkeyvaultmanagedstoragesasdefinitionremoval
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Undo-AzKeyVaultManagedStorageSasDefinitionRemoval.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Undo-AzKeyVaultManagedStorageSasDefinitionRemoval.md
ms.openlocfilehash: 63bfcc03d3bf2b6ee7b5dd93b0b3792f6b256089
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144655850"
---
# Undo-AzKeyVaultManagedStorageSasDefinitionRemoval

## SYNOPSIS
Memulihkan definisi SAS penyimpanan yang dikelola KeyVault yang dihapus sebelumnya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/undo-azkeyvaultmanagedstoragesasdefinitionremoval) untuk informasi terbaru.

## SYNTAX

### Default (Default)
```
Undo-AzKeyVaultManagedStorageSasDefinitionRemoval [-VaultName] <String> [-AccountName] <String>
 [-Name] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Undo-AzKeyVaultManagedStorageSasDefinitionRemoval [-AccountName] <String>
 [-InputObject] <PSDeletedKeyVaultManagedStorageSasDefinitionIdentityItem>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perintah **Undo-AzKeyVaultManagedStorageSasDefinitionRemoval** memulihkan definisi SAS penyimpanan terkelola yang dihapus sebelumnya, asalkan penghapusan sementara diaktifkan untuk vault ini, dan bahwa upaya untuk memulihkan terjadi selama interval pemulihan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzKeyVaultManagedStorageSasDefinition -VaultName myVault -AccountName myAccount -Name mySasName -InRemovedState
Undo-AzKeyVaultManagedStorageSasDefinitionRemoval -VaultName myVault -AccountName myAccount -Name mySasName
```

```output
Id          : https://myvault.vault.azure.net:443/storage/myaccount/sas/mysasname
Secret Id   : https://myvault.vault.azure.net/secrets/myaccount-mysasname
Vault Name  : myVault
AccountName : myAccount
Name        : mySasName
Parameter   :
Enabled     : True
Created     : 5/24/2018 9:11:08 PM
Updated     : 5/24/2018 9:11:08 PM
Tags        :
```

Urutan perintah ini menentukan apakah definisi SAS penyimpanan yang ditentukan ada di vault dalam status dihapus; perintah berikutnya memulihkan definisi sas yang dihapus, membawanya kembali ke status aktif.

## PARAMETERS

### -AccountName
Nama akun penyimpanan yang dikelola KeyVault.
Cmdlet membangun FQDN dari definisi SAS penyimpanan terkelola dari nama vault, lingkungan yang saat ini dipilih, dan nama akun penyimpanan terkelola.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -InputObject
Objek definisi SAS penyimpanan terkelola yang dihapus

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVaultManagedStorageSasDefinitionIdentityItem
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama definisi SAS penyimpanan yang dikelola KeyVault.
Cmdlet membangun FQDN target dari nama vault, lingkungan yang saat ini dipilih, nama akun penyimpanan terkelola, dan nama definisi SAS.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: SasDefinitionName

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama vault.
Cmdlet membangun FQDN vault berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: Default
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

### Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVaultManagedStorageSasDefinitionIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageSasDefinition

## NOTES

## RELATED LINKS
