---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 67AD15B0-94EB-486F-8C17-606EA5F702D3
online version: https://docs.microsoft.com/powershell/module/az.network/new-azloadbalancerbackendaddresspoolconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerBackendAddressPoolConfig.md
ms.openlocfilehash: b6782f6720603422f6c4144a4e1b5ea29fdf628c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139920805"
---
# New-AzLoadBalancerBackendAddressPoolConfig

## SYNOPSIS
Membuat konfigurasi pool alamat backend untuk penyeimbang muat.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/new-azloadbalancerbackendaddresspoolconfig) untuk informasi terkini.

## SYNTAX

```
New-AzLoadBalancerBackendAddressPoolConfig -Name <String> [-TunnelInterface <PSTunnelInterface[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzLoadBalancerBackendAddressPoolConfig** membuat konfigurasi pool alamat backend untuk penyeimbang muat Azure.

## EXAMPLES

### Contoh 1: Membuat konfigurasi pool alamat backend untuk penyeimbang muat
```
PS C:\>New-AzLoadBalancerBackendAddressPoolConfig -Name "BackendAddressPool02"
```

Perintah ini membuat konfigurasi pool alamat backend yang bernama BackendAddressPool02 untuk penyeimbang muat.

### Contoh 2: Membuat konfigurasi pool alamat backend dengan antarmuka interface interface untuk penyeimbang muat
```powershell
## create with Gateway LoadBalancer TunnelInterface configuration
PS C:\> $tunnelInterface1 = New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig -Protocol 'Vxlan' -Type 'Internal' -Port 2000 -Identifier 800
PS C:\> $tunnelInterface2 = New-AzLoadBalancerBackendAddressPoolTunnelInterfaceConfig -Protocol 'Vxlan' -Type 'External' -Port 2001 -Identifier 801
PS C:\> New-AzLoadBalancerBackendAddressPool -ResourceGroupName $resourceGroup -LoadBalancerName $loadBalancerName -Name $backendPool3 -TunnelInterface $tunnelInterface1, $tunnelInterface2
```

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

### -Nama
Menentukan nama konfigurasi address pool untuk dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaceInterface
Konfigurasi Penyedia Gateway LoadBalancer.

```yaml
Type: PSTunnelInterface[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool

## CATATAN

## RELATED LINKS

[Add-AzLoadBalancerBackendAddressPoolConfig](./Add-AzLoadBalancerBackendAddressPoolConfig.md)

[Get-AzLoadBalancerBackendAddressPoolConfig](./Get-AzLoadBalancerBackendAddressPoolConfig.md)

[Remove-AzLoadBalancerBackendAddressPoolConfig](./Remove-AzLoadBalancerBackendAddressPoolConfig.md)


