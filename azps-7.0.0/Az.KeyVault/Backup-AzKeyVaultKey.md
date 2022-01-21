---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: A82392AA-B12B-443E-8704-7CF5A9F8ED58
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultKey.md
ms.openlocfilehash: dfff0e118f9714c49066aebedcd03919b712107e
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136556150"
---
# Backup-AzKeyVaultKey

## SYNOPSIS
Mencadangkan kunci di vault kunci.

## SYNTAX

### ByKeyName (Default)
```
Backup-AzKeyVaultKey [-VaultName] <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HsmByKeyName
```
Backup-AzKeyVaultKey -HsmName <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByKey
```
Backup-AzKeyVaultKey [-InputObject] <PSKeyVaultKeyIdentityItem> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Backup-AzKeyVaultKey** mencadangkan kunci tertentu dalam kunci vault dengan mengunduh dan menyimpannya dalam file.
Jika terdapat beberapa versi kunci, semua versi disertakan dalam cadangan.
Karena dienkripsi, konten yang diunduh tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan kunci yang dicadangkan ke vault kunci apa pun dalam langganan yang menjadi tempat penyimpanan tersebut dicadangkan.
Alasan umum untuk menggunakan cmdlet ini adalah: 
- Anda ingin escrow salinan kunci Anda, sehingga Anda memiliki salinan offline jika Anda secara tidak sengaja menghapus kunci di vault kunci Anda.
 
- Anda membuat kunci menggunakan Key Vault dan sekarang ingin kloning kunci ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan.
Gunakan cmdlet **Backup-AzKeyKey** untuk mengambil kunci dalam format terenkripsi, lalu gunakan cmdlet Restore-AzKeyVaultKey dan tentukan kunci vault di kawasan kedua.

## EXAMPLES

### Contoh 1: Mencadangkan kunci dengan nama file yang dihasilkan secara otomatis
```powershell
PS C:\Users\username\> Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey'

C:\Users\username\mykeyvault-mykey-1527029447.01191
```

Perintah ini mengambil kunci yang bernama MyKey dari penyimpanan kunci bernama MyKeyVault dan menyimpan cadangan kunci tersebut ke file yang otomatis dinamai untuk Anda, dan menampilkan nama file tersebut.

### Contoh 2: Mencadangkan kunci ke nama file tertentu
```powershell
PS C:\> Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey' -OutputFile 'C:\Backup.blob'

C:\Backup.blob
```

Perintah ini mengambil kunci yang bernama MyKey dari kunci vaultnamed MyKeyVault dan menyimpan cadangan kunci itu ke file bernama Backup.blob.

### Contoh 3: Mencadangkan kunci yang sebelumnya diambil ke nama file tertentu, menimpa file tujuan tanpa memberikan perintah.
```powershell
PS C:\> $key = Get-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey'
PS C:\> Backup-AzKeyVaultKey -Key $key -OutputFile 'C:\Backup.blob' -Force

C:\Backup.blob
```

Perintah ini membuat cadangan kunci bernama $key. Nama di vault bernama $key. VaultName ke file bernama Backup.blob, akan menimpa file tanpa masalah jika file sudah ada.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Menimpa file tertentu jika ada

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HsmName
Nama HSM. Cmdlet menyusun FQDN dari HSM yang dikelola berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: HsmByKeyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Bundel utama ke cadangan, saluran dari output panggilan pengambilan.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem
Parameter Sets: ByKey
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama kunci untuk di cadangan.

```yaml
Type: System.String
Parameter Sets: ByKeyName, HsmByKeyName
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kunci vault yang berisi kunci untuk cadangan.

```yaml
Type: System.String
Parameter Sets: ByKeyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem

## OUTPUTS

### System.String

## CATATAN

## RELATED LINKS

[Add-AzKeyVaultKey](./Add-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Remove-AzKeyVaultKey](./Remove-AzKeyVaultKey.md)

[Restore-AzKeyVaultKey](./Restore-AzKeyVaultKey.md)

