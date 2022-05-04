---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/new-azstreamanalyticsjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsJob.md
ms.openlocfilehash: 0b91930b3262a27cf5c032df4569ac121cb3f66b
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144588456"
---
# New-AzStreamAnalyticsJob

## SYNOPSIS
Membuat pekerjaan streaming atau mengganti pekerjaan streaming yang sudah ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.streamanalytics/new-azstreamanalyticsjob) untuk informasi terbaru.

## SYNTAX

```
New-AzStreamAnalyticsJob -Name <String> -ResourceGroupName <String> -Location <String>
 -SkuName <StreamingJobSkuName> [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>]
 [-ClusterId <String>] [-CompatibilityLevel <CompatibilityLevel>] [-DataLocale <String>]
 [-EventsLateArrivalMaxDelayInSecond <Int32>] [-EventsOutOfOrderMaxDelayInSecond <Int32>]
 [-EventsOutOfOrderPolicy <EventsOutOfOrderPolicy>] [-OutputErrorPolicy <OutputErrorPolicy>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat pekerjaan streaming atau mengganti pekerjaan streaming yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat pekerjaan analisis aliran
```powershell
New-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test -Name sajob-02-pwsh -Location westcentralus -SkuName Standard
```
```output
Location        Name          Type                                    ETag
--------        ----          ----                                    ----
West Central US sajob-02-pwsh Microsoft.StreamAnalytics/streamingjobs a687c464-82ce-45cc-b88a-1f72ba2b1dc2
```

Perintah ini membuat pekerjaan analisis aliran.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -ClusterId
Id sumber daya kluster.

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

### -CompatibilityLevel
Mengontrol perilaku runtime tertentu dari pekerjaan streaming.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Support.CompatibilityLevel
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataLocale
Lokal data dari pekerjaan analitik stream.
Nilai harus menjadi nama .NET Culture yang didukung dari set https://msdn.microsoft.com/en-us/library/system.globalization.culturetypes(v=vs.110).aspx.
Tentukan default ke 'en-US' jika tidak ditentukan.

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

### -EventsLateArrivalMaxDelayInSecond
Maksimum penundaan yang dapat ditoleransi dalam hitungan detik agar peristiwa yang datang terlambat dapat disertakan.
Rentang yang didukung adalah -1 hingga 1814399 (20.23:59:59 hari) dan -1 digunakan untuk menentukan tunggu tanpa batas waktu.
Jika properti tidak ada, peristiwa dianggap memiliki nilai -1.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventsOutOfOrderMaxDelayInSecond
Penundaan maksimum yang dapat ditoleransi dalam hitungan detik agar peristiwa yang keluar dari urutan dapat disesuaikan kembali ke dalam urutan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventsOutOfOrderPolicy
Menandakan kebijakan untuk diterapkan ke peristiwa yang sampai di luar urutan dalam aliran peristiwa input.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Support.EventsOutOfOrderPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IfMatch
ETag dari pekerjaan streaming.
Hilangkan nilai ini untuk selalu menimpa kumpulan catatan saat ini.
Tentukan nilai ETag yang terakhir dilihat untuk mencegah penimpaan perubahan bersamaan secara tidak sengaja.

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

### -IfNoneMatch
Atur ke '*' untuk mengizinkan pekerjaan streaming baru dibuat, tetapi untuk mencegah pembaruan kumpulan catatan yang ada.
Nilai lain akan menghasilkan respons 412 Pra-kondisi Gagal.

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

### -Lokasi
Lokasi geografis tempat sumber daya berada

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

### -Name
Nama pekerjaan streaming.

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

### -NoWait
Jalankan perintah secara asinkron

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

### -OutputErrorPolicy
Menandakan kebijakan untuk diterapkan ke peristiwa yang mencapai output dan tidak dapat ditulis ke penyimpanan eksternal karena cacat (nilai kolom hilang, nilai kolom dengan jenis atau ukuran yang salah).

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Support.OutputErrorPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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

### -SkuName
Nama SKUnya.
Diperlukan pada permintaan PUT (CreateOrReplace).

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Support.StreamingJobSkuName
Parameter Sets: (All)
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
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IStreamingJob

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IStreamingJob

## NOTES

ALIAS

## RELATED LINKS

