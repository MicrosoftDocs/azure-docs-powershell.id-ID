---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 457FD595-D5E1-45C4-9DB8-C3C6C30A0E94
online version: https://docs.microsoft.com/powershell/module/az.sql/Update-AzSqlDatabaseAdvancedThreatProtectionSetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Update-AzSqlDatabaseAdvancedThreatProtectionSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Update-AzSqlDatabaseAdvancedThreatProtectionSetting.md
ms.openlocfilehash: a5c7b2cc304eccc0d742b43be61e923146f0211b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144216638"
---
# Update-AzSqlDatabaseAdvancedThreatProtectionSetting

## SYNOPSIS
Mengatur pengaturan perlindungan ancaman tingkat lanjut pada database.

## SYNTAX

```
Update-AzSqlDatabaseAdvancedThreatProtectionSetting [-PassThru] [-NotificationRecipientsEmails <String>]
 [-EmailAdmins <Boolean>] [-ExcludedDetectionType <String[]>] [-StorageAccountName <String>]
 [-RetentionInDays <UInt32>] [-ServerName] <String> [-DatabaseName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzSqlDatabaseAdvancedThreatProtectionSetting** menetapkan pengaturan perlindungan ancaman tingkat lanjut pada database Azure SQL.
Untuk menggunakan cmdlet ini, tentukan parameter *ResourceGroupName*, *ServerName* , dan *DatabaseName* untuk mengidentifikasi database.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mengatur pengaturan perlindungan ancaman tingkat lanjut untuk database
```powershell
Update-AzSqlDatabaseAdvancedThreatProtectionSetting -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
```

Perintah ini mengatur pengaturan perlindungan ancaman tingkat lanjut untuk database bernama Database01 di server bernama Server01.

## PARAMETERS

### -DatabaseName
Menentukan nama database tempat pengaturan diatur.

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

### -EmailAdmins
Menentukan apakah pengaturan perlindungan ancaman tingkat lanjut menghubungi administrator dengan menggunakan email. Biarkan kosong untuk menggunakan pengalaman Azure Security Center yang ditingkatkan untuk mengonsumsi pemberitahuan, mengonfigurasi pemberitahuan, dan menangani supresi

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExcludedDetectionType
Menentukan array jenis deteksi yang akan dikecualikan dari pengaturan. Biarkan kosong untuk menggunakan pengalaman Azure Security Center yang ditingkatkan untuk mengonsumsi pemberitahuan, mengonfigurasi pemberitahuan, dan menangani supresi Nilai yang dapat diterima untuk parameter ini adalah:
- Sql_Injection
- Sql_Injection_Vulnerability
- Access_Anomaly
- Tidak ada

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

### -NotificationRecipientsEmails
Menentukan daftar alamat email yang dipisahkan titik koma tempat pengaturan mengirim pemberitahuan. Biarkan kosong untuk menggunakan pengalaman Azure Security Center yang ditingkatkan untuk mengonsumsi pemberitahuan, mengonfigurasi pemberitahuan, dan menangani supresi

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

### -RetentionInDays
Jumlah hari retensi untuk log audit. Biarkan kosong untuk menggunakan pengalaman Azure Security Center yang ditingkatkan untuk mengonsumsi pemberitahuan, mengonfigurasi pemberitahuan, dan menangani supresi.

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
Menentukan nama server.

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

### -StorageAccountName
Menentukan nama akun penyimpanan yang akan digunakan. Kartubebas tidak diizinkan. Parameter ini tidak diperlukan. Ketika parameter ini tidak disediakan, cmdlet akan menggunakan akun penyimpanan yang didefinisikan sebelumnya sebagai bagian dari pengaturan perlindungan ancaman tingkat lanjut dari database. Biarkan kosong untuk menggunakan pengalaman Azure Security Center yang ditingkatkan untuk mengonsumsi pemberitahuan, mengonfigurasi pemberitahuan, dan menangani supresi.

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

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DetectionType[]

### System.Nullable'1[[System.UInt32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DatabaseThreatDetectionsettingsModel

## NOTES

## RELATED LINKS

[cmdlet Azure SQL Database](/powershell/module/az.sql/)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
