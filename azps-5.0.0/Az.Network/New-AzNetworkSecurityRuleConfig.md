---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 633FB5C9-BEB3-42A3-AF4F-A54CC3F9E0F7
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/new-aznetworksecurityruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/New-AzNetworkSecurityRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/New-AzNetworkSecurityRuleConfig.md
ms.openlocfilehash: adef9e3a2ba0d1e67ee8cb2ec9bdd14d9833f5d7
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132412590"
---
# New-AzNetworkSecurityRuleConfig

## SYNOPSIS
Membuat konfigurasi aturan keamanan jaringan.

## SINTAKS

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

## DESKRIPSI
Cmdlet **New-AzNetworkSecurityRuleConfig** membuat konfigurasi aturan keamanan jaringan Azure untuk grup keamanan jaringan.

## CONTOH

### Contoh 1: Membuat aturan keamanan jaringan untuk memperbolehkan RDP
```powershell
$rule1 = New-AzNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" `
    -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix `
    Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
```

Perintah ini membuat aturan keamanan yang memungkinkan akses dari Internet untuk port 3389

### Contoh 2: Membuat aturan keamanan jaringan yang memungkinkan HTTP
```powershell
$rule2 = New-AzNetworkSecurityRuleConfig -Name web-rule -Description "Allow HTTP" `
    -Access Allow -Protocol Tcp -Direction Inbound -Priority 101 -SourceAddressPrefix `
    Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 80
```

Perintah ini membuat aturan keamanan yang memungkinkan akses dari Internet untuk port 80

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
- Karakter wildcard (*) agar sesuai dengan alamat IP apa pun Anda bisa menggunakan tag seperti VirtualNetwork, AzureLoadBalancer, dan Internet.

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
Grup keamanan aplikasi diatur sebagai tujuan aturan. Parameter ini tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

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
Grup keamanan aplikasi diatur sebagai tujuan aturan. Parameter ini tidak dapat digunakan dengan parameter 'DestinationAddressPrefix'.

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
- Karakter wildcard (*) agar sesuai dengan port apa pun

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
Menentukan apakah aturan akan dievaluasi pada lalu lintas masuk atau keluar.
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
Semakin rendah nomor prioritas, semakin tinggi prioritas aturan.

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

### -Protocol
Menentukan protokol jaringan di mana konfigurasi aturan baru diterapkan.
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
- A CIDR
- Rentang IP sumber
- Karakter wildcard (*) agar sesuai dengan alamat IP apa pun.
Anda juga bisa menggunakan tag seperti VirtualNetwork, AzureLoadBalancer dan Internet.

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
Grup keamanan aplikasi yang diatur sebagai sumber untuk aturan tersebut. Informasi ini tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

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
Grup keamanan aplikasi yang diatur sebagai sumber untuk aturan tersebut. Informasi ini tidak dapat digunakan dengan parameter 'SourceAddressPrefix'.

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
- Karakter wildcard (*) agar sesuai dengan port apa pun

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSSecurityRule

## CATATAN

## LINK TERKAIT

[Add-AzNetworkSecurityRuleConfig](./Add-AzNetworkSecurityRuleConfig.md)

[Get-AzNetworkSecurityRuleConfig](./Get-AzNetworkSecurityRuleConfig.md)

[Remove-AzNetworkSecurityRuleConfig](./Remove-AzNetworkSecurityRuleConfig.md)

[Set-AzNetworkSecurityRuleConfig](./Set-AzNetworkSecurityRuleConfig.md)


