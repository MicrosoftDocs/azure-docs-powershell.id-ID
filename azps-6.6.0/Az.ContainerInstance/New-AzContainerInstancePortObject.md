---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstancePortObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstancePortObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstancePortObject.md
ms.openlocfilehash: b3af6d94b5b712d5a76cc43ebc72fc01531a30cd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142904177"
---
# New-AzContainerInstancePortObject

## SYNOPSIS
Membuat objek dalam memori untuk ContainerPort

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainerinstanceportobject) untuk informasi terbaru.

## SYNTAX

```
New-AzContainerInstancePortObject -Port <Int32> [-Protocol <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ContainerPort

## EXAMPLES

### Contoh 1: Tentukan port 8000 yang diekspos pada instance kontainer dengan protokol TCP
```powershell
PS C:\> New-AzContainerInstancePortObject -Port 8000 -Protocol TCP

Port Protocol
----- --------
8000  TCP
```

Perintah ini menentukan port 8000 yang diekspos pada instance container dengan protokol TCP.

## PARAMETERS

### -Port
Nomor port yang diekspos dalam grup kontainer.

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
Protokol yang terkait dengan porta.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.ContainerPort

## NOTES

ALIAS

## RELATED LINKS

