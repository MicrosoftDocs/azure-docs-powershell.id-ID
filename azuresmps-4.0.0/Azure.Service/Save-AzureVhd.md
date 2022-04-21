---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: E4660D0A-26CB-488C-9A29-3ED94A0DCDA2
online version: ''
schema: 2.0.0
ms.openlocfilehash: e19b9b068742dae3d9da30fa30edd573c2f42749
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142787410"
---
# Save-AzureVhd

## SYNOPSIS
Mengaktifkan unduhan gambar .vhd.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Save-AzureVhd [-Source] <Uri> [-LocalFilePath] <FileInfo> [[-NumberOfThreads] <Int32>] [[-StorageKey] <String>]
 [-OverWrite] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Save-AzureVhd** memungkinkan pengunduhan gambar .vhd dari blob tempat gambar disimpan ke file.
Ini memiliki parameter untuk mengonfigurasi proses pengunduhan dengan menentukan jumlah utas pengunduh yang digunakan atau menimpa file yang sudah ada di jalur file yang ditentukan.

**Save-AzureVhd** tidak melakukan konversi format VHD apa pun dan blob diunduh sebagaimana adanya.

## EXAMPLES

### Contoh 1: Mengunduh file VHD
```
PS C:\> Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd"
```

Perintah ini mengunduh file .vhd.

### Contoh 2: Unduh file VHD dan timpa file lokal
```
PS C:\> Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite
```

Perintah ini mengunduh file .vhd dan menimpa file apa pun di jalur tujuan.

### Contoh 3: Unduh file VHD dan tentukan jumlah utas
```
PS C:\> Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfThreads 32
```

Perintah ini mengunduh file .vhd dan menentukan jumlah utas.

### Contoh 4: Unduh file VHD dan tentukan kunci penyimpanan
```
PS C:\> Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -StorageKey "zNvcH0r5vAGmC5AbwEtpcyWCMyBd3eMDbdaa4ua6kwxq6vTZH3Y+sw=="
```

Perintah ini mengunduh file .vhd dan menentukan kunci penyimpanan.

## PARAMETERS

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
Menentukan jalur file lokal.

```yaml
Type: FileInfo
Parameter Sets: (All)
Aliases: lf

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfThreads
Menentukan jumlah utas unduhan yang digunakan cmdlet ini selama pengunduhan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: th

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timpa
Menentukan bahwa cmdlet ini menghapus file yang ditentukan oleh file *LocalFilePath* jika ada.

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

### -Source
Menentukan Uniform Resource Identifier (URI) ke blob di `Azure`.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: src

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageKey
Menentukan kunci penyimpanan akun penyimpanan blob.
Jika tidak disediakan, **Save-AzureVhd** akan mencoba menentukan kunci penyimpanan akun di *SourceUri* dari Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sk

Required: False
Position: 4
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

[Add-AzureVhd](./Add-AzureVhd.md)


