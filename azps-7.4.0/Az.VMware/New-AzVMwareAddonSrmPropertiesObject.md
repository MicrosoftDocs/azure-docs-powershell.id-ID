---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareAddonSrmPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonSrmPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonSrmPropertiesObject.md
ms.openlocfilehash: 24e09183420cff76f0f6e49eafbdf6f7e35b3a65
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143056349"
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
New-AzVMwareAddonSrmPropertiesObject -LicenseKey "YourLicenseKeyValue"
```
```output
AddonType ProvisioningState LicenseKey
--------- ----------------- ----------
SRM                         YourLicenseKeyValue
```

Membuat objek SRM lokal untuk parameter Properti Addon

## PARAMETERS

### -LicenseKey
Lisensi Site Recovery Manager (SRM).

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.AddonSrmProperties

## NOTES

ALIAS

## RELATED LINKS

