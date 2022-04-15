---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 633FB5C9-BEB3-42A3-AF4F-A54CC3F9E0F7
online version: https://docs.microsoft.com/powershell/module/az.network/new-aznetworksecurityruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkSecurityRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzNetworkSecurityRuleConfig.md
ms.openlocfilehash: 48a486083e3658b42825d8fe812e99b08f91451a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142490975"
---
# New-AzNetworkSecurityRuleConfig

## SYNOPSIS
Membuat konfigurasi aturan keamanan jaringan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-aznetworksecurityruleconfig) untuk informasi terbaru.

## SYNTAX

### SetByResource (Default)
```
New-AzNetworkSecurityRuleConfig -Name <String> [-Description <String>] [-Protocol <String>]
 [-SourcePortRange <String[]>] [-DestinationPortRange <String[]>] [-SourceAddressPrefix <String[]>]
 [-DestinationAddressPrefix <String[]>] [-SourceApplicationSecurityGroup <PSApplicationSecurityGroup[]>]
 [-DestinationApplicationSecurityGroup <PSApplicationSecurityGroup[]>] [-Access <String>] [-Priority <Int32>]
 [-Direction <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResourceId
```
New-AzNetworkSecurityRuleConfig -Name <String> [-Description <String>] [-Protocol <String>]
 [-SourcePortRange <String[]>] [-DestinationPortRange <String[]>] [-SourceAddressPrefix <String[]>]
 [-DestinationAddressPrefix <String[]>] [-SourceApplicationSecurityGroupId <String[]>]
 [-DestinationApplicationSecurityGroupId <String[]>] [-Access <String>] [-Priority <Int32>]
 [-Direction <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzNetworkSecurityRuleConfig** membuat konfigurasi aturan keamanan jaringan Azure untuk grup keamanan jaringan.

## EXAMPLES

### Contoh 1: Membuat aturan keamanan jaringan untuk memperbolehkan RDP
```powershell
$rule1 = New-AzNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" `
    -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix `
    Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
```

Perintah ini membuat aturan keamanan yang memungkinkan akses dari Internet ke port 3389

### Contoh 2: Membuat aturan keamanan jaringan yang memungkinkan HTTP
```powershell
$rule2 = New-AzNetworkSecurityRuleConfig -Name web-rule -Description "Allow HTTP" `
    -Access Allow -Protocol Tcp -Direction Inbound -Priority 101 -SourceAddressPrefix `
    Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 80
```

Perintah ini membuat aturan keamanan yang memungkinkan akses dari Internet ke port 80

## PARAMETERS

### -Access
Menentukan apakah lalu lintas jaringan diperbolehkan atau ditolak.
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
Menentukan deskripsi konfigurasi aturan keamanan jaringan untuk dibuat.

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
- Karakter wildcard (*) untuk mencocokkan alamat IP apa pun Anda dapat menggunakan tag seperti VirtualNetwork, AzureLoadBalancer, dan Internet.

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

### -Nama
Menentukan nama konfigurasi aturan keamanan jaringan yang dibuat cmdlet ini.

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

### -Prioritas
Menentukan prioritas konfigurasi aturan.
Nilai yang dapat diterima untuk parameter ini adalah: Bilangan bulat antara 100 dan 4096.
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
Menentukan protokol jaringan tempat konfigurasi aturan baru diterapkan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tcp
- Udp
- karakter wildcard (*) untuk mencocokkan keduanya.

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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSSecurityRule

## CATATAN

## RELATED LINKS

[Add-AzNetworkSecurityRuleConfig](./Add-AzNetworkSecurityRuleConfig.md)

[Get-AzNetworkSecurityRuleConfig](./Get-AzNetworkSecurityRuleConfig.md)

[Remove-AzNetworkSecurityRuleConfig](./Remove-AzNetworkSecurityRuleConfig.md)

[Set-AzNetworkSecurityRuleConfig](./Set-AzNetworkSecurityRuleConfig.md)


