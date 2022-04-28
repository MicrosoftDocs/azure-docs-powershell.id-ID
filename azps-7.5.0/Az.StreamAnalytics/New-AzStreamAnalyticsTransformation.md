---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/new-azstreamanalyticstransformation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsTransformation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsTransformation.md
ms.openlocfilehash: 7f2d42facee66c54a45d6ca4abdf4631cca83e5b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144112925"
---
# New-AzStreamAnalyticsTransformation

## SYNOPSIS
Membuat transformasi atau mengganti transformasi yang sudah ada di bawah pekerjaan streaming yang ada.

## SYNTAX

```
New-AzStreamAnalyticsTransformation -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>] [-Query <String>]
 [-StreamingUnit <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat transformasi atau mengganti transformasi yang sudah ada di bawah pekerjaan streaming yang ada.

## EXAMPLES

### Contoh 1: Membuat atau mengganti transformasi dalam pekerjaan analisis aliran
```powershell
New-AzStreamAnalyticsTransformation -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh -Name tranf-01 -StreamingUnit 6 -Query "Select Id, Name from input-01"
```
```output
Name     Type                                                    ETag
----     ----                                                    ----
tranf-01 Microsoft.StreamAnalytics/streamingjobs/transformations ec0c7238-6bb2-4dad-b2cf-04c6a9285f4d
```

Perintah ini membuat transformasi dalam pekerjaan analisis aliran yang disebut.

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

### -IfNoneMatch
Atur ke '*' untuk memungkinkan transformasi baru dibuat, tetapi untuk mencegah pembaruan transformasi yang ada.
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

### -JobName
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

### -Name
Nama transformasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TransformationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kueri
Menentukan kueri yang akan dijalankan dalam pekerjaan streaming.
Anda dapat mempelajari selengkapnya tentang Bahasa Kueri Analisis Aliran (SAQL) di sini: https://msdn.microsoft.com/library/azure/dn834998 .
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
Nama tidak peka huruf besar/kecil.

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
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.ITransformation

## NOTES

ALIAS

## RELATED LINKS

