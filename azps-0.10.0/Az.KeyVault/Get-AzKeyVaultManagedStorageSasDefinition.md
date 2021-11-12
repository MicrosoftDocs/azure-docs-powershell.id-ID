---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/get-AzKeyvaultmanagedstoragesasdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedStorageSasDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultManagedStorageSasDefinition.md
ms.openlocfilehash: a6ee2d42fc04c7da666c8f0a4959dc4a18268a81c2074abe481772e5615c8e70
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132413621"
---
# Get-AzKeyVaultManagedStorageSasDefinition

## SYNOPSIS
Mendapatkan Key Vault yang dikelola Storage SAS Definitions.

## SYNTAX

### ByAccountName (Default)
```
Get-AzKeyVaultManagedStorageSasDefinition [-VaultName] <String> [-AccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByDefinitionName
```
Get-AzKeyVaultManagedStorageSasDefinition [-VaultName] <String> [-AccountName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan Kunci Vault yang Storage di Definisi SAS jika nama definisi ditentukan. Jika nama definisi tidak ditentukan, semua definisi SAS yang terkait dengan Key Vault tertentu dikelola Storage Akun di vault akan dicantumkan.

## EXAMPLES

### Contoh 1: Daftar semua Kunci Vault Storage Sas Definitions
```
PS C:\> Get-AzKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount'
```

Mencantumkan semua definisi SAS yang terkait dengan Kunci Vault yang Storage Akun 'mystorageaccount' yang dikelola oleh vault 'myvault'

### Contoh 2: Get a Key Vault managed Storage Account
```
PS C:\> Get-AzKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount' -Name 'mysasDef'
```

Mendapatkan detail Sas Definition 'mysasDef' terkait dengan Key Vault yang dikelola Storage Akun 'mystorageaccount' yang dikelola oleh vault 'myvault'.

## PARAMETERS

### -Nama Akun
Nama Vault.
Cmdlet menyusun FQDN dari vault berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Storage sas definition name.
Cmdlet membangun FQDN dari definisi sas penyimpanan dari nama vault, lingkungan yang saat ini dipilih, nama akun penyimpanan dan nama definisi sas.

```yaml
Type: String
Parameter Sets: ByDefinitionName
Aliases: SasDefinitionName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Nama Vault.
Cmdlet menyusun FQDN dari vault berdasarkan nama dan lingkungan yang saat ini dipilih.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageSasDefinitionListItem, Microsoft.Azure.Commands.KeyVault, Version=2.5.0.0, Culture=neutral, PublicKeyToken=null]]
Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageSasDefinition

## CATATAN

## RELATED LINKS

[Azure PowerShell cmdlet Key Vault](/powershell/module/az.keyvault/)

