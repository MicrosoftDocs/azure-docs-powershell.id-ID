---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewPowerBIDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewPowerBIDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewPowerBIDataSourceObject.md
ms.openlocfilehash: 602fbb6c8686c9dc907acc2eaa22ec59fd1b6d94
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141994655"
---
# New-AzPurviewPowerBIDataSourceObject

## SYNOPSIS
Membuat objek dalam memori untuk PowerBIDataSource.

## SYNTAX

```
New-AzPurviewPowerBIDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-Tenant <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk PowerBIDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data PowerBI
```powershell
PS C:\> New-AzPurviewPowerBIDataSourceObject -Kind 'PowerBI' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -Tenant 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : PowerBI
LastModifiedAt           :
Name                     :
Scan                     :
Tenant                   : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx
```

Membuat objek sumber data PowerBI

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

### -Penyewa

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.PowerBiDataSource

## CATATAN

ALIAS

## RELATED LINKS
