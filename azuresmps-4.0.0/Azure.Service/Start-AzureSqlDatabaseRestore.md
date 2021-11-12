---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 383F36F3-3F52-4FC3-99F7-831096E6037D
online version: ''
schema: 2.0.0
ms.openlocfilehash: c2e2fe901ee407af174f68f79cf6fdb73ca93d9d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425829"
---
# Start-AzureSqlDatabaseRestore

## SYNOPSIS
Melakukan titik dalam pemulihan waktu database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### BySourceDatabaseObject
```
Start-AzureSqlDatabaseRestore [-SourceServerName <String>] -SourceDatabase <Database>
 [-TargetServerName <String>] -TargetDatabaseName <String> [-PointInTime <DateTime>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### BySourceRestorableDatappedDatabaseObject
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

### BySourceRestorableDatappedDatabaseName
```
Start-AzureSqlDatabaseRestore -SourceServerName <String> -SourceDatabaseName <String>
 -SourceDatabaseDeletionDate <DateTime> [-TargetServerName <String>] [-RestorableDropped]
 -TargetDatabaseName <String> [-PointInTime <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSqlDatabaseRestore** menjalankan titik dalam pemulihan waktu database Dasar, Standar, Premium baru.
Azure SQL Database mempertahankan Cadangan database dasar 7 hari, Standar selama 14 hari, dan Premium selama 35 hari.
Operasi pemulihan akan membuat database baru.
Jika database sumber tidak dihapus, parameter *SourceDatabaseName dan* *TargetDatabaseName* harus memiliki nilai yang berbeda.

Azure SQL Database saat ini tidak mendukung pemulihan server silang.
Nama server sumber dan target harus sama.

## EXAMPLES

### Contoh 1: Memulihkan database yang ditentukan sebagai objek ke titik dalam waktu
```
PS C:\> $Database = Get-AzureSqlDatabase -ServerName "Server01" -DatabaseName "Database17" 
PS C:\> $Operation = Start-AzureSqlDatabaseRestore -SourceDatabase $Database -TargetDatabaseName "DatabaseRestored" -PointInTime "2013-01-01 06:00:00"
```

Perintah pertama mendapatkan objek database untuk database yang bernama Database17 di server yang bernama Server01, lalu menyimpannya dalam $Database baru.

Perintah kedua memulihkan database ke titik waktu tertentu.
Perintah menentukan pada nama untuk database baru.

### Contoh 2: Memulihkan database yang ditentukan menurut nama menjadi titik dalam waktu
```
PS C:\> $Operation = Start-AzureSqlDatabaseRestore -SourceServerName "Server01" -SourceDatabaseName "Database17" -TargetDatabaseName "DatabaseRestored" -PointInTime "2013-01-01 06:00:00"
```

Perintah ini memulihkan database bernama Database17 ke titik tertentu dalam waktu.
Perintah menentukan pada nama untuk database baru.

### Contoh 3: Memulihkan database jatuh yang ditentukan sebagai objek ke titik waktu
```
PS C:\> $Database = Get-AzureSqlDatabase -RestorableDropped -ServerName "Server01" -DatabaseName "Database01" -DatabaseDeletionDate "2012-11-09T22:59:43.000Z" 
PS C:\> $Operation = Start-AzureSqlDatabaseRestore -SourceRestorableDroppedDatabase $Database -TargetDatabaseName "DroppedDatabaseRestored"
```

Perintah pertama mendapatkan objek database untuk database yang bernama Database01 di server yang bernama Server01.
Perintah menentukan parameter *RestorablePped.*
Oleh karena itu, cmdlet akan memulihkan database dengan titik pemulihan yang ditentukan.
Perintah menyimpan objek database tersebut dalam $Database baru.

Perintah kedua memulihkan database jatuh yang ditentukan oleh $Database.
Perintah menentukan pada nama untuk database baru.

## PARAMETERS

### -PointInTime
Menentukan titik pemulihan untuk memulihkan database.
Ketika operasi pemulihan selesai, database dipulihkan ke keadaan pada tanggal dan waktu yang ditentukan parameter ini.
Secara default, untuk database langsung yang diatur ke waktu saat ini, dan untuk database yang dijatuhkan, cmdlet ini menggunakan waktu ketika database itu dijatuhkan.

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

### -Restorable Di dapat Disesuaikan
Menunjukkan bahwa cmdlet ini memulihkan database yang dipulihkan.

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
Menentukan tanggal dan waktu penghapusan database.
Anda harus menyertakan milidetik saat menentukan waktu yang sesuai dengan waktu penghapusan database aktual.

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

### -SourceRestorableDatabase
Menentukan objek yang mewakili database yang dapat dipulihkan oleh cmdlet ini.
Untuk mendapatkan objek **RestorableDatappedDatabase,** gunakan cmdlet Get-AzureSqlDatabase, dan tentukan parameter *RestorablePped.*

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
Menentukan nama server di mana database sumber berada dan berjalan, atau di mana database sumber dijalankan sebelum dihapus.

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
Menentukan nama server tempat cmdlet memulihkan database.

Azure SQL Database saat ini tidak mendukung pemulihan server silang.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDataPpedDatabase

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestoreDatabaseOperation

## CATATAN
* Anda harus menggunakan autentikasi berbasis sertifikat untuk menjalankan cmdlet ini. Jalankan perintah berikut di komputer tempat menjalankan cmdlet ini: 

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


