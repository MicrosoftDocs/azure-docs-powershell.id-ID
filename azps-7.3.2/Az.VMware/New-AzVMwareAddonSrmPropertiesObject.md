---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareAddonSrmPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonSrmPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonSrmPropertiesObject.md
ms.openlocfilehash: d0f25d006fcaaf3fcb18e46cdaadc5e25c7c1c1b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140553429"
---
# New-AzVMwareAddonSrmPropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk AddonSrmProperties

## SYNTAX

```
New-AzVMwareAddonSrmPropertiesObject -LicenseKey <String> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AddonSrmProperties

## EXAMPLES

### Contoh 1: Membuat objek SRM lokal untuk parameter Properti Addon
```powershell
PS C:\> New-AzVMwareAddonSrmPropertiesObject -LicenseKey "YourLicenseKeyValue"

AddonType ProvisioningState LicenseKey
--------- ----------------- ----------
SRM                         YourLicenseKeyValue
```

Membuat objek SRM lokal untuk parameter Properti Addon

## PARAMETERS

### -LicenseKey
Lisensi Manajer Pemulihan Situs (SRM).

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.AddonSrmProperties

## CATATAN

ALIAS

## RELATED LINKS

