---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 80AAA327-77C6-4372-9461-FFED5A15E678
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/backup-AzKeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Backup-AzKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Backup-AzKeyVaultSecret.md
ms.openlocfilehash: b1f26123579589c15ac4eff6b577706270a7e15a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141874184"
---
# Backup-AzKeyVaultSecret

## SYNOPSIS
Mencadangkan rahasia dalam kubah kunci.

## SYNTAX

### BySecretName (Default)
```
Backup-AzKeyVaultSecret [-VaultName] <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySecret
```
Backup-AzKeyVaultSecret [-Secret] <Secret> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Backup-AzKeyVaultSecret** mencadangkan rahasia tertentu dalam kubah kunci dengan mengunduhnya dan menyimpannya dalam file.
Jika ada beberapa versi rahasia, semua versi disertakan dalam cadangan.
Karena konten yang diunduh dienkripsi, konten tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan rahasia yang dicadangkan ke kubah kunci apa pun dalam langganan tempat penyimpanan tersebut dicadangkan.

Alasan umum untuk menggunakan cmdlet ini adalah:

- Anda ingin memasukkan salinan rahasia Anda, sehingga Anda memiliki salinan offline jika Anda secara tidak sengaja menghapus rahasia Anda di kubah kunci Anda.
- Anda menambahkan rahasia ke kubah kunci dan sekarang ingin mengkloning rahasia ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan. Gunakan cmdlet Backup-AzKeyVaultSecret untuk mengambil rahasia dalam format terenkripsi lalu gunakan cmdlet Restore-AzKeyVaultSecret dan tentukan kubah kunci di kawasan kedua. (Perhatikan bahwa kawasan harus memiliki geografi yang sama.)

## EXAMPLES

### Contoh 1: Mencadangkan rahasia dengan nama file yang dihasilkan secara otomatis
```
PS C:\>Backup-AzKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret'
```

Perintah ini mengambil rahasia bernama MySecret dari kubah kunci bernama MyKeyVault dan menyimpan cadangan rahasia tersebut ke file yang secara otomatis dinamai untuk Anda, dan menampilkan nama file.

### Contoh 2: Mencadangkan rahasia ke nama file tertentu, menimpa file yang sudah ada tanpa meminta
```
PS C:\>Backup-AzKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret' -OutputFile 'C:\Backup.blob' -Force
```

Perintah ini mengambil rahasia bernama MySecret dari kunci vaultnamed MyKeyVault dan menyimpan cadangan rahasia tersebut ke file bernama Backup.blob.

### Contoh 3: Mencadangkan rahasia yang sebelumnya diambil ke nama file tertentu
```
PS C:\>$secret = Get-AzKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret'
PS C:\>Backup-AzKeyVaultSecret -Secret $secret -OutputFile 'C:\Backup.blob'
```

Perintah ini menggunakan nama dan nama kubah objek $secret untuk mengambil rahasia dan menyimpan cadangannya ke file bernama Backup.blob.

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

### -Paksa
Meminta konfirmasi sebelum menimpa file output, jika ada.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama rahasia untuk dicadangkan.

```yaml
Type: String
Parameter Sets: BySecretName
Aliases: SecretName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputFile
Menentukan berkas output tempat blob cadangan disimpan.
Jika Anda tidak menentukan parameter ini, cmdlet ini akan menghasilkan nama file untuk Anda.
Jika Anda menentukan nama file output yang sudah ada, operasi tidak akan selesai dan mengembalikan pesan kesalahan bahwa file cadangan sudah ada.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rahasia
Menentukan objek yang nama dan kubahnya harus digunakan untuk operasi pencadangan.

```yaml
Type: Secret
Parameter Sets: BySecret
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kubah kunci yang berisi rahasia untuk dicadangkan.

```yaml
Type: String
Parameter Sets: BySecretName
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### String
Cmdlet mengembalikan jalur file output yang berisi cadangan kunci.

## CATATAN

## RELATED LINKS

[Set-AzKeyVaultSecret](./Set-AzKeyVaultSecret.md)

[Get-AzKeyVaultSecret](./Get-AzKeyVaultSecret.md)

[Remove-AzKeyVaultSecret](./Remove-AzKeyVaultSecret.md)

[Restore-AzKeyVaultSecret](./Restore-AzKeyVaultSecret.md)

