---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAmazonSqlDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonSqlDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonSqlDataSourceObject.md
ms.openlocfilehash: 86613cae77251a215608576fd8c23aa701e398fc
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144197475"
---
# New-AzPurviewAmazonSqlDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk AmazonSqlDataSource.

## SYNTAX

```
New-AzPurviewAmazonSqlDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-Port <Int32>] [-ServerEndpoint <String>] [-VpcEndpointServiceName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AmazonSqlDataSource.

## EXAMPLES

### Contoh 1: Membuat amazon SQL objek sumber data
```powershell
PS C:\> New-AzPurviewAmazonSqlDataSourceObject -Kind 'AmazonSql' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -Port 1433 -ServerEndpoint DummyEdnpoint -VpcEndpointServiceName com.amazonaws.ypce.wus.123456789

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : AmazonSql
LastModifiedAt           :
Name                     :
Port                     : 1433
Scan                     :
ServerEndpoint           : DummyEdnpoint
VpcEndpointServiceName   : com.amazonaws.ypce.wus.123456789
```

Membuat objek sumber data Amazon SQL

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

### -Port

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerEndpoint

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

### -VpcEndpointServiceName

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AmazonSqlDataSource

## NOTES

ALIAS

## RELATED LINKS
