---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azcdnedgenode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnEdgeNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnEdgeNode.md
ms.openlocfilehash: 927095427e4c02f505a751008776db66348e9bee
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138297132"
---
# Get-AzCdnEdgeNode

## SYNOPSIS
Mendapatkan Azure CDN edgenodes.

## SYNTAX

```
Get-AzCdnEdgeNode [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzCdnEdgeNode** mendapatkan Azure CDN edgenodes.

## EXAMPLES

### Contoh 1
```powershell
(Get-AzCdnEdgeNode).IpAddressGroups[0] | ConvertTo-Json
```

```Output
{
  "DeliveryRegion": "All",
  "Ipv4Addresses": [
    {
      "BaseIpAddress": "23.200.152.0",
      "PrefixLength": 21
    }
  ],
  "Ipv6Addresses": [
    {
      "BaseIpAddress": "2600:1417:9800::",
      "PrefixLength": 48
    }
  ]
}
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.EdgeNodes.PSEdgeNode

## CATATAN

## RELATED LINKS
