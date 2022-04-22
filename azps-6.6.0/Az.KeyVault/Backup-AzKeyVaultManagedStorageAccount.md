---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultmanagedstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultManagedStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Backup-AzKeyVaultManagedStorageAccount.md
ms.openlocfilehash: ab6bb53e2648af60897252a087fa6a80329b944d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142902629"
---
# Backup-AzKeyVaultManagedStorageAccount

## SYNOPSIS
Mencadangkan akun penyimpanan yang dikelola KeyVault.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/backup-azkeyvaultmanagedstorageaccount) untuk informasi terbaru.

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
Cmdlet **Backup-AzKeyVaultManagedStorageAccount** mencadangkan akun penyimpanan terkelola tertentu dalam kubah kunci dengan mengunduh dan menyimpannya dalam file.
Karena konten yang diunduh dienkripsi, konten tidak dapat digunakan di luar Azure Key Vault.
Anda dapat memulihkan akun penyimpanan yang dicadangkan ke setiap kubah kunci dalam langganan tempat penyimpanan dicadangkan, selama kubah berada dalam geografi Azure yang sama.
Alasan umum untuk menggunakan cmdlet ini adalah: 
- Anda ingin menyimpan salinan offline akun penyimpanan jika Anda secara tidak sengaja menghapus yang asli dari kubah.
 
- Anda membuat akun penyimpanan terkelola menggunakan Key Vault dan sekarang ingin mengkloning objek ke kawasan Azure yang berbeda, sehingga Anda dapat menggunakannya dari semua contoh aplikasi yang didistribusikan.
Gunakan cmdlet **Backup-AzKeyVaultManagedStorageAccount** untuk mengambil akun penyimpanan terkelola dalam format terenkripsi lalu gunakan cmdlet **Restore-AzKeyVaultManagedStorageAccount** dan tentukan kubah kunci di kawasan kedua.

## EXAMPLES

### Contoh 1: Mencadangkan akun penyimpanan terkelola dengan nama file yang dihasilkan secara otomatis
```powershell
PS C:\Users\username\> Backup-AzKeyVaultManagedStorageAccount -VaultName 'MyKeyVault' -Name 'MyMSAK'

C:\Users\username\mykeyvault-mymsak-1527029447.01191
```

Perintah ini mengambil akun penyimpanan terkelola bernama MyMSAK dari kubah kunci bernama MyKeyVault dan menyimpan cadangan akun penyimpanan terkelola tersebut ke file yang secara otomatis dinamai untuk Anda, dan menampilkan nama file.

### Contoh 2: Mencadangkan akun penyimpanan terkelola ke nama file tertentu
```powershell
PS C:\> Backup-AzKeyVaultKey -VaultName 'MyKeyVault' -Name 'MyMSAK' -OutputFile 'C:\Backup.blob'

C:\Backup.blob
```

Perintah ini mengambil akun penyimpanan terkelola bernama MyMSAK dari kubah kunci bernama MyKeyVault dan menyimpan cadangan akun penyimpanan terkelola tersebut ke file bernama Backup.blob.

### Contoh 3: Cadangkan akun penyimpanan terkelola yang sebelumnya diambil ke nama file tertentu, menimpa file tujuan tanpa meminta.
```powershell
PS C:\> $msak = Get-AzKeyVaultManagedStorageAccount -VaultName 'MyKeyVault' -Name 'MyMSAK'
PS C:\> Backup-AzKeyVaultManagedStorageAccount -StorageAccount $msak -OutputFile 'C:\Backup.blob' -Force

C:\Backup.blob
```

Perintah ini membuat cadangan akun penyimpanan terkelola bernama $msak. Nama dalam kubah bernama $msak. VaultName ke file bernama Backup.blob, menimpa file secara diam-diam jika sudah ada.

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

### -Nama
Nama rahasia.
Cmdlet menyusun FQDN rahasia dari nama kubah, lingkungan yang saat ini dipilih dan nama rahasia.

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
Berkas output.
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
Nama kubah.
Cmdlet menyusun FQDN kubah berdasarkan nama dan lingkungan yang saat ini dipilih.

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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS
