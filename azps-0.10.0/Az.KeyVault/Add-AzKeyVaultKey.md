---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/az.keyvault/add-azKeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
ms.openlocfilehash: b01ed80385726660198d3f6fbb20ab1e5ec57dfe
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142847297"
---
# Add-AzKeyVaultKey

## SYNOPSIS
Membuat kunci dalam kubah kunci atau mengimpor kunci ke dalam kubah kunci.

## SYNTAX

### Buat (Default)
```
Add-AzKeyVaultKey [-VaultName] <String> [-Name] <String> -Destination <String> [-Disable]
 [-KeyOps <String[]>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Impor
```
Add-AzKeyVaultKey [-VaultName] <String> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Destination <String>] [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzKeyVaultKey** membuat kunci dalam kubah kunci di Azure Key Vault, atau mengimpor kunci ke dalam kubah kunci.
Gunakan cmdlet ini untuk menambahkan kunci menggunakan salah satu metode berikut:

- Buat kunci dalam modul keamanan perangkat keras (HSM) di layanan Key Vault.
- Buat kunci dalam perangkat lunak di layanan Key Vault.
- Impor kunci dari modul keamanan perangkat keras (HSM) Anda sendiri ke HSM dalam layanan Key Vault.
- Impor kunci dari file .pfx di komputer Anda.
- Impor kunci dari file .pfx di komputer Anda ke modul keamanan perangkat keras (HSM) di layanan Key Vault.

Untuk salah satu operasi ini, Anda dapat menyediakan atribut utama atau menerima pengaturan default.

Jika Anda membuat atau mengimpor kunci yang memiliki nama yang sama dengan kunci yang sudah ada di kubah kunci, kunci asli diperbarui dengan nilai yang Anda tentukan untuk kunci baru. Anda dapat mengakses nilai sebelumnya menggunakan URI khusus versi untuk versi kunci tersebut. Untuk mempelajari tentang versi utama dan struktur URI, lihat [Tentang Keys andSecrets](http://go.microsoft.com/fwlink/?linkid=518560) dalam dokumentasi KEY VAULT REST API.

Catatan: Untuk mengimpor kunci dari modul keamanan perangkat keras Anda sendiri, Anda harus terlebih dahulu membuat paket BYOK (file dengan ekstensi nama file .byok) menggunakan toolset Azure Key Vault BYOK. Untuk informasi selengkapnya, lihat [Cara Menghasilkan dan Mentransfer Kunci HSM-Protected untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).

Sebagai praktik terbaik, cadangkan kunci Anda setelah dibuat atau diperbarui, dengan menggunakan cmdlet Backup-AzKeyVaultKey. Tidak ada fungsionalitas yang belum dihapus, jadi jika Anda secara tidak sengaja menghapus kunci atau menghapusnya lalu berubah pikiran, kunci tidak dapat dipulihkan kecuali Anda memiliki cadangannya yang dapat Anda pulihkan.

## EXAMPLES

### Contoh 1: Membuat kunci
```
PS C:\>Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware' -Destination 'Software'
```

Perintah ini membuat kunci yang dilindungi perangkat lunak bernama ITSoftware dalam kubah kunci bernama Contoso.

### Contoh 2: Membuat kunci yang dilindungi HSM
```
PS C:\>Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITHsm' -Destination 'HSM'
```

Perintah ini membuat kunci yang dilindungi HSM di kubah kunci bernama Contoso.

### Contoh 3: Membuat kunci dengan nilai non-default
```
PS C:\>$KeyOperations = 'decrypt', 'verify'
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $NotBefore = (Get-Date).ToUniversalTime()
PS C:\> $Tags = @{'Severity' = 'high'; 'Accounting' = null}
PS C:\> Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITHsmNonDefault' -Destination 'HSM' -Expires $Expires -NotBefore $NotBefore -KeyOps $KeyOperations -Disable -Tag $Tags
```

Perintah pertama menyimpan nilai yang didekripsi dan diverifikasi dalam variabel $KeyOperations.

Perintah kedua membuat objek **DateTime** , yang ditentukan dalam UTC, menggunakan cmdlet **Get-Date** .
Objek tersebut menentukan waktu dua tahun di masa mendatang. Perintah menyimpan tanggal tersebut dalam variabel $Expires. Untuk informasi selengkapnya, ketik .`Get-Help Get-Date`

Perintah ketiga membuat objek **DateTime** menggunakan cmdlet **Get-Date** . Objek tersebut menentukan waktu UTC saat ini. Perintah menyimpan tanggal tersebut dalam variabel $NotBefore.

Perintah akhir membuat kunci bernama ITHsmNonDefault yang merupakan kunci yang dilindungi HSM. Perintah menentukan nilai untuk operasi kunci yang diperbolehkan yang disimpan $KeyOperations. Perintah menentukan waktu untuk parameter *Kedaluwarsa* dan *NotBefore* yang dibuat dalam perintah sebelumnya, dan tag untuk tingkat keparahan tinggi dan TI. Kunci baru dinonaktifkan. Anda dapat mengaktifkannya menggunakan cmdlet **Set-AzKeyVaultKey** .

### Contoh 4: Mengimpor kunci yang dilindungi HSM
```
PS C:\>Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITByok' -KeyFilePath 'C:\Contoso\ITByok.byok' -Destination 'HSM'
```

Perintah ini mengimpor kunci bernama ITByok dari lokasi yang ditentukan parameter *KeyFilePath* . Kunci yang diimpor adalah kunci yang dilindungi HSM.

Untuk mengimpor kunci dari modul keamanan perangkat keras Anda sendiri, Anda harus terlebih dahulu membuat paket BYOK (file dengan ekstensi nama file .byok) menggunakan toolset Azure Key Vault BYOK.
Untuk informasi selengkapnya, lihat [Cara Menghasilkan dan Mentransfer Kunci HSM-Protected untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).

### Contoh 5: Mengimpor kunci yang dilindungi perangkat lunak
```
PS C:\>$Password = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITPfx' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password
```

Perintah pertama mengonversi string menjadi string aman menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Password. Untuk informasi selengkapnya, ketik .`Get-Help
ConvertTo-SecureString`

Perintah kedua membuat kata sandi perangkat lunak di kubah kunci Contoso. Perintah menentukan lokasi untuk kunci dan kata sandi yang disimpan di $Password.

### Contoh 6: Mengimpor kunci dan menetapkan atribut
```
PS C:\>$Password = ConvertTo-SecureString -String 'password' -AsPlainText -Force
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'high'; 'Accounting' = null }
PS C:\> Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITPfxToHSM' -Destination 'HSM' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password -Expires $Expires -Tag $Tags
```

Perintah pertama mengonversi string menjadi string aman menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Password.

Perintah kedua membuat objek **DateTime** menggunakan cmdlet **Get-Date** , lalu menyimpan objek tersebut dalam variabel $Expires.

Perintah ketiga membuat variabel $tags untuk mengatur tag untuk tingkat keparahan tinggi dan TI.

Perintah akhir mengimpor kunci sebagai kunci HSM dari lokasi yang ditentukan. Perintah menentukan waktu kedaluwarsa yang disimpan dalam $Expires dan kata sandi yang disimpan di $Password, dan menerapkan tag yang disimpan di $tags.

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

### -Tujuan
Menentukan apakah akan menambahkan kunci sebagai kunci yang dilindungi perangkat lunak atau kunci yang dilindungi HSM dalam layanan Key Vault.
Nilai yang valid adalah: HSM dan Perangkat Lunak.

Catatan: Untuk menggunakan HSM sebagai tujuan, Anda harus memiliki kubah kunci yang mendukung HSM. Untuk informasi selengkapnya tentang tingkat layanan dan kapabilitas untuk Azure Key Vault, lihat [situs web Harga Azure Key Vault](http://go.microsoft.com/fwlink/?linkid=512521).

Parameter ini diperlukan saat Anda membuat kunci baru. Jika Anda mengimpor kunci menggunakan parameter *KeyFilePath* , parameter ini opsional:

- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .byok, cmdlet ini akan mengimpor kunci tersebut sebagai kunci yang dilindungi HSM. Cmdlet tidak bisa mengimpor kunci tersebut sebagai kunci yang dilindungi perangkat lunak.

- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .pfx, cmdlet ini mengimpor kunci sebagai kunci yang dilindungi perangkat lunak.

```yaml
Type: String
Parameter Sets: Create
Aliases: 
Accepted values: HSM, Software

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Import
Aliases: 
Accepted values: HSM, Software

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Non-fungsikan
Menunjukkan bahwa kunci yang Anda tambahkan diatur ke status awal nonaktif. Setiap upaya untuk menggunakan kunci akan gagal. Gunakan parameter ini jika Anda melakukan pramuat kunci yang ingin anda aktifkan nanti.

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

### -Kedaluwarsa
Menentukan waktu kedaluwarsa, sebagai objek **DateTime** , untuk kunci yang ditambahkan cmdlet ini. Parameter ini menggunakan Waktu Universal Terkoordinasi (UTC). Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** . Untuk informasi selengkapnya, ketik .`Get-Help Get-Date` Jika Anda tidak menentukan parameter ini, kunci tidak akan kedaluwarsa.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyFilePassword
Menentukan kata sandi untuk file yang diimpor sebagai objek **SecureString** . Untuk mendapatkan objek **SecureString** , gunakan cmdlet **ConvertTo-SecureString** . Untuk informasi selengkapnya, ketik .`Get-Help ConvertTo-SecureString` Anda harus menentukan kata sandi ini untuk mengimpor file dengan ekstensi nama file .pfx.

```yaml
Type: SecureString
Parameter Sets: Import
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath
Menentukan jalur file lokal yang berisi materi kunci yang diimpor cmdlet ini.
Ekstensi nama file yang valid adalah .byok dan .pfx.

- Jika file adalah file .byok, kunci secara otomatis diproteksi oleh HSM setelah impor dan Anda tidak dapat menimpa default ini.

- Jika file adalah file .pfx, kunci secara otomatis dilindungi oleh perangkat lunak setelah pengimporan. Untuk menimpa default ini, atur parameter *Tujuan* ke HSM sehingga kunci dilindungi HSM.

Saat Anda menentukan parameter ini, parameter *Tujuan* bersifat opsional.

```yaml
Type: String
Parameter Sets: Import
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyOps
Menentukan array operasi yang dapat dilakukan dengan menggunakan kunci yang ditambahkan cmdlet ini.
Jika Anda tidak menentukan parameter ini, semua operasi dapat dilakukan.

Nilai yang dapat diterima untuk parameter ini adalah daftar operasi kunci yang dipisahkan koma seperti yang ditentukan oleh [spesifikasi JSON Web Key (JWK):](http://go.microsoft.com/fwlink/?LinkID=613300)

- Mengenkripsi
- Mendekripsi
- Bungkus
- Membuka
- Tanda
- Memverifikasi

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama kunci untuk ditambahkan ke kubah kunci. Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN) kunci berdasarkan nama yang ditentukan parameter ini, nama kubah kunci, dan lingkungan Anda saat ini. Nama harus berupa string yang panjangnya 1 sampai 63 karakter yang hanya berisi 0-9, a-z, A-Z, dan - (simbol garis putus-putus).

```yaml
Type: String
Parameter Sets: (All)
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TidakBefore
Menentukan waktu, sebagai objek **DateTime** , sebelum kunci tidak dapat digunakan. Parameter ini menggunakan UTC. Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** . Jika Anda tidak menentukan parameter ini, kunci dapat segera digunakan.

```yaml
Type: DateTime
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
Menentukan nama kubah kunci tempat cmdlet ini menambahkan kunci. Cmdlet ini menyusun FQDN kubah kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.KeyBundle

## NOTES

## RELATED LINKS

[Backup-AzKeyVaultKey](./Backup-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Hapus-AzKeyVaultKey](./Remove-AzKeyVaultKey.md)

[Set-AzKeyVaultKeyAttribute](./Set-AzKeyVaultKeyAttribute.md)
