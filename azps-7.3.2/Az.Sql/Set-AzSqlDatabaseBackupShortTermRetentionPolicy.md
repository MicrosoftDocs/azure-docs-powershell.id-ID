---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqldatabasebackupshorttermretentionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseBackupShortTermRetentionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseBackupShortTermRetentionPolicy.md
ms.openlocfilehash: 9e76e42899c82c11a0765a324ddf6516f2b55d67
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142207567"
---
# Set-AzSqlDatabaseBackupShortTermRetentionPolicy

## SYNOPSIS
Mengatur kebijakan penyimpanan jangka pendek cadangan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/set-azsqldatabasebackupshorttermretentionpolicy) untuk informasi terbaru.

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
Cmdlet **Set-AzSqlDatabaseBackupShortTermRetentionPolicy** mengatur kebijakan penyimpanan jangka pendek untuk database ini.
Kebijakan ini adalah periode penyimpanan, dalam hari, untuk pencadangan pemulihan point-in-time dan frekuensi pencadangan disensial, dalam jam.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzSqlDatabaseBackupShortTermRetentionPolicy -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 -RetentionDays 6 -DiffBackupIntervalInHours 24
ResourceGroupName ServerName DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ---------- ------------ ------------- -------------------------
resourcegroup01   server01   database01   6             24
```

Perintah ini mengatur kebijakan penyimpanan jangka pendek untuk database01 hingga 6 hari penyimpanan dan 24 jam interval cadangan disendata.

### Contoh 2
```powershell
PS C:\> Get-AzSqlDatabase -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 | Set-AzSqlDatabaseBackupShortTermRetentionPolicy -RetentionDays 5 -DiffBackupIntervalInHours 12
ResourceGroupName ServerName DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ---------- ------------ ------------- ------------------------
resourcegroup01   server01   database01   5             12
```

Perintah ini mengatur kebijakan penyimpanan jangka pendek untuk database01 hingga 5 hari penyimpanan dan 12 jam interval cadangan disendata melalui pipa dalam objek database.

### Contoh 3
```powershell
PS C:\> Set-AzSqlDatabaseBackupShortTermRetentionPolicy -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 -RetentionDays 7
ResourceGroupName ServerName DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ---------- ------------ ------------- -------------------------
resourcegroup01   server01   database01   7             12
```

Perintah ini mengatur kebijakan penyimpanan jangka pendek untuk database01 hingga 7 hari penyimpanan saja. DiffBackupIntervalInHours tidak berubah.  

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
Nama Azure SQL Database untuk digunakan.

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
Frekuensi pencadangan dibingkai dalam jam.

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
Pengaturan penyimpanan cadangan, dalam beberapa hari.

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
Nama Server Azure SQL tempat database berada.

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

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseBackupShortTermRetentionPolicyModel

## CATATAN

## RELATED LINKS
