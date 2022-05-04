---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/update-azmanagedcassandradatacenter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraDataCenter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraDataCenter.md
ms.openlocfilehash: 4ebc35d0f2f269a730e671dcaf2fd8cf6b7c8c0c
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144662058"
---
# Update-AzManagedCassandraDatacenter

## SYNOPSIS
Perbarui pusat data Azure Managed Instances for Apache Cassandra yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/update-azmanagedcassandradatacenter) untuk informasi terbaru.

## SYNTAX

### ByNameParameterSet (Default)
```
Update-AzManagedCassandraDatacenter -ResourceGroupName <String> -ClusterName <String> -DatacenterName <String>
 [-NodeCount <Int32>] [-Base64EncodedCassandraYamlFragment <String>] [-BackupStorageCustomerKeyUri <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Update-AzManagedCassandraDatacenter -ResourceId <String> [-NodeCount <Int32>]
 [-Base64EncodedCassandraYamlFragment <String>] [-BackupStorageCustomerKeyUri <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Update-AzManagedCassandraDatacenter -InputObject <PSDataCenterResource> [-NodeCount <Int32>]
 [-Base64EncodedCassandraYamlFragment <String>] [-BackupStorageCustomerKeyUri <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Update-AzManagedCassandraDatacenter -ParentObject <PSClusterResource> [-NodeCount <Int32>]
 [-Base64EncodedCassandraYamlFragment <String>] [-BackupStorageCustomerKeyUri <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Update-AzManagedCassandraDataCenter** memperbarui pusat data Cassandra terkelola yang ada.

## EXAMPLES

### Contoh 1
```powershell
Update-AzManagedCassandraDataCenter `
 -ResourceGroupName {resourceGroupName} `
 -ClusterName {clusterName} `
 -DataCenterName {dataCenterName} `
 -NodeCount {N}
```

## PARAMETERS

### -BackupStorageCustomerKeyUri
URI ke kunci KeyVault yang digunakan untuk mengenkripsi cadangan Cassandra. Jika tidak diatur, akan menggunakan kunci Azure sendiri. Pastikan identitas kluster yang ditetapkan sistem telah diberi izin yang sesuai (izin kunci get/wrap/unwrap) pada kunci.

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

### -Base64EncodedCassandraYamlFragment
Fragmen konfigurasi untuk disertakan pada `cassandra.yaml` simpul pusat data ini, dikodekan Base64.

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

### -DatacenterName
Nama Pusat Data Cassandra Terkelola.

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

### -NodeCount
Jumlah simpul yang akan dibuat di pusat data ini.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentObject
Objek kluster Cassandra untuk membuat pusat data.

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
ResourceId sumber daya.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## NOTES

## RELATED LINKS
