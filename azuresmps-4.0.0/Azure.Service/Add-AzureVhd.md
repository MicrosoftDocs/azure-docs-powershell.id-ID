---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 99DC239C-EA68-4830-9345-762CD6A3F68C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7b247aa500cfdbcadcbcf7e75ff580bb393eb875
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142917574"
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
**Cmdlet Add-AzureVhd** mengunggah gambar hard disk Virtual (VHD) lokal ke akun penyimpanan blob sebagai gambar .vhd tetap.
Ini memiliki parameter untuk mengonfigurasi proses pengunggahan seperti menentukan jumlah utas pengunggah yang akan digunakan atau menimpa blob yang sudah ada dalam URI tujuan yang ditentukan.
Untuk gambar VHD lokal, skenario patching juga didukung sehingga gambar disk diff dapat diunggah tanpa harus mengunggah gambar dasar yang sudah diunggah. URI Shared Access Signature (SAS) juga didukung.

## EXAMPLES

### Contoh 1: Menambahkan file VHD
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.

### Contoh 2: Menambahkan file VHD dan menimpa tujuan
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.

### Contoh 3: Menambahkan file VHD dan menentukan jumlah utas
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfThreads 32
```

Perintah ini menambahkan file .vhd ke akun penyimpanan dan menentukan jumlah utas untuk digunakan untuk mengunggah file.

### Contoh 4: Menambahkan file VHD dan menentukan SAS URI
```
PS C:\> Add-AzureVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd?st=2013-01-09T22%3A15%3A49Z&amp;se=2013-01-09T23%3A10%3A49Z&amp;sr=b&amp;sp=w&amp;sig=13T9Ow%2FRJAMmhfO%2FaP3HhKKJ6AY093SmveOSIV4%2FR7w%3D" -LocalFilePath "C:\vhd\win7baseimage.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan dan menentukan SAS URI.

## PARAMETERS

### -BaseImageUriToPatch
Menentukan URI ke blob gambar dasar dalam Azure Blob Storage.
SAS dalam input URI juga didukung.

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
SAS dalam input URI didukung.
Namun, dalam skenario patching, tujuan tidak dapat berupa URI SAS.

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
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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
Menentukan jumlah utas yang digunakan untuk diunggah.

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

### -Timpa
Menentukan bahwa cmdlet ini menghapus blob yang sudah ada dalam URI tujuan yang ditentukan jika ada.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Simpan-AzureVhd](./Save-AzureVhd.md)


