---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: C4E7ACDF-22FB-4D49-93B3-69E787B7E0CD
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/restore-AzKeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Restore-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Restore-AzKeyVaultKey.md
ms.openlocfilehash: 5d090bae05e3d931fbf41b656ea66409d1297e8f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142499206"
---
# Restore-AzKeyVaultKey

## SYNOPSIS
Membuat kunci dalam kubah kunci dari tombol yang dicadangkan.

## SYNTAX

```
Restore-AzKeyVaultKey [-VaultName] <String> [-InputFile] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzKeyVaultKey** membuat kunci dalam kubah kunci yang ditentukan.
Kunci ini adalah replika kunci yang dicadangkan dalam file input dan memiliki nama yang sama dengan kunci aslinya.
Jika kubah kunci sudah memiliki kunci dengan nama yang sama, cmdlet ini gagal, bukan menimpa kunci asli.
Jika cadangan berisi beberapa versi kunci, semua versi akan dipulihkan.

Kubah kunci yang Anda pulihkan kuncinya bisa berbeda dari kubah kunci yang Anda cadangkan dari kunci.
Namun, kubah kunci harus menggunakan langganan yang sama dan berada di kawasan Azure dalam geografi yang sama (misalnya, Amerika Utara).
Lihat Pusat Kepercayaan Microsoft Azure (https://azure.microsoft.com/support/trust-center/) untuk pemetaan kawasan Azure ke geografis.

## EXAMPLES

### Contoh 1: Memulihkan kunci cadangan
```
PS C:\>Restore-AzKeyVaultKey -VaultName 'MyKeyVault' -InputFile "C:\Backup.blob"
```

Perintah ini memulihkan kunci, termasuk semua versinya, dari file cadangan bernama Backup.blob ke dalam kubah kunci bernama MyKeyVault.

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

### -InputFile
Menentukan berkas input yang berisi cadangan kunci untuk dipulihkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kubah kunci untuk memulihkan kunci.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.KeyBundle

## CATATAN

## RELATED LINKS

[Add-AzKeyVaultKey](./Add-AzKeyVaultKey.md)

[Backup-AzKeyVaultKey](./Backup-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Hapus-AzKeyVaultKey](./Remove-AzKeyVaultKey.md)

