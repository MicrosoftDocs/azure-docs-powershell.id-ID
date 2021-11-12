---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 7427A101-9439-45B9-B72E-F8C2DA85E412
online version: ''
schema: 2.0.0
ms.openlocfilehash: 70b60e311a2a9fc653c12a89c0d8ca15d9b6030a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421569"
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
Anda dapat menentukan server dengan konteks koneksi Azure SQL Database server yang dibuat menggunakan cmdlet **New-AzureSqlDatabaseServerContext.**
Atau, jika Anda menentukan Azure SQL Database server, cmdlet menggunakan informasi langganan Azure saat ini untuk mengautentikasi permintaan agar dapat mengakses server.

Jika Anda tidak menentukan database, cmdlet **Get-AzureSqlDatabase** mengembalikan semua database dari server yang ditentukan.

Mengambil database yang bisa dikembalikan:

Ambil database yang bisa dikembalikan dengan menggunakan parameter *Restorable Restorable Restorpped.*
Untuk mengembalikan semua database yang bisa dikembalikan gunakan parameter  *RestorableName dan* *DatabaseDeletionDate*.
Untuk mengembalikan database tertentu yang bisa dikembalikan gunakan parameter *RestorablePped* dengan parameter *DatabaseName* *dan DatabaseDeletionDate.*
Saat mengambil database tertentu yang dapat dikembalikan menggunakan parameter *DatabaseName* Anda juga harus menyertakan parameter *DatabaseDeletionDate* dan nilai *DatabaseDeletionDate* yang ditentukan harus menyertakan milidetik agar cocok dengan database yang diinginkan.

Cmdlet **Get-AzureSqlDatabase** mengembalikan semua database yang rusak di server, atau satu database tertentu yang cocok baik *DatabaseName* maupun *DatabaseDeletionDate*.
Untuk mengembalikan database yang bisa dikembalikan yang memenuhi kriteria berbeda, seperti semua database bernama tertentu yang bisa dikembalikan, Anda harus mengembalikan semua database yang bisa dikembalikan, lalu memfilter hasil pada klien.

## EXAMPLES

### Contoh 1: Mengambil semua database di server
```
PS C:\> Get-AzureSqlDatabase -ServerName "lpqd0zbr8y"
```

Perintah ini mengambil semua database di server bernama lpqd0zbr8y.

### Contoh 2: Mengambil semua database yang jatuh dan dapat dikembalikan di server
```
PS C:\> Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -RestorableDropped
```

This command retrieves all restorable dropped databases on the server named lpqd0zbr8y.

### Contoh 3: Mengambil database dari server yang ditentukan oleh konteks koneksi
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
```

Perintah ini mengambil database yang bernama Database01 dari server yang ditentukan oleh koneksi $Context.

### Contoh 4: Menyimpan objek database dalam variabel
```
PS C:\> $Database01 = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
```

Perintah ini mengambil database yang bernama Database01 dari server yang bernama lpqd0zbr8y.
Perintah menyimpan objek database di variabel $Database 01.

### Contoh 5: Mengambil database yang bisa dikembalikan
```
PS C:\> $DroppedDB = Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01" -DatabaseDeletionDate "2012-11-09T22:59:43.000Z" -RestorableDropped
```

Perintah ini mengambil database yang dihapus yang bisa dikembalikan bernama Database01 yang dihapus pada 9/11/2012 dari server yang bernama lpqd0zbr8y.
Perintah ini menyimpan hasil dalam $DroppedDB variabel.

### Contoh 6: Ambil semua database yang bisa dikembalikan di server dan filter hasilnya
```
PS C:\> Get-AzureSqlDatabase -ServerName "lpqd0zbr8y" -RestorableDropped | Where-Object {$_.Name -eq "ContactDB"}
```

Perintah ini mengambil semua database yang bisa dikembalikan di server yang bernama lpqd0zbr8y, lalu memfilter hasil hanya untuk database bernama ContactDB.

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
Jika Anda menentukan parameter *RestorablePped,* tentukan parameter ini untuk mengambil database yang dihapus yang bisa dikembalikan berdasarkan tanggal dan waktu penghapusan.

Parameter *DatabaseDeletionDate* harus menyertakan milidetik untuk mencocokkan waktu database yang diinginkan.
Menentukan nilai tanpa hasil milidetik dalam database tidak ditemukan.

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
Menunjukkan bahwa cmdlet ini mengembalikan *objek Restorable RestorablePpedDatabase* dan bukan *objek Database.*
Anda bisa menggunakan *parameter DatabaseDeletionDate* untuk memilih database tertentu yang diturunkan.

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

### -RestorableDatabase
Menentukan objek yang mewakili database jatuh yang dapat dikembalikan yang diambil cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDataPpedDatabase

## OUTPUTS

### IEnumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database\>
Cmdlet ini mengembalikan *objek Database* jika Anda tidak menentukan parameter *RestorablePped.*

### IEnumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.RestorableDroppedDatabase\>
Cmdlet ini mengembalikan objek *RestorableDatabase jika* Anda menentukan parameter *RestorablePped.*

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database SQL Azure](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[New-AzureSqlDatabase](./New-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)

[Remove-AzureSqlDatabase](./Remove-AzureSqlDatabase.md)

[Set-AzureSqlDatabase](./Set-AzureSqlDatabase.md)


