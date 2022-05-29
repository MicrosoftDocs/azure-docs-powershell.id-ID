---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayautoscaleconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayAutoscaleConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayAutoscaleConfiguration.md
ms.openlocfilehash: dfb4d71af20e2fb48565dc2e420a8ca187b236bc
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145794104"
---
# Get-AzApplicationGatewayAutoscaleConfiguration

## SYNOPSIS
Mendapatkan Konfigurasi Skala Otomatis Application Gateway.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azapplicationgatewayautoscaleconfiguration) untuk informasi terbaru.

## SYNTAX

```
Get-AzApplicationGatewayAutoscaleConfiguration -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayAutoscaleConfiguration** mendapatkan Konfigurasi Skala Otomatis Application Gateway.

## EXAMPLES

### Contoh 1
```powershell
$gw = Get-AzApplicationGateway -Name $appgwName -ResourceGroupName $resgpName
$autoscaleConfiguration = Get-AzApplicationGatewayAutoscaleConfiguration -ApplicationGateway $gw
$autoscaleConfiguration.MinCapacity
```

Perintah pertama mendapatkan gateway aplikasi dan menyimpannya dalam variabel $gw.
Perintah kedua mengekstrak konfigurasi skala otomatis dari gateway aplikasi.

## PARAMETERS

### -ApplicationGateway
ApplicationGateway

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAutoscaleConfiguration

## NOTES

## RELATED LINKS

[New-AzApplicationGatewayAutoscaleConfiguration](./New-AzApplicationGatewayAutoscaleConfiguration.md)

[Remove-AzApplicationGatewayAutoscaleConfiguration](./Remove-AzApplicationGatewayAutoscaleConfiguration.md)

[Set-AzApplicationGatewayAutoscaleConfiguration](./Set-AzApplicationGatewayAutoscaleConfiguration.md)
