---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 494E185D-3746-4959-846E-660017A1F392
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmLoadBalancer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmLoadBalancer.md
ms.openlocfilehash: be09bb6592ebf950c2fb3de6b4a512235fd0feab
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420974"
---
# Set-AzureRmLoadBalancer

## SYNOPSIS
Mengatur status tujuan untuk penyeimbang muat.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmLoadBalancer -LoadBalancer <PSLoadBalancer> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmLoadBalancer** mengatur status tujuan untuk penyeimbang muat Azure.

## EXAMPLES

### Contoh 1: Mengubah penyeimbang muat
```
PS C:\>$slb = Get-AzureRmLoadBalancer -Name "NRPLB" -ResourceGroupName "NRP-RG"
PS C:\> $slb | Add-AzureRmLoadBalancerInboundNatRuleConfig -Name "NewRule" -FrontendIpConfiguration $slb.FrontendIpConfigurations[0] -FrontendPort 81 -BackendPort 8181 -Protocol "TCP"
PS C:\> $slb | Set-AzureRmLoadBalancer
```

Perintah pertama mendapatkan penyeimbang muat yang bernama NRPLB, lalu menyimpannya dalam $slb baru.

Perintah kedua menggunakan operator pipeline untuk melewati penyeimbang muat di $slb ke Add-AzureRmLoadBalancerInboundNatRuleConfig, yang menambahkan aturan NAT masuk yang bernama NewRule.

Perintah ketiga memindahkan penyeimbang muat ke **Set-AzureRmLoadBalancer,** yang memperbarui konfigurasi penyeimbang muat dan menyimpannya.

## PARAMETERS

### -LoadBalancer
Menentukan penyeimbang muat.
Cmdlet ini mengatur status tujuan untuk penyeimbang muat yang ditentukan parameter ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSLoadBalancer
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSLoadBalancer
Parameter 'LoadBalancer' menerima nilai tipe 'PSLoadBalancer' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## CATATAN

## RELATED LINKS

[Get-AzureRmLoadBalancer](./Get-AzureRmLoadBalancer.md)

[New-AzureRmLoadBalancer](./New-AzureRmLoadBalancer.md)

[Remove-AzureRmLoadBalancer](./Remove-AzureRmLoadBalancer.md)


