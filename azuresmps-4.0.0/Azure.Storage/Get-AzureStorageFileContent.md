---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 6420CBE1-BF9D-493D-BCA8-E8C6688FAF3B
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9f397038431f1e609082c4e563ff2df3641c711a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423562"
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

### Bagikan
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

Perintah ini mengunduh file yang bernama CurrentDataFile dalam folder ContosoWorkingFolder dari file bersama ContosoShare06 ke folder saat ini.

## PARAMETERS

### -CheckMd5
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Cmdlet ini mengunduh konten file ke lokasi yang ditentukan oleh parameter ini.

Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Menentukan folder sebagai objek **CloudFileDirectory.**
Cmdlet ini mendapatkan konten untuk file dalam folder yang ditentukan parameter ini.
Untuk mendapatkan direktori, gunakan cmdlet New-AzureStorageDirectory.
Anda juga dapat menggunakan cmdlet Get-AzureStorageFile cmdlet untuk mendapatkan direktori.

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
Menentukan file sebagai objek **CloudFile.**
Cmdlet ini mendapatkan file yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudFile,** gunakan cmdlet Get-AzureStorageFile.

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

### -Force
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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

### -Path
Menentukan jalur file.
Cmdlet ini akan mendapatkan konten file yang ditentukan parameter ini.
Jika file tidak ada, cmdlet ini akan mengembalikan kesalahan.

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
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.

Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Menentukan objek **CloudFileShare.**
Cmdlet ini mengunduh konten file dalam fitur bagikan parameter ini.
Untuk mendapatkan objek **CloudFileShare,** gunakan cmdlet Get-AzureStorageShare baru.
Objek ini berisi konteks penyimpanan.
Jika Anda menentukan parameter ini, jangan tentukan parameter *Konteks.*

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
Menentukan nama berbagi file.
Cmdlet ini mengunduh konten file dalam fitur bagikan parameter ini.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureStorageFile](./Get-AzureStorageFile.md)

[Set-AzureStorageFileContent](./Set-AzureStorageFileContent.md)


