---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareAddonSrmPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonSrmPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonSrmPropertiesObject.md
ms.openlocfilehash: c0acc1b9cb560c616cbf1fd81cf4cf10d35289e4
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138258139"
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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20210601.AddonSrmProperties

## CATATAN

ALIAS

## RELATED LINKS

