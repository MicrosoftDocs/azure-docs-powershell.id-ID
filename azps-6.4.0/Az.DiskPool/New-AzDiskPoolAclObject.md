---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolAclObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolAclObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolAclObject.md
ms.openlocfilehash: 512016a92c64a9d3c6ac8680e9632c02e908a9cb
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136207167"
---
# New-AzDiskPoolAclObject

## SYNOPSIS
Membuat objek dalam memori untuk Acl

## SYNTAX

```
New-AzDiskPoolAclObject -InitiatorIqn <String> -MappedLun <String[]> [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Acl

## EXAMPLES

### Contoh 1: Membuat objek acl
```powershell
PS C:\> New-AzDiskPoolAclObject -InitiatorIqn 'iqn.2021-05.com.microsoft:target0' -MappedLun @('lun0')

InitiatorIqn                      MappedLun
------------                      ---------
iqn.2021-05.com.microsoft:target0 {lun0}
```

Perintah ini membuat objek acl.

## PARAMETERS

### -InitiatorIqn
Inisiasi iSCSI IQN (Nama yang Memenuhi Syarat iSCSI); contoh: "iqn.2005-03.org.iscsi:client".

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

### -MappedLun
Daftar nama LUN yang dipetakan ke ACL.

```yaml
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210401Preview.Acl

## CATATAN

ALIAS

## RELATED LINKS

