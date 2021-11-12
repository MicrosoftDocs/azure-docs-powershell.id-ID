---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 2B15B224-E36C-454B-B6C2-F2BE032AE962
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/remove-azloadbalancerprobeconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Remove-AzLoadBalancerProbeConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Remove-AzLoadBalancerProbeConfig.md
ms.openlocfilehash: 341bd8df76870de638db949fb844ac7187776509
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408663"
---
# Remove-AzLoadBalancerProbeConfig

## SYNOPSIS
Menghapus konfigurasi konfigurasi konfigurasi konfigurasi konfigurasi dari penyeimbang muat.

## SINTAKS

```
Remove-AzLoadBalancerProbeConfig -LoadBalancer <PSLoadBalancer> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Remove-AzLoadBalancerProbeConfig** menghapus konfigurasi configuration configuration configuration dari load balancer.

## CONTOH

### Contoh 1: Menghapus konfigurasi konfigurasi konfigurasi konfigurasi dari penyeimbang muat
```
PS C:\>$loadbalancer = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:> Remove-AzLoadBalancerProbeConfig -Name "MyProbe" -LoadBalancer $loadbalancer
```

Perintah pertama mendapatkan penyeimbang muat bernama MyLoadBalancer, lalu menyimpannya dalam $loadbalancer variabel.
Perintah kedua menghapus konfigurasi yang bernama MyProbe dari penyeimbang muat dalam $loadbalancer.

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
Menentukan penyeimbang muat yang berisi konfigurasi cmdlet ini.

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
Menentukan nama konfigurasi konfigurasi ini yang dihapus cmdlet ini.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## CATATAN

## LINK TERKAIT

[Add-AzLoadBalancerProbeConfig](./Add-AzLoadBalancerProbeConfig.md)

[Get-AzLoadBalancer](./Get-AzLoadBalancer.md)

[Get-AzLoadBalancerProbeConfig](./Get-AzLoadBalancerProbeConfig.md)

[New-AzLoadBalancerProbeConfig](./New-AzLoadBalancerProbeConfig.md)

[Set-AzLoadBalancerProbeConfig](./Set-AzLoadBalancerProbeConfig.md)


