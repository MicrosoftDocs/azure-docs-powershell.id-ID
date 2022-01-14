---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/add-azapplicationgatewayprivatelinkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Add-AzApplicationGatewayPrivateLinkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Add-AzApplicationGatewayPrivateLinkConfiguration.md
ms.openlocfilehash: 0bc3d62ad690ab8bed961045ce46448af8700bd8
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "136039198"
---
# Add-AzApplicationGatewayPrivateLinkConfiguration

## SYNOPSIS
Menambahkan konfigurasi link privat ke gateway aplikasi.

## SYNTAX

```
Add-AzApplicationGatewayPrivateLinkConfiguration -ApplicationGateway <PSApplicationGateway> -Name <String>
 -IpConfiguration <PSApplicationGatewayPrivateLinkIpConfiguration[]> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzApplicationGatewayPrivateLinkConfiguration** menambahkan konfigurasi link privat ke gateway aplikasi.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $PrivateLinkIpConfiguration = New-AzApplicationGatewayPrivateLinkConfiguration -Name "ipConfig01" -Subnet $subnet -Primary
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzApplicationGatewayPrivateLinkConfiguration -ApplicationGateway $AppGw -Name "privateLinkConfig01" -IpConfiguration $PrivateLinkIpConfiguration
```

Perintah pertama membuat privateLinkIpConfiguration dan menyimpannya di $PrivateLinkIpConfiguration variabel.
Perintah kedua mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01, dan menyimpannya di $AppGw sumber daya.
Perintah ketiga menambahkan konfigurasi link privat bernama privateLinkConfig01, untuk gateway di $AppGw

## PARAMETERS

### -ApplicationGateway
ApplicationGateway

```yaml
Type: PSApplicationGateway
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpConfiguration
Daftar ipConfiguration

```yaml
Type: PSApplicationGatewayPrivateLinkIpConfiguration[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama konfigurasi privateLink

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayPrivateLinkIpConfiguration[]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[New-AzApplicationGatewayPrivateLinkConfiguration](./New-AzApplicationGatewayPrivateLinkConfiguration.md)

[Get-AzApplicationGatewayPrivateLinkConfiguration](./Get-AzApplicationGatewayPrivateLinkConfiguration.md)

[Remove-AzApplicationGatewayPrivateLinkConfiguration](./Remove-AzApplicationGatewayPrivateLinkConfiguration.md)

[Set-AzApplicationGatewayPrivateLinkConfiguration](./Set-AzApplicationGatewayPrivateLinkConfiguration.md)