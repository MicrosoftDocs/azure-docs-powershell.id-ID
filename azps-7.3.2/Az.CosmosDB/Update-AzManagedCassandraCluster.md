---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/update-azmanagedcassandracluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzManagedCassandraCluster.md
ms.openlocfilehash: e341e553f52ca541b06bc1438084717ad5e66454
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140394906"
---
# Update-AzManagedCassandraCluster

## SYNOPSIS
Memperbarui Azure Managed Instances yang sudah ada untuk kluster Apache Apache Apache.

## SYNTAX

### NameParameterSet (Default)
```
Update-AzManagedCassandraCluster 
 -ResourceGroupName <String> 
 -ClusterName <String>
 [-ExternalGossipCertificate <String[]>]
 [-ClientCertificate <String[]>]
 [-RepairEnabled <bool>]
 [-TimeBetweenBackupInHours <int>]
 [-AuthenticationMethod <String>]
 [-CassandraVersion <String>]
 [-ExternalSeedNode <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Update-AzManagedCassandraCluster 
 -ResourceId <String> 
 [-Tag <Hashtable>]
 [-ExternalGossipCertificate <String[]>]
 [-ClientCertificate <String[]>]
 [-RepairEnabled <bool>]
 [-TimeBetweenBackupInHours <int>]
 [-AuthenticationMethod <String>]
 [-CassandraVersion <String>]
 [-ExternalSeedNode <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ObjectParameterSet
```
Update-AzManagedCassandraCluster 
 -InputObject <PSClusterResource> 
 [-Tag <Hashtable>]
 [-ExternalGossipCertificate <String[]>]
 [-ClientCertificate <String[]>]
 [-RepairEnabled <bool>]
 [-TimeBetweenBackupInHours <int>]
 [-AuthenticationMethod <String>]
 [-CassandraVersion <String>]
 [-ExternalSeedNode <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzManagedCass clusterCluster** mengubah kluster Cmdlet Cmdlet Kelola Kelola yang sudah ada.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Update-AzManagedCassandraCluster `
 -ResourceGroupName {resourceGroupName} `
 -ClusterName {clusterName} `
 -ExternalGossipCertificate {certificates} `
 -ClientCertificate {certificates} `
 -RepairEnabled {boolean}
```

### Contoh 2
```powershell
PS C:\> Update-AzManagedCassandraCluster `
 -ResourceId {clusterResourceId} `
 -ExternalGossipCertificate {certificates} `
 -ClientCertificate {certificates} `
 -RepairEnabled {boolean}
```

### Contoh 3
```powershell
PS C:\> $clusterResource | Update-AzManagedCassandraCluster `
 -ExternalGossipCertificate {certificates} `
 -ClientCertificate {certificates} `
 -RepairEnabled {boolean}
```

## PARAMETERS

### -AuthenticationMethod
Cara mengautentikasi klien, salah satu dari `Cassandra` (untuk autentikasi kata sandi), `Ldap` (untuk autentikasi LDAP/AD), `None` atau (untuk tidak memerlukan autentikasi).

```yaml
Type: System.String
Parameter Sets: (All)

Required: False
Position: Named
Default value: Cassandra
Accept pipeline input: False
Accept wildcard characters: False
```

### -B arc arcVersion
Versi Desktop mana yang akan dijalankan. Saat ini hanya 3,11 yang didukung.

```yaml
Type: System.String
Parameter Sets: (All)

Required: False
Position: Named
Default value: 3.11
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientCertificate
Daftar sertifikat TLS untuk digunakan untuk mengautentikasi klien. Jika dihilangkan, semua koneksi klien masih tersambung dengan TLS, tetapi tidak diperlukan untuk menyediakan sertifikat klien yang valid. Jika ini disediakan, klien sebagian besar menyediakan sertifikat klien TLS yang valid untuk tersambung ke kluster.

```yaml
Type: System.String[]
Parameter Sets: (All)

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
Parameter Sets: (All)
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
Daftar sertifikat TLS tambahan yang dikelola kluster Tls akan digunakan untuk mengautentikasi gossip.

```yaml
Type: System.String[]
Parameter Sets: (All)

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalSeedNode
Daftar alamat IP node awal eksternal untuk menjembatani kluster ini.

```yaml
Type: System.String[]
Parameter Sets: (All)

Required: False
Position: Named
Default value: None
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

### -RepairEnabled
Jika true, managed Hosting akan menjalankan reaper untuk memperbaiki database secara teratur. Hal ini hanya akan dinonaktifkan untuk kluster hibrid yang menjalankan proses perbaikan mereka sendiri di luar Azure.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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

### -TimeBetweenBackupInHours
Jam antara membuat cadangan penuh kluster.

```yaml
Type: System.Integer
Parameter Sets: (All))
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## CATATAN

## RELATED LINKS
