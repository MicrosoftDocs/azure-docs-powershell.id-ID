---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azapplicationgatewaybackendhttpsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayBackendHttpSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayBackendHttpSetting.md
ms.openlocfilehash: efad0cec5bf0aafaaf98c76d7c51cc94240bf55b
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144699098"
---
# Remove-AzApplicationGatewayBackendHttpSetting

## SYNOPSIS
Menghapus pengaturan HTTP back-end dari gateway aplikasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azapplicationgatewaybackendhttpsetting) untuk informasi terbaru.

## SYNTAX

```
Remove-AzApplicationGatewayBackendHttpSetting -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzApplicationGatewayBackendHttpSetting menghapus pengaturan Hypertext Transfer Protocol (HTTP) back-end dari gateway aplikasi Azure.

## EXAMPLES

### Contoh 1: Menghapus pengaturan HTTP back-end dari gateway aplikasi
```powershell
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
Remove-AzApplicationGatewayBackendHttpSetting -ApplicationGateway $AppGw -Name "BackEndSetting02"
Set-AzApplicationGateway -ApplicationGateway $AppGW
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 yang termasuk dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $AppGw.
Perintah kedua menghapus pengaturan HTTP back-end bernama BackEndSetting02 dari gateway aplikasi yang disimpan di $AppGw. Terakhir, perintah ketiga memperbarui gateway aplikasi.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat cmdlet ini menghapus pengaturan HTTP back-end.

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

### -Name
Menentukan nama pengaturan HTTP back-end yang dihapus cmdlet ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewayBackendHttpSetting](./Add-AzApplicationGatewayBackendHttpSetting.md)

[New-AzApplicationGatewayBackendHttpSetting](./New-AzApplicationGatewayBackendHttpSetting.md)

[Get-AzApplicationGatewayBackendHttpSetting](./Get-AzApplicationGatewayBackendHttpSetting.md)

[Set-AzApplicationGatewayBackendHttpSetting](./Set-AzApplicationGatewayBackendHttpSetting.md)

