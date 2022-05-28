---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnHealthProbeParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnHealthProbeParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnHealthProbeParametersObject.md
ms.openlocfilehash: 5b08e5fdaf8fe8050389b5bd8e1b919e7976695e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145536293"
---
# New-AzCdnHealthProbeParametersObject

## SYNOPSIS
Buat objek dalam memori untuk HealthProbeParameters.

## SYNTAX

```
New-AzCdnHealthProbeParametersObject [-ProbeIntervalInSecond <Int32>] [-ProbePath <String>]
 [-ProbeProtocol <ProbeProtocol>] [-ProbeRequestType <HealthProbeRequestType>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk HealthProbeParameters.

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

### -ProbeIntervalInSecond
Jumlah detik antara pemeriksaan kesehatan. Defaultnya adalah 240 detik.

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

### -ProbePath
Jalur relatif terhadap asal yang digunakan untuk menentukan kesehatan asal.

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

### -ProbeProtocol
Protokol yang digunakan untuk pemeriksaan kesehatan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.ProbeProtocol
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
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.HealthProbeRequestType
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.HealthProbeParameters

## NOTES

ALIAS

## RELATED LINKS

