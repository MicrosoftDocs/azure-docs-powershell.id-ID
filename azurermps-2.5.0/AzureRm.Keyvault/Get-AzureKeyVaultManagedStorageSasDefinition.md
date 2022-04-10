---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/get-azurekeyvaultmanagedstoragesasdefinition
schema: 2.0.0
ms.openlocfilehash: dd02aa2235a154e5bb600b13c935ebe9b229ba18
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "140863946"
---
# Get-AzureKeyVaultManagedStorageSasDefinition

## SYNOPSIS
Mendapatkan Key Vault yang Storage Sas Definitions.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByAccountName (Default)
```
Get-AzureKeyVaultManagedStorageSasDefinition [-VaultName] <String> [-AccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByDefinitionName
```
Get-AzureKeyVaultManagedStorageSasDefinition [-VaultName] <String> [-AccountName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan Kunci Vault yang Storage sas Definition jika nama definisi ditentukan. Jika nama definisi tidak ditentukan, maka semua definisi SAS yang terkait dengan Key Vault tertentu dikelola Storage Akun di vault dicantumkan.

## EXAMPLES

### Contoh 1: Daftar semua Kunci Vault Storage Sas Definitions
```
PS C:\> Get-AzureKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount'
```

Mencantumkan semua definisi SAS yang terkait dengan Kunci Vault yang dikelola Storage 'mystorageaccount' yang dikelola oleh vault 'myvault'

### Contoh 2: Get a Key Vault managed Storage Account
```
PS C:\> Get-AzureKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount' -Name 'mysasDef'
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
Aliases: AzureRmContext, AzureCredential

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageSasDefinitionListItem, Microsoft.Azure.Commands.KeyVault, Version=2.5.0.0, Culture=neutral, PublicKeyToken=null]]
Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageSasDefinition

## CATATAN

## RELATED LINKS

[Cmdlet Key Vault Azure](/powershell/module/azurerm.keyvault/)
