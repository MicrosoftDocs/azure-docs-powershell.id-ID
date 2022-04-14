---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareAddonVrPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonVrPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareAddonVrPropertiesObject.md
ms.openlocfilehash: bb51db30b38b2d0d48fa5a8c3b04defca6f7c5e4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141794066"
---
# New-AzVMwareAddonVrPropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk AddonVrProperties

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.vmware/new-azvmwareaddonvrpropertiesobject) untuk informasi terbaru.

## SYNTAX

```
New-AzVMwareAddonVrPropertiesObject -VrsCount <Int32> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AddonVrProperties

## EXAMPLES

### Contoh 1: Membuat objek VR lokal untuk parameter Properti Addon
```powershell
PS C:\> New-AzVMwareAddonVrPropertiesObject -VrsCount 2

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20210601.AddonVrProperties

## CATATAN

ALIAS

## RELATED LINKS

