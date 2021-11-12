---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 18E1AD70-42A6-47A2-A685-6E218B6DC4BE
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Save-AzureRmVhd.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Save-AzureRmVhd.md
ms.openlocfilehash: cc43308f0e0051a050b3983968d9c86f67ec66b7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425677"
---
# Save-AzureRmVhd

## SYNOPSIS
Menyimpan gambar .vhd yang diunduh secara lokal.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ResourceGroupParameterSetName
```
Save-AzureRmVhd [-ResourceGroupName] <String> [-SourceUri] <Uri> [-LocalFilePath] <FileInfo>
 [[-NumberOfThreads] <Int32>] [-OverWrite] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### StorageKeyParameterSetName
```
Save-AzureRmVhd [-StorageKey] <String> [-SourceUri] <Uri> [-LocalFilePath] <FileInfo>
 [[-NumberOfThreads] <Int32>] [-OverWrite] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Save-AzureRmVhd** menyimpan gambar .vhd dari blob tempat gambar disimpan ke file.
Anda dapat menentukan jumlah utas topik yang digunakan oleh proses dan apakah akan mengganti file yang sudah ada.

Cmdlet ini mengunduh konten apa pun.
Ini tidak menerapkan konversi format Hard Disk Virtual (VHD).

## EXAMPLES

### Contoh 1: Unduh gambar
```
PS C:\> Save-AzureRmVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd"
```

Perintah ini mengunduh file .vhd, dan menyimpannya di jalur lokal C:\vhd\Win7Image.vhd.

### Contoh 2: Unduh gambar dan timpa file lokal
```
PS C:\> Save-AzureRmVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite
```

Perintah ini akan mengunduh file .vhd, lalu menyimpannya dalam jalur lokal.
Perintah menyertakan parameter *Overwrite.*
Oleh karena itu, jika C:\vhd\Win7Image.vhd sudah ada, perintah ini akan menggantikannya.

### Contoh 3: Mengunduh gambar menggunakan jumlah utas yang ditentukan
```
PS C:\> Save-AzureRmVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfThreads 32
```

Perintah ini akan mengunduh file .vhd, lalu menyimpannya dalam jalur lokal.
Perintah menentukan nilai 32 untuk parameter *NumberOfThreads.*
Oleh karena itu, cmdlet menggunakan 32 utas untuk tindakan ini.

### Contoh 4: Unduh gambar dan tentukan kunci penyimpanan
```
PS C:\> Save-AzureRmVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -StorageKey "zNvcH0r5vAGmC5AbwEtpcyWCMyBd3eMDbdaa4ua6kwxq6vTZH3Y+sw=="
```

Perintah ini akan mengunduh file .vhd dan menentukan kunci penyimpanan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Menentukan nama grup sumber daya komputer virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureRmVhd](./Add-AzureRMVhd.md)


