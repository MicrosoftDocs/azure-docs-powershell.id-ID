---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 82F4DB8F-8DAF-40D2-8031-3EDBF5D08417
online version: ''
schema: 2.0.0
ms.openlocfilehash: be5852c06ffbb38517aacce5a70d9ea3e8cf1d52
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143041697"
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
Cmdlet **Set-AzureSqlDatabase** mengatur properti untuk Azure SQL Database.
Anda bisa menentukan database menurut nama, atau melewati objek Azure SQL Database melalui pipeline.
Anda bisa menentukan server menurut nama, atau melewati konteks koneksi server Azure SQL Database.
Buat konteks koneksi dengan menjalankan cmdlet **New-AzureSqlDatabaseServerContext** .
Jika Anda menentukan server berdasarkan nama, cmdlet menggunakan informasi langganan Azure saat ini untuk mengautentikasi permintaan.

## EXAMPLES

### Contoh 1: Mengubah ukuran database menggunakan konteks koneksi
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
PS C:\> Set-AzureSqlDatabase -ConnectionContext $Context -Database $Database01 -MaxSizeGB 20
```

Contoh ini mengubah ukuran database bernama Database01 menjadi 20 GB, dalam konteks koneksi server Azure SQL Database $Context.

### Contoh 2: Mengubah ukuran database menggunakan nama server
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
PS C:\> Set-AzureSqlDatabase -ServerName "lpqd0zbr8y" -Database $Database01 -MaxSizeGB 20
```

Contoh ini mengubah ukuran database bernama Database01 menjadi 20 GB di server bernama lpqd0zbr8y.

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
Menentukan objek yang mewakili Azure SQL Database yang diubah cmdlet ini.

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
Menentukan nama database yang diubah cmdlet ini.

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

### -Edisi
Menentukan edisi baru untuk Azure SQL Database.
Nilai yang valid adalah: 

- Tidak
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

### -Paksa
Memperbolehkan tindakan selesai tanpa meminta konfirmasi kepada Anda.

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
Anda dapat menentukan parameter ini atau parameter *MaxSizeGB* .
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
Anda dapat menentukan parameter ini atau parameter *MaxSizeBytes* .
Nilai yang dapat diterima berbeda berdasarkan edisi.

Nilai Edisi Dasar: 1 atau 2

Nilai Edisi Standar: 1, 2, 5, 10, 20, 30, 40, 50, 100, 150, 200, atau 250

nilai Premium Edition: 1, 2, 5, 10, 20, 30, 40, 50, 100, 150, 200, 250, 300, 400, atau 500

Nilai Web Edition: 1 atau 5

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
Mengembalikan Azure SQL Database yang diperbarui.

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Menentukan nama server yang berisi database yang diubah cmdlet ini.

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
Nilai yang valid adalah: 

- Dasar: dd6d99bb-f193-4ec1-86f2-43d3bccbc49c
- Standar (S0): f1173c43-91bd-4aaa-973c-54e79e15235b
- Standar (S1): 1b1ebd4d-d903-4baa-97f9-4ea675f5e928
- Standar (S2): 455330e1-00cd-488b-b5fa-177c226f28b7
- *Standar (S3): 789681b8-ca10-4eb0-bdf2-e0b050601b40
- Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
- Premium (P2): a7d1b92d-c987-4375-b54d-2b1d0e0f5bb0
- Premium (P3): a7c4c615-cfb1-464b-b252-925be0a19446

*Standar (S3) adalah bagian dari Pembaruan SQL Database Terbaru V12 (pratinjau).
Untuk informasi selengkapnya, lihat Apa yang Baru dalam Pratinjauhttps://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/ Azure SQL Database V12.

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

### -Sinkronkan
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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Memperbarui Database](https://msdn.microsoft.com/en-us/library/azure/dn505718.aspx)

[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)

[AzureSqlDatabase baru](./New-AzureSqlDatabase.md)

[Hapus-AzureSqlDatabase](./Remove-AzureSqlDatabase.md)

[Baru-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


