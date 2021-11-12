---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 99DC239C-EA68-4830-9345-762CD6A3F68C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6e5ad1bc490d96ee136cc1742488a0abc1dc795dea63e215ebc65cc0febc27d5
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416473"
---
# Add-AzureVhd

## SYNOPSIS
Mengunggah file VHD dari komputer lokal ke blob di akun penyimpanan cloud di Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureVhd [-Destination] <Uri> [-LocalFilePath] <FileInfo> [[-NumberOfUploaderThreads] <Int32>]
 [[-BaseImageUriToPatch] <Uri>] [-OverWrite] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureVhd** mengunggah gambar hard disk virtual (VHD) lokal ke akun penyimpanan blob sebagai gambar .vhd tetap.
Alat ini memiliki parameter untuk mengonfigurasi proses pengunggahan seperti menentukan jumlah utas pengunggah yang akan digunakan atau menimpa blob yang sudah ada di URI tujuan yang ditentukan.
Untuk gambar VHD lokal, skenario patching juga didukung sehingga gambar disk diff bisa diunggah tanpa harus mengunggah gambar dasar yang sudah diunggah. URI Akses Bersama (Shared Access Signature) URI juga didukung.

## EXAMPLES

### Contoh 1: Tambahkan file VHD
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.

### Contoh 2: Tambahkan file VHD dan timpa tujuan
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.

### Contoh 3: Tambahkan file VHD dan tentukan jumlah utas
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfThreads 32
```

Perintah ini menambahkan file .vhd ke akun penyimpanan dan menentukan jumlah utas yang digunakan untuk mengunggah file.

### Contoh 4: Tambahkan file VHD dan tentukan SAS URI
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd?st=2013-01-09T22%3A15%3A49Z&amp;se=2013-01-09T23%3A10%3A49Z&amp;sr=b&amp;sp=w&amp;sig=13T9Ow%2FRJAMmhfO%2FaP3HhKKJ6AY093SmveOSIV4%2FR7w%3D" -LocalFilePath "C:\vhd\win7baseimage.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan dan menentukan URI SAS.

## PARAMETERS

### -BaseImageUriToPatch
Menentukan URI ke blob gambar dasar di Azure Blob Storage.
Input SAS in URI juga didukung.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: bs

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tujuan
Menentukan URI ke blob di Microsoft Azure Blob Storage.
Input SAS in URI didukung.
Namun, dalam skenario patching, tujuan tidak dapat menjadi URI SAS.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: dst

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalFilePath
Spesies jalur file dari file .vhd lokal.

```yaml
Type: FileInfo
Parameter Sets: (All)
Aliases: lf

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberOfUploaderThreads
Menentukan jumlah utas yang akan digunakan untuk unggahan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: th

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverWrite
Menentukan bahwa cmdlet ini akan menghapus blob yang sudah ada di URI tujuan yang ditentukan jika ada.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: o

Required: False
Position: 5
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Save-AzureVhd](./Save-AzureVhd.md)


