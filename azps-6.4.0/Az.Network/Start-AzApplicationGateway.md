---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 95731734-EDCA-432A-A7BF-94D1E3725FB2
online version: https://docs.microsoft.com/powershell/module/az.network/start-azapplicationgateway
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Start-AzApplicationGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Start-AzApplicationGateway.md
ms.openlocfilehash: a96510b7f7a1ed80c5d6ad2b7f7298c22e121dd7
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136180050"
---
# Start-AzApplicationGateway

## SYNOPSIS
Memulai gateway aplikasi.

## SYNTAX

```
Start-AzApplicationGateway -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzApplicationGateway** memulai gateway aplikasi Azure

## EXAMPLES

### Contoh1: Memulai gateway aplikasi
```
PS C:\>$AppGw = Start-AzApplicationGateway -ApplicationGateway $AppGw
```

Perintah ini memulai gateway aplikasi yang disimpan di $AppGw lain.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi yang dimulai cmdlet ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Stop-AzApplicationGateway](./Stop-AzApplicationGateway.md)


