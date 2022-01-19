---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerGroupPortObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupPortObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupPortObject.md
ms.openlocfilehash: dbd0bc927ce4ca5901a1da6361a41c442fcb883f
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136160298"
---
# New-AzContainerGroupPortObject

## SYNOPSIS
Membuat objek dalam memori untuk Port

## SYNTAX

```
New-AzContainerGroupPortObject -Port <Int32> [-Protocol <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Port

## EXAMPLES

### Contoh 1: Menentukan port 8000 yang diekspos pada grup wadah dengan protokol TCP
```powershell
PS C:\> New-AzContainerGroupPortObject -Port 8000 -Protocol TCP

Port1 Protocol
----- --------
8000  TCP
```

Perintah ini menentukan port 8000 yang diekspos pada grup wadah dengan protokol TCP.

## PARAMETERS

### -Port
Nomor port.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Protokol yang berkaitan dengan port.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.Port

## CATATAN

ALIAS

## RELATED LINKS

