---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: A7C287C4-E9FD-407A-91BD-EFA17C33FC8B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/get-azurermkeyvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Get-AzureRmKeyVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Get-AzureRmKeyVault.md
ms.openlocfilehash: 7b26eeb94854d21791bb662b4c1d9ce19973a193
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421385"
---
# Get-AzureRmKeyVault

## SYNOPSIS
Dapatkan kunci vault.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ListAllVaultsInSubscription (Default)
```
Get-AzureRmKeyVault [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetVaultByName
```
Get-AzureRmKeyVault [[-VaultName] <String>] [[-ResourceGroupName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByDeletedVault
```
Get-AzureRmKeyVault [-VaultName] <String> [-Location] <String> [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListAllDeletedVaultsInSubscription
```
Get-AzureRmKeyVault [-InRemovedState] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmKeyVault** mendapatkan informasi tentang vault kunci dalam langganan. Anda dapat melihat semua contoh key vault dalam langganan, atau memfilter hasil menurut grup sumber daya atau key vault tertentu.

Perlu diingat bahwa meskipun menentukan grup sumber daya bersifat opsional untuk cmdlet ini saat Anda mendapatkan vault kunci tunggal, Anda harus melakukannya untuk kinerja yang lebih baik.

## EXAMPLES

### Contoh 1: Mendapatkan semua kunci vault dalam langganan Anda saat ini
```
PS C:\>Get-AzureRMKeyVault
```

Perintah ini akan memasukkan semua kunci vault di langganan Anda saat ini.

### Contoh 2: Dapatkan vault kunci tertentu
```
PS C:\>$MyVault = Get-AzureRMKeyVault -VaultName 'Contoso03Vault'
```

Perintah ini akan memasukkan kunci vault bernama Contoso03Vault dalam langganan Anda saat ini, lalu menyimpannya dalam $MyVault tersebut. Anda dapat memeriksa properti $MyVault untuk mendapatkan detail tentang kunci vault.

### Contoh 3: Dapatkan vault kunci dalam grup sumber daya
```
PS C:\>Get-AzureRmKeyVault -ResourceGroupName 'ContosoPayRollResourceGroup'
```

Perintah ini memasukkan semua penyimpanan kunci ke grup sumber daya bernama ContosoPayRollResourceGroup.

### Contoh 4: Mendapatkan semua vault kunci yang dihapus di langganan Anda saat ini
```
PS C:\>Get-AzureRmKeyVault -InRemovedState
```

Perintah ini akan memasukkan semua kunci vault yang dihapus di langganan Anda saat ini.

### Contoh 5: Mendapatkan vault kunci terhapus
```
PS C:\>Get-AzureRMKeyVault -VaultName 'Contoso03Vault'  -Location 'eastus2' -InRemovedState
```

Perintah ini mendapatkan informasi kunci vault terhapus yang bernama Contoso03Vault dalam langganan Anda saat ini dan di kawasan eastus2.

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

### -InRemovedState
Menentukan apakah akan memperlihatkan vault yang dihapus sebelumnya dalam output.

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
Lokasi vault yang dihapus.

```yaml
Type: String
Parameter Sets: ByDeletedVault
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang terkait dengan key vault atau key vaults yang sedang ditanya.

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
Menentukan nama kunci vault.

```yaml
Type: String
Parameter Sets: GetVaultByName
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByDeletedVault
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault

### System.Collections.Generic.List'1[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultIdentityItem]

### Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVault

### System.Collections.Generic.List'1[Microsoft.Azure.Commands.KeyVault.Models.PSDeletedKeyVault]

## CATATAN

## RELATED LINKS

[New-AzureRmKeyVault](./New-AzureRmKeyVault.md)

[Remove-AzureRmKeyVault](./Remove-AzureRmKeyVault.md)
