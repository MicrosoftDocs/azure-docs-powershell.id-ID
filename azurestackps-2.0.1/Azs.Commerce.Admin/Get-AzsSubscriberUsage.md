---
external help file: ''
Module Name: Azs.Commerce.Admin
online version: https://docs.microsoft.com/powershell/module/azs.commerce.admin/get-azssubscriberusage
schema: 2.0.0
ms.openlocfilehash: 596815ffdb3f5a241259b1011bc67d4311c882b9489c374a72efa284323122eb
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416818"
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

### Contoh 1: Dapatkan data penggunaan diagregasi menurut hari
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "2019-12-30T00:00:00Z" -ReportedEndTime "2019-12-31T00:00:00Z" -AggregationGranularity Daily
```

Dapatkan data penggunaan untuk seluruh hari ke-30 Des 2019 (dalam UTC) untuk semua penyewa di bawah penyedia yang diagregatkan menurut hari.
ReportedStartTime dan ReportedEndTime harus dibulatkan ke hari.
Jika dipanggil sebagai administrator layanan, ini secara efektif memperlihatkan semua data penggunaan untuk setiap penyewa.

### Contoh 2: Dapatkan data penggunaan diagregasi menurut jam
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "2019-12-30T00:00:00Z" -ReportedEndTime "2019-12-30T02:00:00Z" -AggregationGranularity Hourly
```

Dapatkan data penggunaan antara pukul 00.00 - 02.00 pada tanggal 30 Des 2019 (dalam UTC) yang diagregatkan menurut jam.
ReportedStartTime dan ReportedEndTime harus dibulatkan menjadi jam.
Demikian pula, jika dipanggil sebagai administrator layanan, ini secara efektif memperlihatkan semua data penggunaan untuk setiap penyewa.

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
Waktu selesai yang dilaporkan (eksklusif).

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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure Anda. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Commerce.Models.Api20150601Preview.IUsageAggregate



## CATATAN

## RELATED LINKS

