---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: A7C287C4-E9FD-407A-91BD-EFA17C33FC8B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/get-azurermkeyvault
schema: 2.0.0
ms.openlocfilehash: 7cbcf722b71919096ca2c7d1dc3201ad2fe42f2a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142735894"
---
# Get-AzureRmKeyVault

## SYNOPSIS
Mendapatkan kubah kunci.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetVaultByName
```
Get-AzureRmKeyVault [-VaultName] <String> [[-ResourceGroupName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByDeletedVault
```
Get-AzureRmKeyVault [-VaultName] <String> [-Location] <String> [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListVaultsByResourceGroup
```
Get-AzureRmKeyVault [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ListAllDeletedVaultsInSubscription
```
Get-AzureRmKeyVault [-InRemovedState] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListAllVaultsInSubscription
```
Get-AzureRmKeyVault [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmKeyVault** mendapatkan informasi tentang kubah kunci dalam langganan. Anda dapat menampilkan semua contoh kubah kunci dalam langganan, atau memfilter hasil menurut grup sumber daya atau kubah kunci tertentu.

Perhatikan bahwa meskipun menentukan grup sumber daya bersifat opsional untuk cmdlet ini ketika Anda mendapatkan kubah kunci tunggal, Anda harus melakukannya untuk kinerja yang lebih baik.

## EXAMPLES

### Contoh 1: Dapatkan semua kubah kunci dalam langganan Anda saat ini
```
PS C:\>Get-AzureRMKeyVault
```

Perintah ini mendapatkan semua kubah kunci dalam langganan Anda saat ini.

### Contoh 2: Dapatkan kubah kunci tertentu
```
PS C:\>$MyVault = Get-AzureRMKeyVault -VaultName 'Contoso03Vault'
```

Perintah ini mendapatkan kubah kunci bernama Contoso03Vault dalam langganan Anda saat ini, lalu menyimpannya dalam variabel $MyVault. Anda dapat memeriksa properti $MyVault untuk mendapatkan detail tentang kubah kunci.

### Contoh 3: Dapatkan kubah kunci dalam grup sumber daya
```
PS C:\>Get-AzureRmKeyVault -ResourceGroupName 'ContosoPayRollResourceGroup'
```

Perintah ini mendapatkan semua kubah kunci dalam grup sumber daya bernama ContosoPayRollResourceGroup.

### Contoh 4: Dapatkan semua kubah kunci yang dihapus dalam langganan Anda saat ini
```
PS C:\>Get-AzureRmKeyVault -InRemovedState
```

Perintah ini mendapatkan semua kubah kunci yang dihapus dalam langganan Anda saat ini.

### Contoh 5: Dapatkan kubah kunci yang dihapus
```
PS C:\>Get-AzureRMKeyVault -VaultName 'Contoso03Vault'  -Location 'eastus2' -InRemovedState
```

Perintah ini mendapatkan informasi kubah kunci yang dihapus bernama Contoso03Vault dalam langganan Anda saat ini dan di kawasan eastus2.

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

### -InRemovedState
Menentukan apakah akan memperlihatkan kubah yang dihapus sebelumnya dalam output.

```yaml
Type: SwitchParameter
Parameter Sets: ByDeletedVault, ListAllDeletedVaultsInSubscription
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi kubah yang dihapus.

```yaml
Type: String
Parameter Sets: ByDeletedVault
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang terkait dengan kubah kunci atau kubah kunci yang sedang dikueri.

```yaml
Type: String
Parameter Sets: GetVaultByName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ListVaultsByResourceGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya:

@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: Hashtable
Parameter Sets: ListAllVaultsInSubscription
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kubah kunci.

```yaml
Type: String
Parameter Sets: GetVaultByName, ByDeletedVault
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSVault

### System.Collections.Generic.List'1[Microsoft.Azure.Commands.KeyVault.Models.PSVaultIdentityItem]

### Microsoft.Azure.Commands.KeyVault.Models.PSDeletedVault

### System.Collections.Generic.List'1[Microsoft.Azure.Commands.KeyVault.Models.PSDeletedVault]

## NOTES

## RELATED LINKS

[New-AzureRmKeyVault](./New-AzureRmKeyVault.md)

[Hapus-AzureRmKeyVault](./Remove-AzureRmKeyVault.md)
