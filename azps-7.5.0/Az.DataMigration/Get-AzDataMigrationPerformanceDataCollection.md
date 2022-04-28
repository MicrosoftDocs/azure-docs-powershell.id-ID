---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationperformancedatacollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationPerformanceDataCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationPerformanceDataCollection.md
ms.openlocfilehash: 6fee7ec3ca85be41fee875dbaa44edbcdab326f2
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144202266"
---
# Get-AzDataMigrationPerformanceDataCollection

## SYNOPSIS
Mengumpulkan data performa untuk instans SQL Server yang diberikan

## SYNTAX

### CommandLine (Default)
```
Get-AzDataMigrationPerformanceDataCollection -SqlConnectionStrings <String[]> [-OutputFolder <String>]
 [-PerfQueryInterval <String>] [-StaticQueryInterval <String>] [-NumberOfIterations <String>] [-PassThru]
 [<CommonParameters>]
```

### ConfigFile
```
Get-AzDataMigrationPerformanceDataCollection -ConfigFilePath <String> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Mengumpulkan data performa untuk instans SQL Server yang diberikan

## EXAMPLES

### Contoh 1: Jalankan Pengumpulan Data Performa pada SQL Server tertentu menggunakan string koneksi
```powershell
PS C:\> Get-AzDataMigrationPerformanceDataCollection -SqlConnectionStrings "Data Source=AALAB03-2K8.REDMOND.CORP.MICROSOFT.COM;Initial Catalog=master;Integrated Security=False;User Id=dummyUserId;Password=dummyPassword" -NumberOfIterations 2

Connecting to the SQL server(s)...
Starting data collection...
Press the Enter key to stop the data collection at any time...

Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
UTC 2022-02-03 07:04:50, Server AALAB03-2K8:
        Performance data query iteration: 1 of 2, collected 349 data points.
UTC 2022-02-03 07:04:52, Server AALAB03-2K8:
        Collected static configuration data, and saved to C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment.
Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
UTC 2022-02-03 07:05:44, Server AALAB03-2K8:
        Performance data query iteration: 2 of 2, collected 347 data points.
UTC 2022-02-03 07:07:13, Server AALAB03-2K8:
        Aggregated 696 raw data points to 263 performance counters, and saved to C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment.
UTC 2022-02-03 07:07:16, Server AALAB03-2K8:
        Performance data query iteration: 1 of 2, collected 349 data points.

Event and Error Logs Folder Path: C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan Pengumpulan Data Performa pada SQL Server tertentu menggunakan string koneksi.

### Contoh 2: Jalankan Pengumpulan Data Performa pada SQL Server tertentu menggunakan file konfigurasi penilaian
```powershell
PS C:\> Get-AzDataMigrationAssessment -ConfigFilePath "C:\Users\user\document\config.json"

Connecting to the SQL server(s)...
Starting data collection...
Press the Enter key to stop the data collection at any time...

Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
UTC 2022-02-03 07:04:50, Server AALAB03-2K8:
        Performance data query iteration: 1 of 2, collected 349 data points.
UTC 2022-02-03 07:04:52, Server AALAB03-2K8:
        Collected static configuration data, and saved to C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment.
Security Warning: The negotiated TLS 1.0 is an insecure protocol and is supported for backward compatibility only. The recommended protocol version is TLS 1.2 and later.
UTC 2022-02-03 07:05:44, Server AALAB03-2K8:
        Performance data query iteration: 2 of 2, collected 347 data points.
UTC 2022-02-03 07:07:13, Server AALAB03-2K8:
        Aggregated 696 raw data points to 263 performance counters, and saved to C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment.
UTC 2022-02-03 07:07:16, Server AALAB03-2K8:
        Performance data query iteration: 1 of 2, collected 349 data points.

Event and Error Logs Folder Path: C:\Users\vmanhas\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan Pengumpulan Data Performa pada SQL Server tertentu menggunakan file konfigurasi.

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

### -NumberOfIterations
Jumlah perulangan pengumpulan data performa yang harus dilakukan sebelum bertahan ke file.
Misalnya, dengan nilai default, data performa akan dipertahankan setiap 30 detik * 20 iterasi = 10 menit.
(Default: 20, Minimum: 2)

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

### -PerfQueryInterval
Interval untuk mengkueri data performa, dalam hitungan detik.
(Default: 30)

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

### -SqlConnectionStrings
String Koneksi Sql Server

```yaml
Type: System.String[]
Parameter Sets: CommandLine
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticQueryInterval
Interval untuk mengkueri dan mempertahankan data konfigurasi statis, dalam hitungan detik.
(Default: 3600)

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
