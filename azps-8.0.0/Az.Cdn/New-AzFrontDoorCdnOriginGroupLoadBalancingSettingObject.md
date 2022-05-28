---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnOriginGroupLoadBalancingSettingObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnOriginGroupLoadBalancingSettingObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnOriginGroupLoadBalancingSettingObject.md
ms.openlocfilehash: eb7c59725cc85a6cd277fbd63e3070b93b7c8c55
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145522615"
---
# New-AzFrontDoorCdnOriginGroupLoadBalancingSettingObject

## SYNOPSIS
Buat objek dalam memori untuk LoadBalancingSettingsParameters.

## SYNTAX

```
New-AzFrontDoorCdnOriginGroupLoadBalancingSettingObject [-AdditionalLatencyInMillisecond <Int32>]
 [-SampleSize <Int32>] [-SuccessfulSamplesRequired <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk LoadBalancingSettingsParameters.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -AdditionalLatencyInMillisecond
Latensi tambahan dalam milidetik untuk pemeriksaan jatuh ke dalam wadah latensi terendah.

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

### -SampleSize
Jumlah sampel yang perlu dipertimbangkan untuk keputusan penyeimbangan beban.

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

### -SuccessfulSamplesRequired
Jumlah sampel dalam periode sampel yang harus berhasil.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.LoadBalancingSettingsParameters

## NOTES

ALIAS

## RELATED LINKS

