---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 57A6DB40-43EC-402C-9784-06817ECD99B8
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayrequestroutingrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayRequestRoutingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayRequestRoutingRule.md
ms.openlocfilehash: fd31b5a2a9d852c0e4f3087a799bd8250d0b5f7b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143282357"
---
# Get-AzApplicationGatewayRequestRoutingRule

## SYNOPSIS
Mendapatkan aturan perutean permintaan gateway aplikasi.

## SYNTAX

```
Get-AzApplicationGatewayRequestRoutingRule [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayRequestRoutingRule** mendapatkan aturan perutean permintaan gateway aplikasi.

## EXAMPLES

### Contoh 1: Dapatkan aturan perutean permintaan tertentu
```powershell
$AppGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$Rule = Get-AzApplicationGatewayRequestRoutingRule -Name "Rule01" -ApplicationGateway $AppGW
```

Perintah pertama mendapatkan Application Gateway bernama ApplicationGateway01 dan menyimpan hasilnya dalam variabel bernama $AppGW.
Perintah kedua mendapatkan aturan perutean permintaan bernama Rule01 dari Application Gateway yang disimpan dalam variabel bernama $AppGW.

### Contoh 2: Dapatkan daftar aturan perutean permintaan
```powershell
$AppGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$Rules = Get-AzApplicationGatewayRequestRoutingRule -ApplicationGateway $AppGW
```

Perintah pertama mendapatkan Application Gateway bernama ApplicationGateway01 dan menyimpan hasilnya dalam variabel bernama $AppGW.
Perintah kedua mendapatkan daftar aturan perutean permintaan dari Application Gateway yang disimpan dalam variabel bernama $AppGW.

## PARAMETERS

### -ApplicationGateway
Menentukan objek gateway aplikasi yang berisi aturan perutean permintaan.

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
Menentukan nama aturan perutean permintaan yang didapatkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewayRequestRoutingRule](./Add-AzApplicationGatewayRequestRoutingRule.md)

[New-AzApplicationGatewayRequestRoutingRule](./New-AzApplicationGatewayRequestRoutingRule.md)

[Remove-AzApplicationGatewayRequestRoutingRule](./Remove-AzApplicationGatewayRequestRoutingRule.md)

[Set-AzApplicationGatewayRequestRoutingRule](./Set-AzApplicationGatewayRequestRoutingRule.md)


