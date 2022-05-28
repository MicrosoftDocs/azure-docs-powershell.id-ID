---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/update-azstreamanalyticstransformation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Update-AzStreamAnalyticsTransformation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Update-AzStreamAnalyticsTransformation.md
ms.openlocfilehash: daa53aa07bb970a2a1ed9e79f2c5dfcdf156b023
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145529878"
---
# Update-AzStreamAnalyticsTransformation

## SYNOPSIS
Memperbarui transformasi yang ada di bawah pekerjaan streaming yang ada.
Ini dapat digunakan untuk memperbarui sebagian (yaitu.
memperbarui satu atau dua properti) transformasi tanpa memengaruhi sisa definisi pekerjaan atau transformasi.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzStreamAnalyticsTransformation -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-IfMatch <String>] [-Query <String>] [-StreamingUnit <Int32>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzStreamAnalyticsTransformation -InputObject <IStreamAnalyticsIdentity> [-IfMatch <String>]
 [-Query <String>] [-StreamingUnit <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Memperbarui transformasi yang ada di bawah pekerjaan streaming yang ada.
Ini dapat digunakan untuk memperbarui sebagian (yaitu.
memperbarui satu atau dua properti) transformasi tanpa memengaruhi sisa definisi pekerjaan atau transformasi.

## EXAMPLES

### Contoh 1: Memperbarui transformasi dalam pekerjaan analisis aliran
```powershell
Update-AzStreamAnalyticsTransformation -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh -Name tranf-01 -StreamingUnit 1
```
```output
Name     Type                                                    ETag
----     ----                                                    ----
tranf-01 Microsoft.StreamAnalytics/streamingjobs/transformations 6d100b9a-91c1-4b27-ae62-68c55635154f
```

Perintah ini memperbarui transformasi dalam pekerjaan analisis aliran.

### Contoh 2: Memperbarui transformasi dalam pekerjaan analisis aliran menurut alur
```powershell
Get-AzStreamAnalyticsTransformation -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh -Name tranf-01 | Update-AzStreamAnalyticsTransformation -StreamingUnit 1
```
```output
Name     Type                                                    ETag
----     ----                                                    ----
tranf-01 Microsoft.StreamAnalytics/streamingjobs/transformations 3d6570c5-6e0f-4ec6-b242-ba9e161c3e01
```

Perintah ini memperbarui transformasi dalam pekerjaan analisis aliran berdasarkan alur.

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

### -IfMatch
ETag transformasi.
Hilangkan nilai ini untuk selalu menimpa transformasi saat ini.
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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -JobName
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

### -Name
Nama transformasi.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: TransformationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kueri
Menentukan kueri yang akan dijalankan dalam pekerjaan streaming.
Anda dapat mempelajari selengkapnya tentang Bahasa Kueri Azure Stream Analytics (SAQL) di sini: https://msdn.microsoft.com/library/azure/dn834998 .
Diperlukan pada permintaan PUT (CreateOrReplace).

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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

### -StreamingUnit
Menentukan jumlah unit streaming yang digunakan pekerjaan streaming.

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

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.ITransformation

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IStreamAnalyticsIdentity>: Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster.
  - `[FunctionName <String>]`: Nama fungsi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InputName <String>]`: Nama input.
  - `[JobName <String>]`: Nama dari pekerjaan streaming.
  - `[Location <String>]`: Wilayah tempat untuk mengambil informasi kuota langganan. Anda dapat mengetahui wilayah mana yang didukung Azure Stream Analytics di sini: https://azure.microsoft.com/en-us/regions/
  - `[OutputName <String>]`: Nama output.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[TransformationName <String>]`: Nama transformasi.

## RELATED LINKS

