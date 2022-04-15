---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 7EFFFF43-501E-4955-A4EE-2C09B8863B30
online version: https://docs.microsoft.com/powershell/module/az.network/set-aznetworksecurityruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzNetworkSecurityRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzNetworkSecurityRuleConfig.md
ms.openlocfilehash: e9cfc7b76d252447d97676fb792ad6d4678e1866
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142318387"
---
# Set-AzNetworkSecurityRuleConfig

## SYNOPSIS
Memperbarui konfigurasi aturan keamanan jaringan untuk grup keamanan jaringan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/set-aznetworksecurityruleconfig) untuk informasi terbaru.

## SYNTAX

### SetByResource (Default)
```
Set-AzNetworkSecurityRuleConfig -Name <String> -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-Description <String>] [-Protocol <String>] [-SourcePortRange <String[]>] [-DestinationPortRange <String[]>]
 [-SourceAddressPrefix <String[]>] [-DestinationAddressPrefix <String[]>]
 [-SourceApplicationSecurityGroup <PSApplicationSecurityGroup[]>]
 [-DestinationApplicationSecurityGroup <PSApplicationSecurityGroup[]>] [-Access <String>] [-Priority <Int32>]
 [-Direction <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResourceId
```
Set-AzNetworkSecurityRuleConfig -Name <String> -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-Description <String>] [-Protocol <String>] [-SourcePortRange <String[]>] [-DestinationPortRange <String[]>]
 [-SourceAddressPrefix <String[]>] [-DestinationAddressPrefix <String[]>]
 [-SourceApplicationSecurityGroupId <String[]>] [-DestinationApplicationSecurityGroupId <String[]>]
 [-Access <String>] [-Priority <Int32>] [-Direction <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzNetworkSecurityRuleConfig** memperbarui konfigurasi aturan keamanan jaringan untuk grup keamanan jaringan.

## EXAMPLES

### Contoh 1: Mengubah konfigurasi akses dalam aturan keamanan jaringan
```powershell
PS C:\>$nsg = Get-AzNetworkSecurityGroup -Name "NSG-FrontEnd" -ResourceGroupName "TestRG"
PS C:\> $nsg | Get-AzNetworkSecurityRuleConfig -Name "rdp-rule"
PS C:\> Set-AzNetworkSecurityRuleConfig -Name "rdp-rule" -NetworkSecurityGroup $nsg -Access "Deny"
```

Perintah pertama mendapatkan grup keamanan jaringan bernama NSG-FrontEnd, lalu menyimpannya dalam variabel $nsg.
Perintah kedua menggunakan operator pipeline untuk melewati grup keamanan dalam $nsg ke Get-AzNetworkSecurityRuleConfig, yang mendapatkan konfigurasi aturan keamanan bernama rdp-rule.
Perintah ketiga mengubah konfigurasi akses aturan rdp menjadi Tolak. Namun, ini menimpa aturan dan hanya mengatur parameter yang dikirimkan ke fungsi Set-AzNetworkSecurityRuleConfig.   CATATAN: Tidak ada cara untuk mengubah atribut tunggal

### Contoh 2

Memperbarui konfigurasi aturan keamanan jaringan untuk grup keamanan jaringan. (autogenerasi)

<!-- Aladdin Generated Example -->
```powershell
Set-AzNetworkSecurityRuleConfig -Access Allow -DestinationAddressPrefix * -DestinationPortRange 3389 -Direction Inbound -Name 'rdp-rule' -NetworkSecurityGroup <PSNetworkSecurityGroup> -Priority 1 -Protocol Tcp -SourceAddressPrefix 'Internet' -SourcePortRange *
```

### Contoh 3

Memperbarui konfigurasi aturan keamanan jaringan untuk grup keamanan jaringan. (autogenerasi)

<!-- Aladdin Generated Example -->
```powershell
Set-AzNetworkSecurityRuleConfig -Access Allow -Description 'Allow RDP' -DestinationAddressPrefix * -DestinationPortRange 3389 -Direction Inbound -Name 'rdp-rule' -NetworkSecurityGroup <PSNetworkSecurityGroup> -Priority 1 -Protocol Tcp -SourceAddressPrefix 'Internet' -SourcePortRange *
```

### Contoh 4

Memperbarui konfigurasi aturan keamanan jaringan untuk grup keamanan jaringan (Alamat IP sumber)

```powershell
$nsg = Get-AzNetworkSecurityGroup -ResourceGroupName "MyResource" -Name "MyNsg"
($nsg.SecurityRules | Where-Object {$_.Name -eq "RuleName"}).SourceAddressPrefix = ([System.String[]] @("xxx.xxx.xxx.xxx"))
$nsg | Set-AzNetworkSecurityGroup | Get-AzNetworkSecurityRuleConfig -Name "RuleName"
```

## PARAMETERS

### -Access
Menentukan apakah lalu lintas jaringan diperbolehkan atau ditolak. Nilai yang dapat diterima untuk parameter ini adalah: Izinkan dan Tolak.

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
Menentukan deskripsi untuk konfigurasi aturan.
Ukuran maksimum adalah 140 karakter.

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
Menentukan prefiks alamat tujuan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Alamat Classless Interdomain Routing (CIDR) 
- Rentang alamat IP tujuan 
- Karakter wildcard (*) untuk mencocokkan alamat IP apa pun.
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
Grup keamanan aplikasi diatur sebagai tujuan untuk aturan tersebut. Tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

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
Grup keamanan aplikasi diatur sebagai tujuan untuk aturan tersebut. Tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

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
- Karakter wildcard (*) untuk mencocokkan port apa pun

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
Menentukan apakah aturan dievaluasi untuk lalu lintas masuk atau keluar.
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

### -Nama
Menentukan nama konfigurasi aturan keamanan jaringan yang diatur cmdlet ini.

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
Menentukan objek **NetworkSecurityGroup** yang berisi konfigurasi aturan keamanan jaringan yang akan diatur.

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
Nilai yang dapat diterima untuk parameter ini adalah:Bilangan bulat antara 100 dan 4096.
Nomor prioritas harus unik untuk setiap aturan dalam kumpulan.
Semakin rendah angka prioritas, semakin tinggi prioritas aturan.

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
Menentukan protokol jaringan yang diterapkan konfigurasi aturan.
Nilai yang dapat diterima untuk parameter ini adalah: --Tcp
- Udp
- Karakter wildcard (*) untuk mencocokkan keduanya

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
Menentukan prefiks alamat sumber.
Nilai yang dapat diterima untuk parameter ini adalah:
- SEBUAH CIDR
- Rentang IP sumber
- Karakter wildcard (*) untuk mencocokkan alamat IP apa pun.
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
Grup keamanan aplikasi diatur sebagai sumber untuk aturan. Tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

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
Grup keamanan aplikasi diatur sebagai sumber untuk aturan. Tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

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
Nilai yang dapat diterima untuk parameter ini adalah:
- Bilangan bulat
- Rentang bilangan bulat antara 0 dan 65535
- Karakter wildcard (*) untuk mencocokkan port apa pun

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkSecurityGroup

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkSecurityGroup

## CATATAN

## RELATED LINKS

[Add-AzNetworkSecurityRuleConfig](./Add-AzNetworkSecurityRuleConfig.md)

[Get-AzNetworkSecurityRuleConfig](./Get-AzNetworkSecurityRuleConfig.md)

[New-AzNetworkSecurityRuleConfig](./New-AzNetworkSecurityRuleConfig.md)

[Remove-AzNetworkSecurityRuleConfig](./Remove-AzNetworkSecurityRuleConfig.md)


