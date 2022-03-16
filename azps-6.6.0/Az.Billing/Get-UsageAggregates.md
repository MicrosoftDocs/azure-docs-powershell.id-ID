---
external help file: Microsoft.Azure.PowerShell.Cmdlets.UsageAggregates.dll-Help.xml
Module Name: Az.Billing
ms.assetid: 52B3ECCB-80E5-4E16-954A-B83D0BDC7E22
online version: https://docs.microsoft.com/powershell/module/az.billing/get-usageaggregates
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-UsageAggregates.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-UsageAggregates.md
ms.openlocfilehash: ceb83d688dcbefbaecbb1f0519ea6d5b9eb5ba3f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139979745"
---
# Get-UsageAggregates

## SYNOPSIS
Dapatkan detail penggunaan langganan Azure yang dilaporkan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.billing/get-usageaggregates) untuk informasi terkini.

## SYNTAX

```
Get-UsageAggregates -ReportedStartTime <DateTime> -ReportedEndTime <DateTime>
 [-AggregationGranularity <AggregationGranularity>] [-ShowDetails <Boolean>] [-ContinuationToken <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-UsageAggregates** mendapatkan agregat data penggunaan langganan Azure dengan properti berikut: 
- Waktu mulai dan berakhirnya laporan penggunaan.
- Presisi agregasi, baik harian atau per jam.
- Detail tingkat contoh untuk beberapa contoh dari sumber daya yang sama.
Untuk hasil yang konsisten, data yang dikembalikan didasarkan pada waktu detail penggunaan dilaporkan oleh sumber daya Azure.
Untuk informasi selengkapnya, lihat Referensi API REST Tagihanhttps://msdn.microsoft.com/library/azure/1ea5b323-54bb-423d-916f-190de96c6a3c Azure (https://msdn.microsoft.com/library/azure/1ea5b323-54bb-423d-916f-190de96c6a3c) di pustaka Jaringan Pengembang Microsoft.

## EXAMPLES

### Contoh 1: Mengambil data langganan
```
PS C:\>Get-UsageAggregates -ReportedStartTime "5/2/2015" -ReportedEndTime "5/5/2015"
```

Perintah ini mengambil data penggunaan yang dilaporkan untuk langganan antara tanggal 5/2/2015 dan 5/5/2015.

## PARAMETERS

### -AggregationGranularity
Menentukan presisi agregasi data.
Nilai valid adalah: Harian dan Per jam.
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
Menentukan token lanjutan yang diambil dari badan respons dalam panggilan sebelumnya.
Untuk kumpulan hasil yang besar, respons di paged dengan menggunakan token kelanjutan.
Token kelanjutan berfungsi sebagai bookmark untuk kemajuan.
Jika Anda tidak menentukan parameter ini, data diambil dari awal hari atau jam yang ditentukan di *ReportedStartTime*.
Kami menyarankan agar Anda mengikuti link berikutnya dalam respons ke halaman meskipun data.

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
Menentukan waktu akhir yang dilaporkan ketika penggunaan sumber daya dicatat dalam sistem tagihan Azure.
Azure adalah sistem terdistribusi yang mencakup beberapa pusat data di seluruh dunia, sehingga ada penundaan antara kapan sumber daya tersebut benar-benar digunakan, yaitu waktu penggunaan sumber daya, dan waktu penggunaan mencapai sistem tagihan, yakni waktu penggunaan sumber daya yang dilaporkan.
Untuk mendapatkan semua kejadian penggunaan untuk langganan yang dilaporkan selama periode waktu, Anda membuat kueri menurut waktu yang dilaporkan.
Meskipun Anda membuat kueri menurut waktu yang dilaporkan, cmdlet menggabungkan data respons menurut waktu penggunaan sumber daya.
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
Menentukan waktu mulai yang dilaporkan ketika penggunaan sumber daya dicatat dalam sistem tagihan Azure.

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
Jika $False, layanan menggabungkan hasil di sisi server, dan oleh karena itu mengembalikan lebih sedikit grup agregat.
Misalnya, jika Anda menjalankan tiga situs web, secara default Anda akan mendapatkan tiga item baris untuk penggunaan situs web.
Namun, ketika nilai diciutkan ke dalam $False, semua data untuk **subscriptionId**, **meterId**, **usageStartTime**, dan **usageEndTime** diciutkan menjadi satu baris item.

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

## CATATAN

## RELATED LINKS
