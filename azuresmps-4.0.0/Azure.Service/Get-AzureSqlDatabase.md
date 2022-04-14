---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 7427A101-9439-45B9-B72E-F8C2DA85E412
online version: ''
schema: 2.0.0
ms.openlocfilehash: 70b60e311a2a9fc653c12a89c0d8ca15d9b6030a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141772362"
---
# Get-AzureSqlDatabase

## SYNOPSIS
Mengambil satu atau beberapa database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByConnectionContext (Default)
```
Get-AzureSqlDatabase -ConnectionContext <IServerDataServiceContext> [-Database <Database>]
 [-DatabaseName <String>] [-RestorableDropped] [-RestorableDroppedDatabase <RestorableDroppedDatabase>]
 [-DatabaseDeletionDate <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByServerName
```
Get-AzureSqlDatabase -ServerName <String> [-Database <Database>] [-DatabaseName <String>] [-RestorableDropped]
 [-RestorableDroppedDatabase <RestorableDroppedDatabase>] [-DatabaseDeletionDate <DateTime>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabase** mengambil satu atau beberapa contoh Azure SQL Database dari server Azure SQL Database.
Anda dapat menentukan server dengan konteks koneksi server Azure SQL Database yang dibuat menggunakan cmdlet **New-AzureSqlDatabaseServerContext**.
Atau, jika Anda menentukan nama server Azure SQL Database, cmdlet menggunakan informasi langganan Azure saat ini untuk mengautentikasi permintaan untuk mengakses server.

Jika Anda tidak menentukan database, cmdlet **Get-AzureSqlDatabase** mengembalikan semua database dari server yang ditentukan.

Mengambil database yang dihapus yang dapat dipulihkan:

Ambil database yang dihapus kembali menggunakan parameter *RestorableDropped* .
Untuk mengembalikan semua database yang dihapus kembali, gunakan parameter *RestorableDropped* tanpa *DatabaseName* dan *DatabaseDeletionDate*.
Untuk mengembalikan database tertentu yang dipulihkan, gunakan parameter *RestorableDropped* dengan parameter *DatabaseName* dan *DatabaseDeletionDate* .
Saat mengambil database tertentu yang dapat dipulihkan menggunakan parameter *DatabaseName* , Anda juga harus menyertakan parameter *DatabaseDeletionDate* dan nilai *DatabaseDeletionDate* tertentu harus menyertakan milidetik agar sesuai dengan database yang diinginkan.

Cmdlet **Get-AzureSqlDatabase** mengembalikan semua database yang dihapus kembali di server, atau satu database tertentu yang cocok dengan *DatabaseName* dan *DatabaseDeletionDate*.
Untuk mengembalikan database yang dihapus yang dapat dipulihkan yang memenuhi kriteria yang berbeda, seperti semua database yang dipulihkan kembali dari nama tertentu, Anda harus mengembalikan semua database yang dipulihkan kembali, lalu memfilter hasil pada klien.

## EXAMPLES

### Contoh 1: Mengambil semua database di server
```
PS C:\> Get-AzureSqlDatabase -ServerName "lpqd0zbr8y"
```

Perintah ini mengambil semua database di server bernama lpqd0zbr8y.

### Contoh 2: Mengambil semua database yang diletakkan kembali di server
```
PS C:\> Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -RestorableDropped
```

Perintah ini mengambil semua database yang dihapus kembali di server bernama lpqd0zbr8y.

### Contoh 3: Mengambil database dari server yang ditentukan oleh konteks koneksi
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
```

Perintah ini mengambil database bernama Database01 dari server yang ditentukan oleh konteks koneksi $Context.

### Contoh 4: Menyimpan objek database dalam variabel
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
```

Perintah ini mengambil database bernama Database01 dari server bernama lpqd0zbr8y.
Perintah menyimpan objek database dalam variabel $Database 01.

### Contoh 5: Mengambil database yang diletakkan dengan pemulihan
```
PS C:\> $DroppedDB = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01" -DatabaseDeletionDate "2012-11-09T22:59:43.000Z" -RestorableDropped
```

Perintah ini mengambil database yang dihapus kembali bernama Database01 yang dihapus pada 9/11/2012 dari server bernama lpqd0zbr8y.
Perintah ini menyimpan hasil dalam variabel $DroppedDB.

### Contoh 6: Mengambil semua database yang dihapus kembali di server dan memfilter hasilnya
```
PS C:\> Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -RestorableDropped | Where-Object {$_.Name -eq "ContactDB"}
```

Perintah ini mengambil semua database yang dibuang kembali di server bernama lpqd0zbr8y, lalu memfilter hasil ke database yang bernama ContactDB saja.

## PARAMETERS

### -ConnectionContext
Menentukan konteks koneksi server untuk mengambil database.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: Context

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Database
Menentukan objek yang mewakili database yang diambil cmdlet ini.

```yaml
Type: Database
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseDeletionDate
Menentukan tanggal dan waktu penghapusan.
Jika Anda menentukan parameter *RestorableDropped, tentukan* parameter ini untuk mengambil database yang dihapus kembali berdasarkan tanggal dan waktu penghapusan.

Parameter *DatabaseDeletionDate* harus menyertakan milidetik agar sesuai dengan waktu database yang diinginkan.
Menentukan nilai tanpa milidetik menghasilkan database yang tidak ditemukan.

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

### -DatabaseName
Menentukan nama database yang diambil cmdlet ini.

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
Menunjukkan bahwa cmdlet ini mengembalikan objek *RestorableDroppedDatabase* , bukan objek *Database* .
Anda bisa menggunakan parameter *DatabaseDeletionDate* untuk memilih database tertentu yang dihapus yang dapat disembuhkan.

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

### -RestorableDroppedDatabase
Menentukan objek yang mewakili database yang dijatuhkan kembali yang diambil cmdlet ini.

```yaml
Type: RestorableDroppedDatabase
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server yang berisi database yang diambil cmdlet ini.
Cmdlet menggunakan langganan Azure saat ini untuk mengakses server.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDroppedDatabase

## OUTPUTS

### Ienumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database\>
Cmdlet ini mengembalikan objek *Database* jika Anda tidak menentukan parameter *RestorableDropped* .

### Ienumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDroppedDatabase\>
Cmdlet ini mengembalikan objek *RestorableDroppedDatabase* jika Anda menentukan parameter *RestorableDropped* .

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[AzureSqlDatabase baru](./New-AzureSqlDatabase.md)

[Baru-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)

[Hapus-AzureSqlDatabase](./Remove-AzureSqlDatabase.md)

[Set-AzureSqlDatabase](./Set-AzureSqlDatabase.md)


