---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/update-azmanagedcassandradatacenter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraDataCenter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraDataCenter.md
ms.openlocfilehash: 405bdfbd3f8fe01504ceee9a7efd533196f10f83
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143245997"
---
# Update-AzManagedCassandraDataCenter

## SYNOPSIS
Perbarui Instans Terkelola Azure yang sudah ada untuk pusat data Apache Cassandra.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/update-azmanagedcassandradatacenter) untuk informasi terbaru.

## SYNTAX

### NameParameterSet (Default)
```
Update-AzManagedCassandraDataCenter 
 -ResourceGroupName <String> 
 -ClusterName <String>
 -DataCenterName <String>
 [-NodeCount <int>]
 [-Tag <Hashtable>]
 [-Base64EncodedCassandraYamlFragment <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Update-AzManagedCassandraDataCenter 
 -ResourceId <String> 
 [-NodeCount <int>]
 [-Tag <Hashtable>]
 [-Base64EncodedCassandraYamlFragment <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ObjectParameterSet
```
Update-AzManagedCassandraDataCenter 
 -InputObject <PSDataCenterResource> 
 [-NodeCount <int>]
 [-Tag <Hashtable>]
 [-Base64EncodedCassandraYamlFragment <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentObjectParameterSet
```
Update-AzManagedCassandraDataCenter 
 -ParentObject <PSClusterResource>
 -DataCenterName <String>
 [-NodeCount <int>]
 [-Tag <Hashtable>]
 [-Base64EncodedCassandraYamlFragment <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Update-AzManagedCassandraDataCenter** memperbarui pusat data Cassandra yang dikelola yang sudah ada.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Update-AzManagedCassandraDataCenter `
 -ResourceGroupName {resourceGroupName} `
 -ClusterName {clusterName} `
 -DataCenterName {dataCenterName} `
 -NodeCount {N}
```

## PARAMETERS

### -Base64EncodedCassandraYamlFragment
Fragmen konfigurasi untuk disertakan dalam `cassandra.yaml` simpul pusat data ini, base64 dikodekan.

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

### -NodeCount
Jumlah node yang akan dibuat di pusat data ini.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentObject
Objek kluster Cassandra untuk membuat pusat data di dalamnya.

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

### -Tag
Hashtable tag untuk diatur pada sumber daya pusat data.

```yaml
Type: System.Hashtable
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

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## NOTES

## RELATED LINKS
