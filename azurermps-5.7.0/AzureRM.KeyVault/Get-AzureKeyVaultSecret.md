---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 8C9B33EE-10DE-4803-B76D-FE9FC2AC3372
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/get-azurekeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Get-AzureKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Get-AzureKeyVaultSecret.md
ms.openlocfilehash: f2507d441dc04fd01217dde685deb667211f4034
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421386"
---
# Get-AzureKeyVaultSecret

## SYNOPSIS
Rahasianya ada di kunci vault.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByVaultName (Default)
```
Get-AzureKeyVaultSecret [-VaultName] <String> [[-Name] <String>] [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### BySecretName
```
Get-AzureKeyVaultSecret [-VaultName] <String> [-Name] <String> [-Version] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### BySecretVersions
```
Get-AzureKeyVaultSecret [-VaultName] <String> [-Name] <String> [-IncludeVersions]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByInputObjectVaultName
```
Get-AzureKeyVaultSecret [-InputObject] <PSKeyVault> [[-Name] <String>] [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByInputObjectSecretName
```
Get-AzureKeyVaultSecret [-InputObject] <PSKeyVault> [-Name] <String> [-Version] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByInputObjectSecretVersions
```
Get-AzureKeyVaultSecret [-InputObject] <PSKeyVault> [-Name] <String> [-IncludeVersions]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureKeyVaultSecret** rahasia di vault kunci.
Cmdlet ini rahasia tertentu atau rahasia semua rahasia dalam kunci vault.

## EXAMPLES

### Contoh 1: Mendapatkan semua versi rahasia saat ini dalam kunci vault
```
PS C:\>Get-AzureKeyVaultSecret -VaultName 'Contoso'
```

Perintah ini rahasia semua versi terbaru di kunci vault bernama Contoso.

### Contoh 2: Mendapatkan semua versi rahasia tertentu
```
PS C:\>Get-AzureKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -IncludeVersions
```

Perintah ini mendapatkan semua versi rahasia bernama ITSecret dalam kunci vault bernama Contoso.

### Contoh 3: Mendapatkan versi rahasia tertentu saat ini
```
PS C:\>Get-AzureKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret'
```

Perintah ini menggunakan versi rahasia saat ini yang bernama ITSecret dalam kunci vault bernama Contoso.

### Contoh 4: Mendapatkan versi rahasia tertentu
```
PS C:\>Get-AzureKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -Version '6A12A286385949DB8B5F82AFEF85CAE9'
```

Perintah ini memiliki versi rahasia tertentu yang bernama ITSecret dalam kunci vault bernama Contoso.

### Contoh 5: Mendapatkan nilai teks biasa dari versi rahasia tertentu saat ini
```
PS C:\>$secret = Get-AzureKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret'
PS C:\> Write-Host "Secret Value is: " $secret.SecretValueText
```

Perintah ini mendapatkan versi rahasia saat ini yang bernama ITSecret, lalu menampilkan nilai teks biasa dari rahasia tersebut.

### Contoh 6: Dapatkan semua rahasia yang telah dihapus tapi tidak di purged untuk vault kunci ini.
```
PS C:\>Get-AzureKeyVaultSecret -VaultName 'Contoso' -InRemovedState
```

Perintah ini mendapatkan semua rahasia yang telah dihapus sebelumnya, tapi tidak di pembersihan, di kunci vault bernama Contoso.

### Contoh 7: Gets the secret ITSecret that has been deleted but not purged for this key vault.
```
PS C:\>Get-AzureKeyVaultSecret -VaultName 'Contoso' -KeyName 'ITSecret' -InRemovedState
```

Perintah ini mendapatkan ITSecret rahasia yang telah dihapus sebelumnya, namun tidak di pembersihan, di key vault bernama Contoso.
Perintah ini akan mengembalikan metadata seperti tanggal penghapusan, dan tanggal pembersihan terjadwal dari rahasia yang dihapus ini.

## PARAMETERS

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

### -IncludeVersions
Mengindikasikan bahwa cmdlet ini mendapatkan semua versi rahasia.
Versi rahasia saat ini adalah versi pertama dalam daftar.
Jika Anda menentukan parameter ini, Anda juga harus menentukan *parameter* *Nama dan VaultName.*

Jika Anda tidak menentukan parameter *IncludeVersions,* cmdlet ini mendapatkan versi rahasia terbaru dengan Nama yang *ditentukan.*

```yaml
Type: SwitchParameter
Parameter Sets: BySecretVersions, ByInputObjectSecretVersions
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek KeyVault.

```yaml
Type: PSKeyVault
Parameter Sets: ByInputObjectVaultName, ByInputObjectSecretName, ByInputObjectSecretVersions
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InRemovedState
Menentukan apakah akan memperlihatkan rahasia yang sebelumnya dihapus dalam output

```yaml
Type: SwitchParameter
Parameter Sets: ByVaultName, ByInputObjectVaultName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama rahasia untuk mendapatkannya.

```yaml
Type: String
Parameter Sets: ByVaultName, ByInputObjectVaultName
Aliases: SecretName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: BySecretName, BySecretVersions, ByInputObjectSecretName, ByInputObjectSecretVersions
Aliases: SecretName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kunci vault yang menjadi miliknya.
Cmdlet ini menyusun nama domain (FQDN) yang sepenuhnya memenuhi syarat dari kunci vault berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

```yaml
Type: String
Parameter Sets: ByVaultName, BySecretName, BySecretVersions
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Menentukan versi rahasia.
Cmdlet ini menyusun FQDN dari rahasia berdasarkan nama key vault, lingkungan yang Anda pilih saat ini, nama rahasia, dan versi rahasia.

```yaml
Type: String
Parameter Sets: BySecretName, ByInputObjectSecretName
Aliases: SecretVersion

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### String

## OUTPUTS

### List<Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecretIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecret, List<Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVaultSecretIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVaultSecret

## CATATAN

## RELATED LINKS

[Remove-AzureKeyVaultSecret](./Remove-AzureKeyVaultSecret.md)

[Undo-AzureKeyVaultSecretRemoval](./Undo-AzureKeyVaultSecretRemoval.md)

[Set-AzureKeyVaultSecret](./Set-AzureKeyVaultSecret.md)

