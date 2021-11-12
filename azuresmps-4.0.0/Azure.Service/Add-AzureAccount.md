---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 03EAFFB2-EA64-4227-A33B-D24EB4A75F71
online version: ''
schema: 2.0.0
ms.openlocfilehash: d77d3acbc53603663cbe160f01ddd14db3127868
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426569"
---
# Add-AzureAccount

## SYNOPSIS
Menambahkan akun Azure ke Windows PowerShell.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Pengguna (Default)
```
Add-AzureAccount [-Environment <String>] [-Credential <PSCredential>] [-Tenant <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ServicePrincipal
```
Add-AzureAccount [-Environment <String>] -Credential <PSCredential> [-ServicePrincipal] -Tenant <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureAccount** membuat akun Azure dan langganannya tersedia di Windows PowerShell.
Ini seperti masuk ke akun Azure Anda di Windows PowerShell.
Untuk keluar dari akun, gunakan cmdlet **Remove-AzureAccount.**

**Add-AzureAccount** mengunduh informasi tentang akun Azure dan menyimpannya dalam file data langganan di profil pengguna roaming.
Token ini juga mendapatkan token akses yang memungkinkan Windows PowerShell mengakses akun Azure atas nama Anda.
Ketika perintah selesai, Anda dapat mengelola akun Azure di Windows PowerShell.

Ada dua cara berbeda untuk membuat akun Azure Anda tersedia untuk Windows PowerShell.
Anda dapat menggunakan cmdlet **Add-AzureAccount,** yang menggunakan token akses autentikasi Azure Active Directory (Azure AD), atau **Import-AzurePublishSettingsFile,** yang menggunakan sertifikat manajemen.
Untuk panduan tentang metode yang digunakan, lihat [Cara: Koneksi ke langganan Anda](https://azure.microsoft.com/documentation/articles/install-configure-powershell) ( https://azure.microsoft.com/documentation/articles/install-configure-powershell/#Connect) .

Ketika menjalankan **Add-AzureAccount,** jendela interaktif yang meminta Anda untuk masuk ke akun Azure akan ditampilkan.
Proses masuk ini berlaku hingga token akses kedaluwarsa.
Ketika kedaluwarsa, cmdlet yang memerlukan akses ke akun meminta Anda untuk menjalankan **Add-AzureAccount** lagi.

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Tambahkan akun
```
PS C:\> Add-AzureAccount
```

Perintah ini menambahkan akun Azure ke Windows PowerShell.
Saat Anda menjalankan perintah tersebut, jendela akan muncul untuk meminta nama pengguna dan kata sandi akun.

### Contoh 2: Gunakan file data langganan alternatif
```
PS C:\> Add-AzureAccount -SubscriptionDataFile C:\Testing\SDF.xml
```

Perintah ini menggunakan parameter **SubscriptionDataFile** untuk mengarahkan **Add-AzureAccount untuk** menyimpan data akun dalam file C:\Testing\SDF.xml, bukan file default.

## PARAMETERS

### -Credential
```yaml
Type: PSCredential
Parameter Sets: User
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: PSCredential
Parameter Sets: ServicePrincipal
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkungan
Menentukan lingkungan Azure.

Lingkungan Azure, penyebaran independen dari Microsoft Azure, seperti AzureCloud untuk global Azure dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga bisa membuat lingkungan Azure lokal dengan menggunakan Paket Azure dan cmdlet WAPack.
Untuk informasi selengkapnya, lihat [Azure Pack](/previous-versions/azure/windows-server-azure-pack/).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipal
```yaml
Type: SwitchParameter
Parameter Sets: ServicePrincipal
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Penyewa
```yaml
Type: String
Parameter Sets: User
Aliases: TenantId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ServicePrincipal
Aliases: TenantId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Anda tidak dapat pipa input ke cmdlet ini

## OUTPUTS

### Tidak ada
Cmdlet ini tidak mengembalikan output apa pun.

## CATATAN
* **Add-AzureAccount** (dan metode autentikasi Azure AD) diutamakan lebih dari **Impor-AzurePublishSettings** (dan metode sertifikat manajemen). Jika Anda menggunakan **Add-AzureAccount** sekali pun di akun Anda, metode autentikasi Azure AD digunakan dan sertifikat manajemen diabaikan. Untuk menghapus token Azure AD dan memulihkan metode sertifikat manajemen, gunakan cmdlet **Remove-AzureAccount.** Untuk informasi selengkapnya, ketik: **Get-Help Remove-AzureAccount**.
* Kesalahan, "Kredensial Anda telah kedaluwarsa. Gunakan Add-AzureAccount untuk masuk lagi." menunjukkan bahwa token akses Anda telah kedaluwarsa dan Windows PowerShell tidak dapat mengakses akun Azure Anda. Untuk memulihkan akses ke akun Anda, jalankan **kembali Add-AzureAccount.**
* Cmdlet Azure PowerShell dan langganan mendapatkan data mereka dari file data langganan, bukan dari akun Azure langsung. Jika mengubah akun atau langganan di luar Windows PowerShell, seperti menggunakan Portal Manajemen Azure, jalankan **kembali Add-AzureAccount** untuk merefresh file data langganan.

## RELATED LINKS

[Add-AzureEnvironment](./Add-AzureEnvironment.md)

[Get-AzureEnvironment](./Get-AzureEnvironment.md)

[Import-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)

[Get-AzureAccount](./Get-AzureAccount.md)

[Remove-AzureAccount](./Remove-AzureAccount.md)


