---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 2049CB74-E3CB-4294-B97C-B41E91209A1E
online version: https://docs.microsoft.com/powershell/module/az.network/new-azloadbalancerprobeconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/New-AzLoadBalancerProbeConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/New-AzLoadBalancerProbeConfig.md
ms.openlocfilehash: b06679d47bdbedb2cdcf3584d23cf43b5fcc0c99
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "136034485"
---
# New-AzLoadBalancerProbeConfig

## SYNOPSIS
Membuat konfigurasi configuration configuration for a load balancer.

## SYNTAX

```
New-AzLoadBalancerProbeConfig -Name <String> [-Protocol <String>] -Port <Int32> -IntervalInSeconds <Int32>
 -ProbeCount <Int32> [-RequestPath <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzLoadBalancerProbeConfig** membuat konfigurasi untuk penyeimbang muat Azure.

## EXAMPLES

### Contoh 1: Membuat konfigurasi konfigurasi konfigurasi
```powershell
PS C:\>New-AzLoadBalancerProbeConfig -Name "MyProbe" -Protocol "http" -Port 80 -IntervalInSeconds 15 -ProbeCount 15
```

Perintah ini membuat konfigurasi konfigurasi myProbe yang bernama MyProbe menggunakan protokol HTTP.
Port 80 akan terhubung dengan layanan seimbang muatan di port 80.

### Contoh 2

Membuat konfigurasi configuration configuration for a load balancer. (otomatisgenerated)

<!-- Aladdin Generated Example -->
```powershell
New-AzLoadBalancerProbeConfig -IntervalInSeconds 15 -Name 'MyProbe' -Port 80 -ProbeCount 15 -Protocol 'http' -RequestPath 'healthcheck.aspx'
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

### -IntervalInSeconds
Menentukan interval, dalam detik, antar nilai ke setiap instans layanan dengan beban seimbang.

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

### -Nama
Menentukan nama konfigurasi konfigurasi konfigurasi konfigurasi untuk dibuat.

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
Menentukan port yang harus tersambung dengan layanan keseimbangan muat baru.

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

### -DipesanCount
Menentukan jumlah kegagalan berturut-turut per instans untuk suatu instans dianggap tidak sehat.

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

### -Protocol
Menentukan protokol yang akan digunakan untuk konfigurasi konfigurasi.
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
Menentukan jalur dalam layanan muatan seimbang untuk menemukan kesehatan.

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

## INPUTS

### System.String

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSProbe

## CATATAN

## RELATED LINKS

[Add-AzLoadBalancerProbeConfig](./Add-AzLoadBalancerProbeConfig.md)

[Get-AzLoadBalancerProbeConfig](./Get-AzLoadBalancerProbeConfig.md)

[Remove-AzLoadBalancerProbeConfig](./Remove-AzLoadBalancerProbeConfig.md)

[Set-AzLoadBalancerProbeConfig](./Set-AzLoadBalancerProbeConfig.md)


