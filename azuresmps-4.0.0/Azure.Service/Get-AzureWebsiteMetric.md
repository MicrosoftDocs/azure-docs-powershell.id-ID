---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 717023DA-AA2D-4F1B-AE46-67ED75AA0D15
online version: ''
schema: 2.0.0
ms.openlocfilehash: 03a5a2ee26823b5e1feffca0e0831a8a7d885baf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143104481"
---
# Get-AzureWebsiteMetric

## SYNOPSIS
Mendapatkan metrik untuk situs web Azure dalam langganan saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureWebsiteMetric [-MetricNames <String[]>] [-StartDate <DateTime>] [-EndDate <DateTime>]
 [-TimeGrain <String>] [-InstanceDetails] [-SlotView] [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Get-AzureWebsiteMetric** mendapatkan metrik untuk situs web Azure dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan metrik selama tiga jam terakhir pada tingkat per instans untuk situs web
```
PS C:\> Get-AzureWebsiteMetric -Name "ContosoWebSite" -StartDate (get-date).AddHours(-3) -MetricNames "Requests" -InstanceDetails -SlotView -TimeGrain "PT1M" 
PS C:\> $metrics[1].Data Name : Requests 

Unit : Count 

StartTime : 8/11/2014 7:05:00 AM 

EndTime : 8/11/2014 5:06:01 PM 

TimeGrain : PT1M 
PrimaryAggregationType : Instance 
Values : {Time:8/11/2014 7:05:00 AM, Total:4, Min:, Max:, Time:8/11/2014 7:06:00 AM, Total:3, Min:, Max:, 
Time:8/11/2014 7:07:00 AM, Total:3, Min:, Max:, Time:8/11/2014 7:08:00 AM, Total:12, Min:, Max:...} 
$metrics[1].Data.Values | ft 
TimeCreated Total Minimum Maximum Count InstanceName 
----------- ----- ------- ------- ----- ------------ 
8/11/2014 7:05:00 AM 4 1 RD00155DC24599 
8/11/2014 7:06:00 AM 3 1 RD00155DC24599 
8/11/2014 7:07:00 AM 3 1 RD00155DC24589 
8/11/2014 7:08:00 AM 12 1 RD00155DC24599
8/11/2014 7:09:00 AM 37 1 RD00155DC24599 
8/11/2014 7:10:00 AM 9 1 RD00155DC24599
```

Perintah ini mendapatkan metrik selama tiga jam terakhir pada tingkat per instans untuk situs web.

## PARAMETERS

### -EndDate
Menentukan waktu, sebagai objek **DateTime** , untuk berhenti mendapatkan metrik.
Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** .
Untuk informasi selengkapnya, ketik .`Get-Help Get-Date`

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceDetails
Menunjukkan bahwa cmdlet ini menyertakan detail pada tingkat per instans.
Jika paket hosting web berjalan di dua komputer atau lebih, cmdlet ini mengembalikan metrik untuk setiap komputer.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetricNames
Menentukan array metrik untuk didapatkan.
Jika Anda tidak menentukan parameter ini, cmdlet mendapatkan semua metrik.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama situs web dalam langganan.
Parameter ini tidak mendukung karakter wildcard.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Slot
Menentukan lingkungan penyebaran layanan awan.
Nilai yang valid adalah: Produksi dan Pementasan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SlotView
Menunjukkan bahwa cmdlet ini mendapatkan metrik untuk nama host yang menerima lalu lintas di slot saat ini.
Jika swap terjadi selama periode waktu, metrik akan digabungkan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDate
Menentukan waktu, sebagai objek **DateTime** , untuk mulai mendapatkan metrik.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeGrain
Menentukan unit waktu untuk metrik.
Nilai yang valid adalah: 

- PT1M (Menit) 
- PT1H (Hour) 
- P1D (Hari)

Nilai defaultnya adalah PT1H.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Anda dapat meneruskan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Websites.Services.WebEntities.MetricResponse
Secara default, **Get-AzureWebsiteMetric** mengembalikan array objek **MetricResponse** .

## NOTES

## RELATED LINKS

[Dapatkan-AzureWebsite](./Get-AzureWebsite.md)


