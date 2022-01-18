---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudserviceloadbalancerfrontendipconfigurationobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject.md
ms.openlocfilehash: 8a89ffd3d9a364471ae7762a146f6b5a4e6d6afa
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136195922"
---
# New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk LoadBalancerFrontendIPConfiguration

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
PS C:\> $publicIP = Get-AzPublicIpAddress -ResourceGroupName 'ContosoOrg' -Name 'ContosoPublicIP'
PS C:\> $feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -PublicIPAddressId $publicIp.Id
PS C:\> $loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig
```

Perintah ini membuat objek konfigurasi IP frontend load balancer yang digunakan untuk membuat atau memperbarui layanan awan.
Untuk detail selengkapnya, lihat New-AzCloudService.

### Contoh 2: Buat penyeimbang muat objek konfigurasi IP frontend dengan alamat ID Privat
```powershell
# Create role profile object
PS C:\> $subnet = New-AzVirtualNetworkSubnetConfig -Name "WebTier" -AddressPrefix "10.0.0.0/24" -WarningAction SilentlyContinue 
PS C:\> $feIpConfig = New-AzCloudServiceLoadBalancerFrontendIPConfigurationObject -Name 'ContosoFe' -privateIPAddress '10.0.0.6' -subnetId $Subnet.Id
PS C:\> $loadBalancerConfig = New-AzCloudServiceLoadBalancerConfigurationObject -Name 'ContosoLB' -FrontendIPConfiguration $feIpConfig

```

Perintah ini membuat penyeimbang muat objek konfigurasi IP frontend dengan alamat IP Privat

## PARAMETERS

### -Nama
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
Subnet ID

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.LoadBalancerFrontendIPConfiguration

## CATATAN

ALIAS

## RELATED LINKS

