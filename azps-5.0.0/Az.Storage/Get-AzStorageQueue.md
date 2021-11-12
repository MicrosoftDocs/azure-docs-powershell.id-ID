---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: C2EBCCF0-56CE-4D49-A138-74E52FC3A9AC
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/get-azstoragequeue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/Get-AzStorageQueue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/Get-AzStorageQueue.md
ms.openlocfilehash: df4d31c1a90808e4d289cab60c5edf9785de1182
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132406900"
---
# Get-AzStorageQueue

## SYNOPSIS
Mencantumkan antrean penyimpanan.

## SINTAKS

### QueueName (Default)
```
Get-AzStorageQueue [[-Name] <String>] [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### QueuePrefix
```
Get-AzStorageQueue -Prefix <String> [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzStorageQueue** mencantumkan antrean penyimpanan yang terkait dengan Azure Storage Anda.

## CONTOH

### Contoh 1: List all Azure Storage queues
```
PS C:\>Get-AzStorageQueue
```

Perintah ini mendapatkan daftar semua antrean penyimpanan untuk akun Storage saat ini.

### Contoh 2: Daftar Azure Storage antre menggunakan karakter wildcard
```
PS C:\>Get-AzStorageQueue -Name queue*
```

Perintah ini menggunakan karakter wildcard untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

### Contoh 3: Daftar Azure Storage antre menggunakan prefiks nama antrean
```
PS C:\>Get-AzStorageQueue -Prefix "queue"
```

Contoh ini menggunakan parameter *Prefix* untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya menggunakan cmdlet **New-AzStorageContext.**

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

### -Prefix
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUT

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageQueue

## CATATAN

## LINK TERKAIT

[New-AzStorageQueue](./New-AzStorageQueue.md)

[Remove-AzStorageQueue](./Remove-AzStorageQueue.md)


