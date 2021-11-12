---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: A5419F76-B85E-445D-84EA-CC695B175C8D
online version: ''
schema: 2.0.0
ms.openlocfilehash: e84df3f81d0d27e40bd9d041fa0503ebbcb72fe3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421156"
---
# Get-AzurePublishSettingsFile

## SYNOPSIS
Mengunduh file pengaturan penerbitan untuk langganan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzurePublishSettingsFile [-Environment <String>] [-Realm <String>] [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzurePublishSettingsFile** mengunduh file pengaturan penerbitan untuk langganan di akun Anda.
Setelah perintah selesai, Anda dapat menggunakan cmdlet **Import-PublishSettingsFile** agar pengaturan dalam file tersedia untuk Windows PowerShell.

Agar akun Azure tersedia untuk Windows PowerShell, Anda dapat menggunakan file pengaturan penerbitan atau cmdlet **Add-AzureAccount.**
Terbitkan file pengaturan memungkinkan Anda mempersiapkan sesi sebelumnya sehingga Anda bisa menjalankan skrip dan pekerjaan latar belakang tanpa dikelola.
Namun, tidak semua layanan mendukung penerbitan file pengaturan.
Misalnya, modul **AzureResourceManager** tidak mendukung penerbitan file pengaturan.

Ketika menjalankan **Get-AzurePublishSettingsFile**, program akan membuka browser default dan meminta Anda masuk ke akun Azure, memilih langganan, lalu memilih lokasi sistem file untuk menerbitkan file pengaturan.
Kemudian, file pengaturan penerbitan akan diunduh ke file yang Anda pilih untuk langganan Anda.

"terbitkan file pengaturan" adalah file XML dengan ekstensi nama file .publishsettings.
File berisi sertifikat berkode yang menyediakan kredensial manajemen untuk langganan Azure Anda.

**Catatan Keamanan:** Menerbitkan file pengaturan berisi kredensial yang digunakan untuk mengelola langganan dan layanan Azure Anda.
Jika pengguna jahat mengakses file pengaturan penerbitan Anda, mereka dapat mengedit, membuat, dan menghapus layanan Azure Anda.
Sebagai praktik terbaik keamanan, simpan file ke lokasi dalam folder Unduhan atau Dokumen Anda lalu hapus setelah menggunakan cmdlet **Import-AzurePublishSettingsFile** untuk mengimpor pengaturan.

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Unduh file pengaturan penerbitan
```
PS C:\> Get-AzurePublishSettingsFile
```

Perintah ini akan membuka browser default Anda, tersambung ke Windows Azure, lalu mengunduh file .publishsettings untuk akun Anda.

### Contoh 2: Menentukan realm
```
PS C:\> Get-AzurePublishSettingsFile -Realm contoso.com -Passthru
```

Perintah ini mengunduh file pengaturan penerbitan untuk akun di contoso.com domain.
Gunakan perintah dengan parameter **Realm** saat Anda masuk ke Azure dengan akun organisasi, bukan akun Microsoft.

## PARAMETERS

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan $True jika perintah berhasil $False jika gagal.
Secara default, cmdlet ini tidak mengembalikan output apa pun.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Realm
Menentukan organisasi dalam ID organisasi.
Misalnya, jika Anda masuk ke Azure admin@contoso.com sebagai, nilai parameter **Realm** adalah contoso.com.
Gunakan parameter ini ketika Anda menggunakan ID organisasi untuk masuk ke portal Azure.
Parameter ini tidak diperlukan ketika Anda menggunakan akun Microsoft, seperti akun outlook.com live.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### Tidak Ada atau System.Boolean
Ketika Anda menggunakan parameter *PassThru,* cmdlet ini mengembalikan nilai Boolean.
Jika tidak, cmdlet ini tidak akan mengembalikan output apa pun

## CATATAN

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Import-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)


