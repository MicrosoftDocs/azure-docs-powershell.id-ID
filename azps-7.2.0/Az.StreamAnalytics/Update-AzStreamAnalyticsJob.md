---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/update-azstreamanalyticsjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Update-AzStreamAnalyticsJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Update-AzStreamAnalyticsJob.md
ms.openlocfilehash: 483f2d3011705681326c4edc80a6e12bb25ec8f4
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138259180"
---
# Update-AzStreamAnalyticsJob

## SYNOPSIS
Membuat pekerjaan streaming atau mengganti pekerjaan streaming yang sudah ada.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzStreamAnalyticsJob -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-IfMatch <String>] [-IfNoneMatch <String>] [-ClusterId <String>] [-DataLocale <String>]
 [-EventsLateArrivalMaxDelayInSecond <Int32>] [-EventsOutOfOrderMaxDelayInSecond <Int32>]
 [-EventsOutOfOrderPolicy <EventsOutOfOrderPolicy>] [-OutputErrorPolicy <OutputErrorPolicy>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzStreamAnalyticsJob -InputObject <IStreamAnalyticsIdentity> [-IfMatch <String>]
 [-IfNoneMatch <String>] [-ClusterId <String>] [-DataLocale <String>]
 [-EventsLateArrivalMaxDelayInSecond <Int32>] [-EventsOutOfOrderMaxDelayInSecond <Int32>]
 [-EventsOutOfOrderPolicy <EventsOutOfOrderPolicy>] [-OutputErrorPolicy <OutputErrorPolicy>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat pekerjaan streaming atau mengganti pekerjaan streaming yang sudah ada.

## EXAMPLES

### Contoh 1: Memperbarui pekerjaan analitik streaming
```powershell
PS C:\> Update-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test -Name sajob-01-pwsh -EventsLateArrivalMaxDelayInSecond 13 -EventsOutOfOrderMaxDelayInSecond 21

Location        Name          Type                                    ETag
--------        ----          ----                                    ----
West Central US sajob-01-pwsh Microsoft.StreamAnalytics/streamingjobs a5eb4626-ab6c-45bb-be0d-86593ad92021
```

Perintah ini memperbarui pekerjaan analitik streaming.

### Contoh 2: Memperbarui pekerjaan analitik streaming menurut saluran
```powershell
PS C:\> Get-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test -Name sajob-01-pwsh | Update-AzStreamAnalyticsJob -EventsLateArrivalMaxDelayInSecond 13 -EventsOutOfOrderMaxDelayInSecond 21

Location        Name          Type                                    ETag
--------        ----          ----                                    ----
West Central US sajob-01-pwsh Microsoft.StreamAnalytics/streamingjobs c1aa3d2a-1784-4586-926f-df5bfd084e31
```

Perintah ini memperbarui pekerjaan analitik streaming menurut saluran.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -DataLocale
Lokal data pekerjaan analitik streaming.
Nilai harus merupakan nama .NET Culture yang didukung dari kumpulan tersebut https://msdn.microsoft.com/en-us/library/system.globalization.culturetypes(v=vs.110).aspx.
Default ke 'en-US' jika tidak ada yang ditentukan.

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
Penundaan maksimum yang dapat dilerangkan dalam detik ketika acara yang datang terlambat dapat disertakan.
Rentang yang didukung adalah -1 hingga 1814399 (20.23.59.59 hari) dan -1 digunakan untuk menentukan tunggu tanpa batas.
Jika properti absen, properti diinterpretasikan memiliki nilai -1.

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
Penundaan maksimum yang dapat dilerangkan dalam detik ketika kejadian di luar urutan dapat disesuaikan agar sesuai urutan.

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
Menunjukkan kebijakan untuk diterapkan pada kejadian yang tidak sesuai urutan di streaming kejadian input.

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
ETag pekerjaan streaming.
Menghilangkan nilai ini agar selalu menimpa kumpulan data saat ini.
Tentukan nilai ETag yang terakhir dilihat untuk mencegah secara tidak sengaja menimpa perubahan bersama.

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
Atur ke '*' untuk memperbolehkan pekerjaan streaming baru dibuat, tapi untuk mencegah memperbarui kumpulan rekaman yang sudah ada.
Nilai lainnya akan menghasilkan respons Gagal Pra-Kondisi 412.

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
Parameter Sets: UpdateViaIdentityExpanded
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
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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
Menunjukkan kebijakan untuk diterapkan pada kejadian yang tiba di output dan tidak bisa ditulis ke penyimpanan eksternal karena dibentuk (nilai kolom yang hilang, nilai kolom dari tipe atau ukuran yang salah).

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
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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
Parameter Sets: UpdateExpanded
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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IStreamingJob

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IStreamAnalyticsIdentity>: Parameter Identitas
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

