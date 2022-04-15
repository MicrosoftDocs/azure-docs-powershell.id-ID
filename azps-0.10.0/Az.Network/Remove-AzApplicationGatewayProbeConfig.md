---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/remove-azapplicationgatewayprobeconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Remove-AzApplicationGatewayProbeConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Remove-AzApplicationGatewayProbeConfig.md
ms.openlocfilehash: 320588b81791c033b94a07261f769fa0886d2f2c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141916437"
---
# Remove-AzApplicationGatewayProbeConfig

## SYNOPSIS
Menghapus pemeriksaan kesehatan dari gateway aplikasi yang sudah ada.

## SYNTAX

```
Remove-AzApplicationGatewayProbeConfig -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzApplicationGatewayProbeConfig menghapus penyelidikan heath dari gateway aplikasi yang sudah ada.

## EXAMPLES

### Contoh 1: Menghapus pemeriksaan kesehatan dari gateway aplikasi yang sudah ada
```
PS C:\>$Gateway = Remove-AzApplicationGatewayProbeConfig -ApplicationGateway Gateway -Name "Probe04"
```

Perintah ini menghapus pemeriksaan kesehatan bernama Probe04 dari gateway aplikasi bernama Gateway.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat cmdlet ini menghapus probe.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan nama probe yang akan dihapus cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSApplicationGateway
Parameter 'ApplicationGateway' menerima nilai tipe 'PSApplicationGateway' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Menghapus probe dari gateway aplikasi yang sudah ada](https://azure.microsoft.com/en-us/documentation/articles/application-gateway-create-probe-ps/#remove-a-probe-from-an-existing-application-gateway)

[Add-AzApplicationGatewayProbeConfig]()

[Get-AzApplicationGatewayProbeConfig]()

[New-AzApplicationGatewayProbeConfig]()

[Set-AzApplicationGatewayProbeConfig]()

