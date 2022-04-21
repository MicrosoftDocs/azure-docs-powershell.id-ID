---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 8C9B33EE-10DE-4803-B76D-FE9FC2AC3372
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/get-AzKeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Get-AzKeyVaultSecret.md
ms.openlocfilehash: b14e97ba09cba70a9ec571b2fbf1273de7157930
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142782442"
---
# Get-AzKeyVaultSecret

## SYNOPSIS
Mendapatkan rahasia dalam kubah kunci.

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
Cmdlet **Get-AzKeyVaultSecret** mendapatkan rahasia dalam kubah kunci.
Cmdlet ini mendapatkan rahasia tertentu atau semua rahasia dalam kubah kunci.

## EXAMPLES

### Contoh 1: Dapatkan semua versi saat ini dari semua rahasia dalam kubah kunci
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso'
```

Perintah ini mendapatkan versi saat ini dari semua rahasia dalam kubah kunci bernama Contoso.

### Contoh 2: Dapatkan semua versi rahasia tertentu
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -IncludeVersions
```

Perintah ini mendapatkan semua versi rahasia bernama ITSecret dalam kubah kunci bernama Contoso.

### Contoh 3: Mendapatkan versi rahasia tertentu saat ini
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret'
```

Perintah ini mendapatkan versi rahasia saat ini bernama ITSecret dalam kubah kunci bernama Contoso.

### Contoh 4: Mendapatkan versi tertentu dari rahasia tertentu
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -Version '6A12A286385949DB8B5F82AFEF85CAE9'
```

Perintah ini mendapatkan versi rahasia tertentu yang bernama ITSecret dalam kubah kunci bernama Contoso.

### Contoh 5: Mendapatkan nilai teks biasa dari versi rahasia tertentu saat ini
```
PS C:\>$secret = Get-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret'
PS C:\> Write-Host "Secret Value is: " $secret.SecretValueText
```

Perintah ini mendapatkan versi rahasia saat ini yang bernama ITSecret, lalu menampilkan nilai teks biasa rahasia tersebut.

### Contoh 6: Dapatkan semua rahasia yang telah dihapus tetapi tidak dibersihkan untuk kubah kunci ini.
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -InRemovedState
```

Perintah ini mendapatkan semua rahasia yang telah dihapus sebelumnya, tetapi tidak dibersihkan, di kubah kunci bernama Contoso.

### Contoh 7: Gets the secret ITSecret that has been deleted but not purged for this key vault.
```
PS C:\>Get-AzKeyVaultSecret -VaultName 'Contoso' -KeyName 'ITSecret' -InRemovedState
```

Perintah ini mendapatkan itsecret rahasia yang telah dihapus sebelumnya, tetapi tidak dibersihkan, dalam kubah kunci bernama Contoso.
Perintah ini akan mengembalikan metadata seperti tanggal penghapusan, dan tanggal pembersihan terjadwal rahasia yang dihapus ini.

## PARAMETERS

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

### -IncludeVersions
Menunjukkan bahwa cmdlet ini mendapatkan semua versi rahasia.
Versi rahasia saat ini adalah versi pertama dalam daftar.
Jika menentukan parameter ini, Anda juga harus menentukan parameter *Name* dan *VaultName* .

Jika Anda tidak menentukan parameter *IncludeVersions* , cmdlet ini akan mendapatkan versi rahasia saat ini dengan *Nama* yang ditentukan.

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
Menentukan apakah akan menampilkan rahasia yang dihapus sebelumnya dalam output

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
Menentukan nama rahasia yang akan didapatkan.

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
Menentukan nama kubah kunci tempat rahasia berada.
Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN) dari kubah kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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
Cmdlet ini menyusun FQDN rahasia berdasarkan nama kubah kunci, lingkungan yang dipilih saat ini, nama rahasia, dan versi rahasia.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Daftar<Microsoft.Azure.Commands.KeyVault.Models.SecretIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.Secret, Daftar<Microsoft.Azure.Commands.KeyVault.Models.DeletedSecretIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.DeletedSecret

## NOTES

## RELATED LINKS

[Remove-AzKeyVaultSecret](./Remove-AzKeyVaultSecret.md)

[Batalkan-AzKeyVaultSecretRemoval](./Undo-AzKeyVaultSecretRemoval.md)

[Set-AzKeyVaultSecret](./Set-AzKeyVaultSecret.md)

