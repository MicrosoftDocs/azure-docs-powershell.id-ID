---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azmanagedcassandradatacenter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraDataCenter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraDataCenter.md
ms.openlocfilehash: 53819e611f08ef6f2974c9dbad3a34a1ebccb4ad
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136542092"
---
# New-AzManagedCassandraDataCenter

## SYNOPSIS
Membuat Azure Managed Instances baru untuk Apache Apache Apache data center.

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
Cmdlet **New-AzManagedCass cmdletDataCenter** membuat pusat data Cmdlet yang dikelola baru.

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
URI ke tombol KeyVault yang digunakan untuk mengenkripsi cadangan kluster. Jika dihilangkan, tombol Azure sendiri akan digunakan.

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

### -Base64EncodedCassyamlFragment
Konfigurasi fragmen untuk disertakan di simpul `cassandra.yaml` dari pusat data ini, Base64 dikodekan.

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
Nama kluster Properti terkelola.

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
Id sumber daya subnet jaringan virtual tempat Terkelola subnet seharusnya melampirkan antarmuka jaringan.

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
Jumlah disk data yang akan tersambung ke setiap simpul dalam kluster.

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
Lokasi untuk membuat kluster Premium yang dikelola di.

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
URI tombol KeyVault digunakan untuk mengenkripsi data yang disimpan dalam kluster. Jika dihilangkan, tombol Azure sendiri akan digunakan.

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
Jumlah node yang dibuat di pusat data ini.

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
Objek kluster Tujuan untuk membuat pusat data.

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
Nama sku mesin virtual yang akan digunakan untuk simpul di pusat data ini. Lihat [dokumentasi untuk](https://docs.microsoft.com/en-us/azure/managed-instance-apache-cassandra/create-cluster-cli) sku yang didukung.

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
Hashtaf tag yang diatur pada sumber daya pusat data.

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
Jika diatur, alokasikan node di pusat data ini menggunakan zona ketersediaan jika didukung di kawasan tersebut.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDataCenterResource

## CATATAN

## RELATED LINKS
