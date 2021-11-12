---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: F421174A-B138-45EB-AF84-CB3CE5870F27
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermloadbalancerbackendaddresspoolconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmLoadBalancerBackendAddressPoolConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmLoadBalancerBackendAddressPoolConfig.md
ms.openlocfilehash: 2a9fca5faf7ba024a5d5c891aa1c74ba002ac053
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420688"
---
# Get-AzureRmLoadBalancerBackendAddressPoolConfig

## SYNOPSIS
Mendapatkan konfigurasi pool alamat backend untuk penyeimbang muat.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmLoadBalancerBackendAddressPoolConfig -LoadBalancer <PSLoadBalancer> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmLoadBalancerBackendAddressPoolConfig** mendapatkan satu pool alamat backend atau daftar kolam renang alamat backend dalam penyeimbang muat.

## EXAMPLES

### Contoh 1: Dapatkan pool alamat backend
```
PS C:\>$loadbalancer = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> Get-AzureRmLoadBalancerBackendAddressPoolConfig -Name "BackendAddressPool02" -LoadBalancer $loadbalancer
```

Perintah pertama mendapatkan penyeimbang muat yang sudah ada bernama MyLoadBalancer dalam grup sumber daya yang bernama MyResourceGroup, lalu menyimpannya di $loadbalancer lokal.
Perintah kedua mendapatkan konfigurasi pool alamat backend terkait yang bernama BackendAddressPool02 untuk penyeimbang muat dalam $loadbalancer.

## PARAMETERS

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

### -LoadBalancer
Menentukan penyeimbang muat yang terkait dengan pool alamat backend untuk mendapatkan.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSLoadBalancer
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama penyeimbang muat yang berisi pool alamat backend untuk mendapatkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer
Parameter: LoadBalancer (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## CATATAN

## RELATED LINKS

[Add-AzureRmLoadBalancerBackendAddressPoolConfig](./Add-AzureRmLoadBalancerBackendAddressPoolConfig.md)

[Get-AzureRmLoadBalancer](./Get-AzureRmLoadBalancer.md)

[New-AzureRmLoadBalancerBackendAddressPoolConfig](./New-AzureRmLoadBalancerBackendAddressPoolConfig.md)

[Remove-AzureRmLoadBalancerBackendAddressPoolConfig](./Remove-AzureRmLoadBalancerBackendAddressPoolConfig.md)


