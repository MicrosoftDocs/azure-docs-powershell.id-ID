---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/az.keyvault/add-azkeyvaultmanagedstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Add-AzKeyVaultManagedStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Add-AzKeyVaultManagedStorageAccount.md
ms.openlocfilehash: 63e3e6c1a68e604c8da5a72aefeff751e0fd22d2b38cd6866f9a847929524c16
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132413630"
---
# Add-AzKeyVaultManagedStorageAccount

## SYNOPSIS
Menambahkan Akun Azure Storage yang sudah ada ke key vault tertentu agar kunci-kuncinya dikelola oleh layanan Key Vault.

## SYNTAX

```
Add-AzKeyVaultManagedStorageAccount [-VaultName] <String> [-AccountName] <String>
 [-AccountResourceId] <String> [-ActiveKeyName] <String> [-DisableAutoRegenerateKey]
 [-RegenerationPeriod <TimeSpan>] [-Disable] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menyiapkan Akun Azure Storage yang sudah ada dengan Key Vault Storage kunci Akun agar dikelola oleh Key Vault. Akun Storage harus sudah ada. Tombol Storage tidak pernah diekspos ke penelepon.
Kunci Vault otomatis meregenerasi dan beralih kunci aktif berdasarkan periode regenerasi.

## EXAMPLES

### Contoh 1: Atur akun Azure Storage dengan Key Vault untuk mengelola kuncinya
```
PS C:\> $regenerationPeriod = [System.Timespan]::FromDays(90)
PS C:\> Add-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -ResourceId '/subscriptions/<subscription id>/resourceGroups/myresourcegroup/providers/Microsoft.Storage/storageAccounts/mystorageaccount' -ActiveKeyName 'key1' -RegenerationPeriod $regenerationPeriod
```

Mengatur akun Storage Anda dengan Key Vault agar kuncinya dikelola oleh Key Vault. Kumpulan kunci aktif adalah 'key1'. Kunci ini akan digunakan untuk menghasilkan token sas. Key Vault akan meregenerasi kunci 'key2' setelah periode regenerasi dari waktu perintah ini dan mengaturnya sebagai kunci aktif. Proses regenerasi otomatis ini akan berlanjut antara 'key1' dan 'key2' dengan jeda 90 hari.

### Contoh 2: Mengatur Akun Azure Storage Klasik dengan Key Vault untuk mengelola tombolnya
```
PS C:\> $regenerationPeriod = [System.Timespan]::FromDays(90)
PS C:\> Add-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -ResourceId '/subscriptions/<subscription id>/resourceGroups/myresourcegroup/providers/Microsoft.ClassicStorage/storageAccounts/mystorageaccount' -ActiveKeyName 'Primary' -RegenerationPeriod $regenerationPeriod
```

Mengatur Akun Storage Klasik dengan Key Vault agar kuncinya dikelola oleh Key Vault. Kumpulan kunci aktif adalah 'Utama'. Kunci ini akan digunakan untuk menghasilkan token sas. Kunci Vault akan meregenerasi kunci 'Sekunder' setelah periode regenerasi dari waktu perintah ini dan mengaturnya sebagai kunci aktif. Proses regenerasi otomatis ini akan berlanjut antara 'Primer' dan 'Sekunder' dengan kesenjangan 90 hari.

## PARAMETERS

### -Nama Akun
Nama akun penyimpanan terkelola Key Vault. Cmdlet membangun FQDN dari nama akun penyimpanan terkelola dari nama vault, lingkungan yang saat ini dipilih dan nama akun penyimpanan tertentu.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountName, Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AccountResourceId
Id sumber daya Azure dari akun penyimpanan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountResourceId

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ActiveKeyName
Nama kunci akun penyimpanan yang harus digunakan untuk menghasilkan token sas.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Disable
Menonaktifkan penggunaan kunci akun penyimpanan terkelola untuk generasi token sas.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutoRegateKey
Kunci regenerasi otomatis. Jika true, maka kunci tidak aktif akun penyimpanan terkelola akan digenerasi otomatis dan menjadi kunci aktif baru setelah periode regenerasi. Jika false, maka kunci akun penyimpanan yang dikelola tidak digenerasi secara otomatis.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegenerationPeriod
Periode regenerasi. Jika kunci regenerasi otomatis diaktifkan, nilai ini menentukan rentang waktu di mana tombol tidak aktif pada akun penyimpanan terkelola mendapatkan regenerasi otomatis dan menjadi kunci aktif baru.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya:

@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Nama Vault.
Cmdlet menyusun FQDN dari vault berdasarkan nama dan lingkungan yang saat ini dipilih.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.ManagedStorageAccount

## CATATAN

## RELATED LINKS

[Az.KeyVault](/powershell/module/Az.keyvault)
