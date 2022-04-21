---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqldatabaselongtermretentionbackup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabaseLongTermRetentionBackup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabaseLongTermRetentionBackup.md
ms.openlocfilehash: 0ab98480d33ba4cc209e492426dc931ac213357f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142757728"
---
# Get-AzSqlDatabaseLongTermRetentionBackup

## SYNOPSIS
Mendapatkan satu atau beberapa cadangan penyimpanan jangka panjang.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/get-azsqldatabaselongtermretentionbackup) untuk informasi terbaru.

## SYNTAX

### Lokasi (Default)
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ResourceGroupName <String>]
 [-OnlyLatestPerDatabase] [-DatabaseState <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ServerName
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ServerName] <String> [-DatabaseName <String>]
 [-ResourceGroupName <String>] [-OnlyLatestPerDatabase] [-DatabaseState <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BackupName
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ServerName] <String> -DatabaseName <String>
 [-BackupName] <String> [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### GetBackupByResourceId
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ResourceId] <String> [-BackupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetBackupsByResourceId
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ResourceId] <String> [-OnlyLatestPerDatabase]
 [-DatabaseState <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetBackupByInputObject
```
Get-AzSqlDatabaseLongTermRetentionBackup [-InputObject] <AzureSqlDatabaseModel> [-BackupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetBackupsByInputObject
```
Get-AzSqlDatabaseLongTermRetentionBackup [-InputObject] <AzureSqlDatabaseModel> [-OnlyLatestPerDatabase]
 [-DatabaseState <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlDatabaseLongTermRetentionBackup** mendapatkan semua cadangan penyimpanan jangka panjang untuk lokasi, server, atau database atau mendapatkan cadangan penyimpanan jangka panjang tertentu.

## EXAMPLES

### Contoh 1: Dapatkan semua cadangan untuk lokasi
```powershell
PS C:\> Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope


BackupExpirationTime             : 3/22/2018 5:50:55 AM
BackupName                       : 601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
BackupTime                       : 3/15/2018 5:50:55 AM
DatabaseName                     : database01
DatabaseDeletionTime             :
Location                         : northeurope
ResourceId                       : /subscriptions/371edd6d-9630-4558-a7bd-ee139498e6a1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
ServerName                       : server01
ServerCreateTime                 : 2/29/2018 12:12:19 AM
ResourceGroupName                : 
BackupStorageRedundancy          : Geo

BackupExpirationTime             : 3/22/2018 11:43:18 PM
BackupName                       : 55970792-164c-4a4a-88e5-7158d092d503;131656309980000000
BackupTime                       : 3/15/2018 11:43:18 PM
DatabaseName                     : database02
DatabaseDeletionTime             : 3/18/2018 4:36:00 PM
Location                         : northeurope
ResourceId                       : /subscriptions/371edd6d-9630-4558-a7bd-ee139498e6a1/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server02/longTermRetentionDatabases/database02/longTermRetentionBackups/55970792-164c-4a4a-88e5-7158d092d503;131656309980000000
ServerName                       : server02
ServerCreateTime                 : 2/28/2018 12:12:19 AM
ResourceGroupName                : 
BackupStorageRedundancy          : Geo
```

Perintah ini mendapatkan semua cadangan penyimpanan jangka panjang untuk semua database (yang mungkin hidup atau dihapus) di southeastasia, grup sumber daya hanya akan diatur jika server aktif.

### Contoh 2: Dapatkan semua cadangan untuk lokasi di bawah grup sumber daya
```powershell
PS C:\> Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope -ResourceGroup resourceGroup01


BackupExpirationTime             : 3/22/2018 5:50:55 AM
BackupName                           : 601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
BackupTime                           : 3/15/2018 5:50:55 AM
DatabaseName                         : database01
DatabaseDeletionTime             :
Location                               : northeurope
ResourceId                           : /subscriptions/371edd6d-9630-4558-a7bd-ee139498e6a1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
ServerName                           : server01
ServerCreateTime                 : 2/29/2018 12:12:19 AM
ResourceGroupName          : resourceGroup01
BackupStorageRedundancy      : Geo
```

Perintah ini mendapatkan semua cadangan penyimpanan jangka panjang untuk semua database (yang mungkin hidup atau dihapus) di bawah grup sumber daya di northeurope.

### Contoh 3: Dapatkan cadangan penyimpanan jangka panjang tertentu
```powershell
PS C:\> Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope -ServerName server01 -DatabaseName database01 -BackupName "601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000"


BackupExpirationTime             : 3/22/2018 5:50:55 AM
BackupName                           : 601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
BackupTime                           : 3/15/2018 5:50:55 AM
DatabaseName                         : database01
DatabaseDeletionTime             :
Location                               : northeurope
ResourceId                         : /subscriptions/371edd6d-9630-4558-a7bd-ee139498e6a1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
ServerName                           : server01
ServerCreateTime                 : 2/29/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy      : Geo
```

Perintah ini mendapatkan cadangan dengan nama 601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000

### Contoh 4: Mendapatkan semua cadangan penyimpanan jangka panjang untuk database
```powershell
PS C:\> Get-AzSqlDatabase -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 | Get-AzSqlDatabaseLongTermRetentionBackup


BackupExpirationTime             : 3/22/2018 5:50:55 AM
BackupName                           : 601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
BackupTime                           : 3/15/2018 5:50:55 AM
DatabaseName                         : database01
DatabaseDeletionTime             :
Location                               : northeurope
ResourceId                           : /subscriptions/371edd6d-9630-4558-a7bd-ee139498e6a1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
ServerName                           : server01
ServerCreateTime                   : 2/29/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy      : Geo
```

Perintah ini mendapatkan semua cadangan penyimpanan jangka panjang untuk database01

### Contoh 5: Dapatkan cadangan penyimpanan jangka panjang menggunakan pemfilteran
```powershell
PS C:\> Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope -ServerName server01 -DatabaseName database01 -BackupName "601061b7*"

BackupExpirationTime             : 3/22/2018 11:43:18 PM
BackupName                         : 601061b7-164c-4a4a-88e5-7158d092d503;131656309980000000
BackupTime                           : 3/15/2018 11:43:18 PM
DatabaseName                         : database02
DatabaseDeletionTime             : 3/18/2018 4:36:00 PM
Location                               : northeurope
ResourceId                         : /subscriptions/371edd6d-9630-4558-a7bd-ee139498e6a1/resourceGroups/resourcegroup01/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database02/longTermRetentionBackups/601061b7-164c-4a4a-88e5-7158d092d503;131656309980000000
ServerName                           : server01
ServerCreateTime                   : 2/28/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy      : Geo

BackupExpirationTime             : 3/22/2018 5:50:55 AM
BackupName                           : 601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
BackupTime                           : 3/15/2018 5:50:55 AM
DatabaseName                         : database01
DatabaseDeletionTime             :
Location                               : northeurope
ResourceId                           : /subscriptions/371edd6d-9630-4558-a7bd-ee139498e6a1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/601061b7-d10b-46e0-bf77-a2bfb16a6add;131655666550000000
ServerName                           : server01
ServerCreateTime                   : 2/29/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy      : Geo
```

Perintah ini mendapatkan semua cadangan dengan nama yang dimulai dengan "601061b7"

## PARAMETERS

### -BackupName
Nama cadangan.

```yaml
Type: System.String
Parameter Sets: BackupName, GetBackupByResourceId, GetBackupByInputObject
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -DatabaseName
Nama Azure SQL Database cadangan berasal.

```yaml
Type: System.String
Parameter Sets: ServerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: BackupName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseState
Status database yang cadangannya ingin Anda temukan, Hidup, Dihapus, atau Semua.
Default ke Semua

```yaml
Type: System.String
Parameter Sets: Location, ServerName, GetBackupsByResourceId, GetBackupsByInputObject
Aliases:
Accepted values: All, Deleted, Live

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Objek database untuk mendapatkan cadangan.

```yaml
Type: Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel
Parameter Sets: GetBackupByInputObject, GetBackupsByInputObject
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
Parameter Sets: Location, ServerName, BackupName, GetBackupByResourceId, GetBackupsByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlyLatestPerDatabase
Apakah hanya mendapatkan cadangan terbaru per database.
Default ke false.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Location, ServerName, GetBackupsByResourceId, GetBackupsByInputObject
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Location, ServerName, BackupName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya database untuk mendapatkan cadangan.

```yaml
Type: System.String
Parameter Sets: GetBackupByResourceId, GetBackupsByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Nama server Azure SQL cadangan berada di bawah.

```yaml
Type: System.String
Parameter Sets: ServerName, BackupName
Aliases:

Required: True
Position: 1
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

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseLongTermRetentionBackupModel

## NOTES

## RELATED LINKS

[Update-AzSqlDatabaseLongTermRetentionBackup](./Update-AzSqlDatabaseLongTermRetentionBackup.md)

[Copy-AzSqlDatabaseLongTermRetentionBackup](./Copy-AzSqlDatabaseLongTermRetentionBackup.md)

[Remove-AzSqlDatabaseLongTermRetentionBackup](./Remove-AzSqlDatabaseLongTermRetentionBackup.md)

[Get-AzSqlDatabaseBackupLongTermRetentionPolicy](./Get-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[Set-AzSqlDatabaseBackupLongTermRetentionPolicy](./Set-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
