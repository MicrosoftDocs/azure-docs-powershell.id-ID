---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: F421174A-B138-45EB-AF84-CB3CE5870F27
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azloadbalancerbackendaddresspoolconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzLoadBalancerBackendAddressPoolConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzLoadBalancerBackendAddressPoolConfig.md
ms.openlocfilehash: f6acd469c49df7e67e8aa9bf00faf4952a33eb79
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132406784"
---
# Get-AzLoadBalancerBackendAddressPoolConfig

## SYNOPSIS
Mendapatkan konfigurasi pool alamat backend untuk penyeimbang muat.

## SINTAKS

```
Get-AzLoadBalancerBackendAddressPoolConfig -LoadBalancer <PSLoadBalancer> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzLoadBalancerBackendAddressPoolConfig** mendapatkan satu pool alamat backend atau daftar kolam renang alamat backend dalam penyeimbang muat.

## CONTOH

### Contoh 1: Dapatkan pool alamat backend
```
PS C:\>$loadbalancer = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> Get-AzLoadBalancerBackendAddressPoolConfig -Name "BackendAddressPool02" -LoadBalancer $loadbalancer
```

Perintah pertama mendapatkan penyeimbang muat yang sudah ada bernama MyLoadBalancer dalam grup sumber daya yang bernama MyResourceGroup, lalu menyimpannya di $loadbalancer lokal.
Perintah kedua mendapatkan konfigurasi pool alamat backend terkait yang bernama BackendAddressPool02 untuk penyeimbang muat dalam $loadbalancer.

## PARAMETERS

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## CATATAN

## LINK TERKAIT

[Add-AzLoadBalancerBackendAddressPoolConfig](./Add-AzLoadBalancerBackendAddressPoolConfig.md)

[Get-AzLoadBalancer](./Get-AzLoadBalancer.md)

[New-AzLoadBalancerBackendAddressPoolConfig](./New-AzLoadBalancerBackendAddressPoolConfig.md)

[Remove-AzLoadBalancerBackendAddressPoolConfig](./Remove-AzLoadBalancerBackendAddressPoolConfig.md)


