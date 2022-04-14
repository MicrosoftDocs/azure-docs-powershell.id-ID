---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 555D58AB-1361-4BB1-ACD0-905C3C6F4F7E
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqlelasticpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlElasticPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlElasticPool.md
ms.openlocfilehash: 3a322a3a63a61c9d4de5a7b0d18b0edf214d597f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141786686"
---
# Set-AzSqlElasticPool

## SYNOPSIS
Mengubah properti kumpulan database elastis di Azure SQL Database.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/set-azsqlelasticpool) untuk informasi terbaru.

## SYNTAX

### DtuBasedPool (Default)
```
Set-AzSqlElasticPool [-ElasticPoolName] <String> [-Edition <String>] [-Dtu <Int32>] [-StorageMB <Int32>]
 [-DatabaseDtuMin <Int32>] [-DatabaseDtuMax <Int32>] [-Tags <Hashtable>] [-ZoneRedundant]
 [-LicenseType <String>] [-MaintenanceConfigurationId <String>] [-AsJob] [-ServerName] <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VcoreBasedPool
```
Set-AzSqlElasticPool [-ElasticPoolName] <String> [-Edition <String>] [-StorageMB <Int32>] [-VCore <Int32>]
 [-ComputeGeneration <String>] [-DatabaseVCoreMin <Double>] [-DatabaseVCoreMax <Double>] [-Tags <Hashtable>]
 [-ZoneRedundant] [-LicenseType <String>] [-MaintenanceConfigurationId <String>] [-AsJob]
 [-ServerName] <String> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlElasticPool** mengatur properti untuk kolam elastis di Azure SQL Database. Cmdlet ini dapat mengubah eDTUs per pool (*Dtu*), ukuran maksimal penyimpanan per pool (*StorageMB*), eDTUs maksimum per database (*DatabaseDtuMax), dan eDTUs* minimum per database (*DatabaseDtuMin*).
Beberapa parameter (*-Dtu, -DatabaseDtuMin, dan -DatabaseDtuMax*) memerlukan nilai yang diatur adalah dari daftar nilai yang valid untuk parameter tersebut. Misalnya, -DatabaseDtuMax untuk kumpulan eDTU Standar 100 hanya dapat diatur ke 10, 20, 50, atau 100.  Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran tertentu dalam [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).

## EXAMPLES

### Contoh 1: Memodifikasi properti untuk kumpulan elastis
```powershell
PS C:\>Set-AzSqlElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -Dtu 1000 -DatabaseDtuMax 100 -DatabaseDtuMin 20
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

Perintah ini mengubah properti untuk kolam elastis bernama elasticpool01. Perintah mengatur jumlah DPU untuk kumpulan elastis menjadi 1000 dan mengatur DPU minimum dan maksimum.

### Contoh 2: Modifikasi ukuran maksimal penyimpanan dari kumpulan elastis
```powershell
PS C:\>Set-AzSqlElasticPool -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ElasticPoolName "ElasticPool01" -StorageMB 2097152
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

Perintah ini mengubah properti untuk kolam elastis bernama elasticpool01. Perintah mengatur penyimpanan maksimum untuk kumpulan elastis menjadi 2 TB.

### Contoh 3

Mengubah properti kumpulan database elastis di Azure SQL Database. (autogenerasi)

```powershell
<!-- Aladdin Generated Example --> 
Set-AzSqlElasticPool -Dtu 1000 -Edition 'GeneralPurpose' -ElasticPoolName 'ElasticPool01' -ResourceGroupName 'ResourceGroup01' -ServerName 'Server01'
```

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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
Generasi komputasi untuk ditetapkan.

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
Menentukan jumlah maksimum DSU yang dapat digunakan oleh database tunggal dalam kumpulan.
Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran tertentu dalam [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).
Nilai default untuk edisi berbeda adalah sebagai berikut:
- Dasar.  5 DTU
- Standar. 100 DKU
- Premium. 125 DKU

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
Menentukan jumlah minimum DPU yang dijamin oleh kumpulan elastis ke semua database dalam kumpulan.
Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran tertentu dalam [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).
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
Jumlah VCore maksimum yang dapat digunakan database SqlAzure dalam kumpulan.

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
Angka VCore minimum setiap Database SqlAzure dapat digunakan di kolam renang.

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
Menentukan jumlah total DPU bersama untuk kumpulan elastis.
Untuk detail tentang nilai mana yang valid, lihat tabel untuk kumpulan ukuran tertentu dalam [kumpulan elastis](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool).
Nilai default untuk edisi berbeda adalah sebagai berikut:
- Dasar. 100 DKU
- Standar. 100 DKU
- Premium. 125 DKU

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
- Tidak
- Dasar
- Standar
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
Menentukan nama server yang menjadi host kumpulan elastis.

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
Menentukan kamus pasangan nilai kunci yang terkait cmdlet ini dengan kumpulan elastis dalam bentuk tabel hash. Misalnya: `@{key0="value0";"key 1"=$null;key2="value2"}`

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
Jumlah total bersama Vcore untuk Sql Azure Elastic Pool.

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
Redundansi zona untuk dikaitkan dengan Azure Sql Elastic Pool

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ElasticPool.Model.AzureSqlElasticPoolModel

## CATATAN

## RELATED LINKS

[Get-AzSqlElasticPool](./Get-AzSqlElasticPool.md)

[Get-AzSqlElasticPoolActivity](./Get-AzSqlElasticPoolActivity.md)

[Get-AzSqlElasticPoolDatabase](./Get-AzSqlElasticPoolDatabase.md)

[New-AzSqlElasticPool](./New-AzSqlElasticPool.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
