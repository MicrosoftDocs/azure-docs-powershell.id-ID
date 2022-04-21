---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: A123CB7F-2F95-49EE-9F57-E264EB1F9093
online version: https://docs.microsoft.com/powershell/module/az.sql/new-azsqldatabasedatamaskingrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlDatabaseDataMaskingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlDatabaseDataMaskingRule.md
ms.openlocfilehash: 661dd9d25aaefc0e6b7d97d39e9988d94e2f07a8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142693530"
---
# New-AzSqlDatabaseDataMaskingRule

## SYNOPSIS
Membuat aturan masking data untuk database.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/new-azsqldatabasedatamaskingrule) untuk informasi terbaru.

## SYNTAX

```
New-AzSqlDatabaseDataMaskingRule -MaskingFunction <String> [-PrefixSize <UInt32>] [-ReplacementString <String>]
 [-SuffixSize <UInt32>] [-NumberFrom <Double>] [-NumberTo <Double>] [-PassThru] -SchemaName <String>
 -TableName <String> -ColumnName <String> [-ServerName] <String> [-DatabaseName] <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSqlDatabaseDataMaskingRule** membuat aturan masking data untuk database Azure SQL.
Untuk menggunakan cmdlet, gunakan parameter *ResourceGroupName*, *ServerName*, dan *DatabaseName* untuk mengidentifikasi aturan.
Sediakan *TableName* dan *ColumnName* untuk menentukan target aturan dan parameter *MaskingFunction* untuk menentukan cara data disematkan.
Jika *MaskingFungction* memiliki nilai Angka atau Teks, Anda dapat menentukan parameter *NumberFrom* dan *NumberTo* , untuk masking angka, atau *PrefixSize*, *ReplacementString*, dan *SuffixSize* untuk masking teks.
Jika perintah berhasil dan parameter *PassThru* digunakan, cmdlet mengembalikan objek yang menjelaskan properti aturan masking data selain pengidentifikasi aturan.
Pengidentifikasi aturan menyertakan, tetapi tidak terbatas pada, *ResourceGroupName*, *ServerName*, *DatabaseName*, dan *RuleID*.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Membuat aturan masking data untuk kolom angka dalam database
```
PS C:\>New-AzSqlDatabaseDataMaskingRule -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01"  -SchemaName "Schema01" -TableName "Table01" -ColumnName "Column01" -MaskingFunction "Number" -NumberFrom 5 -NumberTo 14
```

Perintah ini membuat aturan masking data untuk kolom bernama Column01 dalam tabel bernama Table01 dalam skema bernama Schema01.
Database yang bernama Database01 berisi semua item ini.
Aturan ini adalah aturan masker angka yang menggunakan angka acak antara 5 dan 14 sebagai nilai masker.

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

### -MaskingFungsi
Menentukan fungsi masking yang digunakan aturan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Default
- NoMasking
- Teks
- Nomor
- SocialSecurityNumber
- CreditCardNumber
- Email Nilai defaultnya adalah Default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: NoMasking, Default, Text, Number, SocialSecurityNumber, CreditCardNumber, Email

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberFrom
Menentukan jumlah batas bawah interval tempat nilai acak dipilih.
Tentukan parameter ini hanya jika Anda menentukan nilai Angka untuk parameter *MaskingFunction* .
Nilai defaultnya adalah 0.

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
Menentukan nomor terikat atas interval tempat nilai acak dipilih.
Tentukan parameter ini hanya jika Anda menentukan nilai Angka untuk parameter *MaskingFunction* .
Nilai defaultnya adalah 0.

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
Menentukan jumlah karakter di awal teks yang tidak disematkan.
Tentukan parameter ini hanya jika Anda menentukan nilai Teks untuk parameter *MaskingFunction* .
Nilai defaultnya adalah 0.

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
Menentukan jumlah karakter di akhir teks yang tidak disematkan.
Tentukan parameter ini hanya jika Anda menentukan nilai Teks untuk parameter *MaskingFunction* .
Nilai defaultnya adalah string kosong.

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
Menentukan jumlah karakter di akhir teks yang tidak disematkan.
Tentukan parameter ini hanya jika Anda menentukan nilai Teks untuk parameter *MaskingFunction* .
Nilai defaultnya adalah 0.

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

### System.Nullable'1[[System.UInt32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Double, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.Sql.DataMasking.Model.DatabaseDataMaskingRuleModel

## NOTES

## RELATED LINKS

[Get-AzSqlDatabaseDataMaskingRule](./Get-AzSqlDatabaseDataMaskingRule.md)

[Remove-AzSqlDatabaseDataMaskingRule](./Remove-AzSqlDatabaseDataMaskingRule.md)

[Set-AzSqlDatabaseDataMaskingRule](./Set-AzSqlDatabaseDataMaskingRule.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


