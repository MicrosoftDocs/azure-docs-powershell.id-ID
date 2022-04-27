---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayconnectiondraining
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayConnectionDraining.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayConnectionDraining.md
ms.openlocfilehash: 8c59c6d571000333fc2a281498c03eb6071ad203
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144241272"
---
# Get-AzApplicationGatewayConnectionDraining

## SYNOPSIS
Mendapatkan konfigurasi pengurasan koneksi dari objek pengaturan HTTP back-end.

## SYNTAX

```
Get-AzApplicationGatewayConnectionDraining -BackendHttpSettings <PSApplicationGatewayBackendHttpSettings>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayConnectionDraining** mendapatkan konfigurasi pengurasan koneksi dari objek pengaturan HTTP back-end.

## EXAMPLES

### Contoh 1
```powershell
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$Settings  = Get-AzApplicationGatewayBackendHttpSettings -Name "Settings01" -ApplicationGateway $AppGw
$ConnectionDraining = Get-AzApplicationGatewayConnectionDraining -BackendHttpSettings $Settings
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $AppGw.
Perintah kedua mendapatkan pengaturan HTTP back-end bernama Pengaturan01 untuk $AppGw dan menyimpan pengaturan dalam variabel $Pengaturan.
Perintah terakhir mendapatkan konfigurasi pengurasan koneksi dari pengaturan HTTP back-end $Pengaturan dan menyimpannya dalam variabel $ConnectionDraining.

## PARAMETERS

### -BackendHttpSettings
Pengaturan http backend

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayConnectionDraining

## NOTES

## RELATED LINKS

[Get-AzApplicationGateway](./Get-AzApplicationGateway.md)

[Get-AzApplicationGatewayBackendHttpSetting](./Get-AzApplicationGatewayBackendHttpSetting.md)

[New-AzApplicationGatewayConnectionDraining](./New-AzApplicationGatewayConnectionDraining.md)

[Remove-AzApplicationGatewayConnectionDraining](./Remove-AzApplicationGatewayConnectionDraining.md)

[Set-AzApplicationGatewayConnectionDraining](./Set-AzApplicationGatewayConnectionDraining.md)
