---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/get-azurekeyvaultmanagedstoragesasdefinition
schema: 2.0.0
ms.openlocfilehash: dd02aa2235a154e5bb600b13c935ebe9b229ba18
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142991081"
---
# Get-AzureKeyVaultManagedStorageSasDefinition

## SYNOPSIS
Dapatkan Key Vault dikelola Storage Definisi SAS.

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
Mendapatkan Key Vault dikelola Storage Definisi SAS jika nama definisi ditentukan. Jika nama definisi tidak ditentukan, maka semua definisi SAS yang terkait dengan Key Vault akun Storage dikelola yang ditentukan dalam kubah dicantumkan.

## EXAMPLES

### Contoh 1: Mencantumkan semua definisi Key Vault dikelola Storage SAS
```
PS C:\> Get-AzureKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount'
```

Mencantumkan semua definisi SAS yang terkait dengan Key Vault dikelola Storage Akun 'mystorageaccount' yang dikelola oleh kubah 'myvault'

### Contoh 2: Dapatkan akun Storage terkelola Key Vault
```
PS C:\> Get-AzureKeyVaultManagedStorageSasDefinition -VaultName 'myvault' -AccountName 'mystorageaccount' -Name 'mysasDef'
```

Mendapatkan detail definisi SAS 'mysasDef' yang terkait dengan Key Vault dikelola Storage Akun 'mystorageaccount' yang dikelola oleh vault 'myvault'.

## PARAMETERS

### -AccountName
Nama kubah.
Cmdlet menyusun FQDN kubah berdasarkan nama dan lingkungan yang saat ini dipilih.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Storage nama definisi sas.
Cmdlet menyusun FQDN definisi sas penyimpanan dari nama kubah, lingkungan yang saat ini dipilih, nama akun penyimpanan dan nama definisi sas.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageSasDefinitionListItem, Microsoft.Azure.Commands.KeyVault, Version=2.5.0.0, Culture=neutral, PublicKeyToken=null]]
Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageSasDefinition

## NOTES

## RELATED LINKS

[Cmdlet Azure Key Vault](/powershell/module/azurerm.keyvault/)
