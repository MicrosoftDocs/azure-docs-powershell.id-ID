---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 2B82F5BA-ABC6-4B37-B641-353CFE814290
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqlserverthreatdetectionpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerThreatDetectionPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerThreatDetectionPolicy.md
ms.openlocfilehash: f7b970693fff43515ce8a0291c6a1e62165aaf3f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142314514"
---
# Set-AzureRmSqlServerThreatDetectionPolicy

## SYNOPSIS
Mengatur kebijakan deteksi ancaman pada server.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmSqlServerThreatDetectionPolicy [-PassThru] [-NotificationRecipientsEmails <String>]
 [-EmailAdmins <Boolean>] [-ExcludedDetectionType <DetectionType[]>] [-StorageAccountName <String>]
 [-RetentionInDays <UInt32>] -ServerName <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmSqlServerThreatDetectionPolicy** menetapkan kebijakan deteksi ancaman di server Azure SQL.
Untuk mengaktifkan deteksi ancaman pada server, kebijakan audit harus diaktifkan pada server tersebut.
Untuk menggunakan cmdlet ini, tentukan parameter *ResourceGroupName* dan ServerName untuk mengidentifikasi server.

## EXAMPLES

### Contoh 1: Mengatur kebijakan deteksi ancaman untuk database
```
PS C:\>Set-AzureRmSqlServerThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -NotificationRecipientsEmails "admin01@contoso.com;secadmin@contoso.com" -EmailAdmins $False -ExcludedDetectionType "Sql_Injection_Vulnerability","SQL_Injection" -StorageAccountName "mystorageAccount"
```

Perintah ini mengatur kebijakan deteksi ancaman untuk server bernama Server01.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Menentukan array tipe deteksi untuk dikecualikan dari kebijakan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Sql_Injection
- Sql_Injection_Vulnerability
- Access_Anomaly
- Tidak

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
Menentukan daftar alamat email yang dipisahkan titik koma tempat kebijakan mengirim pemberitahuan.

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
Menentukan nama grup sumber daya tempat server berada.

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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama akun penyimpanan yang akan digunakan. Wildcard tidak diizinkan. Parameter ini tidak diperlukan. Ketika parameter ini tidak disediakan, cmdlet akan menggunakan akun penyimpanan yang ditetapkan sebelumnya sebagai bagian dari kebijakan deteksi ancaman database. Jika ini pertama kalinya kebijakan deteksi database theat ditentukan dan parameter ini tidak disediakan, cmdlet akan gagal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Boolean, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DetectionType[]

### System.Nullable'1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ThreatDetection.Model.ServerThreatDetectionPolicyModel

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlServerThreatDetectionPolicy](./Get-AzureRmSqlServerThreatDetectionPolicy.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
