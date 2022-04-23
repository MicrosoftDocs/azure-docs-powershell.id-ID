---
external help file: Microsoft.Azure.Commands.UsageAggregates.dll-Help.xml
Module Name: AzureRM.UsageAggregates
ms.assetid: 52B3ECCB-80E5-4E16-954A-B83D0BDC7E22
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.usageaggregates/get-usageaggregates
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/UsageAggregates/Commands.UsageAggregates/help/Get-UsageAggregates.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/UsageAggregates/Commands.UsageAggregates/help/Get-UsageAggregates.md
ms.openlocfilehash: cf7554cc287ff88dbcc2569a41d50c300a43ba75
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143212579"
---
# Get-UsageAggregates

## SYNOPSIS
Mendapatkan detail penggunaan langganan Azure yang dilaporkan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-UsageAggregates -ReportedStartTime <DateTime> -ReportedEndTime <DateTime>
 [-AggregationGranularity <AggregationGranularity>] [-ShowDetails <Boolean>] [-ContinuationToken <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-UsageAggregates** mendapatkan data penggunaan langganan Azure agregat oleh properti berikut: 
- Waktu mulai dan berakhir saat penggunaan dilaporkan.
- Presisi agregasi, baik harian atau per jam.
- Detail tingkat instans untuk beberapa contoh sumber daya yang sama.
Untuk hasil yang konsisten, data yang dikembalikan didasarkan pada kapan detail penggunaan dilaporkan oleh sumber daya Azure.
Untuk informasi selengkapnya, lihat Referensihttps://msdn.microsoft.com/library/azure/1ea5b323-54bb-423d-916f-190de96c6a3c API REST Tagihan Azure (https://msdn.microsoft.com/library/azure/1ea5b323-54bb-423d-916f-190de96c6a3c) di pustaka Jaringan Pengembang Microsoft.

## EXAMPLES

### Contoh 1: Mengambil data langganan
```
PS C:\>Get-UsageAggregates -ReportedStartTime "5/2/2015" -ReportedEndTime "5/5/2015"
```

Perintah ini mengambil data penggunaan yang dilaporkan untuk langganan antara 5/2/2015 dan 5/5/2015.

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
Untuk rangkaian hasil yang besar, respons diisi dengan menggunakan token kelanjutan.
Token kelanjutan berfungsi sebagai bookmark untuk kemajuan.
Jika Anda tidak menentukan parameter ini, data diambil dari awal hari atau jam yang ditentukan dalam *ReportedStartTime*.
Kami menyarankan Agar Anda mengikuti tautan berikutnya dalam respons ke halaman meskipun data.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportedEndTime
Menentukan waktu akhir yang dilaporkan ketika penggunaan sumber daya direkam dalam sistem tagihan Azure.
Azure adalah sistem terdistribusi, mencakup beberapa pusat data di seluruh dunia, sehingga terjadi penundaan antara kapan sumber daya benar-benar digunakan, yang merupakan waktu penggunaan sumber daya, dan ketika kejadian penggunaan mencapai sistem penagihan, yang merupakan waktu yang dilaporkan penggunaan sumber daya.
Untuk mendapatkan semua acara penggunaan untuk langganan yang dilaporkan untuk periode waktu tertentu, Anda membuat kueri menurut waktu yang dilaporkan.
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
Menentukan waktu mulai yang dilaporkan ketika penggunaan sumber daya direkam dalam sistem tagihan Azure.

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
Misalnya, jika Anda menjalankan tiga situs web, secara default Anda akan mendapatkan tiga item baris untuk konsumsi situs web.
Namun, ketika nilai $False, semua data untuk **langganan yang samaId**, **meterId**, **usageStartTime**, dan **usageEndTime** diciutkan menjadi item baris tunggal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commerce.UsageAggregates.Models.UsageAggregationGetResponse

## NOTES

## RELATED LINKS
