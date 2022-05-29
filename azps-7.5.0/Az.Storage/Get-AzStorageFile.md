---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 38207027-FD76-45EE-8817-88599735C0B0
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragefile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageFile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageFile.md
ms.openlocfilehash: 6e4b6c05ca84b2df2d1d160fc2df51df623aa46b
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145717318"
---
# Get-AzStorageFile

## SYNOPSIS
Mencantumkan direktori dan file untuk jalur.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/get-azstoragefile) untuk informasi terbaru.

## SYNTAX

### ShareName (Default)
```
Get-AzStorageFile [-ShareName] <String> [[-Path] <String>] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### Bagikan
```
Get-AzStorageFile [-Share] <CloudFileShare> [[-Path] <String>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

### Direktori
```
Get-AzStorageFile [-Directory] <CloudFileDirectory> [[-Path] <String>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageFile** mencantumkan direktori dan file untuk berbagi atau direktori yang Anda tentukan.
Tentukan parameter *Jalur* untuk mendapatkan instans direktori atau file di jalur yang ditentukan.
Cmdlet ini mengembalikan objek **AzureStorageFile** dan **AzureStorageDirectory** .
Anda dapat menggunakan properti **IsDirectory** untuk membedakan antara folder dan file.

## EXAMPLES

### Contoh 1: Mencantumkan direktori dalam berbagi
```
PS C:\>Get-AzStorageFile -ShareName "ContosoShare06" | where {$_.GetType().Name -eq "AzureStorageFileDirectory"}
```

Perintah ini hanya mencantumkan direktori di berbagi ContosoShare06.
Ini pertama-tama mengambil file dan direktori, meneruskannya ke operator **tempat** dengan menggunakan operator alur, lalu membuang objek apa pun yang jenisnya bukan "AzureStorageFileDirectory".

### Contoh 2: Mencantumkan Direktori File
```
PS C:\> Get-AzStorageFile -ShareName "ContosoShare06" -Path "ContosoWorkingFolder" | Get-AzStorageFile
```

Perintah ini mencantumkan file dan folder di direktori ContosoWorkingFolder di bawah berbagi ContosoShare06.
Ini pertama-tama mendapatkan instans direktori, dan kemudian menyalurkannya ke cmdlet **Get-AzStorageFile** untuk mencantumkan direktori.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu habis sisi klien, dalam detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba kembali permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini mengembalikan kesalahan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ClientTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Menentukan panggilan jaringan bersamaan maksimum.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi untuk membatasi penggunaan CPU dan bandwidth lokal dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah jumlah absolut dan tidak dikalikan dengan jumlah inti.
Parameter ini dapat membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth rendah, seperti 100 kilobit per detik.
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

### -Context
Menentukan konteks Azure Storage.
Untuk mendapatkan konteks Storage, gunakan cmdlet New-AzStorageContext.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
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
Untuk mendapatkan direktori, gunakan cmdlet New-AzStorageDirectory.
Anda juga dapat menggunakan cmdlet **Get-AzStorageFile** untuk mendapatkan direktori.

```yaml
Type: Microsoft.Azure.Storage.File.CloudFileDirectory
Parameter Sets: Directory
Aliases: CloudFileDirectory

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur folder.
Jika Anda menghilangkan parameter *Jalur* , **Get-AzStorageFile mencantumkan** direktori dan file dalam berbagi atau direktori yang ditentukan.
Jika Anda menyertakan parameter *Jalur* , **Get-AzStorageFile** mengembalikan instans direktori atau file di jalur yang ditentukan.

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
Menentukan interval batas waktu sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan Storage mengembalikan kesalahan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ServerTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bagikan
Menentukan objek **CloudFileShare** .
Cmdlet ini mendapatkan file atau direktori dari berbagi file yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudFileShare** , gunakan cmdlet Get-AzStorageShare.
Objek ini berisi konteks Storage.
Jika Anda menentukan parameter ini, jangan tentukan parameter *Konteks* .

```yaml
Type: Microsoft.Azure.Storage.File.CloudFileShare
Parameter Sets: Share
Aliases: CloudFileShare

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ShareName
Menentukan nama berbagi file.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure. Storage. File.CloudFileShare

### Microsoft.Azure. Storage. File.CloudFileDirectory

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageFile

## NOTES

## RELATED LINKS

[Get-AzStorageFileContent](./Get-AzStorageFileContent.md)

[New-AzStorageDirectory](./New-AzStorageDirectory.md)

[Remove-AzStorageDirectory](./Remove-AzStorageDirectory.md)

[Remove-AzStorageFile](./Remove-AzStorageFile.md)

[Set-AzStorageFileContent](./Set-AzStorageFileContent.md)


