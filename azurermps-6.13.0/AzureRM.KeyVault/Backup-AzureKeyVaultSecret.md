---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 80AAA327-77C6-4372-9461-FFED5A15E678
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/backup-azurekeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Backup-AzureKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Backup-AzureKeyVaultSecret.md
ms.openlocfilehash: 6021e9c4c3be3ac4eb2721684b9f94463e1b69af
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143162333"
---
# Backup-AzureKeyVaultSecret

## SYNOPSIS
Mencadangkan rahasia dalam kubah kunci.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### BySecretName (Default)
```
Backup-AzureKeyVaultSecret [-VaultName] <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySecret
```
Backup-AzureKeyVaultSecret [-InputObject] <PSKeyVaultSecretIdentityItem> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Backup-AzureKeyVaultSecret** mencadangkan rahasia tertentu dalam kubah kunci dengan mengunduhnya dan menyimpannya dalam file.
Jika ada beberapa versi rahasia, semua versi disertakan dalam cadangan.
Karena konten yang diunduh dienkripsi, konten tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan rahasia yang dicadangkan ke kubah kunci apa pun dalam langganan tempat penyimpanan tersebut dicadangkan.
Alasan umum untuk menggunakan cmdlet ini adalah:
- Anda ingin memasukkan salinan rahasia Anda, sehingga Anda memiliki salinan offline jika Anda secara tidak sengaja menghapus rahasia Anda di kubah kunci Anda.
- Anda menambahkan rahasia ke kubah kunci dan sekarang ingin mengkloning rahasia ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan. Gunakan cmdlet Backup-AzureKeyVaultSecret untuk mengambil rahasia dalam format terenkripsi lalu gunakan cmdlet Restore-AzureKeyVaultSecret dan tentukan kubah kunci di kawasan kedua. (Perhatikan bahwa kawasan harus memiliki geografi yang sama.)

## EXAMPLES

### Contoh 1: Mencadangkan rahasia dengan nama file yang dihasilkan secara otomatis
```powershell
PS C:\Users\username\> Backup-AzureKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret'

C:\Users\username\mykeyvault-mysecret-1527029447.01191
```

Perintah ini mengambil rahasia bernama MySecret dari kubah kunci bernama MyKeyVault dan menyimpan cadangan rahasia tersebut ke file yang secara otomatis dinamai untuk Anda, dan menampilkan nama file.

### Contoh 2: Mencadangkan rahasia ke nama file tertentu, menimpa file yang sudah ada tanpa meminta
```powershell
PS C:\> Backup-AzureKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret' -OutputFile 'C:\Backup.blob' -Force

C:\Backup.blob
```

Perintah ini mengambil rahasia bernama MySecret dari kunci vaultnamed MyKeyVault dan menyimpan cadangan rahasia tersebut ke file bernama Backup.blob.

### Contoh 3: Mencadangkan rahasia yang sebelumnya diambil ke nama file tertentu
```powershell
PS C:\> $secret = Get-AzureKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret'
PS C:\> Backup-AzureKeyVaultSecret -Secret $secret -OutputFile 'C:\Backup.blob'

C:\Backup.blob
```

Perintah ini menggunakan nama dan nama kubah objek $secret untuk mengambil rahasia dan menyimpan cadangannya ke file bernama Backup.blob.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Paksa
Meminta konfirmasi sebelum menimpa file output, jika ada.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Rahasia untuk dicadangkan, disalurkan dari output panggilan pengambilan.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecretIdentityItem
Parameter Sets: BySecret
Aliases: Secret

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama rahasia untuk dicadangkan.

```yaml
Type: System.String
Parameter Sets: BySecretName
Aliases: SecretName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFile
Menentukan berkas output tempat blob cadangan disimpan.
Jika Anda tidak menentukan parameter ini, cmdlet ini akan menghasilkan nama file untuk Anda.
Jika Anda menentukan nama file output yang sudah ada, operasi tidak akan selesai dan mengembalikan pesan kesalahan bahwa file cadangan sudah ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kubah kunci yang berisi rahasia untuk dicadangkan.

```yaml
Type: System.String
Parameter Sets: BySecretName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecretIdentityItem
Parameter: InputObject (ByValue)

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Set-AzureKeyVaultSecret](./Set-AzureKeyVaultSecret.md)

[Get-AzureKeyVaultSecret](./Get-AzureKeyVaultSecret.md)

[Hapus-AzureKeyVaultSecret](./Remove-AzureKeyVaultSecret.md)

[Pulihkan-AzureKeyVaultSecret](./Restore-AzureKeyVaultSecret.md)

