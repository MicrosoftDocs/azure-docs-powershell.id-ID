---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 278228EB-0126-4F27-A30F-51DC498C65FE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermloadbalancerprobeconfig
schema: 2.0.0
ms.openlocfilehash: 30989d3b9c71821c2eae3cdfd97f9e4e5fc0cb15
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422804"
---
# Get-AzureRmLoadBalancerProbeConfig

## SYNOPSIS
Mendapatkan konfigurasi configuration configuration for a load balancer.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmLoadBalancerProbeConfig [-Name <String>] -LoadBalancer <PSLoadBalancer>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmLoadBalancerProbeConfig** mendapatkan satu atau beberapa konfigurasi untuk penyeimbang muat.

## EXAMPLES

### Contoh 1: Mendapatkan konfigurasi konfigurasi pemuatan
```
PS C:\>$slb = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> Get-AzureRmLoadBalancerProbeConfig -Name "MyProbe" -LoadBalancer $slb
```

Perintah pertama mendapatkan penyeimbang muat bernama MyLoadBalancer, lalu menyimpannya dalam variabel $slb.

Perintah kedua mendapatkan konfigurasi konfigurasi konfigurasi konfigurasi terkait bernama MyProbe dari penyeimbang muat di $slb.

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

### -LoadBalancer
Menentukan penyeimbang muat yang terkait dengan konfigurasi utama untuk mendapatkan.

```yaml
Type: PSLoadBalancer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi konfigurasi untuk mendapatkan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSLoadBalancer
Parameter 'LoadBalancer' menerima nilai tipe 'PSLoadBalancer' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSProbe

## CATATAN

## RELATED LINKS

[Add-AzureRmLoadBalancerProbeConfig](./Add-AzureRmLoadBalancerProbeConfig.md)

[Get-AzureRmLoadBalancer](./Get-AzureRmLoadBalancer.md)

[New-AzureRmLoadBalancerProbeConfig](./New-AzureRmLoadBalancerProbeConfig.md)

[Remove-AzureRmLoadBalancerProbeConfig](./Remove-AzureRmLoadBalancerProbeConfig.md)

[Set-AzureRmLoadBalancerProbeConfig](./Set-AzureRmLoadBalancerProbeConfig.md)


