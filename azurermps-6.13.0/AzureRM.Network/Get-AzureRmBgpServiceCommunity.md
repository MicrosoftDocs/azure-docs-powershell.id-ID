---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermbgpservicecommunity
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmBgpServiceCommunity.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmBgpServiceCommunity.md
ms.openlocfilehash: f951aab0ab655d073c830d08e2665533c961960a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142986833"
---
# Get-AzureRmBgpServiceCommunity

## SYNOPSIS
Menyediakan daftar semua layanan / kawasan, komunitas BGP, dan prefiks terkait.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBgpServiceCommunity [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini menyediakan daftar semua layanan / kawasan, komunitas BGP, dan prefiks terkait.

## EXAMPLES

### Contoh 1
```
Get-AzureRmBgpServiceCommunity

...

Name           : AzureCentralIndia
Id             : /subscriptions//resourceGroups//providers/Microsoft.Network/bgpServiceCommunities/AzureCentralIndia
Type           : Microsoft.Network/bgpServiceCommunities
BgpCommunities : [
                   {
                     "ServiceSupportedRegion": "Global",
                     "CommunityName": "Azure Central India",
                     "CommunityValue": "12076:51017",
                     "CommunityPrefixes": [
                       "13.71.0.0/18",
                       "20.190.146.0/25",
                       "40.79.214.0/24",
                       "40.81.224.0/19",
                       "40.87.224.0/22",
                       "40.112.39.0/25",
                       "40.112.39.128/26",
                       "40.126.18.0/25",
                       "52.136.24.0/24",
                       "52.140.64.0/18",
                       "52.159.64.0/19",
                       "52.172.128.0/17",
                       "52.239.135.64/26",
                       "52.239.202.0/24",
                       "52.245.96.0/22",
                       "52.253.168.0/22",
                       "104.47.210.0/23",
                       "104.211.64.0/20",
                       "104.211.81.0/24",
                       "104.211.82.0/23",
                       "104.211.84.0/22",
                       "104.211.88.0/21",
                       "104.211.96.0/19"
                     ],
                     "IsAuthorizedToUse": true,
                     "ServiceGroup": "Azure"
                   }
                 ]
...
```

Cmdlet ini menyediakan daftar semua layanan / kawasan, komunitas BGP, dan prefiks terkait.

## PARAMETERS

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBgpServiceCommunity

## NOTES

## RELATED LINKS

[Pindahkan-AzureRmExpressRouteCircuit](Move-AzureRmExpressRouteCircuit.md)

[Baru-AzureRmExpressRouteCircuit](New-AzureRmExpressRouteCircuit.md)

[Hapus-AzureRmExpressRouteCircuit](Remove-AzureRmExpressRouteCircuit.md)

[Set-AzureRmExpressRouteCircuit](Set-AzureRmExpressRouteCircuit.md)

[Get-AzureRmRouteFilter](Get-AzureRmRouteFilter.md)

[Get-AzureRmRouteFilterRuleConfig](Get-AzureRmRouteFilterRuleConfig.md)

[Hapus-AzureRmRouteFilter](Remove-AzureRmRouteFilter.md)

[Hapus-AzureRmRouteFilterRuleConfig](Remove-AzureRmRouteFilterRuleConfig.md)

[Set-AzureRmRouteFilter](Set-AzureRmRouteFilter.md)

[Set-AzureRmRouteFilterRuleConfig](Set-AzureRmRouteFilterRuleConfig.md)

[AzureRmRouteFilter Baru](New-AzureRmRouteFilter.md)

[New-AzureRmRouteFilterRuleConfig](New-AzureRmRouteFilterRuleConfig.md)
