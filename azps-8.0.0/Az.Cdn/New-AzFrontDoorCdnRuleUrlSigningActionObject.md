---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnRuleUrlSigningActionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleUrlSigningActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleUrlSigningActionObject.md
ms.openlocfilehash: 09c7c8427bb67eae04c49445d10795aab9a17b2d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145618970"
---
# New-AzFrontDoorCdnRuleUrlSigningActionObject

## SYNOPSIS
Buat objek dalam memori untuk UrlSigningAction.

## SYNTAX

```
New-AzFrontDoorCdnRuleUrlSigningActionObject -Name <DeliveryRuleAction> [-ParameterAlgorithm <Algorithm>]
 [-ParameterNameOverride <IUrlSigningParamIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk UrlSigningAction.

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

### -ParameterAlgorithm
Algoritma yang digunakan untuk penandatanganan URL.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.Algorithm
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterNameOverride
Menentukan parameter string kueri mana di url yang akan dipertimbangkan untuk kedaluwarsa, id kunci, dll. . Untuk membuat, lihat bagian CATATAN untuk properti PARAMETERNAMEOVERRIDE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IUrlSigningParamIdentifier[]
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.UrlSigningAction

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PARAMETERNAMEOVERRIDE <IUrlSigningParamIdentifier[]>: Menentukan parameter string kueri mana di url yang akan dipertimbangkan untuk kedaluwarsa, id kunci, dll. .
  - `ParamIndicator <ParamIndicator>`: Menunjukkan tujuan parameter
  - `ParamName <String>`: Nama parameter

## RELATED LINKS

