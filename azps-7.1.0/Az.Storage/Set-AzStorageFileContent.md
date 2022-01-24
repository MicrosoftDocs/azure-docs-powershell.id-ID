---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: FA98E64B-D589-4653-9ACC-86573FAF4550
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstoragefilecontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageFileContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageFileContent.md
ms.openlocfilehash: 7e314cd504275d1cd65363bfe28ae018fcd634f1
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136699512"
---
# Set-AzStorageFileContent

## SYNOPSIS
Mengunggah konten file.

## SYNTAX

### ShareName (Default)
```
Set-AzStorageFileContent [-ShareName] <String> [-Source] <String> [[-Path] <String>] [-PassThru] [-Force]
 [-AsJob] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [-PreserveSMBAttribute] [<CommonParameters>]
```

### Bagikan
```
Set-AzStorageFileContent [-Share] <CloudFileShare> [-Source] <String> [[-Path] <String>] [-PassThru] [-Force]
 [-AsJob] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [-PreserveSMBAttribute] [<CommonParameters>]
```

### Direktori
```
Set-AzStorageFileContent [-Directory] <CloudFileDirectory> [-Source] <String> [[-Path] <String>] [-PassThru]
 [-Force] [-AsJob] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [-PreserveSMBAttribute] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageFileContent** mengunggah konten file ke file pada berbagi yang ditentukan.

## EXAMPLES

### Contoh 1: Upload file dalam folder saat ini
```
PS C:\>Set-AzStorageFileContent -ShareName "ContosoShare06" -Source "DataFile37" -Path "ContosoWorkingFolder/CurrentDataFile"
```

Perintah ini mengunggah file yang bernama DataFile37 dalam folder saat ini sebagai file yang bernama CurrentDataFile dalam folder bernama ContosoWorkingFolder.

### Contoh 2: Upload semua file dalam folder saat ini
```
PS C:\>$CurrentFolder = (Get-Item .).FullName
PS C:\> $Container = Get-AzStorageShare -Name "ContosoShare06"
PS C:\> Get-ChildItem -Recurse | Where-Object { $_.GetType().Name -eq "FileInfo"} | ForEach-Object {
    $path=$_.FullName.Substring($Currentfolder.Length+1).Replace("\","/")
    Set-AzStorageFileContent -Share $Container -Source $_.FullName -Path $path -Force
}
```

Contoh ini menggunakan beberapa cmdlet Windows PowerShell umum dan cmdlet saat ini untuk mengunggah semua file dari folder saat ini ke folder akar wadah ContosoShare06.
Perintah pertama mendapatkan nama folder saat ini dan menyimpannya di $CurrentFolder variabel.
Perintah kedua menggunakan cmdlet **Get-AzStorageShare** untuk mendapatkan berbagi file bernama ContosoShare06, lalu menyimpannya dalam $Container baru.
Perintah terakhir mendapatkan konten folder saat ini dan meneruskannya ke cmdlet Where-Object dengan menggunakan operator pipeline.
Cmdlet tersebut memfilter objek yang bukan file, lalu meneruskan file ke cmdlet ForEach-Object cmdlet.
Cmdlet tersebut menjalankan blok skrip untuk setiap file yang membuat jalur yang sesuai untuknya, lalu menggunakan cmdlet saat ini untuk mengunggah file.
Hasilnya memiliki nama yang sama dan posisi relatif yang sama berkaitan dengan file lain yang diunggah contoh ini.
Untuk informasi selengkapnya tentang blok skrip, ketik `Get-Help about_Script_Blocks` .

### Contoh 3: Upload menggunakan file lokal ke file Azure, dan memesan properti SMB File lokal (File Attributtes, Waktu Pembuatan File, Waktu Penulisan Terakhir File) di file Azure.
```
PS C:\>Get-AzStorageFileContent -source $localFilePath -ShareName sample -Path "dir1/file1" -PreserveSMBAttribute
```

Contoh ini mengunggah file lokal ke file Azure, dan menghemat properti SMB File lokal (File Attributtes, Waktu Pembuatan File, Waktu Penulisan Terakhir File) di file Azure.

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

### -ClientTimeoutPerRequest
Menentukan interval waktu yang habis di sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini akan mengembalikan kesalahan.

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
Menentukan jumlah maksimum panggilan jaringan bersama.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi guna membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini bisa membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth yang rendah, seperti 100 kilobit per detik.
Nilai default adalah 10.

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
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet [New-AzStorageContext.](./New-AzStorageContext.md)

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
Menentukan folder sebagai objek **CloudFileDirectory.**
Cmdlet ini mengunggah file ke folder yang ditentukan parameter ini.
Untuk mendapatkan direktori, gunakan cmdlet New-AzStorageDirectory.
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

### -Force
Menunjukkan bahwa cmdlet ini menimpa file penyimpanan Azure yang sudah ada.

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
Menunjukkan bahwa cmdlet ini mengembalikan objek **AzureStorageFile** yang dibuat atau diunggah.

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
Menentukan jalur file atau folder.
Cmdlet ini mengunggah konten ke file yang ditentukan oleh parameter ini, atau ke file dalam folder yang ditentukan oleh parameter ini.
Jika Anda menentukan folder, cmdlet ini akan membuat file yang memiliki nama yang sama dengan file sumber.
Jika Anda menentukan jalur file yang tidak ada, cmdlet ini membuat file itu dan menyimpan konten ke file itu.
Jika Anda menentukan file yang sudah ada, dan Anda menentukan parameter _Paksa,_ cmdlet ini menimpa konten file.
Jika Anda menentukan file yang sudah ada dan Anda tidak menentukan _Paksa,_ cmdlet ini tidak melakukan perubahan, dan akan mengembalikan kesalahan.
Jika Anda menentukan jalur folder yang tidak ada, cmdlet ini tidak melakukan perubahan, dan mengembalikan kesalahan.

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
Menentukan lamanya periode waktu habis untuk bagian server dari permintaan.

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
Menentukan objek **CloudFileShare.**
Cmdlet ini mengunggah ke file dalam berbagi file yang ditentukan parameter ini.
Untuk mendapatkan objek **CloudFileShare,** gunakan cmdlet Get-AzStorageShare baru.
Objek ini berisi konteks penyimpanan.
Jika Anda menentukan parameter ini, jangan tentukan parameter *Konteks.*

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
Cmdlet ini mengunggah ke file dalam berbagi file yang ditentukan parameter ini.

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

### -Source
Menentukan file sumber yang diunggah cmdlet ini.
Jika Anda menentukan file yang tidak ada, cmdlet ini akan mengembalikan kesalahan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure. Storage. File.CloudFileShare

### Microsoft.Azure. Storage. File.CloudFileDirectory

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageFile

## CATATAN

## RELATED LINKS

[Remove-AzStorageDirectory](./Remove-AzStorageDirectory.md)

[New-AzStorageDirectory](./New-AzStorageDirectory.md)

[Get-AzStorageFileContent](./Get-AzStorageFileContent.md)
