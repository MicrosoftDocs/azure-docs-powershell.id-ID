---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.dll-Help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/New-AzDataMigrationMongoDbCollectionSetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbCollectionSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbCollectionSetting.md
ms.openlocfilehash: 7197238d7acfbaf5329c203f19dc22c96b1346b0
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140556839"
---
# New-AzDataMigrationMongoDbCollectionSetting

## SYNOPSIS
Membuat pengaturan kumpulan untuk migrasi sesuai dengan migrasi dbdb

## SYNTAX

```
New-AzDataMigrationMongoDbCollectionSetting [-TargetRequestUnit <Int32>] [-CanDelete] [-UniqueShard]
 [-ShardKey <String>] [-DefaultProfile <IAzureContextContainer>] -Name <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzDataMigrationMongoDbCollectionSetting membuat objek pengaturan migrasi yang menentukan perilaku throughput dan penghapusan.
Output cmdlet adalah key value pair dengan nama kumpulan, dan nilai pengaturan. Output digunakan dalam merangkai pengaturan tingkat database untuk migrasi.

## EXAMPLES

### Contoh 1
```
PS C:\> $x = New-AzDataMigrationMongoDbCollectionSetting -Name myCollection -TargetRequestUnit 1000 -CanDelete -ShardKey "_id:-1,age:1,name"
PS C:\> $x

Name         Setting
----         -------
myCollection Microsoft.Azure.Management.DataMigration.Models.MongoDbCollectionSettings

PS C:\> $x.Setting

CanDelete ShardKey                                                               TargetRUs
--------- --------                                                               ---------
     True Microsoft.Azure.Management.DataMigration.Models.MongoDbShardKeySetting      1000
```

## PARAMETERS

### -CanDelete
Apakah data target seharusnya dihapus, jika sakelar diatur, sakelar akan dibersihkan pada saat migrasi

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: Clean

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Nama
Nama koleksi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CollectionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skey
Daftar tombol sah yang dipisahkan koma. Untuk target hashoDb, Anda dapat menentukan urutan kunci s key "S altkeyName:Order", dengan urutan 1, -1 atau kosong untuk disederhan, misalnya "_id,email:-1".

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

### -TargetRequestUnit
Nilai unit permintaan kumpulan khusus. Jika belum ditetapkan, kumpulan itu menggunakan database bersama RU.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: RU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueS unique
Apakah akan membuat kunci unik untuk kunci s key

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: Unique

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.DataMigration.Models.DatabaseoDbCollectionSetting>

## CATATAN

## RELATED LINKS
