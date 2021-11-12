---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 636FAD5B-8C39-4E5C-8978-6845C6B89BC0
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/set-Azkeyvaultaccesspolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultAccessPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultAccessPolicy.md
ms.openlocfilehash: 466c80f57cda8c2358dcac96374ca2617b30bdd119b4bb086e7c376456ddbcef
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415453"
---
# Set-AzKeyVaultAccessPolicy

## SYNOPSIS
Memberikan atau mengubah izin yang sudah ada untuk pengguna, aplikasi, atau grup keamanan untuk melakukan operasi dengan kunci vault.

## SYNTAX

### ByServicePrincipalName
```
Set-AzKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>]
 -ServicePrincipalName <String> [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-PermissionsToCertificates <String[]>] [-PermissionsToStorage <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByUserPrincipalName
```
Set-AzKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>]
 -UserPrincipalName <String> [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-PermissionsToCertificates <String[]>] [-PermissionsToStorage <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectId
```
Set-AzKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] -ObjectId <String>
 [-ApplicationId <Guid>] [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-PermissionsToCertificates <String[]>] [-PermissionsToStorage <String[]>] [-BypassObjectIdValidation]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByEmailAddress
```
Set-AzKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] -EmailAddress <String>
 [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>] [-PermissionsToCertificates <String[]>]
 [-PermissionsToStorage <String[]>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ForVault
```
Set-AzKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] [-EnabledForDeployment]
 [-EnabledForTemplateDeployment] [-EnabledForDiskEncryption] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzKeyVaultAccessPolicy** memberi atau mengubah izin yang sudah ada untuk pengguna, aplikasi, atau grup keamanan untuk menjalankan operasi tertentu dengan kunci vault. Itu tidak mengubah izin yang ada pada pengguna lain, aplikasi, atau grup keamanan di vault utama.

Jika Anda mengatur izin untuk grup keamanan, operasi ini hanya memengaruhi pengguna dalam grup keamanan tersebut.

Direktori berikut semuanya harus sama dengan Azure directory:
- Direktori default langganan Azure tempat penyimpanan kunci berada.
- Direktori Azure yang berisi pengguna atau grup aplikasi yang Anda berikan izinnya.

Contoh skenario saat kondisi ini tidak terpenuhi dan cmdlet ini tidak akan berfungsi adalah:

- Mengomuritaskan pengguna dari organisasi lain untuk mengelola kunci vault.
Setiap organisasi memiliki direktorinya sendiri.
- Akun Azure Anda memiliki beberapa direktori.
Jika Anda mendaftarkan aplikasi di direktori selain direktori default, Anda tidak dapat mengotorisasi aplikasi tersebut untuk menggunakan kunci vault.
Aplikasi harus berada dalam direktori default.

Perhatikan bahwa meskipun menentukan grup sumber daya bersifat opsional untuk cmdlet ini, Anda harus melakukannya untuk kinerja yang lebih baik.

## EXAMPLES

### Contoh 1: Memberikan izin kepada pengguna untuk penyimpanan kunci dan mengubah izin
```
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToKeys create,import,delete,list -PermissionsToSecrets set,delete
PS C:\> Set-AzKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToSecrets set,delete,get -PassThru
PS C:\> Set-AzKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToKeys @() -PassThru
```

Perintah pertama memberikan izin bagi pengguna dalam Azure Active Directory Anda, untuk menjalankan operasi kunci dan rahasia dengan kunci PattiFuller@contoso.com vault yang bernama Contoso03Vault.

Perintah kedua mengubah izin yang diberikan pada perintah pertama, untuk sekarang memungkinkan mendapatkan rahasia selain mengatur PattiFuller@contoso.com dan menghapusnya. Izin operasi utama tetap tidak berubah setelah perintah ini. Parameter *PassThru* menghasilkan objek yang diperbarui yang dikembalikan oleh cmdlet.

Perintah terakhir selanjutnya mengubah izin yang sudah ada untuk PattiFuller@contoso.com menghapus semua izin ke operasi utama. Izin operasi rahasia tidak berubah setelah perintah ini. Parameter *PassThru* menghasilkan objek yang diperbarui yang dikembalikan oleh cmdlet.

### Contoh 2: Memberikan izin untuk prinsipal layanan aplikasi untuk rahasia baca dan tulis
```
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -ServicePrincipalName 'http://payroll.contoso.com' -PermissionsToSecrets Get,Set
```

Perintah ini memberikan izin untuk aplikasi untuk penyimpanan kunci bernama Contoso03Vault.

Parameter *ServicePrincipalName* menentukan aplikasi. Aplikasi harus terdaftar di komputer Azure Active Directory. Nilai parameter *ServicePrincipalName* harus merupakan nama prinsipal layanan aplikasi atau GUID ID aplikasi.

Contoh ini menentukan nama prinsipal layanan `http://payroll.contoso.com` , dan perintah memberikan izin aplikasi untuk membaca dan menulis rahasia.

### Contoh 3: Berikan izin untuk aplikasi menggunakan ID objeknya
```
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -ObjectId 34595082-9346-41b6-8d6b-295a2808b8db -PermissionsToSecrets Get,Set
```

Perintah ini memberikan izin aplikasi untuk membaca dan menulis rahasia.

Contoh ini menentukan aplikasi menggunakan ID objek prinsipal layanan aplikasi.

### Contoh 4: Memberikan izin untuk nama prinsipal pengguna
```
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToSecrets Get,List,Set
```

Perintah ini memberikan izin get, list, dan mengatur izin untuk nama prinsipal pengguna tertentu untuk akses menuju rahasia.

### Contoh 5: Mengaktifkan rahasia yang diambil dari vault vault kunci oleh penyedia sumber daya Microsoft.Compute
```
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -EnabledForDeployment
```

Perintah ini memberikan izin rahasia agar diambil dari penyimpanan kunci Contoso03Vault oleh penyedia sumber daya Microsoft.Compute.

### Contoh 6: Berikan izin ke grup keamanan
```
PS C:\>Get-AzADGroup
PS C:\> Set-AzKeyVaultAccessPolicy -VaultName 'myownvault' -ObjectId (Get-AzADGroup -SearchString 'group2')[0].Id -PermissionsToKeys All -PermissionsToSecrets All
DisplayName                    Type                           ObjectId
-----------                    ----                           --------
group1                                                        96a0daa6-9841-4a9c-bdeb-e7062276c688
group2                                                        b8a401eb-63ad-4a30-b0e1-a7461969fe54
group3                                                        da07a6be-2c1e-4e42-934d-ceb57cf652b4
```

Perintah pertama menggunakan cmdlet Get-AzADGroup untuk mendapatkan semua grup Direktori Aktif. Dari output, Anda melihat 3 grup yang dikembalikan, bernama **grup1**, **grup2**, dan **grup3**. Beberapa grup dapat memiliki nama yang sama tetapi selalu mempunyai ObjectId yang unik. Ketika lebih dari satu grup dengan nama yang sama dikembalikan, gunakan ObjectId dalam output untuk mengidentifikasi yang ingin Anda gunakan.

Anda lalu menggunakan output perintah ini dengan Set-AzKeyVaultAccessPolicy untuk memberikan izin ke group2 untuk penyimpanan kunci Anda, bernama **myownvault**. Contoh ini menghitung grup yang bernama sebaris 'grup2' dalam baris perintah yang sama.

Mungkin terdapat beberapa grup dalam daftar yang dikembalikan yang bernama 'grup2'.
Contoh ini memilih yang pertama, yang ditunjukkan dengan indeks \[ 0 \] dalam daftar yang dikembalikan.

### Contoh 7: Berikan akses Perlindungan Informasi Azure ke kunci penyewa yang dikelola pelanggan (BYOK)
```
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName 'Contoso04Vault' -ServicePrincipalName 00000012-0000-0000-c000-000000000000 -PermissionsToKeys decrypt,sign,get
```

Perintah ini mengotorisasi Perlindungan Informasi Azure untuk menggunakan kunci yang dikelola pelanggan (yang menghadirkan kunci Anda sendiri, atau skenario "BYOK" sebagai kunci penyewa Perlindungan Informasi Azure.

Ketika menjalankan perintah ini, tentukan nama kunci vault Anda sendiri, tetapi parameter *ServicePrincipalName* harus ditentukan dengan GUID **00000012-0000-0000-c000-00000000000 dan** tentukan izin dalam contoh.

## PARAMETERS

### -ApplicationId
Untuk penggunaan di masa mendatang.

```yaml
Type: Guid
Parameter Sets: ByObjectId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BypassObjectIdValidation
Memungkinkan Anda menentukan ID objek tanpa memvalidasi bahwa objek ada di Azure Active Directory.

Gunakan parameter ini hanya jika Anda ingin memberikan akses ke kunci vault ke ID objek yang merujuk ke grup keamanan terdelegasi dari penyewa Azure lain.

```yaml
Type: SwitchParameter
Parameter Sets: ByObjectId
Aliases:

Required: False
Position: Named
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

### -EmailAddress
Menentukan alamat email pengguna dari pengguna yang akan diberi izin.

Alamat email harus ada dalam direktori yang terkait dengan langganan saat ini dan unik.

```yaml
Type: String
Parameter Sets: ByEmailAddress
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnabledForDeployment
Memungkinkan penyedia sumber daya Microsoft.Compute untuk mendapatkan rahasia dari key vault ini saat key vault ini direferensikan dalam pembuatan sumber daya, misalnya saat membuat mesin virtual.

```yaml
Type: SwitchParameter
Parameter Sets: ForVault
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnabledForDiskEncryption
Memungkinkan layanan enkripsi disk Azure untuk mendapatkan kunci rahasia dan unwrap dari kunci vault ini.

```yaml
Type: SwitchParameter
Parameter Sets: ForVault
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnabledForTemplateDeployment
Memungkinkan Azure Resource Manager untuk mendapatkan rahasia dari key vault ini ketika key vault ini direferensikan dalam penyebaran templat.

```yaml
Type: SwitchParameter
Parameter Sets: ForVault
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Menentukan ID objek pengguna atau prinsipal layanan dalam Azure Active Directory untuk memberikan izin.

```yaml
Type: String
Parameter Sets: ByObjectId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.

Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -PermissionsToCertificates
Menentukan array izin sertifikat yang akan diberikan kepada pengguna atau prinsipal layanan.

Nilai yang dapat diterima untuk parameter ini:

- Dapatkan
- Daftar
- Hapus
- Buat
- Impor
- Perbarui
- Managecontacts
- Getissuers
- Listissuers
- Setissuers
- Deleteissuers
- Manageissuers

```yaml
Type: String[]
Parameter Sets: ByServicePrincipalName, ByUserPrincipalName, ByObjectId, ByEmailAddress
Aliases:
Accepted values: get, list, delete, create, import, update, managecontacts, getissuers, listissuers, setissuers, deleteissuers, manageissuers, recover, purge, all

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PermissionsToKeys
Menentukan array izin operasi utama yang diberikan kepada pengguna atau prinsipal layanan.

Nilai yang dapat diterima untuk parameter ini:

- Dekripsi
- Encrypt
- UnwrapKey
- WrapKey
- Verifikasi
- Tanda tangani
- Dapatkan
- Daftar
- Perbarui
- Buat
- Impor
- Hapus
- Pencadangan
- Pulihkan
- Pulihkan
- Purge

```yaml
Type: String[]
Parameter Sets: ByServicePrincipalName, ByUserPrincipalName, ByObjectId, ByEmailAddress
Aliases:
Accepted values: decrypt, encrypt, unwrapKey, wrapKey, verify, sign, get, list, update, create, import, delete, backup, restore, recover, purge, all

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PermissionsToSecrets
Menentukan array izin operasi rahasia yang diberikan kepada pengguna atau prinsipal layanan.

Nilai yang dapat diterima untuk parameter ini:

- Dapatkan
- Daftar
- Set
- Hapus
- Pencadangan
- Pulihkan
- Pulihkan
- Purge

```yaml
Type: String[]
Parameter Sets: ByServicePrincipalName, ByUserPrincipalName, ByObjectId, ByEmailAddress
Aliases:
Accepted values: get, list, set, delete, backup, restore, recover, purge, all

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PermissionsToStorage
Menentukan izin operasi definisi SaS dan akun penyimpanan terkelola yang diberikan kepada pengguna atau prinsipal layanan.

```yaml
Type: String[]
Parameter Sets: ByServicePrincipalName, ByUserPrincipalName, ByObjectId, ByEmailAddress
Aliases:
Accepted values: get, list, delete, set, update, regeneratekey, getsas, listsas, deletesas, setsas, all

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePrincipalName
Menentukan nama prinsipal layanan aplikasi untuk memberikan izin.

Tentukan ID aplikasi, dikenal juga sebagai ID klien, yang terdaftar untuk aplikasi di AzureActive Directory. Aplikasi dengan nama prinsipal layanan yang ditentukan parameter ini harus terdaftar dalam direktori Azure yang berisi langganan Anda saat ini.

```yaml
Type: String
Parameter Sets: ByServicePrincipalName
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserPrincipalName
Menentukan nama utama pengguna bagi pengguna yang akan diberi izin.

Nama prinsipal pengguna ini harus ada dalam direktori yang terkait dengan langganan saat ini.

```yaml
Type: String
Parameter Sets: ByUserPrincipalName
Aliases: UPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kunci vault.

Cmdlet ini mengubah kebijakan akses untuk key vault yang ditentukan oleh parameter ini.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

### String, Guid, String[], Sakelar

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSVault

## CATATAN

## RELATED LINKS

[Get-AzKeyVault](./Get-AzKeyVault.md)

[Remove-AzKeyVaultAccessPolicy](./Remove-AzKeyVaultAccessPolicy.md)

