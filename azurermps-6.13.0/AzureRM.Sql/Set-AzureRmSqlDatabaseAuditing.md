---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: F7EF35E3-BC53-43D9-A71E-0B4316260A08
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqldatabaseauditing
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlDatabaseAuditing.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlDatabaseAuditing.md
ms.openlocfilehash: e28295a5f743e1475075e93a52c21bba8bd83e08
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "140856638"
---
# Set-AzureRmSqlDatabaseAuditing

## SYNOPSIS
Mengubah pengaturan pengauditan untuk database SQL Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DefaultParameterSet (Default)
```
Set-AzureRmSqlDatabaseAuditing -State <String> [-PassThru] [-AuditActionGroup <AuditActionGroups[]>]
 [-AuditAction <String[]>] [-StorageAccountName <String>] [-StorageKeyType <String>]
 [-RetentionInDays <UInt32>] [-PredicateExpression <String>] [-ServerName] <String> [-DatabaseName] <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### StorageAccountSubscriptionIdSet
```
Set-AzureRmSqlDatabaseAuditing -State <String> [-PassThru] [-AuditActionGroup <AuditActionGroups[]>]
 [-AuditAction <String[]>] -StorageAccountName <String> [-StorageAccountSubscriptionId <Guid>]
 [-StorageKeyType <String>] [-RetentionInDays <UInt32>] [-PredicateExpression <String>] [-ServerName] <String>
 [-DatabaseName] <String> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmSqlDatabaseAuditing** mengubah pengaturan audit database SQL Azure.
Untuk menggunakan cmdlet, gunakan parameter *ResourceGroupName*, *ServerName*, *dan DatabaseName* untuk mengidentifikasi database.
Tentukan parameter *StorageAccountName* untuk menentukan akun penyimpanan bagi log audit dan parameter *StorageKeyType* untuk menentukan kunci penyimpanan.
Gunakan parameter *Status* untuk mengaktifkan/menonaktifkan kebijakan.
Anda juga bisa menentukan penyimpanan untuk log audit dengan mengatur nilai parameter *RetentionInDays* untuk menentukan periode untuk log audit.
Setelah cmdlet berhasil dijalankan, pengauditan database akan diaktifkan.
Jika cmdlet berhasil dan Anda menggunakan parameter *PassThru* , objek akan mengembalikan objek yang menjelaskan kebijakan audit blob saat ini selain pengidentifikasi database.
Pengidentifikasi database menyertakan, tetapi tidak terbatas pada, **ResourceGroupName**, **ServerName**, dan **DatabaseName**.

## EXAMPLES

### Contoh 1: Mengaktifkan kebijakan pengauditan database Azure SQL baru
```
PS C:\>Set-AzureRmSqlDatabaseAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22" -DatabaseName "Database01"
```

### Contoh 2: Menonaktifkan kebijakan audit blob database SQL Azure
```
PS C:\>Set-AzureRmSqlDatabaseAuditing -State Disabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01"
```

### Contoh 3: Mengaktifkan kebijakan pengauditan database Azure SQL menggunakan akun penyimpanan dari langganan lain
```
PS C:\>Set-AzureRmSqlDatabaseAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22" -StorageAccountSubscriptionId "7fe3301d-31d3-4668-af5e-211a890ba6e3"
```

### Contoh 4: Mengaktifkan kebijakan pengauditan yang diperluas database Azure SQL baru
```
PS C:\>Set-AzureRmSqlDatabaseAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22" -DatabaseName "Database01" -PredicateExpression "statement <> 'select 1'"
```

### Contoh 5: Hapus kebijakan pengauditan yang diperluas database Azure SQL, lalu atur kebijakan pengauditan, bukan kebijakan audit.
```
PS C:\>Set-AzureRmSqlDatabaseAuditing -State Enabled -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountName "Storage22" -DatabaseName "Database01" -PredicateExpression ""
```

## PARAMETERS

### -AuditAction
Kumpulan tindakan audit.
Tindakan yang didukung untuk diaudit adalah: SELECT UPDATE INSERT DELETE EXECUTE RECEIVE REFERENCES Formulir umum untuk menetapkan tindakan yang akan diaudit adalah: [tindakan] ON [objek] BY [prinsipal] Perhatikan bahwa [objek] dalam format di atas dapat merujuk ke objek seperti tabel, tampilan, atau prosedur yang disimpan, atau seluruh database atau skema. Untuk kasus yang terakhir ini, formulir DATABASE::[dbname] dan SCHEMA::[schemaname] digunakan untuk masing-masing.
Misalnya: SELECT on dbo.myTable dengan public SELECT on DATABASE::myDatabase by public SELECT di SCHEMA::mySchema by public Untuk informasi selengkapnya, lihat https://docs.microsoft.com/en-us/sql/relational-databases/security/auditing/sql-server-audit-action-groups-and-actions#database-level-audit-actions.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuditActionGroup
Kumpulan grup tindakan yang disarankan untuk digunakan adalah kombinasi berikut ini, yang akan mengaudit semua kueri dan prosedur tersimpan yang dijalankan terhadap database, serta berhasil dan gagal masuk: "BATCH_COMPLETED_GROUP", "SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP", "FAILED_DATABASE_AUTHENTICATION_GROUP" Kombinasi di atas juga merupakan kumpulan yang dikonfigurasi secara default. Grup ini mencakup SQL pernyataan privasi dan prosedur tersimpan yang dijalankan terhadap database, dan tidak boleh digunakan dalam kombinasi dengan grup lain karena ini akan menghasilkan log audit duplikat. Untuk informasi selengkapnya, lihat https://docs.microsoft.com/en-us/sql/relational-databases/security/auditing/sql-server-audit-action-groups-and-actions#database-level-audit-action-groups.

```yaml
Type: Microsoft.Azure.Commands.Sql.Auditing.Model.AuditActionGroups[]
Parameter Sets: (All)
Aliases:
Accepted values: BATCH_STARTED_GROUP, BATCH_COMPLETED_GROUP, APPLICATION_ROLE_CHANGE_PASSWORD_GROUP, BACKUP_RESTORE_GROUP, DATABASE_LOGOUT_GROUP, DATABASE_OBJECT_CHANGE_GROUP, DATABASE_OBJECT_OWNERSHIP_CHANGE_GROUP, DATABASE_OBJECT_PERMISSION_CHANGE_GROUP, DATABASE_OPERATION_GROUP, AUDIT_CHANGE_GROUP, DATABASE_PERMISSION_CHANGE_GROUP, DATABASE_PRINCIPAL_CHANGE_GROUP, DATABASE_PRINCIPAL_IMPERSONATION_GROUP, DATABASE_ROLE_MEMBER_CHANGE_GROUP, FAILED_DATABASE_AUTHENTICATION_GROUP, SCHEMA_OBJECT_ACCESS_GROUP, SCHEMA_OBJECT_CHANGE_GROUP, SCHEMA_OBJECT_OWNERSHIP_CHANGE_GROUP, SCHEMA_OBJECT_PERMISSION_CHANGE_GROUP, SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP, USER_CHANGE_PASSWORD_GROUP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
SQL Database nama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
{{fill passThru Description}}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PredicateExpression
Pernyataan Klausul Where digunakan untuk memfilter log audit.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionInDays
Jumlah hari penyimpanan untuk log audit.

```yaml
Type: System.Nullable`1[System.UInt32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
SQL Database server baru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Negara Bagian
Status kebijakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Nama akun penyimpanan. Karakter wildcard tidak diizinkan.
Parameter ini tidak diperlukan.
Jika Anda tidak menentukan parameter ini, cmdlet menggunakan akun penyimpanan yang sebelumnya ditetapkan sebagai bagian dari kebijakan audit.
Jika ini adalah kali pertama kebijakan audit ditetapkan dan Anda tidak menentukan parameter ini, cmdlet akan gagal.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: StorageAccountSubscriptionIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountSubscriptionId
Menentukan id langganan akun penyimpanan

```yaml
Type: System.Guid
Parameter Sets: StorageAccountSubscriptionIdSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageKeyType
Menentukan kunci akses penyimpanan mana yang akan digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Primary, Secondary

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS
