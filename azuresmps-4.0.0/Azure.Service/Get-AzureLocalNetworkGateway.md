---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: D7A50D71-1D23-431E-9ACD-3A0D1BDC2B17
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9f0e5c8d46941af35ba4203d97b92e33833f8d25
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141966460"
---
# Get-AzureLocalNetworkGateway

## SYNOPSIS
Mendapatkan gateway jaringan lokal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureLocalNetworkGateway [-GatewayId <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureLocalNetworkGateway** mendapatkan gateway jaringan lokal.

## EXAMPLES

## PARAMETERS

### -GatewayId
Menentukan ID gateway untuk didapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
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

## OUTPUTS

## CATATAN

## RELATED LINKS

[AzureLocalNetworkGateway baru](./New-AzureLocalNetworkGateway.md)

[Hapus-AzureLocalNetworkGateway](./Remove-AzureLocalNetworkGateway.md)

[Mengatur ulang AzureLocalNetworkGateway](./Reset-AzureLocalNetworkGateway.md)
