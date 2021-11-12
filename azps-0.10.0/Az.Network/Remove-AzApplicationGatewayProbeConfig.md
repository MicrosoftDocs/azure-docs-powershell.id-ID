---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/remove-azapplicationgatewayprobeconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Remove-AzApplicationGatewayProbeConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Remove-AzApplicationGatewayProbeConfig.md
ms.openlocfilehash: 3b92451a1dcd5387d89b952149a5fe283775e583730e20612a1b9eb35c92b852
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418413"
---
# Remove-AzApplicationGatewayProbeConfig

## SYNOPSIS
Menghapus properti kesehatan dari gateway aplikasi yang sudah ada.

## SYNTAX

```
Remove-AzApplicationGatewayProbeConfig -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzApplicationGatewayProbeConfig menghapus cmdlet heath cmdlet dari gateway aplikasi yang sudah ada.

## EXAMPLES

### Contoh 1: Menghapus health gateway dari gateway aplikasi yang sudah ada
```
PS C:\>$Gateway = Remove-AzApplicationGatewayProbeConfig -ApplicationGateway Gateway -Name "Probe04"
```

Perintah ini menghapus perintah kesehatan yang bernama Default04 dari gateway aplikasi yang bernama Gateway.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat cmdlet ini menghapus cmdlet.

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
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSApplicationGateway
Parameter 'ApplicationGateway' menerima nilai tipe 'PSApplicationGateway' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Menghapus default dari gateway aplikasi yang sudah ada](https://azure.microsoft.com/en-us/documentation/articles/application-gateway-create-probe-ps/#remove-a-probe-from-an-existing-application-gateway)

[Add-AzApplicationGatewayProbeConfig]()

[Get-AzApplicationGatewayProbeConfig]()

[New-AzApplicationGatewayProbeConfig]()

[Set-AzApplicationGatewayProbeConfig]()

