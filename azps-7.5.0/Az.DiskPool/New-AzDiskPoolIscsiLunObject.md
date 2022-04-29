---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolIscsiLunObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
ms.openlocfilehash: 2e5aa084b9470fb2859ec1edc0e80fb036b21e0b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144225690"
---
# New-AzDiskPoolIscsiLunObject

## SYNOPSIS
Membuat objek dalam memori untuk IscsiLun

## SYNTAX

```
New-AzDiskPoolIscsiLunObject -ManagedDiskAzureResourceId <String> -Name <String> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk IscsiLun

## EXAMPLES

### Contoh 1: Membuat objek lun iSCSI
```powershell
New-AzDiskPoolIscsiLunObject -ManagedDiskAzureResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/storagepool-rg-test/providers/Microsoft.Compute/disks/disk-pool-disk-1" -Name 'lun0'
```

Perintah ini membuat objek lun iSCSI.

## PARAMETERS

### -ManagedDiskAzureResourceId
ID Sumber Daya Azure dari Disk Terkelola.

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

### -Name
Nama yang ditentukan pengguna untuk iSCSI LUN; contoh: "lun0".

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

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IscsiLun

## NOTES

ALIAS

## RELATED LINKS

