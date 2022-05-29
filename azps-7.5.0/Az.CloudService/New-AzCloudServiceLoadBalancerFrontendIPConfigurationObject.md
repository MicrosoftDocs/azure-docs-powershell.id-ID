---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudserviceloadbalancerfrontendipconfigurationobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject.md
ms.openlocfilehash: 7a2dfa6661f26f971b416770d96b2734c262c99e
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145737892"
---
# New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk LoadBalancerFrontendIPConfiguration

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cloudservice/new-azcloudserviceloadbalancerfrontendipconfigurationobject) untuk informasi terbaru.

## SYNTAX

### DefaultParameterSet (Default)
```
New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject [-Name <String>] [-PublicIPAddressId <String>]
 [<CommonParameters>]
```

### PrivateIP
```
New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject [-Name <String>] [-PrivateIPAddress <String>]
 [-SubnetId <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk LoadBalancerFrontendIPConfiguration

## EXAMPLES

### Contoh 1: Membuat objek konfigurasi IP frontend load balancer
```powershell
$publicIP = Get-AzPublicIpAddress -ResourceGroupName 'ContosoOrg' -Name 'ContosoPublicIP'
$feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
$loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
```

Perintah ini membuat objek konfigurasi IP frontend load balancer yang digunakan untuk membuat atau memperbarui layanan cloud.
Untuk detail selengkapnya, lihat New-AzCloudService.

### Contoh 2: Membuat objek konfigurasi IP frontend load balancer dengan alamat ID Privat
```powershell
# Create role profile object
$subnet = New-AzVirtualNetworkSubnetConfig -Name "WebTier" -AddressPrefix "10.0.0.0/24" -WarningAction SilentlyContinue 
$feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -privateIPAddress '10.0.0.6' -subnetId $Subnet.Id
$loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig

```

Perintah ini membuat objek konfigurasi IP frontend load balancer dengan alamat IP Privat

## PARAMETERS

### -Name
Nama FrontendIpConfigration.

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

### -PrivateIPAddress
Alamat IP Privat

```yaml
Type: System.String
Parameter Sets: PrivateIP
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIPAddressId
Id Sumber Daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
ID Subnet

```yaml
Type: System.String
Parameter Sets: PrivateIP
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.LoadBalancerFrontendIPConfiguration

## NOTES

ALIAS

## RELATED LINKS

