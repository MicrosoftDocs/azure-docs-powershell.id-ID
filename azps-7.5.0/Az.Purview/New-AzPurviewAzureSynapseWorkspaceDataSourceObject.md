---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureSynapseWorkspaceDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSynapseWorkspaceDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSynapseWorkspaceDataSourceObject.md
ms.openlocfilehash: fe258c9313b06c8d8451eb9a71bb6718f48993b6
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144224111"
---
# New-AzPurviewAzureSynapseWorkspaceDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk AzureSynapseWorkspaceDataSource.

## SYNTAX

```
New-AzPurviewAzureSynapseWorkspaceDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-DedicatedSqlEndpoint <String>] [-Location <String>] [-ResourceGroup <String>]
 [-ResourceName <String>] [-ServerlessSqlEndpoint <String>] [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureSynapseWorkspaceDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data ruang kerja Azure Synapse
```powershell
PS C:\> New-AzPurviewAzureSynapseWorkspaceDataSourceObject -Kind 'AzureSynapseWorkspace' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -DedicatedSqlEndpoint 'g1euap.sql.azuresynapse.net' -ServerlessSqlEndpoint 'rg1euap-ondemand.sql.azuresynapse.net'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
DedicatedSqlEndpoint     : g1euap.sql.azuresynapse.net
Id                       :
Kind                     : AzureSynapseWorkspace
LastModifiedAt           :
Location                 :
Name                     :
ResourceGroup            :
ResourceName             :
Scan                     :
ServerlessSqlEndpoint    : rg1euap-ondemand.sql.azuresynapse.net
SubscriptionId           :
```

Membuat objek sumber data ruang kerja Azure Synapse

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

### -DedicatedSqlEndpoint

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

### -ServerlessSqlEndpoint

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureSynapseWorkspaceDataSource

## NOTES

ALIAS

## RELATED LINKS
