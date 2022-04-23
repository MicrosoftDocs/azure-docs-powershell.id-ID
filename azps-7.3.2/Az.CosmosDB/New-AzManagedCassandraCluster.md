---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azmanagedcassandracluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzManagedCassandraCluster.md
ms.openlocfilehash: 21e32e33bbc5051cb5c32b669c20bd12bd7d8bb1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143246213"
---
# New-AzManagedCassandraCluster

## SYNOPSIS
Membuat Instans Terkelola Azure baru untuk klaster Apache Cassandra.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/new-azmanagedcassandracluster) untuk informasi terbaru.

## SYNTAX

### NameParameterSet (Default)
```
New-AzManagedCassandraCluster 
 -ResourceGroupName <String> 
 -ClusterName <String>
 -DelegatedManagementSubnetId <String>
 -Location <String>
 [-Tag <Hashtable>]
 [-InitialCassandraAdminPassword <String>]
 [-ExternalGossipCertificate <String[]>]
 [-ClientCertificate <String[]>]
 [-RepairEnabled <bool>]
 [-TimeBetweenBackupInHours <int>]
 [-AuthenticationMethod <String>]
 [-CassandraVersion <String>]
 [-ExternalSeedNode <String[]>]
 [-ClusterNameOverride <String>]
 [-RestoreFromBackupId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzManagedCassandraCluster** menciptakan kluster Cassandra yang dikelola baru.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzManagedCassandraCluster `
 -ResourceGroupName {resourceGroupName} `
 -ClusterName {clusterName} `
 -DelegatedManagementSubnetId {resourceId} `
 -Location {location} `
 -InitialCassandraAdminPassword {password}
```

## PARAMETERS

### -AuthenticationMethod
Cara mengautentikasi klien, salah satu dari `Cassandra` (untuk autentikasi kata sandi), `Ldap` (untuk autentikasi LDAP/AD), atau `None` (tanpa memerlukan autentikasi).

```yaml
Type: System.String
Parameter Sets: (All)

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterNameOverride
Jika nama kluster di `cassandra.yaml` perlu berbeda dari argumen `-ClusterName`, gunakan properti ini untuk mengatur.

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

### -ExternalGossipCertificate
Daftar sertifikat TLS tambahan yang akan digunakan kluster Cassandra yang dikelola untuk mengautentikasi gosip.

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
Daftar alamat IP dari node benih eksternal untuk menjemput kluster ini.

```yaml
Type: System.String[]
Parameter Sets: (All)

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialCassandraAdminPassword
Kata sandi awal untuk akun admin pada kluster jika kluster menggunakan kata sandi auth.

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

### -RepairEnabled
Jika benar, Cassandra yang dikelola akan menjalankan reaper untuk memperbaiki database secara rutin. Ini seharusnya hanya dinonaktifkan untuk kluster hibrid yang menjalankan proses perbaikan mereka sendiri di luar Azure.

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

### -RestoreFromBackupId
Id sumber daya cadangan untuk dipulihkan ke dalam kluster ini. Jika dihilangkan, membuat klaster kosong baru.

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
Jam antara mengambil cadangan penuh dari kluster.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSClusterResource

## NOTES

## RELATED LINKS
