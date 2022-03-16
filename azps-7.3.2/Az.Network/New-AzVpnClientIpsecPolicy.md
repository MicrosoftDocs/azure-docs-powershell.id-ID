---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientipsecpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientIpsecPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientIpsecPolicy.md
ms.openlocfilehash: ddc6e75aa4aac5287b4587eaa692c8c52c047af5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139999686"
---
# New-AzVpnClientIpsecPolicy

## SYNOPSIS
Perintah ini memungkinkan pengguna untuk membuat objek kebijakan ipsec Vpn yang menentukan satu atau semua nilai seperti IpsecEncryption,IpsecIntegrity,IkeEncryption,IkeIntegrity,DhGroup,PfsGroup untuk disetel di gateway VPN. Perintah ini memungkinkan objek output digunakan untuk mengatur kebijakan ipsec vpn untuk gateway baru / yang sudah ada.

## SYNTAX

```
New-AzVpnClientIpsecPolicy [-SALifeTime <Int32>] [-SADataSize <Int32>] [-IpsecEncryption <String>]
 [-IpsecIntegrity <String>] [-IkeEncryption <String>] [-IkeIntegrity <String>] [-DhGroup <String>]
 [-PfsGroup <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini memungkinkan pengguna untuk membuat objek kebijakan ipsec Vpn yang menentukan satu atau semua nilai seperti IpsecEncryption,IpsecIntegrity,IkeEncryption,IkeIntegrity,DhGroup,PfsGroup untuk disetel di gateway VPN. Perintah ini memungkinkan objek output digunakan untuk mengatur kebijakan ipsec vpn untuk gateway baru / yang sudah ada.

## EXAMPLES

### Contoh 1: Tentukan objek kebijakan ipsec vpn:
```powershell
PS C:\>$vpnclientipsecpolicy = New-AzVpnClientIpsecPolicy -IpsecEncryption AES256 -IpsecIntegrity SHA256 -SALifeTime 86472 -SADataSize 429497 -IkeEncryption AES256 -IkeIntegrity SHA256 -DhGroup DHGroup2 -PfsGroup None
```

Cmdlet ini digunakan untuk membuat objek kebijakan ipsec vpn menggunakan satu atau semua nilai parameter yang bisa diberikan pengguna ke param:VpnClientIpsecPolicy perintah PS memungkinkan: New-AzVirtualNetworkGateway (pembuatan Gateway VPN Baru) / Set-AzVirtualNetworkGateway (pembaruan Gateway VPN yang sudah ada) di ResourceGroup:

### Contoh 2: Buat gateway jaringan virtual baru dengan pengaturan kebijakan ipsec kustom vpn:
```powershell
PS C:\> $vnetGateway = New-AzVirtualNetworkGateway -ResourceGroupName vnet-gateway -name myNGW -location $location -IpConfigurations $vnetIpConfig -GatewayType Vpn -VpnType RouteBased -GatewaySku VpnGw1 -VpnClientIpsecPolicy $vpnclientipsecpolicy
```

Cmdlet ini mengembalikan objek gateway jaringan virtual setelah pembuatan. 

### Contoh 3: Set vpn kebijakan ipsec kustom pada gateway jaringan virtual yang sudah ada:
```powershell
PS C:\> $vnetGateway = Set-AzVirtualNetworkGateway -VirtualNetworkGateway $gateway -VpnClientIpsecPolicy $vpnclientipsecpolicy
```

Cmdlet ini mengembalikan objek gateway jaringan virtual setelah mengatur kebijakan ipsec kustom vpn.

### Contoh 4: Dapatkan gateway jaringan virtual untuk melihat apakah kebijakan kustom vpn telah diatur dengan benar:
```powershell
PS C:\> $gateway = Get-AzVirtualNetworkGateway -ResourceGroupName vnet-gateway -name myNGW
```

Cmdlet ini mengembalikan objek gateway jaringan virtual.

## PARAMETERS

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

### -DhGroup
VpnClient DH Groups digunakan di IKE Fase 1 untuk awal SA

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DHGroup24, ECP384, ECP256, DHGroup14, DHGroup2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IkeEncryption
Algoritma enkripsi IKE VpnClient (Fase 2 IKE)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: GCMAES256, GCMAES128, AES256, AES128

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IkeIntegrity
Algoritma integritas IKE VpnClient (Fase 2 IKE)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA384, SHA256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpsecEncryption
Algoritma enkripsi VPNClient IPSec (IKE Fase 1)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: GCMAES256, GCMAES128, AES256, AES128

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpsecIntegrity
Algoritma integritas IPSec VpnClient (Fase 1 IKE)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: GCMAES256, GCMAES128, SHA256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PfsGroup
Grup VpnClient PFS yang digunakan di IKE Fase 2 untuk anak baru SA

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: PFS24, PFSMM, ECP384, ECP256, PFS14, PFS2, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SADataSize
Ukuran muat IpSec Security Association (juga disebut Mode Cepat atau Fase 2 SA) di KB

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

### -SALifeTime
VpnClient IPSec Security Association (juga disebut Mode Cepat atau Fase 2 SA) seumur hidup dalam detik

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSIpsecPolicy

## CATATAN

## RELATED LINKS
