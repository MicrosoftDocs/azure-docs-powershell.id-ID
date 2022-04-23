---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 6420CBE1-BF9D-493D-BCA8-E8C6688FAF3B
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9f397038431f1e609082c4e563ff2df3641c711a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143210051"
---
# Get-AzureStorageFileContent

## SYNOPSIS
Mengunduh konten file.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ShareName (Default)
```
Get-AzureStorageFileContent [-ShareName] <String> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-PassThru] [-Force] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Berbagi
```
Get-AzureStorageFileContent [-Share] <CloudFileShare> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-PassThru] [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Direktori
```
Get-AzureStorageFileContent [-Directory] <CloudFileDirectory> [-Path] <String> [[-Destination] <String>]
 [-CheckMd5] [-PassThru] [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### File
```
Get-AzureStorageFileContent [-File] <CloudFile> [[-Destination] <String>] [-CheckMd5] [-PassThru] [-Force]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageFileContent** mengunduh konten file, lalu menyimpannya ke tujuan yang Anda tentukan.
Cmdlet ini tidak mengembalikan konten file.

## EXAMPLES

### Contoh 1: Mengunduh file dari folder
```
PS C:\>Get-AzureStorageFileContent -ShareName "ContosoShare06" -Path "ContosoWorkingFolder/CurrentDataFile"
```

Perintah ini mengunduh file yang bernama CurrentDataFile dalam folder ContosoWorkingFolder dari file berbagi ContosoShare06 ke folder saat ini.

## PARAMETERS

### -CheckMd5
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

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

### -ClientTimeoutPerRequest
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konteks
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

```yaml
Type: IStorageContext
Parameter Sets: ShareName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tujuan
Menentukan jalur tujuan.
Cmdlet ini mengunduh konten file ke lokasi yang ditentukan parameter ini.

Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direktori
Menentukan folder sebagai objek **CloudFileDirectory** .
Cmdlet ini mendapatkan konten untuk file dalam folder yang ditentukan parameter ini.
Untuk mendapatkan direktori, gunakan cmdlet New-AzureStorageDirectory.
Anda juga dapat menggunakan cmdlet Get-AzureStorageFile untuk mendapatkan direktori.

```yaml
Type: CloudFileDirectory
Parameter Sets: Directory
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -File
Menentukan file sebagai objek **CloudFile** .
Cmdlet ini mendapatkan file yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudFile** , gunakan cmdlet Get-AzureStorageFile.

```yaml
Type: CloudFile
Parameter Sets: File
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Paksa
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

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

### -PassThru
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

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

### -Jalur
Menentukan jalur file.
Cmdlet ini mendapatkan konten file yang ditentukan parameter ini.
Jika file tidak ada, cmdlet ini mengembalikan kesalahan.

```yaml
Type: String
Parameter Sets: ShareName, Share, Directory
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten dalam file baru.
Jika Anda menentukan jalur file yang sudah ada dan Anda menentukan parameter *Force* , cmdlet menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan Anda tidak menentukan *Force*, cmdlet akan meminta Anda sebelum melanjutkan.

Jika Anda menentukan jalur folder, cmdlet ini akan mencoba membuat file yang memiliki nama file penyimpanan Azure.

```yaml
Type: Int32
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
Cmdlet ini mengunduh konten file dalam parameter berbagi ini yang ditentukan.
Untuk mendapatkan objek **CloudFileShare** , gunakan cmdlet Get-AzureStorageShare.
Objek ini berisi konteks penyimpanan.
Jika Anda menentukan parameter ini, jangan tentukan parameter *Konteks* .

```yaml
Type: CloudFileShare
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
Cmdlet ini mengunduh konten file dalam parameter berbagi ini yang ditentukan.

```yaml
Type: String
Parameter Sets: ShareName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageFile](./Get-AzureStorageFile.md)

[Set-AzureStorageFileContent](./Set-AzureStorageFileContent.md)


