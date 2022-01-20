---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/powershell/module/az.batch/new-azbatchresourcefile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchResourceFile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchResourceFile.md
ms.openlocfilehash: 5f1126386c48138ffa5a279de735bd666a6a6ce4
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136349346"
---
# New-AzBatchResourceFile

## SYNOPSIS
Membuat File Sumber Daya untuk penggunaan oleh `New-AzBatchTask` .

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
Membuat File Sumber Daya untuk penggunaan oleh `New-AzBatchTask` .

## EXAMPLES

### Contoh 1: Buat file sumber daya dari URL HTTP yang menunjuk pada satu file
```
PS C:\> $file = New-AzBatchResourceFile -HttpUrl "https://testacct.blob.core.windows.net/" -FilePath "file1"
PS C:\> New-AzBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -ResourceFiles $file -BatchContext $Context
```

Membuat `PSResourceFile` referensi url HTTP.

### Contoh 2: Membuat file sumber daya dari URL Azure Storage penampung
```
PS C:\> $file = New-AzBatchResourceFile -StorageContainerUrl "https://testacct.blob.core.windows.net/mycontainer" -FilePath "myfolder"
PS C:\> New-AzBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -ResourceFiles $file -BatchContext $Context
```

Membuat referensi `PSResourceFile` URL wadah Azure Storage. Semua file dalam wadah akan diunduh ke folder yang ditentukan.

### Contoh 3: Buat file sumber daya dari nama wadah Storage otomatis
```
PS C:\> $file = New-AzBatchResourceFile -AutoStorageContainerName "mycontainer" -FilePath "myfolder"
PS C:\> New-AzBatchTask -JobId "Job-000001" -Id "Task23" -CommandLine "cmd /c dir /s" -ResourceFiles $file -BatchContext $Context
```

Membuat referensi `PSResourceFile` untuk nama wadah Storage Otomatis. Semua file dalam wadah akan diunduh ke folder yang ditentukan.

## PARAMETERS

### -AutoStorageContainerName
Nama wadah penyimpanan di akun penyimpanan otomatis.

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
Mendapatkan prefiks blob untuk digunakan ketika mengunduh blob dari Azure Storage penampung.
Hanya blob yang namanya dimulai dengan prefiks tertentu yang akan diunduh.
Prefiks ini dapat merupakan nama file parsial atau subarah.
Jika prefiks tidak ditentukan, semua file dalam wadah akan diunduh.

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
Properti ini berlaku hanya jika file sumber daya diunduh ke simpul Linux.
Jika properti ini tidak ditentukan untuk simpul Linux, nilai defaultnya adalah 0770.

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
Lokasi pada node perhitungan untuk mengunduh file, relatif terhadap direktori kerja tugas. Jika parameter HttpUrl ditentukan, FilePath diperlukan dan menjelaskan jalur tujuan pengunduhan file, termasuk nama file. Jika tidak, jika parameter AutoStorageContainerName atau StorageContainerUrl ditentukan, FilePath bersifat opsional dan merupakan direktori untuk mengunduh file. Dalam kasus di mana FilePath digunakan sebagai direktori, struktur direktori apa pun yang sudah terkait dengan data input akan dipertahankan secara penuh dan ditambahkan ke direktori FilePath yang ditentukan. Jalur relatif tertentu tidak bisa keluar dari direktori kerja tugas (misalnya dengan menggunakan '.').

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

### -httpUrl
URL file yang akan diunduh.
Jika URL-nya adalah Azure Blob Storage, URL tersebut harus dapat dibaca menggunakan akses anonim; artinya, layanan Batch tidak menyajikan kredensial apa pun saat mengunduh blob.
Ada dua cara untuk mendapatkan URL untuk blob di penyimpanan Azure: menyertakan izin baca pada Shared Access Signature (SAS) di blob, atau mengatur ACL untuk blob atau wadahnya untuk mengizinkan akses publik.

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
URL wadah blob dalam Azure Blob Storage.
URL ini harus dapat dibaca dan dapat di listable menggunakan akses anonim; artinya, layanan Batch tidak menyajikan kredensial apa pun saat mengunduh blob dari wadah.
Ada dua cara untuk mendapatkan URL untuk wadah di penyimpanan Azure: menyertakan izin baca pada wadah Tanda Tangan Akses Bersama (SAS, Shared Access Signature) pada wadah, atau mengatur ACL untuk wadah untuk memungkinkan akses publik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSResourceFile

## CATATAN

## RELATED LINKS

[New-AzBatchTask](./New-AzBatchTask.md)