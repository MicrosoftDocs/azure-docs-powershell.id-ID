---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerGroupPortObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupPortObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupPortObject.md
ms.openlocfilehash: 8069894e3d987221daa7f64b0cec09b1e1aff399
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139942081"
---
# New-AzContainerGroupPortObject

## SYNOPSIS
Membuat objek dalam memori untuk Port

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.containerinstance/new-azcontainergroupportobject) untuk informasi terkini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.Port

## CATATAN

ALIAS

## RELATED LINKS

