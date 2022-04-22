---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 03EAFFB2-EA64-4227-A33B-D24EB4A75F71
online version: ''
schema: 2.0.0
ms.openlocfilehash: d77d3acbc53603663cbe160f01ddd14db3127868
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143044595"
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
Cmdlet **Add-AzureAccount** membuat akun Azure Anda dan langganannya tersedia di Windows PowerShell.
Ini seperti masuk ke akun Azure Anda di Windows PowerShell.
Untuk keluar dari akun, gunakan cmdlet **Hapus-AzureAccount** .

**Add-AzureAccount** mengunduh informasi tentang akun Azure Anda dan menyimpannya dalam file data langganan di profil pengguna jelajah Anda.
Ini juga mendapatkan token akses yang memungkinkan Windows PowerShell mengakses akun Azure Anda atas nama Anda.
Setelah perintah selesai, Anda dapat mengelola akun Azure di Windows PowerShell.

Ada dua cara berbeda untuk membuat akun Azure Anda tersedia untuk Windows PowerShell.
Anda dapat menggunakan cmdlet **Add-AzureAccount**, yang menggunakan Azure Active Directory (Azure AD) token akses autentikasi, atau **Import-AzurePublishSettingsFile**, yang menggunakan sertifikat manajemen.
Untuk panduan tentang metode mana yang digunakan, lihat [Cara: Koneksi langganan Anda](https://azure.microsoft.com/documentation/articles/install-configure-powershell) (https://azure.microsoft.com/documentation/articles/install-configure-powershell/#Connect).

Saat Anda menjalankan **Add-AzureAccount**, jendela interaktif akan menampilkan jendela interaktif yang meminta Anda untuk masuk ke akun Azure.
Proses masuk ini berlaku hingga token akses kedaluwarsa.
Ketika kedaluwarsa, cmdlet yang memerlukan akses ke akun meminta Anda untuk menjalankan **Add-AzureAccount** lagi.

Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

## EXAMPLES

### Contoh 1: Menambahkan akun
```
PS C:\> Add-AzureAccount
```

Perintah ini menambahkan akun Azure ke Windows PowerShell.
Saat Anda menjalankan perintah, jendela muncul untuk meminta nama pengguna dan kata sandi akun tersebut.

### Contoh 2: Menggunakan file data langganan alternatif
```
PS C:\> Add-AzureAccount -SubscriptionDataFile C:\Testing\SDF.xml
```

Perintah ini menggunakan parameter **SubscriptionDataFile** untuk mengarahkan **Add-AzureAccount** untuk menyimpan data akun dalam file C:\Testing\SDF.xml, bukan file default.

## PARAMETERS

### -Kredensial
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

Lingkungan Azure merupakan penyebaran independen Microsoft Azure, seperti AzureCloud untuk Azure global dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga dapat membuat lingkungan Azure lokal dengan menggunakan cmdlet Azure Pack dan WAPack.
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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda tidak dapat menyalurkan input ke cmdlet ini

## OUTPUTS

### Tidak
Cmdlet ini tidak mengembalikan output apa pun.

## NOTES
* **Add-AzureAccount** (dan metode autentikasi Azure AD) lebih diutamakan daripada **Import-AzurePublishSettings** (dan metode sertifikat manajemen). Jika Anda menggunakan **Add-AzureAccount** bahkan sekali di akun Anda, metode autentikasi Azure AD digunakan dan sertifikat manajemen diabaikan. Untuk menghapus token Azure AD dan memulihkan metode sertifikat manajemen, gunakan cmdlet **Hapus-AzureAccount**. Untuk informasi selengkapnya, ketik: **Dapatkan Bantuan Hapus-AzureAccount**.
* Kesalahan, "Kredensial Anda telah kedaluwarsa. Silakan gunakan Add-AzureAccount untuk masuk lagi." menunjukkan bahwa token akses Anda telah kedaluwarsa dan Windows PowerShell tidak dapat mengakses akun Azure Anda. Untuk memulihkan akses ke akun Anda, jalankan kembali **Add-AzureAccount** .
* Cmdlet langganan dan akun Azure PowerShell mendapatkan data mereka dari file data langganan, bukan dari akun Azure langsung. Jika Anda mengubah akun atau langganan di luar Windows PowerShell, seperti menggunakan Portal Manajemen Azure, jalankan kembali **Add-AzureAccount** untuk merefresh file data langganan.

## RELATED LINKS

[Add-AzureEnvironment](./Add-AzureEnvironment.md)

[Get-AzureEnvironment](./Get-AzureEnvironment.md)

[Impor-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)

[Dapatkan-AzureAccount](./Get-AzureAccount.md)

[Hapus-AzureAccount](./Remove-AzureAccount.md)


