---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 5D887302-7678-44C0-86F3-CEF2EF8A0991
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewaywebapplicationfirewallconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayWebApplicationFirewallConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayWebApplicationFirewallConfiguration.md
ms.openlocfilehash: a196a34065e21d765c27d409bc746238264d31b4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142176954"
---
# Get-AzApplicationGatewayWebApplicationFirewallConfiguration

## SYNOPSIS
Mendapatkan konfigurasi WAF gateway aplikasi.

## SYNTAX

```
Get-AzApplicationGatewayWebApplicationFirewallConfiguration -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayWebApplicationFirewallConfiguration** mendapatkan konfigurasi firewall aplikasi web (WAF) gateway aplikasi.

## EXAMPLES

### Contoh 1: Dapatkan konfigurasi firewall aplikasi gateway web
```powershell
$AppGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$FirewallConfig = Get-AzApplicationGatewayWebApplicationFirewallConfiguration -ApplicationGateway $AppGW
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01, lalu menyimpannya dalam variabel $AppGW.
Perintah kedua mendapatkan konfigurasi firewall gateway aplikasi di $AppGW, lalu menyimpannya di $FirewallConfig.

## PARAMETERS

### -ApplicationGateway
Menentukan objek gateway aplikasi.
Anda bisa menggunakan cmdlet Get-AzApplicationGateway untuk mendapatkan objek gateway aplikasi.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayWebApplicationFirewallConfiguration

## CATATAN

## RELATED LINKS

[Get-AzApplicationGateway](./Get-AzApplicationGateway.md)

[New-AzApplicationGatewayWebApplicationFirewallConfiguration](./New-AzApplicationGatewayWebApplicationFirewallConfiguration.md)

[Set-AzApplicationGatewayWebApplicationFirewallConfiguration](./Set-AzApplicationGatewayWebApplicationFirewallConfiguration.md)


