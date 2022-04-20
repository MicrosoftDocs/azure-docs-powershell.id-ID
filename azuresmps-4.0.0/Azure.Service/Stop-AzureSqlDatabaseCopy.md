---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: CB601E21-424D-4B09-85E5-A4B2A5068267
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8a7ad4662e63d5785bfbbbc80998285c5a4cc156
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142653976"
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
Cmdlet **Stop-AzureSqlDatabaseCopy** mengakhiri hubungan salinan berkelanjutan.
Cmdlet ini menghentikan pergerakan data antara database sumber dan database sekunder atau target, lalu mengubah status database sekunder menjadi database online mandiri.

Ada dua cara untuk mengakhiri hubungan salinan berkelanjutan, penghentian atau penghentian yang direncanakan dan penghentian paksa dengan kemungkinan hilangnya data.
Di server yang menghosting database sumber, Anda bisa menjalankan cmdlet ini dalam mode penghentian atau penghentian paksa.
Di server yang menghosting database sekunder, Anda harus menggunakan mode penghentian paksa.

Penghentian yang direncanakan menunggu hingga semua transaksi yang dilakukan pada database sumber, pada saat Anda menjalankan cmdlet, telah direplikasi ke database sekunder.
Penghentian paksa tidak menunggu replikasi transaksi yang dilakukan secara beredar, dan dapat menyebabkan kemungkinan hilangnya data dalam database sekunder.

Saat status replikasi DITUNDA, hanya penghentian paksa yang berhasil mengakhiri hubungan salinan berkelanjutan.
Jika status replikasi DITUNDA, penghentian yang tidak dipaksakan tidak didukung.

## EXAMPLES

### Contoh 1: Mengakhiri hubungan salinan berkelanjutan
```
PS C:\>Stop-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders" -PartnerServer "bk0b8kf658"
```

Perintah ini mengakhiri hubungan salinan database berkelanjutan bernama Pesanan di server bernama lpqd0zbr8y.
Server yang bernama bk0b8kf658 menghosting database sekunder.

### Contoh 2: Menghentikan hubungan salinan berkelanjutan secara paksa
```
PS C:\>$DatabaseCopy = Get-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -DatabaseName "Orders"
PS C:\> $DatabaseCopy | Stop-AzureSqlDatabaseCopy -ServerName "lpqd0zbr8y" -ForcedTermination
```

Perintah pertama mendapatkan hubungan salinan database untuk database bernama Pesanan di server bernama lpqd0zbr8y.

Perintah kedua menghentikan hubungan salinan berkelanjutan secara paksa dari server yang menghosting database sekunder.

## PARAMETERS

### -Database
Menentukan objek yang mewakili sumber Azure SQL Database.
Cmdlet ini mengakhiri hubungan salinan database berkelanjutan yang ditentukan parameter ini.

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
Cmdlet ini mengakhiri hubungan salinan database berkelanjutan yang ditentukan parameter ini.
Parameter ini menerima input pipeline.

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
Cmdlet ini mengakhiri hubungan salinan database berkelanjutan yang ditentukan parameter ini.

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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
Menunjukkan bahwa cmdlet ini menyebabkan penghentian paksa hubungan salinan berkelanjutan.
Penghentian paksa dapat menyebabkan hilangnya data.
Untuk menjalankan cmdlet ini di server yang menghosting database target, Anda harus menentukan parameter ini.
Untuk menjalankan cmdlet ini di server yang menghosting database sumber, jika database sekunder tidak tersedia, Anda harus menentukan parameter ini.

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
Jika Anda menentukan nama, nama harus sesuai dengan nama database sumber.

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
Menentukan nama server tempat database sumber berada.

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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.DatabaseCopy

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

### Tidak

## NOTES
* Autentikasi: Cmdlet ini memerlukan autentikasi berbasis sertifikat. Untuk contoh cara menggunakan autentikasi berbasis sertifikat untuk mengatur langganan saat ini, lihat cmdlet **New-AzureSqlDatabaseServerContext** .
* Pembatasan: Di server yang menjadi host database sekunder, hanya penghentian paksa yang didukung.
* Dampak penghentian pada database sekunder sebelumnya: Setelah penghentian, database sekunder menjadi database independen. Jika penyemaian sudah selesai di database sekunder, setelah penghentian database ini terbuka untuk akses penuh. Jika database sumber adalah database baca-tulis, database sekunder sebelumnya juga menjadi database baca-tulis.

  Jika penyemaian saat ini sedang berlangsung, penyemaian dibatalkan, dan database sekunder sebelumnya tidak pernah terlihat di server yang menjadi host database sekunder.

* Anda bisa mengatur database sumber ke mode baca-saja. Ini menjamin bahwa database sumber dan sekunder disinkronkan setelah penghentian, dan memastikan bahwa tidak ada transaksi yang dilakukan selama penghentian. Setelah penghentian selesai, atur kembali sumber ke mode baca-tulis. Secara opsional, Anda juga bisa mengatur database sekunder sebelumnya ke mode baca-tulis.
* Pemantauan: Untuk memverifikasi status operasi pada sumber dan target hubungan salinan berkelanjutan, gunakan cmdlet **Get-AzureSqlDatabaseOperation** .

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Hentikan Salinan Database](https://msdn.microsoft.com/en-us/library/dn509573.aspx)



[Get-AzureSqlDatabaseCopy](./Get-AzureSqlDatabaseCopy.md)

[Start-AzureSqlDatabaseCopy](./Start-AzureSqlDatabaseCopy.md)


