---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayconnectiondraining
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayConnectionDraining.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayConnectionDraining.md
ms.openlocfilehash: 10d67628f23f3b692bf3120682b82db0f47038e6
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139973661"
---
# Get-AzApplicationGatewayConnectionDraining

## SYNOPSIS
Dapatkan koneksi dengan menghabiskan konfigurasi objek pengaturan HTTP ujung belakang.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/get-azapplicationgatewayconnectiondraining) untuk informasi terkini.

## SYNTAX

```
Get-AzApplicationGatewayConnectionDraining -BackendHttpSettings <PSApplicationGatewayBackendHttpSettings>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayConnectionDriging** mendapatkan konfigurasi koneksi menghabiskan konfigurasi objek pengaturan HTTP ujung belakang.

## EXAMPLES

### Contoh 1
```
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Settings  = Get-AzApplicationGatewayBackendHttpSettings -Name "Settings01" -ApplicationGateway $AppGw
PS C:\> $ConnectionDraining = Get-AzApplicationGatewayConnectionDraining -BackendHttpSettings $Settings
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya yang bernama ResourceGroup01 dan menyimpannya dalam $AppGw sumber daya.
Perintah kedua mendapatkan pengaturan HTTP ujung belakang yang bernama Settings01 untuk $AppGw dan menyimpan pengaturan dalam variabel $Pengaturan .
Perintah terakhir mendapatkan koneksi menghabiskan konfigurasi dari pengaturan HTTP ujung belakang $Pengaturan dan menyimpannya dalam $ConnectionDraining akhir.

## PARAMETERS

### -BackendHttpSettings
Pengaturan backend http

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayConnectionD adaptering

## CATATAN

## RELATED LINKS

[Get-AzApplicationGateway](./Get-AzApplicationGateway.md)

[Get-AzApplicationGatewayBackendHttpSetting](./Get-AzApplicationGatewayBackendHttpSetting.md)

[New-AzApplicationGatewayConnectionDriging](./New-AzApplicationGatewayConnectionDraining.md)

[Remove-AzApplicationGatewayConnectionDriging](./Remove-AzApplicationGatewayConnectionDraining.md)

[Set-AzApplicationGatewayConnectionDriging](./Set-AzApplicationGatewayConnectionDraining.md)
