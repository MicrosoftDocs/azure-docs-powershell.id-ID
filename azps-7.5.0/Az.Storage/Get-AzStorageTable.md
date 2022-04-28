---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 4631D36F-926A-4279-AA4D-5F694C18081E
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragetable
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageTable.md
ms.openlocfilehash: d2a10da8aab33dca5d9c3adcae219925d14c4eb3
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144193555"
---
# Get-AzStorageTable

## SYNOPSIS
Mencantumkan tabel penyimpanan.

## SYNTAX

### TableName (Default)
```
Get-AzStorageTable [[-Name] <String>] [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### TablePrefix
```
Get-AzStorageTable -Prefix <String> [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageTable** mencantumkan tabel penyimpanan yang terkait dengan akun penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Mencantumkan semua tabel Azure Storage
```
PS C:\>Get-AzStorageTable
```

Perintah ini mendapatkan semua tabel penyimpanan untuk akun Storage.

### Contoh 2: Mencantumkan tabel Azure Storage menggunakan karakter kartubebas
```
PS C:\>Get-AzStorageTable -Name table*
```

Perintah ini menggunakan karakter kartubebas untuk mendapatkan tabel penyimpanan yang namanya dimulai dengan tabel.

### Contoh 3: Mencantumkan tabel Azure Storage menggunakan awalan nama tabel
```
PS C:\>Get-AzStorageTable -Prefix "table"
```

Perintah ini menggunakan parameter *Awalan* untuk mendapatkan tabel penyimpanan yang namanya dimulai dengan tabel.

## PARAMETERS

### -Context
Menentukan konteks penyimpanan.
Untuk membuatnya, Anda dapat menggunakan cmdlet New-AzStorageContext.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Menentukan nama tabel.
Jika nama tabel kosong, cmdlet mencantumkan semua tabel.
Jika tidak, ini mencantumkan semua tabel yang cocok dengan nama yang ditentukan atau pola nama reguler.

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

### -Awalan
Menentukan awalan yang digunakan dalam nama tabel atau tabel yang ingin Anda dapatkan.
Anda dapat menggunakan ini untuk menemukan semua tabel yang dimulai dengan string yang sama, seperti tabel.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageTable

## NOTES

## RELATED LINKS

[New-AzStorageTable](./New-AzStorageTable.md)

[Remove-AzStorageTable](./Remove-AzStorageTable.md)


