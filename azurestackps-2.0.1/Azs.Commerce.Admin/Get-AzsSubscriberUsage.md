---
external help file: ''
Module Name: Azs.Commerce.Admin
online version: https://docs.microsoft.com/powershell/module/azs.commerce.admin/get-azssubscriberusage
schema: 2.0.0
ms.openlocfilehash: 9eed3f6f2a4d07bd48136c50ec173f801b30c928
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142379789"
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
Get-AzsSubscriberUsage -ReportedStartTime "2019-12-30T00:00:00Z" -ReportedEndTime "2019-12-31T00:00:00Z" -AggregationGranularity Daily
```

Dapatkan data penggunaan untuk seluruh hari dari 30 Des 2019 (dalam UTC) untuk semua penyewa di bawah penyedia yang diagregasi dari hari ke hari.
ReportedStartTime dan ReportedEndTime harus dibulatkan menjadi hari.
Jika dipanggil sebagai administrator layanan, ini secara efektif memperlihatkan semua data penggunaan untuk setiap penyewa.

### Contoh 2: Dapatkan data penggunaan yang diagregasi per jam
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "2019-12-30T00:00:00Z" -ReportedEndTime "2019-12-30T02:00:00Z" -AggregationGranularity Hourly
```

Dapatkan data penggunaan antara 12am - 2am pada 30 Des 2019 (dalam UTC) yang diagregasi setiap jam.
ReportedStartTime dan ReportedEndTime harus dibulatkan ke jam.
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



## CATATAN

## RELATED LINKS

