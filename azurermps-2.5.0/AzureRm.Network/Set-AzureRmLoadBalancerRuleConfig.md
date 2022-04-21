---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 2638B226-B974-43B6-ACC2-D67573CF6B56
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermloadbalancerruleconfig
schema: 2.0.0
ms.openlocfilehash: 59e20a557c0e32d35dd853a0b3ff7e619ec2a955
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142735295"
---
# Set-AzureRmLoadBalancerRuleConfig

## SYNOPSIS
Mengatur status tujuan untuk konfigurasi aturan penyeimbang muatan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResourceId
```
Set-AzureRmLoadBalancerRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfigurationId <String>] [-BackendAddressPoolId <String>] [-ProbeId <String>]
 [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>]
 [-LoadDistribution <String>] [-EnableFloatingIP] [-DisableOutboundSNAT]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
Set-AzureRmLoadBalancerRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-BackendAddressPool <PSBackendAddressPool>]
 [-Probe <PSProbe>] [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>]
 [-IdleTimeoutInMinutes <Int32>] [-LoadDistribution <String>] [-EnableFloatingIP] [-DisableOutboundSNAT]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmLoadBalancerRuleConfig** mengatur status tujuan untuk konfigurasi aturan penyeimbang beban.

## EXAMPLES

### Contoh 1: Mengubah konfigurasi aturan penyeimbangan beban
```
PS C:\>$slb = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> $slb | Add-AzureRmLoadBalancerRuleConfig -Name "NewRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350 -EnableFloatingIP
PS C:\> $slb | Set-AzureRmLoadBalancerRuleConfig -Name "NewRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350
```

Perintah pertama mendapatkan load balancer bernama MyLoadBalancer, lalu menyimpannya dalam variabel $slb.

Perintah kedua menggunakan operator pipeline untuk mengirimkan penyeimbang muatan dalam $slb ke Add-AzureRmLoadBalancerRuleConfig, yang menambahkan aturan bernama NewRule ke dalamnya.

Perintah ketiga melewati penyeimbang muatan ke **Set-AzureRmLoadBalancerRuleConfig**, yang mengatur konfigurasi aturan baru.
Perhatikan bahwa konfigurasi tidak mengaktifkan alamat IP mengambang, yang telah diaktifkan oleh perintah sebelumnya.

## PARAMETERS

### -BackendAddressPool
Menentukan objek **BackendAddressPool** untuk dikaitkan dengan aturan load balancer.

```yaml
Type: PSBackendAddressPool
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendAddressPoolId
Menentukan ID objek **BackendAddressPool** untuk dikaitkan dengan konfigurasi aturan load balancer.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendPort
Menentukan port backend untuk lalu lintas yang cocok dengan konfigurasi aturan ini.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DisableOutboundSNAT
Mengonfigurasi SNAT untuk VM dalam kumpulan backend untuk menggunakan alamat publicIP yang ditentukan di bagian depan aturan keseimbangan beban.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFloatingIP
Menunjukkan bahwa cmdlet ini memungkinkan alamat IP mengambang untuk konfigurasi aturan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendIpConfiguration
Menentukan daftar alamat IP ujung-depan untuk dikaitkan dengan konfigurasi aturan penyeimbang muatan.

```yaml
Type: PSFrontendIPConfiguration
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendIpConfigurationId
Menentukan ID untuk konfigurasi alamat IP ujung depan.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendPort
Menentukan port ujung depan yang cocok dengan konfigurasi aturan penyeimbang muatan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Menentukan durasi waktu, dalam menit, di mana status percakapan dipertahankan dalam penyeimbang beban.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancer
Menentukan penyeimbang beban.
Cmdlet ini mengatur konfigurasi aturan status tujuan untuk penyeimbang beban yang ditentukan parameter ini.

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

### -LoadDistribution
Menentukan distribusi beban.
Nilai yang dapat diterima untuk parameter ini adalah: SourceIP dan SourceIPProtocol.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Default, SourceIP, SourceIPProtocol

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama penyeimbang muatan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Probe
Menentukan probe untuk dikaitkan dengan konfigurasi aturan penyeimbang muatan.

```yaml
Type: PSProbe
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeId
Menentukan ID probe untuk dikaitkan dengan konfigurasi aturan penyeimbang muatan.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protokol
Menentukan protokol yang cocok dengan aturan penyeimbang muatan.
Nilai yang dapat diterima untuk parameter ini adalah: Tcp atau Udp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Tcp, Udp, All

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

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## NOTES

## RELATED LINKS

[Add-AzureRmLoadBalancerRuleConfig](./Add-AzureRmLoadBalancerRuleConfig.md)

[Add-AzureRmLoadBalancerRuleConfig](./Add-AzureRmLoadBalancerRuleConfig.md)

[Get-AzureRmLoadBalancerRuleConfig](./Get-AzureRmLoadBalancerRuleConfig.md)

[New-AzureRmLoadBalancerRuleConfig](./New-AzureRmLoadBalancerRuleConfig.md)

[Hapus-AzureRmLoadBalancerRuleConfig](./Remove-AzureRmLoadBalancerRuleConfig.md)


