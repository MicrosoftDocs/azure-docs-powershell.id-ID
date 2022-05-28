---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerGroupPortObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupPortObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupPortObject.md
ms.openlocfilehash: 2dc9f5d85b1cc624052d01aa37396903e3077ab4
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145531423"
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

### Contoh 1: Tentukan port 8000 yang diekspos pada grup kontainer dengan protokol TCP
```powershell
New-AzContainerGroupPortObject -Port 8000 -Protocol TCP
```

```output
Port1 Protocol
----- --------
8000  TCP
```

Perintah ini menentukan port 8000 yang diekspos pada grup kontainer dengan protokol TCP.

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

### -Protokol
Protokol yang terkait dengan port.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.Port

## NOTES

ALIAS

## RELATED LINKS

