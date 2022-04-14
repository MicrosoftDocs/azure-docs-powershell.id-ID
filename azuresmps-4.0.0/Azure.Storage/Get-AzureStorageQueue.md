---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: C2EBCCF0-56CE-4D49-A138-74E52FC3A9AC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 26f64625cae5f916b59944b4a635752d81e65a1c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141965409"
---
# Get-AzureStorageQueue

## SYNOPSIS
Mencantumkan antrean penyimpanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### QueueName (Default)
```
Get-AzureStorageQueue [[-Name] <String>] [-Context <IStorageContext>] [<CommonParameters>]
```

### AntreanPrefix
```
Get-AzureStorageQueue -Prefix <String> [-Context <IStorageContext>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageQueue** mencantumkan antrean penyimpanan yang terkait dengan akun Azure Storage.

## EXAMPLES

### Contoh 1: Mencantumkan semua antrean Azure Storage
```
PS C:\>Get-AzureStorageQueue
```

Perintah ini mendapatkan daftar semua antrean penyimpanan untuk akun Storage saat ini.

### Contoh 2: Daftar antrean Azure Storage menggunakan karakter wildcard
```
PS C:\>Get-AzureStorageQueue -Name queue*
```

Perintah ini menggunakan karakter wildcard untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

### Contoh 3: Daftar antrean Azure Storage menggunakan prefiks nama antrean
```
PS C:\>Get-AzureStorageQueue -Prefix "queue"
```

Contoh ini menggunakan parameter *Prefiks* untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya menggunakan cmdlet **New-AzureStorageContext** .

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
Menentukan nama.
Jika tidak ada nama yang ditentukan, cmdlet akan mendapatkan daftar semua antrean.
Jika nama lengkap atau sebagian ditentukan, cmdlet akan mendapatkan semua antrean yang sesuai dengan pola nama.

```yaml
Type: String
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
Type: String
Parameter Sets: QueuePrefix
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

## OUTPUTS

## CATATAN

## RELATED LINKS

[Antrean AzureStorage Baru](./New-AzureStorageQueue.md)

[Hapus-AzureStorageQueue](./Remove-AzureStorageQueue.md)


