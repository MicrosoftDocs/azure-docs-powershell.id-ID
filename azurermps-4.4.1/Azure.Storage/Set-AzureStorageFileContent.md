---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: FA98E64B-D589-4653-9ACC-86573FAF4550
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Set-AzureStorageFileContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Set-AzureStorageFileContent.md
ms.openlocfilehash: 4d104c5da83c51adb197dd13710f1d65ff5f17aa
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423919"
---
# Set-AzureStorageFileContent

## SYNOPSIS
Mengunggah konten file.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ShareName (Default)
```
Set-AzureStorageFileContent [-ShareName] <String> [-Source] <String> [[-Path] <String>] [-PassThru] [-Force]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Bagikan
```
Set-AzureStorageFileContent [-Share] <CloudFileShare> [-Source] <String> [[-Path] <String>] [-PassThru]
 [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Direktori
```
Set-AzureStorageFileContent [-Directory] <CloudFileDirectory> [-Source] <String> [[-Path] <String>] [-PassThru]
 [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStorageFileContent** mengunggah konten file ke file pada berbagi yang ditentukan.

## EXAMPLES

### Contoh 1: Upload file dalam folder saat ini
```
PS C:\>Set-AzureStorageFileContent -ShareName "ContosoShare06" -Source "DataFile37" -Path "ContosoWorkingFolder/CurrentDataFile"
```

Perintah ini mengunggah file yang bernama DataFile37 dalam folder saat ini sebagai file yang bernama CurrentDataFile dalam folder bernama ContosoWorkingFolder.

### Contoh 2: Upload semua file dalam folder saat ini
```
PS C:\>$CurrentFolder = (Get-Item .).FullName
PS C:\> $Container = Get-AzureStorageShare -Name "ContosoShare06"
PS C:\> Get-ChildItem -Recurse | Where-Object { $_.GetType().Name -eq "FileInfo"} | ForEach-Object {
    $path=$_.FullName.Substring($Currentfolder.Length+1).Replace("\","/")
    Set-AzureStorageFileContent -Share $Container -Source $_.FullName -Path $path -Force
}
```

Contoh ini menggunakan beberapa cmdlet Windows PowerShell umum dan cmdlet saat ini untuk mengunggah semua file dari folder saat ini ke folder akar wadah ContosoShare06.

Perintah pertama mendapatkan nama folder saat ini dan menyimpannya dalam variabel $CurrentFolder baru.

Perintah kedua menggunakan cmdlet **Get-AzureStorageShare** untuk mendapatkan berbagi file bernama ContosoShare06, lalu menyimpannya dalam $Container baru.

Perintah terakhir mendapatkan konten folder saat ini dan meneruskannya ke cmdlet Where-Object dengan menggunakan operator pipeline.
Cmdlet tersebut memfilter objek yang bukan file, lalu meneruskan file ke cmdlet ForEach-Object cmdlet.
Cmdlet tersebut menjalankan blok skrip untuk setiap file yang membuat jalur yang sesuai untuknya, lalu menggunakan cmdlet saat ini untuk mengunggah file.
Hasilnya memiliki nama yang sama dan posisi relatif yang sama berkaitan dengan file lain yang diunggah contoh ini.
Untuk informasi selengkapnya tentang blok skrip, ketik `Get-Help about_Script_Blocks` .

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu yang habis di sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini akan mengembalikan kesalahan.

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
Menentukan jumlah maksimum panggilan jaringan bersama.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi guna membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini bisa membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth yang rendah, seperti 100 kilobit per detik.
Nilai default adalah 10.

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
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet [New-AzureStorageContext.](./New-AzureStorageContext.md)

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

### -Direktori
Menentukan folder sebagai objek **CloudFileDirectory.**
Cmdlet ini mengunggah file ke folder yang ditentukan parameter ini.
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

### -Force
Menunjukkan bahwa cmdlet ini menimpa file penyimpanan Azure yang sudah ada.

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
Menunjukkan bahwa cmdlet ini mengembalikan objek **AzureStorageFile** yang dibuat atau diunggah.

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
Menentukan jalur file atau folder.
Cmdlet ini mengunggah konten ke file yang ditentukan oleh parameter ini, atau ke file dalam folder yang ditentukan oleh parameter ini.
Jika Anda menentukan folder, cmdlet ini akan membuat file yang memiliki nama yang sama dengan file sumber.

Jika Anda menentukan jalur file yang tidak ada, cmdlet ini membuat file itu dan menyimpan konten ke file itu.
Jika Anda menentukan file yang sudah ada, dan Anda menentukan parameter _Paksa,_ cmdlet ini menimpa konten file.
Jika Anda menentukan file yang sudah ada dan Anda tidak menentukan _Paksa,_ cmdlet ini tidak melakukan perubahan, dan akan mengembalikan kesalahan.

Jika Anda menentukan jalur folder yang tidak ada, cmdlet ini tidak melakukan perubahan, dan mengembalikan kesalahan.


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

### -ServerTimeoutPerRequest
Menentukan lamanya periode waktu habis untuk bagian server dari permintaan.

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
Cmdlet ini mengunggah ke file dalam berbagi file yang ditentukan parameter ini.
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
Cmdlet ini mengunggah ke file dalam berbagi file yang ditentukan parameter ini.

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

### -Source
Menentukan file sumber yang diunggah cmdlet ini.
Jika Anda menentukan file yang tidak ada, cmdlet ini akan mengembalikan kesalahan.

```yaml
Type: String
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

### IStorageContext

Parameter 'Konteks' menerima nilai tipe 'IStorageContext' dari saluran

### CloudFileDirectory

Parameter 'Directory' menerima nilai tipe 'CloudFileDirectory' dari saluran

### CloudFileShare

Nilai parameter 'Berbagi' menerima nilai dari tipe 'CloudFileShare' dari saluran

## OUTPUTS

## CATATAN

## RELATED LINKS

[Remove-AzureStorageDirectory](./Remove-AzureStorageDirectory.md)

[New-AzureStorageDirectory](./New-AzureStorageDirectory.md)

[Get-AzureStorageFileContent](./Get-AzureStorageFileContent.md)
