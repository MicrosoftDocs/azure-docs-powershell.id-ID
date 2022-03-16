---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstorageblobrangetorestore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageBlobRangeToRestore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageBlobRangeToRestore.md
ms.openlocfilehash: 27630efd6d86c7a633d3b727b5215d0ba611ebd9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140260813"
---
# New-AzStorageBlobRangeToRestore

## SYNOPSIS
Membuat objek Rentang Blob untuk memulihkan akun Storage tersebut.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.storage/new-azstorageblobrangetorestore) untuk informasi terkini.

## SYNTAX

```
New-AzStorageBlobRangeToRestore [-StartRange <String>] [-EndRange <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageBlobRangeToRestore** membuat objek rentang Blob, yang dapat digunakan dalam Restore-AzStorageBlobRange.

## EXAMPLES

### Contoh 1: Membuat rentang blob untuk memulihkan
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange container1/blob1 -EndRange container2/blob2
```

Perintah ini akan membuat rentang blob untuk dipulihkan, yang dimulai pada container1/blob1 (termasuk), dan berakhir pada container2/blob2 (tidak termasuk).

### Contoh 2: Membuat rentang blob yang akan memulihkan dari blob pertama dalam urutan alfabet, ke blob tertentu (tidak termasuk)
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange "" -EndRange container2/blob2
```

Perintah ini membuat rentang blob yang akan memulihkan dari urutan alfabet pertama blob, ke wadah blob tertentu2/blob2 (tidak termasuk)

### Contoh 3: Membuat rentang blob yang akan dipulihkan dari blob tertentu (termasuk), ke blob terakhir dalam urutan alfabet
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange container1/blob1 -EndRange ""
```

Perintah ini membuat rentang blob yang akan memulihkan dari wadah blob tertentu1/blob1 (termasuk), ke blob terakhir dalam urutan alfabet.

### Contoh 4: Membuat rentang blob yang akan memulihkan semua blob
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange "" -EndRange ""
```

Perintah ini akan membuat rentang blob yang akan memulihkan semua blob.

## PARAMETERS

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

### -EndRange
Tentukan rentang Akhir pemulihan blob.
Rentang akhir akan dikecualikan dalam pemulihan blob.
Atur sebagai strng kosong untuk dikembalikan ke akhir.

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

### -StartRange
Tentukan rentang mulai pemulihan blob.
Rentang mulai akan disertakan dalam pemulihan blob.
Atur string tersebut sebagai string kosong untuk dipulihkan dari awal.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobRestoreRange

## CATATAN

## RELATED LINKS
