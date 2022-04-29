---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 4B2066B6-51D7-46D8-8A72-1A232B3E6589
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewaybackendaddresspool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayBackendAddressPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayBackendAddressPool.md
ms.openlocfilehash: 89d9ec088e8e11d147685b3bd7ec8d60e85f0cb4
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144188518"
---
# Get-AzApplicationGatewayBackendAddressPool

## SYNOPSIS
Mendapatkan kumpulan alamat back-end untuk gateway aplikasi.

## SYNTAX

```
Get-AzApplicationGatewayBackendAddressPool [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayBackendAddressPool** mendapatkan satu atau beberapa konfigurasi kumpulan alamat backend dari gateway aplikasi.

## EXAMPLES

### Contoh 1: Mendapatkan kumpulan server back-end tertentu
```powershell
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$BackendPool = Get-AzApplicationGatewayBackendAddressPool -Name "Pool01" -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $AppGw.
Perintah kedua mendapatkan kumpulan alamat back-end yang terkait dengan $AppGw bernama Pool01 dan menyimpannya dalam variabel $BackendPool.

### Contoh 2: Mendapatkan daftar kumpulan server back-end
```powershell
$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$BackendPools = Get-AzApplicationGatewayBackendAddressPool -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $AppGw.
Perintah kedua mendapatkan daftar kumpulan alamat back-end yang terkait dengan $AppGw, dan menyimpan daftar dalam variabel $BackendPools.

## PARAMETERS

### -ApplicationGateway
Cmdlet **Get-AzApplicationGatewayBackendAddressPool** mendapatkan kumpulan alamat back-end untuk gateway aplikasi.

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
Menentukan nama kumpulan alamat back-end yang didapat cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewayBackendAddressPool](./Add-AzApplicationGatewayBackendAddressPool.md)

[New-AzApplicationGatewayBackendAddressPool](./New-AzApplicationGatewayBackendAddressPool.md)

[Remove-AzApplicationGatewayBackendAddressPool](./Remove-AzApplicationGatewayBackendAddressPool.md)

[Set-AzApplicationGatewayBackendAddressPool](./Set-AzApplicationGatewayBackendAddressPool.md)


