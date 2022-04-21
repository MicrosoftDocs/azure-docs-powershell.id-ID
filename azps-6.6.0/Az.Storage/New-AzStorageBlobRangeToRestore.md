---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstorageblobrangetorestore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageBlobRangeToRestore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageBlobRangeToRestore.md
ms.openlocfilehash: 27630efd6d86c7a633d3b727b5215d0ba611ebd9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142706500"
---
# New-AzStorageBlobRangeToRestore

## SYNOPSIS
Membuat objek Blob Range untuk memulihkan akun Storage.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.storage/new-azstorageblobrangetorestore) untuk informasi terbaru.

## SYNTAX

```
New-AzStorageBlobRangeToRestore [-StartRange <String>] [-EndRange <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageBlobRangeToRestore** membuat objek rentang Blob, yang dapat digunakan dalam Restore-AzStorageBlobRange.

## EXAMPLES

### Contoh 1: Membuat rentang blob untuk dipulihkan
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange container1/blob1 -EndRange container2/blob2
```

Perintah ini membuat rentang blob untuk dipulihkan, yang dimulai dari container1/blob1 (include), dan berakhir di container2/blob2 (tidak termasuk).

### Contoh 2: Membuat rentang blob yang akan memulihkan dari blob pertama dalam urutan alfabet, ke blob tertentu (tidak termasuk)
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange "" -EndRange container2/blob2
```

Perintah ini membuat rentang blob yang akan memulihkan dari gumpakan pertama urutan alfabet, ke wadah blob2/blob2 tertentu (tidak termasuk)

### Contoh 3: Membuat rentang blob yang akan dipulihkan dari blob tertentu (include), hingga blob terakhir dalam urutan alfabet
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange container1/blob1 -EndRange ""
```

Perintah ini membuat rentang blob yang akan dipulihkan dari wadah blob tertentu1/blob1 (termasuk), ke gumpakan terakhir dalam urutan alfabet.

### Contoh 4: Membuat rentang blob yang akan memulihkan semua blob
```powershell
PS C:\> $range = New-AzStorageBlobRangeToRestore -StartRange "" -EndRange ""
```

Perintah ini membuat rentang blob yang akan memulihkan semua blob.

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
Rentang akhir akan dikecualikan dalam blob pemulihan.
Atur sebagai strng kosong untuk memulihkan ke akhir.

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
Rentang mulai akan disertakan dalam blob pemulihan.
Atur sebagai string kosong untuk dipulihkan dari awal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobRestoreRange

## NOTES

## RELATED LINKS
