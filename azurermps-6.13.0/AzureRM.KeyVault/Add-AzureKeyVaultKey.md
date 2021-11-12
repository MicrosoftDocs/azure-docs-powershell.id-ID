---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 846F781C-73A3-4BBE-ABD9-897371109FBE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/add-azurekeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Add-AzureKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/KeyVault/Commands.KeyVault/help/Add-AzureKeyVaultKey.md
ms.openlocfilehash: 447360e8ec3f9d7f2988f1cd830fb5c544f317ce
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426319"
---
# Add-AzureKeyVaultKey

## SYNOPSIS
Membuat kunci di kunci vault atau mengimpor kunci ke kunci vault.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### InteractiveCreate (Default)
```
Add-AzureKeyVaultKey [-VaultName] <String> [-Name] <String> -Destination <String> [-Disable]
 [-KeyOps <String[]>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InteractiveImport
```
Add-AzureKeyVaultKey [-VaultName] <String> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Destination <String>] [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectCreate
```
Add-AzureKeyVaultKey [-InputObject] <PSKeyVault> [-Name] <String> -Destination <String> [-Disable]
 [-KeyOps <String[]>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectImport
```
Add-AzureKeyVaultKey [-InputObject] <PSKeyVault> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Destination <String>] [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdCreate
```
Add-AzureKeyVaultKey [-ResourceId] <String> [-Name] <String> -Destination <String> [-Disable]
 [-KeyOps <String[]>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdImport
```
Add-AzureKeyVaultKey [-ResourceId] <String> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Destination <String>] [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureKeyVaultKey** membuat kunci di penyimpanan kunci di Azure Key Vault, atau mengimpor kunci ke vault kunci.
Gunakan cmdlet ini untuk menambahkan tombol menggunakan salah satu metode berikut:
- Buat kunci di modul keamanan perangkat keras (HSM) di layanan Key Vault.
- Buat kunci di perangkat lunak dalam layanan Key Vault.
- Mengimpor kunci dari modul keamanan perangkat keras (HSM) Anda sendiri ke HSM di layanan Key Vault.
- Mengimpor kunci dari file .pfx di komputer Anda.
- Mengimpor kunci dari file .pfx di komputer Anda ke modul keamanan perangkat keras (HSMS) di layanan Key Vault.
Untuk setiap operasi ini, Anda dapat menyediakan atribut kunci atau menerima pengaturan default.
Jika Anda membuat atau mengimpor kunci yang memiliki nama yang sama dengan kunci yang sudah ada di kunci vault, kunci asli diperbarui dengan nilai yang Anda tentukan untuk kunci baru. Anda bisa mengakses nilai sebelumnya dengan menggunakan URI khusus versi untuk versi kunci tersebut. Untuk mempelajari tentang versi kunci dan struktur URI, lihat [Tentang Kunci dan Rahasia](https://go.microsoft.com/fwlink/?linkid=518560) dalam dokumentasi API REST Vault Kunci.
Catatan: Untuk mengimpor kunci dari modul keamanan perangkat keras milik sendiri, Anda harus membuat paket BYOK terlebih dahulu (file dengan ekstensi nama file .byok) menggunakan perangkat keras Azure Key Vault BYOK. Untuk informasi selengkapnya, [lihat Cara Membuat dan Mentransfer HSM-Protected Kunci untuk Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=522252).
Sebagai praktik terbaik, cadangankan kunci Anda setelah dibuat atau diperbarui, dengan menggunakan cmdlet Backup-AzureKeyVaultKey. Tidak ada fungsionalitas yang dibatalkan, jadi jika Anda secara tidak sengaja menghapus kunci atau menghapusnya lalu berubah pikiran, kunci tersebut tidak dapat dipulihkan kecuali Anda memiliki cadangannya yang bisa dipulihkan.

## EXAMPLES

### Contoh 1: Buat kunci
```powershell
PS C:\> Add-AzureKeyVaultKey -VaultName 'contoso' -Name 'ITSoftware' -Destination 'Software'

Vault Name     : contoso
Name           : ITSoftware
Version        : 67da57e9cadf48a2ad8d366b115843ab
Id             : https://contoso.vault.azure.net:443/keys/ITSoftware/67da57e9cadf48a2ad8d366b115843ab
Enabled        : True
Expires        :
Not Before     :
Created        : 5/21/2018 11:10:58 PM
Updated        : 5/21/2018 11:10:58 PM
Purge Disabled : False
Tags           :
```

Perintah ini akan membuat kunci yang dilindungi perangkat lunak bernama ITSoftware dalam kunci vault bernama Contoso.

### Contoh 2: Membuat kunci yang dilindungi HSM
```powershell
PS C:\> Add-AzureKeyVaultKey -VaultName 'contoso' -Name 'ITHsm' -Destination 'HSM'

Vault Name     : contoso
Name           : ITHsm
Version        : 67da57e9cadf48a2ad8d366b115843ab
Id             : https://contoso.vault.azure.net:443/keys/ITSoftware/67da57e9cadf48a2ad8d366b115843ab
Enabled        : True
Expires        :
Not Before     :
Created        : 5/21/2018 11:10:58 PM
Updated        : 5/21/2018 11:10:58 PM
Purge Disabled : False
Tags           :
```

Perintah ini akan membuat kunci yang dilindungi HSM dalam kunci vault bernama Contoso.

### Contoh 3: Membuat kunci dengan nilai non-default
```powershell
PS C:\> $KeyOperations = 'decrypt', 'verify'
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $NotBefore = (Get-Date).ToUniversalTime()
PS C:\> $Tags = @{'Severity' = 'high'; 'Accounting' = "true"}
PS C:\> Add-AzureKeyVaultKey -VaultName 'contoso' -Name 'ITHsmNonDefault' -Destination 'HSM' -Expires $Expires -NotBefore $NotBefore -KeyOps $KeyOperations -Disable -Tag $Tags

Vault Name     : contoso
Name           : ITHsmNonDefault
Version        : 929bfc14db84439b823ffd1bedadaf5f
Id             : https://contoso.vault.azure.net:443/keys/ITHsmNonDefault/929bfc14db84439b823ffd1bedadaf5f
Enabled        : False
Expires        : 5/21/2020 11:12:43 PM
Not Before     : 5/21/2018 11:12:50 PM
Created        : 5/21/2018 11:13:17 PM
Updated        : 5/21/2018 11:13:17 PM
Purge Disabled : False
Tags           : Name        Value
                 Severity    high
                 Accounting  true
```

Perintah pertama menyimpan nilai yang didekripsi dan diverifikasi dalam $KeyOperations nilai.
Perintah kedua membuat objek **DateTime,** yang ditentukan dalam UTC, dengan menggunakan cmdlet **Get-Date.**
Objek tersebut menentukan waktu dua tahun di masa mendatang. Perintah menyimpan tanggal itu dalam variabel $Expires baru. Untuk informasi selengkapnya, ketik `Get-Help Get-Date` .
Perintah ketiga membuat objek **DateTime** menggunakan cmdlet **Get-Date.** Objek tersebut menentukan waktu UTC saat ini. Perintah menyimpan tanggal itu dalam variabel $NotBefore baru.
Perintah terakhir membuat kunci bernama ITHsmNonDefault yang merupakan kunci yang dilindungi HSM. Perintah menentukan nilai untuk operasi tombol diperbolehkan yang disimpan $KeyOperations. Perintah menentukan waktu untuk  parameter Kedaluwarsa dan *NotBefore* yang dibuat di perintah sebelumnya, dan tag untuk tingkat keparahan tinggi dan IT. Kunci baru dinonaktifkan. Anda dapat mengaktifkannya menggunakan cmdlet **Set-AzureKeyVaultKey.**

### Contoh 4: Mengimpor kunci yang diproteksi HSM
```powershell
PS C:\> Add-AzureKeyVaultKey -VaultName 'contoso' -Name 'ITByok' -KeyFilePath 'C:\Contoso\ITByok.byok' -Destination 'HSM'

Vault Name     : contoso
Name           : ITByok
Version        : 67da57e9cadf48a2ad8d366b115843ab
Id             : https://contoso.vault.azure.net:443/keys/ITByok/67da57e9cadf48a2ad8d366b115843ab
Enabled        : True
Expires        :
Not Before     :
Created        : 5/21/2018 11:10:58 PM
Updated        : 5/21/2018 11:10:58 PM
Purge Disabled : False
Tags           :
```

Perintah ini mengimpor kunci bernama ITByok dari lokasi yang ditentukan oleh parameter *KeyFilePath.* Kunci yang diimpor adalah kunci yang diproteksi HSM.
Untuk mengimpor kunci dari modul keamanan perangkat keras milik sendiri, Anda harus terlebih dahulu membuat paket BYOK (file dengan ekstensi nama file .byok) menggunakan peralatan BYOK Azure Key Vault.
Untuk informasi selengkapnya, [lihat Cara Membuat dan Mentransfer HSM-Protected Kunci untuk Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=522252).

### Contoh 5: Mengimpor kunci yang dilindungi perangkat lunak
```powershell
PS C:\> $Password = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> Add-AzureKeyVaultKey -VaultName 'contoso' -Name 'ITPfx' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password

Vault Name     : contoso
Name           : ITPfx
Version        : 67da57e9cadf48a2ad8d366b115843ab
Id             : https://contoso.vault.azure.net:443/keys/ITPfx/67da57e9cadf48a2ad8d366b115843ab
Enabled        : True
Expires        :
Not Before     :
Created        : 5/21/2018 11:10:58 PM
Updated        : 5/21/2018 11:10:58 PM
Purge Disabled : False
Tags           :
```

Perintah pertama mengonversi string menjadi string aman dengan menggunakan cmdlet **ConvertTo-SecureString,** lalu menyimpan string itu di $Password variabel. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString` .
Perintah kedua membuat kata sandi perangkat lunak dalam kunci vault Contoso. Perintah menentukan lokasi untuk kunci dan kata sandi yang disimpan di $Password.

### Contoh 6: Mengimpor kunci dan menetapkan atribut
```powershell
PS C:\> $Password = ConvertTo-SecureString -String 'password' -AsPlainText -Force
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'high'; 'Accounting' = "true" }
PS C:\> Add-AzureKeyVaultKey -VaultName 'contoso' -Name 'ITPfxToHSM' -Destination 'HSM' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password -Expires $Expires -Tag $Tags

Vault Name     : contoso
Name           : ITPfxToHSM
Version        : 929bfc14db84439b823ffd1bedadaf5f
Id             : https://contoso.vault.azure.net:443/keys/ITPfxToHSM/929bfc14db84439b823ffd1bedadaf5f
Enabled        : True
Expires        : 5/21/2020 11:12:43 PM
Not Before     : 
Created        : 5/21/2018 11:13:17 PM
Updated        : 5/21/2018 11:13:17 PM
Purge Disabled : False
Tags           : Name        Value
                 Severity    high
                 Accounting  true
```

Perintah pertama mengonversi string menjadi string aman dengan menggunakan cmdlet **ConvertTo-SecureString,** lalu menyimpan string itu di $Password variabel.
Perintah kedua membuat objek **DateTime** menggunakan cmdlet **Get-Date,** lalu menyimpan objek tersebut dalam $Expires variabel.
Perintah ketiga membuat $tags variabel untuk mengatur tag tingkat keparahan tinggi dan TI.
Perintah terakhir mengimpor kunci sebagai tombol HSM dari lokasi tertentu. Perintah menentukan waktu kedaluwarsa yang disimpan di $Expires kata sandi dan disimpan di $Password, dan menerapkan tag yang disimpan di $tags.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Tujuan
Menentukan apakah akan menambahkan kunci sebagai kunci yang diproteksi perangkat lunak atau kunci yang diproteksi HSM di layanan Key Vault.
Nilai valid adalah: HSM dan Perangkat Lunak.
Catatan: Untuk menggunakan HSM sebagai tujuan, Anda harus memiliki kunci vault yang mendukung HSM. Untuk informasi selengkapnya tentang tingkat layanan dan kemampuan Key Vault Azure, lihat situs web [Harga Azure Key Vault](https://go.microsoft.com/fwlink/?linkid=512521).
Parameter ini diperlukan ketika Anda membuat kunci baru. Jika Anda mengimpor kunci menggunakan parameter *KeyFilePath,* parameter ini bersifat opsional:
- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .byok, cmdlet tersebut akan mengimpor kunci tersebut sebagai tombol yang diproteksi HSM. Cmdlet tidak dapat mengimpor kunci tersebut sebagai kunci yang dilindungi perangkat lunak.
- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .pfx, cmdlet akan mengimpor kunci tersebut sebagai kunci yang diproteksi perangkat lunak.

```yaml
Type: System.String
Parameter Sets: InteractiveCreate, InputObjectCreate, ResourceIdCreate
Aliases:
Accepted values: HSM, Software

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: InteractiveImport, InputObjectImport, ResourceIdImport
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Vault.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault
Parameter Sets: InputObjectCreate, InputObjectImport
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyFilePassword
Menentukan kata sandi untuk file yang diimpor sebagai objek **SecureString.** Untuk mendapatkan objek **SecureString,** gunakan cmdlet **ConvertTo-SecureString.** Untuk informasi selengkapnya, ketik `Get-Help ConvertTo-SecureString` . Anda harus menentukan kata sandi ini untuk mengimpor file dengan ekstensi nama file .pfx.

```yaml
Type: System.Security.SecureString
Parameter Sets: InteractiveImport, InputObjectImport, ResourceIdImport
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
Type: System.String
Parameter Sets: InteractiveImport, InputObjectImport, ResourceIdImport
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
Nilai yang dapat diterima untuk parameter ini adalah daftar operasi kunci yang dipisahkan koma seperti yang ditetapkan oleh [spesifikasi JSON Web Key (JWK):](https://go.microsoft.com/fwlink/?LinkID=613300)
- Encrypt
- Dekripsi
- Bungkus
- Membatalkan rap
- Tanda tangani
- Verifikasi

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama kunci untuk ditambahkan ke kunci vault. Cmdlet ini menyusun nama domain (FQDN) yang sepenuhnya memenuhi syarat dari kunci berdasarkan nama yang ditentukan parameter ini, nama kunci vault, dan lingkungan Anda saat ini. Nama harus memiliki panjang string dari 1 sampai 63 karakter yang hanya berisi 0-9, a-z, A-Z, dan - (simbol garis putus-putus).

```yaml
Type: System.String
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
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya Vault.

```yaml
Type: System.String
Parameter Sets: ResourceIdCreate, ResourceIdImport
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Size
Ukuran tombol RSA, dalam bit. Jika tidak ditentukan, layanan akan menyediakan default yang aman.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: InteractiveCreate, InputObjectCreate, ResourceIdCreate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Menentukan nama key vault tempat cmdlet menambahkan kunci tersebut. Cmdlet ini menyusun FQDN dari kunci vault berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

```yaml
Type: System.String
Parameter Sets: InteractiveCreate, InteractiveImport
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault
Parameter: InputObject (ByValue)

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKey

## CATATAN

## RELATED LINKS

[Backup-AzureKeyVaultKey](./Backup-AzureKeyVaultKey.md)

[Get-AzureKeyVaultKey](./Get-AzureKeyVaultKey.md)

[Remove-AzureKeyVaultKey](./Remove-AzureKeyVaultKey.md)

