---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 2049CB74-E3CB-4294-B97C-B41E91209A1E
online version: https://docs.microsoft.com/powershell/module/az.network/new-azloadbalancerprobeconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerProbeConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzLoadBalancerProbeConfig.md
ms.openlocfilehash: 65f4289e97aa9acf7f9fb36ba2b6248fac443da2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142900505"
---
# New-AzLoadBalancerProbeConfig

## SYNOPSIS
Membuat konfigurasi probe untuk load balancer.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azloadbalancerprobeconfig) untuk informasi terbaru.

## SYNTAX

```
New-AzLoadBalancerProbeConfig -Name <String> [-Protocol <String>] -Port <Int32> -IntervalInSeconds <Int32>
 -ProbeCount <Int32> [-RequestPath <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzLoadBalancerProbeConfig** membuat konfigurasi probe untuk load balancer Azure.

## EXAMPLES

### Contoh 1: Membuat konfigurasi probe
```powershell
PS C:\>New-AzLoadBalancerProbeConfig -Name "MyProbe" -Protocol "http" -Port 80 -IntervalInSeconds 15 -ProbeCount 15
```

Perintah ini membuat konfigurasi pemeriksaan bernama MyProbe menggunakan protokol HTTP.
Probe baru akan tersambung ke layanan load-balanced pada port 80.

### Contoh 2

Membuat konfigurasi probe untuk load balancer. (autogenerasi)

<!-- Aladdin Generated Example -->
```powershell
New-AzLoadBalancerProbeConfig -IntervalInSeconds 15 -Name 'MyProbe' -Port 80 -ProbeCount 15 -Protocol 'http' -RequestPath 'healthcheck.aspx'
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
Menentukan interval, dalam detik, antara probe untuk setiap instans layanan yang seimbang beban.

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
Menentukan nama konfigurasi probe yang akan dibuat.

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
Menentukan port tempat probe baru harus tersambung ke layanan load-balanced.

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
Menentukan jumlah kegagalan berturut-turut per instans yang dianggap tidak sehat.

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
Menentukan protokol yang digunakan untuk konfigurasi probe.
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
Menentukan jalur dalam layanan seimbang-muat untuk melakukan pemeriksaan untuk menentukan kesehatan.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSProbe

## NOTES

## RELATED LINKS

[Add-AzLoadBalancerProbeConfig](./Add-AzLoadBalancerProbeConfig.md)

[Get-AzLoadBalancerProbeConfig](./Get-AzLoadBalancerProbeConfig.md)

[Remove-AzLoadBalancerProbeConfig](./Remove-AzLoadBalancerProbeConfig.md)

[Set-AzLoadBalancerProbeConfig](./Set-AzLoadBalancerProbeConfig.md)


