---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: D7A50D71-1D23-431E-9ACD-3A0D1BDC2B17
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9f0e5c8d46941af35ba4203d97b92e33833f8d25
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "132414938"
---
# Get-AzureLocalNetworkGateway

## SYNOPSIS
Mendapatkan gateway jaringan lokal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureLocalNetworkGateway [-GatewayId <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureLocalNetworkGateway** mendapatkan gateway jaringan lokal.

## EXAMPLES

## PARAMETERS

### -GatewayId
Menentukan ID gateway yang akan dapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[New-AzureLocalNetworkGateway](./New-AzureLocalNetworkGateway.md)

[Remove-AzureLocalNetworkGateway](./Remove-AzureLocalNetworkGateway.md)

[Reset-AzureLocalNetworkGateway](./Reset-AzureLocalNetworkGateway.md)
