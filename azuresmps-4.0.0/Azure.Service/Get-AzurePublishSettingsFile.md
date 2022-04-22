---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: A5419F76-B85E-445D-84EA-CC695B175C8D
online version: ''
schema: 2.0.0
ms.openlocfilehash: e84df3f81d0d27e40bd9d041fa0503ebbcb72fe3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142981631"
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
Setelah perintah selesai, Anda dapat menggunakan cmdlet **Import-PublishSettingsFile** untuk membuat pengaturan dalam file tersedia untuk Windows PowerShell.

Agar akun Azure tersedia untuk Windows PowerShell, Anda dapat menggunakan file pengaturan penerbitan atau cmdlet **Add-AzureAccount**.
Terbitkan file pengaturan memungkinkan Anda mempersiapkan sesi terlebih dahulu sehingga Anda bisa menjalankan skrip dan pekerjaan latar belakang tanpa dijaga.
Namun, tidak semua layanan mendukung penerbitan file pengaturan.
Misalnya, modul **AzureResourceManager** tidak mendukung penerbitan file pengaturan.

Saat Anda menjalankan **Get-AzurePublishSettingsFile**, aplikasi akan membuka browser default dan meminta Anda masuk ke akun Azure, memilih langganan, dan memilih lokasi sistem file untuk file pengaturan penerbitan.
Lalu, file ini mengunduh file pengaturan penerbitan untuk langganan Anda ke dalam file yang Anda pilih.

"menerbitkan file pengaturan" adalah file XML dengan ekstensi nama file .publishsettings.
File berisi sertifikat berkode yang menyediakan kredensial manajemen untuk langganan Azure Anda.

**Catatan Keamanan:** Terbitkan file pengaturan berisi kredensial yang digunakan untuk mengelola langganan dan layanan Azure Anda.
Jika pengguna berbahaya mengakses file pengaturan penerbitan, mereka dapat mengedit, membuat, dan menghapus layanan Azure Anda.
Sebagai praktik terbaik keamanan, simpan file ke lokasi di folder Unduhan atau Dokumen, lalu hapus setelah menggunakan cmdlet **Impor-AzurePublishSettingsFile** untuk mengimpor pengaturan.

Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

## EXAMPLES

### Contoh 1: Mengunduh file pengaturan penerbitan
```
PS C:\> Get-AzurePublishSettingsFile
```

Perintah ini membuka browser default Anda, tersambung ke akun Azure Windows Anda, lalu mengunduh file .publishsettings untuk akun Anda.

### Contoh 2: Tentukan realm
```
PS C:\> Get-AzurePublishSettingsFile -Realm contoso.com -Passthru
```

Perintah ini mengunduh file pengaturan penerbitan untuk akun di domain contoso.com.
Gunakan perintah dengan parameter **Realm** saat Anda masuk ke Azure dengan akun organisasi, bukan akun Microsoft.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan $True jika perintah berhasil dan $False jika gagal.
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

### -Realm
Menentukan organisasi dalam ID organisasi.
Misalnya, jika Anda masuk ke Azure sebagai admin@contoso.com, nilai parameter **Realm** contoso.com.
Gunakan parameter ini saat Anda menggunakan ID organisasi untuk masuk ke portal Azure.
Parameter ini tidak diperlukan saat Anda menggunakan akun Microsoft, seperti akun outlook.com atau live.com.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda dapat menyalurkan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak ada atau System.Boolean
Saat Anda menggunakan parameter *PassThru* , cmdlet ini mengembalikan nilai Boolean.
Jika tidak, cmdlet ini tidak mengembalikan output apa pun

## NOTES

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Impor-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)


