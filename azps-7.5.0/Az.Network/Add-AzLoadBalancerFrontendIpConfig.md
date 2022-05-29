---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 07FF274A-F365-44E5-A66B-6740CD165664
online version: https://docs.microsoft.com/powershell/module/az.network/add-azloadbalancerfrontendipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzLoadBalancerFrontendIpConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzLoadBalancerFrontendIpConfig.md
ms.openlocfilehash: a3e3b353ff5239c3b29130365ce2c546c366ecb8
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145767594"
---
# Add-AzLoadBalancerFrontendIpConfig

## SYNOPSIS
Menambahkan konfigurasi IP front-end ke load balancer.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/add-azloadbalancerfrontendipconfig) untuk informasi terbaru.

## SYNTAX

### SetByResourceSubnet (Default)
```
Add-AzLoadBalancerFrontendIpConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-PrivateIpAddress <String>]
 [-PrivateIpAddressVersion <String>] [-Zone <String[]>] -Subnet <PSSubnet>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceIdSubnet
```
Add-AzLoadBalancerFrontendIpConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-PrivateIpAddress <String>]
 [-PrivateIpAddressVersion <String>] [-Zone <String[]>] -SubnetId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceIdPublicIpAddress
```
Add-AzLoadBalancerFrontendIpConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Zone <String[]>]
 -PublicIpAddressId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByResourcePublicIpAddress
```
Add-AzLoadBalancerFrontendIpConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Zone <String[]>]
 -PublicIpAddress <PSPublicIpAddress> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByResourceIdPublicIpAddressPrefix
```
Add-AzLoadBalancerFrontendIpConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Zone <String[]>]
 -PublicIpAddressPrefixId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByResourcePublicIpAddressPrefix
```
Add-AzLoadBalancerFrontendIpConfig -LoadBalancer <PSLoadBalancer> -Name <String> [-Zone <String[]>]
 -PublicIpAddressPrefix <PSPublicIpPrefix> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzLoadBalancerFrontendIpConfig** menambahkan konfigurasi IP front-end ke load balancer Azure.

## EXAMPLES

### Contoh 1 Menambahkan konfigurasi IP front-end dengan alamat IP dinamis
```powershell
$Subnet = Get-AzVirtualNetwork -Name "MyVnet" -ResourceGroupName "MyRg" | Get-AzVirtualNetworkSubnetConfig -Name "MySubnet"
Get-AzLoadBalancer -Name "MyLB" -ResourceGroupName "NrpTest" | Add-AzLoadBalancerFrontendIpConfig -Name "FrontendName" -Subnet $Subnet | Set-AzLoadBalancer
```

Perintah pertama mendapatkan jaringan virtual Azure bernama MyVnet dan meneruskan hasilnya menggunakan alur ke cmdlet **Get-AzVirtualNetworkSubnetConfig** untuk mendapatkan subnet bernama MySubnet.
Perintah kemudian menyimpan hasilnya dalam variabel bernama $Subnet.
Perintah kedua mendapatkan load balancer bernama MyLB dan meneruskan hasilnya ke cmdlet **Add-AzLoadBalancerFrontendIpConfig** yang menambahkan konfigurasi IP front-end ke load balancer dengan alamat IP privat dinamis dari subnet yang disimpan dalam variabel bernama $MySubnet.

### Contoh 2 Menambahkan konfigurasi IP front-end dengan alamat IP statis
```powershell
$Subnet = Get-AzVirtualNetwork -Name "MyVnet" -ResourceGroupName "RG001" | Get-AzVirtualNetworkSubnetConfig -Name "MySubnet"
Get-AzLoadBalancer -Name "MyLB" -ResourceGroupName "NrpTest" | Add-AzLoadBalancerFrontendIpConfig -Name "FrontendName" -Subnet $Subnet -PrivateIpAddress "10.0.1.6" | Set-AzLoadBalancer
```

Perintah pertama mendapatkan jaringan virtual Azure bernama MyVnet dan meneruskan hasilnya menggunakan alur ke cmdlet **Get-AzVirtualNetworkSubnetConfig** untuk mendapatkan subnet bernama MySubnet.
Perintah kemudian menyimpan hasilnya dalam variabel bernama $Subnet.
Perintah kedua mendapatkan load balancer bernama MyLB dan meneruskan hasilnya ke cmdlet **Add-AzLoadBalancerFrontendIpConfig** yang menambahkan konfigurasi IP front-end ke load balancer dengan alamat IP privat statis dari subnet yang disimpan dalam variabel bernama $Subnet.

### Contoh 3 Menambahkan konfigurasi IP front-end dengan alamat IP publik
```powershell
$PublicIp = Get-AzPublicIpAddress -ResourceGroupName "myRG" -Name "MyPub"
Get-AzLoadBalancer -Name "MyLB" -ResourceGroupName "NrpTest" | Add-AzLoadBalancerFrontendIpConfig -Name "FrontendName" -PublicIpAddress $PublicIp | Set-AzLoadBalancer
```

Perintah pertama mendapatkan alamat IP publik Azure bernama MyPub dan menyimpan hasilnya dalam variabel bernama $PublicIp.
Perintah kedua mendapatkan load balancer bernama MyLB dan meneruskan hasilnya ke cmdlet **Add-AzLoadBalancerFrontendIpConfig** yang menambahkan konfigurasi IP front-end ke load balancer dengan alamat IP publik yang disimpan dalam variabel bernama $PublicIp.

### Contoh 4 Menambahkan konfigurasi IP front-end dengan awalan IP publik
```powershell
$PublicIpPrefix = Get-AzPublicIpPrefix -ResourceGroupName "myRG" -Name "MyPubPrefix"
Get-AzLoadBalancer -Name "MyLB" -ResourceGroupName "NrpTest" | Add-AzLoadBalancerFrontendIpConfig -Name "FrontendName" -PublicIpAddressPrefix $PublicIpPrefix | Set-AzLoadBalancer
```

Perintah pertama mendapatkan awalan IP publik Azure bernama MyPubPrefix dan menyimpan hasilnya dalam variabel bernama $PublicIpPrefix.
Perintah kedua mendapatkan load balancer bernama MyLB dan meneruskan hasilnya ke cmdlet **Add-AzLoadBalancerFrontendIpConfig** yang menambahkan konfigurasi IP front-end ke load balancer dengan awalan IP publik yang disimpan dalam variabel bernama $PublicIpPrefix.

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

### -LoadBalancer
Menentukan objek **LoadBalancer** .
Cmdlet ini menambahkan konfigurasi IP front-end ke load balancer yang ditentukan parameter ini.

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
Menentukan nama konfigurasi IP front-end yang akan ditambahkan.

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

### -PrivateIpAddress
Menentukan alamat IP privat untuk dikaitkan dengan konfigurasi IP front-end.

```yaml
Type: System.String
Parameter Sets: SetByResourceSubnet, SetByResourceIdSubnet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateIpAddressVersion
Versi alamat IP privat dari konfigurasi IP.

```yaml
Type: System.String
Parameter Sets: SetByResourceSubnet, SetByResourceIdSubnet
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIpAddress
Menentukan alamat IP publik untuk dikaitkan dengan konfigurasi IP front-end.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress
Parameter Sets: SetByResourcePublicIpAddress
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIpAddressId
Menentukan ID alamat IP publik untuk menambahkan konfigurasi IP front-end.

```yaml
Type: System.String
Parameter Sets: SetByResourceIdPublicIpAddress
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIpAddressPrefix
Menentukan objek awalan alamat IP publik untuk dikaitkan dengan konfigurasi IP front-end.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpPrefix
Parameter Sets: SetByResourcePublicIpAddressPrefix
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIpAddressPrefixId
Menentukan ID objek awalan alamat IP publik untuk dikaitkan dengan konfigurasi IP front-end.

```yaml
Type: System.String
Parameter Sets: SetByResourceIdPublicIpAddressPrefix
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subnet
Menentukan objek subnet untuk menambahkan konfigurasi IP front-end.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSSubnet
Parameter Sets: SetByResourceSubnet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetId
Menentukan ID subnet untuk menambahkan konfigurasi IP front-end.

```yaml
Type: System.String
Parameter Sets: SetByResourceIdSubnet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona
Daftar zona ketersediaan yang menunjukkan IP yang dialokasikan untuk kebutuhan sumber daya.

```yaml
Type: System.String[]
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

### System.String

### System.String[]

### Microsoft.Azure.Commands.Network.Models.PSSubnet

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## NOTES

## RELATED LINKS

[Get-AzLoadBalancerFrontendIpConfig](./Get-AzLoadBalancerFrontendIpConfig.md)

[Pulihkan-AzSqlDatabase](./Get-AzVirtualNetwork.md)

[Get-AzVirtualNetworkSubnetConfig](./Get-AzVirtualNetworkSubnetConfig.md)

[New-AzLoadBalancerFrontendIpConfig](./New-AzLoadBalancerFrontendIpConfig.md)

[Remove-AzLoadBalancerFrontendIpConfig](./Remove-AzLoadBalancerFrontendIpConfig.md)

[Set-AzLoadBalancerFrontendIpConfig](./Set-AzLoadBalancerFrontendIpConfig.md)


