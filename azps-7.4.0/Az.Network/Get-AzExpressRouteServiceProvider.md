---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 009F6E65-0268-4505-AEC1-FF379CB96804
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressrouteserviceprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteServiceProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteServiceProvider.md
ms.openlocfilehash: 40fe5148f0b916f673d491e77f350a72faf414f5
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144696584"
---
# Get-AzExpressRouteServiceProvider

## SYNOPSIS
Mendapatkan daftar penyedia layanan ExpressRoute dan atributnya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azexpressrouteserviceprovider) untuk informasi terbaru.

## SYNTAX

```
Get-AzExpressRouteServiceProvider [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRouteServiceProvider** mengambil daftar penyedia layanan ExpressRoute dan atributnya. Atribut mencakup opsi lokasi dan bandwidth.

## EXAMPLES

### Contoh 1: Dapatkan daftar penyedia layanan dengan lokasi di "Silicon Valley"
```powershell
Get-AzExpressRouteServiceProvider |
   Where-Object PeeringLocations -Contains "Silicon Valley" |
   Select-Object Name
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteServiceProvider

## NOTES

## RELATED LINKS

[Get-AzExpressRouteCircuitARPTable](Get-AzExpressRouteCircuitARPTable.md)

[Get-AzExpressRouteCircuitRouteTable](Get-AzExpressRouteCircuitRouteTable.md)

[Get-AzExpressRouteCircuitRouteTableSummary](Get-AzExpressRouteCircuitRouteTableSummary.md)

[Get-AzExpressRouteCircuitStat](./Get-AzExpressRouteCircuitStat.md)
