---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolAclObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolAclObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolAclObject.md
ms.openlocfilehash: 63df88fa298cf0f5eec0d4a87786357ecc4ad922
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145517134"
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
New-AzDiskPoolAclObject -InitiatorIqn 'iqn.2021-05.com.microsoft:target0' -MappedLun @('lun0')
```

```output
InitiatorIqn                      MappedLun
------------                      ---------
iqn.2021-05.com.microsoft:target0 {lun0}
```

Perintah ini membuat objek acl.

## PARAMETERS

### -InisiatorIqn
Inisiator iSCSI IQN (Nama Yang Memenuhi Syarat iSCSI); contoh: "iqn.2005-03.org.iscsi:client".

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.Acl

## NOTES

ALIAS

## RELATED LINKS

