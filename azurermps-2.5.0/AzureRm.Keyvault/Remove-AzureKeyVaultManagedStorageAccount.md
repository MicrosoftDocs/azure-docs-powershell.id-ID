---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/remove-azurekeyvaultmanagedstorageaccount
schema: 2.0.0
ms.openlocfilehash: 345d4ad784ad00480e15daf5580f23cbb0595e43
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142927775"
---
# Remove-AzureKeyVaultManagedStorageAccount

## SYNOPSIS
Menghapus akun Azure Storage yang dikelola Key Vault dan semua definisi SAS terkait.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureKeyVaultManagedStorageAccount [-VaultName] <String> [-AccountName] <String> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memisahkan Akun Azure Storage dari Key Vault. Tindakan ini tidak menghapus Akun Azure Storage tetapi menghapus kunci akun agar tidak dikelola oleh Azure Key Vault. Semua definisi Key Vault dikelola Storage SAS yang terkait juga dihapus.

## EXAMPLES

### Contoh 1: Hapus akun Azure Storage terkelola Key Vault dan semua definisi SAS terkait.
```
PS C:\> Remove-AzureKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount'
```

Memisahkan Azure Storage Akun 'mystorageaccount' dari Key Vault 'myvault' dan menghentikan Key Vault mengelola kuncinya. Akun 'mystorageaccount' tidak akan dihapus. Semua Key Vault dikelola Storage definisi SAS yang terkait dengan akun ini akan dihapus.

### Contoh 2: Hapus akun Azure Storage yang dikelola Key Vault dan semua definisi SAS terkait tanpa konfirmasi pengguna.
```
PS C:\> Remove-AzureKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount' -Force -Confirm:$False
```

Memisahkan Azure Storage Akun 'mystorageaccount' dari Key Vault 'myvault' dan menghentikan Key Vault mengelola kuncinya. Akun 'mystorageaccount' tidak akan dihapus. Semua Key Vault dikelola Storage definisi SAS yang terkait dengan akun ini akan dihapus.

## PARAMETERS

### -AccountName
Key Vault nama akun penyimpanan terkelola. Cmdlet menyusun FQDN nama akun penyimpanan terkelola dari nama kubah, lingkungan yang saat ini dipilih, dan nama akun penyimpanan yang ditukar.

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

### -Paksa
Jangan meminta konfirmasi.

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

### -PassThru
Cmdlet tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, cmdlet mengembalikan akun penyimpanan terkelola yang dihapus.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageAccount

## NOTES

## RELATED LINKS

[Cmdlet Azure Key Vault](/powershell/module/azurerm.keyvault/)
