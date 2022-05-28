---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/powershell/module/az.batch/new-azbatchresourcefile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchResourceFile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchResourceFile.md
ms.openlocfilehash: 4117d2373f4c8f04cf0e95e5a61934f55e2cbad5
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145687360"
---
# New-AzBatchResourceFile

## SYNOPSIS
Membuat File Sumber Daya untuk penggunaan oleh `New-AzBatchTask`.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.batch/new-azbatchresourcefile) untuk informasi terbaru.

## SYNTAX

### HttpUrl (Default)
```
New-AzBatchResourceFile -HttpUrl <String> -FilePath <String> [-FileMode <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### StorageContainerUrl
```
New-AzBatchResourceFile [-FilePath <String>] [-FileMode <String>] [-BlobPrefix <String>]
 -StorageContainerUrl <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AutoStorageContainerName
```
New-AzBatchResourceFile [-FilePath <String>] [-FileMode <String>] -AutoStorageContainerName <String>
 [-BlobPrefix <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat File Sumber Daya untuk penggunaan oleh `New-AzBatchTask`.

## EXAMPLES

### Contoh 1: Membuat file sumber daya dari URL HTTP yang menunjuk ke satu file
```powershell
$file = New-AzBatchResourceFile -HttpUrl "https://testacct.blob.core.windows.net/" -FilePath "file1"
New-AzBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -ResourceFiles $file -BatchContext $Context
```

`PSResourceFile` Membuat referensi url HTTP.

### Contoh 2: Membuat file sumber daya dari URL kontainer Azure Storage
```powershell
$file = New-AzBatchResourceFile -StorageContainerUrl "https://testacct.blob.core.windows.net/mycontainer" -FilePath "myfolder"
New-AzBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -ResourceFiles $file -BatchContext $Context
```

`PSResourceFile` Membuat referensi URL kontainer Azure Storage. Semua file dalam kontainer akan diunduh ke folder yang ditentukan.

### Contoh 3: Membuat file sumber daya dari nama kontainer Storage Otomatis
```powershell
$file = New-AzBatchResourceFile -AutoStorageContainerName "mycontainer" -FilePath "myfolder"
New-AzBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -ResourceFiles $file -BatchContext $Context
```

`PSResourceFile` Membuat referensi nama kontainer Storage Otomatis. Semua file dalam kontainer akan diunduh ke folder yang ditentukan.

## PARAMETERS

### -AutoStorageContainerName
Nama kontainer penyimpanan di akun penyimpanan otomatis.

```yaml
Type: System.String
Parameter Sets: AutoStorageContainerName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobPrefix
Mendapatkan awalan blob untuk digunakan saat mengunduh blob dari kontainer Azure Storage.
Hanya blob yang namanya dimulai dengan awalan yang ditentukan yang akan diunduh.
Awalan ini bisa berupa nama file parsial atau subdirektori.
Jika awalan tidak ditentukan, semua file dalam kontainer akan diunduh.

```yaml
Type: System.String
Parameter Sets: StorageContainerUrl, AutoStorageContainerName
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

### -FileMode
Mendapatkan atribut mode izin file dalam format oktal.
Properti ini hanya berlaku jika file sumber daya diunduh ke simpul Linux.
Jika properti ini tidak ditentukan untuk simpul Linux, maka nilai defaultnya adalah 0770.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Lokasi pada simpul komputasi untuk mengunduh file, relatif terhadap direktori kerja tugas. Jika parameter HttpUrl ditentukan, FilePath diperlukan dan menjelaskan jalur tempat file akan diunduh, termasuk nama file. Jika tidak, jika parameter AutoStorageContainerName atau StorageContainerUrl ditentukan, FilePath bersifat opsional dan merupakan direktori untuk mengunduh file. Dalam kasus di mana FilePath digunakan sebagai direktori, struktur direktori apa pun yang sudah terkait dengan data input akan disimpan secara penuh dan ditambahkan ke direktori FilePath yang ditentukan. Jalur relatif yang ditentukan tidak dapat keluar dari direktori kerja tugas (misalnya dengan menggunakan '..').

```yaml
Type: System.String
Parameter Sets: HttpUrl
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: StorageContainerUrl, AutoStorageContainerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpUrl
URL file yang akan diunduh.
Jika URL Azure Blob Storage, URL harus dapat dibaca menggunakan akses anonim; artinya, layanan Batch tidak menyajikan kredensial apa pun saat mengunduh blob.
Ada dua cara untuk mendapatkan URL seperti itu untuk blob di penyimpanan Azure: sertakan Tanda Tangan Akses Bersama (SAS) yang memberikan izin baca pada blob, atau atur ACL untuk blob atau kontainernya untuk memungkinkan akses publik.

```yaml
Type: System.String
Parameter Sets: HttpUrl
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContainerUrl
URL kontainer blob dalam Azure Blob Storage.
URL ini harus dapat dibaca dan dapat dicantumkan menggunakan akses anonim; artinya, layanan Batch tidak menyajikan kredensial apa pun saat mengunduh blob dari kontainer.
Ada dua cara untuk mendapatkan URL seperti itu untuk kontainer di penyimpanan Azure: sertakan Tanda Tangan Akses Bersama (SAS) yang memberikan izin baca pada kontainer, atau atur ACL untuk kontainer untuk memungkinkan akses publik.

```yaml
Type: System.String
Parameter Sets: StorageContainerUrl
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSResourceFile

## NOTES

## RELATED LINKS

[New-AzBatchTask](./New-AzBatchTask.md)
