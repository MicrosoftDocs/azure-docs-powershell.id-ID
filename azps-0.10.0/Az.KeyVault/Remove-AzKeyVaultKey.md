---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 817BF177-519F-47BA-86CF-4591FB402E2Dl
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/remove-AzKeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Remove-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Remove-AzKeyVaultKey.md
ms.openlocfilehash: 15470f18e457f31deec66554c955890b52e26e83
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426212"
---
# Remove-AzKeyVaultKey

## SYNOPSIS
Menghapus kunci di kunci vault.

## SYNTAX

```
Remove-AzKeyVaultKey [-VaultName] <String> [-Name] <String> [-Force] [-PassThru] [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzKeyVaultKey akan menghapus kunci dalam kunci vault.
Jika kunci tidak sengaja terhapus, kunci dapat dipulihkan menggunakan Undo-AzKeyVaultKeyRemoval oleh pengguna dengan izin khusus 'pulihkan'.
Cmdlet ini memiliki nilai yang tinggi untuk **properti ConfirmImpact.**

## EXAMPLES

### Contoh 1: Menghapus kunci dari key vault
```
PS C:\>Remove-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware'
```

Perintah ini akan menghapus kunci yang bernama ITSoftware dari kunci vault bernama Contoso.

### Contoh 2: Hapus kunci tanpa konfirmasi pengguna
```
PS C:\>Remove-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware' -Force -Confirm:$False
```

Perintah ini akan menghapus kunci yang bernama ITSoftware dari kunci vault bernama Contoso.
Perintah menentukan parameter *Paksa* *dan Konfirmasi,* dan oleh karena itu, cmdlet tidak meminta konfirmasi Anda.

### Contoh 3: Membersihkan kunci yang dihapus dari key vault secara permanen
```
PS C:\>Remove-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware' -InRemovedState
```

Perintah ini akan menghapus kunci yang bernama ITSoftware dari penyimpanan kunci yang bernama Contoso secara permanen.
Menjalankan cmdlet ini memerlukan izin 'pembersihan', yang harus sebelumnya dan secara eksplisit diberikan kepada pengguna untuk vault kunci ini.

### Contoh 4: Menghapus tombol menggunakan operator saluran
```
PS C:\>Get-AzKeyVaultKey -VaultName 'Contoso' | Where-Object {$_.Attributes.Enabled -eq $False} | Remove-AzKeyVaultKey
```

Perintah ini memasukkan semua tombol di kunci vault bernama Contoso, dan memasukkannya ke cmdlet **Where-Object** menggunakan operator pipeline.
Cmdlet tersebut melewati tombol yang memiliki nilai lebih $False atribut **Enabled** ke cmdlet saat ini.
Cmdlet tersebut akan menghapus tombol tersebut.

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

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -InRemovedState
Menghapus kunci yang dihapus sebelumnya secara permanen.

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

### -Nama
Menentukan nama kunci yang akan dihapus.
Cmdlet ini menyusun nama domain (FQDN) yang sepenuhnya memenuhi syarat dari kunci berdasarkan nama yang ditentukan parameter ini, nama kunci vault, dan lingkungan Anda saat ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Menunjukkan bahwa cmdlet ini mengembalikan objek **Microsoft.Azure.Commands.KeyVault.Models.KeyBundle.**
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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
Menentukan nama key vault untuk menghapus kunci tersebut.
Cmdlet ini menyusun FQDN dari kunci vault berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.DeletedKeyBundle
Cmdlet ini akan mengembalikan nilai hanya jika Anda menentukan parameter *PassThru.*

## CATATAN

## RELATED LINKS

[Add-AzKeyVaultKey](./Add-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Set-AzKeyVaultKeyAttribute](./Set-AzKeyVaultKeyAttribute.md)

[Undo-AzKeyVaultKeyRemoval](./Undo-AzKeyVaultKeyRemoval.md)

