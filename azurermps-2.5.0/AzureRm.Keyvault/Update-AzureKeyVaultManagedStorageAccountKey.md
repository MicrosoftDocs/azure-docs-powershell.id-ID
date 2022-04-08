---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/update-azurekeyvaultmanagedstorageaccountkey
schema: 2.0.0
ms.openlocfilehash: cab7b76f6179ffb2b5c077b7d42f7ee3a9f02360
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "140852796"
---
# Update-AzureKeyVaultManagedStorageAccountKey

## SYNOPSIS
Meregenerasi kunci tertentu dari Key Vault Azure Storage Baru.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Update-AzureKeyVaultManagedStorageAccountKey [-VaultName] <String> [-AccountName] <String> [-KeyName] <String>
 [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Meregenerasi kunci tertentu dari Key Vault Azure Storage Akun dan mengatur kunci tersebut sebagai kunci aktif. Key Vault proksi panggilan ke Azure Resource Manager untuk meregenerasi kunci. Penelepon harus memiliki izin untuk meregenerasi kunci pada akun Azure Storage tertentu.

## EXAMPLES

### Contoh 1: Regenerate a key
```
PS C:\> Update-AzureKeyVaultManagedStorageAccountKey -VaultName 'myvault' -AccountName 'mystorageaccount' -KeyName 'key1'
```

Meregenerasi 'key1' akun 'mystorageaccount' dan mengatur 'key1' sebagai aktif Key Vault yang Azure Storage Account.

## PARAMETERS

### -Nama Akun
Nama akun penyimpanan terkelola Key Vault. Cmdlet membangun FQDN dari nama akun penyimpanan terkelola dari nama vault, lingkungan yang saat ini dipilih dan nama akun penyimpanan tertentu.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountName, Name

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

### -Force
Jangan minta konfirmasi.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyName
Nama kunci akun penyimpanan untuk meregenerasi dan menjadi aktif.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, cmdlet akan mengembalikan akun penyimpanan terkelola yang dihapus.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageAccount

## CATATAN

## RELATED LINKS

[Cmdlet Key Vault Azure](/powershell/module/azurerm.keyvault/)
