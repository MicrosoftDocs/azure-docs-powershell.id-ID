---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 48CF206C-AF63-4013-834E-8EC3646D180B
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqldatabasedatamaskingrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseDataMaskingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseDataMaskingRule.md
ms.openlocfilehash: 01ad51523cd6a407a49b3b6770c9afe6234523a2
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145619140"
---
# Get-AzSqlDatabaseMaskingRule

## SYNOPSIS
Mengatur properti aturan masking data untuk database.

## SYNTAX

```
Set-AzSqlDatabaseDataMaskingRule [-MaskingFunction <String>] [-PrefixSize <UInt32>]
 [-ReplacementString <String>] [-SuffixSize <UInt32>] [-NumberFrom <Double>] [-NumberTo <Double>] [-PassThru]
 -SchemaName <String> -TableName <String> -ColumnName <String> [-ServerName] <String> [-DatabaseName] <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlDatabaseDataMaskingRule** menetapkan aturan masking data untuk database Azure SQL.
Untuk menggunakan cmdlet, berikan parameter *ResourceGroupName*, *ServerName*, *DatabaseName*, dan *RuleId* untuk mengidentifikasi aturan.
Anda dapat memberikan salah satu parameter *SchemaName*, *TableName*, dan *ColumnName* untuk menargetkan ulang aturan.
Tentukan parameter *MaskingFunction* untuk mengubah cara data disembunyikan.
Jika Anda menentukan nilai Angka atau Teks untuk *MaskingFunction*, Anda dapat menentukan parameter *NumberFrom* dan *NumberTo* untuk masking angka atau parameter *PrefiksSize*, *ReplacementString*, dan parameter *SuffixSize* untuk masking teks.
Jika perintah berhasil, dan jika Anda menentukan parameter *PassThru*, cmdlet mengembalikan objek yang menjelaskan properti aturan masking data dan pengidentifikasi aturan.
Pengidentifikasi aturan termasuk, tetapi tidak terbatas pada, **ResourceGroupName**, **ServerName**, **DatabaseName**, dan **RuleId**.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mengubah rentang aturan masking data dalam database
```powershell
Set-AzSqlDatabaseDataMaskingRule -ResourceGroupName $params.rgname -ServerName $params.serverName  -DatabaseName $params.databaseName -SchemaName "dbo" -TableName  "table1" -ColumnName "column1" -MaskingFunction "Default"
```

Perintah ini memodifikasi aturan masking data yang memiliki Aturan ID17.
Aturan itu beroperasi dalam database bernama Database01 di server Server01.
Perintah ini mengubah batas untuk interval di mana angka acak dihasilkan sebagai nilai yang ditutupi.
Rentang baru adalah antara 23 dan 42.

### Contoh 2

Mengatur properti aturan masking data untuk database. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Set-AzSqlDatabaseDataMaskingRule -ColumnName 'column1' -DatabaseName $params.databaseName -MaskingFunction NoMasking -NumberFrom 5 -NumberTo 14 -PrefixSize <UInt32> -ReplacementString <String> -ResourceGroupName $params.rgname -SchemaName 'dbo' -ServerName $params.serverName -SuffixSize <UInt32> -TableName 'table1'
```

## PARAMETERS

### -ColumnName
Menentukan nama kolom yang ditargetkan oleh aturan masking.

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
Menentukan nama database.

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

### -MaskingFunction
Menentukan fungsi masking yang digunakan aturan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Default
- NoMasking
- Teks
- Telepon
- SocialSecurityNumber
- CreditCardNumber
- Email Nilai defaultnya adalah Default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: NoMasking, Default, Text, Number, SocialSecurityNumber, CreditCardNumber, Email

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberFrom
Menentukan jumlah batas bawah interval tempat nilai acak dipilih.
Tentukan parameter ini hanya jika Anda menentukan nilai Angka untuk parameter *MaskingFunction* .
Nilai default adalah 0.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberTo
Menentukan jumlah batas atas interval tempat nilai acak dipilih.
Tentukan parameter ini hanya jika Anda menentukan nilai Angka untuk parameter *MaskingFunction* .
Nilai default adalah 0.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item tempat Anda bekerja.
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

### -PrefixSize
Menentukan jumlah karakter di awal teks yang tidak diselubungi.
Tentukan parameter ini hanya jika Anda menentukan nilai Teks untuk parameter *MaskingFunction* .
Nilai default adalah 0.

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

### -ReplacementString
Menentukan jumlah karakter di akhir teks yang tidak diselubungi.
Tentukan parameter ini hanya jika Anda menentukan nilai Teks untuk parameter *MaskingFunction* .
Nilai default adalah 0.

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

### -SchemaName
Menentukan nama skema.

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

### -SuffixSize
Menentukan jumlah karakter di akhir teks yang tidak diselubungi.
Tentukan parameter ini hanya jika Anda menentukan nilai Teks untuk parameter *MaskingFunction* .
Nilai default adalah 0.

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

### -TableName
Menentukan nama tabel database yang berisi kolom bertopeng.

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

### System.Nullable'1[[System.UInt32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Double, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.Sql.DataMasking.Model.DatabaseDataMaskingRuleModel

## NOTES

## RELATED LINKS

[Get-AzSqlDatabaseMaskingRule](./Get-AzSqlDatabaseDataMaskingRule.md)

[Get-AzSqlDatabaseMaskingRule](./New-AzSqlDatabaseDataMaskingRule.md)

[Get-AzSqlDatabaseMaskingRule](./Remove-AzSqlDatabaseDataMaskingRule.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


