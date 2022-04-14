---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: F7EF35E3-BC53-43D9-A71E-0B4316260A08
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqldatabaseauditingpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlDatabaseAuditingPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlDatabaseAuditingPolicy.md
ms.openlocfilehash: a9f0f2e478e94b45349efe85c6de643b5003a361
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141774040"
---
# Set-AzureRmSqlDatabaseAuditingPolicy

## SYNOPSIS
Mengatur kebijakan pengauditan untuk database.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmSqlDatabaseAuditingPolicy [-AuditType <AuditType>] [-PassThru]
 [-AuditActionGroup <AuditActionGroups[]>] [-AuditAction <String[]>] [-EventType <String[]>]
 [-StorageAccountName <String>] [-StorageKeyType <String>] [-RetentionInDays <UInt32>]
 [-TableIdentifier <String>] [-ServerName] <String> [-DatabaseName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmSqlDatabaseAuditingPolicy** mengubah kebijakan pengauditan database Azure SQL.
Untuk menggunakan cmdlet, gunakan parameter *ResourceGroupName*, *ServerName*, dan *DatabaseName* untuk mengidentifikasi database.
Tentukan parameter *StorageAccountName* untuk menentukan akun penyimpanan untuk log audit dan parameter *StorageKeyType* untuk menentukan kunci penyimpanan.
Anda juga bisa menentukan retensi untuk tabel log audit dengan mengatur nilai parameter *RetentionInDays* dan *TableIdentifier* untuk menentukan titik dan seed untuk nama tabel log audit.
Tentukan parameter *EventType* untuk menentukan tipe kejadian mana yang akan diaudit.
Setelah cmdlet berjalan dengan sukses, pengauditan database diaktifkan.
Untuk Pengaudungan Tabel, jika database menggunakan kebijakan servernya untuk diaudit sebelum Anda menjalankan cmdlet ini, pengauditan berhenti menggunakan kebijakan tersebut. Untuk Audit Blob, jika database menggunakan kebijakan servernya untuk diaudit sebelum Anda menjalankan cmdlet ini, kedua kebijakan pengauditan akan ada secara berdampingan.
Jika cmdlet berhasil dan Anda menggunakan parameter *PassThru* , cmdlet mengembalikan objek yang menjelaskan kebijakan audit saat ini selain pengidentifikasi database.
Pengidentifikasi database menyertakan, tetapi tidak terbatas pada, **ResourceGroupName**, **ServerName**, dan **DatabaseName**.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mengatur kebijakan audit database untuk menggunakan Pengauditan tabel
```
PS C:\>Set-AzureRmSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -AuditType Table -StorageAccountName "Storage31"
```

Perintah ini mengatur kebijakan audit database bernama Database01 yang terletak di Server01 untuk menggunakan akun penyimpanan bernama Storage31.

### Contoh 2: Mengatur kunci akun penyimpanan dari kebijakan pengauditan database yang sudah ada
```
PS C:\>Set-AzureRmSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -StorageAccountKey Secondary
```

Perintah ini mengatur kebijakan pengaudungan database bernama Database01 yang terletak di Server01 agar tetap menggunakan nama akun penyimpanan yang sama tetapi sekarang menggunakan kunci sekunder.

### Contoh 3: Mengatur kebijakan audit database untuk menggunakan tipe kejadian tertentu
```
PS C:\>Set-AzureRmSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -EventType Login_Failure
```

### Contoh 4: Mengatur kebijakan audit database agar menggunakan audit Blob
```
PS C:\>Set-AzureRmSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -AuditType Blob -StorageAccountName "Storage31" -AuditActionGroup "SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP", "FAILED_DATABASE_AUTHENTICATION_GROUP" -AuditAction "UPDATE ON database::[Database01] BY [public]"  -RetentionInDays 8
```

Perintah ini mengatur kebijakan pengaudungan database bernama Database01 yang terletak di Server01.
Kebijakan mencatat tipe kejadian Login_Failure.
Perintah tidak mengubah pengaturan penyimpanan.

## PARAMETERS

### -AuditAction
Tentukan satu atau beberapa tindakan audit.
Parameter ini hanya berlaku untuk audit Blob.

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

### -AuditActionGroup
Tentukan satu atau beberapa grup tindakan audit.
Parameter ini hanya berlaku untuk audit Blob.

```yaml
Type: Microsoft.Azure.Commands.Sql.Auditing.Model.AuditActionGroups[]
Parameter Sets: (All)
Aliases:
Accepted values: BATCH_STARTED_GROUP, BATCH_COMPLETED_GROUP, APPLICATION_ROLE_CHANGE_PASSWORD_GROUP, BACKUP_RESTORE_GROUP, DATABASE_LOGOUT_GROUP, DATABASE_OBJECT_CHANGE_GROUP, DATABASE_OBJECT_OWNERSHIP_CHANGE_GROUP, DATABASE_OBJECT_PERMISSION_CHANGE_GROUP, DATABASE_OPERATION_GROUP, AUDIT_CHANGE_GROUP, DATABASE_PERMISSION_CHANGE_GROUP, DATABASE_PRINCIPAL_CHANGE_GROUP, DATABASE_PRINCIPAL_IMPERSONATION_GROUP, DATABASE_ROLE_MEMBER_CHANGE_GROUP, FAILED_DATABASE_AUTHENTICATION_GROUP, SCHEMA_OBJECT_ACCESS_GROUP, SCHEMA_OBJECT_CHANGE_GROUP, SCHEMA_OBJECT_OWNERSHIP_CHANGE_GROUP, SCHEMA_OBJECT_PERMISSION_CHANGE_GROUP, SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP, USER_CHANGE_PASSWORD_GROUP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuditType
```yaml
Type: Microsoft.Azure.Commands.Sql.Auditing.Model.AuditType
Parameter Sets: (All)
Aliases:
Accepted values: NotSet, Table, Blob

Required: False
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventType
Menentukan tipe kejadian untuk diaudit.
Parameter ini hanya berlaku untuk pengauditan Tabel.
Anda dapat menentukan beberapa tipe acara.
Anda bisa menentukan Semua untuk mengaudit semua tipe kejadian atau Tidak Ada untuk menentukan bahwa tidak ada kejadian yang akan diaudit.
Jika Anda menentukan Semua atau Tidak Ada pada saat yang sama, cmdlet tidak berjalan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: PlainSQL_Success, PlainSQL_Failure, ParameterizedSQL_Success, ParameterizedSQL_Failure, StoredProcedure_Success, StoredProcedure_Failure, Login_Success, Login_Failure, TransactionManagement_Success, TransactionManagement_Failure, All, None

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

### -RetentionInDays
Menentukan jumlah hari penyimpanan untuk tabel log audit.
Nilai nol (0) berarti bahwa tabel tidak dipertahankan.
Nilai defaultnya adalah nol.
Jika menentukan nilai yang lebih besar dari nol, Anda harus menentukan nilai untuk parameter *TableIdentifer* .

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

### -StorageAccountName
Menentukan nama akun penyimpanan untuk mengaudit database.
Karakter wildcard tidak diizinkan.
Parameter ini tidak diperlukan.
Jika Anda tidak menentukan parameter ini, cmdlet menggunakan akun penyimpanan yang ditetapkan sebelumnya sebagai bagian dari kebijakan pengauditan database.
Jika ini pertama kalinya kebijakan audit database ditetapkan dan Anda tidak menentukan parameter ini, cmdlet gagal.

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

### -StorageKeyType
Menentukan kunci akses penyimpanan mana yang akan digunakan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Utama
- Sekunder Nilai defaultnya adalah Utama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Primary, Secondary

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TableIdentifier
Menentukan nama tabel log audit.
Tentukan nilai ini jika Anda menentukan nilai yang lebih besar dari nol untuk parameter *RetentionInDays* .

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

### Microsoft.Azure.Commands.Sql.Auditing.Model.AuditType

### Microsoft.Azure.Commands.Sql.Auditing.Model.AuditActionGroups[]

### System.String[]

### System.String

### System.Nullable'1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Auditing.Model.AuditingPolicyModel

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlDatabaseAuditingPolicy](./Get-AzureRmSqlDatabaseAuditingPolicy.md)

[Hapus-AzureRmSqlDatabaseAuditing](./Remove-AzureRmSqlDatabaseAuditing.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


