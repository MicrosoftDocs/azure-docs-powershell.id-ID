---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/get-azstreamanalyticsjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsJob.md
ms.openlocfilehash: 796b4390468ba72915c18ad83f37b1cc9b2c9a60
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136550309"
---
# Get-AzStreamAnalyticsJob

## SYNOPSIS
Dapatkan detail tentang pekerjaan streaming tertentu.

## SYNTAX

### Daftar1 (Default)
```
Get-AzStreamAnalyticsJob [-SubscriptionId <String[]>] [-Expand <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzStreamAnalyticsJob -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-Expand <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzStreamAnalyticsJob -InputObject <IStreamAnalyticsIdentity> [-Expand <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzStreamAnalyticsJob -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Expand <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan detail tentang pekerjaan streaming tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang semua pekerjaan dalam langganan
```powershell
PS C:\> Get-AzStreamAnalyticsJob

Location        Name          Type                                    ETag
--------        ----          ----                                    ----
West Central US sajob-02-pwsh Microsoft.StreamAnalytics/streamingjobs
West Central US sajob-01-pwsh Microsoft.StreamAnalytics/streamingjobs
```

Perintah ini mengembalikan informasi tentang semua pekerjaan Stream Analytics dalam langganan Azure.

### Contoh 2: Mendapatkan informasi tentang semua pekerjaan dalam grup sumber daya
```powershell
PS C:\> Get-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test

Location        Name          Type                                    ETag
--------        ----          ----                                    ----
West Central US sajob-02-pwsh Microsoft.StreamAnalytics/streamingjobs
West Central US sajob-01-pwsh Microsoft.StreamAnalytics/streamingjobs
```

Perintah ini mengembalikan informasi tentang semua pekerjaan Stream Analytics dalam grup sumber daya.

### Contoh 3: Mendapatkan informasi tentang pekerjaan tertentu dalam grup sumber daya
```powershell
PS C:\> Get-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test -Name sajob-02-pwsh

Location        Name          Type                                    ETag
--------        ----          ----                                    ----
West Central US sajob-02-pwsh Microsoft.StreamAnalytics/streamingjobs ac26a506-a4cb-4a7d-9ec8-c3149b8589bd
```

Perintah ini mengembalikan informasi tentang pekerjaan Streaming Analytics StreamingJob dalam grup sumber daya.

### Contoh 4: Mendapatkan informasi tentang pekerjaan tertentu dalam grup sumber daya menurut saluran
```powershell
PS C:\> New-AzStreamAnalyticsJob -ResourceGroupName lucas-rg-test -Name sajob-02-pwsh -Location westcentralus -SkuName Standard | Get-AzStreamAnalyticsJob 

Location        Name          Type                                    ETag
--------        ----          ----                                    ----
West Central US sajob-02-pwsh Microsoft.StreamAnalytics/streamingjobs ac26a506-a4cb-4a7d-9ec8-c3149b8589bd
```

Perintah ini mengembalikan informasi tentang pekerjaan Streaming Analytics StreamingJob dalam grup sumber daya.

## PARAMETERS

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

### -Perluas
Parameter $expand kueri OData.
Ini adalah daftar properti streaming tambahan yang dipisahkan koma untuk disertakan dalam respons, di luar kumpulan default yang dikembalikan saat parameter ini absen.
Kumpulan default adalah semua properti pekerjaan streaming selain 'input', 'transformasi', 'output', dan 'fungsi'.

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama pekerjaan streaming.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IStreamingJob

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IStreamAnalyticsIdentity> : Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster.
  - `[FunctionName <String>]`: Nama fungsi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InputName <String>]`: Nama input.
  - `[JobName <String>]`: Nama pekerjaan streaming.
  - `[Location <String>]`: Kawasan untuk mengambil informasi kuota langganan. Anda dapat mencari tahu wilayah mana Azure Stream Analytics didukung di sini: https://azure.microsoft.com/en-us/regions/
  - `[OutputName <String>]`: Nama output.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[TransformationName <String>]`: Nama transformasi tersebut.

## RELATED LINKS

