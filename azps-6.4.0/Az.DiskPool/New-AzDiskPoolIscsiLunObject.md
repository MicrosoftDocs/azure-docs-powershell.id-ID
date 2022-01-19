---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolIscsiLunObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
ms.openlocfilehash: 405ceb4f0d2c154cfaedf467c1811c6da7fc5a6e
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136207153"
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

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210401Preview.IscsiLun

## CATATAN

ALIAS

## RELATED LINKS

