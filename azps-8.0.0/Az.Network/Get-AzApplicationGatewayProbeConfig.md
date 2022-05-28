---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayprobeconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayProbeConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayProbeConfig.md
ms.openlocfilehash: 8856d4527d7fc766645978cb5e3332e3b45d6963
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145506334"
---
# Get-AzApplicationGatewayProbeConfig

## SYNOPSIS
Mendapatkan konfigurasi pemeriksaan kesehatan yang ada dari Application Gateway.

## SYNTAX

```
Get-AzApplicationGatewayProbeConfig [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzApplicationGatewayProbeConfig mendapatkan konfigurasi pemeriksaan kesehatan yang ada dari Application Gateway.

## EXAMPLES

### Contoh 1: Mendapatkan pemeriksaan yang sudah ada dari gateway aplikasi
```powershell
Get-AzApplicationGatewayProbeConfig -ApplicationGateway Gateway -Name "Probe02"
```

Perintah ini mendapatkan pemeriksaan kesehatan bernama Probe02 dari gateway aplikasi bernama Gateway.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat cmdlet ini mendapatkan konfigurasi pemeriksaan.

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
Menentukan nama probe.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayProbe

## NOTES

## RELATED LINKS

[Menambahkan pemeriksaan ke gateway aplikasi yang sudah ada](https://azure.microsoft.com/en-us/documentation/articles/application-gateway-create-probe-ps/#add-a-probe-to-an-existing-application-gateway)

[Add-AzApplicationGatewayProbeConfig](./Add-AzApplicationGatewayProbeConfig.md)

[New-AzApplicationGatewayProbeConfig](./New-AzApplicationGatewayProbeConfig.md)

[Remove-AzApplicationGatewayProbeConfig](./Remove-AzApplicationGatewayProbeConfig.md)

[Set-AzApplicationGatewayProbeConfig](./Set-AzApplicationGatewayProbeConfig.md)

