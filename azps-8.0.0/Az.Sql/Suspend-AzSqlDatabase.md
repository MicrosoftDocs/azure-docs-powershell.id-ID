---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 7302D785-9DD0-4CC0-93C9-9A6EA60591CF
online version: https://docs.microsoft.com/powershell/module/az.sql/suspend-azsqldatabase
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Suspend-AzSqlDatabase.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Suspend-AzSqlDatabase.md
ms.openlocfilehash: c1b848e541168420024c395b225ede32aa867e36
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513219"
---
# Menangguhkan-AzSqlDatabase

## SYNOPSIS
Menangguhkan database Gudang Data SQL.

## SYNTAX

```
Suspend-AzSqlDatabase [-ServerName] <String> -DatabaseName <String> [-AsJob] [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Suspend-AzSqlDatabase** menangguhkan database Gudang Data Azure SQL.

## EXAMPLES

### Contoh 1: Menangguhkan database Gudang Data Azure SQL
```powershell
Suspend-AzSqlDatabase -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01"
```

Perintah ini menangguhkan database Gudang Data Azure SQL aktif.

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

### -DatabaseName
Menentukan nama database yang ditangguhkan cmdlet ini.

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
Menentukan nama grup sumber daya tempat server ditetapkan.

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
Menentukan nama server yang menghosting database.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

## NOTES
* **Cmdlet Suspend-AzSqlDatabase** hanya berfungsi pada database Gudang Data Azure SQL. Operasi ini tidak didukung pada edisi dasar, standar, dan Premium Azure SQL Database.

## RELATED LINKS

[Dapatkan-AzSqlDatabase](./Get-AzSqlDatabase.md)

[Baru-AzSqlDatabase](./New-AzSqlDatabase.md)

[Hapus-AzSqlDatabase](./Remove-AzSqlDatabase.md)

[Melanjutkan-AzSqlDatabase](./Resume-AzSqlDatabase.md)

[Set-AzSqlDatabase](./Set-AzSqlDatabase.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


