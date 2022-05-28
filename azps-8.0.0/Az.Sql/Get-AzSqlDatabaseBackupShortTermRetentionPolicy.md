---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqldatabasebackupshorttermretentionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabaseBackupShortTermRetentionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabaseBackupShortTermRetentionPolicy.md
ms.openlocfilehash: 17158c5f44208233df6861e7488fd9758a99f192
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513246"
---
# Get-AzSqlDatabaseBackupShortTermRetentionPolicy

## SYNOPSIS
Mendapatkan kebijakan penyimpanan jangka pendek cadangan.

## SYNTAX

### PolicyByResourceServerDatabaseSet (Default)
```
Get-AzSqlDatabaseBackupShortTermRetentionPolicy [-ResourceGroupName] <String> [-ServerName] <String>
 [-DatabaseName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyByInputObjectSet
```
Get-AzSqlDatabaseBackupShortTermRetentionPolicy -AzureSqlDatabaseObject <AzureSqlDatabaseModel>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyByResourceIdSet
```
Get-AzSqlDatabaseBackupShortTermRetentionPolicy -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlDatabaseBackupShortTermRetentionPolicy** mendapatkan kebijakan penyimpanan jangka pendek yang terdaftar untuk database ini.
Kebijakan ini adalah periode retensi dalam hari dan interval pencadangan diferensial dalam jam, untuk pencadangan pemulihan titik waktu.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSqlDatabaseBackupShortTermRetentionPolicy -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01
```

```output
ResourceGroupName ServerName  DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ----------  ------------ ------------- -------------------------
resourcegroup01   server01    database01   7             24
```

Perintah ini mendapatkan kebijakan penyimpanan jangka pendek untuk database01.

### Contoh 2
```powershell
Get-AzSqlDatabase -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 | Get-AzSqlDatabaseBackupShortTermRetentionPolicy
```

```output
ResourceGroupName ServerName  DatabaseName RetentionDays DiffBackupIntervalInHours
----------------- ----------  ------------ ------------- -------------------------
resourcegroup01   server01    database01   7             24
```

Perintah ini mendapatkan kebijakan penyimpanan jangka pendek untuk database01 melalui piping dalam objek database.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseBackupShortTermRetentionPolicyModel

## NOTES

## RELATED LINKS
