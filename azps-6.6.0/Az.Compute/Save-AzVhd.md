---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 18E1AD70-42A6-47A2-A685-6E218B6DC4BE
online version: https://docs.microsoft.com/powershell/module/az.compute/save-azvhd
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Save-AzVhd.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Save-AzVhd.md
ms.openlocfilehash: 66b785c7278fe5fb31edc114da6268ffcf654a46
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136353561"
---
# Save-AzVhd

## SYNOPSIS
Menyimpan gambar .vhd yang diunduh secara lokal.

## SYNTAX

### ResourceGroupParameterSetName
```
Save-AzVhd [-ResourceGroupName] <String> [-SourceUri] <Uri> [-LocalFilePath] <FileInfo>
 [[-NumberOfThreads] <Int32>] [-OverWrite] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### StorageKeyParameterSetName
```
Save-AzVhd [-StorageKey] <String> [-SourceUri] <Uri> [-LocalFilePath] <FileInfo> [[-NumberOfThreads] <Int32>]
 [-OverWrite] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Save-AzVhd** menyimpan gambar .vhd dari blob tempat gambar disimpan ke file.
Anda dapat menentukan jumlah utas topik yang digunakan oleh proses dan apakah akan mengganti file yang sudah ada.
Cmdlet ini mengunduh konten apa pun.
Ini tidak menerapkan konversi format Hard Disk Virtual (VHD).

## EXAMPLES

### Contoh 1: Unduh gambar
```
PS C:\> Save-AzVhd -SourceUri "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -ResourceGroupName "rgname"
```

Perintah ini mengunduh file .vhd, dan menyimpannya di jalur lokal C:\vhd\Win7Image.vhd.

### Contoh 2: Unduh gambar dan timpa file lokal
```
PS C:\> Save-AzVhd -SourceUri "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite -ResourceGroupName "rgname"
```

Perintah ini akan mengunduh file .vhd, lalu menyimpannya dalam jalur lokal.
Perintah menyertakan parameter *Overwrite.*
Oleh karena itu, jika C:\vhd\Win7Image.vhd sudah ada, perintah ini akan menggantikannya.

### Contoh 3: Mengunduh gambar menggunakan jumlah utas yang ditentukan
```
PS C:\> Save-AzVhd -SourceUri "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfThreads 32 -ResourceGroupName "rgname"
```

Perintah ini akan mengunduh file .vhd, lalu menyimpannya dalam jalur lokal.
Perintah menentukan nilai 32 untuk parameter *NumberOfThreads.*
Oleh karena itu, cmdlet menggunakan 32 utas untuk tindakan ini.

### Contoh 4: Unduh gambar dan tentukan kunci penyimpanan
```
PS C:\> Save-AzVhd -SourceUri "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -StorageKey "zNvcH0r5vAGmC5AbwEtpcyWCMyBd3eMDbdaa4ua6kwxq6vTZH3Y+sw==" -ResourceGroupName "rgname"
```

Perintah ini akan mengunduh file .vhd dan menentukan kunci penyimpanan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Pekerjaan untuk melacak kemajuan.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalFilePath
Menentukan jalur file lokal dari gambar yang disimpan.

```yaml
Type: System.IO.FileInfo
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
Type: System.Int32
Parameter Sets: (All)
Aliases: th

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverWrite
Cmdlet ini menggantikan file yang ditentukan oleh file *LocalFilePath* jika ada.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: o

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya akun penyimpanan.

```yaml
Type: System.String
Parameter Sets: ResourceGroupParameterSetName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceUri
Menentukan Uniform Resource Identifier (URI) dari blob di `Azure` .

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: src, Source

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageKey
Menentukan kunci penyimpanan akun penyimpanan blob.
Jika Anda tidak menentukan kunci, cmdlet ini akan berusaha menentukan kunci penyimpanan akun tersebut di *SourceUri* dari Azure.

```yaml
Type: System.String
Parameter Sets: StorageKeyParameterSetName
Aliases: sk

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Uri

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.VhdDownloadContext

## CATATAN

## RELATED LINKS

[Add-Azvhd](./Add-AzVhd.md)


