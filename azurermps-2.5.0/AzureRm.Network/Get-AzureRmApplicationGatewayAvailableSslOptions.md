---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermapplicationgatewayavailablessloptions
schema: 2.0.0
ms.openlocfilehash: 023b2a43114fe47b50956e7f4626a75706e914f5
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "140851140"
---
# Get-AzureRmApplicationGatewayAvailableSslOptions

## SYNOPSIS
Mendapatkan semua opsi ssl yang tersedia untuk kebijakan ssl untuk Gateway Aplikasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmApplicationGatewayAvailableSslOptions [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmApplicationGatewayAvailableSslOptions** mendapatkan semua opsi ssl yang tersedia untuk kebijakan ssl

## EXAMPLES

### Contoh 1
```
PS C:\>$sslOptions = Get-AzureRmApplicationGatewayAvailableSslOptions
```

Perintah ini mengembalikan semua opsi ssl yang tersedia untuk kebijakan ssl.

## PARAMETERS

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAvailableSslOptions

## CATATAN

## RELATED LINKS

