---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: F4FE79DB-B481-49BD-A33B-7C642A136890
online version: ''
schema: 2.0.0
ms.openlocfilehash: 030002c5aebf7f45e6541f70dbcdf5a0af2a0cb2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142245149"
---
# New-AzureSqlDatabase

## SYNOPSIS
Membuat Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByConnectionContext
```
New-AzureSqlDatabase -ConnectionContext <IServerDataServiceContext> -DatabaseName <String>
 [-Collation <String>] [-Edition <DatabaseEdition>] [-ServiceObjective <ServiceObjective>] [-MaxSizeGB <Int32>]
 [-MaxSizeBytes <Int64>] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByServerName
```
New-AzureSqlDatabase -ServerName <String> -DatabaseName <String> [-Collation <String>]
 [-Edition <DatabaseEdition>] [-ServiceObjective <ServiceObjective>] [-MaxSizeGB <Int32>]
 [-MaxSizeBytes <Int64>] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **AzureSqlDatabase Baru** membuat Azure SQL Database.
Anda dapat menentukan server menggunakan konteks koneksi server Azure SQL Database yang dibuat menggunakan cmdlet **New-AzureSqlDatabaseServerContext**.
Atau, jika Anda menentukan nama server, cmdlet menggunakan informasi langganan Azure saat ini untuk mengautentikasi permintaan untuk mengakses server.

Saat Anda membuat database baru dengan menentukan server Azure SQL Database, cmdlet **New-AzureSqlDatabase** membuat konteks koneksi sementara menggunakan nama server yang ditentukan dan informasi langganan Azure saat ini untuk melakukan operasi.

## EXAMPLES

### Contoh 1: Membuat database
```
PS C:\> $Database01 = New-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01" -Edition "Business" -MaxSizeGB 50 -Collation "SQL_Latin1_General_CP1_CI_AS"
```

Perintah ini membuat Azure SQL Database bernama Database1, untuk $Context konteks koneksi server Azure SQL Database.

### Contoh 2: Membuat database dalam langganan saat ini
```
PS C:\> $Database01 = New-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01" -Edition "Business" -MaxSizeGB 50 -Collation "SQL_Latin1_General_CP1_CI_AS"
```

Contoh ini membuat database bernama Database1, di server Azure SQL Database yang ditentukan bernama lpqd0zbr8y.
Cmdlet menggunakan informasi langganan Azure saat ini untuk mengautentikasi permintaan untuk mengakses server.

## PARAMETERS

### -Collation
Menentukan kolase untuk database baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionContext
Menentukan konteks koneksi server tempat cmdlet ini membuat database.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: Context

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Edisi
Menentukan edisi untuk Azure SQL Database baru.
Nilai yang valid adalah: 

- Tidak
- Web
- Bisnis
- Dasar
- Standar
-  Premium

Nilai defaultnya adalah Web.

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
Memperbolehkan tindakan untuk diselesaikan tanpa meminta konfirmasi kepada pengguna.

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
Menentukan ukuran maksimum database dalam byte.
Anda dapat menentukan parameter ini atau parameter *MaxSizeGB* .
Lihat deskripsi parameter *MaxSizeGB* untuk nilai yang dapat diterima berdasarkan edisi.

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
Menentukan ukuran maksimum database dalam gigabyte.
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
Menentukan nama server Azure SQL Database untuk memuat database baru.

```yaml
Type: String
Parameter Sets: ByServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceObjective
Menentukan objek yang mewakili tujuan layanan baru (tingkat kinerja) untuk database ini.
Nilai ini menunjukkan tingkat sumber daya yang ditetapkan untuk database ini.
Nilai yang valid adalah: 

Dasar: dd6d99bb-f193-4ec1-86f2-43d3bccbc49c Standard (S0): f1173c43-91bd-4aaa-973c-54e79e15235b Standard (S1): 1b1ebd4d-d903-4baa-97f9-4ea675f5e928 Standard (S2): 455330e1-00cd-488b-b5fa-177c226f28b7 *Standard (S3): 789681b8-ca10-4eb0-bdf2-e0b050601b40 Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d Premium (P2): a7d1b92d-c987-4375-b54d-2b1d0e0f5bb0 Premium (P3): a7c4c615-cfb1-464b-b252-925be0a19446

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

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## CATATAN
* Untuk menghapus database yang dibuat oleh **New-AzureSqlDatabase**, gunakan cmdlet Remove-AzureSqlDatabase.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Membuat Database](https://msdn.microsoft.com/en-us/library/azure/dn505701.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)

[Baru-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)

[Hapus-AzureSqlDatabase](./Remove-AzureSqlDatabase.md)

[Set-AzureSqlDatabase](./Set-AzureSqlDatabase.md)


