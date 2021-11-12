---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 009899E5-83BF-4A3F-877E-70C16D5CD1AC
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/new-azurermsqlelasticpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/New-AzureRmSqlElasticPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/New-AzureRmSqlElasticPool.md
ms.openlocfilehash: 3d93b0d82a2769acce620ce97141be68c003c281
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420748"
---
# New-AzureRmSqlElasticPool

## SYNOPSIS
Membuat pool database elastis untuk suatu SQL Database.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmSqlElasticPool -ElasticPoolName <String> [-Edition <DatabaseEdition>] [-Dtu <Int32>]
 [-StorageMB <Int32>] [-DatabaseDtuMin <Int32>] [-DatabaseDtuMax <Int32>] [-Tags <Hashtable>] [-ZoneRedundant]
 [-AsJob] [-ServerName] <String> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmSqlElasticPool** membuat pool database elastis untuk Azure SQL Database.

Beberapa parameter (*-Dtu, -DatabaseDtuMin, dan -DatabaseDtuMax*) memerlukan nilai yang ditetapkan adalah dari daftar nilai yang valid untuk parameter tersebut. Misalnya, -DatabaseDtuMax untuk kumpulan eDTU Standar 100 hanya dapat diatur ke 10, 20, 50, atau 100.  Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool). 

## EXAMPLES

### Contoh 1: Membuat pool elastis
```
PS C:\>New-AzureRmSqlElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -Edition "Standard" -Dtu 400 -DatabaseDtuMin 10 -DatabaseDtuMax 100
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

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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
- Premium. 125 DKU

Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool) 


```yaml
Type: Int32
Parameter Sets: (All)
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
Type: Int32
Parameter Sets: (All)
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
125 DKU

Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool). 

```yaml
Type: Int32
Parameter Sets: (All)
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

- Premium
- Dasar
- Standar
- DataWarehouse
- Regang

```yaml
Type: DatabaseEdition
Parameter Sets: (All)
Aliases:
Accepted values: None, Premium, Basic, Standard, DataWarehouse, Stretch, Free, PremiumRS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ElastisPoolName
Menentukan nama kolam renang elastis yang dibuat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya di mana cmdlet ini menetapkan kumpulan elastis.

```yaml
Type: String
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
Type: String
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
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Menentukan kamus pasangan Nilai kunci dalam bentuk tabel hash yang terkait dengan cmdlet ini dengan pool elastis. Misalnya:

@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneRedundant
Kelebihan zona untuk dikaitkan dengan Pool Elastis Azure Sql

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.sql.elastisPool.Model.AzureSqlElasticPoolModel

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlElasticPool](./Get-AzureRmSqlElasticPool.md)

[Get-AzureRmSqlElasticPoolActivity](./Get-AzureRmSqlElasticPoolActivity.md)

[Get-AzureRmSqlElasticPoolDatabase](./Get-AzureRmSqlElasticPoolDatabase.md)

[Remove-AzureRmSqlElasticPool](./Remove-AzureRmSqlElasticPool.md)

[Set-AzureRmSqlElasticPool](./Set-AzureRmSqlElasticPool.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)
