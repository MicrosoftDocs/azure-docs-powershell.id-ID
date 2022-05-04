---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/update-azsqldatabaselongtermretentionbackup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Update-AzSqlDatabaseLongTermRetentionBackup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Update-AzSqlDatabaseLongTermRetentionBackup.md
ms.openlocfilehash: d04b0e882bfe00bbb28cb85890429f3fef641691
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144708490"
---
# Update-AzSqlDatabaseLongTermRetentionBackup

## SYNOPSIS
Memperbarui cadangan retensi jangka panjang.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/update-azsqldatabaselongtermretentionbackup) untuk informasi terbaru.

## SYNTAX

### UpdateBackupDefault (Default)
```
Update-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ServerName] <String>
 [-DatabaseName] <String> [-BackupName] <String> [-ResourceGroupName <String>]
 [-BackupStorageRedundancy <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateBackupByResourceId
```
Update-AzSqlDatabaseLongTermRetentionBackup [-ResourceId] <String> [-BackupStorageRedundancy <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateByInputObjectSet
```
Update-AzSqlDatabaseLongTermRetentionBackup [-BackupStorageRedundancy <String>]
 [-InputObject] <AzureSqlDatabaseLongTermRetentionBackupModel> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui properti cadangan retensi jangka panjang.
  

## EXAMPLES

### Contoh 1: Perbarui Pencadangan Storage Redundansi cadangan retensi jangka panjang.
```powershell
Update-AzSqlDatabaseLongTermRetentionBackup -Location southeastasia -ServerName ayang-stage-seas -DatabaseName ltr3 -BackupName 'e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000' -ResourceGroupName testrg -BackupStorageRedundancy Geo
```

```output
BackupExpirationTime             : 3/19/2021 1:33:52 AM
BackupName                       : e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000
BackupTime                       : 2/17/2021 1:33:52 AM
DatabaseName                     : ltr3
DatabaseDeletionTime             : 3/16/2021 6:28:11 AM
Location                         : southeastasia
ResourceId                       : /subscriptions/01c4ec88-e179-44f7-9eb0-e9719a5087ab/resourceGroups/testrg/providers/Microsoft.Sql/locations/southeastasia/longTermRetentionServers/ayang-stage-seas/longTermRetentionDatabases/ltr3/longTermRetentionBackups/e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000
ServerName                       : ayang-stage-seas
ServerCreateTime                 : 4/22/2020 9:58:33 PM
ResourceGroupName                : testrg
BackupStorageRedundancy          : Geo
```

Perintah ini mengatur Redundansi Storage Cadangan yang ditentukan menggunakan nama lokasi dan Grup Sumber Daya, Server, Database, dan Cadangan.  

### Contoh 2: Memperbarui Pencadangan Storage Redundansi cadangan retensi jangka panjang (menggunakan Id Sumber Daya).
```powershell
Update-AzSqlDatabaseLongTermRetentionBackup -ResourceId '/subscriptions/01c4ec88-e179-44f7-9eb0-e9719a5087ab/resourceGroups/testrg/providers/Microsoft.Sql/locations/southeastasia/longTermRetentionServers/ayang-stage-seas/longTermRetentionDatabases/ltr3/longTermRetentionBackups/e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000' -BackupStorageRedundancy Geo
```

```output
BackupExpirationTime             : 3/19/2021 1:33:52 AM
BackupName                       : e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000
BackupTime                       : 2/17/2021 1:33:52 AM
DatabaseName                     : ltr3
DatabaseDeletionTime             : 3/16/2021 6:28:11 AM
Location                         : southeastasia
ResourceId                       : /subscriptions/01c4ec88-e179-44f7-9eb0-e9719a5087ab/resourceGroups/testrg/providers/Microsoft.Sql/locations/southeastasia/longTermRetentionServers/ayang-stage-seas/longTermRetentionDatabases/ltr3/longTermRetentionBackups/e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000
ServerName                       : ayang-stage-seas
ServerCreateTime                 : 4/22/2020 9:58:33 PM
ResourceGroupName                : testrg
BackupStorageRedundancy          : Geo
```

Perintah ini mengatur Redundansi Storage Cadangan yang ditentukan menggunakan Id Sumber Daya cadangan. 

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -BackupName
Nama cadangan.

```yaml
Type: System.String
Parameter Sets: UpdateBackupDefault
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackupStorageRedundancy
Redundansi penyimpanan Cadangan yang digunakan untuk menyimpan cadangan untuk SQL Database.
Opsinya adalah: Lokal, Zona, dan Geo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Zone, Geo

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Nama Azure SQL Database cadangan berasal.

```yaml
Type: System.String
Parameter Sets: UpdateBackupDefault
Aliases:

Required: True
Position: 2
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

### -InputObject
Objek Cadangan Retensi Jangka Panjang Database yang akan diperbarui.

```yaml
Type: Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseLongTermRetentionBackupModel
Parameter Sets: UpdateByInputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi server sumber cadangan.

```yaml
Type: System.String
Parameter Sets: UpdateBackupDefault
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateBackupDefault
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya dari Cadangan Retensi Jangka Panjang Database untuk dihapus.

```yaml
Type: System.String
Parameter Sets: UpdateBackupByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Nama Server Azure SQL tempat cadangan berada.

```yaml
Type: System.String
Parameter Sets: UpdateBackupDefault
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseLongTermRetentionBackupModel

## NOTES

## RELATED LINKS

[Get-AzSqlDatabaseLongTermRetentionBackup](./Get-AzSqlDatabaseLongTermRetentionBackup.md)

[Copy-AzSqlDatabaseLongTermRetentionBackup](./Copy-AzSqlDatabaseLongTermRetentionBackup.md)

[Remove-AzSqlDatabaseLongTermRetentionBackup](./Remove-AzSqlDatabaseLongTermRetentionBackup.md)

[Get-AzSqlDatabaseBackupLongTermRetentionPolicy](./Get-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[Set-AzSqlDatabaseBackupLongTermRetentionPolicy](./Set-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
