---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 5AEF7D44-624D-4794-86FF-156E6729BB56
online version: ''
schema: 2.0.0
ms.openlocfilehash: 26b4df0e9247004a65e061fe3f7842405264e81549d7506586863e539da60f9e
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419235"
---
# Get-AzureSqlDatabaseCopy

## SYNOPSIS
Memeriksa status hubungan salinan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByServerNameOnly (Default)
```
Get-AzureSqlDatabaseCopy -ServerName <String> [-DatabaseName <String>] [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByInputObject
```
Get-AzureSqlDatabaseCopy -ServerName <String> -DatabaseCopy <DatabaseCopy> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByDatabase
```
Get-AzureSqlDatabaseCopy -ServerName <String> -Database <Database> [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseCopy** memeriksa status salah satu atau beberapa hubungan salin aktif.
Jalankan cmdlet ini setelah Anda menjalankan cmdlet Start-AzureSqlDatabaseCopy Stop-AzureSqlDatabaseCopy cmdlet.
Anda bisa memeriksa hubungan salinan tertentu, semua hubungan salinan, atau daftar hubungan salinan yang difilter, seperti semua salinan pada server target tertentu.
Anda dapat menjalankan cmdlet ini di server yang meng host database sumber atau target.

Cmdlet ini sinkron.
Cmdlet memblokir Azure PowerShell konsol hingga mengembalikan objek status.

Parameter *PartnerServer* *dan PartnerDatabase* bersifat opsional.
Jika Anda tidak menentukan salah satu parameter, cmdlet ini akan mengembalikan tabel hasil.
Untuk melihat status hanya untuk database tertentu, tentukan kedua parameter.

## EXAMPLES

### Contoh 1: Mendapatkan status salinan database
```
PS C:\> Get-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf658"
```

Perintah ini mendapatkan status database bernama Pesanan di server yang bernama lpqd0zbr8y.
Parameter *PartnerServer* membatasi perintah ini ke server bk0b8kf658.

### Contoh 2: Mendapatkan status semua salinan di serverDapatkan status semua salinan di server
```
PS C:\> Get-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y"
```

Perintah ini mendapatkan status semua salinan aktif di server yang bernama lpqd0zbr8y.

## PARAMETERS

### -Database
Menentukan objek yang mewakili sumber Azure SQL Database.
Cmdlet ini mendapatkan status salinan database yang ditentukan oleh parameter ini.

```yaml
Type: Database
Parameter Sets: ByDatabase
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseCopy
Menentukan objek yang mewakili database.
Cmdlet ini mendapatkan status salinan database yang ditentukan oleh parameter ini.
Parameter ini menerima input saluran.

```yaml
Type: DatabaseCopy
Parameter Sets: ByInputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database sumber.
Cmdlet ini mendapatkan status salinan database yang ditentukan oleh parameter ini.

```yaml
Type: String
Parameter Sets: ByServerNameOnly
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerDatabase
Menentukan nama database sekunder.
Jika database ini tidak ditemukan dalam tampilan sys.dm_database_copies manajemen dinamis, cmdlet ini akan mengembalikan objek status kosong.

```yaml
Type: String
Parameter Sets: ByServerNameOnly, ByDatabase
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerServer
Menentukan nama server yang menjadi host database target.
Jika server ini tidak ditemukan dalam tampilan manajemen sys.dm_database_copies dinamis, cmdlet ini akan mengembalikan objek status kosong.

```yaml
Type: String
Parameter Sets: ByServerNameOnly, ByDatabase
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
Menentukan nama server tempat salinan database berada.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

## CATATAN
* Autentikasi: Cmdlet ini memerlukan autentikasi berbasis sertifikat. Untuk contoh cara menggunakan autentikasi berbasis sertifikat untuk mengatur langganan saat ini, lihat cmdlet New-AzureSqlDatabaseServerContext cmdlet.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)



[Start-AzureSqlDatabaseCopy](./Start-AzureSqlDatabaseCopy.md)

[Stop-AzureSqlDatabaseCopy](./Stop-AzureSqlDatabaseCopy.md)


