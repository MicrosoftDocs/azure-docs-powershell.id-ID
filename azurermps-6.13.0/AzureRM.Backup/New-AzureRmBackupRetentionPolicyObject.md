---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 9574CEB5-B699-4606-8C5E-CE2C0D01092D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/new-azurermbackupretentionpolicyobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/New-AzureRmBackupRetentionPolicyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/New-AzureRmBackupRetentionPolicyObject.md
ms.openlocfilehash: 740077def0ba0eccb1d962b88317fadb3c5c897c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420379"
---
# New-AzureRmBackupRetentionPolicyObject

## SYNOPSIS
Membuat kebijakan penyimpanan Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DailyRetentionParamSet
```
New-AzureRmBackupRetentionPolicyObject [-DailyRetention] -Retention <Int32>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### WeeklyRetentionParamSet
```
New-AzureRmBackupRetentionPolicyObject [-WeeklyRetention] -DaysOfWeek <String[]> -Retention <Int32>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### MonthlyRetentionInDailyFormatParamSet
```
New-AzureRmBackupRetentionPolicyObject [-MonthlyRetentionInDailyFormat]
 -DaysOfMonth <System.Collections.Generic.List`1[System.String]> -Retention <Int32>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### MonthlyRetentionInWeeklyFormatParamSet
```
New-AzureRmBackupRetentionPolicyObject [-MonthlyRetentionInWeeklyFormat] -DaysOfWeek <String[]>
 -WeekNumber <String[]> -Retention <Int32> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### YearlyRetentionInDailyFormatParamSet
```
New-AzureRmBackupRetentionPolicyObject [-YearlyRetentionInDailyFormat]
 -DaysOfMonth <System.Collections.Generic.List`1[System.String]> -MonthsOfYear <String[]> -Retention <Int32>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### YearlyRetentionInWeeklyFormatParamSet
```
New-AzureRmBackupRetentionPolicyObject [-YearlyRetentionInWeeklyFormat] -DaysOfWeek <String[]>
 -WeekNumber <String[]> -MonthsOfYear <String[]> -Retention <Int32> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmBackupRetentionPolicyObject** membuat kebijakan penyimpanan Azure Backup.
Kebijakan penyimpanan menentukan berapa lama Cadangan mempertahankan titik pemulihan.
Tipe penyimpanan adalah sebagai berikut: 
- Harian 
- Mingguan 
- Bulanan 
- Tahunan Buat satu kebijakan penyimpanan untuk setiap tipe penyimpanan yang ingin Anda gunakan.
Kebijakan pencadangan dikaitkan dengan setidaknya satu kebijakan penyimpanan.
Untuk membuat kebijakan pencadangan, gunakan cmdlet New-AzureRmBackupProtectionPolicy lanjut.
Sebagai gantinya, Anda dapat menyediakan kebijakan penyimpanan Enable-AzureRmBackupProtection cmdlet.

## EXAMPLES

### Contoh 1: Membuat kebijakan penyimpanan untuk penyimpanan harian
```
PS C:\>$Daily = New-AzureRmBackupRetentionPolicyObject -DailyRetention -Retention 30
PS C:\> $Daily
RetentionType      Retention          RetentionTimes
-------------      ---------          --------------
Daily              30
```

Perintah pertama membuat kebijakan penyimpanan selama 30 hari penyimpanan harian, lalu menyimpannya di $Daily penyimpanan.
Perintah kedua menampilkan konten $Daily.

### Contoh 2: Membuat kebijakan penyimpanan bulanan
```
PS C:\>$Monthly = New-AzureRmBackupRetentionPolicyObject -MonthlyRetentionInDailyFormat -DaysOfMonth (10, 20) -Retention 12
PS C:\> $Monthly | select *
RetentionFormat : Daily
DaysOfMonth     : {10, 20}
WeekNumber      : 
DaysOfWeek      : 
RetentionType   : Monthly
Retention       : 12
RetentionTimes  :
```

Perintah pertama membuat kebijakan penyimpanan yang menyimpan cadangan pada kesepuluh dan kesepuluh dari setiap bulan selama dua belas bulan.
Perintah menyimpan kebijakan penyimpanan di $Monthly penyimpanan.
Perintah kedua menampilkan konten $Monthly.

## PARAMETERS

### -DailyRetention
Mengindikasikan bahwa cmdlet ini membuat kebijakan penyimpanan Harian.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DailyRetentionParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfMonth
Menentukan hari-hari dalam bulan yang mengidentifikasi poin pemulihan mana yang dipertahankan Cadangan dan untuk berapa lama.
Nilai yang dapat diterima untuk parameter ini adalah: bilangan bulat dari 1 sampai 28 dan Terakhir.
Tentukan parameter ini jika Anda menentukan parameter *DailyRetention*, *MonthlyRetentionInDailyFormat*, dan *YearlyRetentionInDailyFormat.*

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: MonthlyRetentionInDailyFormatParamSet, YearlyRetentionInDailyFormatParamSet
Aliases:
Accepted values: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, Last

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Menentukan array hari dalam seminggu.
Hari-hari yang ditetapkan cmdlet ini untuk mengidentifikasi poin pemulihan mana yang dipertahankan Cadangan dan untuk berapa lama.
Nilai yang dapat diterima untuk parameter ini adalah:
- Senin 
- Selasa 
- Rabu 
- Kamis 
- Jumat 
- Sabtu 
- Minggu Tentukan parameter ini jika Anda menentukan parameter *WeeklyRetention*, *MonthlyRetentionInWeeklyFormat*, dan *YearlyRetentionInWeeklyFormat.*
Pastikan bahwa hari dalam seminggu Anda memilih untuk pencadangan dan untuk penyimpanan rata.
Misalnya, jika cadangan diatur untuk hari Sabtu, kebijakan penyimpanan juga harus menggunakan hari Sabtu.

```yaml
Type: System.String[]
Parameter Sets: WeeklyRetentionParamSet, MonthlyRetentionInWeeklyFormatParamSet, YearlyRetentionInWeeklyFormatParamSet
Aliases:
Accepted values: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthlyRetentionInDailyFormat
Mengindikasikan bahwa cmdlet ini membuat kebijakan Bulanan dalam format Harian.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MonthlyRetentionInDailyFormatParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthlyRetentionInWeeklyFormat
Mengindikasikan bahwa cmdlet ini membuat kebijakan Bulanan dalam format Mingguan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MonthlyRetentionInWeeklyFormatParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthsOfYear
Menentukan bulan mana dalam setahun memiliki poin pemulihan yang dipertahankan Cadangan setiap tahun.
Nilai yang dapat diterima untuk parameter ini adalah: nama bulan, seperti Januari atau Februari.

```yaml
Type: System.String[]
Parameter Sets: YearlyRetentionInDailyFormatParamSet, YearlyRetentionInWeeklyFormatParamSet
Aliases:
Accepted values: January, February, March, April, May, June, July, August, September, October, November, December

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Penyimpanan
Menentukan periode penyimpanan, dalam hari, bulan, atau tahun, di mana Cadangan menyimpan titik pencadangan.
Unit bergantung pada apakah cmdlet ini memilih opsi penyimpanan harian, bulanan, atau tahunan.
Misalnya, jika menentukan parameter *DailyRetention,* cmdlet akan menafsirkan parameter saat ini sebagai jumlah hari.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeklyRetention
Mengindikasikan bahwa cmdlet ini membuat kebijakan penyimpanan Mingguan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WeeklyRetentionParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeekNumber
Menentukan minggu dalam bulan yang mengidentifikasi poin pemulihan mana yang dipertahankan Cadangan dan untuk berapa lama.
Nilai yang dapat diterima untuk parameter ini adalah:
- Pertama 
- Detik 
- Ketiga 
- Fourth 
- Terakhir

```yaml
Type: System.String[]
Parameter Sets: MonthlyRetentionInWeeklyFormatParamSet, YearlyRetentionInWeeklyFormatParamSet
Aliases:
Accepted values: First, Second, Third, Fourth, Last

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -YearlyRetentionInDailyFormat
Mengindikasikan bahwa cmdlet ini membuat kebijakan penyimpanan Tahunan dalam format Harian.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: YearlyRetentionInDailyFormatParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -YearlyRetentionInWeeklyFormat
Mengindikasikan bahwa cmdlet ini membuat kebijakan penyimpanan Tahunan dalam format Mingguan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: YearlyRetentionInWeeklyFormatParamSet
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupRetentionPolicy

## CATATAN
* Tidak ada

## RELATED LINKS

[Enable-AzureRmBackupProtection](./Enable-AzureRmBackupProtection.md)

[New-AzureRmBackupProtectionPolicy](./New-AzureRmBackupProtectionPolicy.md)


