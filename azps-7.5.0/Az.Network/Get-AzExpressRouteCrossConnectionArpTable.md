---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: F0370845-13D9-4FB5-B30E-826A22EBC5E0
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressroutecrossconnectionarptable
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteCrossConnectionArpTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteCrossConnectionArpTable.md
ms.openlocfilehash: bffb2d450998518c014ee2875a7a0d40b32daf63
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144244786"
---
# Get-AzExpressRouteCrossConnectionArpTable

## SYNOPSIS
Mendapatkan tabel ARP dari koneksi silang ExpressRoute.

## SYNTAX

### SpecifyByParameterValues
```
Get-AzExpressRouteCrossConnectionArpTable -ResourceGroupName <String> -CrossConnectionName <String>
 -PeeringType <String> -DevicePath <DevicePathEnum> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SpecifyByReference
```
Get-AzExpressRouteCrossConnectionArpTable -ExpressRouteCrossConnection <PSExpressRouteCrossConnection>
 -PeeringType <String> -DevicePath <DevicePathEnum> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRouteCrossConnectionARPTable** mengambil tabel ARP dari kedua antarmuka koneksi silang ExpressRoute. Tabel ARP menyediakan pemetaan alamat IPv4 ke alamat MAC untuk peering tertentu. Anda dapat menggunakan tabel ARP untuk memvalidasi konfigurasi dan konektivitas lapisan 2.

## EXAMPLES

### Contoh 1: Menampilkan tabel ARP untuk peer ExpressRoute
```powershell
Get-AzExpressRouteCrossConnectionARPTable -ResourceGroupName $RG -ExpressRouteCrossConnectionName $CrossConnectionName -PeeringType MicrosoftPeering -DevicePath Primary
```

## PARAMETERS

### -CrossConnectionName
Nama Koneksi Lintas Rute Ekspres

```yaml
Type: System.String
Parameter Sets: SpecifyByParameterValues
Aliases: Name, ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -DevicePath
Nilai yang dapat diterima untuk parameter ini adalah: `Primary` atau `Secondary`

```yaml
Type: Microsoft.Azure.Commands.Network.DevicePathEnum
Parameter Sets: (All)
Aliases:
Accepted values: Primary, Secondary

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpressRouteCrossConnection
Koneksi Lintas Rute Ekspres

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSExpressRouteCrossConnection
Parameter Sets: SpecifyByReference
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PeeringType
Nilai yang dapat diterima untuk parameter ini adalah: `AzurePrivatePeering`, , `AzurePublicPeering`dan `MicrosoftPeering`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: AzurePrivatePeering, AzurePublicPeering, MicrosoftPeering

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi koneksi silang ExpressRoute.

```yaml
Type: System.String
Parameter Sets: SpecifyByParameterValues
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitArpTable

## NOTES

## RELATED LINKS

[Get-AzExpressRouteCrossConnectionRouteTable](Get-AzExpressRouteCrossConnectionRouteTable.md)

[Get-AzExpressRouteCrossConnectionRouteTableSummary](Get-AzExpressRouteCrossConnectionRouteTableSummary.md)
