---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientipsecpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientIpsecPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientIpsecPolicy.md
ms.openlocfilehash: 9fb62db30a588b06c62851452511929a57e2d617
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144621660"
---
# New-AzVpnClientIpsecPolicy

## SYNOPSIS
Perintah ini memungkinkan pengguna untuk membuat objek kebijakan Vpn ipsec yang menentukan satu atau semua nilai seperti IpsecEncryption,IpsecIntegrity,IkeEncryption,IkeIntegrity,DhGroup,PfsGroup untuk diatur pada gateway VPN. Perintah ini memungkinkan objek output digunakan untuk mengatur kebijakan ipsec vpn untuk gateway baru/yang sudah ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azvpnclientipsecpolicy) untuk informasi terbaru.

## SYNTAX

```
New-AzVpnClientIpsecPolicy [-SALifeTime <Int32>] [-SADataSize <Int32>] [-IpsecEncryption <String>]
 [-IpsecIntegrity <String>] [-IkeEncryption <String>] [-IkeIntegrity <String>] [-DhGroup <String>]
 [-PfsGroup <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini memungkinkan pengguna untuk membuat objek kebijakan Vpn ipsec yang menentukan satu atau semua nilai seperti IpsecEncryption,IpsecIntegrity,IkeEncryption,IkeIntegrity,DhGroup,PfsGroup untuk diatur pada gateway VPN. Perintah ini memungkinkan objek output digunakan untuk mengatur kebijakan ipsec vpn untuk gateway baru/yang sudah ada.

## EXAMPLES

### Contoh 1: Tentukan objek kebijakan ipsec vpn:
```powershell
$vpnclientipsecpolicy = New-AzVpnClientIpsecPolicy -IpsecEncryption AES256 -IpsecIntegrity SHA256 -SALifeTime 86472 -SADataSize 429497 -IkeEncryption AES256 -IkeIntegrity SHA256 -DhGroup DHGroup2 -PfsGroup None
```

Cmdlet ini digunakan untuk membuat objek kebijakan ipsec vpn menggunakan nilai satu atau semua parameter yang diteruskan yang dapat diteruskan pengguna ke param:VpnClientIpsecPolicy dari perintah PS memungkinkan: New-AzVirtualNetworkGateway (Pembuatan VPN Gateway baru) / Set-AzVirtualNetworkGateway (pembaruan VPN Gateway yang ada) di ResourceGroup :

### Contoh 2: Buat gateway jaringan virtual baru dengan mengatur kebijakan ipsec kustom vpn:
```powershell
$vnetGateway = New-AzVirtualNetworkGateway -ResourceGroupName vnet-gateway -name myNGW -location $location -IpConfigurations $vnetIpConfig -GatewayType Vpn -VpnType RouteBased -GatewaySku VpnGw1 -VpnClientIpsecPolicy $vpnclientipsecpolicy
```

Cmdlet ini mengembalikan objek gateway jaringan virtual setelah pembuatan. 

### Contoh 3: Atur kebijakan ipsec kustom vpn pada gateway jaringan virtual yang ada:
```powershell
$vnetGateway = Set-AzVirtualNetworkGateway -VirtualNetworkGateway $gateway -VpnClientIpsecPolicy $vpnclientipsecpolicy
```

Cmdlet ini mengembalikan objek gateway jaringan virtual setelah mengatur kebijakan ipsec kustom vpn.

### Contoh 4: Dapatkan gateway jaringan virtual untuk melihat apakah kebijakan kustom vpn diatur dengan benar:
```powershell
$gateway = Get-AzVirtualNetworkGateway -ResourceGroupName vnet-gateway -name myNGW
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
Grup VpnClient DH yang digunakan dalam IKE Fase 1 untuk SA awal

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
Algoritma enkripsi VpnClient IKE (IKE Fase 2)

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
Algoritma integritas IKE VpnClient (IKE Fase 2)

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
Algoritma integritas VpnClient IPSec (IKE Fase 1)

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
Grup PFS VpnClient yang digunakan dalam IKE Fase 2 untuk SA anak baru

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
Ukuran payload VpnClient IPSec Security Association (juga disebut Mode Cepat atau Fase 2 SA) dalam KB

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
Asosiasi Keamanan VPNClient IPSec (juga disebut Mode Cepat atau Fase 2 SA) seumur hidup dalam hitungan detik

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

## NOTES

## RELATED LINKS
