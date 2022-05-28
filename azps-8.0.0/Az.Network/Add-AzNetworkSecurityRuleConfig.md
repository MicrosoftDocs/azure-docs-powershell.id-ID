---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 9160A21D-0F83-415B-830B-F35C8B863E90
online version: https://docs.microsoft.com/powershell/module/az.network/add-aznetworksecurityruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzNetworkSecurityRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzNetworkSecurityRuleConfig.md
ms.openlocfilehash: e69d55d0db6321037601e71da6e82b1969551c8b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145499404"
---
# Tambahkan-AzNetworkSecurityRuleConfig

## SYNOPSIS
Menambahkan konfigurasi aturan keamanan jaringan ke grup keamanan jaringan.

## SYNTAX

### SetByResource (Default)
```
Add-AzNetworkSecurityRuleConfig -Name <String> -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-Description <String>] [-Protocol <String>] [-SourcePortRange <String[]>] [-DestinationPortRange <String[]>]
 [-SourceAddressPrefix <String[]>] [-DestinationAddressPrefix <String[]>]
 [-SourceApplicationSecurityGroup <PSApplicationSecurityGroup[]>]
 [-DestinationApplicationSecurityGroup <PSApplicationSecurityGroup[]>] [-Access <String>] [-Priority <Int32>]
 [-Direction <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResourceId
```
Add-AzNetworkSecurityRuleConfig -Name <String> -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-Description <String>] [-Protocol <String>] [-SourcePortRange <String[]>] [-DestinationPortRange <String[]>]
 [-SourceAddressPrefix <String[]>] [-DestinationAddressPrefix <String[]>]
 [-SourceApplicationSecurityGroupId <String[]>] [-DestinationApplicationSecurityGroupId <String[]>]
 [-Access <String>] [-Priority <Int32>] [-Direction <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzNetworkSecurityRuleConfig** menambahkan konfigurasi aturan keamanan jaringan ke grup keamanan jaringan Azure.

## EXAMPLES

### Contoh 1: Menambahkan grup keamanan jaringan
```powershell
Get-AzNetworkSecurityGroup -Name nsg1 -ResourceGroupName rg1 | 
Add-AzNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" -Access `
    Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet `
    -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389 |
    Set-AzNetworkSecurityGroup
```

Perintah pertama mengambil grup keamanan jaringan Azure bernama "nsg1" dari grup sumber daya "rg1". Perintah kedua menambahkan aturan keamanan jaringan bernama "rdp-rule" yang memungkinkan lalu lintas dari internet pada port 3389 ke objek kelompok keamanan jaringan yang diambil. Mempertahankan grup keamanan jaringan Azure yang dimodifikasi.

### Contoh 2: Menambahkan aturan keamanan baru dengan grup keamanan aplikasi
```powershell
$srcAsg = New-AzApplicationSecurityGroup -ResourceGroupName MyResourceGroup -Name srcAsg -Location "West US"
$destAsg = New-AzApplicationSecurityGroup -ResourceGroupName MyResourceGroup -Name destAsg -Location "West US"

Get-AzNetworkSecurityGroup -Name nsg1 -ResourceGroupName rg1 |
Add-AzNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" -Access `
    Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceApplicationSecurityGroup `
    $srcAsg -SourcePortRange * -DestinationApplicationSecurityGroup $destAsg -DestinationPortRange 3389 |
Set-AzNetworkSecurityGroup
```

Pertama, kami membuat dua kelompok keamanan aplikasi baru. Kemudian, kami mengambil grup keamanan jaringan Azure bernama "nsg1" dari grup sumber daya "rg1". dan tambahkan aturan keamanan jaringan bernama "rdp-rule" ke dalamnya. Aturan ini memungkinkan lalu lintas dari semua konfigurasi IP dalam kelompok keamanan aplikasi "srcAsg" ke semua konfigurasi IP di "destAsg" pada port 3389. Setelah menambahkan aturan, kami mempertahankan grup keamanan jaringan Azure yang dimodifikasi.

## PARAMETERS

### -Access
Menentukan apakah lalu lintas jaringan diizinkan atau ditolak.
Nilai yang dapat diterima untuk parameter ini adalah: Izinkan dan Tolak.

```yaml
Type: System.String
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

### -Deskripsi
Menentukan deskripsi konfigurasi aturan keamanan jaringan.

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

### -DestinationAddressPrefix
Menentukan awalan alamat tujuan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Alamat Classless Interdomain Routing (CIDR)
- Rentang alamat IP tujuan
- Karakter kartubebas (*) agar sesuai dengan alamat IP apa pun.
Anda dapat menggunakan tag seperti VirtualNetwork, AzureLoadBalancer, dan Internet.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationApplicationSecurityGroup
Kelompok keamanan aplikasi ditetapkan sebagai tujuan untuk aturan. Ini tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup[]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationApplicationSecurityGroupId
Kelompok keamanan aplikasi ditetapkan sebagai tujuan untuk aturan. Ini tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

```yaml
Type: System.String[]
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
- Karakter kartubebas (*) untuk mencocokkan port apa pun

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Arah
Menentukan apakah aturan dievaluasi pada lalu lintas masuk atau keluar.
Nilai yang dapat diterima untuk parameter ini adalah: Masuk dan Keluar.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Inbound, Outbound

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Menentukan nama konfigurasi aturan keamanan jaringan.

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

### -NetworkSecurityGroup
Menentukan objek **NetworkSecurityGroup** .
Cmdlet ini menambahkan konfigurasi aturan keamanan jaringan ke objek yang ditentukan parameter ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkSecurityGroup
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
Nilai yang dapat diterima untuk parameter ini adalah: Bilangan bulat antara 100 dan 4096.
Nomor prioritas harus unik untuk setiap aturan dalam koleksi.
Semakin rendah jumlah prioritas, semakin tinggi prioritas aturan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protokol
Menentukan protokol jaringan tempat konfigurasi aturan berlaku.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tcp
- Udp
- Karakter kartubebas (*) untuk mencocokkan keduanya

```yaml
Type: System.String
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
Menentukan awalan alamat sumber.
Nilai yang dapat diterima untuk parameter ini adalah:
- A CIDR
- Rentang IP sumber
- Karakter kartubebas (*) agar sesuai dengan alamat IP apa pun.
Anda juga dapat menggunakan tag seperti VirtualNetwork, AzureLoadBalancer, dan Internet.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceApplicationSecurityGroup
Kelompok keamanan aplikasi ditetapkan sebagai sumber untuk aturan. Ini tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup[]
Parameter Sets: SetByResource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceApplicationSecurityGroupId
Kelompok keamanan aplikasi ditetapkan sebagai sumber untuk aturan. Ini tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

```yaml
Type: System.String[]
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
Nilai ini dinyatakan sebagai bilangan bulat, sebagai rentang antara 0 dan 65535, atau sebagai karakter kartubebas (*) untuk mencocokkan port sumber apa pun.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkSecurityGroup

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkSecurityGroup

## NOTES

## RELATED LINKS

[Get-AzNetworkSecurityRuleConfig](./Get-AzNetworkSecurityRuleConfig.md)

[New-AzNetworkSecurityRuleConfig](./New-AzNetworkSecurityRuleConfig.md)

[Remove-AzNetworkSecurityRuleConfig](./Remove-AzNetworkSecurityRuleConfig.md)

[Set-AzNetworkSecurityRuleConfig](./Set-AzNetworkSecurityRuleConfig.md)


