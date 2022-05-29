---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareAddonVrPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonVrPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonVrPropertiesObject.md
ms.openlocfilehash: 916eae8c0df6685e365fcdb7e3a90809247bca21
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145702036"
---
# New-AzVMwareAddonVrPropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk AddonVrProperties

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.vmware/new-azvmwareaddonvrpropertiesobject) untuk informasi terbaru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.AddonVrProperties

## NOTES

ALIAS

## RELATED LINKS

