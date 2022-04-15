---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 4D5F469D-FF1F-4D49-AC42-26E6DECFAA26
online version: https://docs.microsoft.com/powershell/module/az.network/set-azapplicationgatewayipconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewayIPConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewayIPConfiguration.md
ms.openlocfilehash: 0d8497394d5758769cfdbb22c56dd84067947285
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142468043"
---
# Set-AzApplicationGatewayIPConfiguration

## SYNOPSIS
Mengubah konfigurasi IP untuk gateway aplikasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azapplicationgatewayipconfiguration) untuk informasi terbaru.

## SYNTAX

### SetByResourceId
```
Set-AzApplicationGatewayIPConfiguration -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-SubnetId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
Set-AzApplicationGatewayIPConfiguration -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-Subnet <PSSubnet>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApplicationGatewayIPConfiguration** mengubah konfigurasi IP.
Konfigurasi IP berisi subnet tempat gateway aplikasi digunakan.

## EXAMPLES

### Contoh 1: Memperbarui konfigurasi IP untuk gateway aplikasi
```
PS C:\>$VNet = Get-AzVirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet 
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewayIPConfiguration -ApplicationGateway $AppGw -Name "AppgwSubnet01" -Subnet $Subnet
```

Perintah pertama mendapatkan jaringan virtual bernama VNet01 yang termasuk dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $VNet.
Perintah kedua mendapatkan konfigurasi subnet bernama Subnet01 menggunakan $VNet dan menyimpannya dalam variabel $Subnet.
Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 milik grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $AppGw.
Perintah keempat mengatur konfigurasi IP gateway aplikasi yang disimpan di $AppGw ke konfigurasi subnet yang disimpan di $Subnet.

## PARAMETERS

### -ApplicationGateway
Menentukan objek gateway aplikasi tempat cmdlet ini mengaitkan konfigurasi IP.

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

### -Nama
Menentukan nama konfigurasi IP.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Menentukan subnet.
Ini adalah subnet tempat gateway aplikasi digunakan.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSSubnet
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Menentukan ID subnet.
Ini adalah subnet tempat gateway aplikasi digunakan.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Add-AzApplicationGatewayIPConfiguration](./Add-AzApplicationGatewayIPConfiguration.md)

[Add-AzApplicationGatewayIPConfiguration](./Add-AzApplicationGatewayIPConfiguration.md)

[Get-AzApplicationGatewayIPConfiguration](./Get-AzApplicationGatewayIPConfiguration.md)

[New-AzApplicationGatewayIPConfiguration](./New-AzApplicationGatewayIPConfiguration.md)

[Remove-AzApplicationGatewayIPConfiguration](./Remove-AzApplicationGatewayIPConfiguration.md)


