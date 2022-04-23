---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/update-azmanagedcassandracluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraCluster.md
ms.openlocfilehash: 2ebbceff47c428dfa65218f9856682a538245730
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143125955"
---
# Update-AzManagedCassandraCluster

## SYNOPSIS
Perbarui Instans Terkelola Azure yang sudah ada untuk klaster Apache Cassandra.

## SYNTAX

### ByNameParameterSet (Default)
```
Update-AzManagedCassandraCluster -ResourceGroupName <String> -ClusterName <String> [-Tag <Hashtable>]
 [-ExternalGossipCertificate <String[]>] [-ClientCertificate <String[]>] [-RepairEnabled <Boolean>]
 [-TimeBetweenBackupInHours <Int32>] [-AuthenticationMethod <String>] [-CassandraVersion <String>]
 [-ExternalSeedNode <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Update-AzManagedCassandraCluster -ResourceId <String> [-Tag <Hashtable>]
 [-ExternalGossipCertificate <String[]>] [-ClientCertificate <String[]>] [-RepairEnabled <Boolean>]
 [-TimeBetweenBackupInHours <Int32>] [-AuthenticationMethod <String>] [-CassandraVersion <String>]
 [-ExternalSeedNode <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByObjectParameterSet
```
Update-AzManagedCassandraCluster -InputObject <PSClusterResource> [-Tag <Hashtable>]
 [-ExternalGossipCertificate <String[]>] [-ClientCertificate <String[]>] [-RepairEnabled <Boolean>]
 [-TimeBetweenBackupInHours <Int32>] [-AuthenticationMethod <String>] [-CassandraVersion <String>]
 [-ExternalSeedNode <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzManagedCassandraCluster** mengubah kluster Cassandra terkelola yang sudah ada.

## EXAMPLES

### Contoh 1
```powershell
Update-AzManagedCassandraCluster `
 -ResourceGroupName {resourceGroupName} `
 -ClusterName {clusterName} `
 -ExternalGossipCertificate {certificates} `
 -ClientCertificate {certificates} `
 -RepairEnabled {boolean}
```

### Contoh 2
```powershell
Update-AzManagedCassandraCluster `
 -ResourceId {clusterResourceId} `
 -ExternalGossipCertificate {certificates} `
 -ClientCertificate {certificates} `
 -RepairEnabled {boolean}
```

### Contoh 3
```powershell
$clusterResource | Update-AzManagedCassandraCluster `
 -ExternalGossipCertificate {certificates} `
 -ClientCertificate {certificates} `
 -RepairEnabled {boolean}
```

## PARAMETERS

### -AuthenticationMethod
Cara mengautentikasi klien, salah satu dari `Cassandra` (untuk autentikasi kata sandi), `Ldap` (untuk autentikasi LDAP/AD), atau `None` (tanpa memerlukan autentikasi).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Cassandra
Accept pipeline input: False
Accept wildcard characters: False
```

### -CassandraVersion
Versi Cassandra mana yang akan dijalankan. Saat ini hanya 3.11 yang didukung.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 3.11
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientCertificate
Daftar sertifikat TLS untuk digunakan untuk mengautentikasi klien. Jika ini dihilangkan, semua koneksi klien masih terhubung dengan TLS, tetapi tidak diharuskan untuk menyediakan sertifikat klien yang valid. Jika ini disediakan, klien paling banyak menyediakan sertifikat klien TLS yang valid untuk menyambungkan ke kluster.

```yaml
Type: System.String[]
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

### -ExternalGossipCertificate
Daftar sertifikat TLS tambahan yang akan digunakan kluster Cassandra yang dikelola untuk mengautentikasi gosip.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalSeedNode
Daftar alamat IP dari node benih eksternal untuk menjemput kluster ini.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Cluster Cassandra terkelola

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RepairEnabled
Jika benar, Cassandra yang dikelola akan menjalankan reaper untuk memperbaiki database secara rutin. Ini seharusnya hanya dinonaktifkan untuk kluster hibrid yang menjalankan proses perbaikan mereka sendiri di luar Azure.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
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

### -Tag
Hashtable tag untuk diatur pada sumber daya pusat data.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeBetweenBackupInHours
Jam antara mengambil cadangan penuh dari kluster.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## NOTES

## RELATED LINKS
