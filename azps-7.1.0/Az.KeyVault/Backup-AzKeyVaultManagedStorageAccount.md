---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultmanagedstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultManagedStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultManagedStorageAccount.md
ms.openlocfilehash: 048d9dccccea15272c5e104ca5447ef16bd7cd0f
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136762150"
---
# Backup-AzKeyVaultManagedStorageAccount

## SYNOPSIS
Mencadangkan akun penyimpanan yang dikelola KeyVault.

## SYNTAX

### ByStorageAccountName (Default)
```
Backup-AzKeyVaultManagedStorageAccount [-VaultName] <String> [-Name] <String> [[-OutputFile] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByStorageAccount
```
Backup-AzKeyVaultManagedStorageAccount [-InputObject] <PSKeyVaultManagedStorageAccountIdentityItem>
 [[-OutputFile] <String>] [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Backup-AzKeyVaultManagedStorageAccount** mencadangkan akun penyimpanan terkelola tertentu dalam kunci vault dengan mengunduh dan menyimpannya dalam file.
Karena dienkripsi, konten yang diunduh tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan akun penyimpanan yang dicadangkan ke vault kunci apa pun dalam langganan yang menjadi sumber cadangan, selama vault tersebut berada di Azure geography yang sama.
Alasan umum untuk menggunakan cmdlet ini adalah: 
- Anda ingin mempertahankan salinan offline akun penyimpanan jika anda tidak sengaja menghapus file asli dari vault.
 
- Anda membuat akun penyimpanan terkelola menggunakan Key Vault dan sekarang ingin kloning objek ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan.
Gunakan cmdlet **Backup-AzKeyVaultManagedStorageAccount** untuk mengambil akun penyimpanan terkelola dalam format terenkripsi lalu gunakan cmdlet **Restore-AzKeyVaultManagedStorageAccount** dan menentukan kunci vault di kawasan kedua.

## EXAMPLES

### Contoh 1: Mencadangkan akun penyimpanan terkelola dengan nama file yang dihasilkan secara otomatis
```powershell
PS C:\Users\username\> Backup-AzKeyVaultManagedStorageAccount -VaultName 'MyKeyVault' -Name 'MyMSAK'

C:\Users\username\mykeyvault-mymsak-1527029447.01191
```

Perintah ini mengambil akun penyimpanan terkelola bernama MyMSAK dari penyimpanan kunci bernama MyKeyVault dan menyimpan cadangan akun penyimpanan terkelola itu ke file yang diberi nama secara otomatis untuk Anda, dan menampilkan nama file tersebut.

### Contoh 2: Mencadangkan akun penyimpanan terkelola ke nama file tertentu
```powershell
PS C:\> Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyMSAK' -OutputFile 'C:\Backup.blob'

C:\Backup.blob
```

Perintah ini mengambil akun penyimpanan terkelola bernama MyMSAK dari penyimpanan kunci bernama MyKeyVault dan menyimpan cadangan akun penyimpanan yang dikelola itu ke file bernama Backup.blob.

### Contoh 3: Mencadangkan akun penyimpanan terkelola yang sebelumnya diambil ke nama file tertentu, menimpa file tujuan tanpa meminta.
```powershell
PS C:\> $msak = Get-AzKeyVaultManagedStorageAccount -VaultName 'MyKeyVault' -Name 'MyMSAK'
PS C:\> Backup-AzKeyVaultManagedStorageAccount -StorageAccount $msak -OutputFile 'C:\Backup.blob' -Force

C:\Backup.blob
```

Perintah ini membuat cadangan akun penyimpanan terkelola yang bernama $msak. Nama di vault bernama $msak. VaultName ke file bernama Backup.blob, akan menimpa file tanpa masalah jika file sudah ada.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -InputObject
Storage akun Anda dicadangkan, dibuat salurannya dari output panggilan pengambilan.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem
Parameter Sets: ByStorageAccount
Aliases: StorageAccount

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama rahasia.
Cmdlet menyusun FQDN rahasia dari nama vault, lingkungan yang saat ini dipilih dan nama rahasia.

```yaml
Type: System.String
Parameter Sets: ByStorageAccountName
Aliases: StorageAccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFile
File output.
File output untuk menyimpan cadangan akun penyimpanan.
Jika tidak ditentukan, nama file default akan dibuat.

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
Nama Vault.
Cmdlet menyusun FQDN dari vault berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: ByStorageAccountName
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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem

## OUTPUTS

### System.String

## CATATAN

## RELATED LINKS
