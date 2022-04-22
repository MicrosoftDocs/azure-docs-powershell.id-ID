---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 4FCC7D8B-A46E-4E5B-8BE2-F62B3D3E715D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqlserverauditingpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerAuditingPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerAuditingPolicy.md
ms.openlocfilehash: dd3c54b8e2769e1b7643d154b259b4f47fd51f2a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143045244"
---
# Set-AzureRmSqlServerAuditingPolicy

## SYNOPSIS
Mengubah kebijakan pengauditan server SQL Database.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmSqlServerAuditingPolicy [-AuditType <AuditType>] [-AuditActionGroup <AuditActionGroups[]>]
 [-PassThru] [-EventType <String[]>] [-StorageAccountName <String>] [-StorageKeyType <String>]
 [-RetentionInDays <UInt32>] [-TableIdentifier <String>] -ServerName <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmSqlServerAuditingPolicy** mengubah kebijakan audit server Azure SQL Database.
Tentukan parameter *ResourceGroupName* dan *ServerName* untuk mengidentifikasi server, parameter *StorageAccountName* untuk menentukan akun penyimpanan untuk log audit, dan parameter *StorageKeyType* untuk menentukan kunci penyimpanan yang akan digunakan.
Anda juga bisa menentukan retensi untuk tabel log audit dengan mengatur nilai parameter *RetentionInDays* dan *TableIdentifier* untuk menentukan titik dan seed untuk nama tabel log audit.
Tentukan parameter *EventType* untuk menentukan tipe kejadian mana yang akan diaudit.
Setelah Anda menjalankan cmdlet ini, pengauditan database yang menggunakan kebijakan server ini diaktifkan.
Jika cmdlet berhasil dan Anda menentukan parameter *PassThru* , cmdlet mengembalikan objek yang menjelaskan kebijakan audit saat ini, dan pengidentifikasi server.
Pengidentifikasi server menyertakan **ResourceGroupName** dan **ServerName**.

## EXAMPLES

### Contoh 1: Mengatur kebijakan audit server Azure SQL menggunakan Pengauditan tabel
```
PS C:\>Set-AzureRmSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -AuditType Table -StorageAccountName "Storage22"
```

Perintah ini mengatur kebijakan pengaudungan server bernama Server01 untuk menggunakan akun penyimpanan bernama Storage22.

### Contoh 2: Mengatur kunci akun penyimpanan kebijakan pengauditan server Azure SQL yang sudah ada
```
PS C:\>Set-AzureRmSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountKey Secondary
```

Perintah ini mengatur kebijakan pengaudungan server bernama Server01 untuk menggunakan kunci sekunder.
Perintah tidak mengubah nama akun penyimpanan.

### Contoh 3: Mengatur kebijakan audit server Azure SQL untuk menggunakan tipe kejadian tertentu
```
PS C:\>Set-AzureRmSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -EventType Login_Failure
```

### Contoh 4: Mengatur kebijakan audit database agar menggunakan audit Blob
```
PS C:\>Set-AzureRmSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -AuditType Blob -StorageAccountName "Storage31" -AuditActionGroup "SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP", "FAILED_DATABASE_AUTHENTICATION_GROUP" -RetentionInDays 8
```

Perintah ini mengatur kebijakan pengaudungan server bernama Server01 untuk menggunakan tipe kejadian Login_Failure.
Perintah ini tidak mengubah pengaturan lainnya.

## PARAMETERS

### -AuditActionGroup
Tentukan satu atau beberapa grup tindakan audit. Parameter ini hanya berlaku untuk audit Blob.

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
Tentukan tipe audit. Log audit dapat ditulis ke penyimpanan Tabel atau penyimpanan Blob. Audit blob memberikan kinerja yang lebih tinggi dan mendukung pengauditan tingkat objek.

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
Jika Anda menentukan Semua atau Tidak Ada pada saat yang sama, perintah gagal.

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
Menentukan nama grup sumber daya yang berisi database.

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
ini adalah defaultnya.
Jika menentukan nilai yang lebih besar dari nol, Anda juga harus menentukan nilai untuk parameter *TableIdentifer* .

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
Menentukan nama server yang berisi database.

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
Menentukan nama akun penyimpanan untuk mengaudit database.
Karakter wildcard tidak diizinkan.
Jika Anda tidak menentukan parameter ini, cmdlet menggunakan akun penyimpanan yang ditetapkan sebelumnya sebagai bagian dari kebijakan pengauditan database.
Jika ini pertama kalinya kebijakan audit database ditetapkan dan Anda tidak menentukan parameter ini, perintah gagal.

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

## NOTES

## RELATED LINKS

[Get-AzureRmSqlServerAuditingPolicy](./Get-AzureRmSqlServerAuditingPolicy.md)

[Use-AzureRmSqlServerAuditingPolicy](./Use-AzureRmSqlServerAuditingPolicy.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


