---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewFilterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewFilterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewFilterObject.md
ms.openlocfilehash: 2bbd6f6169374f7506479df5f4c002cf912e1c50
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142430404"
---
# New-AzPurviewFilterObject

## SYNOPSIS
Membuat objek dalam memori untuk Filter.

## SYNTAX

```
New-AzPurviewFilterObject [-ExcludeUriPrefix <String[]>] [-IncludeUriPrefix <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Filter.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.Filter

## CATATAN

ALIAS

## RELATED LINKS
