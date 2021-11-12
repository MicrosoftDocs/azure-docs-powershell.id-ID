---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 555D58AB-1361-4BB1-ACD0-905C3C6F4F7E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqlelasticpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlElasticPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlElasticPool.md
ms.openlocfilehash: 563cddc1723f0706eb5cdde691e9ab960e871989
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421752"
---
# Set-AzureRmSqlElasticPool

## SYNOPSIS
Mengubah properti pool database elastis di Azure SQL Database.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmSqlElasticPool [-ElasticPoolName] <String> [-Edition <DatabaseEdition>] [-Dtu <Int32>]
 [-StorageMB <Int32>] [-DatabaseDtuMin <Int32>] [-DatabaseDtuMax <Int32>] [-Tags <Hashtable>] [-ZoneRedundant]
 [-AsJob] [-ServerName] <String> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmSqlElasticPool mengatur** properti untuk kumpulan elastis dalam Azure SQL Database. Cmdlet ini dapat memodifikasi eDTUs per pool (*Dtu*), ukuran maksimum penyimpanan per pool (*StorageMB*), eDTUs maksimal per database (*DatabaseDtuMax*), dan minimum eDTUs per database (*DatqabaseDtuMin*).

Beberapa parameter (*-Dtu, -DatabaseDtuMin, dan -DatabaseDtuMax*) memerlukan nilai yang ditetapkan adalah dari daftar nilai yang valid untuk parameter tersebut. Misalnya, -DatabaseDtuMax untuk kumpulan eDTU Standar 100 hanya dapat diatur ke 10, 20, 50, atau 100.  Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).

## EXAMPLES

### Contoh 1: Modifikasi properti untuk pool elastis
```
PS C:\>Set-AzureRmSqlDatabaseElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -Dtu 1000 -DatabaseDtuMax 100 -DatabaseDtuMin 20
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

Perintah ini mengubah properti untuk kolam elastis bernama elastispool01. Perintah mengatur jumlah DKU untuk pool elastis menjadi 1000 dan mengatur DKU minimum dan maksimum.

### Contoh 2: Modifikasi ukuran maksimum penyimpanan dari pool elastis
```
PS C:\>Set-AzureRmSqlDatabaseElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -StorageMB 2097152
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

Perintah ini mengubah properti untuk kolam elastis bernama elastispool01. Perintah mengatur penyimpanan maks untuk pool elastis hingga 2 TB.

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
Menentukan jumlah maksimum DTU yang dapat digunakan database tunggal dalam pool. 

Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool). 

Nilai default untuk edisi yang berbeda adalah sebagai berikut:

- Dasar.  5 DKU
- Standar. 100 DKU
- Premium. 125 DKU


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

Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).

Nilai defaultnya adalah nol (0).

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

Untuk detail tentang nilai mana yang valid, lihat tabel untuk kolam renang ukuran tertentu dalam kolam renang [elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool). 

Nilai default untuk edisi yang berbeda adalah sebagai berikut:

- Dasar. 100 DKU
- Standar. 100 DKU
- Premium. 125 DKU

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
Menentukan edisi produk terlekat untuk Azure SQL Database elastis. Anda tidak dapat mengubah edisi. Nilai yang dapat diterima untuk parameter ini adalah:

- Tidak ada
- Dasar
- Standar
- Premium
- DataWarehouse

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
Menentukan nama kolam renang elastis.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat kelompok elastis ditetapkan.

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
Menentukan batas penyimpanan, dalam megabyte, untuk pool elastis. Untuk informasi selengkapnya, lihat New-AzureRmSqlElasticPool cmdlet.

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
Menentukan kamus pasangan Nilai kunci yang mengaitkan cmdlet ini dengan pool elastis dalam bentuk tabel hash. Misalnya:

`@{key0="value0";"key 1"=$null;key2="value2"}`

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

[New-AzureRmSqlElasticPool](./New-AzureRmSqlElasticPool.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)
