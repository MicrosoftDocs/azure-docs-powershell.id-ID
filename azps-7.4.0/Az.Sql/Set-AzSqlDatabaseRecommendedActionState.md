---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: BDBA3AA3-DCC6-4C83-84C8-EE6D93BFE1D3
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqldatabaserecommendedactionstate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseRecommendedActionState.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseRecommendedActionState.md
ms.openlocfilehash: 13e6e0ec48b0a3f1d184473614fa07a6dfabe706
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142933373"
---
# Set-AzSqlDatabaseRecommendedActionState

## SYNOPSIS
Memperbarui status tindakan yang direkomendasikan Azure SQL Database.

## SYNTAX

```
Set-AzSqlDatabaseRecommendedActionState -RecommendedActionName <String> -State <RecommendedActionState>
 -ServerName <String> -DatabaseName <String> -AdvisorName <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Set-AzSqlDatabaseRecommendedActionState** memperbarui status Tindakan yang Direkomendasikan Azure SQL Database.
Ini memungkinkan tindakan yang direkomendasikan untuk diterapkan, dikembalikan, atau dibuang berdasarkan status baru.

## EXAMPLES

### Contoh 1: Menerapkan status tindakan yang disarankan ke tertunda
```powershell
Set-AzSqlDatabaseRecommendedActionState -ResourceGroupName "WIRunnersProd" -ServerName "wi-runner-australia-east" -DatabaseName "WIRunner" -AdvisorName "CreateIndex" -RecommendedActionName "IR_[test_schema]_[test_table_0.0361551]_6C7AE8CC9C87E7FD5893" -State Pending
```

```output
DatabaseName               : WIRunner

ResourceGroupName          : WIRunnersProd
ServerName                 : wi-runner-australia-east
AdvisorName                : CreateIndex
RecommendedActionName      : IR_[test_schema]_[test_table_0.0361551]_6C7AE8CC9C87E7FD5893
Details                    : {[indexName, nci_wi_test_table_0.0361551_6C7AE8CC9C87E7FD5893], [indexType, 
                             NONCLUSTERED], [schema, [test_schema]], [table, [test_table_0.0361551]]...} 
ErrorDetails               : Microsoft.Azure.Management.Sql.Models.RecommendedActionErrorInfo
EstimatedImpact            : {ActionDuration, SpaceChange}
ExecuteActionDuration      : PT1M
ExecuteActionInitiatedBy   : User
ExecuteActionInitiatedTime : 4/21/2016 3:24:47 PM
ExecuteActionStartTime     : 4/21/2016 3:24:47 PM
ImplementationDetails      : Microsoft.Azure.Management.Sql.Models.RecommendedActionImplementationInfo
IsArchivedAction           : False
IsExecutableAction         : True
IsRevertableAction         : True
LastRefresh                : 4/21/2016 3:24:47 PM
LinkedObjects              : {}
ObservedImpact             : {CpuUtilization, LogicalReads, LogicalWrites, QueriesWithImprovedPerformance...} 
RecommendationReason       : 
RevertActionDuration       : 
RevertActionInitiatedBy    : 
RevertActionInitiatedTime  : 
RevertActionStartTime      : 
Score                      : 2
State                      : Microsoft.Azure.Management.Sql.Models.RecommendedActionStateInfo
TimeSeries                 : {}
ValidSince                 : 4/21/2016 3:24:47 PM
```

Perintah ini memperbarui status tindakan yang direkomendasikan bernama IR_\[test_schema\]_\[test_table_0.0361551\]_6C7AE8CC9C87E7FD5893 yang termasuk dalam database bernama WIRunner menjadi Tertunda.

## PARAMETERS

### -AdvisorName
Menentukan nama penasihat tempat tindakan yang direkomendasikan ini berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database tempat cmdlet ini mengatur status tindakan yang disarankan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -RecommendedActionName
Menentukan nama tindakan yang disarankan untuk status yang sedang diperbarui.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya server yang berisi database ini.

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

### -ServerName
Menentukan nama server tempat database berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Negara Bagian
Menentukan nilai baru di mana cmdlet ini memperbarui status tindakan yang direkomendasikan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Aktif
- Tertunda
- PendingRevert
- RevertCancelled
- Diabaikan
- Diselesaikan

```yaml
Type: Microsoft.Azure.Commands.Sql.RecommendedAction.Cmdlet.RecommendedActionState
Parameter Sets: (All)
Aliases:
Accepted values: Active, Pending, PendingRevert, RevertCancelled, Ignored, Resolved

Required: True
Position: Named
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

### System.String

### Microsoft.Azure.Commands.Sql.RecommendedAction.Cmdlet.RecommendedActionState

## OUTPUTS

### Microsoft.Azure.Commands.Sql.RecommendedAction.Model.AzureSqlDatabaseRecommendedActionModel

## NOTES
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, sql, database, mssql, penasihat, rekomendasi

## RELATED LINKS

[Get-AzSqlServerAdvisor](./Get-AzSqlServerAdvisor.md)

[Get-AzSqlElasticPoolAdvisor](./Get-AzSqlElasticPoolAdvisor.md)

[Get-AzSqlServerRecommendedAction](./Get-AzSqlServerRecommendedAction.md)

[Get-AzSqlElasticPoolRecommendedAction](./Get-AzSqlElasticPoolRecommendedAction.md)

[Set-AzSqlElasticPoolRecommendedActionState](./Set-AzSqlElasticPoolRecommendedActionState.md)

[Set-AzSqlElasticPoolAdvisorAutoExecuteStatus](./Set-AzSqlElasticPoolAdvisorAutoExecuteStatus.md)

[Set-AzSqlElasticPoolRecommendedActionState](./Set-AzSqlElasticPoolRecommendedActionState.md)

[Set-AzSqlServerRecommendedActionState](./Set-AzSqlServerRecommendedActionState.md)

[Set-AzSqlElasticPoolAdvisorAutoExecuteStatus](./Set-AzSqlElasticPoolAdvisorAutoExecuteStatus.md)

[Set-AzSqlServerAdvisorAutoExecuteStatus](./Set-AzSqlServerAdvisorAutoExecuteStatus.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
