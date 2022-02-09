---
external help file: ''
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationassessment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationAssessment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationAssessment.md
ms.openlocfilehash: aade402d810ed24c1c820cec805e94fbbed0d4e7
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138290236"
---
# Get-AzDataMigrationAssessment

## SYNOPSIS
Mulai penilaian SQL Server contoh

## SYNTAX

### CommandLine (Default)
```
Get-AzDataMigrationAssessment -ConnectionString <String[]> [-OutputFolder <String>] [-Overwrite] [-PassThru]
 [<CommonParameters>]
```

### ConfigFile
```
Get-AzDataMigrationAssessment -ConfigFilePath <String> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Mulai penilaian SQL Server contoh

## EXAMPLES

### Contoh 1: Jalankan SQL Penilaian penggunaan SQL Server menggunakan string koneksi
```powershell
PS C:\> Get-AzDataMigrationAssessment -ConnectionString "Data Source=LabServer.database.net;Initial Catalog=master;Integrated Security=False;User Id=User;Password=password" -OutputFolder "C:\AssessmentOutput" -Overwrite

Starting SQL assessment...
Progress: 100%; Issues Found: 100; Objects Assessed: 500/500; Status: Completed; Total time: 00:01:50.000.

Finishing SQL assessment...
Assessment report saved to C:\Users\user\AppData\Local\Microsoft\SqlAssessment\SqlAssessmentReport.json.
Event and Error Logs Folder Path: C:\Users\user\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan SQL Assessment pada kali SQL Server menggunakan string koneksi.

### Contoh 2: Jalankan SQL Assessment on given SQL Server using assessment config file
```powershell
PS C:\> Get-AzDataMigrationAssessment -ConfigFilePath "C:\Users\user\document\config.json"

Starting SQL assessment...
Progress: 100%; Issues Found: 100; Objects Assessed: 550/550; Status: Completed; Total time: 00:01:50.000.

Finishing SQL assessment...
Assessment report saved to C:\Users\user\AppData\Local\Microsoft\SqlAssessment\SqlAssessmentReport.json.
Event and Error Logs Folder Path: C:\Users\user\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan SQL Assessment on given SQL Server using assessment config file.

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

### -ConnectionString
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

### -OutputFolder
Folder output untuk menyimpan laporan penilaian

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

### -Overwrite
Aktifkan parameter ini untuk menimpa laporan penilaian yang sudah ada

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

## RELATED LINKS

