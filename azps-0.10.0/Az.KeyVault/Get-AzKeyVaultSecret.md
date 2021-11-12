---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 8C9B33EE-10DE-4803-B76D-FE9FC2AC3372
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/get-AzKeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultSecret.md
ms.openlocfilehash: b14e97ba09cba70a9ec571b2fbf1273de7157930
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425026"
---
# Get-AzKeyVaultSecret

## SYNOPSIS
Rahasianya ada di kunci vault.

## SYNTAX

### ByVaultName (Default)
```
Get-AzKeyVaultSecret [-VaultName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### BySecretName
```
Get-AzKeyVaultSecret [-VaultName] <String> [-Name] <String> [[-Version] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### BySecretVersions
```
Get-AzKeyVaultSecret [-VaultName] <String> [-Name] <String> [-IncludeVersions]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByDeletedSecrets
```
Get-AzKeyVaultSecret [-VaultName] <String> [[-Name] <String>] [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzKeyVaultSecret** rahasia dalam kunci vault.
Cmdlet ini rahasia tertentu atau rahasia semua rahasia dalam kunci vault.

## EXAMPLES

### Contoh 1: Mendapatkan semua versi rahasia saat ini dalam kunci vault
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso'
```

Perintah ini rahasia semua versi terbaru di kunci vault bernama Contoso.

### Contoh 2: Mendapatkan semua versi rahasia tertentu
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -IncludeVersions
```

Perintah ini mendapatkan semua versi rahasia bernama ITSecret dalam kunci vault bernama Contoso.

### Contoh 3: Mendapatkan versi rahasia tertentu saat ini
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret'
```

Perintah ini menggunakan versi rahasia saat ini yang bernama ITSecret dalam kunci vault bernama Contoso.

### Contoh 4: Mendapatkan versi rahasia tertentu
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -Version '6A12A286385949DB8B5F82AFEF85CAE9'
```

Perintah ini mendapatkan versi rahasia tertentu yang bernama ITSecret dalam kunci vault bernama Contoso.

### Contoh 5: Mendapatkan nilai teks biasa dari versi rahasia tertentu saat ini
```
PS C:\>$secret = Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret'
PS C:\> Write-Host "Secret Value is: " $secret.SecretValueText
```

Perintah ini mendapatkan versi rahasia saat ini yang bernama ITSecret, lalu menampilkan nilai teks biasa dari rahasia tersebut.

### Contoh 6: Dapatkan semua rahasia yang telah dihapus tapi tidak di purged untuk vault kunci ini.
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -InRemovedState
```

Perintah ini mendapatkan semua rahasia yang telah dihapus sebelumnya, tapi tidak di pembersihan, di kunci vault bernama Contoso.

### Contoh 7: Gets the secret ITSecret that has been deleted but not purged for this key vault.
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -KeyName 'ITSecret' -InRemovedState
```

Perintah ini mendapatkan ITSecret rahasia yang telah dihapus sebelumnya, namun tidak di pembersihan, di key vault bernama Contoso.
Perintah ini akan mengembalikan metadata seperti tanggal penghapusan, dan tanggal pembersihan terjadwal dari rahasia yang dihapus ini.

## PARAMETERS

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

### -IncludeVersions
Mengindikasikan bahwa cmdlet ini mendapatkan semua versi rahasia.
Versi rahasia saat ini adalah versi pertama dalam daftar.
Jika Anda menentukan parameter ini, Anda juga harus menentukan *parameter Nama* *dan VaultName.*

Jika Anda tidak menentukan parameter *IncludeVersions,* cmdlet ini mendapatkan versi rahasia terbaru dengan Nama yang *ditentukan.*

```yaml
Type: SwitchParameter
Parameter Sets: BySecretVersions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InRemovedState
Menentukan apakah akan memperlihatkan rahasia yang sebelumnya dihapus dalam output

```yaml
Type: SwitchParameter
Parameter Sets: ByDeletedSecrets
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama rahasia untuk mendapatkannya.

```yaml
Type: String
Parameter Sets: BySecretName, BySecretVersions
Aliases: SecretName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByDeletedSecrets
Aliases: SecretName

Required: False
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
Parameter Sets: (All)
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
Parameter Sets: BySecretName
Aliases: SecretVersion

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### String

## OUTPUTS

### List<Microsoft.Azure.Commands.KeyVault.Models.SecretIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.Secret, List<Microsoft.Azure.Commands.KeyVault.Models.DeletedSecretIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.DeletedSecret

## CATATAN

## RELATED LINKS

[Remove-AzKeyVaultSecret](./Remove-AzKeyVaultSecret.md)

[Undo-AzKeyVaultSecretRemoval](./Undo-AzKeyVaultSecretRemoval.md)

[Set-AzKeyVaultSecret](./Set-AzKeyVaultSecret.md)

