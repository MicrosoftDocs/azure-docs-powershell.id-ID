---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/new-azdatamigrationtosqldb
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationToSqlDb.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationToSqlDb.md
ms.openlocfilehash: 2d667d72cf28d235af3d2ef2c0b9e6e51ccc2c89
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144201871"
---
# New-AzDataMigrationToSqlDb

## SYNOPSIS
Buat migrasi database baru ke SQL Db tertentu.

## SYNTAX

```
New-AzDataMigrationToSqlDb -ResourceGroupName <String> -SqlDbInstanceName <String> -TargetDbName <String>
 [-SubscriptionId <String>] [-Kind <ResourceType>] [-MigrationService <String>] [-Scope <String>]
 [-SourceDatabaseName <String>] [-SourceSqlConnectionAuthentication <String>]
 [-SourceSqlConnectionDataSource <String>] [-SourceSqlConnectionEncryptConnection]
 [-SourceSqlConnectionPassword <SecureString>] [-SourceSqlConnectionTrustServerCertificate]
 [-SourceSqlConnectionUserName <String>] [-TableList <String[]>] [-TargetDatabaseCollation <String>]
 [-TargetSqlConnectionAuthentication <String>] [-TargetSqlConnectionDataSource <String>]
 [-TargetSqlConnectionEncryptConnection] [-TargetSqlConnectionPassword <SecureString>]
 [-TargetSqlConnectionTrustServerCertificate] [-TargetSqlConnectionUserName <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Buat migrasi database baru ke SQL Db tertentu.

## EXAMPLES

### Contoh 1: Memulai Migrasi Database dari Sql Server Sumber lokal untuk menargetkan Sql Db
```powershell
New-AzDataMigrationToSqlDb -ResourceGroupName myRG -SqlDbInstanceName "mysqldb" -MigrationService  "/subscriptions/1111-2222-3333-4444/resourceGroups/myRG/providers/Microsoft.DataMigration/SqlMigrationServices/myDMS" -TargetSqlConnectionAuthentication "SqlAuthentication" -TargetSqlConnectionDataSource "mydb.windows.net" -TargetSqlConnectionPassword "pass" -TargetSqlConnectionUserName "user" -SourceSqlConnectionAuthentication "SqlAuthentication" -SourceSqlConnectionDataSource "xyz.MICROSOFT.COM" -SourceSqlConnectionUserName "user1" -SourceSqlConnectionPassword "password" -SourceDatabaseName "sourcedb" -TargetDbName "mydb1" -Scope  "/subscriptions/1111-2222-3333-4444/resourceGroups/myRG/providers/Microsoft.Sql/servers/mysqldb"
```

```output
Name       Kind  ProvisioningState MigrationStatus
-----       ----  ----------------- ---------------
mydb1       SqlDb   Succeeded         InProgress
```

Memulai Migrasi Database dari Sql Server Sumber lokal untuk menargetkan Sql Db

### Contoh 2: Memulai Migrasi Database dengan beberapa tabel yang dipilih dari Sql Server Sumber lokal untuk menargetkan Sql Db
```powershell
$sourcePassword = ConvertTo-SecureString "pass123" -AsPlainText -Force
$targetPassword = ConvertTo-SecureString "pass123" -AsPlainText -Force
New-AzDataMigrationToSqlDb -ResourceGroupName myRG -SqlDbInstanceName "mysqldb" -MigrationService  "/subscriptions/1111-2222-3333-4444/resourceGroups/myRG/providers/Microsoft.DataMigration/SqlMigrationServices/myDMS" -TargetSqlConnectionAuthentication "SqlAuthentication" -TargetSqlConnectionDataSource "mydb.windows.net" -TargetSqlConnectionPassword $targetPassword -TargetSqlConnectionUserName "user" -SourceSqlConnectionAuthentication "SqlAuthentication" -SourceSqlConnectionDataSource "xyz.MICROSOFT.COM" -SourceSqlConnectionUserName "user1" -SourceSqlConnectionPassword $sourcePassword -SourceDatabaseName "sourcedb" -TargetDbName "mydb1" -Scope  "/subscriptions/1111-2222-3333-4444/resourceGroups/myRG/providers/Microsoft.Sql/servers/mysqldb"  -TableList "table_1"
```

```output
Name       Kind  ProvisioningState MigrationStatus
-----       ----  ----------------- ---------------
mydb1       SqlDb   Succeeded         InProgress
```

Memulai Migrasi Database dengan beberapa tabel yang dipilih dari Sql Server Sumber lokal untuk menargetkan Sql Db

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kind
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Support.ResourceType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationService
ID Sumber Daya dari Layanan Migrasi.

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

### -NoWait
Jalankan perintah secara asinkron

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

### -PassThru
Mengembalikan true saat perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

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

### -Cakupan
Id sumber daya sumber daya target (SQL VM atau SQL Managed Instance)

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

### -SourceDatabaseName
Nama database sumber.

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

### -SourceSqlConnectionAuthentication
Jenis autentikasi.

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

### -SourceSqlConnectionDataSource
Sumber data.

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

### -SourceSqlConnectionEncryptConnection
Apakah akan mengenkripsi koneksi atau tidak.

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

### -SourceSqlConnectionPassword
Kata sandi untuk menyambungkan ke SQL sumber.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceSqlConnectionTrustServerCertificate
Apakah akan mempercayai sertifikat server atau tidak.

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

### -SourceSqlConnectionUserName
Nama pengguna untuk menyambungkan ke SQL sumber.

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

### -SqlDbInstanceName
.

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

### -SubscriptionId
ID langganan yang mengidentifikasi langganan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableList
Daftar tabel yang akan disalin.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabaseCollation
Kolase database yang akan digunakan untuk database target.

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

### -TargetDbName
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

### -TargetSqlConnectionAuthentication
Jenis autentikasi.

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

### -TargetSqlConnectionDataSource
Sumber data.

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

### -TargetSqlConnectionEncryptConnection
Apakah akan mengenkripsi koneksi atau tidak.

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

### -TargetSqlConnectionPassword
Kata sandi untuk menyambungkan ke SQL sumber.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetSqlConnectionTrustServerCertificate
Apakah akan mempercayai sertifikat server atau tidak.

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

### -TargetSqlConnectionUserName
Nama pengguna untuk menyambungkan ke SQL sumber.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20220330Preview.IDatabaseMigrationSqlDb

## NOTES

ALIAS

## RELATED LINKS
