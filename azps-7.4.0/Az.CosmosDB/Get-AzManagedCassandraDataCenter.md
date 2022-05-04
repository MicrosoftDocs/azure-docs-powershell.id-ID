---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azmanagedcassandradatacenter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzManagedCassandraDataCenter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzManagedCassandraDataCenter.md
ms.openlocfilehash: ad607593539916c38e5021d9aab7189ac48aa0a8
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144594700"
---
# Get-AzManagedCassandraDatacenter

## SYNOPSIS
Mendapatkan pusat data Azure Managed Instances for Apache Cassandra.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/get-azmanagedcassandradatacenter) untuk informasi terbaru.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzManagedCassandraDatacenter -ResourceGroupName <String> -ClusterName <String> [-DataCenterName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzManagedCassandraDatacenter -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByObjectParameterSet
```
Get-AzManagedCassandraDatacenter -InputObject <PSDataCenterResource> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzManagedCassandraDatacenter -ParentObject <PSClusterResource> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzManagedCassandraDataCenter** mengambil properti pusat data Cassandra terkelola yang ada.

## EXAMPLES

### Contoh 1
```powershell
Get-AzManagedCassandraDataCenter -ResourceGroupName {resourceGroupName} -ClusterName {clusterName} -DataCenterName {dataCenterName}
```

### Contoh 2
```powershell
Get-AzManagedCassandraDataCenter -ResourceId {resourceId}
```

### Contoh 3
```powershell
$clusterResource | Get-AzManagedCassandraDataCenter
```

## PARAMETERS

### -ClusterName
Nama kluster Cassandra terkelola.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataCenterName
Nama pusat data Cassandra terkelola.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Pusat Data Cassandra Terkelola

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ParentObject
Objek kluster Cassandra terkelola

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya kluster Cassandra terkelola.

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
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

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## NOTES

## RELATED LINKS
