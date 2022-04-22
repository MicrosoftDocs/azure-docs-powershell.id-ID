---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: 4631D36F-926A-4279-AA4D-5F694C18081E
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/get-azurestoragetable
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Get-AzureStorageTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Get-AzureStorageTable.md
ms.openlocfilehash: 1d31bff44bb93db1022a88a464c2942a2a3fadbb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142925165"
---
# Get-AzureStorageTable

## SYNOPSIS
Mencantumkan tabel penyimpanan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### TableName (Default)
```
Get-AzureStorageTable [[-Name] <String>] [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### TablePrefix
```
Get-AzureStorageTable -Prefix <String> [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageTable** mencantumkan tabel penyimpanan yang terkait dengan akun penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Mencantumkan semua tabel Azure Storage
```
PS C:\>Get-AzureStorageTable
```

Perintah ini mendapatkan semua tabel penyimpanan untuk akun Storage.

### Contoh 2: Daftar tabel Azure Storage menggunakan karakter wildcard
```
PS C:\>Get-AzureStorageTable -Name table*
```

Perintah ini menggunakan karakter wildcard untuk mendapatkan tabel penyimpanan yang namanya dimulai dengan tabel.

### Contoh 3: Daftar tabel Azure Storage menggunakan prefiks nama tabel
```
PS C:\>Get-AzureStorageTable -Prefix "table"
```

Perintah ini menggunakan parameter *Prefiks* untuk mendapatkan tabel penyimpanan yang namanya dimulai dengan tabel.

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
Menentukan nama tabel.
Jika nama tabel kosong, cmdlet mencantumkan semua tabel.
Jika tidak, tabel mencantumkan semua tabel yang cocok dengan nama tertentu atau pola nama reguler.

```yaml
Type: System.String
Parameter Sets: TableName
Aliases: N, Table

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Prefiks
Menentukan prefiks yang digunakan dalam nama tabel atau tabel yang ingin Anda dapatkan.
Anda dapat menggunakannya untuk menemukan semua tabel yang dimulai dengan string yang sama, seperti tabel.

```yaml
Type: System.String
Parameter Sets: TablePrefix
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageTable

## NOTES

## RELATED LINKS

[AzureStorageTable Baru](./New-AzureStorageTable.md)

[Hapus-AzureStorageTable](./Remove-AzureStorageTable.md)


