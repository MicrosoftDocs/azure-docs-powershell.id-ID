---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewSapS4HanaDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapS4HanaDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapS4HanaDataSourceObject.md
ms.openlocfilehash: 018403547c1d33775d64f25a925ec029cc031e25
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145536573"
---
# New-AzPurviewSapS4HanaDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk SapS4HanaDataSource.

## SYNTAX

```
New-AzPurviewSapS4HanaDataSourceObject -Kind <DataSourceType> [-ApplicationServer <String>]
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-SystemNumber <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk SapS4HanaDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data SAPS4Hana
```powershell
PS C:\> New-AzPurviewSapS4HanaDataSourceObject -Kind 'SapS4Hana' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -ApplicationServer '12.13.14.12' -SystemNumber 32

ApplicationServer        : 12.13.14.12
CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : SapS4Hana
LastModifiedAt           :
Name                     :
Scan                     :
SystemNumber             : 32
```

Membuat objek sumber data SAPS4

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

### -Kind

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.SapS4HanaDataSource

## NOTES

ALIAS

## RELATED LINKS
