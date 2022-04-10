---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: F1EC601C-3ADD-402A-A5F7-84A95D312187
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragequeuestoredaccesspolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageQueueStoredAccessPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageQueueStoredAccessPolicy.md
ms.openlocfilehash: 71fcfca6de80afc67c098847508c3aec0dab548d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140553812"
---
# Get-AzStorageQueueStoredAccessPolicy

## SYNOPSIS
Mendapatkan kebijakan atau kebijakan akses tersimpan untuk antrean penyimpanan Azure.

## SYNTAX

```
Get-AzStorageQueueStoredAccessPolicy [-Queue] <String> [[-Policy] <String>] [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageQueueStoredAccessPolicy** mencantumkan kebijakan akses tersimpan atau kebijakan untuk antrean penyimpanan Azure.

## EXAMPLES

### Contoh 1: Mendapatkan kebijakan akses yang disimpan dalam antrean
```
PS C:\>Get-AzStorageQueueStoredAccessPolicy -Queue "MyQueue" -Policy "Policy12"
```

Perintah ini mendapatkan kebijakan akses yang bernama Policy12 dalam antrean penyimpanan yang bernama MyQueue.

### Contoh 2: Mendapatkan semua kebijakan akses yang disimpan dalam antrean
```
PS C:\>Get-AzStorageQueueStoredAccessPolicy -Queue "MyQueue"
```

Perintah ini akan membuat semua kebijakan akses tersimpan dalam antrean yang bernama MyQueue.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet New-AzStorageContext.

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

### -Kebijakan
Menentukan kebijakan akses tersimpan, yang mencakup izin untuk token Shared Access Signature (SAS) ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Antrean
Menentukan nama antrean penyimpanan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.Azure. Storage. Queue.SharedAccessQueuePolicy

## CATATAN

## RELATED LINKS

[New-AzStorageQueueStoredAccessPolicy](./New-AzStorageQueueStoredAccessPolicy.md)

[Remove-AzStorageQueueStoredAccessPolicy](./Remove-AzStorageQueueStoredAccessPolicy.md)

[Set-AzStorageQueueStoredAccessPolicy](./Set-AzStorageQueueStoredAccessPolicy.md)

[New-AzStorageContext](./New-AzStorageContext.md)


