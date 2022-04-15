---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: C2EBCCF0-56CE-4D49-A138-74E52FC3A9AC
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/get-azstoragequeue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Get-AzStorageQueue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Get-AzStorageQueue.md
ms.openlocfilehash: d26e25f839d295f07fc9ea20f2d8efcde2dd9abd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142055459"
---
# Get-AzStorageQueue

## SYNOPSIS
Mencantumkan antrean penyimpanan.

## SYNTAX

### QueueName (Default)
```
Get-AzStorageQueue [[-Name] <String>] [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AntreanPrefix
```
Get-AzStorageQueue -Prefix <String> [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageQueue** mencantumkan antrean penyimpanan yang terkait dengan akun Azure Storage.

## EXAMPLES

### Contoh 1: Mencantumkan semua antrean Azure Storage
```
PS C:\>Get-AzStorageQueue
```

Perintah ini mendapatkan daftar semua antrean penyimpanan untuk akun Storage saat ini.

### Contoh 2: Daftar antrean Azure Storage menggunakan karakter wildcard
```
PS C:\>Get-AzStorageQueue -Name queue*
```

Perintah ini menggunakan karakter wildcard untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

### Contoh 3: Daftar antrean Azure Storage menggunakan prefiks nama antrean
```
PS C:\>Get-AzStorageQueue -Prefix "queue"
```

Contoh ini menggunakan parameter *Prefiks* untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya menggunakan cmdlet **New-AzStorageContext** .

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
Menentukan nama.
Jika tidak ada nama yang ditentukan, cmdlet akan mendapatkan daftar semua antrean.
Jika nama lengkap atau sebagian ditentukan, cmdlet akan mendapatkan semua antrean yang sesuai dengan pola nama.

```yaml
Type: System.String
Parameter Sets: QueueName
Aliases: N, Queue

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Prefiks
Menentukan prefiks yang digunakan dalam nama antrean yang ingin Anda dapatkan.

```yaml
Type: System.String
Parameter Sets: QueuePrefix
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageQueue

## CATATAN

## RELATED LINKS

[Antrean AzStorage Baru](./New-AzStorageQueue.md)

[Antrean Remove-AzStorage](./Remove-AzStorageQueue.md)


