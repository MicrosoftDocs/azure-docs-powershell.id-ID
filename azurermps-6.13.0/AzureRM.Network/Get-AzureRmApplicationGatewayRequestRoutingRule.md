---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 57A6DB40-43EC-402C-9784-06817ECD99B8
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermapplicationgatewayrequestroutingrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmApplicationGatewayRequestRoutingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmApplicationGatewayRequestRoutingRule.md
ms.openlocfilehash: 7a6d8bef710ddf41f805c6ced558e12781a23276
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142139243"
---
# Get-AzureRmApplicationGatewayRequestRoutingRule

## SYNOPSIS
Mendapatkan aturan perutean permintaan gateway aplikasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmApplicationGatewayRequestRoutingRule [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmApplicationGatewayRequestRoutingRule** mendapatkan aturan perutean permintaan gateway aplikasi.

## EXAMPLES

### Contoh 1: Dapatkan aturan perutean permintaan tertentu
```
PS C:\>$AppGW = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Rule = Get-AzureRmApplicationGatewayRequestRoutingRule -"Rule01" -ApplicationGateway $AppGW
```

Perintah pertama mendapatkan Application Gateway bernama ApplicationGateway01 dan menyimpan hasilnya dalam variabel bernama $AppGW.
Perintah kedua mendapatkan aturan perutean permintaan bernama Rule01 dari Application Gateway yang disimpan dalam variabel bernama $AppGW.

### Contoh 2: Dapatkan daftar aturan perutean permintaan
```
PS C:\>$AppGW = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Rules = Get-AzureRmApplicationGatewayRequestRoutingRule -ApplicationGateway $AppGW
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway
Parameter: ApplicationGateway (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule

## CATATAN

## RELATED LINKS

[Add-AzureRmApplicationGatewayRequestRoutingRule](./Add-AzureRmApplicationGatewayRequestRoutingRule.md)

[New-AzureRmApplicationGatewayRequestRoutingRule](./New-AzureRmApplicationGatewayRequestRoutingRule.md)

[Hapus-AzureRmApplicationGatewayRequestRoutingRule](./Remove-AzureRmApplicationGatewayRequestRoutingRule.md)

[Set-AzureRmApplicationGatewayRequestRoutingRule](./Set-AzureRmApplicationGatewayRequestRoutingRule.md)


