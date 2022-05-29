---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 50E09DF7-F5B5-4668-9520-73D562E91800
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqldatabaseadvisorautoexecutestatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseAdvisorAutoExecuteStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseAdvisorAutoExecuteStatus.md
ms.openlocfilehash: 723ccd51f62271fbe198343f6f0cf0aed718730c
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145723582"
---
# Set-AzSqlDatabaseAdvisorAutoExecuteStatus

## SYNOPSIS
Memodifikasi status eksekusi otomatis Azure SQL Database Advisor.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/set-azsqldatabaseadvisorautoexecutestatus) untuk informasi terbaru.

## SYNTAX

```
Set-AzSqlDatabaseAdvisorAutoExecuteStatus -AdvisorName <String> -AutoExecuteStatus <AdvisorAutoExecuteStatus>
 -ServerName <String> -DatabaseName <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlDatabaseAdvisorAutoExecuteStatus** memodifikasi properti eksekusi otomatis untuk Azure SQL Database Advisor.
Saat ini, cmdlet ini mendukung nilai Diaktifkan, Dinonaktifkan, dan Default.

## EXAMPLES

### Contoh 1: Mengaktifkan eksekusi otomatis untuk advisor
```powershell
Set-AzSqlDatabaseAdvisorAutoExecuteStatus -ResourceGroupName "ContosoRunnersProd" -ServerName "runner-australia-east" -DatabaseName "ContosoRunner" -AdvisorName "CreateIndex" -AutoExecuteStatus Enabled
```

```output
DatabaseName                   : ContosoRunner
ResourceGroupName              : ContosoRunnersProd
ServerName                     : runner-australia-east
AdvisorName                    : CreateIndex
AdvisorStatus                  : GA
AutoExecuteStatus              : Enabled
AutoExecuteStatusInheritedFrom : Database
LastChecked                    : 8/1/2016 2:36:47 PM
RecommendationsStatus          : Ok
RecommendedActions             : {}
```

Perintah ini mengubah status eksekusi otomatis penasihat bernama CreateIndex menjadi Diaktifkan.

## PARAMETERS

### -AdvisorName
Menentukan nama advisor yang cmdlet ini memodifikasi status.

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

### -AutoExecuteStatus
Menentukan nilai untuk status.
Nilai yang dapat diterima untuk parameter ini adalah:
- Aktif 
- Nonaktif 
- Default

```yaml
Type: Microsoft.Azure.Commands.Sql.Advisor.Cmdlet.AdvisorAutoExecuteStatus
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled, Default

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database yang cmdlet ini memodifikasi status.

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
Menentukan nama server untuk database.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.Sql. Advisor. Cmdlet.AdvisorAutoExecuteStatus

## OUTPUTS

### Microsoft.Azure.Commands.Sql. Advisor. Model.AzureSqlDatabaseAdvisorModel

## NOTES

## RELATED LINKS

[Get-AzSqlDatabaseAdvisor](./Get-AzSqlDatabaseAdvisor.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)

