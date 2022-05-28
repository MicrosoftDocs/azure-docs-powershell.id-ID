---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallAssociationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallAssociationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallAssociationObject.md
ms.openlocfilehash: 920d27a8b92cc7fcf2ac89b77a2881ac55f0ed36
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145561664"
---
# New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallAssociationObject

## SYNOPSIS
Buat objek dalam memori untuk SecurityPolicyWebApplicationFirewallAssociation.

## SYNTAX

```
New-AzFrontDoorCdnSecurityPolicyWebApplicationFirewallAssociationObject
 [-Domain <IActivatedResourceReference[]>] [-PatternsToMatch <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk SecurityPolicyWebApplicationFirewallAssociation.

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

### -Domain
Daftar domain.
Untuk membuat, lihat bagian CATATAN untuk properti DOMAIN dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IActivatedResourceReference[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PatternsToMatch
Daftar jalur.

```yaml
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.SecurityPolicyWebApplicationFirewallAssociation

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DOMAIN <IActivatedResourceReference[]>: Daftar domain.
  - `[Id <String>]`: ID Sumber Daya.

## RELATED LINKS

