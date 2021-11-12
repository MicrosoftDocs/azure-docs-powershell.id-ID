---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: A82392AA-B12B-443E-8704-7CF5A9F8ED58
online version: https://go.microsoft.com/fwlink/?LinkId=690296
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Backup-AzureKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Backup-AzureKeyVaultKey.md
ms.openlocfilehash: f6d6b362a93897dc854170b8cbbbfd228b305abc
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422366"
---
# Backup-AzureKeyVaultKey

## SYNOPSIS
Mencadangkan kunci di vault kunci.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByKeyName (Default)
```
Backup-AzureKeyVaultKey [-VaultName] <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByKey
```
Backup-AzureKeyVaultKey [-Key] <KeyBundle> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Backup-AzureKeyVaultKey** mencadangkan kunci tertentu dalam kunci vault dengan mengunduh dan menyimpannya dalam file.
Jika terdapat beberapa versi kunci, semua versi disertakan dalam cadangan.
Karena dienkripsi, konten yang diunduh tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan kunci yang dicadangkan ke vault kunci apa pun dalam langganan yang menjadi tempat penyimpanan tersebut dicadangkan.

Alasan umum untuk menggunakan cmdlet ini adalah: 

- Anda ingin escrow salinan kunci Anda, sehingga Anda memiliki salinan offline jika Anda secara tidak sengaja menghapus kunci di vault kunci Anda.
 
- Anda membuat kunci menggunakan Key Vault dan sekarang ingin kloning kunci ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan.
Gunakan cmdlet **Backup-AzureKeyKey** untuk mengambil kunci dalam format terenkripsi, lalu gunakan cmdlet Restore-AzureKeyVaultKey dan tentukan kunci vault di kawasan kedua.

## EXAMPLES

### Contoh 1: Mencadangkan kunci dengan nama file yang dihasilkan secara otomatis
```
PS C:\>Backup-AzureKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey'
```

Perintah ini mengambil kunci yang bernama MyKey dari penyimpanan kunci bernama MyKeyVault dan menyimpan cadangan kunci tersebut ke file yang otomatis dinamai untuk Anda, dan menampilkan nama file tersebut.

### Contoh 2: Mencadangkan kunci ke nama file tertentu
```
PS C:\>Backup-AzureKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey' -OutputFile 'C:\Backup.blob'
```

Perintah ini mengambil kunci yang bernama MyKey dari kunci vaultnamed MyKeyVault dan menyimpan cadangan kunci itu ke file bernama Backup.blob.

### Contoh 3: Mencadangkan kunci yang sebelumnya diambil ke nama file tertentu, menimpa file tujuan tanpa memberikan perintah.
```
PS C:\>$key = Get-AzureKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey'
PS C:\>Backup-AzureKeyVaultKey -Key $key -OutputFile 'C:\Backup.blob' -Force
```

Perintah ini membuat cadangan kunci bernama $key. Nama di vault bernama $key. VaultName ke file bernama Backup.blob, akan menimpa file tanpa masalah jika file sudah ada.

## PARAMETERS

### -Force
Menimpa file tertentu jika ada

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key
Menentukan kunci yang diambil sebelumnya yang akan dicadangkan.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.KeyBundle
Parameter Sets: ByKey
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama kunci untuk di cadangan.

```yaml
Type: System.String
Parameter Sets: ByKeyName
Aliases: KeyName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputFile
Menentukan file output tempat blob cadangan disimpan.
Jika Anda tidak menentukan parameter ini, cmdlet ini akan menghasilkan nama file untuk Anda.
Jika Anda menentukan nama file output yang sudah ada, operasi tidak akan selesai dan mengembalikan pesan kesalahan bahwa file cadangan sudah ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kunci vault yang berisi kunci untuk cadangan.

```yaml
Type: System.String
Parameter Sets: ByKeyName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### String
Cmdlet mengembalikan jalur file output yang berisi cadangan kunci.

## CATATAN

## RELATED LINKS

[Add-AzureKeyVaultKey](./Add-AzureKeyVaultKey.md)

[Get-AzureKeyVaultKey](./Get-AzureKeyVaultKey.md)

[Remove-AzureKeyVaultKey](./Remove-AzureKeyVaultKey.md)

[Restore-AzureKeyVaultKey](./Restore-AzureKeyVaultKey.md)

