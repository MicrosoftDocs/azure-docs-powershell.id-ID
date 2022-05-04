---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewFilterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewFilterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewFilterObject.md
ms.openlocfilehash: 992d9b1088e4ab7f8f64e4c6a5300f10cf8c718d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144565262"
---
# New-AzPurviewFilterObject

## SYNOPSIS
Buat objek dalam memori untuk Filter.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewfilterobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewFilterObject [-ExcludeUriPrefix <String[]>] [-IncludeUriPrefix <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk Filter.

## EXAMPLES

### Contoh 1: Membuat objek filter
```powershell
PS C:\> New-AzPurviewFilterObject -ExcludeUriPrefix @('https://foo.file.core.windows.net/share1/user/temp') -IncludeUriPrefix @('https://foo.file.core.windows.net/share1/user','https://foo.file.core.windows.net/share1/aggregated')

ExcludeUriPrefix  : {https://foo.file.core.windows.net/share1/user/temp}
Id                :
IncludeUriPrefix  : {https://foo.file.core.windows.net/share1/user,
                    https://foo.file.core.windows.net/share1/aggregated}
Name              :
```

Membuat objek filter

## PARAMETERS

### -ExcludeUriPrefix

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeUriPrefix

```yaml
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.Filter

## NOTES

ALIAS

## RELATED LINKS
