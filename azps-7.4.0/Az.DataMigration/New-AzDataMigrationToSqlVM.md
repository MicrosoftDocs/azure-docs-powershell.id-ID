---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/new-azdatamigrationtosqlvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationToSqlVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationToSqlVM.md
ms.openlocfilehash: b4acd313554cc031525bd357a4abdac016a9aa7a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141998291"
---
# New-AzDataMigrationToSqlVM

## SYNOPSIS
Buat migrasi database baru ke VM SQL tertentu.

## SYNTAX

```
New-AzDataMigrationToSqlVM -ResourceGroupName <String> -SqlVirtualMachineName <String> -TargetDbName <String>
 [-SubscriptionId <String>] [-AzureBlobAccountKey <String>] [-AzureBlobContainerName <String>]
 [-AzureBlobStorageAccountResourceId <String>] [-FileSharePassword <String>] [-FileSharePath <String>]
 [-FileShareUsername <String>] [-Kind <ResourceType>] [-MigrationOperationId <String>]
 [-MigrationService <String>] [-Offline] [-OfflineConfigurationLastBackupName <String>]
 [-ProvisioningError <String>] [-Scope <String>] [-SourceDatabaseName <String>]
 [-SourceSqlConnectionAuthentication <String>] [-SourceSqlConnectionDataSource <String>]
 [-SourceSqlConnectionEncryptConnection] [-SourceSqlConnectionPassword <String>]
 [-SourceSqlConnectionTrustServerCertificate] [-SourceSqlConnectionUserName <String>]
 [-StorageAccountKey <String>] [-StorageAccountResourceId <String>] [-TargetDatabaseCollation <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Buat migrasi database baru ke VM SQL tertentu.

## EXAMPLES

### Contoh 1: Memulai Migrasi Database dari Sumber Sql Server lokal untuk menargetkan Sql VM
```powershell
New-AzDataMigrationToSqlVM -ResourceGroupName "MyResourceGroup" -SqlVirtualMachineName "MyVM" -TargetDbName "MyDb" -Kind "SqlVm" -Scope "/subscriptions/0000-1111-2222-3333-4444/resourceGroups/MyResourceGroup/providers/Microsoft.SqlVirtualMachine/sqlVirtualMachine/MyVM" -MigrationService "/subscriptions/0000-1111-2222-3333-4444/resourceGroups/MyResourceGroup/providers/Microsoft.DataMigration/SqlMigrationServices/MySqlMigrationService" -StorageAccountResourceId "/subscriptions/0000-1111-2222-3333-4444/resourceGroups/MyResourceGroup/providers/Microsoft.Storage/storageAccounts/MyStorageAccount" -StorageAccountKey "aaaaaccccoooouuunnntttkkkeeeyy" -FileSharePath "\\filesharepath.com\SharedBackup\MyBackUps" -FileShareUsername "filesharepath\User" -FileSharePassword "password" -SourceSqlConnectionAuthentication "SqlAuthentication" -SourceSqlConnectionDataSource "LabServer.database.net" -SourceSqlConnectionUserName "User" -SourceSqlConnectionPassword "password" -SourceDatabaseName "AdventureWorks"
```

```output
Name                 Type                                       Kind  ProvisioningState MigrationStatus
----                 ----                                       ----  ----------------- ---------------
MyDb                 Microsoft.DataMigration/databaseMigrations SqlVm Succeeded         InProgress
```

Perintah ini memulai Migrasi Database dari Source Sql Server untuk menargetkan Sql VM.
Contoh ini untuk migrasi online.
Untuk membuatnya offline tambahkan -Offline ke parameter.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -AzureBlobAccountKey
Storage Kunci Akun.

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

### -AzureBlobContainerName
Nama kontainer blob tempat cadangan disimpan.

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

### -AzureBlobStorageAccountResourceId
Id Sumber Daya dari akun penyimpanan tempat cadangan disimpan.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSharePassword
Kata sandi untuk nama pengguna untuk mengakses lokasi berbagi file.

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

### -FileSharePath
Lokasi sebagai berbagi SMB atau drive lokal tempat pencadangan ditempatkan.

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

### -FileShareUsername
Nama pengguna untuk mengakses lokasi berbagi file untuk cadangan.

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

### -Jenis
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Support.ResourceType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationOperationId
ID melacak operasi migrasi saat ini.

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

### -MigrationService
Id Sumber Daya Layanan Migrasi.

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

### -NoWait
Jalankan perintah secara asinkron

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

### -Offline
Migrasi offline

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

### -OfflineConfigurationLastBackupName
Nama cadangan terakhir untuk migrasi offline.
Ini opsional untuk migrasi dari berbagi file.
Jika tidak disediakan, maka layanan akan menentukan nama file cadangan terakhir berdasarkan file cadangan terbaru yang ada dalam berbagi file.

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

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ProvisioningError
Pesan kesalahan untuk kegagalan penyediaan migrasi, jika ada.

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

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.

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

### -Lingkup
Id Sumber Daya sumber daya sumber daya (SQL VM atau SQL Managed Instance)

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

### -SourceDatabaseName
Nama database sumber.

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

### -SourceSqlConnectionAuthentication
Tipe autentikasi.

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

### -SourceSqlConnectionDataSource
Sumber data.

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

### -SourceSqlConnectionEncryptConnection
Apakah akan mengenkripsi koneksi atau tidak.

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

### -SourceSqlConnectionPassword
Kata sandi untuk menyambungkan ke sumber SQL.

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

### -SourceSqlConnectionTrustServerCertificate
Apakah mempercayai sertifikat server atau tidak.

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

### -SourceSqlConnectionUserName
Nama pengguna untuk menyambungkan ke SQL sumber.

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

### -SqlVirtualMachineName
.

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

### -StorageAccountKey
Storage Kunci Akun.

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

### -StorageAccountResourceId
Id Sumber Daya dari akun penyimpanan yang menyalin cadangan.

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

### -SubscriptionId
ID Langganan yang mengidentifikasi langganan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabaseCollation
Kolatasi database yang akan digunakan untuk database target.

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

### -TargetDbName
Nama database target.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IDatabaseMigrationSqlVM

## CATATAN

ALIAS

## RELATED LINKS
