---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnFrontDoorSecurityPolicyWebApplicationFirewallParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallParametersObject.md
ms.openlocfilehash: 6ff0a0194787c95e916d84de582660036dde2d46
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145505057"
---
# New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallParametersObject

## SYNOPSIS
Buat objek dalam memori untuk SecurityPolicyWebApplicationFirewallParameters.

## SYNTAX

```
New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallParametersObject
 [-Association <ISecurityPolicyWebApplicationFirewallAssociation[]>] [-WafPolicyId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk SecurityPolicyWebApplicationFirewallParameters.

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

### -Asosiasi
Asosiasi Waf.
Untuk membuat, lihat bagian CATATAN untuk properti ASSOCIATION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.ISecurityPolicyWebApplicationFirewallAssociation[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WafPolicyId
ID Sumber Daya.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.SecurityPolicyWebApplicationFirewallParameters

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ASOSIASI <ISecurityPolicyWebApplicationFirewallAssociation[]>: Asosiasi Waf.
  - `[Domain <IActivatedResourceReference[]>]`: Daftar domain.
    - `[Id <String>]`: ID Sumber Daya.
  - `[PatternsToMatch <String[]>]`: Daftar jalur

## RELATED LINKS

