---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.DiskPool/new-AzDiskPoolAclObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolAclObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolAclObject.md
ms.openlocfilehash: 7a77a33ec5bd6094702842347349940a5c4f66a0
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140482521"
---
# New-AzDiskPoolAclObject

## SYNOPSIS
Membuat objek dalam memori untuk Acl

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.diskpool/new-azdiskpoolaclobject) untuk informasi terkini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.Acl

## CATATAN

ALIAS

## RELATED LINKS

