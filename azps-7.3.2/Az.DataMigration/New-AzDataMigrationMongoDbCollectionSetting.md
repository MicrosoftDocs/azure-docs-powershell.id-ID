---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.dll-Help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/New-AzDataMigrationMongoDbCollectionSetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbCollectionSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationMongoDbCollectionSetting.md
ms.openlocfilehash: 364a1717932271b961b073d9ed9e09f90ba9c1f6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141939957"
---
# New-AzDataMigrationMongoDbCollectionSetting

## SYNOPSIS
Membuat pengaturan pengumpulan untuk migrasi sesuai dengan migrasi mongoDb

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/new-azdatamigrationmongodbcollectionsetting) untuk informasi terbaru.

## SYNTAX

```
New-AzDataMigrationMongoDbCollectionSetting [-TargetRequestUnit <Int32>] [-CanDelete] [-UniqueShard]
 [-ShardKey <String>] [-DefaultProfile <IAzureContextContainer>] -Name <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzDataMigrationMongoDbCollectionSetting membuat objek pengaturan migrasi yang menentukan throughput dan menghapus perilaku.
Output cmdlet adalah pasangan nilai kunci dengan nama koleksi, dan nilai pengaturan. Output digunakan dalam menyusun pengaturan tingkat database untuk migrasi.

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
Apakah data target seharusnya dihapus, jika sakelar diatur, data tersebut akan dibersihkan saat migrasi

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

### -ShardKey
Daftar tanda koma yang dipisahkan dari tombol shard. Untuk target mongoDb, Anda dapat menentukan urutan kunci shard "ShardKeyName:Order", dengan urutan 1, -1 atau kosong untuk hash, misalnya "_id,email:-1".

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
Nilai unit permintaan pengumpulan khusus. Jika tidak diatur, kumpulan tersebut menggunakan database bersama RU.

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

### -UniqueShard
Apakah akan membuat kunci unik untuk tombol shard

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.DataMigration.Models.MongoDbCollectionSetting>

## CATATAN

## RELATED LINKS
