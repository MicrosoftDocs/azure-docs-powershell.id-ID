---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: 3B4F32F3-51ED-4851-B38F-172658186C96
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/new-azurestoragetable
schema: 2.0.0
ms.openlocfilehash: 4fe02c9824945593de4b4160e9db10b1573a335a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141782690"
---
# New-AzureStorageTable

## SYNOPSIS
Membuat tabel penyimpanan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureStorageTable [-Name] <String> [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

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

### -Nama
Menentukan nama untuk tabel baru.

```yaml
Type: System.String
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

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageTable

## CATATAN

## RELATED LINKS

[Get-AzureStorageTable](./Get-AzureStorageTable.md)

[Hapus-AzureStorageTable](./Remove-AzureStorageTable.md)


