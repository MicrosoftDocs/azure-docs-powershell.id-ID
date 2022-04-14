---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 1FDA90C0-D01F-45E1-9149-16AD04046271
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermloadbalancerinboundnatruleconfig
schema: 2.0.0
ms.openlocfilehash: fbfa70146a5eb70d118e6cd1859f968c576d8a0f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141781562"
---
# Get-AzureRmLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Mendapatkan konfigurasi aturan NAT masuk untuk penyeimbang beban.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmLoadBalancerInboundNatRuleConfig [-Name <String>] -LoadBalancer <PSLoadBalancer>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmLoadBalancerInboundNatRuleConfig** mendapatkan satu atau beberapa aturan terjemahan alamat jaringan masuk (NAT) dalam penyeimbang muatan Azure.

## EXAMPLES

### Contoh 1: Dapatkan konfigurasi aturan NAT masuk
```
PS C:\>$slb = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> Get-AzureRmLoadBalancerInboundNatRuleConfig -Name "MyInboundNatRule1" -LoadBalancer $slb
```

Perintah pertama mendapatkan load balancer bernama MyLoadBalancer, dan menyimpannya dalam variabel $slb.

Perintah kedua mendapatkan aturan NAT terkait bernama MyInboundNatRule1 dari load balancer di $slb.

## PARAMETERS

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

### -LoadBalancer
Menentukan penyeimbang muatan yang terkait dengan konfigurasi aturan NAT masuk yang akan didapatkan.

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
Menentukan nama konfigurasi aturan NAT masuk yang akan didapatkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSLoadBalancer
Parameter 'LoadBalancer' menerima nilai tipe 'PSLoadBalancer' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSInboundNatRule

## CATATAN

## RELATED LINKS

[Get-AzureRmLoadBalancer](./Get-AzureRmLoadBalancer.md)

[New-AzureRmLoadBalancerInboundNatRuleConfig](./New-AzureRmLoadBalancerInboundNatRuleConfig.md)

[Hapus-AzureRmLoadBalancerInboundNatRuleConfig](./Remove-AzureRmLoadBalancerInboundNatRuleConfig.md)

[Set-AzureRmLoadBalancerInboundNatRuleConfig](./Set-AzureRmLoadBalancerInboundNatRuleConfig.md)


