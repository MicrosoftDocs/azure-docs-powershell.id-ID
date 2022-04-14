---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolIscsiLunObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiLunObject.md
ms.openlocfilehash: 440b011480fb1db58efc1f9afdd5c7dfef4569ab
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142110977"
---
# New-AzDiskPoolIscsiLunObject

## SYNOPSIS
Membuat objek dalam memori untuk IscsiLun

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.diskpool/new-azdiskpooliscsilunobject) untuk informasi terbaru.

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

Perintah ini membuat objek lun iSCSI.

## PARAMETERS

### -ManagedDiskAzureResourceId
AZURE Resource ID dari Managed Disk.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IscsiLun

## CATATAN

ALIAS

## RELATED LINKS

