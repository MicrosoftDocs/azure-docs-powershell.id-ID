---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareAddonVrPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonVrPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonVrPropertiesObject.md
ms.openlocfilehash: bed91da18a0be3e38e0b524785a8bd2f4ffc3527
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142427697"
---
# New-AzVMwareAddonVrPropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk AddonVrProperties

## SYNTAX

```
New-AzVMwareAddonVrPropertiesObject -VrsCount <Int32> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AddonVrProperties

## EXAMPLES

### Contoh 1: Membuat objek VR lokal untuk parameter Properti Addon
```powershell
New-AzVMwareAddonVrPropertiesObject -VrsCount 2
```
```output
AddonType ProvisioningState VrsCount
--------- ----------------- --------
VR                          2
```

Membuat objek VR lokal untuk parameter Properti Addon

## PARAMETERS

### -VrsCount
Jumlah vSphere Replication Server (VRS).

```yaml
Type: System.Int32
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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.AddonVrProperties

## CATATAN

ALIAS

## RELATED LINKS

