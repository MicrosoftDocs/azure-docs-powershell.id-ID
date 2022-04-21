---
external help file: ''
Module Name: Azs.Commerce.Admin
online version: https://docs.microsoft.com/powershell/module/azs.commerce.admin/get-azssubscriberusage
schema: 2.0.0
ms.openlocfilehash: e3254ab018abaf191b45327f8b8efa6d5b063f9d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142784008"
---
# Get-AzsSubscriberUsage

## SYNOPSIS
Mendapatkan kumpulan SubscriberUsageAggregates, yaitu UsageAggregates dari pengguna.

## SYNTAX

```
Get-AzsSubscriberUsage -ReportedEndTime <DateTime> -ReportedStartTime <DateTime> [-SubscriptionId <String[]>]
 [-AggregationGranularity <String>] [-ContinuationToken <String>] [-SubscriberId <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kumpulan SubscriberUsageAggregates, yaitu UsageAggregates dari pengguna.

## EXAMPLES

### Contoh 1: Dapatkan data penggunaan yang diagregasi menurut hari
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "2019/12/30" -ReportedEndTime "2019-12-31" -AggregationGranularity Daily
```

Dapatkan data penggunaan untuk seluruh hari dari 30 Des 2019 (dalam UTC) untuk semua penyewa di bawah penyedia yang diagregasi dari hari ke hari. Tentukan tanggal menggunakan format `mm/dd/yyyy`.  
Jika dipanggil sebagai administrator layanan, ini secara efektif memperlihatkan semua data penggunaan untuk setiap penyewa.

### Contoh 2: Dapatkan data penggunaan yang diagregasi per jam
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "12/30/2019 15:00" -ReportedEndTime "12/30/2019 16:00" -AggregationGranularity Hourly
```

Dapatkan data penggunaan antara 15.00 - 04.00 pada 30 Des 2019 (dalam UTC) yang diagregasi setiap jam. Tentukan tanggal dan waktu menggunakan format `mm/dd/yyyy HH:MM`.  
Demikian juga, jika disebut sebagai administrator layanan, ini secara efektif memperlihatkan semua data penggunaan untuk setiap penyewa.

## PARAMETERS

### -AggregationGranularity
Granularitas agregasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -ContinuationToken
Token kelanjutan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -ReportedEndTime
Waktu akhir yang dilaporkan (eksklusif).

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -ReportedStartTime
Waktu mulai yang dilaporkan (inklusif).

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -SubscriberId
Pengidentifikasi langganan penyewa.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -SubscriptionId
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False

```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Commerce.Models.Api20150601Preview.IUsageAggregate



## NOTES

## RELATED LINKS
