---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azexpressrouteportidentity
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzExpressRoutePortIdentity.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzExpressRoutePortIdentity.md
ms.openlocfilehash: 246675a2473bb20e5040f3898b6931f1b3ee6933
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410509"
---
# Get-AzExpressRoutePortIdentity

## SYNOPSIS
Tetapkan identitas ke ExpressRoutePort.

## SINTAKS

```
Get-AzExpressRoutePortIdentity -ExpressRoutePort <PSExpressRoutePort>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzExpressRoutePortIdentity** mendapatkan identitas yang ditetapkan ke objek Azure ExpressRoutePort lokal.

## CONTOH

### Contoh 1
```powershell
PS C:\> $exrPort = Get-AzExpressRoutePort -Name $exrPortName -ResourceGroupName $resgpName
PS C:\> $identity = Get-AzExpressRoutePortIdentity -ExpressRoutePort $exrPort
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -ExpressRoutePort
The ExpressRoute Port

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSManagedServiceIdentity

## CATATAN

## LINK TERKAIT
[Set-AzExpressRoutePortIdentity](./Set-AzExpressRoutePortIdentity.md)

[New-AzExpressRoutePortIdentity](./New-AzExpressRoutePortIdentity.md)

[Remove-AzExpressRoutePortIdentity](./Remove-AzExpressRoutePortIdentity.md)