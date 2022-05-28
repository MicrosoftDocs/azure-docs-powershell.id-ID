---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.ConnectedNetwork/new-AzConnectedNetworkAzureStackEdgeObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkAzureStackEdgeObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkAzureStackEdgeObject.md
ms.openlocfilehash: 627a5c4a93ca039ca673f4b11bbe2a808a4985b5
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145499695"
---
# New-AzConnectedNetworkAzureStackEdgeObject

## SYNOPSIS
Membuat objek dalam memori untuk AzureStackEdgeFormat

## SYNTAX

```
New-AzConnectedNetworkAzureStackEdgeObject [-AzureStackEdgeId <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AzureStackEdgeFormat

## EXAMPLES

### Contoh 1: Membuat objek AzureStackEdgeFormat yang disimpan dalam memori untuk membuat perangkat
```powershell
PS C:\> New-AzConnectedNetworkAzureStackEdgeObject -AzureStackEdgeId "/subscriptions/xxxxx-00000-xxxxx-00000/resourcegroups/myResources/providers/Microsoft.DataBoxEdge/dataBoxEdgeDevices/myAse1"

eviceType     ProvisioningState Status
----------     ----------------- ------
AzureStackEdge
```

Membuat objek AzureStackEdgeFormat yang disimpan dalam memori untuk membuat perangkat

## PARAMETERS

### -AzureStackEdgeId
ID Sumber Daya.

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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.AzureStackEdgeFormat

## NOTES

ALIAS

## RELATED LINKS

