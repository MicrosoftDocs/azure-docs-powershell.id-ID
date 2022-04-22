---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: D29C82CC-2080-48DA-880A-1AA83007E552
online version: https://docs.microsoft.com/powershell/module/az.network/new-aznetworkinterfaceipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkInterfaceIpConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkInterfaceIpConfig.md
ms.openlocfilehash: 60b42f9416e2f07c315dd10b3cabdb9bd663105a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142938791"
---
# New-AzNetworkInterfaceIpConfig

## SYNOPSIS
Membuat konfigurasi IP antarmuka jaringan.

## SYNTAX

### SetByResource (Default)
```
New-AzNetworkInterfaceIpConfig -Name <String> [-PrivateIpAddressVersion <String>] [-PrivateIpAddress <String>]
 [-Primary] [-Subnet <PSSubnet>] [-PublicIpAddress <PSPublicIpAddress>]
 [-LoadBalancerBackendAddressPool <PSBackendAddressPool[]>] [-LoadBalancerInboundNatRule <PSInboundNatRule[]>]
 [-ApplicationGatewayBackendAddressPool <PSApplicationGatewayBackendAddressPool[]>]
 [-ApplicationSecurityGroup <PSApplicationSecurityGroup[]>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SetByResourceId
```
New-AzNetworkInterfaceIpConfig -Name <String> [-PrivateIpAddressVersion <String>] [-PrivateIpAddress <String>]
 [-Primary] [-SubnetId <String>] [-PublicIpAddressId <String>] [-LoadBalancerBackendAddressPoolId <String[]>]
 [-LoadBalancerInboundNatRuleId <String[]>] [-ApplicationGatewayBackendAddressPoolId <String[]>]
 [-ApplicationSecurityGroupId <String[]>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzNetworkInterfaceIpConfig** membuat konfigurasi IP antarmuka jaringan Azure untuk antarmuka jaringan.

## EXAMPLES

### Contoh 1: Membuat konfigurasi IP dengan alamat IP publik untuk antarmuka jaringan
```powershell
$vnet = Get-AzVirtualNetwork -Name myvnet -ResourceGroupName myrg
$Subnet = Get-AzVirtualNetworkSubnetConfig -Name mysubnet -VirtualNetwork $vnet
$PIP1 = Get-AzPublicIPAddress -Name "PIP1" -ResourceGroupName "RG1"

$IPConfig1 = New-AzNetworkInterfaceIpConfig -Name "IPConfig-1" -Subnet $Subnet -PublicIpAddress $PIP1
    -Primary

 $nic = New-AzNetworkInterface -Name $NicName -ResourceGroupName myrg -Location westus
    -IpConfiguration $IpConfig1
```

Dua perintah pertama mendapatkan jaringan virtual yang disebut myvnet dan subnet yang disebut mysubnet yang sebelumnya dibuat. Ini disimpan di $vnet dan $Subnet masing-masing. Perintah ketiga mendapatkan alamat IP publik yang sebelumnya dibuat yang disebut PIP1. Perintah forth membuat konfigurasi IP baru yang disebut "IPConfig-1" sebagai konfigurasi IP utama dengan alamat IP publik yang terkait dengannya.
Perintah terakhir kemudian membuat antarmuka jaringan yang disebut mynic1 menggunakan konfigurasi IP ini.

### Contoh 2: Membuat konfigurasi IP dengan alamat IP pribadi
```powershell
$vnet = Get-AzVirtualNetwork -Name myvnet -ResourceGroupName myrg
$Subnet = Get-AzVirtualNetworkSubnetConfig -Name mysubnet -VirtualNetwork $vnet

$IPConfig2 = New-AzNetworkInterfaceIpConfig -Name "IP-Config2" -Subnet $Subnet -PrivateIpAddress
    10.0.0.5

$nic = New-AzNetworkInterface -Name mynic1 -ResourceGroupName myrg -Location westus -IpConfiguration
    $IpConfig2
```

Dua perintah pertama mendapatkan jaringan virtual yang disebut myvnet dan subnet yang disebut mysubnet yang sebelumnya dibuat. Ini disimpan di $vnet dan $Subnet masing-masing. Perintah ketiga membuat konfigurasi IP baru yang disebut "IPConfig-2" dengan alamat IP pribadi 10.0.0.5 yang terkait dengannya.
Perintah terakhir kemudian membuat antarmuka jaringan yang disebut mynic1 menggunakan konfigurasi IP ini.

### Contoh 3

Membuat konfigurasi IP antarmuka jaringan. (autogenerasi)

<!-- Aladdin Generated Example -->
```powershell
New-AzNetworkInterfaceIpConfig -Name 'IP-Config2' -PrivateIpAddress '10.0.1.10' -PrivateIpAddressVersion IPv4 -SubnetId <String>
```

## PARAMETERS

### -ApplicationGatewayBackendAddressPool
Menentukan kumpulan referensi kumpulan alamat backend gateway aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool[]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationGatewayBackendAddressPoolId
Menentukan kumpulan referensi kumpulan alamat backend gateway aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.String[]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationSecurityGroup
Menentukan kumpulan referensi grup keamanan aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup[]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationSecurityGroupId
Menentukan kumpulan referensi grup keamanan aplikasi tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.String[]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -LoadBalancerBackendAddressPool
Menentukan kumpulan referensi kumpulan alamat backend load balancer tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool[]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerBackendAddressPoolId
Menentukan kumpulan referensi kumpulan alamat backend load balancer tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.String[]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerInboundNatRule
Menentukan kumpulan referensi Aturan Nat masuk penyeimbang muatan tempat IPConfiguration antarmuka jaringan ini berada.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSInboundNatRule[]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerInboundNatRuleId
Menentukan kumpulan referensi aturan terjemahan alamat jaringan masuk (NAT) penyeimbang muat tempat konfigurasi IP antarmuka jaringan ini berada.

```yaml
Type: System.String[]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi IP antarmuka jaringan.

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

### -Primer
```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateIpAddress
Menentukan alamat IP statis dari konfigurasi IP antarmuka jaringan.

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

### -PrivateIpAddressVersion
Menentukan versi alamat IP dari konfigurasi IP antarmuka jaringan.
Nilai yang dapat diterima untuk parameter ini adalah:
- IPv4
- IPv6

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIpAddress
Menentukan objek **PublicIPAddress** .
Cmdlet ini membuat referensi ke Alamat IP publik untuk dikaitkan dengan konfigurasi IP antarmuka jaringan ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIpAddressId
Cmdlet ini membuat referensi ke Alamat IP publik untuk dikaitkan dengan konfigurasi IP antarmuka jaringan ini.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Menentukan objek **Subnet** .
Cmdlet ini membuat referensi ke subnet tempat konfigurasi IP antarmuka jaringan ini dibuat.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSSubnet
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Menentukan referensi ke subnet tempat konfigurasi IP antarmuka jaringan ini dibuat.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool[]

### Microsoft.Azure.Commands.Network.Models.PSInboundNatRule[]

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool[]

### Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup[]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterfaceIPConfiguration

## NOTES
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, jaringan, jaringan

## RELATED LINKS

[Add-AzNetworkInterfaceIpConfig](./Add-AzNetworkInterfaceIpConfig.md)

[Get-AzNetworkInterfaceIpConfig](./Get-AzNetworkInterfaceIpConfig.md)

[Remove-AzNetworkInterfaceIpConfig](./Remove-AzNetworkInterfaceIpConfig.md)

[Set-AzNetworkInterfaceIpConfig](./Set-AzNetworkInterfaceIpConfig.md)
