---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 6420CBE1-BF9D-493D-BCA8-E8C6688FAF3B
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragefilecontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageFileContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageFileContent.md
ms.openlocfilehash: 917e8e67c28e9b2ba4206f87482a47c6451f76bb
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140553849"
---
# Get-AzStorageFileContent

## SYNOPSIS
Mengunduh konten file.

## SYNTAX

### ShareName (Default)
```
Get-AzStorageFileContent [-ShareName] <String> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-PassThru] [-Force] [-AsJob] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [-PreserveSMBAttribute] [<CommonParameters>]
```

### Bagikan
```
Get-AzStorageFileContent [-Share] <CloudFileShare> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-PassThru] [-Force] [-AsJob] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [-PreserveSMBAttribute] [<CommonParameters>]
```

### Direktori
```
Get-AzStorageFileContent [-Directory] <CloudFileDirectory> [-Path] <String> [[-Destination] <String>]
 [-CheckMd5] [-PassThru] [-Force] [-AsJob] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [-PreserveSMBAttribute] [<CommonParameters>]
```

### File
```
Get-AzStorageFileContent [-File] <CloudFile> [[-Destination] <String>] [-CheckMd5] [-PassThru] [-Force]
 [-AsJob] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [-PreserveSMBAttribute] [<CommonParameters>]
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

### Contoh 3: Unduh file Azure ke file lokal, dan serve properti SMB Azure File (File Attributtes, File Creation Time, File Last Write Time) dalam file lokal.
```
PS C:\>Get-AzStorageFileContent -ShareName sample -Path "dir1/file1" -Destination $localFilePath -PreserveSMBAttribute
```

Contoh ini mengunduh file Azure ke file lokal, dan menghemat properti SMB Azure File (File Attributtes, File Creation Time, File Last Write Time) di file lokal.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang.

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

### -CheckMd5
Menentukan apakah akan memeriksa jumlah Md5 untuk file yang diunduh.

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
Menentukan interval waktu yang habis di sisi klien, dalam hitungan detik, untuk satu permintaan layanan. Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba permintaan. Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini akan mengembalikan kesalahan.

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
Menentukan jumlah maksimum panggilan jaringan bersama. Anda dapat menggunakan parameter ini untuk membatasi konkurensi guna membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan. Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti. Parameter ini bisa membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth yang rendah, seperti 100 kilobit per detik. Nilai default adalah 10.

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
Menentukan Azure Storage konteks. Untuk mendapatkan konteks, gunakan cmdlet New-AzStorageContext cmdlet.

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
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa* , cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa*, cmdlet akan meminta Anda sebelum melanjutkannya.
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
Menentukan folder sebagai objek **CloudFileDirectory** .
Cmdlet ini mendapatkan konten untuk file dalam folder yang ditentukan parameter ini.
Untuk mendapatkan direktori, gunakan cmdlet New-AzStorageDirectory cmdlet.
Anda juga dapat menggunakan cmdlet Get-AzStorageFile untuk mendapatkan direktori.

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

### -File
Menentukan file sebagai objek **CloudFile** .
Cmdlet ini mendapatkan file yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudFile** , gunakan cmdlet Get-AzStorageFile.

```yaml
Type: Microsoft.Azure.Storage.File.CloudFile
Parameter Sets: File
Aliases: CloudFile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini akan membuat file tersebut, dan menyimpan konten di file baru.
Jika menentukan jalur file yang sudah ada dan menentukan parameter *Paksa* , cmdlet akan menimpa file.
Jika Anda menentukan jalur file yang sudah ada dan tidak menentukan *Paksa*, cmdlet akan meminta Anda sebelum melanjutkannya.
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
Menunjukkan bahwa cmdlet ini mengembalikan objek **AzureStorageFile** yang diunduhnya.

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

### -PreserveSMBAttribute
Pertahankan properti SMB File sumber (File Attributtes, Waktu Pembuatan File, Waktu Penulisan Terakhir File) di File tujuan. Parameter ini hanya tersedia pada Windows.

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

### -ServerTimeoutPerRequest
Menentukan interval waktu habis di sisi layanan, dalam detik, untuk permintaan. Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan penyimpanan mengembalikan kesalahan.

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
Cmdlet ini mengunduh konten file dalam fitur bagikan parameter ini.
Untuk mendapatkan objek **CloudFileShare** , gunakan cmdlet Get-AzStorageShare tersebut.
Objek ini berisi konteks penyimpanan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure. Storage. File.CloudFileShare

### Microsoft.Azure. Storage. File.CloudFileDirectory

### Microsoft.Azure. Storage. File.CloudFile

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageFile

## CATATAN

## RELATED LINKS

[Get-AzStorageFile](./Get-AzStorageFile.md)

[Set-AzStorageFileContent](./Set-AzStorageFileContent.md)


