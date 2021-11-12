---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: E9500392-6BE1-46EC-9AF5-9234281025E6
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/new-azstoragequeue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/New-AzStorageQueue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/New-AzStorageQueue.md
ms.openlocfilehash: 1ce3615d7eeef4986f1fefd20ec5be2ea1aaac7b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424440"
---
# New-AzStorageQueue

## SYNOPSIS
Membuat antrean penyimpanan.

## SYNTAX

```
New-AzStorageQueue [-Name] <String> [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageQueue** membuat antrean penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Membuat antrean penyimpanan Azure
```
PS C:\>New-AzStorageQueue -Name "queueabc"
```

Contoh ini membuat antrean penyimpanan bernama queueabc.

### Contoh 2: Membuat beberapa antrean penyimpanan Azure
```
PS C:\>"queue1 queue2 queue3".split() | New-AzStorageQueue
```

Contoh ini membuat beberapa antrean penyimpanan.
Alur kerja menggunakan metode Terpisah dari kelas .NET String lalu melewati nama dalam saluran.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Anda dapat membuatnya menggunakan cmdlet New-AzStorageContext baru.

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
Menentukan nama untuk antrean.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Queue

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageQueue

## CATATAN

## RELATED LINKS

[Get-AzStorageQueue](./Get-AzStorageQueue.md)

[Remove-AzStorageQueue](./Remove-AzStorageQueue.md)


