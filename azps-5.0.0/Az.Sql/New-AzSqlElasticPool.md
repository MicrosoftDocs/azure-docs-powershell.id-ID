---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 009899E5-83BF-4A3F-877E-70C16D5CD1AC
online version: https://docs.microsoft.com/en-us/powershell/module/az.sql/new-azsqlelasticpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Sql/Sql/help/New-AzSqlElasticPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Sql/Sql/help/New-AzSqlElasticPool.md
ms.openlocfilehash: 8fed3f32f5ff0a9920b87438b75cb25cee7c9217
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132407228"
---
# New-AzSqlElasticPool

## SYNOPSIS
Membuat pool database elastis untuk SQL Database.

## SINTAKS

### DtuBasedPool (Default)
```
New-AzSqlElasticPool [-ElasticPoolName] <String> [-Edition <String>] [-Dtu <Int32>] [-StorageMB <Int32>]
 [-DatabaseDtuMin <Int32>] [-DatabaseDtuMax <Int32>] [-Tags <Hashtable>] [-ZoneRedundant]
 [-LicenseType <String>] [-AsJob] [-ServerName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VcoreBasedPool
```
New-AzSqlElasticPool [-ElasticPoolName] <String> -Edition <String> [-StorageMB <Int32>] -VCore <Int32>
 -ComputeGeneration <String> [-DatabaseVCoreMin <Double>] [-DatabaseVCoreMax <Double>] [-Tags <Hashtable>]
 [-ZoneRedundant] [-LicenseType <String>] [-AsJob] [-ServerName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzSqlElasticPool** membuat pool database elastis untuk Azure SQL Database.
Beberapa parameter (*-Dtu, -DatabaseDtuMin, dan -DatabaseDtuMax*) memerlukan nilai yang ditetapkan adalah dari daftar nilai yang valid untuk parameter tersebut. Misalnya, -DatabaseDtuMax untuk kumpulan eDTU Standar 100 hanya dapat diatur ke 10, 20, 50, atau 100.  Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).

## CONTOH

### Contoh 1: Membuat kolam elastis DTU

```powershell
PS C:\>New-AzSqlElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -Edition "Standard" -Dtu 400 -DatabaseDtuMin 10 -DatabaseDtuMax 100
ResourceId        : /subscriptions/00000000-0000-0000-0000-000000000001/resourceGroups/resourcegroup01/providers/Microsoft.Sql/servers/server01/elasticPools/elasticpool01
ResourceGroupName : resourcegroup01
ServerName        : server01
ElasticPoolName   : elasticpool01
Location          : Central US
CreationDate      : 8/26/2015 10:00:17 PM
State             : Ready
Edition           : Standard
Dtu               : 400
DatabaseDtuMax    : 100
DatabaseDtuMin    : 10
StorageMB         : 409600
Tags              :
```

Perintah ini membuat kolam elastis di tingkat layanan Standar bernama ElastisPool01. Server bernama server01, ditetapkan ke grup sumber daya Azure bernama ResourceGroup01, meng host kumpulan elastis di dalam. Perintah menentukan nilai properti DTU untuk pool dan database dalam pool.

### Contoh 2: Membuat kolam elastis vCore

```powershell
PS C:\> New-AzSqlElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -Edition "GeneralPurpose" -vCore 2 -ComputeGeneration Gen5
ResourceId          : /subscriptions/00000000-0000-0000-0000-000000000001/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/servers/server01/elasticPools/ElasticPool01
ResourceGroupName   : ResourceGroup01
ServerName          : Server01
ElasticPoolName     : ElasticPool01
Location            : Central US
CreationDate        : 8/29/2019 2:16:40 AM
State               : Ready
Edition             : GeneralPurpose
SkuName             : GP_Gen5
Dtu                 : 2
DatabaseDtuMax      : 2
DatabaseDtuMin      : 0
Capacity            : 2
DatabaseCapacityMin : 0
DatabaseCapacityMax : 2
Family              : Gen5
MaxSizeBytes        : 34359738368
StorageMB           : 32768
Tags                :
```

Perintah ini membuat kolam elastis di tingkat layanan GengeralPurpose bernama ElastisPool01. Server bernama server01, ditetapkan ke grup sumber daya Azure bernama ResourceGroup01, meng host kumpulan elastis di dalam. Perintah menentukan nilai properti vCore untuk pool dan database dalam pool.

### Contoh 3

Membuat pool database elastis untuk SQL Database. (otomatisgenerated)

```powershell
<!-- Aladdin Generated Example --> 
New-AzSqlElasticPool -ComputeGeneration Gen5 -Edition 'GeneralPurpose' -ElasticPoolName 'ElasticPool01' -ResourceGroupName 'ResourceGroup01' -ServerName 'Server01' -StorageMB 2097152 -VCore 2
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
Pembuatan perhitungan untuk ditetapkan.

```yaml
Type: System.String
Parameter Sets: VcoreBasedPool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseDtuMax
Menentukan jumlah maksimum Unit Throughput Database (DTU, Database Throughput Units) yang dapat digunakan oleh setiap database dalam pool.
Nilai default untuk edisi yang berbeda adalah sebagai berikut:
- Dasar. 5 DKU
- Standar. 100 DKU
- Premium. 125 DKU Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool)

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
Menentukan jumlah minimum DTU yang dijamin oleh elastis pool untuk semua database di dalam pool.
Nilai defaultnya adalah nol (0).
Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).

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
Jumlah maksimum VCore setiap Database SqlAzure dapat digunakan dalam pool.

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
Jumlah VCore minimum database SqlAzure dapat digunakan dalam pool.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Menentukan jumlah total DTU bersama untuk pool elastis.
Nilai default untuk edisi yang berbeda adalah sebagai berikut:
- Dasar.
100 DKU
- Standar.
100 DKU
- Premium.
125 DKU Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).

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

### -Edition
Menentukan edisi produk produk yang Azure SQL Database untuk elastis pool.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak ada
- Dasar
- Standar
- Premium
- DataWarehouse
- Gratis
- Regang
- GeneralPurpose
- BusinessCritical

```yaml
Type: System.String
Parameter Sets: DtuBasedPool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: VcoreBasedPool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ElastisPoolName
Menentukan nama kolam renang elastis yang dibuat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Tipe lisensi untuk database Azure Sql.

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
Menentukan nama grup sumber daya di mana cmdlet ini menetapkan kumpulan elastis.

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
Menentukan nama server yang menjadi host kolam elastis.

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
Menentukan batas penyimpanan, dalam megabyte, untuk pool elastis. Jika Anda tidak menentukan parameter ini, cmdlet ini menghitung nilai yang bergantung pada nilai parameter *Dtu.*
Lihat [eDTU dan batas penyimpanan untuk](/azure/sql-database/sql-database-elastic-pool#edtu-and-storage-limits-for-elastic-pools) nilai yang mungkin.

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

### -Tag
Menentukan kamus pasangan Nilai kunci dalam bentuk tabel hash yang terkait dengan cmdlet ini dengan pool elastis. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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
Total jumlah bersama Vcore untuk Pool Elastis Sql Azure.

```yaml
Type: System.Int32
Parameter Sets: VcoreBasedPool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneRedundant
Kelebihan zona untuk dikaitkan dengan Pool Elastis Azure Sql

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.sql.elastisPool.Model.AzureSqlElasticPoolModel

## CATATAN

## LINK TERKAIT

[Get-AzSqlElasticPool](./Get-AzSqlElasticPool.md)

[Get-AzSqlElasticPoolActivity](./Get-AzSqlElasticPoolActivity.md)

[Get-AzSqlElasticPoolDatabase](./Get-AzSqlElasticPoolDatabase.md)

[Remove-AzSqlElasticPool](./Remove-AzSqlElasticPool.md)

[Set-AzSqlElasticPool](./Set-AzSqlElasticPool.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)
