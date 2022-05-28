---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/invoke-azoperationalinsightsquery
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Invoke-AzOperationalInsightsQuery.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Invoke-AzOperationalInsightsQuery.md
ms.openlocfilehash: 35ac1d94e1aa37a8583dee0d43ed80975be8f573
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145617747"
---
# Invoke-AzOperationalInsightsQuery

## SYNOPSIS
Mengembalikan hasil pencarian berdasarkan parameter yang ditentukan.

## SYNTAX

### ByWorkspaceId (Default)
```
Invoke-AzOperationalInsightsQuery -WorkspaceId <String> -Query <String> [-Timespan <TimeSpan>] [-Wait <Int32>]
 [-IncludeRender] [-IncludeStatistics] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByWorkspaceObject
```
Invoke-AzOperationalInsightsQuery -Workspace <PSWorkspace> -Query <String> [-Timespan <TimeSpan>]
 [-Wait <Int32>] [-IncludeRender] [-IncludeStatistics] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Invoke-AzOperationalInsightsQuery** mengembalikan hasil pencarian berdasarkan parameter yang ditentukan.
Anda dapat mengakses status pencarian di properti Metadata dari objek yang dikembalikan.
Jika status tertunda, maka pencarian belum selesai, dan hasilnya akan berasal dari arsip.
Anda dapat mengambil hasil pencarian dari properti Nilai dari objek yang dikembalikan.
Silakan periksa detail batas kueri umum di sini: https://docs.microsoft.com/azure/azure-monitor/service-limits#log-queries-and-language.

## EXAMPLES

### Contoh 1: Mendapatkan hasil pencarian menggunakan kueri
```powershell
$queryResults = Invoke-AzOperationalInsightsQuery -WorkspaceId "63613592-b6f7-4c3d-a390-22ba13102111" -Query "union * | take 10"
$queryResults.Results
```

Setelah dipanggil, $queryResults.Results akan berisi semua baris yang dihasilkan dari kueri Anda.

### Contoh 2: Konversi $results. Hasil IEnumerable ke array
```powershell
$queryResults = Invoke-AzOperationalInsightsQuery -WorkspaceId "63613592-b6f7-4c3d-a390-22ba13102111" -Query "union * | take 10"
$resultsArray = [System.Linq.Enumerable]::ToArray($queryResults.Results)
```

Beberapa kueri dapat mengakibatkan himpunan data yang sangat besar dikembalikan. Karena itu, perilaku default cmdlet adalah mengembalikan IEnumerable untuk mengurangi biaya memori. Jika Anda lebih suka memiliki array hasil, Anda dapat menggunakan metode ekstensi LINQ Enumerable.ToArray() untuk mengonversi IEnumerable ke array.

### Contoh 3: Mendapatkan hasil pencarian menggunakan kueri melalui jangka waktu tertentu
```powershell
$queryResults = Invoke-AzOperationalInsightsQuery -WorkspaceId "63613592-b6f7-4c3d-a390-22ba13102111" -Query "union * | take 10" -Timespan (New-TimeSpan -Hours 24)
$queryResults.Results
```

Hasil dari kueri ini akan dibatasi hingga 24 jam terakhir.

### Contoh 4: Menyertakan statistik & render dalam hasil kueri
```powershell
$queryResults = Invoke-AzOperationalInsightsQuery -WorkspaceId "63613592-b6f7-4c3d-a390-22ba13102111" -Query "union * | take 10" -IncludeRender -IncludeStatistics
$queryResults.Results
...
$queryResults.Render
...
$queryResults.Statistics
...
```

Lihat [https://dev.loganalytics.io/documentation/Using-the-API/RequestOptions](https://dev.loganalytics.io/documentation/Using-the-API/RequestOptions) untuk detail tentang info render dan statistik.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
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

### -IncludeRender
Jika ditentukan, informasi penyajian untuk kueri metrik akan disertakan dalam respons.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeStatistics
Jika ditentukan, statistik kueri akan disertakan dalam respons.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kueri
Kueri yang akan dijalankan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rentang waktu
Rentang waktu untuk mengikat kueri.

```yaml
Type: System.Nullable`1[System.TimeSpan]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tunggu
Menempatkan batas atas pada jumlah waktu yang akan dihabiskan server untuk memproses kueri.
Melihat: https://dev.loganalytics.io/documentation/Using-the-API/Timeouts

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ruang kerja
Ruang kerja

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter Sets: ByWorkspaceObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkspaceId
ID ruang kerja.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSQueryResponse

## NOTES

## RELATED LINKS
