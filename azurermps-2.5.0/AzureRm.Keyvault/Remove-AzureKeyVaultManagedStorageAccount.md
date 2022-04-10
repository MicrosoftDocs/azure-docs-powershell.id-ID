---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/remove-azurekeyvaultmanagedstorageaccount
schema: 2.0.0
ms.openlocfilehash: b9379ff63e027cf8e8be6365cdb5cafde9895fcd2ede071bb4de6d02fd74389c
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140863901"
---
# Remove-AzureKeyVaultManagedStorageAccount

## SYNOPSIS
Menghapus kunci vault yang dikelola Azure Storage Dan semua definisi SAS terkait.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureKeyVaultManagedStorageAccount [-VaultName] <String> [-AccountName] <String> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memisahkan akun Azure Storage dari Key Vault. Ini tidak akan menghapus Azure Storage Anda, tetapi menghapus kunci akun agar tidak dikelola oleh Azure Key Vault. Semua kunci vault yang terkait Storage definisi SAS juga dihapus.

## EXAMPLES

### Contoh 1: Hapus Kunci Vault yang Azure Storage akun dan semua definisi SAS terkait.
```
PS C:\> Remove-AzureKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount'
```

Memisahkan akun Azure Storage 'mystorageaccount' dari Key Vault 'myvault' dan menghentikan Key Vault mengelola kuncinya. Akun 'mystorageaccount' tidak akan dihapus. Semua definisi Key Vault Storage SAS yang terkait dengan akun ini akan dihapus.

### Contoh 2: Hapus Kunci Vault yang Azure Storage akun dan semua definisi SAS terkait tanpa konfirmasi pengguna.
```
PS C:\> Remove-AzureKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount' -Force -Confirm:$False
```

Memisahkan akun Azure Storage 'mystorageaccount' dari Key Vault 'myvault' dan menghentikan Key Vault mengelola kuncinya. Akun 'mystorageaccount' tidak akan dihapus. Semua definisi Key Vault Storage SAS yang terkait dengan akun ini akan dihapus.

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
