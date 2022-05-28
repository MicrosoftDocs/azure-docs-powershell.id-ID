---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 1B138185-E836-414F-93CD-7BAE7F474E73
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqldatabasedatamaskingpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseDataMaskingPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseDataMaskingPolicy.md
ms.openlocfilehash: 96296421eff723624c46b524b810c845a2f8edf9
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145521082"
---
# Get-AzSqlDatabaseDataMaskingPolicy

## SYNOPSIS
Mengatur masking data untuk database.

## SYNTAX

```
Set-AzSqlDatabaseDataMaskingPolicy [-PassThru] [-PrivilegedUsers <String>] [-DataMaskingState <String>]
 [-ServerName] <String> [-DatabaseName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlDatabaseDataMaskingPolicy** menetapkan kebijakan masking data untuk database Azure SQL.
Untuk menggunakan cmdlet ini, gunakan parameter *ResourceGroupName*, *ServerName*, dan *DatabaseName* untuk mengidentifikasi database.
Anda dapat mengatur parameter *DataMaskingState* untuk menentukan apakah operasi masking data diaktifkan atau dinonaktifkan.
Jika cmdlet berhasil dan parameter *PassThru* digunakan, cmdlet mengembalikan objek yang menjelaskan kebijakan masking data saat ini selain pengidentifikasi database.
Pengidentifikasi database mencakup, tetapi tidak terbatas pada, **ResourceGroupName**, **ServerName**, dan **DatabaseName**.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mengatur kebijakan masking data untuk database
```powershell
Set-AzSqlDatabaseDataMaskingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -PrivilegedUsers "public" -DataMaskingState "Enabled"
```

Perintah ini mengatur kebijakan masking data untuk database bernama database01 di server bernama server01.

## PARAMETERS

### -DatabaseName
Menentukan nama database tempat kebijakan diatur.

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

### -DataMaskingState
Menentukan apakah operasi masking data diaktifkan atau dinonaktifkan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Aktif
- Dinonaktifkan Nilai default Diaktifkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
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

### -PassThru
Mengembalikan objek yang mewakili item yang sedang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -PrivilegedUsers
Menentukan daftar ID pengguna istimewa yang dipisahkan titik koma.
Pengguna ini diizinkan untuk melihat data masking.

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
Menentukan nama grup sumber daya tempat database ditetapkan.

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

### Microsoft.Azure.Commands.Sql.DataMasking.Model.DatabaseDataMaskingPolicyModel

## NOTES

## RELATED LINKS

[Get-AzSqlDatabaseDataMaskingPolicy](./Get-AzSqlDatabaseDataMaskingPolicy.md)

[Get-AzSqlDatabaseMaskingRule](./Get-AzSqlDatabaseDataMaskingRule.md)

[Get-AzSqlDatabaseMaskingRule](./New-AzSqlDatabaseDataMaskingRule.md)

[Get-AzSqlDatabaseMaskingRule](./Remove-AzSqlDatabaseDataMaskingRule.md)

[Get-AzSqlDatabaseMaskingRule](./Set-AzSqlDatabaseDataMaskingRule.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


