---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azapplicationgatewaysslprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewaySslProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewaySslProfile.md
ms.openlocfilehash: 4ba275dc8a148fa367661cc70cae7a936b0258a5
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136165713"
---
# Remove-AzApplicationGatewaySslProfile

## SYNOPSIS
Menghapus profil ssl dari gateway aplikasi.

## SYNTAX

```
Remove-AzApplicationGatewaySslProfile -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzApplicationGatewaySslProfile** menghapus profil ssl dari gateway aplikasi.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzApplicationGatewaySslProfile -ApplicationGateway $AppGw -Name "SslProfile01"
PS C:\> Set-AzApplicationGateway -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01 dan menyimpannya dalam $AppGw sumber daya. Perintah kedua menghapus profil ssl yang bernama SslProfile01 dari gateway aplikasi yang disimpan di $AppGw.
Perintah terakhir memperbarui gateway aplikasi.

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

### -Nama
Nama profil ssl

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[New-AzApplicationGatewaySslProfile](./New-AzApplicationGatewaySslProfile.md)

[Add-AzApplicationGatewaySslProfile](./Add-AzApplicationGatewaySslProfile.md)

[Get-AzApplicationGatewaySslProfile](./Get-AzApplicationGatewaySslProfile.md)

[Set-AzApplicationGatewaySslProfile](./Set-AzApplicationGatewaySslProfile.md)
