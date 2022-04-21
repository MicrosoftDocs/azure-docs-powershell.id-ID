---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: F421174A-B138-45EB-AF84-CB3CE5870F27
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermloadbalancerbackendaddresspoolconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmLoadBalancerBackendAddressPoolConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmLoadBalancerBackendAddressPoolConfig.md
ms.openlocfilehash: 2a9fca5faf7ba024a5d5c891aa1c74ba002ac053
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142791748"
---
# Get-AzureRmLoadBalancerBackendAddressPoolConfig

## SYNOPSIS
Mendapatkan konfigurasi kumpulan alamat backend untuk penyeimbang beban.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmLoadBalancerBackendAddressPoolConfig -LoadBalancer <PSLoadBalancer> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmLoadBalancerBackendAddressPoolConfig** mendapatkan satu kumpulan alamat backend atau daftar kumpulan alamat backend dalam load balancer.

## EXAMPLES

### Contoh 1: Dapatkan kumpulan alamat backend
```
PS C:\>$loadbalancer = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> Get-AzureRmLoadBalancerBackendAddressPoolConfig -Name "BackendAddressPool02" -LoadBalancer $loadbalancer
```

Perintah pertama mendapatkan load balancer yang sudah ada bernama MyLoadBalancer dalam grup sumber daya bernama MyResourceGroup, lalu menyimpannya dalam variabel $loadbalancer.
Perintah kedua mendapatkan konfigurasi kumpulan alamat backend terkait bernama BackendAddressPool02 untuk penyeimbang muatan di $loadbalancer.

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

### -LoadBalancer
Menentukan penyeimbang muatan yang terkait dengan kumpulan alamat backend yang akan didapatkan.

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
Menentukan nama penyeimbang muatan yang berisi kumpulan alamat backend untuk didapatkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer
Parameter: LoadBalancer (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## NOTES

## RELATED LINKS

[Add-AzureRmLoadBalancerBackendAddressPoolConfig](./Add-AzureRmLoadBalancerBackendAddressPoolConfig.md)

[Get-AzureRmLoadBalancer](./Get-AzureRmLoadBalancer.md)

[New-AzureRmLoadBalancerBackendAddressPoolConfig](./New-AzureRmLoadBalancerBackendAddressPoolConfig.md)

[Remove-AzureRmLoadBalancerBackendAddressPoolConfig](./Remove-AzureRmLoadBalancerBackendAddressPoolConfig.md)


