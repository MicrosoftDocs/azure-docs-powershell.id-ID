---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/start-azstreamanalyticsjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Start-AzStreamAnalyticsJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Start-AzStreamAnalyticsJob.md
ms.openlocfilehash: 1e74c19def6b049ce3d09940a3be589a2ea89ec5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142171178"
---
# Start-AzStreamAnalyticsJob

## SYNOPSIS
Memulai pekerjaan streaming.
Setelah pekerjaan dimulai, proses akan mulai memproses kejadian input dan menghasilkan output.

## SYNTAX

### StartExpanded (Default)
```
Start-AzStreamAnalyticsJob -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-OutputStartMode <OutputStartMode>] [-OutputStartTime <DateTime>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### StartViaIdentityExpanded
```
Start-AzStreamAnalyticsJob -InputObject <IStreamAnalyticsIdentity> [-OutputStartMode <OutputStartMode>]
 [-OutputStartTime <DateTime>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memulai pekerjaan streaming.
Setelah pekerjaan dimulai, proses akan mulai memproses kejadian input dan menghasilkan output.

## EXAMPLES

### Contoh 1: Memulai pekerjaan Stream Analytics
```powershell
Start-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test -Name sajob-01-portal

```

Perintah ini memulai pekerjaan StreamingJob.

### Contoh 2: Memulai pekerjaan Stream Analytics menurut pipeline
```powershell
Get-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test -Name sajob-01-portal | Start-AzStreamAnalyticsJob

```

Perintah ini memulai pekerjaan StreamingJob menurut saluran.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity
Parameter Sets: StartViaIdentityExpanded
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
Parameter Sets: StartExpanded
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

### -OutputStartMode
Value may be JobStartTime, CustomTime, or LastOutputEventTime to indicate whether the starting point of the output event stream should start whenever the job is started, start at a custom user time stamp specified via outputStartTime property, or start from the last event output time.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Support.OutputStartMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputStartTime
Nilai adalah stempel waktu yang diformat ISO-8601 yang menunjukkan titik awal aliran kejadian output, atau null untuk menunjukkan bahwa streaming kejadian output akan dimulai setiap kali pekerjaan streaming dimulai.
Properti ini harus memiliki nilai jika outputStartMode diatur ke CustomTime.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: StartExpanded
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
Parameter Sets: StartExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### System.Boolean

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
  - `[Location <String>]`: Kawasan tempat untuk mengambil informasi kuota langganan. Anda dapat mengetahui kawasan mana Azure Stream Analytics didukung di sini: https://azure.microsoft.com/en-us/regions/
  - `[OutputName <String>]`: Nama output.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[TransformationName <String>]`: Nama transformasi.

## RELATED LINKS

