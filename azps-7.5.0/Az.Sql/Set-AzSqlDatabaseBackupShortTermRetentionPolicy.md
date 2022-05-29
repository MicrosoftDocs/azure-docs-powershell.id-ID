---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqldatabasebackupshorttermretentionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseBackupShortTermRetentionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseBackupShortTermRetentionPolicy.md
ms.openlocfilehash: 10fb6e62b48d3702d0683fab6ffc7bf07028047e
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145723546"
---
# Set-AzSqlDatabaseBackupShortTermRetentionPolicy

## SYNOPSIS
Menetapkan kebijakan penyimpanan jangka pendek cadangan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/set-azsqldatabasebackupshorttermretentionpolicy) untuk informasi terbaru.

## SYNTAX

### PolicyByResourceServerDatabaseSet (Default)
```
Set-AzSqlDatabaseBackupShortTermRetentionPolicy [-RetentionDays <Int32>] [-DiffBackupIntervalInHours <Int32>]
 [-ResourceGroupName] <String> [-ServerName] <String> [-DatabaseName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PolicyByInputObjectSet
```
Set-AzSqlDatabaseBackupShortTermRetentionPolicy [-RetentionDays <Int32>] [-DiffBackupIntervalInHours <Int32>]
 -AzureSqlDatabaseObject <AzureSqlDatabaseModel> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### PolicyByResourceIdSet
```
Set-AzSqlDatabaseBackupShortTermRetentionPolicy [-RetentionDays <Int32>] [-DiffBackupIntervalInHours <Int32>]
 -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlDatabaseBackupShortTermRetentionPolicy** menetapkan kebijakan penyimpanan jangka pendek untuk database ini.
Kebijakan ini adalah periode retensi, dalam hari, untuk pencadangan pemulihan titik waktu dan frekuensi pencadangan diferensial, dalam jam.

## EXAMPLES

### Contoh 1
```powershell
Set-AzSqlDatabaseBackupShortTermRetentionPolicy -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 -RetentionDays 6 -DiffBackupIntervalInHours 24
```

```output
ResourceGroupName ServerName DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ---------- ------------ ------------- -------------------------
resourcegroup01   server01   database01   6             24
```

Perintah ini menetapkan kebijakan penyimpanan jangka pendek untuk database01 hingga 6 hari retensi dan 24 jam interval cadangan diferensial.

### Contoh 2
```powershell
Get-AzSqlDatabase -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 | Set-AzSqlDatabaseBackupShortTermRetentionPolicy -RetentionDays 5 -DiffBackupIntervalInHours 12
```

```output
ResourceGroupName ServerName DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ---------- ------------ ------------- ------------------------
resourcegroup01   server01   database01   5             12
```

Perintah ini menetapkan kebijakan penyimpanan jangka pendek untuk database01 hingga 5 hari retensi dan 12 jam interval cadangan diferensial melalui piping dalam objek database.

### Contoh: 3
```powershell
Set-AzSqlDatabaseBackupShortTermRetentionPolicy -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 -RetentionDays 7
```

```output
ResourceGroupName ServerName DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ---------- ------------ ------------- -------------------------
resourcegroup01   server01   database01   7             12
```

Perintah ini menetapkan kebijakan penyimpanan jangka pendek hanya untuk database01 hingga 7 hari retensi. DiffBackupIntervalInHours tidak berubah.  

## PARAMETERS

### -AzureSqlDatabaseObject
Objek database untuk mendapatkan kebijakan.

```yaml
Type: Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel
Parameter Sets: PolicyByInputObjectSet
Aliases: AzureSqlDatabase

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Nama Azure SQL Database yang akan digunakan.

```yaml
Type: System.String
Parameter Sets: PolicyByResourceServerDatabaseSet
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiffBackupIntervalInHours
Frekuensi pencadangan diferensial dalam jam.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: PolicyByResourceServerDatabaseSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya kebijakan penyimpanan jangka pendek.

```yaml
Type: System.String
Parameter Sets: PolicyByResourceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionDays
Pengaturan retensi cadangan, dalam beberapa hari.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 7
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Nama server Azure SQL tempat database berada.

```yaml
Type: System.String
Parameter Sets: PolicyByResourceServerDatabaseSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseBackupShortTermRetentionPolicyModel

## NOTES

## RELATED LINKS
