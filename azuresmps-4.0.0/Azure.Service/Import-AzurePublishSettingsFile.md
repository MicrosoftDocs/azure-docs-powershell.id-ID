---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 79D64D7C-6671-4F03-8776-70A716F36512
online version: ''
schema: 2.0.0
ms.openlocfilehash: f71a9972dca0fcb0c6d2b364a0687ca2d35da9d5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142094571"
---
# Import-AzurePublishSettingsFile

## SYNOPSIS
Mengimpor file pengaturan penerbitan yang memungkinkan Anda mengelola akun Azure di Windows PowerShell.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Import-AzurePublishSettingsFile -PublishSettingsFile <String> [-Environment <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Impor-AzurePublishSettingsFile** mengimpor file pengaturan penerbitan (*.publishsettings) yang berisi informasi tentang akun Azure Anda dan menyimpan file data langganan di komputer Anda.
Setelah cmdlet selesai, Anda dapat mengelola akun Azure di Windows PowerShell.

Sebelum menjalankan **Impor-AzurePublishSettingsFile**, jalankan **Get-AzurePublishSettingsFile**, yang mengunduh dan menyimpan file pengaturan penerbitan sehingga Anda dapat mengimpornya.

Agar akun Azure tersedia untuk Windows PowerShell, Anda dapat menggunakan file pengaturan penerbitan atau cmdlet **Add-AzureAccount**.
Terbitkan file pengaturan memungkinkan Anda mempersiapkan sesi terlebih dahulu sehingga Anda bisa menjalankan skrip dan pekerjaan latar belakang tanpa dijaga.
Namun, tidak semua layanan mendukung penerbitan file pengaturan.
Misalnya, modul **AzureResourceManager** tidak mendukung penerbitan file pengaturan.

**Catatan Keamanan:** Terbitkan file pengaturan berisi sertifikat manajemen yang dikodekan, tetapi tidak dienkripsi.
Jika pengguna jahat mengakses file pengaturan penerbitan Anda, mereka mungkin dapat mengedit, membuat, dan menghapus layanan Azure Anda.
Sebagai praktik terbaik keamanan, simpan file ke lokasi di folder Unduhan atau Dokumen, lalu hapus setelah menggunakan cmdlet **Impor-AzurePublishSettingsFile** untuk mengimpor pengaturan.

## EXAMPLES

### Contoh 1: Mengimpor file
```
PS C:\> Import-AzurePublishSettingsFile -PublishSettingsFile C:\Temp\MyAccount.publishsettings
```

Perintah ini mengimpor file "C:\Temp\MyAccount.publishsettings".

## PARAMETERS

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

### -PublishSettingsFile
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda dapat menyalurkan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak
Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN
* "menerbitkan file pengaturan" adalah file XML dengan ekstensi nama file .publishsettings. File berisi sertifikat berkode yang menyediakan kredensial manajemen untuk langganan Azure Anda. Setelah mengimpor file ini, hapus file tersebut untuk menghindari risiko keamanan.
* "File data langganan" adalah file XML yang dapat disimpan di komputer Anda dengan aman. Secara default, file disimpan di profil pengguna jelajah Anda ($home/AppData/Roaming).

## RELATED LINKS

[Cara Menginstal dan Mengonfigurasi Azure PowerShell](https://azure.microsoft.com/documentation/articles/install-configure-powershell/)

[Add-AzureAccount](./Add-AzureAccount.md)

[Get-AzurePublishSettingsFile](./Get-AzurePublishSettingsFile.md)


