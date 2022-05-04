---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 846F781C-73A3-4BBE-ABD9-897371109FBE
online version: https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Add-AzKeyVaultKey.md
ms.openlocfilehash: 6eafef1f455d9abd27c0709b0947d479c5baa091
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144608864"
---
# Add-AzKeyVaultKey

## SYNOPSIS
Membuat kunci dalam brankas kunci atau mengimpor kunci ke dalam brankas kunci.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/add-azkeyvaultkey) untuk informasi terbaru.

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

### HsmInteractiveBuat
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
Cmdlet **Add-AzKeyVaultKey** membuat kunci di brankas kunci di Azure Key Vault, atau mengimpor kunci ke dalam brankas kunci.
Gunakan cmdlet ini untuk menambahkan kunci dengan menggunakan salah satu metode berikut:
- Buat kunci dalam modul keamanan perangkat keras (HSM) di layanan Key Vault.
- Buat kunci dalam perangkat lunak di layanan Key Vault.
- Impor kunci dari modul keamanan perangkat keras (HSM) Anda sendiri ke HSM dalam layanan Key Vault.
- Impor kunci dari file .pfx pada komputer Anda.
- Impor kunci dari file .pfx di komputer Anda ke modul keamanan perangkat keras (HSM) di layanan Key Vault.
Untuk salah satu operasi ini, Anda dapat menyediakan atribut utama atau menerima pengaturan default.
Jika Anda membuat atau mengimpor kunci yang memiliki nama yang sama dengan kunci yang ada di brankas kunci Anda, kunci asli diperbarui dengan nilai yang Anda tentukan untuk kunci baru. Anda dapat mengakses nilai sebelumnya dengan menggunakan URI khusus versi untuk versi kunci tersebut. Untuk mempelajari tentang versi kunci dan struktur URI, lihat [Tentang Kunci dan Rahasia](http://go.microsoft.com/fwlink/?linkid=518560) dalam dokumentasi REST API Key Vault.
Catatan: Untuk mengimpor kunci dari modul keamanan perangkat keras Anda sendiri, Anda harus terlebih dahulu membuat paket BYOK (file dengan ekstensi nama file .byok) dengan menggunakan toolset Azure Key Vault BYOK. Untuk informasi selengkapnya, lihat [Cara Membuat dan Mentransfer Kunci HSM-Protected untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).
Sebagai praktik terbaik, cadangkan kunci Anda setelah dibuat atau diperbarui, dengan menggunakan cmdlet Backup-AzKeyVaultKey. Tidak ada fungsionalitas yang tidak dihapus, jadi jika Anda secara tidak sengaja menghapus kunci atau menghapusnya dan kemudian berubah pikiran, kunci tidak dapat dipulihkan kecuali Anda memiliki cadangan yang dapat Anda pulihkan.

## EXAMPLES

### Contoh 1: Membuat kunci
```powershell
Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITSoftware' -Destination 'Software'
```

```output
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

Perintah ini membuat kunci yang dilindungi perangkat lunak bernama ITSoftware di brankas kunci bernama Contoso.

### Contoh 2: Membuat kunci EC
```powershell
Add-AzKeyVaultKey -VaultName test-kv -Name test-key -Destination Software -KeyType EC
```

```output
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

Perintah ini membuat kunci EC yang dilindungi perangkat lunak bernama test-key di brankas kunci bernama test-kv. Nama kurvanya adalah P-256 secara default.

### Contoh 3: Membuat kunci yang dilindungi HSM
```powershell
Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITHsm' -Destination 'HSM'
```

```output
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

Perintah ini membuat kunci yang dilindungi HSM di brankas kunci bernama Contoso.

### Contoh 4: Membuat kunci dengan nilai non-default
```powershell
$KeyOperations = 'decrypt', 'verify'
$Expires = (Get-Date).AddYears(2).ToUniversalTime()
$NotBefore = (Get-Date).ToUniversalTime()
$Tags = @{'Severity' = 'high'; 'Accounting' = "true"}
Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITHsmNonDefault' -Destination 'HSM' -Expires $Expires -NotBefore $NotBefore -KeyOps $KeyOperations -Disable -Tag $Tags
```

```output
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

Perintah pertama menyimpan nilai yang didekripsi dan memverifikasi dalam variabel $KeyOperations.
Perintah kedua membuat objek **DateTime** , yang ditentukan dalam UTC, dengan menggunakan cmdlet **Get-Date** .
Objek itu menentukan waktu dua tahun di masa depan. Perintah menyimpan tanggal tersebut dalam variabel $Expires. Untuk informasi selengkapnya, ketik `Get-Help Get-Date`.
Perintah ketiga membuat objek **DateTime** dengan menggunakan cmdlet **Get-Date** . Objek tersebut menentukan waktu UTC saat ini. Perintah menyimpan tanggal tersebut dalam variabel $NotBefore.
Perintah akhir membuat kunci bernama ITHsmNonDefault yang merupakan kunci yang dilindungi HSM. Perintah menentukan nilai untuk operasi kunci yang diizinkan yang disimpan $KeyOperations. Perintah menentukan waktu untuk parameter *Kedaluwarsa* dan *NotBefore* yang dibuat dalam perintah sebelumnya, dan tag untuk tingkat keparahan tinggi dan TI. Kunci baru dinonaktifkan. Anda dapat mengaktifkannya dengan menggunakan cmdlet **Set-AzKeyVaultKey** .

### Contoh 5: Mengimpor kunci yang dilindungi HSM
```powershell
Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITByok' -KeyFilePath 'C:\Contoso\ITByok.byok' -Destination 'HSM'
```

```output
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

Perintah ini mengimpor kunci bernama ITByok dari lokasi yang ditentukan parameter *KeyFilePath* . Kunci yang diimpor adalah kunci yang dilindungi HSM.
Untuk mengimpor kunci dari modul keamanan perangkat keras Anda sendiri, Anda harus terlebih dahulu membuat paket BYOK (file dengan ekstensi nama file .byok) dengan menggunakan toolset Azure Key Vault BYOK.
Untuk informasi selengkapnya, lihat [Cara Membuat dan Mentransfer Kunci HSM-Protected untuk Azure Key Vault](http://go.microsoft.com/fwlink/?LinkId=522252).

### Contoh 6: Mengimpor kunci yang dilindungi perangkat lunak
```powershell
$Password = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITPfx' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password
```

```output
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

Perintah pertama mengonversi string menjadi string aman dengan menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Password. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString`.
Perintah kedua membuat kata sandi perangkat lunak di brankas kunci Contoso. Perintah menentukan lokasi untuk kunci dan kata sandi yang disimpan di $Password.

### Contoh 7: Mengimpor kunci dan menetapkan atribut
```powershell
$Password = ConvertTo-SecureString -String 'password' -AsPlainText -Force
$Expires = (Get-Date).AddYears(2).ToUniversalTime()
$Tags = @{ 'Severity' = 'high'; 'Accounting' = "true" }
Add-AzKeyVaultKey -VaultName 'contoso' -Name 'ITPfxToHSM' -Destination 'HSM' -KeyFilePath 'C:\Contoso\ITPfx.pfx' -KeyFilePassword $Password -Expires $Expires -Tag $Tags
```

```output
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

Perintah pertama mengonversi string menjadi string aman dengan menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Password.
Perintah kedua membuat objek **DateTime** dengan menggunakan cmdlet **Get-Date** , lalu menyimpan objek tersebut dalam variabel $Expires.
Perintah ketiga membuat variabel $tags untuk mengatur tag untuk tingkat keparahan tinggi dan IT.
Perintah akhir mengimpor kunci sebagai kunci HSM dari lokasi yang ditentukan. Perintah menentukan waktu kedaluwarsa yang disimpan dalam $Expires dan kata sandi yang disimpan di $Password, dan menerapkan tag yang disimpan di $tags.

### Contoh 8: Buat Kunci Exchange Kunci (KEK) untuk fitur "bring your own key" (BYOK)

```powershell
$key = Add-AzKeyVaultKey -VaultName $vaultName -Name $keyName -Destination HSM -Size 2048 -KeyOps "import"
```

Menghasilkan kunci (disebut sebagai Kunci Exchange Kunci (KEK)). KEK harus berupa kunci RSA-HSM yang hanya memiliki operasi kunci impor. Hanya Key Vault Premium SKU yang mendukung kunci RSA-HSM.
Untuk detail selengkapnya, silakan merujuk ke https://docs.microsoft.com/azure/key-vault/keys/hsm-protected-keys

## PARAMETERS

### -CurveName
Menentukan nama kurva kriptografi kurva elips, nilai ini valid saat KeyType adalah EC.

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

### -Destination
Menentukan apakah akan menambahkan kunci sebagai kunci yang dilindungi perangkat lunak atau kunci yang dilindungi HSM dalam layanan Key Vault.
Nilai yang valid adalah: HSM dan Perangkat Lunak.
Catatan: Untuk menggunakan HSM sebagai tujuan, Anda harus memiliki brankas kunci yang mendukung HSM. Untuk informasi selengkapnya tentang tingkat layanan dan kemampuan untuk Azure Key Vault, lihat [situs web Harga Azure Key Vault](http://go.microsoft.com/fwlink/?linkid=512521).
Parameter ini diperlukan saat Anda membuat kunci baru. Jika Anda mengimpor kunci dengan menggunakan parameter *KeyFilePath* , parameter ini bersifat opsional:
- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .byok, cmdlet ini mengimpor kunci tersebut sebagai kunci yang dilindungi HSM. Cmdlet tidak dapat mengimpor kunci tersebut sebagai kunci yang dilindungi perangkat lunak.
- Jika Anda tidak menentukan parameter ini, dan cmdlet ini mengimpor kunci yang memiliki ekstensi nama file .pfx, cmdlet ini mengimpor kunci sebagai kunci yang dilindungi perangkat lunak.

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

### -Nonaktifkan
Menunjukkan bahwa kunci yang Anda tambahkan diatur ke status awal dinonaktifkan. Setiap upaya untuk menggunakan kunci akan gagal. Gunakan parameter ini jika Anda memuat kunci sebelumnya yang ingin Anda aktifkan nanti.

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
Menentukan waktu kedaluwarsa, sebagai objek **DateTime** , untuk kunci yang ditambahkan cmdlet ini. Parameter ini menggunakan Waktu Universal Terkoordinasi (UTC). Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** . Untuk informasi selengkapnya, ketik `Get-Help Get-Date`. Jika Anda tidak menentukan parameter ini, kunci tidak akan kedaluwarsa.

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
Nama HSM. Cmdlet membangun FQDN dari HSM terkelola berdasarkan nama dan lingkungan yang saat ini dipilih.

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
ID sumber daya HSM.

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
Objek vault.

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
Menentukan kata sandi untuk file yang diimpor sebagai objek **SecureString** . Untuk mendapatkan objek **SecureString** , gunakan cmdlet **ConvertTo-SecureString** . Untuk informasi selengkapnya, ketik `Get-Help ConvertTo-SecureString`. Anda harus menentukan kata sandi ini untuk mengimpor file dengan ekstensi nama file .pfx.

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
Menentukan jalur file lokal yang berisi materi kunci yang diimpor cmdlet ini.
Ekstensi nama file yang valid adalah .byok dan .pfx.
- Jika file adalah file .byok, kunci secara otomatis dilindungi oleh HSM setelah impor dan Anda tidak dapat mengambil alih default ini.
- Jika file adalah file .pfx, kunci secara otomatis dilindungi oleh perangkat lunak setelah impor. Untuk mengambil alih default ini, atur parameter *Tujuan* ke HSM sehingga kunci dilindungi HSM.
Saat Anda menentukan parameter ini, parameter *Tujuan* bersifat opsional.

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
Menentukan array operasi yang dapat dilakukan dengan menggunakan kunci yang ditambahkan cmdlet ini.
Jika Anda tidak menentukan parameter ini, semua operasi dapat dilakukan.
Nilai yang dapat diterima untuk parameter ini adalah daftar operasi kunci yang dipisahkan dengan koma sebagaimana didefinisikan oleh [spesifikasi JSON Web Key (JWK)](http://go.microsoft.com/fwlink/?LinkID=613300):
- mengenkripsi
- mendekripsi
- wrapKey
- unwrapKey
- sign
- verify
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
Menentukan tipe kunci kunci ini. Saat mengimpor kunci BYOK, kunci defaultnya adalah 'RSA'.

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

### -Name
Menentukan nama kunci yang akan ditambahkan ke brankas kunci. Cmdlet ini membangun nama domain yang sepenuhnya memenuhi syarat (FQDN) dari kunci berdasarkan nama yang ditentukan parameter ini, nama brankas kunci, dan lingkungan Anda saat ini. Nama harus berupa string dengan panjang 1 hingga 63 karakter yang hanya berisi 0-9, a-z, A-Z, dan - (simbol tanda hubung).

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
Menentukan waktu, sebagai objek **DateTime** , sebelum kunci tidak dapat digunakan. Parameter ini menggunakan UTC. Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** . Jika Anda tidak menentukan parameter ini, kunci dapat segera digunakan.

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

### -Ukuran
Ukuran kunci RSA, dalam bit. Jika tidak ditentukan, layanan akan menyediakan default yang aman.

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
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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
Menentukan nama brankas kunci tempat cmdlet ini menambahkan kunci. Cmdlet ini membangun FQDN dari brankas kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultKey

## NOTES

## RELATED LINKS

[Cadangan-KunciAzKeyVault](./Backup-AzKeyVaultKey.md)

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Remove-AzKeyVaultKey](./Remove-AzKeyVaultKey.md)
