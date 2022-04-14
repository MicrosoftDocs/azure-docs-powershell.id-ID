---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: E9500392-6BE1-46EC-9AF5-9234281025E6
online version: ''
schema: 2.0.0
ms.openlocfilehash: c5e139b889384431205bfbd930d7527b68c5be0d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142242952"
---
# New-AzureStorageQueue

## SYNOPSIS
Membuat antrean penyimpanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorageQueue [-Name] <String> [-Context <IStorageContext>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Antrean AzureStorage Baru** membuat antrean penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Membuat antrean penyimpanan Azure
```
PS C:\>New-AzureStorageQueue -Name "queueabc"
```

Contoh ini membuat antrean penyimpanan bernama antrean.

### Contoh 2: Membuat beberapa antrean penyimpanan azure
```
PS C:\>"queue1 queue2 queue3".split() | New-AzureStorageQueue
```

Contoh ini membuat beberapa antrean penyimpanan.
Ini menggunakan metode Split dari kelas .NET String lalu meneruskan nama pada pipeline.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya menggunakan cmdlet New-AzureStorageContext.

```yaml
Type: IStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk antrean.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N, Queue

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Dapatkan-AzureStorageQueue](./Get-AzureStorageQueue.md)

[Hapus-AzureStorageQueue](./Remove-AzureStorageQueue.md)


