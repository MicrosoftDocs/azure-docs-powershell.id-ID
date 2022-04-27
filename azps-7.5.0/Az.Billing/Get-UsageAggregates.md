---
external help file: Microsoft.Azure.PowerShell.Cmdlets.UsageAggregates.dll-Help.xml
Module Name: Az.Billing
ms.assetid: 52B3ECCB-80E5-4E16-954A-B83D0BDC7E22
online version: https://docs.microsoft.com/powershell/module/az.billing/get-usageaggregates
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-UsageAggregates.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-UsageAggregates.md
ms.openlocfilehash: 5d3a4edeaabe71225b7bf4ea83ad11a58f156899
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144207758"
---
# Get-UsageAggregates

## SYNOPSIS
Mendapatkan detail penggunaan langganan Azure yang dilaporkan.

## SYNTAX

```
Get-UsageAggregates -ReportedStartTime <DateTime> -ReportedEndTime <DateTime>
 [-AggregationGranularity <AggregationGranularity>] [-ShowDetails <Boolean>] [-ContinuationToken <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-UsageAggregates** mendapatkan data penggunaan langganan Azure agregat dengan properti berikut: 
- Waktu mulai dan berakhir saat penggunaan dilaporkan.
- Presisi agregasi, baik harian atau per jam.
- Detail tingkat instans untuk beberapa instans sumber daya yang sama.
Untuk hasil yang konsisten, data yang dikembalikan didasarkan pada kapan detail penggunaan dilaporkan oleh sumber daya Azure.
Untuk informasi selengkapnya, lihat Referensihttps://msdn.microsoft.com/library/azure/1ea5b323-54bb-423d-916f-190de96c6a3c REST API Penagihan Azure (https://msdn.microsoft.com/library/azure/1ea5b323-54bb-423d-916f-190de96c6a3c) di pustaka Microsoft Developer Network.

## EXAMPLES

### Contoh 1: Mengambil data langganan
```powershell
Get-UsageAggregates -ReportedStartTime "5/2/2015" -ReportedEndTime "5/5/2015"
```

Perintah ini mengambil data penggunaan yang dilaporkan untuk langganan antara 2/5/2015 dan 5/5/2015.

## PARAMETERS

### -AggregationGranularity
Menentukan presisi agregasi data.
Nilai yang valid adalah: Harian dan Per Jam.
Nilai defaultnya adalah Harian.

```yaml
Type: Microsoft.Azure.Commerce.UsageAggregates.Models.AggregationGranularity
Parameter Sets: (All)
Aliases:
Accepted values: Daily, Hourly

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContinuationToken
Menentukan token kelanjutan yang diambil dari isi respons dalam panggilan sebelumnya.
Untuk kumpulan hasil besar, respons di-paged dengan menggunakan token kelanjutan.
Token kelanjutan berfungsi sebagai bookmark untuk kemajuan.
Jika Anda tidak menentukan parameter ini, data diambil dari awal hari atau jam yang ditentukan dalam *ReportedStartTime*.
Kami menyarankan agar Anda mengikuti tautan berikutnya dalam respons ke halaman melalui data.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportedEndTime
Menentukan waktu akhir yang dilaporkan ketika penggunaan sumber daya dicatat dalam sistem penagihan Azure.
Azure adalah sistem terdistribusi, yang mencakup beberapa pusat data di seluruh dunia, sehingga ada penundaan antara kapan sumber daya benar-benar digunakan, yang merupakan waktu penggunaan sumber daya, dan ketika peristiwa penggunaan mencapai sistem penagihan, yang merupakan waktu yang dilaporkan penggunaan sumber daya.
Untuk mendapatkan semua peristiwa penggunaan untuk langganan yang dilaporkan untuk jangka waktu tertentu, Anda mengkueri berdasarkan waktu yang dilaporkan.
Meskipun Anda mengkueri berdasarkan waktu yang dilaporkan, cmdlet menggabungkan data respons berdasarkan waktu penggunaan sumber daya.
Data penggunaan sumber daya adalah pivot yang berguna untuk menganalisis data.

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
Menentukan waktu mulai yang dilaporkan ketika penggunaan sumber daya dicatat dalam sistem penagihan Azure.

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

### -ShowDetails
Menunjukkan apakah cmdlet ini mengembalikan detail tingkat instans dengan data penggunaan.
Nilai defaultnya adalah $True.
Jika $False, layanan menggabungkan hasil di sisi server, dan karenanya mengembalikan lebih sedikit grup agregat.
Misalnya, jika Anda menjalankan tiga situs web, secara default Anda akan mendapatkan tiga item baris untuk konsumsi situs web.
Namun, ketika nilai $False, semua data untuk **subscriptionId**, **meterId**, **usageStartTime**, dan **usageEndTime** yang sama diciutkan menjadi satu item baris.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commerce.UsageAggregates.Models.UsageAggregationGetResponse

## NOTES

## RELATED LINKS
