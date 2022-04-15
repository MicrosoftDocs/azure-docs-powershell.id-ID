---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/copy-azsqldatabaselongtermretentionbackup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Copy-AzSqlDatabaseLongTermRetentionBackup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Copy-AzSqlDatabaseLongTermRetentionBackup.md
ms.openlocfilehash: a7369e708380aa4a80b5834e50f69c7d0848f631
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142120571"
---
# Copy-AzSqlDatabaseLongTermRetentionBackup

## SYNOPSIS
Menyalin cadangan penyimpanan jangka panjang ke database target.  

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/copy-azsqldatabaselongtermretentionbackup) untuk informasi terbaru.

## SYNTAX

### CopyBackupDefault (Default)
```
Copy-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ServerName] <String> [-DatabaseName] <String>
 [-BackupName] <String> [-ResourceGroupName <String>] -TargetDatabaseName <String>
 [-TargetServerFullyQualifiedDomainName <String>] [-TargetServerName <String>] -TargetSubscriptionId <String>
 -TargetResourceGroupName <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CopyBackupByResourceId
```
Copy-AzSqlDatabaseLongTermRetentionBackup [-ResourceId] <String> -TargetDatabaseName <String>
 [-TargetServerFullyQualifiedDomainName <String>] [-TargetServerName <String>] -TargetSubscriptionId <String>
 -TargetResourceGroupName <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CopyBackupByInputObject
```
Copy-AzSqlDatabaseLongTermRetentionBackup [-InputObject] <AzureSqlDatabaseLongTermRetentionBackupModel>
 -TargetDatabaseName <String> [-TargetServerFullyQualifiedDomainName <String>] [-TargetServerName <String>]
 -TargetSubscriptionId <String> -TargetResourceGroupName <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menyalin cadangan penyimpanan jangka panjang ke database target.  Database target mungkin berada dalam kluster yang berbeda dari sumber cadangan.  

## EXAMPLES

### Contoh 1: Salin cadangan penyimpanan jangka panjang ke server lain dalam lingkungan yang sama.
```powershell
PS C:\> Copy-AzSqlDatabaseLongTermRetentionBackup -Location southeastasia -ServerName test-server -DatabaseName test-database -BackupName 'e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000' -ResourceGroupName testrg -TargetDatabaseName ltr1 -TargetServerName ayang-eas -TargetSubscriptionId '01c4ec88-e179-44f7-9eb0-e9719a5087ab' -TargetResourceGroupName testrg


SourceResourceGroupName              : test-rg
SourceLocation                       : southeastasia
SourceServerName                     : test-server
SourceDatabaseName                   : test-database
SourceBackupName                     : e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000
SourceBackupResourceId               : /subscriptions/01c4ec88-e179-44f7-9eb0-e9719a5087ab/resourceGroups/test-rg/providers/Microsoft.Sql/locations/SoutheastAsia/longTermRetentionServers/test-server/longTermRetentionDatabases/test-database/longTermRetentionBackups/e5c20f43-494c-4925-89d1-58e0f4569fb3;132579992320000000
SourceBackupStorageRedundancy        : Geo
TargetSubscriptionId                 : 01c4ec88-e179-44f7-9eb0-e9719a5087ab
TargetResourceGroupName              : test-rg
TargetLocation                       : East Asia
TargetServerName                     : ayang-eas
TargetServerFullyQualifiedDomainName :
TargetServerResourceId               : /subscriptions/01c4ec88-e179-44f7-9eb0-e9719a5087ab/resourceGroups/test-rg/providers/Microsoft.Sql/servers/ayang-eas
TargetDatabaseName                   : ltr1
TargetBackupName                     : 70554a1f-ae6e-479e-99b1-50ea320654eb;132579992320000000
TargetBackupResourceId               : /subscriptions/01c4ec88-e179-44f7-9eb0-e9719a5087ab/resourceGroups/test-rg/providers/Microsoft.Sql/locations/East Asia/longTermRetentionServers/ayang-eas/longTermRetentionDatabases/ltr1/longTermRetentionBackups/70554a1f-ae6e-479e-99b1-50ea320654eb;132579992320000000
```

Tindakan ini menyalin cadangan penyimpanan jangka panjang dari database sumber di Asia Tenggara ke database target di Asia Timur.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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
Parameter Sets: CopyBackupDefault
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Nama Azure SQL Database cadangan berasal.

```yaml
Type: System.String
Parameter Sets: CopyBackupDefault
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
Objek Cadangan Penyimpanan Jangka Panjang Database untuk dihapus.

```yaml
Type: Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseLongTermRetentionBackupModel
Parameter Sets: CopyBackupByInputObject
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
Parameter Sets: CopyBackupDefault
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
Parameter Sets: CopyBackupDefault
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya dari Cadangan Penyimpanan Jangka Panjang Database untuk dihapus.

```yaml
Type: System.String
Parameter Sets: CopyBackupByResourceId
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
Parameter Sets: CopyBackupDefault
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabaseName
Nama database target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceGroupName
ID sumber daya langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetServerFullyQualifiedDomainName
Nama domain server target yang sepenuhnya memenuhi syarat.

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

### -TargetServerName
Nama server target.

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

### -TargetSubscriptionId
ID sumber daya langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseLongTermRetentionBackupModel

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseLongTermRetentionBackupModel

## CATATAN

## RELATED LINKS

[Get-AzSqlDatabaseLongTermRetentionBackup](./Get-AzSqlDatabaseLongTermRetentionBackup.md)

[Update-AzSqlDatabaseLongTermRetentionBackup](./Update-AzSqlDatabaseLongTermRetentionBackup.md)

[Remove-AzSqlDatabaseLongTermRetentionBackup](./Remove-AzSqlDatabaseLongTermRetentionBackup.md)

[Get-AzSqlDatabaseBackupLongTermRetentionPolicy](./Get-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[Set-AzSqlDatabaseBackupLongTermRetentionPolicy](./Set-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
