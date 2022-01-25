---
external help file: ''
Module Name: Az.ADDomainServices
online version: https://docs.microsoft.com/powershell/module/az.ADDomainServices/new-AzADDomainServiceReplicaSet
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainServiceReplicaSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainServiceReplicaSet.md
ms.openlocfilehash: 307a0e8a0b38307127f73471b7883305034bb73b
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136730622"
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
PS C:\> New-AzADDomainServiceReplicaSet -Location eastus -SubnetId /subscriptions/**********-****-****-****-****-**********/resourceGroups/youriADDomain-rg-test/providers/Microsoft.Network/virtualNetworks/yourinttest/subnets/default

DomainControllerIPAddress ExternalAccessIPAddress HealthLastEvaluated Location ServiceStatus SubnetId
------------------------- ----------------------- ------------------- -------- ------------- --------
                                                                      eastus                 /subscriptions/****
                                                                      ****-****-****-****-**********/resourceGroups/youriADDomain-rg-test/providers/M…
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.Api202001.ReplicaSet

## CATATAN

ALIAS

## RELATED LINKS

