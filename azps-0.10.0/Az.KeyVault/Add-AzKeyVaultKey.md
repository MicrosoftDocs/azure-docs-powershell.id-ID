---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/az.keyvault/add-azKeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
ms.openlocfilehash: b01ed80385726660198d3f6fbb20ab1e5ec57dfe
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420226"
---
# Add-AzKeyVaultKey

## SYNOPSIS
Membuat kunci di kunci vault atau mengimpor kunci ke kunci vault.

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
Cmdlet **Add-AzKeyVaultKey** membuat kunci di kunci vault di Azure Key Vault, atau mengimpor kunci ke kunci vault.
Gunakan cmdlet ini untuk menambahkan tombol menggunakan salah satu metode berikut:

- Buat kunci di modul keamanan perangkat keras (HSM) di layanan Key Vault.
- Buat kunci di perangkat lunak dalam layanan Key Vault.
- Mengimpor kunci dari modul keamanan perangkat keras (HSM) Anda sendiri ke HSM di layanan Key Vault.
- Mengimpor kunci dari file .pfx di komputer Anda.
- Mengimpor kunci dari file .pfx di komputer Anda ke modul keamanan perangkat keras (HSMS) di layanan Key Vault.

Untuk setiap operasi ini, Anda dapat menyediakan atribut kunci atau menerima pengaturan default.

Jika Anda membuat atau mengimpor kunci yang memiliki nama yang sama dengan kunci yang sudah ada di kunci vault, kunci asli diperbarui dengan nilai yang Anda tentukan untuk kunci baru. Anda bisa mengakses nilai sebelumnya dengan menggunakan URI khusus versi untuk versi kunci tersebut. Untuk mempelajari tentang versi utama dan struktur URI, lihat [Tentang Keys danSecrets](http://go.microsoft.com/fwlink/?linkid=518560) dalam dokumentasi API REST Key Vault.

Catatan: Untuk mengimpor kunci dari modul keamanan perangkat keras milik sendiri, Anda harus membuat paket BYOK terlebih dahulu (file dengan ekstensi nama file .byok) menggunakan perangkat keras Azure Key Vault BYOK. Untuk informasi selengkapnya, [lihat Cara Membuat dan Mentransfer HSM-Protected Kunci untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).

Sebagai praktik terbaik, cadangankan kunci Anda setelah dibuat atau diperbarui, dengan menggunakan cmdlet Backup-AzKeyVaultKey. Tidak ada fungsionalitas yang dibatalkan, jadi jika Anda secara tidak sengaja menghapus kunci atau menghapusnya lalu berubah pikiran, kunci tersebut tidak dapat dipulihkan kecuali Anda memiliki cadangannya yang bisa dipulihkan.

## EXAMPLES

### Contoh 1: Buat kunci
```
PS C:\>Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITSoftware' -Destination 'Software'
```

Perintah ini akan membuat kunci yang dilindungi perangkat lunak bernama ITSoftware dalam kunci vault bernama Contoso.

### Contoh 2: Membuat kunci yang dilindungi HSM
```
PS C:\>Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITHsm' -Destination 'HSM'
```

Perintah ini akan membuat kunci yang dilindungi HSM dalam kunci vault bernama Contoso.

### Contoh 3: Membuat kunci dengan nilai non-default
```
PS C:\>$KeyOperations = 'decrypt', 'verify'
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $NotBefore = (Get-Date).ToUniversalTime()
PS C:\> $Tags = @{'Severity' = 'high'; 'Accounting' = null}
PS C:\> Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITHsmNonDefault' -Destination 'HSM' -Expires $Expires -NotBefore $NotBefore -KeyOps $KeyOperations -Disable -Tag $Tags
```

Perintah pertama menyimpan nilai yang didekripsi dan diverifikasi dalam $KeyOperations nilai.

Perintah kedua membuat objek **DateTime,** yang ditentukan dalam UTC, dengan menggunakan cmdlet **Get-Date.**
Objek tersebut menentukan waktu dua tahun di masa mendatang. Perintah menyimpan tanggal itu dalam variabel $Expires baru. Untuk informasi selengkapnya, ketik `Get-Help Get-Date` .

Perintah ketiga membuat objek **DateTime** menggunakan cmdlet **Get-Date.** Objek tersebut menentukan waktu UTC saat ini. Perintah menyimpan tanggal itu dalam $NotBefore variabel.

Perintah terakhir membuat kunci bernama ITHsmNonDefault yang merupakan kunci yang dilindungi HSM. Perintah menentukan nilai untuk operasi tombol diperbolehkan yang disimpan $KeyOperations. Perintah menentukan waktu untuk  parameter Kedaluwarsa dan *NotBefore* yang dibuat di perintah sebelumnya, dan tag untuk tingkat keparahan tinggi dan IT. Kunci baru dinonaktifkan. Anda dapat mengaktifkannya menggunakan cmdlet **Set-AzKeyVaultKey.**

### Contoh 4: Mengimpor kunci yang diproteksi HSM
```
PS C:\>Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITByok' -KeyFilePath 'C:\Contoso\ITByok.byok' -Destination 'HSM'
```

Perintah ini mengimpor kunci bernama ITByok dari lokasi yang ditentukan oleh parameter *KeyFilePath.* Kunci yang diimpor adalah kunci yang diproteksi HSM.

Untuk mengimpor kunci dari modul keamanan perangkat keras milik sendiri, Anda harus terlebih dahulu membuat paket BYOK (file dengan ekstensi nama file .byok) menggunakan peralatan BYOK Azure Key Vault.
Untuk informasi selengkapnya, [lihat Cara Membuat dan Mentransfer HSM-Protected Kunci untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).

### Contoh 5: Mengimpor kunci yang dilindungi perangkat lunak
```
PS C:\>$Password = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITPfx' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password
```

Perintah pertama mengonversi string menjadi string yang aman dengan menggunakan cmdlet **ConvertTo-SecureString,** lalu menyimpan string itu di $Password variabel. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString` .

Perintah kedua membuat kata sandi perangkat lunak dalam kunci vault Contoso. Perintah menentukan lokasi untuk kunci dan kata sandi yang disimpan di $Password.

### Contoh 6: Mengimpor kunci dan menetapkan atribut
```
PS C:\>$Password = ConvertTo-SecureString -String 'password' -AsPlainText -Force
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'high'; 'Accounting' = null }
PS C:\> Add-AzKeyVaultKey -VaultName 'Contoso' -Name 'ITPfxToHSM' -Destination 'HSM' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password -Expires $Expires -Tag $Tags
```

Perintah pertama mengonversi string menjadi string yang aman dengan menggunakan cmdlet **ConvertTo-SecureString,** lalu menyimpan string itu di $Password variabel.

Perintah kedua membuat objek **DateTime** menggunakan cmdlet **Get-Date,** lalu menyimpan objek tersebut dalam $Expires variabel.

Perintah ketiga membuat $tags variabel untuk mengatur tag tingkat keparahan tinggi dan TI.

Perintah terakhir mengimpor kunci sebagai tombol HSM dari lokasi tertentu. Perintah menentukan waktu kedaluwarsa yang disimpan di $Expires kata sandi dan disimpan di $Password, dan menerapkan tag yang disimpan di $tags.

## PARAMETERS

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

### -Tujuan
Menentukan apakah akan menambahkan kunci sebagai kunci yang diproteksi perangkat lunak atau kunci yang diproteksi HSM di layanan Key Vault.
Nilai valid adalah: HSM dan Perangkat Lunak.

Catatan: Untuk menggunakan HSM sebagai tujuan, Anda harus memiliki kunci vault yang mendukung HSM. Untuk informasi selengkapnya tentang tingkat layanan dan kemampuan Key Vault Azure, lihat situs web [Harga Azure Key Vault](http://go.microsoft.com/fwlink/?linkid=512521).

Parameter ini diperlukan ketika Anda membuat kunci baru. Jika Anda mengimpor kunci menggunakan parameter *KeyFilePath,* parameter ini bersifat opsional:

- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .byok, cmdlet tersebut akan mengimpor kunci tersebut sebagai tombol yang diproteksi HSM. Cmdlet tidak dapat mengimpor kunci tersebut sebagai kunci yang dilindungi perangkat lunak.

- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .pfx, cmdlet akan mengimpor kunci tersebut sebagai kunci yang diproteksi perangkat lunak.

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

### -Disable
Menunjukkan bahwa kunci yang Anda tambahkan diatur ke status awal nonaktif. Setiap percobaan untuk menggunakan kunci akan gagal. Gunakan parameter ini jika Tombol pra-muat yang ingin diaktifkan nanti.

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
Menentukan waktu kedaluwarsa, sebagai objek **DateTime,** untuk kunci yang tambahkan cmdlet ini. Parameter ini menggunakan Waktu Universal Terkoordinasi (UTC). Untuk mendapatkan **objek DateTime,** gunakan cmdlet **Get-Date.** Untuk informasi selengkapnya, ketik `Get-Help Get-Date` . Jika Anda tidak menentukan parameter ini, kunci tidak kedaluwarsa.

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
Menentukan kata sandi untuk file yang diimpor sebagai objek **SecureString.** Untuk mendapatkan objek **SecureString,** gunakan cmdlet **ConvertTo-SecureString.** Untuk informasi selengkapnya, ketik `Get-Help ConvertTo-SecureString` . Anda harus menentukan kata sandi ini untuk mengimpor file dengan ekstensi nama file .pfx.

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
Menentukan jalur file lokal yang berisi materi utama yang diimpor cmdlet ini.
Ekstensi nama file yang valid adalah .byok dan .pfx.

- Jika file tersebut adalah file .byok, kunci secara otomatis diproteksi oleh HSMS setelah impor dan Anda tidak bisa mengesampingkan default ini.

- Jika file adalah file .pfx, kunci secara otomatis dilindungi oleh perangkat lunak setelah impor. Untuk menimpa default ini, atur parameter *Tujuan* ke HSM sehingga kunci terproteksi HSM.

Ketika Anda menentukan parameter ini, *parameter Destination* bersifat opsional.

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
Menentukan larik operasi yang dapat dijalankan menggunakan kunci yang penambahan cmdlet ini.
Jika Anda tidak menentukan parameter ini, semua operasi dapat dijalankan.

Nilai yang dapat diterima untuk parameter ini adalah daftar operasi kunci yang dipisahkan koma seperti yang ditetapkan oleh [spesifikasi JSON Web Key (JWK):](http://go.microsoft.com/fwlink/?LinkID=613300)

- Encrypt
- Dekripsi
- Bungkus
- Membatalkan rap
- Tanda tangani
- Verifikasi

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
Menentukan nama kunci untuk ditambahkan ke kunci vault. Cmdlet ini menyusun nama domain (FQDN) yang sepenuhnya memenuhi syarat dari kunci berdasarkan nama yang ditentukan parameter ini, nama kunci vault, dan lingkungan Anda saat ini. Nama harus memiliki panjang string dari 1 sampai 63 karakter yang hanya berisi 0-9, a-z, A-Z, dan - (simbol garis putus-putus).

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

### -NotBefore
Menentukan waktu, sebagai objek **DateTime,** sebelum tombol tidak dapat digunakan. Parameter ini menggunakan UTC. Untuk mendapatkan **objek DateTime,** gunakan cmdlet **Get-Date.** Jika Anda tidak menentukan parameter ini, kunci dapat langsung digunakan.

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
Menentukan nama key vault tempat cmdlet menambahkan kunci tersebut. Cmdlet ini menyusun FQDN dari kunci vault berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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

### Microsoft.Azure.Commands.KeyVault.Models.KeyBundle

## CATATAN

## RELATED LINKS

[Backup-AzKeyVaultKey](./Backup-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Remove-AzKeyVaultKey](./Remove-AzKeyVaultKey.md)

[Set-AzKeyVaultKeyAttribute](./Set-AzKeyVaultKeyAttribute.md)
