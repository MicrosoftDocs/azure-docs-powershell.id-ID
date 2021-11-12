---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 82F4DB8F-8DAF-40D2-8031-3EDBF5D08417
online version: ''
schema: 2.0.0
ms.openlocfilehash: be5852c06ffbb38517aacce5a70d9ea3e8cf1d52
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419899"
---
# Set-AzureSqlDatabase

## SYNOPSIS
Mengatur properti untuk Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByNameWithConnectionContext
```
Set-AzureSqlDatabase -ConnectionContext <IServerDataServiceContext> -DatabaseName <String>
 [-NewDatabaseName <String>] [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByObjectWithConnectionContext
```
Set-AzureSqlDatabase -ConnectionContext <IServerDataServiceContext> -Database <Database>
 [-NewDatabaseName <String>] [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByNameWithServerName
```
Set-AzureSqlDatabase -ServerName <String> -DatabaseName <String> [-NewDatabaseName <String>]
 [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByObjectWithServerName
```
Set-AzureSqlDatabase -ServerName <String> -Database <Database> [-NewDatabaseName <String>]
 [-Edition <DatabaseEdition>] [-MaxSizeGB <Int32>] [-MaxSizeBytes <Int64>]
 [-ServiceObjective <ServiceObjective>] [-PassThru] [-Force] [-Sync] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureSqlDatabase** menetapkan properti untuk Azure SQL Database.
Anda dapat menentukan database berdasarkan nama, atau melewati Azure SQL Database melalui saluran.
Anda dapat menentukan server berdasarkan nama, atau menyampaikan Azure SQL Database koneksi server.
Buat konteks koneksi dengan menjalankan cmdlet **New-AzureSqlDatabaseServerContext.**
Jika Anda menentukan server berdasarkan nama, cmdlet menggunakan informasi langganan Azure saat ini untuk mengautentikasi permintaan.

## EXAMPLES

### Contoh 1: Mengubah ukuran database menggunakan konteks koneksi
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
PS C:\> Set-AzureSqlDatabase -ConnectionContext $Context -Database $Database01 -MaxSizeGB 20
```

Contoh ini mengubah ukuran database bernama Database01 menjadi 20 GB, dalam Azure SQL Database koneksi server $Context.

### Contoh 2: Mengubah ukuran database menggunakan nama server
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
PS C:\> Set-AzureSqlDatabase -ServerName "lpqd0zbr8y" -Database $Database01 -MaxSizeGB 20
```

Contoh ini mengubah ukuran database yang bernama Database01 menjadi 20 GB dalam server yang bernama lpqd0zbr8y.

## PARAMETERS

### -ConnectionContext
Menentukan konteks koneksi server.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByNameWithConnectionContext, ByObjectWithConnectionContext
Aliases: Context

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Database
Menentukan objek yang mewakili Azure SQL Database yang ditentukan cmdlet ini.

```yaml
Type: Database
Parameter Sets: ByObjectWithConnectionContext, ByObjectWithServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database yang akan dimodifikasi cmdlet ini.

```yaml
Type: String
Parameter Sets: ByNameWithConnectionContext, ByNameWithServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Edition
Menentukan edisi baru untuk edisi Azure SQL Database.
Nilai valid adalah: 

- Tidak ada
- Web
- Bisnis
- Dasar
- Standar
-  Premium

```yaml
Type: DatabaseEdition
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memungkinkan tindakan untuk diselesaikan tanpa meminta konfirmasi kepada Anda.

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

### -MaxSizeBytes
Menentukan ukuran maksimum baru untuk database dalam byte.
Anda dapat menentukan parameter ini atau parameter *MaxSizeGB.*
Lihat parameter *MaxSizeGB* untuk nilai yang dapat diterima berdasarkan edisi.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSizeGB
Menentukan ukuran maksimum baru untuk database dalam gigabyte.
Anda bisa menentukan parameter ini atau parameter *MaxSizeBytes.*
Nilai yang dapat diterima berbeda-beda berdasarkan edisi.

Nilai Edisi Dasar: 1 atau 2

Nilai Edisi Standar: 1, 2, 5, 10, 20, 30, 40, 50, 100, 150, 200, atau 250

nilai edisi Premium: 1, 2, 5, 10, 20, 30, 40, 50, 100, 150, 200, 250, 300, 400, atau 500

Nilai Edisi Web: 1 atau 5

Nilai Edisi Bisnis: 10, 20, 30, 40, 50, 100, atau 150

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDatabaseName
Menentukan nama baru database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan nilai yang Azure SQL Database.

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

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server yang berisi database yang akan dimodifikasi cmdlet ini.

```yaml
Type: String
Parameter Sets: ByNameWithServerName, ByObjectWithServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceObjective
Menentukan objek yang mewakili tujuan layanan baru (tingkat kinerja) untuk database ini.
Nilai valid adalah: 

- Dasar: dd6d99bb-f193-4ec1-86f2-43d3bccbc49c
- Standar (S0): f1173c43-91bd-4aaa-973c-54e79e15235b
- Standar (S1): 1b1ebd4d-d903-4baa-97f9-4ea675f5e928
- Standar (S2): 455330e1-00cd-488b-b5fa-177c226f28b7
- *Standard (S3): 789681b8-ca10-4eb0-bdf2-e0b050601b40
- Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
- Premium (P2): a7d1b92d-c987-4375-b54d-2b1d0e0f5bb0
- Premium (P3): a7c4c615-cfb1-464b-b252-925be0a19446

*Standar (S3) adalah bagian dari Pembaruan SQL Database V12 (pratinjau).
Untuk informasi selengkapnya, lihat Apa yang Baru dalam Azure SQL Database V12 Pratinjau https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/ .

```yaml
Type: ServiceObjective
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sync
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database SQL Azure](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Perbarui Database](https://msdn.microsoft.com/en-us/library/azure/dn505718.aspx)

[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)

[New-AzureSqlDatabase](./New-AzureSqlDatabase.md)

[Remove-AzureSqlDatabase](./Remove-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


