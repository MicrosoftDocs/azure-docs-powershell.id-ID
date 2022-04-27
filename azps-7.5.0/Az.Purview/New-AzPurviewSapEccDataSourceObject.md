---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewSapEccDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapEccDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapEccDataSourceObject.md
ms.openlocfilehash: efac7a9cd8f69e01b98f8295453e8665a7a7abe7
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144186849"
---
# New-AzPurviewSapEccDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk SapEccDataSource.

## SYNTAX

```
New-AzPurviewSapEccDataSourceObject -Kind <DataSourceType> [-ApplicationServer <String>]
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-SystemNumber <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk SapEccDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data SAPECC
```powershell
PS C:\> New-AzPurviewSapEccDataSourceObject -Kind 'SapEcc' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -ApplicationServer '12.13.14.12' -SystemNumber 32

ApplicationServer        : 12.13.14.12
CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : SapEcc
LastModifiedAt           :
Name                     :
Scan                     :
SystemNumber             : 32
```

Membuat objek sumber data SAPECC

## PARAMETERS

### -ApplicationServer

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

### -SystemNumber

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.SapEccDataSource

## NOTES

ALIAS

## RELATED LINKS
