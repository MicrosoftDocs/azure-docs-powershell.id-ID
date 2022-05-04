---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewTeradataDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewTeradataDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewTeradataDataSourceObject.md
ms.openlocfilehash: c27c4a7e8ce6796e02a79f23e9f28c739ed844ea
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144719965"
---
# New-AzPurviewTeradataDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk TeradataDataSource.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewteradatadatasourceobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewTeradataDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-Host <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk TeradataDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data Teradata
```powershell
PS C:\> New-AzPurviewTeradataDataSourceObject -Kind 'Teradata' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -Host '12.13.14.12'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Host                     : 12.13.14.12
Id                       :
Kind                     : Teradata
LastModifiedAt           :
Name                     :
Scan                     :
```

Membuat objek sumber data Teradata

## PARAMETERS

### -CollectionReferenceName

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

### -CollectionType

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

### -Host

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

### -Jenis

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.DataSourceType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.TeradataDataSource

## NOTES

ALIAS

## RELATED LINKS
