---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: A1327BC6-F090-490E-8DC2-2CC48A21C2C0
online version: https://docs.microsoft.com/powershell/module/az.sql/new-azsqldatabaseimport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlDatabaseImport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlDatabaseImport.md
ms.openlocfilehash: 2c1ce82fc033b3faff3afd34e8315dc31e92c0fd
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144593632"
---
# New-AzSqlDatabaseImport

## SYNOPSIS
Mengimpor file .bacpac dan membuat database baru di server.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/new-azsqldatabaseimport) untuk informasi terbaru.

## SYNTAX

```
New-AzSqlDatabaseImport -DatabaseName <String> -Edition <DatabaseEdition> -ServiceObjectiveName <String>
 -DatabaseMaxSizeBytes <Int64> [-ServerName] <String> -StorageKeyType <StorageKeyType> -StorageKey <String>
 -StorageUri <Uri> -AdministratorLogin <String> -AdministratorLoginPassword <SecureString>
 [-AuthenticationType <AuthenticationType>] [-UseNetworkIsolation <Boolean>]
 [-StorageAccountResourceIdForPrivateLink <String>] [-SqlServerResourceIdForPrivateLink <String>]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSqlDatabaseImport** mengimpor file bacpac dari akun penyimpanan Azure ke Azure SQL Database baru.
Permintaan dapatkan status database impor dapat dikirim untuk mengambil informasi status untuk permintaan ini.

## EXAMPLES

### Contoh 1: Membuat permintaan impor untuk file bacpac
```powershell
New-AzSqlDatabaseImport -ResourceGroupName "RG01" -ServerName "Server01" -DatabaseName "Database01" -StorageKeyType "StorageAccessKey" -StorageKey "StorageKey01" -StorageUri "http://account01.blob.core.contoso.net/bacpacs/database01.bacpac" -AdministratorLogin "User" -AdministratorLoginPassword $SecureString -Edition Standard -ServiceObjectiveName S0 -DatabaseMaxSizeBytes 5000000
```

```output
ResourceGroupName          : RG01
ServerName                 : Server01
DatabaseName               : Database01
StorageKeyType             : StorageAccessKey
StorageKey                 : 
StorageUri                 : http://account01.blob.core.contoso.net/bacpacs/database01.bacpac
AdministratorLogin         : User
AdministratorLoginPassword : 
AuthenticationType         : None
OperationStatusLink        : https://management.contoso.com/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resource01/providers/Microsoft.Sql/servers/server01/databases/database01/importExportOperationResults/00000000-00
                             0-0000-0000-000000000000?api-version=2014-04-01
Status                     : InProgress
ErrorMessage               :
```

Perintah ini membuat permintaan impor untuk mengimpor .bacpac ke database baru.

### Contoh 2

Mengimpor file .bacpac dan membuat database baru di server. (dibuat otomatis)

<!-- Aladdin Generated Example -->

```powershell
New-AzSqlDatabaseImport -AdministratorLogin 'User' -AdministratorLoginPassword <SecureString> -AuthenticationType None -DatabaseMaxSizeBytes 5000000 -DatabaseName 'Database01' -Edition None -ResourceGroupName 'RG01' -ServerName 'Server01' -ServiceObjectiveName S0 -StorageKey 'StorageKey01' -StorageKeyType StorageAccessKey -StorageUri 'https://account01.blob.core.contoso.net/bacpacs/database01.bacpac'
```

## PARAMETERS

### -AdministratorLogin
Menentukan nama administrator SQL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdministratorLoginPassword
Menentukan kata sandi administrator SQL.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationType
Menentukan jenis autentikasi yang digunakan untuk mengakses server.
Parameter ini default ke SQL jika tidak ada jenis autentikasi yang diatur.
Nilai yang dapat diterima untuk parameter ini adalah:
- SQL.
SQL autentikasi.
Atur parameter *AdministratorLogin* dan *AdministratorLoginPassword* ke nama pengguna dan kata sandi administrator SQL. 
- Kata Sandi AD.
Autentikasi Azure Active Directory.
Atur *AdministratorLogin* dan *AdministratorLoginPassword* ke nama pengguna dan kata sandi administrator Azure Active Directory.
Parameter ini hanya tersedia di server SQL Database V12.

```yaml
Type: Microsoft.Azure.Commands.Sql.ImportExport.Model.AuthenticationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Sql, AdPassword

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseMaxSizeBytes
Menentukan ukuran maksimum untuk database yang baru diimpor.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama SQL Database.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -Edisi
Menentukan edisi database baru yang akan diimpor.
Nilai yang dapat diterima untuk parameter ini adalah:
- Premium
- Dasar
- Standard
- Gudang Data
- Gratis

```yaml
Type: Microsoft.Azure.Commands.Sql.Database.Model.DatabaseEdition
Parameter Sets: (All)
Aliases:
Accepted values: None, Premium, Basic, Standard, DataWarehouse, Stretch, Free, PremiumRS, GeneralPurpose, BusinessCritical, Hyperscale

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk server SQL Database.

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
Menentukan nama server SQL Database.

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

### -ServiceObjectiveName
Menentukan nama tujuan layanan untuk ditetapkan ke Azure SQL Database.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlServerResourceIdForPrivateLink
Id sumber daya server sql untuk membuat tautan privat

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountResourceIdForPrivateLink
Id sumber daya akun penyimpanan untuk membuat tautan privat

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageKey
Menentukan kunci akses untuk akun penyimpanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageKeyType
Menentukan jenis kunci akses untuk akun penyimpanan.
Nilai yang dapat diterima untuk parameter ini adalah:
- StorageAccessKey.
Menggunakan kunci akun penyimpanan. 
- SharedAccessKey.
Menggunakan kunci Tanda Tangan Akses Bersama (SAS).

```yaml
Type: Microsoft.Azure.Commands.Sql.ImportExport.Model.StorageKeyType
Parameter Sets: (All)
Aliases:
Accepted values: StorageAccessKey, SharedAccessKey

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageUri
Menentukan URI blob dari file .bacpac.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseNetworkIsolation
Jika diatur, akan membuat tautan privat untuk akun penyimpanan dan/atau server SQL

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Azure.Commands.Sql.ImportExport.Model.AzureSqlDatabaseImportExportBaseModel

## NOTES
* Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, sql, database, mssql

## RELATED LINKS

[Get-AzSqlDatabaseImportExportStatus](./Get-AzSqlDatabaseImportExportStatus.md)

[New-AzSqlDatabaseExport](./New-AzSqlDatabaseExport.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)

