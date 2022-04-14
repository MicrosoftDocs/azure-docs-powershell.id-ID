---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azmanagedcassandradatacenter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraDataCenter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraDataCenter.md
ms.openlocfilehash: 8258d0698728a84fef31a6825a308c510efbed6c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141941829"
---
# New-AzManagedCassandraDataCenter

## SYNOPSIS
Buat Instans Terkelola Azure baru untuk pusat data Apache Cassandra.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/new-azmanagedcassandradatacenter) untuk informasi terbaru.

## SYNTAX

### NameParameterSet (Default)
```
New-AzManagedCassandraDataCenter 
 -ResourceGroupName <String> 
 -ClusterName <String>
 -DataCenterName <String>
 -DelegatedSubnetId <String>
 -Location <String>
 -NodeCount <int>
 [-Tag <Hashtable>]
 [-Base64EncodedCassandraYamlFragment <String>]
 [-ManagedDiskCustomerKeyUri <String>]
 [-BackupStorageCustomerKeyUri <String>]
 [-Sku <String>]
 [-DiskCapacity <int>]
 [-UseAvailabilityZone]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentObjectParameterSet
```
New-AzManagedCassandraDataCenter 
 -ParentObject <PSClusterResource>
 -DataCenterName <String>
 -Location <String>
 -DelegatedSubnetId <String>
 -NodeCount <int>
 [-Tag <Hashtable>]
 [-Base64EncodedCassandraYamlFragment <String>]
 [-ManagedDiskCustomerKeyUri <String>]
 [-BackupStorageCustomerKeyUri <String>]
 [-Sku <String>]
 [-DiskCapacity <int>]
 [-UseAvailabilityZone]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet New-AzManagedCassandraDataCenter** membuat pusat data Cassandra yang dikelola baru.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzManagedCassandraDataCenter `
 -ResourceGroupName {resourceGroupName} `
 -ClusterName {clusterName} `
 -DataCenterName {dataCenterName} `
 -DelegatedSubnetId {resourceId} `
 -Location {location} `
 -NodeCount {N}
```

## PARAMETERS

### -BackupStorageCustomerKeyUri
URI ke kunci KeyVault yang digunakan untuk mengenkripsi cadangan kluster. Jika dihilangkan, kunci Azure sendiri akan digunakan.

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

### -DelegatedSubnetId
Id sumber daya subnet jaringan virtual tempat Cassandra yang dikelola harus melampirkan antarmuka jaringan.

```yaml
Type: System.String
Parameter Sets: (All)

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskCapacity
Jumlah disk data yang akan disambungkan ke setiap simpul dalam kluster.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi untuk membuat kluster Cassandra yang dikelola.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskCustomerKeyUri
URI kunci KeyVault digunakan untuk mengenkripsi data saat disimpan di kluster. Jika dihilangkan, kunci Azure sendiri akan digunakan.

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

### -Sku
Nama sku mesin virtual yang digunakan untuk simpul di pusat data ini. Lihat [dokumentasi](https://docs.microsoft.com/en-us/azure/managed-instance-apache-cassandra/create-cluster-cli) untuk sku yang didukung.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Standard_DS14_v2
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

### -UseAvailabilityZone
Jika diatur, alokasikan simpul di pusat data ini menggunakan zona ketersediaan jika didukung di kawasan.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
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
