---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 4631D36F-926A-4279-AA4D-5F694C18081E
online version: ''
schema: 2.0.0
ms.openlocfilehash: e3833d71d88be028691d5ce53a5d6c155678cf4e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421112"
---
# Get-AzureStorageTable

## SYNOPSIS
Mencantumkan tabel penyimpanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Nama Tabel (Default)
```
Get-AzureStorageTable [[-Name] <String>] [-Context <IStorageContext>] [<CommonParameters>]
```

### TablePrefix
```
Get-AzureStorageTable -Prefix <String> [-Context <IStorageContext>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageTable** mencantumkan tabel penyimpanan yang terkait dengan akun penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Mencantumkan semua Azure Storage tabel
```
PS C:\>Get-AzureStorageTable
```

Perintah ini akan mendapatkan semua tabel penyimpanan untuk Storage Anda.

### Contoh 2: Daftar Azure Storage tabel menggunakan karakter wildcard
```
PS C:\>Get-AzureStorageTable -Name table*
```

Perintah ini menggunakan karakter wildcard untuk mendapatkan tabel penyimpanan yang namanya dimulai dengan tabel.

### Contoh 3: Daftar Azure Storage tabel menggunakan prefiks nama tabel
```
PS C:\>Get-AzureStorageTable -Prefix "table"
```

Perintah ini menggunakan parameter *Prefix* untuk mendapatkan tabel penyimpanan yang namanya dimulai dengan tabel.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan.
Untuk membuatnya, Anda dapat menggunakan cmdlet New-AzureStorageContext baru.

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
Menentukan nama tabel.
Jika nama tabel kosong, cmdlet akan mencantumkan semua tabel.
Jika tidak, akan mencantumkan semua tabel yang cocok dengan nama atau pola nama biasa yang ditentukan.

```yaml
Type: String
Parameter Sets: TableName
Aliases: N, Table

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Prefix
Menentukan prefiks yang digunakan dalam nama tabel atau tabel yang ingin Anda dapatkan.
Anda bisa menggunakan ini untuk menemukan semua tabel yang dimulai dengan string yang sama, seperti tabel.

```yaml
Type: String
Parameter Sets: TablePrefix
Aliases: 

Required: True
Position: Named
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

[New-AzureStorageTable](./New-AzureStorageTable.md)

[Remove-AzureStorageTable](./Remove-AzureStorageTable.md)


