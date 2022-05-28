---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 80AAA327-77C6-4372-9461-FFED5A15E678
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultSecret.md
ms.openlocfilehash: cbcb60e57d89f692d5e75f129243051dd843af79
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145538911"
---
# Cadangan-RahasiaAzKeyVault

## SYNOPSIS
Mencadangkan rahasia di brankas kunci.

## SYNTAX

### BySecretName (Default)
```
Backup-AzKeyVaultSecret [-VaultName] <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySecret
```
Backup-AzKeyVaultSecret [-InputObject] <PSKeyVaultSecretIdentityItem> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Backup-AzKeyVaultSecret** mencadangkan rahasia tertentu dalam brankas kunci dengan mengunduhnya dan menyimpannya dalam file.
Jika ada beberapa versi rahasia, semua versi disertakan dalam cadangan.
Karena konten yang diunduh dienkripsi, konten tersebut tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan rahasia yang dicadangkan ke brankas kunci apa pun dalam langganan tempatnya dicadangkan.
Alasan umum untuk menggunakan cmdlet ini adalah:
- Anda ingin mengekstrak salinan rahasia Anda, sehingga Anda memiliki salinan offline jika Anda secara tidak sengaja menghapus rahasia Anda di brankas kunci Anda.
- Anda menambahkan rahasia ke brankas kunci dan sekarang ingin mengkloning rahasia ke wilayah Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua instans aplikasi terdistribusi Anda. Gunakan cmdlet Backup-AzKeyVaultSecret untuk mengambil rahasia dalam format terenkripsi lalu gunakan cmdlet Restore-AzKeyVaultSecret dan tentukan brankas kunci di wilayah kedua. (Perhatikan bahwa wilayah harus termasuk dalam geografi yang sama.)

## EXAMPLES

### Contoh 1: Mencadangkan rahasia dengan nama file yang dibuat secara otomatis
```powershell
Backup-AzKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret'
```

```output
C:\Users\username\mykeyvault-mysecret-1527029447.01191
```

Perintah ini mengambil rahasia bernama MySecret dari brankas kunci bernama MyKeyVault dan menyimpan cadangan rahasia tersebut ke file yang secara otomatis dinamai untuk Anda, dan menampilkan nama file.

### Contoh 2: Mencadangkan rahasia ke nama file tertentu, menimpa file yang ada tanpa meminta
```powershell
Backup-AzKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret' -OutputFile 'C:\Backup.blob' -Force
```

```output
C:\Backup.blob
```

Perintah ini mengambil rahasia bernama MySecret dari brankas kunci bernama MyKeyVault dan menyimpan cadangan rahasia tersebut ke file bernama Backup.blob.

### Contoh 3: Mencadangkan rahasia yang sebelumnya diambil ke nama file tertentu
```powershell
$secret = Get-AzKeyVaultSecret -VaultName 'MyKeyVault' -Name 'MySecret'
Backup-AzKeyVaultSecret -Secret $secret -OutputFile 'C:\Backup.blob'
```

```output
C:\Backup.blob
```

Perintah ini menggunakan nama dan nama vault objek $secret untuk mengambil rahasia dan menyimpan cadangannya ke file bernama Backup.blob.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
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
Rahasia yang akan dicadangkan, disalurkan dari output panggilan pengambilan.

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

### -Name
Menentukan nama rahasia yang akan dicadangkan.

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
Menentukan file output tempat blob cadangan disimpan.
Jika Anda tidak menentukan parameter ini, cmdlet ini menghasilkan nama file untuk Anda.
Jika Anda menentukan nama file output yang ada, operasi tidak akan selesai dan mengembalikan pesan kesalahan bahwa file cadangan sudah ada.

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
Menentukan nama brankas kunci yang berisi rahasia untuk dicadangkan.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecretIdentityItem

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Atur-AzKeyVaultSecret](./Set-AzKeyVaultSecret.md)

[Get-AzKeyVaultSecret](./Get-AzKeyVaultSecret.md)

[Remove-AzKeyVaultSecret](./Remove-AzKeyVaultSecret.md)

[Pemulihan-RahasiaAzKeyVault](./Restore-AzKeyVaultSecret.md)

