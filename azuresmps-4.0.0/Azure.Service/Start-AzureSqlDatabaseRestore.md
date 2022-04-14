---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 383F36F3-3F52-4FC3-99F7-831096E6037D
online version: ''
schema: 2.0.0
ms.openlocfilehash: c2e2fe901ee407af174f68f79cf6fdb73ca93d9d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141965796"
---
# Start-AzureSqlDatabaseRestore

## SYNOPSIS
Melakukan pemulihan titik dalam waktu database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### BySourceDatabaseObject
```
Start-AzureSqlDatabaseRestore [-SourceServerName <String>] -SourceDatabase <Database>
 [-TargetServerName <String>] -TargetDatabaseName <String> [-PointInTime <DateTime>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### BySourceRestorableDroppedDatabaseObject
```
Start-AzureSqlDatabaseRestore [-SourceServerName <String>]
 -SourceRestorableDroppedDatabase <RestorableDroppedDatabase> [-TargetServerName <String>]
 -TargetDatabaseName <String> [-PointInTime <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### BySourceDatabaseName
```
Start-AzureSqlDatabaseRestore -SourceServerName <String> -SourceDatabaseName <String>
 [-TargetServerName <String>] -TargetDatabaseName <String> [-PointInTime <DateTime>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### BySourceRestorableDroppedDatabaseName
```
Start-AzureSqlDatabaseRestore -SourceServerName <String> -SourceDatabaseName <String>
 -SourceDatabaseDeletionDate <DateTime> [-TargetServerName <String>] [-RestorableDropped]
 -TargetDatabaseName <String> [-PointInTime <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSqlDatabaseRestore** menjalankan pemulihan waktu database Dasar, Standar, atau Premium.
Azure SQL Database mempertahankan cadangan database Dasar 7 hari, Standar untuk 14 hari, dan Premium selama 35 hari.
Operasi pemulihan membuat database baru.
Jika database sumber tidak dihapus, parameter *SourceDatabaseName* dan *TargetDatabaseName* harus memiliki nilai yang berbeda.

Azure SQL Database saat ini tidak mendukung pemulihan lintas server.
Nama server sumber dan target harus sama.

## EXAMPLES

### Contoh 1: Memulihkan database yang ditentukan sebagai objek ke titik waktu
```
PS C:\> $Database = Get-AzureSqlDatabase -ServerName "Server01" -DatabaseName "Database17" 
PS C:\> $Operation = Start-AzureSqlDatabaseRestore -SourceDatabase $Database -TargetDatabaseName "DatabaseRestored" -PointInTime "2013-01-01 06:00:00"
```

Perintah pertama mendapatkan objek database untuk database bernama Database17 di server bernama Server01, lalu menyimpannya dalam variabel $Database.

Perintah kedua memulihkan database ke titik waktu tertentu.
Perintah menentukan nama untuk database baru.

### Contoh 2: Memulihkan database yang ditentukan menurut nama ke titik waktu
```
PS C:\> $Operation = Start-AzureSqlDatabaseRestore -SourceServerName "Server01" -SourceDatabaseName "Database17" -TargetDatabaseName "DatabaseRestored" -PointInTime "2013-01-01 06:00:00"
```

Perintah ini memulihkan database bernama Database17 ke titik waktu tertentu.
Perintah menentukan nama untuk database baru.

### Contoh 3: Memulihkan database yang diletakkan yang ditentukan sebagai objek ke titik waktu
```
PS C:\> $Database = Get-AzureSqlDatabase -RestorableDropped -ServerName "Server01" -DatabaseName "Database01" -DatabaseDeletionDate "2012-11-09T22:59:43.000Z" 
PS C:\> $Operation = Start-AzureSqlDatabaseRestore -SourceRestorableDroppedDatabase $Database -TargetDatabaseName "DroppedDatabaseRestored"
```

Perintah pertama mendapatkan objek database untuk database bernama Database01 di server bernama Server01.
Perintah menentukan parameter *RestorableDropped* .
Oleh karena itu, cmdlet mendapatkan database yang dipulihkan kembali ke titik pemulihan yang ditentukan.
Perintah menyimpan objek database tersebut dalam variabel $Database.

Perintah kedua memulihkan database yang dihapus yang ditentukan oleh $Database.
Perintah menentukan nama untuk database baru.

## PARAMETERS

### -PointInTime
Menentukan titik pemulihan untuk memulihkan database.
Ketika operasi pemulihan selesai, database dipulihkan ke status pada tanggal dan waktu yang ditentukan parameter ini.
Secara default, untuk database langsung yang diatur ini ke waktu saat ini, dan untuk database yang dihapus, cmdlet ini menggunakan waktu ketika database dihapus.

```yaml
Type: DateTime
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

### -RestorableDropped
Menunjukkan bahwa cmdlet ini memulihkan database yang dihapus kembali.

```yaml
Type: SwitchParameter
Parameter Sets: BySourceRestorableDroppedDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDatabase
Menentukan nama database yang dipulihkan cmdlet ini.

```yaml
Type: Database
Parameter Sets: BySourceDatabaseObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SourceDatabaseDeletionDate
Menentukan tanggal dan waktu saat database dihapus.
Anda harus menyertakan milidetik saat Menentukan waktu untuk mencocokkan waktu penghapusan database yang sebenarnya.

```yaml
Type: DateTime
Parameter Sets: BySourceRestorableDroppedDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDatabaseName
Menentukan nama database langsung yang dipulihkan cmdlet ini.

```yaml
Type: String
Parameter Sets: BySourceDatabaseName, BySourceRestorableDroppedDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceRestorableDroppedDatabase
Menentukan objek yang mewakili database yang dijatuhkan kembali yang dipulihkan cmdlet ini.
Untuk mendapatkan objek **RestorableDroppedDatabase** , gunakan cmdlet Get-AzureSqlDatabase, dan *tentukan parameter RestorableDropped* .

```yaml
Type: RestorableDroppedDatabase
Parameter Sets: BySourceRestorableDroppedDatabaseObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SourceServerName
Menentukan nama server tempat database sumber dijalankan, atau tempat database sumber dijalankan sebelum database tersebut dihapus.

```yaml
Type: String
Parameter Sets: BySourceDatabaseObject, BySourceRestorableDroppedDatabaseObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: BySourceDatabaseName, BySourceRestorableDroppedDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabaseName
Menentukan nama database baru yang dibuat oleh operasi pemulihan.

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

### -TargetServerName
Menentukan nama server tempat cmdlet ini memulihkan database.

Azure SQL Database saat ini tidak mendukung pemulihan lintas server.
Nama server sumber dan target harus sama.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDroppedDatabase

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestoreDatabaseOperation

## CATATAN
* Anda harus menggunakan autentikasi berbasis sertifikat untuk menjalankan cmdlet ini. Jalankan perintah berikut ini di komputer tempat menjalankan cmdlet ini: 

`PS C:\\\> $subId = \<Subscription ID\>`
`PS C:\\\> $thumbprint = \<Certificate Thumbprint\>`
`PS C:\\\> $myCert = Get-Item Cert:\CurrentUser\My\$thumbprint`
`PS C:\\\> Set-AzureSubscription -SubscriptionName "mySubscription" -SubscriptionId $subId -Certificate $myCert`
`PS C:\\\> Select-AzureSubscription -SubscriptionName "mySubscription"`

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Buat Permintaan Pemulihan Database](https://msdn.microsoft.com/en-us/library/dn509571.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)


