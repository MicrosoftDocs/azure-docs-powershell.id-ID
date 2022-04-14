---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.Logz/new-AzLogzVMResourcesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzVMResourcesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzVMResourcesObject.md
ms.openlocfilehash: 8e74505d12d1bd2c8fc4b7945fce83efb326acba
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141836099"
---
# New-AzLogzVMResourcesObject

## SYNOPSIS
Membuat objek dalam memori untuk VMResources

## SYNTAX

```
New-AzLogzVMResourcesObject [-AgentVersion <String>] [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk VMResources

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk VMResources yang dikirimkan ke parameter VMResource saat memperbarui host vm sumber daya monitor
```powershell
$vmResource = New-AzLogzVMResourcesObject -AgentVersion '1.0' -Id '/SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1'
Update-AzLogzMonitorVMHost -ResourceGroupName logz-rg-test -Name pwsh-logz04 -State 'Install' -VMResource $vmResource
```

```output
AgentVersion Id
------------ --
1.0          /SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1
```

Perintah ini membuat objek dalam memori untuk VMResources yang dikirim ke parameter VMResource ketika memperbarui vm host sumber daya monitor.

## PARAMETERS

### -AgentVersion
Versi agen Logz yang terinstal di VM.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.VMResources

## CATATAN

ALIAS

## RELATED LINKS

