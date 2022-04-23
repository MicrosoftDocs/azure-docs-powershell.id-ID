---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azcdnedgenode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnEdgeNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnEdgeNode.md
ms.openlocfilehash: 736d0d06f757da43d2753a6bd5afacaf149d934b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143137853"
---
# Get-AzCdnEdgeNode

## SYNOPSIS
Mendapatkan Azure CDN edgenode.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cdn/get-azcdnedgenode) untuk informasi terbaru.

## SYNTAX

```
Get-AzCdnEdgeNode [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzCdnEdgeNode** akan Azure CDN edgenode.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.EdgeNodes.PSEdgeNode

## NOTES

## RELATED LINKS
