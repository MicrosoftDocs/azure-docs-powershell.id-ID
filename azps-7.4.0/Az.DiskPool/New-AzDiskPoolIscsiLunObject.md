---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolIscsiLunObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
ms.openlocfilehash: 1915fb3640283d768eb693069a60011b6ae167ba
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144682158"
---
# New-AzDiskPoolIscsiLunObject

## SYNOPSIS
Membuat objek dalam memori untuk IscsiLun

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.diskpool/new-azdiskpooliscsilunobject) untuk informasi terbaru.

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

