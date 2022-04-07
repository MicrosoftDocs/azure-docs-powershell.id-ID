---
external help file: ''
Module Name: Az.ADDomainServices
online version: https://docs.microsoft.com/powershell/module/az.ADDomainServices/new-AzADDomainServiceReplicaSet
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainServiceReplicaSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainServiceReplicaSet.md
ms.openlocfilehash: c63d091eb5fd83b3fa82c26b80dba010d46c3ad9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140395686"
---
# New-AzADDomainServiceReplicaSet

## SYNOPSIS
Membuat objek dalam memori untuk ReplikaSet

## SYNTAX

```
New-AzADDomainServiceReplicaSet [-Location <String>] [-SubnetId <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ReplikaSet

## EXAMPLES

### Contoh 1: Membuat ReplikaSet untuk AdDomain
```powershell
New-AzADDomainServiceReplicaSet -Location eastus -SubnetId /subscriptions/**********-****-****-****-****-**********/resourceGroups/youriADDomain-rg-test/providers/Microsoft.Network/virtualNetworks/yourinttest/subnets/default
```

```output
DomainControllerIPAddress ExternalAccessIPAddress HealthLastEvaluated Location ServiceStatus SubnetId
------------------------- ----------------------- ------------------- -------- ------------- --------
                                                                      eastus                 /subscriptions/********-****-****-****-**********/resourceGroups/youriADDomain-rg-test/providers/M…
```

Membuat ReplikaSet untuk AdDomain

## PARAMETERS

### -Lokasi
Lokasi jaringan virtual.

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

### -SubnetId
Nama jaringan virtual tempat Layanan Domain akan digunakan.
Id subnet tempat Layanan Domain akan digunakan.
/virtualNetwork/vnetName/subnets/subnetName.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.Api202001.ReplicaSet

## CATATAN

ALIAS

## RELATED LINKS

