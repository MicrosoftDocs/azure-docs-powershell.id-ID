---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 817BF177-519F-47BA-86CF-4591FB402E2Dl
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/remove-azurekeyvaultkey
schema: 2.0.0
ms.openlocfilehash: 911ea06fdfa9d4d90f8c9935e3e98c026c70cce5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142104116"
---
# Remove-AzureKeyVaultKey

## SYNOPSIS
Menghapus kunci dalam kubah kunci.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureKeyVaultKey [-VaultName] <String> [-Name] <String> [-Force] [-PassThru] [-InRemovedState]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzureKeyVaultKey menghapus kunci dalam kubah kunci.
Jika kunci dihapus secara tidak sengaja, kunci dapat dipulihkan menggunakan Undo-AzureKeyVaultKeyRemoval oleh pengguna dengan izin khusus 'pulihkan'.
Cmdlet ini memiliki nilai tinggi untuk properti **ConfirmImpact** .

## EXAMPLES

### Contoh 1: Menghapus kunci dari kubah kunci
```
PS C:\>Remove-AzureKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware'
```

Perintah ini menghapus kunci bernama ITSoftware dari kubah kunci bernama Contoso.

### Contoh 2: Menghapus kunci tanpa konfirmasi pengguna
```
PS C:\>Remove-AzureKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware' -Force -Confirm:$False
```

Perintah ini menghapus kunci bernama ITSoftware dari kubah kunci bernama Contoso.
Perintah menentukan parameter *Paksa* dan *Konfirmasi* , dan oleh karena itu, cmdlet tidak meminta Anda untuk mengonfirmasi.

### Contoh 3: Membersihkan kunci yang dihapus dari kubah kunci secara permanen
```
PS C:\>Remove-AzureKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware' -InRemovedState
```

Perintah ini menghapus kunci bernama ITSoftware dari kubah kunci bernama Contoso secara permanen.
Menjalankan cmdlet ini memerlukan izin 'pembersihan', yang harus telah diberikan secara eksplisit dan sebelumnya kepada pengguna untuk kubah kunci ini.

### Contoh 4: Hapus tombol dengan menggunakan operator pipeline
```
PS C:\>Get-AzureKeyVaultKey -VaultName 'Contoso' | Where-Object {$_.Attributes.Enabled -eq $False} | Remove-AzureKeyVaultKey
```

Perintah ini mendapatkan semua kunci di kubah kunci bernama Contoso, dan meneruskannya ke cmdlet **Where-Object** menggunakan operator pipeline.
Cmdlet tersebut melewati kunci yang memiliki nilai $False untuk atribut **Enabled** ke cmdlet saat ini.
Cmdlet itu menghapus kunci tersebut.

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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
Hapus kunci yang dihapus sebelumnya secara permanen.

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
Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN) kunci berdasarkan nama yang ditentukan parameter ini, nama kubah kunci, dan lingkungan Anda saat ini.

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
Menunjukkan bahwa cmdlet ini mengembalikan objek **Microsoft.Azure.Commands.KeyVault.Models.KeyBundle** .
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
Menentukan nama kubah kunci untuk menghapus kunci.
Cmdlet ini menyusun FQDN kubah kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.DeletedKeyBundle
Cmdlet ini mengembalikan nilai hanya jika Anda menentukan parameter *PassThru* .

## CATATAN

## RELATED LINKS

[Add-AzureKeyVaultKey](./Add-AzureKeyVaultKey.md)

[Get-AzureKeyVaultKey](./Get-AzureKeyVaultKey.md)

[Set-AzureKeyVaultKeyAttribute](./Set-AzureKeyVaultKeyAttribute.md)

[Batalkan-AzureKeyVaultKeyRemoval](./Undo-AzureKeyVaultKeyRemoval.md)

