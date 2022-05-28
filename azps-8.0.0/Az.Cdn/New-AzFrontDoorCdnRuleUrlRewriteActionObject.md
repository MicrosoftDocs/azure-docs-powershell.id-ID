---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnRuleUrlRewriteActionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleUrlRewriteActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleUrlRewriteActionObject.md
ms.openlocfilehash: 860236436330ff6280989b587e29593b90e2f7e2
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145504094"
---
# New-AzFrontDoorCdnRuleUrlRewriteActionObject

## SYNOPSIS
Buat objek dalam memori untuk UrlRewriteAction.

## SYNTAX

```
New-AzFrontDoorCdnRuleUrlRewriteActionObject -Name <DeliveryRuleAction> -ParameterDestination <String>
 -ParameterSourcePattern <String> [-ParameterPreserveUnmatchedPath <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk UrlRewriteAction.

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

### -Name
Nama tindakan untuk aturan pengiriman.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.DeliveryRuleAction
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterDestination
Tentukan URL relatif tempat permintaan di atas akan ditulis ulang.

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

### -ParameterPreserveUnmatchedPath
Apakah akan mempertahankan jalur yang tidak cocok.
Nilai defaultnya adalah benar.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterSourcePattern
tentukan pola URI permintaan yang mengidentifikasi jenis permintaan yang mungkin ditulis ulang.
Jika nilai kosong, semua string dicocokkan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.UrlRewriteAction

## NOTES

ALIAS

## RELATED LINKS

