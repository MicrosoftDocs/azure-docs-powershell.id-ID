---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.dll-Help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/new-azdatamigrationmongodbdatabasesetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbDatabaseSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbDatabaseSetting.md
ms.openlocfilehash: 394fc70797d0e336093dca96ff244b073cb606b0
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140090549"
---
# New-AzDataMigrationMongoDbDatabaseSetting

## SYNOPSIS
Membuat pengaturan database untuk migrasi untuk migrasi azureoDb

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.datamigration/new-azdatamigrationmongodbdatabasesetting) untuk informasi terkini.

## SYNTAX

```
New-AzDataMigrationMongoDbDatabaseSetting  -Name <Name> [-RU <RU>] -CollectionSetting <Collections>
```

## DESCRIPTION
Cmdlet New-AzDataMigrationMongoDbDatabaseSetting membuat objek pengaturan migrasi yang menentukan perilaku throughput dan penghapusan.
Output adalah pasangan nilai kunci dengan nama kumpulan dan nilai pengaturan, yang dapat digunakan dalam menjalankan tugas migrasi.

## EXAMPLES

### Contoh 1
```
PS C:\> New-AzDataMigrationMongoDbDatabaseSetting  -Name mycollection -RU 1000 -CollectionSetting @($coll1, $coll2)

Name Setting
---- -------
test Microsoft.Azure.Management.DataMigration.Models.MongoDbDatabaseSettings

```

## PARAMETERS

### -Nama
Nama database

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DatabaseName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```
### -TargetRequestUnit
Nilai unit permintaan tingkat database khusus. Jika belum ditetapkan, kumpulan itu menggunakan database bersama RU.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: RU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Koleksi
Larik objek pengaturan kumpulan SkoroDb dikembalikan oleh New-AzureRmDmsMongoDbDatabaseSetting panggilan.

```yaml
Type: System.Collections.Generic.KeyValuePair<string, MongoDbCollectionSettings>[]
Parameter Sets: (All)
Aliases: colls

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.DataMigration.Models.DatabaseoDbDatabaseSetting

## CATATAN

## RELATED LINKS
