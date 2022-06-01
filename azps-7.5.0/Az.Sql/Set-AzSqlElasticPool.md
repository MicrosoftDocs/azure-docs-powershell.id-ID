---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 555D58AB-1361-4BB1-ACD0-905C3C6F4F7E
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqlelasticpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlElasticPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlElasticPool.md
ms.openlocfilehash: 4529735b4455957e70f6225509ecdd45548730f8
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145972957"
---
# Set-AzSqlElasticPool

## SYNOPSIS
Memodifikasi properti kumpulan database elastis di Azure SQL Database.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/set-azsqlelasticpool) untuk informasi terbaru.

## SYNTAX

### DtuBasedPool (Default)
```
Set-AzSqlElasticPool [-ElasticPoolName] <String> [-Edition <String>] [-Dtu <Int32>] [-StorageMB <Int32>]
 [-DatabaseDtuMin <Int32>] [-DatabaseDtuMax <Int32>] [-Tags <Hashtable>] [-ZoneRedundant]
 [-LicenseType <String>] [-MaintenanceConfigurationId <String>] [-HighAvailabilityReplicaCount <Int32>]
 [-AsJob] [-ServerName] <String> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VcoreBasedPool
```
Set-AzSqlElasticPool [-ElasticPoolName] <String> [-Edition <String>] [-StorageMB <Int32>] [-VCore <Int32>]
 [-ComputeGeneration <String>] [-DatabaseVCoreMin <Double>] [-DatabaseVCoreMax <Double>] [-Tags <Hashtable>]
 [-ZoneRedundant] [-LicenseType <String>] [-MaintenanceConfigurationId <String>]
 [-HighAvailabilityReplicaCount <Int32>] [-AsJob] [-ServerName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlElasticPool** menetapkan properti untuk kumpulan elastis di Azure SQL Database. Cmdlet ini dapat memodifikasi eDTU per kumpulan (*Dtu*), ukuran maksimum penyimpanan per kumpulan (*StorageMB*), eDTU maksimum per database (*DatabaseDtuMax), dan eDTU* minimum per database (*DatabaseDtuMin*).
Beberapa parameter (*-Dtu, -DatabaseDtuMin, dan -DatabaseDtuMax*) memerlukan nilai yang ditetapkan berasal dari daftar nilai yang valid untuk parameter tersebut. Misalnya, -DatabaseDtuMax untuk kumpulan eDTU Standar 100 hanya dapat diatur ke 10, 20, 50, atau 100.  Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran spesifik Anda di [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).

## EXAMPLES

### Contoh 1: Mengubah properti untuk kumpulan elastis
```powershell
Set-AzSqlElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -Dtu 1000 -DatabaseDtuMax 100 -DatabaseDtuMin 20
```

```output
ResourceId        : /subscriptions/00000000-0000-0000-0000-000000000001/resourceGroups/resourcegroup01/providers/Microsoft.Sql/servers/Server01/elasticPools/ElasticPool01
ResourceGroupName : ResourceGroup01
ServerName        : Server01
ElasticPoolName   : ElasticPool01
Location          : Central US
CreationDate      : 8/26/2015 10:00:17 PM
State             : Ready
Edition           : Standard
Dtu               : 200
DatabaseDtuMax    : 100
DatabaseDtuMin    : 20
StorageMB         : 204800
Tags              :
```

Perintah ini memodifikasi properti untuk kumpulan elastis bernama elasticpool01. Perintah menetapkan jumlah DTU untuk kumpulan elastis menjadi 1000 dan menetapkan DTU minimum dan maksimum.

### Contoh 2: Mengubah ukuran maksimum penyimpanan kumpulan elastis
```powershell
Set-AzSqlElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -StorageMB 2097152
```

```output
ResourceId        : /subscriptions/00000000-0000-0000-0000-000000000001/resourceGroups/resourcegroup01/providers/Microsoft.Sql/servers/Server01/elasticPools/ElasticPool01
ResourceGroupName : ResourceGroup01
ServerName        : Server01
ElasticPoolName   : ElasticPool01
Location          : Central US
CreationDate      : 8/26/2015 10:00:17 PM
State             : Ready
Edition           : Premium
Dtu               : 200
DatabaseDtuMax    : 100
DatabaseDtuMin    : 20
StorageMB         : 2097152
Tags              :
```

Perintah ini memodifikasi properti untuk kumpulan elastis bernama elasticpool01. Perintah mengatur penyimpanan maks untuk kumpulan elastis menjadi 2 TB.

### Contoh: 3

Memodifikasi properti kumpulan database elastis di Azure SQL Database. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Set-AzSqlElasticPool -Dtu 1000 -Edition 'GeneralPurpose' -ElasticPoolName 'ElasticPool01' -ResourceGroupName 'ResourceGroup01' -ServerName 'Server01'
```

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputeGeneration
Pembuatan komputasi yang akan ditetapkan.

```yaml
Type: System.String
Parameter Sets: VcoreBasedPool
Aliases: Family

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseDtuMax
Menentukan jumlah maksimum DTU yang dapat digunakan oleh database tunggal dalam kumpulan.
Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran spesifik Anda di [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).
Nilai default untuk edisi yang berbeda adalah sebagai berikut:
- Dasar.  5 DTU
- Standar. 100 DTU
- Premium. 125 DTU

```yaml
Type: System.Int32
Parameter Sets: DtuBasedPool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseDtuMin
Menentukan jumlah minimum DTU yang dijamin kumpulan elastis ke semua database dalam kumpulan.
Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran spesifik Anda di [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).
Nilai defaultnya adalah nol (0).

```yaml
Type: System.Int32
Parameter Sets: DtuBasedPool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseVCoreMax
Nomor VCore maksimum yang dapat digunakan SqlAzure Database di kumpulan.

```yaml
Type: System.Double
Parameter Sets: VcoreBasedPool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseVCoreMin
Nomor VCore minimum yang dapat digunakan SqlAzure Database di kumpulan.

```yaml
Type: System.Double
Parameter Sets: VcoreBasedPool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Dtu
Menentukan jumlah total DTU bersama untuk kumpulan elastis.
Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran spesifik Anda di [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).
Nilai default untuk edisi yang berbeda adalah sebagai berikut:
- Dasar. 100 DTU
- Standar. 100 DTU
- Premium. 125 DTU

```yaml
Type: System.Int32
Parameter Sets: DtuBasedPool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Edisi
Menentukan edisi Azure SQL Database untuk kumpulan elastis. Anda tidak dapat mengubah edisi. Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak ada
- Dasar
- Standard
- Premium
- Gudang Data
- Gratis
- Stretch
- GeneralPurpose
- BusinessCritical

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

### -ElasticPoolName
Menentukan nama kumpulan elastis.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HighAvailabilityReplicaCount
Jumlah total replika ketersediaan tinggi yang terkait dengan kumpulan elastis.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Jenis lisensi untuk database Azure Sql.

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

### -MaintenanceConfigurationId
Id konfigurasi Pemeliharaan untuk SQL Elastic Pool.

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat kumpulan elastis ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server yang menghosting kumpulan elastis.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageMB
Menentukan batas penyimpanan, dalam megabyte, untuk kumpulan elastis. Untuk informasi selengkapnya, lihat cmdlet New-AzSqlElasticPool.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
Menentukan kamus pasangan Kunci-nilai yang dikaitkan cmdlet ini dengan kumpulan elastis dalam bentuk tabel hash. Misalnya: `@{key0="value0";"key 1"=$null;key2="value2"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VCore
Jumlah total bersama Vcore untuk Kumpulan Elastis Azure Sql.

```yaml
Type: System.Int32
Parameter Sets: VcoreBasedPool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneRedundant
Redundansi zona untuk dikaitkan dengan Kumpulan Elastis Azure Sql

```yaml
Type: System.Management.Automation.SwitchParameter
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ElasticPool.Model.AzureSqlElasticPoolModel

## NOTES

## RELATED LINKS

[Get-AzSqlElasticPool](./Get-AzSqlElasticPool.md)

[Get-AzSqlElasticPoolActivity](./Get-AzSqlElasticPoolActivity.md)

[Get-AzSqlElasticPoolDatabase](./Get-AzSqlElasticPoolDatabase.md)

[Baru-AzSqlElasticPool](./New-AzSqlElasticPool.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
