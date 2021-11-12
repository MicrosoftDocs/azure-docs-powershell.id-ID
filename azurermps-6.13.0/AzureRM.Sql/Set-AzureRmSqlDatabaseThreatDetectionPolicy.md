---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 457FD595-D5E1-45C4-9DB8-C3C6C30A0E94
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqldatabasethreatdetectionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlDatabaseThreatDetectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlDatabaseThreatDetectionPolicy.md
ms.openlocfilehash: 15b18f193c458b3158e62f4d9017915d52d586ea43e13a7b902162c3ed523264
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418906"
---
# Set-AzureRmSqlDatabaseThreatDetectionPolicy

## SYNOPSIS
Mengatur kebijakan deteksi ancaman pada database.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmSqlDatabaseThreatDetectionPolicy [-PassThru] [-NotificationRecipientsEmails <String>]
 [-EmailAdmins <Boolean>] [-ExcludedDetectionType <DetectionType[]>] [-StorageAccountName <String>]
 [-RetentionInDays <UInt32>] [-ServerName] <String> [-DatabaseName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmSqlDatabaseThreatDetectionPolicy** menetapkan kebijakan deteksi ancaman di database SQL Azure.
Untuk mengaktifkan deteksi ancaman pada database, kebijakan pengauditan harus diaktifkan pada database tersebut.
Untuk menggunakan cmdlet ini, tentukan parameter *ResourceGroupName,* *ServerName,* *dan DatabaseName* untuk mengidentifikasi database.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mengatur kebijakan deteksi ancaman untuk database
```
PS C:\>Set-AzureRmSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability", "SQL_Injection" -StorageAccountName "mystorageAccount"
```

Perintah ini mengatur kebijakan deteksi ancaman untuk database yang bernama Database01 di server yang bernama Server01.

## PARAMETERS

### -DatabaseName
Menentukan nama database di mana kebijakan ditetapkan.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailAdmins
Menentukan apakah kebijakan deteksi ancaman menghubungi administrator dengan menggunakan email.

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
Menentukan array tipe deteksi untuk dikecualikan dari kebijakan tersebut.
Nilai yang dapat diterima untuk parameter ini adalah:
- Sql_Injection 
- Sql_Injection_Vulnerability 
- Access_Anomaly 
- Tidak ada

```yaml
Type: Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DetectionType[]
Parameter Sets: (All)
Aliases:
Accepted values: Sql_Injection, Sql_Injection_Vulnerability, Access_Anomaly, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NotificationRecipientsEmails
Menentukan daftar alamat email yang dipisahkan titik koma tempat kebijakan mengirimkan pemberitahuan.

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
Mengembalikan objek yang mewakili item yang Anda kerjakan.
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
Jumlah hari penyimpanan untuk log audit

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
Menentukan nama akun penyimpanan yang akan digunakan. Wildcard tidak diizinkan. Parameter ini tidak diperlukan. Saat parameter ini tidak disediakan, cmdlet akan menggunakan akun penyimpanan yang sebelumnya ditetapkan sebagai bagian dari kebijakan deteksi ancaman database. Jika ini adalah pertama kalinya kebijakan deteksi ancaman database ditetapkan dan parameter ini tidak disediakan, cmdlet akan gagal.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Nullable'1[[System.Boolean, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### Microsoft.Azure.Commands.sql.ThreatDetection.Model.DetectionType[]

### System.Nullable'1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DatabaseThreatDetectionPolicyModel

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlDatabaseThreatDetectionPolicy](./Get-AzureRmSqlServerThreatDetectionPolicy.md)

[Remove-AzureRmSqlDatabaseThreatDetectionPolicy](./Remove-AzureRmSqlDatabaseThreatDetectionPolicy.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)


