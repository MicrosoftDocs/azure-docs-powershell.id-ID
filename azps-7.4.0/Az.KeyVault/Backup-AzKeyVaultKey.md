---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: A82392AA-B12B-443E-8704-7CF5A9F8ED58
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultKey.md
ms.openlocfilehash: e0a22ce99438388cfaccbb4f0cc38f8f6e284920
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142747341"
---
# Backup-AzKeyVaultKey

## SYNOPSIS
Mencadangkan kunci dalam kubah kunci.

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
Cmdlet **Backup-AzKeyVaultKey** mencadangkan kunci tertentu dalam kubah kunci dengan mengunduhnya dan menyimpannya dalam file.
Jika terdapat beberapa versi kunci, semua versi disertakan dalam cadangan.
Karena konten yang diunduh dienkripsi, konten tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan kunci yang dicadangkan ke kubah kunci apa pun dalam langganan tempatnya dicadangkan.
Alasan umum untuk menggunakan cmdlet ini adalah: 
- Anda ingin memasukkan salinan kunci, sehingga Anda memiliki salinan offline jika Anda secara tidak sengaja menghapus kunci di kubah kunci Anda.
 
- Anda membuat kunci menggunakan Key Vault dan sekarang ingin mengkloning kunci ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan.
Gunakan cmdlet **Backup-AzKeyVaultKey** untuk mengambil kunci dalam format terenkripsi lalu gunakan cmdlet Restore-AzKeyVaultKey dan tentukan kubah kunci di kawasan kedua.

## EXAMPLES

### Contoh 1: Mencadangkan kunci dengan nama file yang dihasilkan secara otomatis
```powershell
Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey'
```

```output
C:\Users\username\mykeyvault-mykey-1527029447.01191
```

Perintah ini mengambil kunci bernama MyKey dari kubah kunci bernama MyKeyVault dan menyimpan cadangan kunci tersebut ke file yang secara otomatis dinamai untuk Anda, dan menampilkan nama file.

### Contoh 2: Mencadangkan kunci ke nama file tertentu
```powershell
Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey' -OutputFile 'C:\Backup.blob'
```

```output
C:\Backup.blob
```

Perintah ini mengambil kunci bernama MyKey dari kunci vaultnamed MyKeyVault dan menyimpan cadangan kunci tersebut ke file bernama Backup.blob.

### Contoh 3: Mencadangkan kunci yang sebelumnya diambil ke nama file tertentu, menimpa file tujuan tanpa meminta.
```powershell
$key = Get-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyKey'
Backup-AzKeyVaultKey -Key $key -OutputFile 'C:\Backup.blob' -Force
```

```output
C:\Backup.blob
```

Perintah ini membuat cadangan kunci bernama $key. Nama dalam kubah bernama $key. VaultName ke file bernama Backup.blob, menimpa file secara diam-diam jika sudah ada.

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

### -Paksa
Timpa file yang diberikan jika ada

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
Nama HSM. Cmdlet menyusun FQDN dari HSM yang dikelola berdasarkan nama dan lingkungan yang dipilih saat ini.

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
Key bundle untuk mencadangkan, disalurkan dari output panggilan pengambilan.

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
Menentukan nama kunci untuk dicadangkan.

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
Menentukan nama kubah kunci yang berisi kunci untuk dicadangkan.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKeyIdentityItem

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Add-AzKeyVaultKey](./Add-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Hapus-AzKeyVaultKey](./Remove-AzKeyVaultKey.md)

[Restore-AzKeyVaultKey](./Restore-AzKeyVaultKey.md)

