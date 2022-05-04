---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnorigingroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOriginGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOriginGroup.md
ms.openlocfilehash: 9513fdfb3a1c607b654b59c98e2fc8f281fc452d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144595293"
---
# New-AzFrontDoorCdnOriginGroup

## SYNOPSIS
Membuat grup asal.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cdn/new-azfrontdoorcdnorigingroup) untuk informasi terbaru.

## SYNTAX

```
New-AzFrontDoorCdnOriginGroup [-AdditionalLatencyInMillisecond <Int32>] -OriginGroupName <String>
 [-ProbeIntervalInSeconds <Int32>] [-ProbePath <String>] [-ProbeProtocol <String>] [-ProbeRequestType <String>]
 -ProfileName <String> -ResourceGroupName <String> [-SampleSize <Int32>] [-SuccessfulSamplesRequired <Int32>]
 [-TrafficRestorationTimeToHealedOrNewEndpointsInMinutes <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat grup asal.

## EXAMPLES

### Contoh 1
```powershell
New-AzFrontDoorCdnOriginGroup -OriginGroupName $originGroupName -ProfileName $profileName -ResourceGroupName $resourceGroupName
```

Membuat grup asal.

## PARAMETERS

### -AdditionalLatencyInMillisecond
Latensi tambahan dalam milidetik untuk pemeriksaan jatuh ke dalam wadah latensi terendah.

```yaml
Type: Int32
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginGroupName
Nama grup asal Azure Front Door.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeIntervalInSeconds
Jumlah detik antara pemeriksaan kesehatan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbePath
Jalur relatif terhadap asal yang digunakan untuk menentukan kesehatan asal.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeProtocol
Protokol yang digunakan untuk pemeriksaan kesehatan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeRequestType
Jenis permintaan pemeriksaan kesehatan yang dibuat.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil Azure Front Door.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SampleSize
Jumlah sampel yang perlu dipertimbangkan untuk keputusan penyeimbangan beban.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuccessfulSamplesRequired
Jumlah sampel dalam periode sampel yang harus berhasil.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficRestorationTimeToHealedOrNewEndpointsInMinutes
Waktu dalam menit untuk mengalihkan lalu lintas ke titik akhir secara bertahap ketika titik akhir yang tidak sehat sehat atau titik akhir baru ditambahkan.

```yaml
Type: Int32
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
Type: SwitchParameter
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
Type: SwitchParameter
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdOriginGroup

## NOTES

## RELATED LINKS
