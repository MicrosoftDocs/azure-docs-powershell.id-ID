---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 4FCC7D8B-A46E-4E5B-8BE2-F62B3D3E715D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqlserverauditingpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerAuditingPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerAuditingPolicy.md
ms.openlocfilehash: ee54928b1f32c726bc2847eace77e6ccbe48c4d8
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425194"
---
# Set-AzureRmSqlServerAuditingPolicy

## SYNOPSIS
Changes the auditing policy of a SQL Database server.

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
Tentukan parameter *ResourceGroupName* dan *ServerName* untuk mengidentifikasi server, parameter *StorageAccountName* guna menentukan akun penyimpanan untuk log audit, dan parameter *StorageKeyType* untuk menentukan kunci penyimpanan yang akan digunakan.

Anda juga dapat menentukan penyimpanan untuk tabel log audit dengan mengatur nilai parameter *RetentionInDays* dan *TableIdentifier* untuk menentukan periode dan nilai awal untuk nama tabel log audit.
Tentukan parameter *EventType* untuk menentukan tipe kejadian mana yang akan diaudit.
Setelah Anda menjalankan cmdlet ini, pengauditan database yang menggunakan kebijakan server ini diaktifkan.
Jika cmdlet berhasil dan Anda menentukan parameter *PassThru,* cmdlet akan mengembalikan objek yang menguraikan kebijakan audit saat ini, dan pengidentifikasi server.
Pengidentifikasi server menyertakan **ResourceGroupName** dan **ServerName.**

## EXAMPLES

### Contoh 1: Mengatur kebijakan pengauditan kebijakan server Azure SQL pengauditan Tabel
```
PS C:\>Set-AzureRmSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -AuditType Table -StorageAccountName "Storage22"
```

Perintah ini mengatur kebijakan pengauditan server bernama Server01 agar menggunakan akun penyimpanan yang bernama Storage22.

### Contoh 2: Mengatur kunci akun penyimpanan dari kebijakan audit yang sudah ada dari server SQL Azure
```
PS C:\>Set-AzureRmSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -StorageAccountKey Secondary
```

Perintah ini mengatur kebijakan pengauditan server yang bernama Server01 agar menggunakan kunci sekunder.
Perintah tidak mengubah nama akun penyimpanan.

### Contoh 3: Mengatur kebijakan pengauditan server Azure SQL untuk menggunakan tipe kejadian tertentu
```
PS C:\>Set-AzureRmSqlServerAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -EventType Login_Failure
```

### Contoh 4: Mengatur kebijakan audit database untuk menggunakan pengauditan Blob
```
PS C:\>Set-AzureRmSqlDatabaseAuditingPolicy -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -AuditType Blob -StorageAccountName "Storage31" -AuditActionGroup "SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP", "FAILED_DATABASE_AUTHENTICATION_GROUP" -RetentionInDays 8
```

Perintah ini mengatur kebijakan pengauditan server bernama Server01 agar menggunakan tipe Login_Failure kejadian.
Perintah ini tidak memodifikasi pengaturan lainnya.

## PARAMETERS

### -AuditActionGroup
Tentukan satu atau beberapa grup tindakan audit. Parameter ini hanya berlaku untuk pengauditan Blob.

```yaml
Type: AuditActionGroups[]
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
Tentukan tipe audit. Log audit dapat ditulis ke penyimpanan Tabel atau penyimpanan Blob. Pengauditan Blob menyediakan kinerja yang lebih tinggi dan mendukung pengauditan tingkat objek.

```yaml
Type: AuditType
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventType
Menentukan tipe kejadian yang akan diaudit.
Parameter ini hanya berlaku untuk Pengauditan Tabel.

Anda dapat menentukan beberapa tipe kejadian.
You can specify All to audit all of the event types or None to specify that no events will be audited.
Jika Anda menentukan Semua atau Tidak Ada pada saat yang sama, perintah akan gagal.

```yaml
Type: String[]
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
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

```yaml
Type: SwitchParameter
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
Type: String
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
ini adalah pengaturan default.
Jika Anda menentukan nilai yang lebih besar dari nol, Anda juga harus menentukan nilai untuk parameter *TableIdentifer.*

```yaml
Type: UInt32
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
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama akun penyimpanan untuk pengauditan database.
Karakter wildcard tidak diizinkan.
Jika Anda tidak menentukan parameter ini, cmdlet menggunakan akun penyimpanan yang sebelumnya ditetapkan sebagai bagian dari kebijakan audit database.
Jika ini adalah kali pertama kebijakan pengauditan database ditentukan dan Anda tidak menentukan parameter ini, perintah akan gagal.

```yaml
Type: String
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
- Sekunder

Nilai defaultnya adalah Utama.

```yaml
Type: String
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
Tentukan nilai ini jika Anda menentukan nilai yang lebih besar dari nol untuk parameter *RetentionInDays.*

```yaml
Type: String
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
Type: SwitchParameter
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
Type: SwitchParameter
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

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Security.Model.ServerAuditingPolicyModel

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlServerAuditingPolicy](./Get-AzureRmSqlServerAuditingPolicy.md)

[Use-AzureRmSqlServerAuditingPolicy](./Use-AzureRmSqlServerAuditingPolicy.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)


