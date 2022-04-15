---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/add-azapplicationgatewaycustomerror
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzApplicationGatewayCustomError.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzApplicationGatewayCustomError.md
ms.openlocfilehash: d688d6d1a4fa623093cf4a221122dc592753a126
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142431811"
---
# Add-AzApplicationGatewayCustomError

## SYNOPSIS
Menambahkan kesalahan kustom ke gateway aplikasi.

## SYNTAX

```
Add-AzApplicationGatewayCustomError -ApplicationGateway <PSApplicationGateway> -StatusCode <String>
 -CustomErrorPageUrl <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzApplicationGatewayCustomError** menambahkan kesalahan kustom ke gateway aplikasi.

## EXAMPLES

### Contoh 1: Menambahkan kesalahan kustom ke tingkat gateway aplikasi
```powershell
$resourceGroupName = "resourceGroupName"
$AppGWName = "applicationGatewayName"
$AppGw = Get-AzApplicationGateway -Name $AppGWName -ResourceGroup $resourceGroupName
$customError502Url = "https://mycustomerrorpages.blob.core.windows.net/errorpages/502.htm"
$updatedgateway = Add-AzApplicationGatewayCustomError -ApplicationGateway $AppGw -StatusCode HttpStatus502 -CustomErrorPageUrl $customError502Url
Set-AzApplicationGateway -ApplicationGateway $AppGw
```

Perintah ini menambahkan kesalahan kustom kode status http 502 ke gateway aplikasi $appgw, dan mengembalikan gateway yang diperbarui.

### Contoh 2: Menambahkan kesalahan kustom ke tingkat pendengar gateway aplikasi
```powershell
 $resourceGroupName = "resourceGroupName"
 $AppGWName = "applicationGatewayName"
 $customError502Url = "https://mycustomerrorpages.blob.core.windows.net/errorpages/502.htm"
 $listenerName = "listenerName"
 $AppGw = Get-AzApplicationGateway -Name $AppGWName -ResourceGroupName $resourceGroupName
 $listener = Get-AzApplicationGatewayHttpListener -ApplicationGateway $AppGW -Name $listenerName
 $updatedListener = Add-AzApplicationGatewayHttpListenerCustomError -HttpListener $listener -StatusCode HttpStatus502 -CustomErrorPageUrl $customError502Url 
 Set-AzApplicationGateway -ApplicationGateway $AppGw
```

Perintah ini menambahkan kesalahan kustom kode status http 502 ke gateway aplikasi $appgw di tingkat pendengar, dan mengembalikan gateway yang diperbarui.

## PARAMETERS

### -ApplicationGateway
Application Gateway

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

### -CustomErrorPageUrl
URL halaman kesalahan kesalahan pelanggan gateway aplikasi.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -StatusCode
Kode status kesalahan pelanggan gateway aplikasi.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayCustomError

## CATATAN

## RELATED LINKS

[Get-AzApplicationGatewayCustomError](./Get-AzApplicationGatewayCustomError.md)

[New-AzApplicationGatewayCustomError](./New-AzApplicationGatewayCustomError.md)

[Remove-AzApplicationGatewayCustomError](./Remove-AzApplicationGatewayCustomError.md)

[Set-AzApplicationGatewayCustomError](./Set-AzApplicationGatewayCustomError.md)
