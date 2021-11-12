---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: CB601E21-424D-4B09-85E5-A4B2A5068267
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8a7ad4662e63d5785bfbbbc80998285c5a4cc156
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426513"
---
# Stop-AzureSqlDatabaseCopy

## SYNOPSIS
Mengakhiri hubungan salinan berkelanjutan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByInputObject
```
Stop-AzureSqlDatabaseCopy -ServerName <String> -DatabaseCopy <DatabaseCopy> [-ForcedTermination] [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDatabase
```
Stop-AzureSqlDatabaseCopy -ServerName <String> -Database <Database> [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-ForcedTermination] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByDatabaseName
```
Stop-AzureSqlDatabaseCopy -ServerName <String> -DatabaseName <String> [-PartnerServer <String>]
 [-PartnerDatabase <String>] [-ForcedTermination] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureSqlDatabaseCopy** mengakhiri hubungan salin berkelanjutan.
Cmdlet ini menghentikan gerakan data antara database sumber dan database sekunder atau target, lalu mengubah status database sekunder menjadi database online mandiri.

Ada dua cara untuk mengakhiri hubungan salinan berkelanjutan, penghentian atau pemutusan yang direncanakan dan pemutusan paksa dengan kemungkinan hilangnya data.
Di server yang meng host database sumber, Anda bisa menjalankan cmdlet ini dalam mode penghentian atau pemutusan paksa.
Di server yang menjadi host database sekunder, Anda harus menggunakan mode pemutusan paksa.

Penghentian yang direncanakan akan menunggu hingga semua transaksi yang dilakukan pada database sumber, pada saat Anda menjalankan cmdlet, telah direplikasi ke database sekunder.
Pemutusan paksa tidak akan menunggu replikasi semua transaksi yang berkomitmen untuk terjadi, dan dapat menyebabkan kemungkinan hilangnya data dalam database sekunder.

Sementara status replikasi TERTUNDA, hanya pemutusan paksa yang berhasil mengakhiri hubungan salinan berkelanjutan.
Jika status replikasi TERTUNDA, pemutusan yang tidak dipaksa tidak didukung.

## EXAMPLES

### Contoh 1: Akhiri hubungan menyalin berkelanjutan
```
PS C:\>Stop-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf658"
```

Perintah ini mengakhiri hubungan salinan berkelanjutan dari database bernama Orders di server bernama lpqd0zbr8y.
Server yang bernama bk0b8kf658 menjadi host database sekunder.

### Contoh 2: Secara forcibly mengakhiri hubungan menyalin berkelanjutan
```
PS C:\>$DatabaseCopy = Get-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders"
PS C:\> $DatabaseCopy | Stop-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -ForcedTermination
```

Perintah pertama mendapatkan hubungan salinan database untuk database bernama Pesanan di server yang bernama lpqd0zbr8y.

Perintah kedua secara forcibly mengakhiri hubungan menyalin berkelanjutan dari server yang menjadi host database sekunder.

## PARAMETERS

### -Database
Menentukan objek yang mewakili sumber Azure SQL Database.
Cmdlet ini mengakhiri hubungan salinan berkelanjutan dari database yang ditentukan parameter ini.

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
Cmdlet ini mengakhiri hubungan salinan berkelanjutan dari database yang ditentukan parameter ini.
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
Menentukan nama database.
Cmdlet ini mengakhiri hubungan salinan berkelanjutan dari database yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: ByDatabaseName
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

### -ForcedTermination
Mengindikasikan bahwa cmdlet ini menyebabkan pemutusan paksa hubungan salinan berkelanjutan.
Pemutusan paksa dapat mengakibatkan hilangnya data.
Untuk menjalankan cmdlet ini di server yang meng host database target, Anda harus menentukan parameter ini.
Untuk menjalankan cmdlet ini di server yang meng host database sumber, jika database sekunder tidak tersedia, Anda harus menentukan parameter ini.

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

### -PartnerDatabase
Menentukan nama database sekunder.
Jika Anda menentukan sebuah nama, nama itu harus cocok dengan nama database sumber.

```yaml
Type: String
Parameter Sets: ByDatabase, ByDatabaseName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerServer
Menentukan nama server yang menjadi host database target.

```yaml
Type: String
Parameter Sets: ByDatabase, ByDatabaseName
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Tidak ada

## CATATAN
* Autentikasi: Cmdlet ini memerlukan autentikasi berbasis sertifikat. Untuk contoh cara menggunakan autentikasi berbasis sertifikat untuk mengatur langganan saat ini, lihat cmdlet **New-AzureSqlDatabaseServerContext.**
* Pembatasan: Di server yang menjadi host database sekunder, hanya pemutusan paksa yang didukung.
* Dampak pemutusan pada database sekunder sebelumnya: Setelah pemutusan, database sekunder menjadi database independen. Jika pengimatan telah selesai di database sekunder, setelah penghentian, database ini akan terbuka untuk akses penuh. Jika database sumber merupakan database baca-tulis, database kedua juga menjadi database baca-tulis.

  Jika awalan sedang berlangsung, awalan akan dibatalkan, dan database kedua tidak akan terlihat pada server yang menjadi host database sekunder.

* Anda bisa mengatur database sumber ke mode baca-saja. Ini menjamin bahwa database sumber dan sekunder disinkronkan setelah pemutusan, dan memastikan bahwa tidak ada transaksi yang dilakukan selama pemutusan. Setelah pemutusan selesai, atur kembali sumber ke mode baca-tulis. Secara opsional, Anda juga bisa mengatur database sekunder yang sebelumnya ke mode baca-tulis.
* Pemantauan: Untuk memverifikasi status operasi di sumber dan target hubungan salinan berkelanjutan, gunakan cmdlet **Get-AzureSqlDatabaseOperation.**

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database SQL Azure](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Menghentikan Salinan Database](https://msdn.microsoft.com/en-us/library/dn509573.aspx)



[Get-AzureSqlDatabaseCopy](./Get-AzureSqlDatabaseCopy.md)

[Start-AzureSqlDatabaseCopy](./Start-AzureSqlDatabaseCopy.md)


