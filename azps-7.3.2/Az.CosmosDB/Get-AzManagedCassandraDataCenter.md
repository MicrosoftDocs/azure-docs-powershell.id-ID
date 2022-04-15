---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azmanagedcassandradatacenter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzManagedCassandraDataCenter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzManagedCassandraDataCenter.md
ms.openlocfilehash: a294a0eff357bac5090a10d294b551b22ac9f4e2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142216819"
---
# Get-AzManagedCassandraDataCenter

## SYNOPSIS
Mendapatkan Instans Terkelola Azure untuk pusat data Apache Cassandra.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/get-azmanagedcassandradatacenter) untuk informasi terbaru.

## SYNTAX

### NameParameterSet (Default)
```
Get-AzManagedCassandraDataCenter -ResourceGroupName <String> -ClusterName <String> -DataCenterName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzManagedCassandraDataCenter -ResourceId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentObjectParameterSet
```
Get-AzManagedCassandraDataCenter -ParentObject <PSClusterResource>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzManagedCassandraDataCenter** mengambil properti pusat data Cassandra yang dikelola yang sudah ada.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzManagedCassandraDataCenter -ResourceGroupName {resourceGroupName} -ClusterName {clusterName} -DataCenterName {dataCenterName}
```

### Contoh 2
```powershell
PS C:\> Get-AzManagedCassandraDataCenter -ResourceId {resourceId}
```

### Contoh 3
```powershell
PS C:\> $clusterResource | Get-AzManagedCassandraDataCenter
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

### -ParentObject
Objek kluster Cassandra terkelola

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource
Parameter Sets: ParentObjectParameterSet
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
Id sumber daya dari kluster Cassandra yang dikelola.

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

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## CATATAN

## RELATED LINKS
