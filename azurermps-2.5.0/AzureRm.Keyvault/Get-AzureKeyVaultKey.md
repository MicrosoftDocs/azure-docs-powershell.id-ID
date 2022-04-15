---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 2BE34AE1-06FA-4F66-8FDB-CED22C2E0978
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/get-azurekeyvaultkey
schema: 2.0.0
ms.openlocfilehash: 5ebb9ca4a59f713ec81e5099cd3bbcc91084ac4d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141928897"
---
# Get-AzureKeyVaultKey

## SYNOPSIS
Mendapatkan kunci Key Vault.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByVaultName (Default)
```
Get-AzureKeyVaultKey [-VaultName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByKeyName
```
Get-AzureKeyVaultKey [-VaultName] <String> [-Name] <String> [[-Version] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByKeyVersions
```
Get-AzureKeyVaultKey [-VaultName] <String> [-Name] <String> [-IncludeVersions]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByDeletedKey
```
Get-AzureKeyVaultKey [-VaultName] <String> [[-Name] <String>] [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureKeyVaultKey** mendapatkan tombol azure Key Vault.
Cmdlet ini mendapatkan **Microsoft.Azure.Commands.KeyVault.Models.KeyBundle** tertentu atau daftar semua objek **KeyBundle** dalam kubah kunci atau versi.

## EXAMPLES

### Contoh 1: Dapatkan semua kunci dalam kubah kunci
```
PS C:\>Get-AzureKeyVaultKey -VaultName 'Contoso'
```

Perintah ini mendapatkan semua kunci di kubah kunci bernama Contoso.

### Contoh 2: Dapatkan versi kunci saat ini
```
PS C:\>Get-AzureKeyVaultKey -VaultName 'Contoso' -KeyName 'ITPfx'
```

Perintah ini mendapatkan versi kunci saat ini bernama ITPfx di kubah kunci bernama Contoso.

### Contoh 3: Dapatkan semua versi kunci
```
PS C:\>Get-AzureKeyVaultKey -VaultName 'Contoso' -KeyName 'ITPfx' -IncludeVersions
```

Perintah ini mendapatkan semua versi kunci bernama ITPfx dalam kunci vaultnamed Contoso.

### Contoh 4: Mendapatkan versi kunci tertentu
```
PS C:\>$Key = Get-AzureKeyVaultKey -VaultName 'Contoso' -KeyName 'ITPfx' -Version '5A12A276385949DB8B5F82AFEE85CAED'
```

Perintah ini mendapatkan versi kunci tertentu yang bernama ITPfx di kubah kunci bernama Contoso.
Setelah menjalankan perintah ini, Anda dapat memeriksa berbagai properti kunci dengan menavigasi objek $Key.

### Contoh 5: Dapatkan semua kunci yang telah dihapus tetapi tidak dibersihkan untuk kubah kunci ini.
```
PS C:\>Get-AzureKeyVaultKey -VaultName 'Contoso' -InRemovedState
```

Perintah ini mendapatkan semua kunci yang telah dihapus sebelumnya, tetapi tidak dibersihkan, dalam kubah kunci bernama Contoso.

### Contoh 6: Mendapatkan kunci ITPfx yang telah dihapus tetapi tidak dibersihkan untuk kubah kunci ini.
```
PS C:\>Get-AzureKeyVaultKey -VaultName 'Contoso' -KeyName 'ITPfx' -InRemovedState
```

Perintah ini mendapatkan kunci ITPfx yang telah dihapus sebelumnya, tetapi tidak dibersihkan, dalam kubah kunci bernama Contoso.
Perintah ini akan mengembalikan metadata seperti tanggal penghapusan, dan tanggal penghapusan terjadwal kunci yang dihapus ini.

## PARAMETERS

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

### -IncludeVersions
Menunjukkan bahwa cmdlet ini mendapatkan semua versi kunci.
Versi kunci saat ini adalah versi pertama dalam daftar.
Jika menentukan parameter ini, Anda juga harus menentukan parameter *Name* dan *VaultName* .

Jika Anda tidak menentukan parameter *IncludeVersions* , cmdlet ini akan mendapatkan versi kunci saat ini dengan *Nama* yang ditentukan.

```yaml
Type: SwitchParameter
Parameter Sets: ByKeyVersions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InRemovedState
Menentukan apakah akan menampilkan tombol yang dihapus sebelumnya dalam output

```yaml
Type: SwitchParameter
Parameter Sets: ByDeletedKey
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama bundel kunci yang akan didapatkan.

```yaml
Type: String
Parameter Sets: ByKeyName, ByKeyVersions
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByDeletedKey
Aliases: KeyName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kubah kunci tempat cmdlet ini mendapatkan kunci.
Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN) dari kubah kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan yang Anda pilih.

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
Menentukan versi kunci.
Cmdlet ini menyusun FQDN kunci berdasarkan nama kubah kunci, lingkungan yang dipilih saat ini, nama kunci, dan versi kunci.

```yaml
Type: String
Parameter Sets: ByKeyName
Aliases: KeyVersion

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Daftar<Microsoft.Azure.Commands.KeyVault.Models.KeyIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.KeyBundle, Daftar<Microsoft.Azure.Commands.KeyVault.Models.DeletedKeyIdentityItem>, Microsoft.Azure.Commands.KeyVault.Models.DeletedKeyBundle

## CATATAN

## RELATED LINKS

[Add-AzureKeyVaultKey](./Add-AzureKeyVaultKey.md)

[Hapus-AzureKeyVaultKey](./Remove-AzureKeyVaultKey.md)

[Batalkan-AzureKeyVaultKeyRemoval](./Undo-AzureKeyVaultKeyRemoval.md)

[Set-AzureKeyVaultKeyAttribute](./Set-AzureKeyVaultKeyAttribute.md)

