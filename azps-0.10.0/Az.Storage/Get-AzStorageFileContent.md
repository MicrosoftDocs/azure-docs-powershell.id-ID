---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 6420CBE1-BF9D-493D-BCA8-E8C6688FAF3B
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/get-azstoragefilecontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Get-AzStorageFileContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Get-AzStorageFileContent.md
ms.openlocfilehash: aa1c7cebbcb6fe24b06638644d19b07c83c2ff04
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426947"
---
# Get-AzStorageFileContent

## SYNOPSIS
Mengunduh konten file.

## SYNTAX

### ShareName (Default)
```
Get-AzStorageFileContent [-ShareName] <String> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-PassThru] [-Force] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Bagikan
```
Get-AzStorageFileContent [-Share] <CloudFileShare> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-PassThru] [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Direktori
```
Get-AzStorageFileContent [-Directory] <CloudFileDirectory> [-Path] <String> [[-Destination] <String>]
 [-CheckMd5] [-PassThru] [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### File
```
Get-AzStorageFileContent [-File] <CloudFile> [[-Destination] <String>] [-CheckMd5] [-PassThru] [-Force]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageFileContent** mengunduh konten file, lalu menyimpannya ke tujuan yang Anda tentukan.
Cmdlet ini tidak mengembalikan konten file.

## EXAMPLES

### Contoh 1: Mengunduh file dari folder
```
PS C:\>Get-AzStorageFileContent -ShareName "ContosoShare06" -Path "ContosoWorkingFolder/CurrentDataFile"
```

Perintah ini mengunduh file yang bernama CurrentDataFile dalam folder ContosoWorkingFolder dari file bersama ContosoShare06 ke folder saat ini.

### Contoh 2: Mengunduh file di bawah sampel berbagi file
```
PS C:\>Get-AzStorageFile -ShareName sample | ? {$_.GetType().Name -eq "CloudFile"} | Get-AzStorageFileContent
```

Contoh ini mengunduh file di bawah sampel berbagi file

## PARAMETERS

### -CheckMd5
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.
Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.
Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.
Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

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

### -Tujuan
Menentukan jalur tujuan.
Cmdlet ini mengunduh konten file ke lokasi yang ditentukan oleh parameter ini.
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa,* cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa,* cmdlet akan meminta Anda sebelum melanjutkannya.
Jika Anda menentukan jalur folder, cmdlet ini akan berusaha membuat file yang memiliki nama file penyimpanan Azure.

```yaml
Type: System.String
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
Untuk mendapatkan direktori, gunakan cmdlet New-AzStorageDirectory.
Anda juga dapat menggunakan cmdlet Get-AzStorageFile cmdlet untuk mendapatkan direktori.

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

### -File
Menentukan file sebagai objek **CloudFile.**
Cmdlet ini mendapatkan file yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudFile,** gunakan cmdlet Get-AzStorageFile.

```yaml
Type: Microsoft.WindowsAzure.Storage.File.CloudFile
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.String
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
Menentukan objek **CloudFileShare.**
Cmdlet ini mengunduh konten file dalam fitur bagikan parameter ini.
Untuk mendapatkan objek **CloudFileShare,** gunakan cmdlet Get-AzStorageShare.
Objek ini berisi konteks penyimpanan.
Jika Anda menentukan parameter ini, jangan tentukan parameter *Konteks.*

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
Menentukan nama berbagi file.
Cmdlet ini mengunduh konten file dalam fitur bagikan parameter ini.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAz. Storage. File.CloudFileShare
Parameter: Berbagi (ByValue)

### Microsoft.WindowsAz. Storage. File.CloudFileDirectory
Parameter: Direktori (ByValue)

### Microsoft.WindowsAz. Storage. File.CloudFile
Parameter: File (ByValue)

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAz. Storage. File.CloudFile

## CATATAN

## RELATED LINKS

[Get-AzStorageFile](./Get-AzStorageFile.md)

[Set-AzStorageFileContent](./Set-AzStorageFileContent.md)


