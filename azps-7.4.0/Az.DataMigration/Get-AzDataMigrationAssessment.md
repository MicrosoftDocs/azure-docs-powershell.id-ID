---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationassessment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationAssessment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationAssessment.md
ms.openlocfilehash: 431dcdebff18c13db5575343c1657555259bf252
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144678184"
---
# Get-AzDataMigrationAssessment

## SYNOPSIS
Mulai penilaian pada instans SQL Server

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/get-azdatamigrationassessment) untuk informasi terbaru.

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
Mulai penilaian pada instans SQL Server

## EXAMPLES

### Contoh 1: Jalankan Penilaian SQL pada SQL Server tertentu menggunakan string koneksi
```powershell
Get-AzDataMigrationAssessment -ConnectionString "Data Source=LabServer.database.net;Initial Catalog=master;Integrated Security=False;User Id=User;Password=password" -OutputFolder "C:\AssessmentOutput" -Overwrite
```

```output
Starting SQL assessment...
Progress: 100%; Issues Found: 100; Objects Assessed: 500/500; Status: Completed; Total time: 00:01:50.000.

Finishing SQL assessment...
Assessment report saved to C:\Users\user\AppData\Local\Microsoft\SqlAssessment\SqlAssessmentReport.json.
Event and Error Logs Folder Path: C:\Users\user\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan Penilaian SQL pada SQL Server tertentu menggunakan string koneksi.

### Contoh 2: Jalankan Penilaian SQL pada SQL Server tertentu menggunakan file konfigurasi penilaian
```powershell
Get-AzDataMigrationAssessment -ConfigFilePath "C:\Users\user\document\config.json"
```

```output
Starting SQL assessment...
Progress: 100%; Issues Found: 100; Objects Assessed: 550/550; Status: Completed; Total time: 00:01:50.000.

Finishing SQL assessment...
Assessment report saved to C:\Users\user\AppData\Local\Microsoft\SqlAssessment\SqlAssessmentReport.json.
Event and Error Logs Folder Path: C:\Users\user\AppData\Local\Microsoft\SqlAssessment\Logs
```

Perintah ini menjalankan Penilaian SQL pada SQL Server tertentu menggunakan file konfigurasi penilaian.

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

### -Timpa
Aktifkan parameter ini untuk menimpa laporan penilaian yang ada

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

## RELATED LINKS
