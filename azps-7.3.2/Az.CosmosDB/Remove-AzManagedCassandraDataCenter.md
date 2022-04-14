---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/remove-azmanagedcassandradatacenter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Remove-AzManagedCassandraDataCenter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Remove-AzManagedCassandraDataCenter.md
ms.openlocfilehash: 425a7872c0fe3c8ff3a2ecc39fad6e7f93b3546b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141852836"
---
# Remove-AzManagedCassandraDataCenter

## SYNOPSIS
Menghapus Instans terkelola Azure untuk pusat data Apache Cassandra.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/remove-azmanagedcassandradatacenter) untuk informasi terbaru.

## SYNTAX

### NameParameterSet (Default)
```
Remove-AzManagedCassandraDataCenter 
 -ResourceGroupName <String> 
 -ClusterName <String>
 -DataCenterName <String>
 [-AsJob]
 [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Remove-AzManagedCassandraDataCenter 
 -ResourceId <String> 
 [-AsJob]
 [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ObjectParameterSet
```
Remove-AzManagedCassandraDataCenter 
 -InputObject <PSDataCenterResource> 
 [-AsJob]
 [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Remove-AzManagedCassandraDataCenter** menghapus pusat data Cassandra yang dikelola.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Remove-AzManagedCassandraDataCenter `
 -ResourceGroupName {resourceGroupName} `
 -ClusterName {clusterName}
 -DataCenterName {dataCenterName}
```

### Contoh 2
```powershell
PS C:\> Remove-AzManagedCassandraDataCenter -ResourceId {dataCenterResourceId}
```

### Contoh 3
```powershell
PS C:\> $dataCenterResource | Remove-AzManagedCassandraDataCenter
```

## PARAMETERS

### -ClusterName
Nama kluster Cassandra yang dikelola.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataCenterName
Nama pusat data Cassandra yang dikelola.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
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
Objek pusat data Cassandra terkelola

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource
Parameter Sets: ObjectParameterSet
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
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya dari Cassandra DataCenter yang dikelola.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## OUTPUTS

## CATATAN

## RELATED LINKS
