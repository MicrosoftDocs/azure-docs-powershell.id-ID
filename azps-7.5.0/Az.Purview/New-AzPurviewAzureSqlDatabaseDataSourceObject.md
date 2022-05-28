---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureSqlDatabaseDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDatabaseDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDatabaseDataSourceObject.md
ms.openlocfilehash: f1c23f64d548da6d02b132a825af96d2027667c4
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145653286"
---
# New-AzPurviewAzureSqlDatabaseDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk AzureSqlDatabaseDataSource.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewazuresqldatabasedatasourceobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewAzureSqlDatabaseDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-Location <String>] [-ResourceGroup <String>] [-ResourceName <String>]
 [-ServerEndpoint <String>] [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureSqlDatabaseDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data database Azure SQL
```powershell
PS C:\> New-AzPurviewAzureSqlDatabaseDataSourceObject -Kind 'AzureSqlDatabase' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -ServerEndpoint 'ause.database.windows.net'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : AzureSqlDatabase
LastModifiedAt           :
Location                 :
Name                     :
ResourceGroup            :
ResourceName             :
Scan                     :
ServerEndpoint           : ause.database.windows.net
SubscriptionId           :
```

Membuat objek sumber data database Azure SQL

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

### -Lokasi

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

### -ResourceGroup

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

### -ResourceName

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

### -SubscriptionId

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureSqlDatabaseDataSource

## NOTES

ALIAS

## RELATED LINKS
