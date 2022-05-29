---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.Logz/new-AzLogzVMResourcesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzVMResourcesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzVMResourcesObject.md
ms.openlocfilehash: e9ec15fc0ef607cc4bfac43b763c54c50b90f5b8
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145811520"
---
# New-AzLogzVMResourcesObject

## SYNOPSIS
Membuat objek dalam memori untuk VMResources

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.logz/new-azlogzvmresourcesobject) untuk informasi terbaru.

## SYNTAX

```
New-AzLogzVMResourcesObject [-AgentVersion <String>] [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk VMResources

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk VMResources yang diteruskan ke parameter VMResource saat memperbarui host vm sumber daya monitor
```powershell
$vmResource = New-AzLogzVMResourcesObject -AgentVersion '1.0' -Id '/SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1'
Update-AzLogzMonitorVMHost -ResourceGroupName logz-rg-test -Name pwsh-logz04 -State 'Install' -VMResource $vmResource
```

```output
AgentVersion Id
------------ --
1.0          /SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1
```

Perintah ini membuat objek dalam memori untuk VMResources yang diteruskan ke parameter VMResource saat memperbarui host vm sumber daya monitor.

## PARAMETERS

### -AgentVersion
Versi agen Logz yang diinstal pada VM.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Permintaan daftar operasi pembaruan host vm.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.VMResources

## NOTES

ALIAS

## RELATED LINKS

