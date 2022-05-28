---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 2C603E0E-A19F-4EA6-B918-945007BE22FF
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressroutecrossconnectionroutetablesummary
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteCrossConnectionRouteTableSummary.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteCrossConnectionRouteTableSummary.md
ms.openlocfilehash: 8d59a2c9e1d6fdce1f53974f75efc61c18b01fdf
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145546180"
---
# Get-AzExpressRouteCrossConnectionRouteTableSummary

## SYNOPSIS
Mendapatkan ringkasan tabel rute koneksi silang ExpressRoute.

## SYNTAX

### SpecifyByParameterValues
```
Get-AzExpressRouteCrossConnectionRouteTableSummary -ResourceGroupName <String> -CrossConnectionName <String>
 -PeeringType <String> -DevicePath <DevicePathEnum> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SpecifyByReference
```
Get-AzExpressRouteCrossConnectionRouteTableSummary -ExpressRouteCrossConnection <PSExpressRouteCrossConnection>
 -PeeringType <String> -DevicePath <DevicePathEnum> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRouteCrossConnectionRouteTableSummary** mengambil ringkasan informasi tetangga BGP untuk konteks perutean tertentu. Informasi ini berguna untuk menentukan berapa lama konteks perutean telah ditetapkan dan jumlah awalan rute yang diiklankan oleh router peering.

## EXAMPLES

### Contoh 1: Menampilkan ringkasan rute untuk jalur utama
```powershell
Get-AzExpressRouteCrossConnectionRouteTableSummary -ResourceGroupName $RG -CrossConnectionName $CrossConnectionName -PeeringType MicrosoftPeering -DevicePath Primary
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

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCrossConnectionRoutesTableSummary

## NOTES

## RELATED LINKS

[Get-AzExpressRouteCrossConnectionARPTable](Get-AzExpressRouteCrossConnectionARPTable.md)

[Get-AzExpressRouteCrossConnectionRouteTable](Get-AzExpressRouteCrossConnectionRouteTable.md)
