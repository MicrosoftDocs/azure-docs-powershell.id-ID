---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationskurecommendation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSkuRecommendation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSkuRecommendation.md
ms.openlocfilehash: 42e2d7d2b14b37e0190beeaf3a64825c383702d4
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145537178"
---
# Get-AzDataMigrationSkuRecommendation

## SYNOPSIS
Memberikan rekomendasi SKU untuk penawaran Azure SQL

## SYNTAX

### CommandLine (Default)
```
Get-AzDataMigrationSkuRecommendation [-OutputFolder <String>] [-TargetPlatform <String>]
 [-TargetSqlInstance <String>] [-TargetPercentile <String>] [-ScalingFactor <String>] [-StartTime <String>]
 [-EndTime <String>] [-Overwrite] [-DisplayResult] [-ElasticStrategy] [-DatabaseAllowList <String>]
 [-DatabaseDenyList <String>] [-PassThru] [<CommonParameters>]
```

### ConfigFile
```
Get-AzDataMigrationSkuRecommendation -ConfigFilePath <String> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Memberikan rekomendasi SKU untuk penawaran Azure SQL

## EXAMPLES

### Contoh 1: Jalankan Rekomendasi SKU pada SQL Server tertentu menggunakan string koneksi
```powershell
PS C:\> Get-AzDataMigrationSkuRecommendation -DisplayResult
```

```output
Starting SKU recommendation...

Performing aggregation for instance AALAB03-2K8...
Aggregation complete. Calculating SKU recommendations...
Instance name: AALAB03-2K8
SKU recommendation: Azure SQL Managed Instance:
Compute: Gen5 - GeneralPurpose - 4 cores
Storage: 64 GB
Recommendation reasons:
        According to the performance data collected, we estimate that your SQL server instance has a requirement for 0.16 vCores of CPU. For greater flexibility, based on your scaling factor of 100.00%, we are making a recommendation based on 0.16 vCores. Based on all the other factors, including memory, storage, and IO, this is the smallest compute sizing that will satisfy all of your needs.
        This SQL Server instance requires 0.44 GB of memory, which is within this SKU's limit of 20.40 GB.
        This SQL Server instance requires 32.37 GB of storage for data files. We recommend provisioning 64 GB of storage, which is the closest valid amount that can be provisioned that meets your requirement.
        This SQL Server instance requires 0.00 MB/second of combined read/write IO throughput. This is a relatively idle instance, so IO latency is not considered.
        Assuming the database uses the Full Recovery Model, this SQL Server instance requires 1 IOPS for data and log files. 
        This is the most cost-efficient offering among all the performance eligible SKUs.


Finishing SKU recommendations...
Event and Error Logs Folder Path: C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan Jalankan Rekomendasi SKU pada SQL Server yang diberikan menggunakan string koneksi.

### Contoh 2: Jalankan Eksekusi Rekomendasi SKU pada SQL Server yang diberikan menggunakan file konfigurasi penilaian
```powershell
PS C:\> Get-AzDataMigrationSkuRecommendation -ConfigFilePath "C:\Users\user\document\config.json"
```

```output
Starting SKU recommendation...

Performing aggregation for instance AALAB03-2K8...
Aggregation complete. Calculating SKU recommendations...
Instance name: AALAB03-2K8
SKU recommendation: Azure SQL Managed Instance:
Compute: Gen5 - GeneralPurpose - 4 cores
Storage: 64 GB
Recommendation reasons:
        According to the performance data collected, we estimate that your SQL server instance has a requirement for 0.16 vCores of CPU. For greater flexibility, based on your scaling factor of 100.00%, we are making a recommendation based on 0.16 vCores. Based on all the other factors, including memory, storage, and IO, this is the smallest compute sizing that will satisfy all of your needs.
        This SQL Server instance requires 0.44 GB of memory, which is within this SKU's limit of 20.40 GB.
        This SQL Server instance requires 32.37 GB of storage for data files. We recommend provisioning 64 GB of storage, which is the closest valid amount that can be provisioned that meets your requirement.
        This SQL Server instance requires 0.00 MB/second of combined read/write IO throughput. This is a relatively idle instance, so IO latency is not considered.
        Assuming the database uses the Full Recovery Model, this SQL Server instance requires 1 IOPS for data and log files. 
        This is the most cost-efficient offering among all the performance eligible SKUs.


Finishing SKU recommendations...
Event and Error Logs Folder Path: C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan Jalankan Rekomendasi SKU pada SQL Server yang diberikan menggunakan file konfigurasi.

## PARAMETERS

### -ConfigFilePath
Jalur ConfigFile

```yaml
Type: System.String
Parameter Sets: ConfigFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseAllowList
Opsional.
Daftar nama database yang dipisahkan spasi untuk diizinkan untuk pertimbangan rekomendasi SKU sambil mengecualikan semua yang lain.
Hanya atur salah satu dari berikut ini atau tidak: databaseAllowList, databaseDenyList.
Cara meneruskan - "Database1 Database2" (Default: null)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseDenyList
Opsional.
Daftar nama database yang dipisahkan spasi agar tidak dipertimbangkan untuk rekomendasi SKU.
Hanya atur salah satu dari berikut ini atau tidak: databaseAllowList, databaseDenyList.
Cara meneruskan - "Database1 Database2" (Default: null)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayResult
Opsional.
Apakah akan mencetak hasil rekomendasi SKU ke konsol atau tidak.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ElasticStrategy
Opsional.
Apakah akan menggunakan strategi elastis untuk rekomendasi SKU berdasarkan pembuatan profil penggunaan sumber daya atau tidak.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Opsional.
Waktu akhir UTC titik data performa yang perlu dipertimbangkan selama agregasi, dalam format HH:MM-DD YYYY-MM.
Hanya digunakan untuk strategi garis besar (non-elastis).
(Default: semua poin data yang dikumpulkan akan dipertimbangkan)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFolder
Folder data dan laporan hasil mana yang akan ditulis ke/dibaca.
Nilai di sini harus sama dengan yang digunakan dalam PerfDataCollection

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timpa
Opsional.
Apakah akan menimpa laporan rekomendasi SKU yang ada atau tidak.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

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

### -ScalingFactor
Opsional.
Faktor penskalaan (kenyamanan) yang digunakan selama rekomendasi SKU.
Misalnya, jika ditentukan bahwa ada persyaratan CPU 4 vCore dengan faktor penskalaan 150%, maka persyaratan CPU yang sebenarnya adalah 6 vCore.
(Default: 100)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Opsional.
Waktu mulai UTC titik data performa yang perlu dipertimbangkan selama agregasi, dalam format YYYY-MM-DD HH:MM.
Hanya digunakan untuk strategi garis besar (non-elastis).
(Default: semua poin data yang dikumpulkan akan dipertimbangkan)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPercentile
Opsional.
Persentil poin data yang akan digunakan selama agregasi data performa.
Hanya digunakan untuk strategi garis besar (non-elastis).
(Default: 95)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPlatform
Opsional.
Platform target untuk rekomendasi SKU: Baik AzureSqlDatabase, AzureSqlManagedInstance, AzureSqlVirtualMachine, atau Apa pun.
Jika ada yang dipilih, maka rekomendasi SKU untuk ketiga platform target akan dievaluasi, dan yang paling cocok akan dikembalikan.
(Default: Apa pun)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetSqlInstance
Opsional.
Nama instans SQL yang akan ditargetkan oleh rekomendasi SKU.
(Default: outputFolder akan dipindai untuk file yang dibuat oleh tindakan PerfDataCollection, dan rekomendasi akan diberikan untuk setiap instans yang ditemukan)

```yaml
Type: System.String
Parameter Sets: CommandLine
Aliases:

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

### System.Boolean

## NOTES

ALIAS

## RELATED LINKS
