---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultmanagedstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultManagedStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultManagedStorageAccount.md
ms.openlocfilehash: dd0a27bc4b2e0cdbb265c00a20b839d7eac064e8
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144213719"
---
# Cadangan-AkunPenyimpananDikelolaAzKeyVault

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
Cmdlet **Backup-AzKeyVaultManagedStorageAccount** mencadangkan akun penyimpanan terkelola tertentu dalam brankas kunci dengan mengunduhnya dan menyimpannya dalam file.
Karena konten yang diunduh dienkripsi, konten tersebut tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan akun penyimpanan yang dicadangkan ke brankas kunci apa pun dalam langganan tempat penyimpanan dicadangkan, selama vault berada dalam geografi Azure yang sama.
Alasan umum untuk menggunakan cmdlet ini adalah: 
- Anda ingin menyimpan salinan offline akun penyimpanan jika Anda secara tidak sengaja menghapus yang asli dari vault.
 
- Anda membuat akun penyimpanan terkelola menggunakan Key Vault dan sekarang ingin mengkloning objek ke wilayah Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua instans aplikasi terdistribusi Anda.
Gunakan cmdlet **Backup-AzKeyVaultManagedStorageAccount** untuk mengambil akun penyimpanan terkelola dalam format terenkripsi lalu gunakan cmdlet **Restore-AzKeyVaultManagedStorageAccount** dan tentukan brankas kunci di wilayah kedua.

## EXAMPLES

### Contoh 1: Mencadangkan akun penyimpanan terkelola dengan nama file yang dibuat secara otomatis
```powershell
Backup-AzKeyVaultManagedStorageAccount -VaultName 'MyKeyVault' -Name 'MyMSAK'
```

```output
C:\Users\username\mykeyvault-mymsak-1527029447.01191
```

Perintah ini mengambil akun penyimpanan terkelola bernama MyMSAK dari brankas kunci bernama MyKeyVault dan menyimpan cadangan akun penyimpanan terkelola tersebut ke file yang secara otomatis dinamai untuk Anda, dan menampilkan nama file.

### Contoh 2: Mencadangkan akun penyimpanan terkelola ke nama file tertentu
```powershell
Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyMSAK' -OutputFile 'C:\Backup.blob'
```

```output
C:\Backup.blob
```

Perintah ini mengambil akun penyimpanan terkelola bernama MyMSAK dari brankas kunci bernama MyKeyVault dan menyimpan cadangan akun penyimpanan terkelola tersebut ke file bernama Backup.blob.

### Contoh 3: Cadangkan akun penyimpanan terkelola yang diambil sebelumnya ke nama file tertentu, menimpa file tujuan tanpa meminta.
```powershell
$msak = Get-AzKeyVaultManagedStorageAccount -VaultName 'MyKeyVault' -Name 'MyMSAK'
Backup-AzKeyVaultManagedStorageAccount -StorageAccount $msak -OutputFile 'C:\Backup.blob' -Force
```

```output
C:\Backup.blob
```

Perintah ini membuat cadangan akun penyimpanan terkelola bernama $msak. Nama dalam vault bernama $msak. VaultName ke file bernama Backup.blob, secara diam-diam menimpa file jika sudah ada.

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

### -InputObject
Storage bundel akun yang akan dicadangkan, disalurkan dari output panggilan pengambilan.

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

### -Name
Nama rahasia.
Cmdlet membangun FQDN rahasia dari nama vault, lingkungan dan nama rahasia yang saat ini dipilih.

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
Jika tidak ditentukan, nama file default akan dihasilkan.

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
Nama vault.
Cmdlet membangun FQDN vault berdasarkan nama dan lingkungan yang saat ini dipilih.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS
