---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: 38207027-FD76-45EE-8817-88599735C0B0
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/get-azurestoragefile
schema: 2.0.0
ms.openlocfilehash: fac810fe1c58a7be18204f51b0f124a490196edc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142862240"
---
# Get-AzureStorageFile

## SYNOPSIS
Mencantumkan direktori dan file untuk jalur.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ShareName (Default)
```
Get-AzureStorageFile [-ShareName] <String> [[-Path] <String>] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### Berbagi
```
Get-AzureStorageFile [-Share] <CloudFileShare> [[-Path] <String>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

### Direktori
```
Get-AzureStorageFile [-Directory] <CloudFileDirectory> [[-Path] <String>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageFile** mencantumkan direktori dan file untuk berbagi atau direktori yang Anda tentukan.
Tentukan parameter *Jalur* untuk mendapatkan contoh direktori atau file dalam jalur yang ditentukan.
Cmdlet ini mengembalikan objek **AzureStorageFile** dan **AzureStorageDirectory** .
Anda dapat menggunakan properti **IsDirectory** untuk membedakan antara folder dan file.

## EXAMPLES

### Contoh 1: Daftar direktori dalam berbagi
```
PS C:\>Get-AzureStorageFile -ShareName "ContosoShare06" | where {$_.GetType().Name -eq "CloudFileDirectory"}
```

Perintah ini hanya mencantumkan direktori dalam ContosoShare06.
Ini pertama mengambil file dan direktori, meneruskannya ke operator **tempat** dengan menggunakan operator pipeline, lalu membuang objek apa pun yang tipenya bukan "CloudFileDirectory".

### Contoh 2: Mencantumkan Direktori File
```
PS C:\> Get-AzureStorageFile -ShareName "ContosoShare06" -Path "ContosoWorkingFolder" | Get-AzureStorageFile
```

Perintah ini mencantumkan file dan folder dalam direktori ContosoWorkingFolder di bawah berbagi ContosoShare06.
Ini pertama mendapatkan instans direktori, lalu menyalurkannya ke cmdlet **Get-AzureStorageFile** untuk mencantumkan direktori.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval batas waktu sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini akan mencoba kembali permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini mengembalikan kesalahan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Menentukan maksimum panggilan jaringan serentak.
Anda bisa menggunakan parameter ini untuk membatasi konkurensi untuk membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini dapat membantu mengurangi masalah koneksi jaringan dalam lingkungan bandwidth rendah, seperti 100 kilobit per detik.
Nilai defaultnya adalah 10.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konteks
Menentukan konteks Azure Storage.
Untuk mendapatkan konteks Storage, gunakan cmdlet New-AzureStorageContext.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: ShareName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direktori
Menentukan folder sebagai objek **CloudFileDirectory** .
Cmdlet ini mendapatkan folder yang ditentukan parameter ini.
Untuk mendapatkan direktori, gunakan cmdlet New-AzureStorageDirectory.
Anda juga dapat menggunakan cmdlet **Get-AzureStorageFile** untuk mendapatkan direktori.

```yaml
Type: Microsoft.WindowsAzure.Storage.File.CloudFileDirectory
Parameter Sets: Directory
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur folder.
Jika Anda menghilangkan parameter *Jalur* , **Get-AzureStorageFile mencantumkan** direktori dan file dalam berbagi file atau direktori tertentu.
Jika Anda menyertakan parameter *Jalur* , **Get-AzureStorageFile** mengembalikan contoh direktori atau file dalam jalur yang ditentukan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan interval waktu habis sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan Storage mengembalikan kesalahan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bagikan
Menentukan objek **CloudFileShare** .
Cmdlet ini mendapatkan file atau direktori dari berbagi file yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudFileShare** , gunakan cmdlet Get-AzureStorageShare.
Objek ini berisi konteks Storage.
Jika Anda menentukan parameter ini, jangan tentukan parameter *Konteks* .

```yaml
Type: Microsoft.WindowsAzure.Storage.File.CloudFileShare
Parameter Sets: Share
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ShareName
Menentukan nama file yang dibagikan.
Cmdlet ini mendapatkan file atau direktori dari berbagi file yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: ShareName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure. Storage. File.CloudFileShare
Parameter: Bagikan (ByValue)

### Microsoft.WindowsAzure. Storage. File.CloudFileDirectory
Parameter: Direktori (ByValue)

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure. Storage. File.CloudFile

## NOTES

## RELATED LINKS

[Get-AzureStorageFileContent](./Get-AzureStorageFileContent.md)

[AzureStorageDirectory baru](./New-AzureStorageDirectory.md)

[Hapus-AzureStorageDirectory](./Remove-AzureStorageDirectory.md)

[Hapus-AzureStorageFile](./Remove-AzureStorageFile.md)

[Set-AzureStorageFileContent](./Set-AzureStorageFileContent.md)


