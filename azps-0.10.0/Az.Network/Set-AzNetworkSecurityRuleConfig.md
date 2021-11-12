---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 7EFFFF43-501E-4955-A4EE-2C09B8863B30
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/set-aznetworksecurityruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzNetworkSecurityRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzNetworkSecurityRuleConfig.md
ms.openlocfilehash: 963dc6391ef5f500b26068e2a407eacd64ce6c16
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423991"
---
# Set-AzNetworkSecurityRuleConfig

## SYNOPSIS
Menetapkan status tujuan untuk konfigurasi aturan keamanan jaringan.

## SYNTAX

### SetByResource (Default)
```
Set-AzNetworkSecurityRuleConfig -Name <String> -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-Description <String>] [-Protocol <String>]
 [-SourcePortRange <System.Collections.Generic.List`1[System.String]>]
 [-DestinationPortRange <System.Collections.Generic.List`1[System.String]>]
 [-SourceAddressPrefix <System.Collections.Generic.List`1[System.String]>]
 [-DestinationAddressPrefix <System.Collections.Generic.List`1[System.String]>]
 [-SourceApplicationSecurityGroup <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup]>]
 [-DestinationApplicationSecurityGroup <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup]>]
 [-Access <String>] [-Priority <Int32>] [-Direction <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SetByResourceId
```
Set-AzNetworkSecurityRuleConfig -Name <String> -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-Description <String>] [-Protocol <String>]
 [-SourcePortRange <System.Collections.Generic.List`1[System.String]>]
 [-DestinationPortRange <System.Collections.Generic.List`1[System.String]>]
 [-SourceAddressPrefix <System.Collections.Generic.List`1[System.String]>]
 [-DestinationAddressPrefix <System.Collections.Generic.List`1[System.String]>]
 [-SourceApplicationSecurityGroupId <System.Collections.Generic.List`1[System.String]>]
 [-DestinationApplicationSecurityGroupId <System.Collections.Generic.List`1[System.String]>] [-Access <String>]
 [-Priority <Int32>] [-Direction <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzNetworkSecurityRuleConfig** mengatur status tujuan untuk konfigurasi aturan keamanan jaringan Azure.

## EXAMPLES

### Contoh 1: Mengubah konfigurasi akses dalam aturan keamanan jaringan
```
PS C:\>$nsg = Get-AzNetworkSecurityGroup -Name "NSG-FrontEnd" -ResourceGroupName "TestRG"
PS C:\> $nsg | Get-AzNetworkSecurityRuleConfig -Name "rdp-rule"
PS C:\> Set-AzNetworkSecurityRuleConfig -Name "rdp-rule" -NetworkSecurityGroup $nsg -Access "Deny"
```

Perintah pertama mendapatkan grup keamanan jaringan bernama NSG-FrontEnd, lalu menyimpannya dalam variabel $nsg.

Perintah kedua menggunakan operator pipeline untuk melewati grup keamanan dalam $nsg ke Get-AzNetworkSecurityRuleConfig, yang mendapatkan konfigurasi aturan keamanan bernama rdp-rule.

Perintah ketiga mengubah konfigurasi akses dari aturan-rdp menjadi Tolak.

## PARAMETERS

### -Access
Menentukan apakah lalu lintas jaringan diperbolehkan atau ditolak. Nilai yang dapat diterima untuk parameter ini adalah: Izinkan dan Tolak.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Deskripsi
Menentukan deskripsi untuk konfigurasi aturan.
Ukuran maksimalnya adalah 140 karakter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationAddressPrefix
Menentukan prefiks alamat tujuan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Alamat Classless Interdomain Routing (CIDR) 
- Rentang alamat IP tujuan 
- Karakter wildcard (*) untuk mencocokkan alamat IP apa pun

Anda bisa menggunakan tag seperti VirtualNetwork, AzureLoadBalancer, dan Internet.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationApplicationSecurityGroup
Grup keamanan aplikasi diatur sebagai tujuan aturan. Parameter ini tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup]
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationApplicationSecurityGroupId
Grup keamanan aplikasi diatur sebagai tujuan aturan. Parameter ini tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPortRange
Menentukan port atau rentang tujuan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Bilangan bulat 
- Rentang bilangan bulat antara 0 dan 65535
- Karakter wildcard (*) agar sesuai dengan port apa pun

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Arah
Menentukan apakah aturan akan dievaluasi untuk lalu lintas masuk atau keluar.
Nilai yang dapat diterima untuk parameter ini adalah: Masuk dan Keluar.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Inbound, Outbound

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi aturan keamanan jaringan yang ditetapkan cmdlet ini.

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

### -NetworkSecurityGroup
Menentukan objek **NetworkSecurityGroup** yang berisi konfigurasi aturan keamanan jaringan untuk diatur.

```yaml
Type: PSNetworkSecurityGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Prioritas
Menentukan prioritas konfigurasi aturan.
Nilai yang dapat diterima untuk parameter ini adalah:Bilangan bulat antara 100 dan 4096.

Nomor prioritas harus unik untuk setiap aturan dalam kumpulan.
Semakin rendah nomor prioritas, semakin tinggi prioritas aturan.

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

### -Protocol
Menentukan protokol jaringan di mana konfigurasi aturan diterapkan.
Nilai yang dapat diterima untuk parameter ini adalah:

 --Tcp
- Udp
- Karakter wildcard (*) untuk mencocokkan keduanya

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Tcp, Udp, *

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceAddressPrefix
Menentukan prefiks alamat sumber.
Nilai yang dapat diterima untuk parameter ini adalah:

- A CIDR
- Rentang IP sumber
- Karakter wildcard (*) untuk mencocokkan alamat IP apa pun

Anda juga bisa menggunakan tag seperti VirtualNetwork, AzureLoadBalancer dan Internet.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceApplicationSecurityGroup
Grup keamanan aplikasi yang diatur sebagai sumber untuk aturan tersebut. Informasi ini tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup]
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceApplicationSecurityGroupId
Grup keamanan aplikasi yang diatur sebagai sumber untuk aturan tersebut. Informasi ini tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourcePortRange
Menentukan port atau rentang sumber.
Nilai yang dapat diterima untuk parameter ini adalah:

- Bilangan bulat
- Rentang bilangan bulat antara 0 dan 65535
- Karakter wildcard (*) agar sesuai dengan port apa pun

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSNetworkSecurityGroup
Parameter 'NetworkSecurityGroup' menerima nilai tipe 'PSNetworkSecurityGroup' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkSecurityGroup

## CATATAN

## RELATED LINKS

[Add-AzNetworkSecurityRuleConfig](./Add-AzNetworkSecurityRuleConfig.md)

[Get-AzNetworkSecurityRuleConfig](./Get-AzNetworkSecurityRuleConfig.md)

[New-AzNetworkSecurityRuleConfig](./New-AzNetworkSecurityRuleConfig.md)

[Remove-AzNetworkSecurityRuleConfig](./Remove-AzNetworkSecurityRuleConfig.md)


