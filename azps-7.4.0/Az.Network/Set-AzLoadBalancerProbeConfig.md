---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: C8B91455-C1A7-43BD-9E63-A20E2694371F
online version: https://docs.microsoft.com/powershell/module/az.network/set-azloadbalancerprobeconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzLoadBalancerProbeConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzLoadBalancerProbeConfig.md
ms.openlocfilehash: abc82543c693016cffe3c04b9c89180ca628011c
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144585109"
---
# Set-AzLoadBalancerProbeConfig

## SYNOPSIS
Memperbarui konfigurasi pemeriksaan untuk load balancer.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azloadbalancerprobeconfig) untuk informasi terbaru.

## SYNTAX

```
Set-AzLoadBalancerProbeConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Protocol <String>] -Port <Int32>
 -IntervalInSeconds <Int32> -ProbeCount <Int32> [-RequestPath <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzLoadBalancerProbeConfig** memperbarui konfigurasi pemeriksaan untuk load balancer.

## EXAMPLES

### Contoh 1: Mengubah konfigurasi probe pada load balancer
```powershell
$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
$slb | Add-AzLoadBalancerProbeConfig -Name "NewProbe" -Protocol "http" -Port 80 -IntervalInSeconds 15 -ProbeCount 2 -RequestPath "healthcheck.aspx" 
$slb | Set-AzLoadBalancerProbeConfig -Name "NewProbe" -Port 80 -IntervalInSeconds 15 -ProbeCount 2
```

Perintah pertama mendapatkan loadbalancer bernama MyLoadBalancer, lalu menyimpannya dalam variabel $slb.
Perintah kedua menggunakan operator alur untuk meneruskan load balancer di $slb ke Add-AzLoadBalancerProbeConfig, yang menambahkan konfigurasi pemeriksaan baru ke dalamnya.
Perintah ketiga meneruskan load balancer ke **Set-AzLoadBalancerProbeConfig**, yang mengatur konfigurasi baru.
Perhatikan bahwa perlu untuk menentukan beberapa parameter yang sama yang ditentukan dalam perintah sebelumnya karena diperlukan oleh cmdlet saat ini.

### Contoh 2

Memperbarui konfigurasi pemeriksaan untuk load balancer. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Set-AzLoadBalancerProbeConfig -IntervalInSeconds 15 -Name 'NewProbe' -Port 443 -ProbeCount 2 -Protocol https -LoadBalancer <PSLoadBalancer>
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -IntervalInSeconds
Menentukan interval, dalam detik, antara pemeriksaan ke setiap instans layanan yang seimbang.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancer
Menentukan load balancer.
Cmdlet ini memperbarui konfigurasi pemeriksaan untuk load balancer yang ditentukan parameter ini.

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

### -Name
Menentukan nama konfigurasi pemeriksaan yang ditetapkan cmdlet ini.

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

### -Port
Menentukan port tempat pemeriksaan harus tersambung ke layanan yang seimbang.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProbeCount
Menentukan jumlah kegagalan berturut-turut per instans untuk instans yang dianggap tidak sehat.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protokol
Menentukan protokol yang akan digunakan untuk pemeriksaan.
Nilai yang dapat diterima untuk parameter ini adalah: Tcp atau Http.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequestPath
Menentukan jalur dalam layanan dengan beban seimbang untuk pemeriksaan untuk menentukan kesehatan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

### System.String

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## NOTES

## RELATED LINKS

[Tambahkan-AzLoadBalancerProbeConfig](./Add-AzLoadBalancerProbeConfig.md)

[Dapatkan-AzLoadBalancer](./Get-AzLoadBalancer.md)

[Dapatkan-AzLoadBalancerProbeConfig](./Get-AzLoadBalancerProbeConfig.md)

[New-AzLoadBalancerProbeConfig](./New-AzLoadBalancerProbeConfig.md)

[Remove-AzLoadBalancerProbeConfig](./Remove-AzLoadBalancerProbeConfig.md)


