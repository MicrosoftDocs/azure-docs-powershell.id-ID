---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: B7F07494-FBCA-4A77-92BF-E0A2D7ACCD21
online version: ''
schema: 2.0.0
ms.openlocfilehash: 01b9e3689a8dc72871795da559dd71a24c1e1814
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426511"
---
# Start-AzureSqlDatabaseCopy

## SYNOPSIS
Memulai operasi penyalinan Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByInputObject
```
Start-AzureSqlDatabaseCopy -ServerName <String> -Database <Database> [-PartnerServer <String>]
 -PartnerDatabase <String> [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObjectContinuous
```
Start-AzureSqlDatabaseCopy -ServerName <String> -Database <Database> -PartnerServer <String>
 [-PartnerDatabase <String>] [-ContinuousCopy] [-OfflineSecondary] [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDatabaseName
```
Start-AzureSqlDatabaseCopy -ServerName <String> -DatabaseName <String> [-PartnerServer <String>]
 -PartnerDatabase <String> [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDatabaseNameContinuous
```
Start-AzureSqlDatabaseCopy -ServerName <String> -DatabaseName <String> -PartnerServer <String>
 [-PartnerDatabase <String>] [-ContinuousCopy] [-OfflineSecondary] [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSqlDatabaseCopy** memulai operasi penyalinan satu kali atau operasi penyalinan berkelanjutan dari tim Azure SQL Database.
Cmdlet ini tidak bertransaksi.

Database asli adalah database sumber.
Salinannya adalah database sekunder atau target.
Untuk salinan berkelanjutan, database sumber dan target tidak bisa berada di server yang sama, dan server yang menghosting database sumber dan target harus merupakan bagian dari langganan yang sama.

Jika Anda tidak menentukan parameter *ContinuousCopy,* cmdlet ini akan membuat salinan database sumber satu kali.
Saat respons diterima, operasi masih bisa berlangsung.
Anda dapat memantau operasi menggunakan cmdlet Get-AzureSqlDatabaseCopy Get-AzureSqlDatabaseOperation cmdlet.

Jika Anda menentukan *ContinuousCopy*, cmdlet ini akan membuat salinan berkelanjutan database sumber tersebut.
Saat respons diterima, operasi akan berlangsung.
Anda bisa memantau operasi dengan menggunakan **Get-AzureSqlDatabaseCopy** atau **Get-AzureSqlDatabaseOperation**.

Anda bisa membuat salinan berkelanjutan sebagai database online atau offline.
Salinan berkelanjutan online digunakan untuk mengonfigurasi Kode Geo-Replication untuk Azure SQL Database https://azure.microsoft.com/en-us/documentation/articles/sql-database-geo-replication-overview/ .
Salinan berkelanjutan offline digunakan untuk mengonfigurasi standar Geo-Replication untuk Azure SQL Database https://azure.microsoft.com/en-us/documentation/articles/sql-database-business-continuity-scenarios/ .

## EXAMPLES

### Contoh 1: Menjadwalkan salinan database berkelanjutan
```
PS C:\> Start-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf65" -ContinuousCopy
```

Perintah ini menjadwalkan salinan berkelanjutan database bernama Pesanan di server yang bernama lpqd0zbr8y.
Perintah membuat database target di server yang bernama bk0b8kf658.

### Contoh 2: Membuat salinan satu kali di server yang sama
```
PS C:\> Start-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerDatabase "OrdersCopy"
```

Perintah ini membuat salinan satu kali database bernama Pesanan di server yang bernama lpqd0zbr8y.
Perintah membuat salinan bernama OrdersCopy di server yang sama.

### Contoh 3: Menjadwalkan salinan database offline berkelanjutan
```
PS C:\> Start-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf65" -ContinuousCopy -OfflineSecondary
```

Perintah ini menjadwalkan salinan berkelanjutan database bernama Pesanan di server yang bernama lpqd0zbr8y.
Perintah ini membuat database target offline di server yang bernama bk0b8kf658.

## PARAMETERS

### -ContinuousCopy
Menunjukkan bahwa salinan database akan menjadi salinan berkelanjutan (database replika).
Salinan berkelanjutan tidak didukung di dalam server yang sama.
Jika parameter ini tidak ditentukan, maka salinan satu kali dijalankan.
Untuk salinan satu kali, database sumber dan mitra harus berada di server yang sama.

```yaml
Type: SwitchParameter
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Database
Menentukan objek yang mewakili sumber Azure SQL Database.
Parameter ini menerima input saluran.

```yaml
Type: Database
Parameter Sets: ByInputObject, ByInputObjectContinuous
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database sumber.

```yaml
Type: String
Parameter Sets: ByDatabaseName, ByDatabaseNameContinuous
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -OfflineSecsecry
Menentukan bahwa salinan berkelanjutan adalah salinan pasif, bukan salinan aktif.
Jika database sumber adalah database edisi Standar, maka parameter ini diperlukan.
Jika parameter ini ditentukan, *ContinuousCopy* juga harus ditentukan.

```yaml
Type: SwitchParameter
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerDatabase
Menentukan nama database target.
Jika Anda menentukan parameter *ContinuousCopy,* nilai untuk *PartnerDatabase* harus cocok dengan nama database sumber.
Jika tidak menentukan *ContinuousCopy*, Anda harus menentukan nama untuk database target, yang dapat berbeda dari nama database sumber.

```yaml
Type: String
Parameter Sets: ByInputObject, ByDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerServer
Menentukan nama server yang menjadi host database target.
Server ini harus berada dalam langganan Azure yang sama dengan server database sumber.

```yaml
Type: String
Parameter Sets: ByInputObject, ByDatabaseName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByInputObjectContinuous, ByDatabaseNameContinuous
Aliases: 

Required: True
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
Menentukan nama server di mana database sumber berada.

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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

## CATATAN
* Autentikasi: Cmdlet ini memerlukan autentikasi berbasis sertifikat. Untuk contoh cara menggunakan autentikasi berbasis sertifikat untuk mengatur langganan saat ini, lihat New-AzureSqlDatabaseServerContext cmdlet.
* Pemantauan: Untuk memeriksa status satu atau beberapa hubungan salinan berkelanjutan yang aktif di server, gunakan cmdlet **Get-AzureSqlDatabaseCopy.** Untuk memverifikasi status operasi di sumber dan target hubungan salinan berkelanjutan, gunakan cmdlet **Get-AzureSqlDatabaseOperation.**

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Mulai Salinan Database](https://msdn.microsoft.com/en-us/library/azure/dn509576.aspx)



[Get-AzureSqlDatabaseCopy](./Get-AzureSqlDatabaseCopy.md)

[Stop-AzureSqlDatabaseCopy](./Stop-AzureSqlDatabaseCopy.md)


