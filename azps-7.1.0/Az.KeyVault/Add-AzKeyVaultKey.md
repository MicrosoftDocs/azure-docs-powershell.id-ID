---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 846F781C-73A3-4BBE-ABD9-897371109FBE
online version: https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
ms.openlocfilehash: 4c9054282f073c18265f3f516d937db81af11199
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136762178"
---
# Add-AzKeyVaultKey

## SYNOPSIS
Membuat kunci di kunci vault atau mengimpor kunci ke kunci vault.

## SYNTAX

### InteractiveCreate (Default)
```
Add-AzKeyVaultKey [-VaultName] <String> [-Name] <String> -Destination <String> [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>] [-KeyType <String>]
 [-CurveName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InteractiveImport
```
Add-AzKeyVaultKey [-VaultName] <String> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Destination <String>] [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-KeyType <String>] [-CurveName <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HsmInteractiveCreate
```
Add-AzKeyVaultKey -HsmName <String> [-Name] <String> [-Disable] [-KeyOps <String[]>] [-Expires <DateTime>]
 [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>] -KeyType <String> [-CurveName <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HsmInteractiveImport
```
Add-AzKeyVaultKey -HsmName <String> [-Name] <String> -KeyFilePath <String> [-KeyFilePassword <SecureString>]
 [-Disable] [-KeyOps <String[]>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectCreate
```
Add-AzKeyVaultKey [-InputObject] <PSKeyVault> [-Name] <String> -Destination <String> [-Disable]
 [-KeyOps <String[]>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>]
 [-KeyType <String>] [-CurveName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectImport
```
Add-AzKeyVaultKey [-InputObject] <PSKeyVault> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Destination <String>] [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-KeyType <String>] [-CurveName <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HsmInputObjectCreate
```
Add-AzKeyVaultKey [-HsmObject] <PSManagedHsm> [-Name] <String> [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>] -KeyType <String>
 [-CurveName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HsmInputObjectImport
```
Add-AzKeyVaultKey [-HsmObject] <PSManagedHsm> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Disable] [-KeyOps <String[]>] [-Expires <DateTime>]
 [-NotBefore <DateTime>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceIdCreate
```
Add-AzKeyVaultKey [-ResourceId] <String> [-Name] <String> -Destination <String> [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>] [-KeyType <String>]
 [-CurveName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdImport
```
Add-AzKeyVaultKey [-ResourceId] <String> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Destination <String>] [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-KeyType <String>] [-CurveName <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HsmResourceIdCreate
```
Add-AzKeyVaultKey -HsmResourceId <String> [-Name] <String> [-Disable] [-KeyOps <String[]>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-Tag <Hashtable>] [-Size <Int32>] -KeyType <String>
 [-CurveName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HsmResourceIdImport
```
Add-AzKeyVaultKey -HsmResourceId <String> [-Name] <String> -KeyFilePath <String>
 [-KeyFilePassword <SecureString>] [-Disable] [-KeyOps <String[]>] [-Expires <DateTime>]
 [-NotBefore <DateTime>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzKeyVaultKey** membuat kunci di kunci vault di Azure Key Vault, atau mengimpor kunci ke kunci vault.
Gunakan cmdlet ini untuk menambahkan tombol menggunakan salah satu metode berikut:
- Buat kunci di modul keamanan perangkat keras (HSM, Hardware Security Module) di layanan Key Vault.
- Buat kunci di perangkat lunak dalam layanan Key Vault.
- Mengimpor kunci dari modul keamanan perangkat keras (HSM) Anda sendiri ke HSM di layanan Key Vault.
- Mengimpor kunci dari file .pfx di komputer Anda.
- Mengimpor kunci dari file .pfx di komputer Anda ke modul keamanan perangkat keras (HSMS) di layanan Key Vault.
Untuk setiap operasi ini, Anda dapat menyediakan atribut kunci atau menerima pengaturan default.
Jika Anda membuat atau mengimpor kunci yang memiliki nama yang sama dengan kunci yang sudah ada di kunci vault, kunci asli diperbarui dengan nilai yang Anda tentukan untuk kunci baru. Anda bisa mengakses nilai sebelumnya dengan menggunakan URI khusus versi untuk versi kunci tersebut. Untuk mempelajari tentang versi kunci dan struktur URI, lihat [Tentang Kunci dan Rahasia](http://go.microsoft.com/fwlink/?linkid=518560) dalam dokumentasi API REST Vault Kunci.
Catatan: Untuk mengimpor kunci dari modul keamanan perangkat keras milik sendiri, Anda harus membuat paket BYOK terlebih dahulu (file dengan ekstensi nama file .byok) menggunakan perangkat keras Azure Key Vault BYOK. Untuk informasi selengkapnya, [lihat Cara Membuat dan Mentransfer HSM-Protected Kunci untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).
Sebagai praktik terbaik, cadangankan kunci Anda setelah dibuat atau diperbarui, dengan menggunakan cmdlet Backup-AzKeyVaultKey. Tidak ada fungsionalitas yang dibatalkan, jadi jika Anda secara tidak sengaja menghapus kunci atau menghapusnya lalu berubah pikiran, kunci tersebut tidak dapat dipulihkan kecuali Anda memiliki cadangannya yang bisa dipulihkan.

## EXAMPLES

### Contoh 1: Buat kunci
```powershell
PS C:\> Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITSoftware' -Destination 'Software'

Vault/HSM Name : contoso
Name           : ITSoftware
Key Type       : RSA
Key Size       : 2048
Curve Name     : 
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

### Contoh 2: Membuat kunci EC
```powershell
PS C:\> Add-AzKeyVaultKey -VaultName test-kv -Name test-key -Destination Software -KeyType EC

Vault/HSM Name : test-kv
Name           : test-key
Key Type       : EC
Key Size       :
Curve Name     : P-256
Version        : 4da74af2b4fd47d6b1aa0b05c9a2ed13
Id             : https://test-kv.vault.azure.net:443/keys/test-key/4da74af2b4fd47d6b1aa0b05c9a2ed13
Enabled        : True
Expires        :
Not Before     :
Created        : 8/24/2021 6:38:34 AM
Updated        : 8/24/2021 6:38:34 AM
Recovery Level : Recoverable+Purgeable
Tags           :
```

Perintah ini membuat kunci EC yang dilindungi perangkat lunak bernama test-key dalam kunci vault bernama test-vault. Nama kurvanya adalah P-256 secara default.

### Contoh 3: Membuat kunci yang dilindungi HSM
```powershell
PS C:\> Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITHsm' -Destination 'HSM'

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

### Contoh 4: Membuat kunci dengan nilai non-default
```powershell
PS C:\> $KeyOperations = 'decrypt', 'verify'
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $NotBefore = (Get-Date).ToUniversalTime()
PS C:\> $Tags = @{'Severity' = 'high'; 'Accounting' = "true"}
PS C:\> Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITHsmNonDefault' -Destination 'HSM' -Expires $Expires -NotBefore $NotBefore -KeyOps $KeyOperations -Disable -Tag $Tags

Vault/HSM Name : contoso
Name           : ITHsmNonDefault
Key Type       : RSA
Key Size       : 2048
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
Perintah terakhir membuat kunci bernama ITHsmNonDefault yang merupakan kunci yang dilindungi HSM. Perintah menentukan nilai untuk operasi tombol diperbolehkan yang disimpan $KeyOperations. Perintah menentukan waktu untuk  parameter Kedaluwarsa dan *NotBefore* yang dibuat di perintah sebelumnya, dan tag untuk tingkat keparahan tinggi dan IT. Kunci baru dinonaktifkan. Anda dapat mengaktifkannya menggunakan cmdlet **Set-AzKeyVaultKey.**

### Contoh 5: Mengimpor kunci yang diproteksi HSM
```powershell
PS C:\> Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITByok' -KeyFilePath 'C:\Contoso\ITByok.byok' -Destination 'HSM'

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
Untuk informasi selengkapnya, [lihat Cara Membuat dan Mentransfer HSM-Protected Kunci untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).

### Contoh 6: Mengimpor kunci yang diproteksi perangkat lunak
```powershell
PS C:\> $Password = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITPfx' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password

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

### Contoh 7: Mengimpor kunci dan menetapkan atribut
```powershell
PS C:\> $Password = ConvertTo-SecureString -String 'password' -AsPlainText -Force
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'high'; 'Accounting' = "true" }
PS C:\> Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITPfxToHSM' -Destination 'HSM' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password -Expires $Expires -Tag $Tags

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
Perintah ketiga membuat $tags variabel untuk mengatur tag tingkat keparahan tinggi dan IT.
Perintah terakhir mengimpor kunci sebagai tombol HSM dari lokasi tertentu. Perintah menentukan waktu kedaluwarsa yang disimpan di $Expires kata sandi yang disimpan di $Password, dan menerapkan tag yang disimpan di $tags.

### Contoh 8: Menghasilkan Tombol Exchange (KEK) untuk "bawa kunci Anda sendiri" (BYOK) fitur

```powershell
PS C:\> $key = Add-AzKeyVaultKey -VaultName $vaultName -Name $keyName -Destination HSM -Size 2048 -KeyOps "import"
```

Menghasilkan kunci (disebut sebagai Tombol utama Exchange (KEK)). KEK harus merupakan kunci RSA-HSM yang hanya memiliki operasi kunci impor. Hanya Kunci Vault Premium SKU yang mendukung tombol RSA-HSM.
Untuk detail selengkapnya, silakan lihat https://docs.microsoft.com/azure/key-vault/keys/hsm-protected-keys

## PARAMETERS

### -CurveName
Menentukan nama kurva dari kriptografi kurva eksliptik, nilai ini valid ketika KeyType adalah EC.

```yaml
Type: System.String
Parameter Sets: InteractiveCreate, InteractiveImport, HsmInteractiveCreate, InputObjectCreate, InputObjectImport, HsmInputObjectCreate, ResourceIdCreate, ResourceIdImport, HsmResourceIdCreate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Tujuan
Menentukan apakah akan menambahkan kunci sebagai kunci yang diproteksi perangkat lunak atau kunci yang diproteksi HSM di layanan Key Vault.
Nilai valid adalah: HSM dan Perangkat Lunak.
Catatan: Untuk menggunakan HSM sebagai tujuan, Anda harus memiliki kunci vault yang mendukung HSM. Untuk informasi selengkapnya tentang tingkat layanan dan kemampuan Key Vault Azure, lihat situs web [Harga Azure Key Vault](http://go.microsoft.com/fwlink/?linkid=512521).
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

### -HsmName
Nama HSM. Cmdlet menyusun FQDN dari HSM yang dikelola berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: HsmInteractiveCreate, HsmInteractiveImport
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HsmObject
Objek HSM.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm
Parameter Sets: HsmInputObjectCreate, HsmInputObjectImport
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HsmResourceId
ID Sumber Daya HSM.

```yaml
Type: System.String
Parameter Sets: HsmResourceIdCreate, HsmResourceIdImport
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: InteractiveImport, HsmInteractiveImport, InputObjectImport, HsmInputObjectImport, ResourceIdImport, HsmResourceIdImport
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
Parameter Sets: InteractiveImport, HsmInteractiveImport, InputObjectImport, HsmInputObjectImport, ResourceIdImport, HsmResourceIdImport
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
- enkripsi
- dekripsi
- wrapKey
- unwrapKey
- tanda tangan
- verifikasi
- impor (hanya untuk KEK, lihat contoh 7)

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

### -KeyType
Menentukan tipe kunci dari kunci ini. Ketika mengimpor tombol BYOK, defaultnya adalah 'RSA'.

```yaml
Type: System.String
Parameter Sets: InteractiveCreate, InteractiveImport, InputObjectCreate, InputObjectImport, ResourceIdCreate, ResourceIdImport
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: HsmInteractiveCreate, HsmInputObjectCreate, HsmResourceIdCreate
Aliases:

Required: True
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
Parameter Sets: InteractiveCreate, HsmInteractiveCreate, InputObjectCreate, HsmInputObjectCreate, ResourceIdCreate, HsmResourceIdCreate
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKey

## CATATAN

## RELATED LINKS

[Backup-AzKeyVaultKey](./Backup-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Remove-AzKeyVaultKey](./Remove-AzKeyVaultKey.md)
