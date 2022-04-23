---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.ConnectedNetwork/new-AzConnectedNetworkAzureStackEdgeObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkAzureStackEdgeObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkAzureStackEdgeObject.md
ms.openlocfilehash: 6c3ef173e53bc026213b4414f22f575513940ca5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143186327"
---
# New-AzConnectedNetworkAzureStackEdgeObject

## SYNOPSIS
Membuat objek dalam memori untuk AzureStackEdgeFormat

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.connectednetwork/new-azconnectednetworkazurestackedgeobject) untuk informasi terbaru.

## SYNTAX

```
New-AzConnectedNetworkAzureStackEdgeObject [-AzureStackEdgeId <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AzureStackEdgeFormat

## EXAMPLES

### Contoh 1: Membuat objek AzureStackEdgeFormat dalam memori yang disimpan untuk membuat perangkat
```powershell
PS C:\> New-AzConnectedNetworkAzureStackEdgeObject -AzureStackEdgeId "/subscriptions/xxxxx-00000-xxxxx-00000/resourcegroups/myResources/providers/Microsoft.DataBoxEdge/dataBoxEdgeDevices/myAse1"

eviceType     ProvisioningState Status
----------     ----------------- ------
AzureStackEdge
```

Membuat objek AzureStackEdgeFormat dalam memori yang disimpan untuk membuat perangkat

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.AzureStackEdgeFormat

## NOTES

ALIAS

## RELATED LINKS

