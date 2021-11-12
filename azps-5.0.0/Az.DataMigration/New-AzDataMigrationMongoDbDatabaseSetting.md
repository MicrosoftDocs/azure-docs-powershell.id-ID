---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.dll-Help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/en-us/powershell/module/az.datamigration/new-azdatamigrationmongodbdatabasesetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbDatabaseSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbDatabaseSetting.md
ms.openlocfilehash: 9ae50501306dfa1a76fa4966113ac2e9b681f6c5
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132411312"
---
# New-AzDataMigrationMongoDbDatabaseSetting

## SYNOPSIS
Membuat pengaturan database untuk migrasi untuk migrasi azureoDb

## SINTAKS

```
New-AzDataMigrationMongoDbDatabaseSetting  -Name <Name> [-RU <RU>] -CollectionSetting <Collections>
```

## DESKRIPSI
Cmdlet New-AzDataMigrationMongoDbDatabaseSetting membuat objek pengaturan migrasi yang menentukan perilaku penghapusan dan throughput.
Output adalah pasangan nilai kunci dengan nama kumpulan dan nilai pengaturan, yang dapat digunakan dalam menjalankan tugas migrasi.

## CONTOH

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
Array objek pengaturan kumpulan SkoroDb dikembalikan oleh New-AzureRmDmsMongoDbDatabaseSetting panggilan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.DataMigration.Models.DatabaseoDbDatabaseSetting

## CATATAN

## LINK TERKAIT
