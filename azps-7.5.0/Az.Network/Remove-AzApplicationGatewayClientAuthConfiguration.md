---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azapplicationgatewayclientauthconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayClientAuthConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayClientAuthConfiguration.md
ms.openlocfilehash: c0ff0e0f2eed3232d1ebc1b6bf4e6abf4a99465a
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144196344"
---
# Remove-AzApplicationGatewayClientAuthConfiguration

## SYNOPSIS
Menghapus konfigurasi autentikasi klien dari objek profil SSL.

## SYNTAX

```
Remove-AzApplicationGatewayClientAuthConfiguration -SslProfile <PSApplicationGatewaySslProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzApplicationGatewayClientAuthConfiguration** menghapus konfigurasi autentikasi klien objek profil SSL.

## EXAMPLES

### Contoh 1
```powershell
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$profile  = Get-AzApplicationGatewaySslProfile -Name "Profile01" -ApplicationGateway $AppGw
Remove-AzApplicationGatewayClientAuthConfiguration -SslProfile $profile
Set-AzApplicationGateway -ApplicationGateway $AppGW
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $AppGw. Perintah kedua mendapatkan profil SSL bernama Profile01 untuk $AppGw dan menyimpannya dalam variabel $profile. Perintah berikutnya menghapus konfigurasi autentikasi klien profil ssl yang disimpan di $profile. Perintah terakhir memperbarui gateway aplikasi.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslProfile
Profil ssl

```yaml
Type: PSApplicationGatewaySslProfile
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslProfile

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslProfile

## NOTES

## RELATED LINKS

[New-AzApplicationGatewayClientAuthConfiguration](./New-AzApplicationGatewayClientAuthConfiguration.md)

[Get-AzApplicationGatewayClientAuthConfiguration](./Get-AzApplicationGatewayClientAuthConfiguration.md)

[Set-AzApplicationGatewayClientAuthConfiguration](./Set-AzApplicationGatewayClientAuthConfiguration.md)
