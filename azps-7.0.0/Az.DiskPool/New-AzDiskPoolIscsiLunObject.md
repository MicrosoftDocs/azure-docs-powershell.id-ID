---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolIscsiLunObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
ms.openlocfilehash: 08798f89e2b06dde79cbd49cf1d5bccdca853f16
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136544612"
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
PS C:\> New-AzDiskPoolIscsiLunObject -ManagedDiskAzureResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/storagepool-rg-test/providers/Microsoft.Compute/disks/disk-pool-disk-1" -Name 'lun0'

```

Perintah ini akan membuat objek lun iSCSI.

## PARAMETERS

### -ManagedDiskAzureResourceId
ID Sumber Daya Azure dari Disk yang Dikelola.

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

### -Nama
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IscsiLun

## CATATAN

ALIAS

## RELATED LINKS

