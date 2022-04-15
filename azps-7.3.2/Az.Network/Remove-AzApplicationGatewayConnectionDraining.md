---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azapplicationgatewayconnectiondraining
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayConnectionDraining.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayConnectionDraining.md
ms.openlocfilehash: 2b9237fbc6173434743d141150aac867dddd826f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142345067"
---
# Remove-AzApplicationGatewayConnectionDraining

## SYNOPSIS
Menghapus koneksi yang menguras konfigurasi objek pengaturan HTTP ujung-belakang.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azapplicationgatewayconnectiondraining) untuk informasi terbaru.

## SYNTAX

```
Remove-AzApplicationGatewayConnectionDraining -BackendHttpSettings <PSApplicationGatewayBackendHttpSettings>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzApplicationGatewayConnectionDraining** menghapus koneksi menguras konfigurasi objek pengaturan HTTP ujung belakang.

## EXAMPLES

### Contoh 1
```
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Settings  = Get-AzApplicationGatewayBackendHttpSettings -Name "Settings01" -ApplicationGateway $AppGw
PS C:\> Remove-AzApplicationGatewayConnectionDraining -BackendHttpSettings $Settings
PS C:\> Set-AzApplicationGateway -ApplicationGateway $AppGW
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $AppGw.
Perintah kedua mendapatkan pengaturan HTTP ujung-belakang bernama Pengaturan01 untuk $AppGw dan menyimpan pengaturan dalam variabel $Pengaturan.
Perintah ketiga menghapus konfigurasi koneksi yang menguras pengaturan HTTP ujung-belakang yang disimpan dalam $Pengaturan. Dan, perintah terakhir memperbarui gateway aplikasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings

## CATATAN

## RELATED LINKS

[Get-AzApplicationGateway](./Get-AzApplicationGateway.md)

[Get-AzApplicationGatewayBackendHttpSetting](./Get-AzApplicationGatewayBackendHttpSetting.md)

[Get-AzApplicationGatewayConnectionDraining](./Get-AzApplicationGatewayConnectionDraining.md)

[New-AzApplicationGatewayConnectionDraining](./New-AzApplicationGatewayConnectionDraining.md)

[Set-AzApplicationGatewayConnectionDraining](./Set-AzApplicationGatewayConnectionDraining.md)

