---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azmanagedcassandracluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraCluster.md
ms.openlocfilehash: 92c4481a93d0070873c1c219ee66e0a63f01bd76
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145528759"
---
# New-AzManagedCassandraCluster

## SYNOPSIS
Membuat kluster Azure Managed Instances for Apache Cassandra baru.

## SYNTAX

```
New-AzManagedCassandraCluster -Location <String> -DelegatedManagementSubnetId <String>
 [-InitialCassandraAdminPassword <String>] [-ClusterNameOverride <String>] [-RestoreFromBackupId <String>]
 -ResourceGroupName <String> -ClusterName <String> [-Tag <Hashtable>] [-ExternalGossipCertificate <String[]>]
 [-ClientCertificate <String[]>] [-RepairEnabled <Boolean>] [-TimeBetweenBackupInHours <Int32>]
 [-AuthenticationMethod <String>] [-CassandraVersion <String>] [-ExternalSeedNode <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet New-AzManagedCassandraCluster** membuat kluster Cassandra terkelola baru.

## EXAMPLES

### Contoh 1
```powershell
New-AzManagedCassandraCluster `
 -ResourceGroupName "resourceGroupName" `
 -ClusterName "clusterName" `
 -DelegatedManagementSubnetId "resourceId" `
 -Location "location" `
 -InitialCassandraAdminPassword "password"
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
Daftar sertifikat TLS yang akan digunakan untuk mengautentikasi klien. Jika ini dihilangkan, semua koneksi klien masih terhubung dengan TLS, tetapi tidak diperlukan untuk memberikan sertifikat klien yang valid. Jika ini disediakan, klien paling banyak menyediakan sertifikat klien TLS yang valid untuk terhubung ke kluster.

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
Nama kluster Cassandra terkelola.

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

### -ClusterNameOverride
Jika nama kluster di `cassandra.yaml` harus berbeda dari `-ClusterName`argumen , gunakan properti ini untuk mengatur.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Same as -ClusterName
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

### -DelegatedManagementSubnetId
Id sumber daya subnet jaringan virtual tempat Cassandra terkelola harus melampirkan antarmuka jaringan.

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

### -ExternalGossipCertificate
Daftar sertifikat TLS tambahan yang akan digunakan kluster Cassandra terkelola untuk mengautentikasi gosip.

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
Daftar alamat IP node benih eksternal untuk menjemput kluster ini.

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

### -InitialCassandraAdminPassword
Kata sandi awal untuk akun admin pada kluster jika kluster menggunakan autentikasi kata sandi.

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

### -Lokasi
Lokasi untuk membuat kluster Cassandra terkelola.

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
Jika true, Cassandra yang dikelola akan menjalankan reaper untuk memperbaiki database secara teratur. Ini hanya boleh dinonaktifkan untuk kluster hibrid yang menjalankan proses perbaikan mereka sendiri di luar Azure.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreFromBackupId
Id sumber daya cadangan untuk dipulihkan ke kluster ini. Jika dihilangkan, membuat kluster baru yang kosong.

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

### -Tag
Hashtable tag untuk diatur pada sumber daya kluster.

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
Jam antara mengambil cadangan penuh kluster.

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

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## NOTES

## RELATED LINKS
