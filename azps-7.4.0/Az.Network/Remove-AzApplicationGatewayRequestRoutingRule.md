---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: CC033DA8-FACC-44E2-82F9-E30FADBF8926
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azapplicationgatewayrequestroutingrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayRequestRoutingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzApplicationGatewayRequestRoutingRule.md
ms.openlocfilehash: 9f32ab7218320e11184f2eeb764a5ba4b8114ee0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143118845"
---
# Remove-AzApplicationGatewayRequestRoutingRule

## SYNOPSIS
Menghapus aturan perutean permintaan dari gateway aplikasi.

## SYNTAX

```
Remove-AzApplicationGatewayRequestRoutingRule -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzApplicationGatewayRequestRoutingRule** menghapus aturan perutean permintaan dari gateway aplikasi Azure.

## EXAMPLES

### Contoh 1: Menghapus aturan perutean permintaan dari gateway aplikasi
```powershell
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
Remove-AzApplicationGatewayRequestRoutingRule -ApplicationGateway $AppGw -Name "Rule02"
Set-AzApplicationGateway -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi dan menyimpannya dalam variabel $AppGw.
Perintah kedua menghapus aturan perutean permintaan bernama Rule02 dari gateway aplikasi yang disimpan di $AppGw.
Perintah terakhir memperbarui gateway aplikasi.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi untuk menghapus aturan perutean permintaan.

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
Menentukan nama aturan perutean permintaan yang akan dihapus cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewayRequestRoutingRule](./Add-AzApplicationGatewayRequestRoutingRule.md)

[Get-AzApplicationGatewayRequestRoutingRule](./Get-AzApplicationGatewayRequestRoutingRule.md)

[New-AzApplicationGatewayRequestRoutingRule](./New-AzApplicationGatewayRequestRoutingRule.md)

[Set-AzApplicationGatewayRequestRoutingRule](./Set-AzApplicationGatewayRequestRoutingRule.md)


