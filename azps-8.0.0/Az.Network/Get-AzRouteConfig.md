---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: DBD40431-DD7A-42CB-83AA-568B1065A468
online version: https://docs.microsoft.com/powershell/module/az.network/get-azrouteconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteConfig.md
ms.openlocfilehash: 258dabf15b1e7ee1572352c0dcb8473b3509e05f
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145523923"
---
# Get-AzRouteConfig

## SYNOPSIS
Mendapatkan rute dari tabel rute.

## SYNTAX

```
Get-AzRouteConfig -RouteTable <PSRouteTable> [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRouteConfig** mendapatkan rute dari tabel rute Azure.
Anda dapat menentukan rute berdasarkan nama.

## EXAMPLES

### Contoh 1: Mendapatkan tabel rute
```powershell
Get-AzRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01" | Get-AzRouteConfig -Name "Route07"
```

```output
Name              : route07
Id                : 
Etag              : 
ProvisioningState : 
AddressPrefix     : 10.1.0.0/16
NextHopType       : VnetLocal
NextHopIpAddress  :
```

Perintah ini mendapatkan tabel rute bernama RouteTable01 dengan menggunakan cmdlet **Get-AzRouteTable** .
Perintah meneruskan tabel tersebut ke cmdlet saat ini dengan menggunakan operator alur.
Cmdlet saat ini mendapatkan rute bernama Route07 dalam tabel rute bernama RouteTable01.

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

### -Name
Menentukan nama rute yang didapat cmdlet ini.

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

### -RouteTable
Menentukan tabel rute tempat cmdlet ini mendapatkan rute.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSRouteTable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteTable

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRoute

## NOTES

## RELATED LINKS

[New-AzRouteConfig](./Add-AzRouteConfig.md)

[Get-AzRouteTable](./Get-AzRouteTable.md)

[New-AzRouteConfig](./New-AzRouteConfig.md)

[Remove-AzRouteConfig](./Remove-AzRouteConfig.md)

[Set-AzRouteConfig](./Set-AzRouteConfig.md)


