---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureSqlDatabaseManagedInstanceDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDatabaseManagedInstanceDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDatabaseManagedInstanceDataSourceObject.md
ms.openlocfilehash: 4bc661da30f526897f9e3aff42ac51108827eb31
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144226684"
---
# New-AzPurviewAzureSqlDatabaseManagedInstanceDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk AzureSqlDatabaseManagedInstanceDataSource.

## SYNTAX

```
New-AzPurviewAzureSqlDatabaseManagedInstanceDataSourceObject -Kind <DataSourceType>
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-Location <String>] [-ResourceGroup <String>]
 [-ResourceName <String>] [-ServerEndpoint <String>] [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureSqlDatabaseManagedInstanceDataSource.

## EXAMPLES

### Contoh 1: Membuat Azure SQL objek sumber data instans terkelola database
```powershell
PS C:\> New-AzPurviewAzureSqlDatabaseManagedInstanceDataSourceObject -Kind 'AzureSqlDatabaseManagedInstance' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -ServerEndpoint 'tcp:sqlause.public.3b6a39.database.windows.net,3342'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : AzureSqlDatabaseManagedInstance
LastModifiedAt           :
Location                 :
Name                     :
ResourceGroup            :
ResourceName             :
Scan                     :
ServerEndpoint           : tcp:sqlause.public.3b6a39.database.windows.net,3342
SubscriptionId           :
```

Membuat Azure SQL objek sumber data instans terkelola database

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureSqlDatabaseManagedInstanceDataSource

## NOTES

ALIAS

## RELATED LINKS
