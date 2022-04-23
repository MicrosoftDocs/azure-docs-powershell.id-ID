---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 4518D2A9-7DE7-4617-86E0-7778B8CFE48C
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayfrontendport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayFrontendPort.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayFrontendPort.md
ms.openlocfilehash: ea61620476d2cf0e6e1af45f9c0f6a4e364737a7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143179919"
---
# Get-AzApplicationGatewayFrontendPort

## SYNOPSIS
Mendapatkan port ujung depan gateway aplikasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azapplicationgatewayfrontendport) untuk informasi terbaru.

## SYNTAX

```
Get-AzApplicationGatewayFrontendPort [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayFrontendPort** mendapatkan port ujung depan gateway aplikasi.

## EXAMPLES

### Contoh 1: Dapatkan port front-end yang ditentukan
```
PS C:\>$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndPort = Get-AzApplicationGatewayFrontendPort -Name "FrontEndPort01" -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dari grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah kedua mendapatkan port ujung depan bernama FrontEndPort01 dari $AppGw dan menyimpannya dalam variabel $FrontEndPort.

### Contoh 2: Dapatkan daftar port ujung-depan
```
PS C:\>$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndPorts = Get-AzApplicationGatewayFrontendPort  -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dari grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.
Perintah kedua mendapatkan daftar port ujung depan dari $AppGw dan menyimpannya dalam variabel $FrontEndPorts.

## PARAMETERS

### -ApplicationGateway
Menentukan objek gateway aplikasi yang berisi port ujung depan.

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
Menentukan nama port ujung-depan yang akan didapatkan.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewayFrontendPort](./Add-AzApplicationGatewayFrontendPort.md)

[New-AzApplicationGatewayFrontendPort](./New-AzApplicationGatewayFrontendPort.md)

[Remove-AzApplicationGatewayFrontendPort](./Remove-AzApplicationGatewayFrontendPort.md)

[Set-AzApplicationGatewayFrontendPort](./Set-AzApplicationGatewayFrontendPort.md)


