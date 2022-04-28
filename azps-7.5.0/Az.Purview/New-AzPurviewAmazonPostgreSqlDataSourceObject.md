---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAmazonPostgreSqlDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonPostgreSqlDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonPostgreSqlDataSourceObject.md
ms.openlocfilehash: be9686dfeece420720a688a2c182ce16e80e134a
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144192382"
---
# New-AzPurviewAmazonPostgreSqlDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk AmazonPostgreSqlDataSource.

## SYNTAX

```
New-AzPurviewAmazonPostgreSqlDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-Port <Int32>] [-ServerEndpoint <String>] [-VpcEndpointServiceName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AmazonPostgreSqlDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data Amazon PostgreSQL
```powershell
PS C:\>  New-AzPurviewAmazonPostgreSqlDataSourceObject -Kind 'AmazonPostgreSql' -Port 5432 -VpcEndpointServiceName 'com.amazonaws.ypce.wus.123456789' -ServerEndpoint 'DummyServer' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : AmazonPostgreSql
LastModifiedAt           :
Name                     :
Port                     : 5432
Scan                     :
ServerEndpoint           : DummyServer
VpcEndpointServiceName   : com.amazonaws.ypce.wus.123456789
```

Membuat objek sumber data Amazon PostgreSQL

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AmazonPostgreSqlDataSource

## NOTES

ALIAS

## RELATED LINKS
