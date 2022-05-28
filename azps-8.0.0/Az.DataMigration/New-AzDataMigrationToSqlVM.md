---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/new-azdatamigrationtosqlvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationToSqlVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationToSqlVM.md
ms.openlocfilehash: a97120346e997d221e48ba5018f7db651c48b1ae
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145621219"
---
# New-AzDataMigrationToSqlVM

## SYNOPSIS
Buat migrasi database baru ke VM SQL tertentu.

## SYNTAX

```
New-AzDataMigrationToSqlVM -ResourceGroupName <String> -SqlVirtualMachineName <String> -TargetDbName <String>
 [-SubscriptionId <String>] [-AzureBlobAccountKey <String>] [-AzureBlobContainerName <String>]
 [-AzureBlobStorageAccountResourceId <String>] [-FileSharePassword <SecureString>] [-FileSharePath <String>]
 [-FileShareUsername <String>] [-Kind <ResourceType>] [-MigrationService <String>] [-Offline]
 [-OfflineConfigurationLastBackupName <String>] [-Scope <String>] [-SourceDatabaseName <String>]
 [-SourceSqlConnectionAuthentication <String>] [-SourceSqlConnectionDataSource <String>]
 [-SourceSqlConnectionEncryptConnection] [-SourceSqlConnectionPassword <SecureString>]
 [-SourceSqlConnectionTrustServerCertificate] [-SourceSqlConnectionUserName <String>]
 [-StorageAccountKey <String>] [-StorageAccountResourceId <String>] [-TargetDatabaseCollation <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Buat migrasi database baru ke VM SQL tertentu.

## EXAMPLES

### Contoh 1: Memulai Migrasi Database dari Sql Server Sumber lokal untuk menargetkan Sql VM
```powershell
$sourcePassword = ConvertTo-SecureString "pass123" -AsPlainText -Force
$filesharePassword = ConvertTo-SecureString "pass123" -AsPlainText -Force

New-AzDataMigrationToSqlVM -ResourceGroupName "MyResourceGroup" -SqlVirtualMachineName "MyVM" -TargetDbName "MyDb" -Kind "SqlVm" -Scope "/subscriptions/0000-1111-2222-3333-4444/resourceGroups/MyResourceGroup/providers/Microsoft.SqlVirtualMachine/sqlVirtualMachine/MyVM" -MigrationService "/subscriptions/0000-1111-2222-3333-4444/resourceGroups/MyResourceGroup/providers/Microsoft.DataMigration/SqlMigrationServices/MySqlMigrationService" -StorageAccountResourceId "/subscriptions/0000-1111-2222-3333-4444/resourceGroups/MyResourceGroup/providers/Microsoft.Storage/storageAccounts/MyStorageAccount" -StorageAccountKey "aaaaaccccoooouuunnntttkkkeeeyy" -FileSharePath "\\filesharepath.com\SharedBackup\MyBackUps" -FileShareUsername "filesharepath\User" -FileSharePassword $filesharePassword -SourceSqlConnectionAuthentication "SqlAuthentication" -SourceSqlConnectionDataSource "LabServer.database.net" -SourceSqlConnectionUserName "User" -SourceSqlConnectionPassword $sourcePassword -SourceDatabaseName "AdventureWorks"
```

```output
Name                 Type                                       Kind  ProvisioningState MigrationStatus
----                 ----                                       ----  ----------------- ---------------
MyDb                 Microsoft.DataMigration/databaseMigrations SqlVm Succeeded         InProgress
```

Perintah ini memulai Migrasi Database dari Sql Server Sumber untuk menargetkan Sql VM.
Contoh ini untuk migrasi online.
Untuk membuatnya offline, tambahkan -Offline ke parameter.

Catatan : Buat migrasi database baru ke VM SQL tertentu.
Catatan - Untuk parameter Cakupan, gunakan Cakupan VM SQL (/subscriptions/111-222/resourceGroups/myRG/providers/Microsoft.SqlVirtualMachine/SqlVirtualMachines/xyz-SqlVM) dan bukan VM Compute SQL (/subscriptions/111-222/resourceGroups/myRG/providers/Microsoft.Compute/virtualMachines/xyz-SqlVM)

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Id Sumber Daya akun penyimpanan tempat cadangan disimpan.

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
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSharePath
Lokasi sebagai berbagi SMB atau drive lokal tempat cadangan ditempatkan.

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

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

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

### -Cakupan
Id sumber daya sumber daya target (SQL VM).
Untuk parameter Cakupan, gunakan Cakupan VM SQL (/subscriptions/111-222/resourceGroups/myRG/providers/Microsoft.SqlVirtualMachine/SqlVirtualMachines/xyz-SqlVM) dan bukan VM Compute SQL (/subscriptions/111-222/resourceGroups/myRG/providers/Microsoft.Compute/virtualMachines/xyz-SqlVM)

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
Jenis autentikasi.

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
Kata sandi untuk menyambungkan ke SQL sumber.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceSqlConnectionTrustServerCertificate
Apakah akan mempercayai sertifikat server atau tidak.

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
ID langganan yang mengidentifikasi langganan Azure.

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
Kolase database yang akan digunakan untuk database target.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20220330Preview.IDatabaseMigrationSqlVM

## NOTES

ALIAS

## RELATED LINKS
