---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 636FAD5B-8C39-4E5C-8978-6845C6B89BC0
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/set-azurermkeyvaultaccesspolicy
schema: 2.0.0
ms.openlocfilehash: e2564d18653c8ae404ff7b936639711f997dc855
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141971745"
---
# Set-AzureRmKeyVaultAccessPolicy

## SYNOPSIS
Memberikan atau mengubah izin yang sudah ada untuk pengguna, aplikasi, atau grup keamanan untuk melakukan operasi dengan kubah kunci.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByServicePrincipalName
```
Set-AzureRmKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>]
 -ServicePrincipalName <String> [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-PermissionsToCertificates <String[]>] [-PermissionsToStorage <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByUserPrincipalName
```
Set-AzureRmKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>]
 -UserPrincipalName <String> [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-PermissionsToCertificates <String[]>] [-PermissionsToStorage <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectId
```
Set-AzureRmKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] -ObjectId <String>
 [-ApplicationId <Guid>] [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-PermissionsToCertificates <String[]>] [-PermissionsToStorage <String[]>] [-BypassObjectIdValidation]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByEmailAddress
```
Set-AzureRmKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] -EmailAddress <String>
 [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>] [-PermissionsToCertificates <String[]>]
 [-PermissionsToStorage <String[]>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ForVault
```
Set-AzureRmKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] [-EnabledForDeployment]
 [-EnabledForTemplateDeployment] [-EnabledForDiskEncryption] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmKeyVaultAccessPolicy** memberikan atau mengubah izin yang sudah ada untuk pengguna, aplikasi, atau grup keamanan untuk melakukan operasi tertentu dengan kubah kunci. Ini tidak mengubah izin yang dimiliki pengguna, aplikasi, atau grup keamanan lain pada kubah kunci.

Jika Anda mengatur izin untuk grup keamanan, operasi ini hanya memengaruhi pengguna dalam grup keamanan tersebut.

Semua direktori berikut harus sama seperti Azure directory:
- Direktori default langganan Azure tempat kubah kunci berada.
- Direktori Azure yang berisi grup pengguna atau aplikasi yang Anda beri izin.

Contoh skenario ketika kondisi ini tidak terpenuhi dan cmdlet ini tidak akan berfungsi adalah:

- Mengotorisasi pengguna dari organisasi lain untuk mengelola kubah kunci Anda.
Setiap organisasi memiliki direktorinya sendiri.
- Akun Azure Anda memiliki beberapa direktori.
Jika Anda mendaftarkan aplikasi di direktori selain direktori default, Anda tidak dapat mengotorisasi aplikasi tersebut untuk menggunakan kubah kunci Anda.
Aplikasi harus berada dalam direktori default.

Perhatikan bahwa meskipun menentukan grup sumber daya bersifat opsional untuk cmdlet ini, Anda harus melakukannya untuk kinerja yang lebih baik.

## EXAMPLES

### Contoh 1: Memberikan izin kepada pengguna untuk kubah kunci dan mengubah izin
```
PS C:\>Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToKeys create,import,delete,list -PermissionsToSecrets 'set,delete'
PS C:\> Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToSecrets set,delete,get -PassThru
PS C:\> Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToKeys @() -PassThru
```

Perintah pertama memberikan izin bagi pengguna di Azure Active Directory Anda, PattiFuller@contoso.com, untuk melakukan operasi pada kunci dan rahasia dengan kubah kunci bernama Contoso03Vault.

Perintah kedua mengubah izin yang diberikan ke PattiFuller@contoso.com dalam perintah pertama, untuk sekarang memungkinkan mendapatkan rahasia selain mengatur dan menghapusnya. Izin untuk operasi kunci tetap tidak berubah setelah perintah ini. Parameter *PassThru* menghasilkan objek yang diperbarui yang dikembalikan oleh cmdlet.

Perintah terakhir selanjutnya mengubah izin yang sudah ada untuk PattiFuller@contoso.com menghapus semua izin untuk operasi utama. Izin untuk operasi rahasia tetap tidak berubah setelah perintah ini. Parameter *PassThru* menghasilkan objek yang diperbarui yang dikembalikan oleh cmdlet.

### Contoh 2: Memberikan izin untuk prinsipal layanan aplikasi untuk membaca dan menulis rahasia
```
PS C:\>Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -ServicePrincipalName 'http://payroll.contoso.com' -PermissionsToSecrets Get,Set
```

Perintah ini memberikan izin untuk aplikasi untuk kubah kunci bernama Contoso03Vault.

Parameter *ServicePrincipalName* menentukan aplikasi. Aplikasi harus terdaftar di Azure Active Directory Anda. Nilai parameter *ServicePrincipalName* harus berupa nama prinsipal layanan aplikasi atau ID APLIKASI GUID.

Contoh ini menentukan nama `http://payroll.contoso.com`pokok layanan , dan perintah memberikan izin aplikasi untuk membaca dan menulis rahasia.

### Contoh 3: Memberikan izin untuk aplikasi menggunakan ID objeknya
```
PS C:\>Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -ObjectId 34595082-9346-41b6-8d6b-295a2808b8db -PermissionsToSecrets Get,Set
```

Perintah ini memberikan izin aplikasi untuk membaca dan menulis rahasia.

Contoh ini menentukan aplikasi menggunakan ID objek dari prinsipal layanan aplikasi.

### Contoh 4: Memberikan izin untuk nama prinsipal pengguna
```
PS C:\>Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -UserPrincipalName 'PattiFuller@contoso.com' -PermissionsToSecrets Get,List,Set
```

Perintah ini memberikan izin mendapatkan, mencantumkan, dan mengatur izin untuk nama prinsipal pengguna tertentu untuk akses ke rahasia.

### Contoh 5: Aktifkan rahasia untuk diambil dari kubah kunci oleh penyedia sumber daya Microsoft.Compute
```
PS C:\>Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -EnabledForDeployment
```

Perintah ini memberikan izin bagi rahasia untuk diambil dari kubah kunci Contoso03Vault oleh penyedia sumber daya Microsoft.Compute.

### Contoh 6: Memberikan izin ke grup keamanan
```
PS C:\>Get-AzureRmADGroup
PS C:\> Set-AzureRmKeyVaultAccessPolicy -VaultName 'myownvault' -ObjectId (Get-AzureRmADGroup -SearchString 'group2')[0].Id -PermissionsToKeys All -PermissionsToSecrets All
DisplayName                    Type                           ObjectId
-----------                    ----                           --------
group1                                                        96a0daa6-9841-4a9c-bdeb-e7062276c688
group2                                                        b8a401eb-63ad-4a30-b0e1-a7461969fe54
group3                                                        da07a6be-2c1e-4e42-934d-ceb57cf652b4
```

Perintah pertama menggunakan cmdlet Get-AzureRmADGroup untuk mendapatkan semua grup Direktori Aktif. Dari output, Anda melihat 3 grup yang dikembalikan, bernama **grup1**, **grup2**, dan **grup3**. Beberapa grup bisa memiliki nama yang sama tapi selalu memiliki ObjectId yang unik. Ketika lebih dari satu grup yang memiliki nama yang sama dikembalikan, gunakan ObjectId dalam output untuk mengidentifikasi grup yang ingin Anda gunakan.

Anda kemudian menggunakan output perintah ini dengan Set-AzureRmKeyVaultAccessPolicy untuk memberikan izin ke grup2 untuk kubah kunci Anda, bernama **myownvault**. Contoh ini menghitung grup bernama 'group2' sebaris dalam baris perintah yang sama.

Mungkin ada beberapa grup dalam daftar yang dikembalikan yang bernama 'group2'.
Contoh ini memilih yang pertama, yang ditunjukkan oleh indeks \[0\] dalam daftar yang dikembalikan.

### Contoh 7: Memberikan azure Information Protection akses ke kunci penyewa yang dikelola pelanggan (BYOK)
```
PS C:\>Set-AzureRmKeyVaultAccessPolicy -VaultName 'Contoso04Vault' -ServicePrincipalName 00000012-0000-0000-c000-000000000000 -PermissionsToKeys decrypt,sign,get
```

Perintah ini mengotorisasi Azure Information Protection untuk menggunakan kunci yang dikelola pelanggan (kunci Anda sendiri, atau skenario "BYOK") sebagai kunci penyewa Azure Information Protection.

Ketika menjalankan perintah ini, tentukan nama kubah kunci Anda sendiri, tetapi Anda harus menentukan parameter *ServicePrincipalName* dengan GUID **00000012-0000-0000-c000-000000000000000** dan tentukan izin dalam contoh.

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
Memungkinkan Anda menentukan ID objek tanpa memvalidasi bahwa objek ada dalam Azure Active Directory.

Gunakan parameter ini hanya jika Anda ingin memberikan akses ke kubah kunci ke ID objek yang merujuk ke grup keamanan yang didelegasikan dari penyewa Azure lain.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailAddress
Menentukan alamat email pengguna pengguna yang akan memberikan izin.

Alamat email ini harus ada dalam direktori yang terkait dengan langganan saat ini dan bersifat unik.

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
Memungkinkan penyedia sumber daya Microsoft.Compute untuk mengambil rahasia dari kubah kunci ini ketika kubah kunci ini dirujuk dalam pembuatan sumber daya, misalnya saat membuat mesin virtual.

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
Memungkinkan layanan enkripsi disk Azure untuk mendapatkan rahasia dan menghapus kunci dari kubah kunci ini.

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
Memungkinkan Azure Resource Manager untuk mendapatkan rahasia dari kubah kunci ini ketika kubah kunci ini dirujuk dalam penyebaran templat.

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
Menentukan ID objek dari pengguna atau prinsipal layanan dalam Azure Active Directory untuk memberikan izin.

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
Mengembalikan objek yang mewakili item tempat Anda bekerja.

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
Menentukan array izin sertifikat untuk diberikan kepada pengguna atau prinsipal layanan.

Nilai yang dapat diterima untuk parameter ini:

- Mendapatkan
- Daftar
- Menghapus
- Membuat
- Impor
- Update
- Managecontacts
- Getissuers
- Listissuers
- Pengatur
- Deleteissuers
- Pengelola

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
Menentukan array izin operasi utama untuk diberikan kepada pengguna atau prinsipal layanan.

Nilai yang dapat diterima untuk parameter ini:

- Mendekripsi
- Mengenkripsi
- Batalkan Tombol
- WrapKey
- Memverifikasi
- Tanda
- Mendapatkan
- Daftar
- Update
- Membuat
- Impor
- Menghapus
- Cadangan
- Mengembalikan
- Memulihkan
- Membersihkan

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
Menentukan array izin operasi rahasia untuk diberikan kepada pengguna atau prinsipal layanan.

Nilai yang dapat diterima untuk parameter ini:

- Mendapatkan
- Daftar
- Set
- Menghapus
- Cadangan
- Mengembalikan
- Memulihkan
- Membersihkan

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
Menentukan akun penyimpanan terkelola dan izin operasi definisi SaS untuk diberikan kepada pengguna atau prinsipal layanan.

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
Menentukan nama pokok layanan aplikasi untuk memberikan izin.

Tentukan ID aplikasi, juga dikenal sebagai ID klien, terdaftar untuk aplikasi di AzureActive Directory. Aplikasi dengan nama prinsipal layanan yang ditentukan parameter ini harus didaftarkan di direktori Azure yang berisi langganan Anda saat ini.

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
Menentukan nama utama pengguna pengguna yang akan memberikan izin.

Nama utama pengguna ini harus ada di direktori yang terkait dengan langganan saat ini.

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
Menentukan nama kubah kunci.

Cmdlet ini mengubah kebijakan akses untuk kubah kunci yang ditentukan parameter ini.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String, Guid, String[], Sakelar

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSVault

## CATATAN

## RELATED LINKS

[Get-AzureRmKeyVault](./Get-AzureRmKeyVault.md)

[Hapus-AzureRmKeyVaultAccessPolicy](./Remove-AzureRmKeyVaultAccessPolicy.md)

