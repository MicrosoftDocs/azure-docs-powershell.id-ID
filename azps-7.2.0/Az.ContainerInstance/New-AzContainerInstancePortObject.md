---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstancePortObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstancePortObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstancePortObject.md
ms.openlocfilehash: 4afdcff7da9d138e20d906de1c4c42ad38ae57d5
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138308140"
---
# New-AzContainerInstancePortObject

## SYNOPSIS
Membuat objek dalam memori untuk ContainerPort

## SYNTAX

```
New-AzContainerInstancePortObject -Port <Int32> [-Protocol <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ContainerPort

## EXAMPLES

### Contoh 1: Menentukan port 8000 yang diekspos pada wadah dengan protokol TCP
```powershell
PS C:\> New-AzContainerInstancePortObject -Port 8000 -Protocol TCP

Port Protocol
----- --------
8000  TCP
```

Perintah ini menentukan port 8000 yang diekspos pada wadah dengan protokol TCP.

## PARAMETERS

### -Port
Nomor port yang diekspos dalam grup wadah.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.ContainerPort

## CATATAN

ALIAS

## RELATED LINKS

