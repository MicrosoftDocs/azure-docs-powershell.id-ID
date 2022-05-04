---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: C2EBCCF0-56CE-4D49-A138-74E52FC3A9AC
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragequeue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageQueue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageQueue.md
ms.openlocfilehash: 8012df8a4b2252fc5db6defcfc8d769e5a785298
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144565078"
---
# Get-AzStorageQueue

## SYNOPSIS
Mencantumkan antrean penyimpanan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/get-azstoragequeue) untuk informasi terbaru.

## SYNTAX

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

## DESCRIPTION
Cmdlet **Get-AzStorageQueue** mencantumkan antrean penyimpanan yang terkait dengan akun Azure Storage.

## EXAMPLES

### Contoh 1: Mencantumkan semua antrean Azure Storage
```
PS C:\>Get-AzStorageQueue
```

Perintah ini mendapatkan daftar semua antrean penyimpanan untuk akun Storage saat ini.

### Contoh 2: Mencantumkan antrean Azure Storage menggunakan karakter kartubebas
```
PS C:\>Get-AzStorageQueue -Name queue*
```

Perintah ini menggunakan karakter kartubebas untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

### Contoh 3: Mencantumkan antrean Azure Storage menggunakan awalan nama antrean
```
PS C:\>Get-AzStorageQueue -Prefix "queue"
```

Contoh ini menggunakan parameter *Awalan* untuk mendapatkan daftar antrean penyimpanan yang namanya dimulai dengan antrean.

## PARAMETERS

### -Context
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya dengan menggunakan cmdlet **New-AzStorageContext** .

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
Menentukan nama.
Jika tidak ada nama yang ditentukan, cmdlet mendapatkan daftar semua antrean.
Jika nama lengkap atau parsial ditentukan, cmdlet mendapatkan semua antrean yang cocok dengan pola nama.

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

### -Awalan
Menentukan awalan yang digunakan dalam nama antrean yang ingin Anda dapatkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageQueue

## NOTES

## RELATED LINKS

[New-AzStorageQueue](./New-AzStorageQueue.md)

[Remove-AzStorageQueue](./Remove-AzStorageQueue.md)


