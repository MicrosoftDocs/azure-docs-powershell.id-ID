---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/get-AzKeyvaultmanagedstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedStorageAccount.md
ms.openlocfilehash: 536c79b26bb520004af2e2de5b6ba711ca2a4966
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142351043"
---
# Get-AzKeyVaultManagedStorageAccount

## SYNOPSIS
Mendapatkan akun Azure Storage terkelola Key Vault.

## SYNTAX

### ByVaultName (Default)
```
Get-AzKeyVaultManagedStorageAccount [-VaultName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByAccountName
```
Get-AzKeyVaultManagedStorageAccount [-VaultName] <String> [-AccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan akun Azure Storage terkelola Key Vault jika nama akun ditentukan dan kunci akun dikelola oleh kubah yang ditentukan. Jika nama akun tidak ditentukan, maka semua akun yang kuncinya dikelola oleh kubah tertentu akan dicantumkan.

## EXAMPLES

### Contoh 1: Mencantumkan semua akun Storage dikelola Key Vault
```
PS C:\> Get-AzKeyVaultManagedStorageAccount -VaultName 'myvault'
```

Mencantumkan semua akun yang kuncinya dikelola oleh kubah 'myvault'

### Contoh 2: Dapatkan akun Storage terkelola Key Vault
```
PS C:\> Get-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -Name 'mystorageaccount'
```

Mendapatkan detail Key Vault dikelola Storage Akun dari 'mystorageaccount' jika kuncinya dikelola oleh 'myvault' kubah

## PARAMETERS

### -AccountName
Key Vault nama akun penyimpanan terkelola. Cmdlet menyusun FQDN nama akun penyimpanan terkelola dari nama kubah, lingkungan yang saat ini dipilih, dan nama akun penyimpanan yang ditukar.

```yaml
Type: String
Parameter Sets: ByAccountName
Aliases: StorageAccountName, Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama kubah.
Cmdlet menyusun FQDN kubah berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageAccount, Microsoft.Azure.Commands.KeyVault, Version=2.5.0.0, Culture=netral, PublicKeyToken=null]]
Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageAccount

## CATATAN

## RELATED LINKS

[cmdlet Azure PowerShell Key Vault](/powershell/module/az.keyvault/)

