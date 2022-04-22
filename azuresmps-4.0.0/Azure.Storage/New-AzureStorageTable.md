---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 3B4F32F3-51ED-4851-B38F-172658186C96
online version: ''
schema: 2.0.0
ms.openlocfilehash: 50da3cb95a411f306cd9b04f5cfff0fbab701b0c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142978931"
---
# New-AzureStorageTable

## SYNOPSIS
Membuat tabel penyimpanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorageTable [-Name] <String> [-Context <IStorageContext>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageTable** membuat tabel penyimpanan yang terkait dengan akun penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Membuat tabel penyimpanan azure
```
PS C:\>New-AzureStorageTable -Name "tableabc"
```

Perintah ini membuat tabel penyimpanan dengan nama tableabc.

### Contoh 2: Membuat beberapa tabel penyimpanan azure
```
PS C:\>"table1 table2 table3".split() | New-AzureStorageTable
```

Perintah ini membuat beberapa tabel.
Ini menggunakan metode **Split** dari kelas .NET **String** lalu meneruskan nama pada pipeline.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan.
Untuk membuatnya, Anda bisa menggunakan cmdlet New-AzureStorageContext.

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
Menentukan nama untuk tabel baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N, Table

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

## NOTES

## RELATED LINKS

[Get-AzureStorageTable](./Get-AzureStorageTable.md)

[Hapus-AzureStorageTable](./Remove-AzureStorageTable.md)


