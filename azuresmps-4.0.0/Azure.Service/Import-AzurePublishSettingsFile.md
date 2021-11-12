---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 79D64D7C-6671-4F03-8776-70A716F36512
online version: ''
schema: 2.0.0
ms.openlocfilehash: f71a9972dca0fcb0c6d2b364a0687ca2d35da9d5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422924"
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
Cmdlet **Import-AzurePublishSettingsFile** mengimpor file pengaturan penerbitan (*.publishsettings) yang berisi informasi tentang akun Azure dan menyimpan file data langganan di komputer Anda.
Setelah cmdlet selesai, Anda dapat mengelola akun Azure di Windows PowerShell.

Sebelum menjalankan **Import-AzurePublishSettingsFile,** jalankan **Get-AzurePublishSettingsFile**, yang akan mengunduh dan menyimpan file pengaturan penerbitan sehingga Anda dapat mengimpornya.

Agar akun Azure tersedia untuk Windows PowerShell baru, Anda dapat menggunakan file pengaturan penerbitan atau cmdlet **Add-AzureAccount.**
Terbitkan file pengaturan memungkinkan Anda mempersiapkan sesi sebelumnya sehingga Anda bisa menjalankan skrip dan pekerjaan latar belakang tanpa dikelola.
Namun, tidak semua layanan mendukung penerbitan file pengaturan.
Misalnya, modul **AzureResourceManager** tidak mendukung penerbitan file pengaturan.

**Catatan Keamanan:** Menerbitkan file pengaturan berisi sertifikat manajemen yang dikodekan, tapi tidak dienkripsi.
Jika pengguna jahat mengakses file pengaturan penerbitan Anda, mereka mungkin dapat mengedit, membuat, dan menghapus layanan Azure Anda.
Sebagai praktik terbaik keamanan, simpan file ke lokasi dalam folder Unduhan atau Dokumen Anda lalu hapus setelah menggunakan cmdlet **Import-AzurePublishSettingsFile** untuk mengimpor pengaturan.

## EXAMPLES

### Contoh 1: Mengimpor file
```
PS C:\> Import-AzurePublishSettingsFile -PublishSettingsFile C:\Temp\MyAccount.publishsettings
```

Perintah ini mengimpor file "C:\Temp\MyAccount.publishsettings".

## PARAMETERS

### -Lingkungan
Menentukan lingkungan Azure.

Lingkungan Azure, penyebaran independen dari Microsoft Azure, seperti AzureCloud untuk global Azure dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga bisa membuat lingkungan Azure lokal dengan menggunakan Paket Azure dan cmdlet WAPack.
Untuk informasi selengkapnya, lihat [Paket Azure.](/previous-versions/azure/windows-server-azure-pack/)

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Anda dapat pipa input ke cmdlet ini berdasarkan nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak ada
Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN
* "terbitkan file pengaturan" adalah file XML dengan ekstensi nama file .publishsettings. File berisi sertifikat berkode yang menyediakan kredensial manajemen untuk langganan Azure Anda. Setelah Anda mengimpor file ini, hapus file tersebut untuk menghindari risiko keamanan.
* "File data langganan" adalah file XML yang bisa disimpan di komputer Anda dengan aman. Secara default, data tersimpan di profil pengguna roaming (data $home/AppData/Roaming).

## RELATED LINKS

[Cara Menginstal dan Mengonfigurasi Azure PowerShell](https://azure.microsoft.com/documentation/articles/install-configure-powershell/)

[Add-AzureAccount](./Add-AzureAccount.md)

[Get-AzurePublishSettingsFile](./Get-AzurePublishSettingsFile.md)


