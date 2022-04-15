---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 5C309071-A2ED-464C-9197-0A77859C8FBB
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermvirtualnetworkgateway
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGateway.md
ms.openlocfilehash: 1884dd461c0433c4f6a68bf906f56653ca960e27
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142385166"
---
# Set-AzureRmVirtualNetworkGateway

## SYNOPSIS
Memperbarui gateway jaringan virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Default (Default)
```
Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway <PSVirtualNetworkGateway> [-GatewaySku <String>]
 [-GatewayDefaultSite <PSLocalNetworkGateway>]
 [-VpnClientAddressPool <System.Collections.Generic.List`1[System.String]>]
 [-VpnClientProtocol <System.Collections.Generic.List`1[System.String]>]
 [-VpnClientRootCertificates <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate]>]
 [-VpnClientRevokedCertificates <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate]>]
 [-VpnClientIpsecPolicy <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSIpsecPolicy]>]
 [-Asn <UInt32>] [-PeerWeight <Int32>] [-EnableActiveActiveFeature] [-DisableActiveActiveFeature] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RadiusServerConfiguration
```
Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway <PSVirtualNetworkGateway> [-GatewaySku <String>]
 [-GatewayDefaultSite <PSLocalNetworkGateway>]
 [-VpnClientAddressPool <System.Collections.Generic.List`1[System.String]>]
 [-VpnClientProtocol <System.Collections.Generic.List`1[System.String]>]
 [-VpnClientRootCertificates <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate]>]
 [-VpnClientRevokedCertificates <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate]>]
 [-VpnClientIpsecPolicy <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSIpsecPolicy]>]
 [-Asn <UInt32>] [-PeerWeight <Int32>] [-EnableActiveActiveFeature] [-DisableActiveActiveFeature]
 -RadiusServerAddress <String> -RadiusServerSecret <SecureString> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVirtualNetworkGateway** memperbarui gateway jaringan virtual.

## EXAMPLES

### Contoh 1: Mengatur status tujuan gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzureRmVirtualNetworkGateway -ResourceGroupName "ResourceGroup001" -Name "Gateway001"
PS C:\> Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $Gateway -Asn 1337
```

Perintah pertama mendapatkan gateway jaringan virtual bernama Gateway01 milik grup sumber daya ResourceGroup001 dan menyimpannya ke variabel bernama $Gateway Perintah kedua mengatur status tujuan untuk gateway jaringan virtual yang disimpan dalam variabel $Gateway.
Perintah juga mengatur ASN ke 1337.

### Contoh 2: Mengatur status tujuan gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzureRmVirtualNetworkGateway -ResourceGroupName "ResourceGroup001" -Name "Gateway001"
PS C:\> $vpnclientipsecpolicy = New-AzureRmVpnClientIpsecPolicy -IpsecEncryption AES256 -IpsecIntegrity SHA256 -SALifeTimeSeconds 86472 -SADataSizeKilobytes 429497 -IkeEncryption AES256 -IkeIntegrity SHA256 -DhGroup DHGroup2 -PfsGroup None
PS C:\> $gateway = Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $Gateway -VpnClientIpsecPolicy $vpnclientipsecpolicy
```

Perintah pertama mendapatkan gateway jaringan virtual bernama Gateway01 milik grup sumber daya ResourceGroup001 dan menyimpannya ke variabel bernama $Gateway Perintah kedua membuat objek kebijakan ipsec Vpn sesuai parameter ipsec tertentu.
Perintah ketiga mengatur status tujuan untuk gateway jaringan virtual yang disimpan dalam variabel $Gateway.
Perintah ini juga mengatur kebijakan ipsec vpn kustom yang ditentukan dalam objek $vpnclientipsecpolicy di gateway jaringan virtual.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -Asn
Menentukan gateway jaringan virtual Autonomous System Number (ASN) yang digunakan untuk menyiapkan sesi Border Gateway Protocol (BGP) di dalam terowongan IPsec.

```yaml
Type: System.UInt32
Parameter Sets: (All)
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableActiveActiveFeature
Menonaktifkan fitur aktif-aktif.

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

### -EnableActiveActiveFeature
Mengaktifkan fitur aktif-aktif.

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

### -GatewayDefaultSite
Menentukan situs default yang akan digunakan untuk membuat terowongan paksa.
Jika situs default ditentukan, semua lalu lintas internet dari Jaringan Privat Virtual (VPN) gateway dirutekan ke situs tersebut.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSLocalNetworkGateway
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Gatewaysku
Menentukan stock keeping unit (SKU) gateway jaringan virtual.
Nilai yang dapat diterima untuk parameter ini adalah:
- Dasar
- Standar
- HighPerformance
- VpnGw1
- VpnGw2
- VpnGw3
- VpnGw1AZ
- VpnGw2AZ
- VpnGw3AZ
- ErGw1AZ
- ErGw2AZ
- ErGw3AZ

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard, HighPerformance, UltraPerformance, VpnGw1, VpnGw2, VpnGw3, VpnGw1AZ, VpnGw2AZ, VpnGw3AZ, ErGw1AZ, ErGw2AZ, ErGw3AZ

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PeerWeight
Menentukan berat yang ditambahkan ke rute yang dipelajari melalui BGP dari gateway jaringan virtual ini

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusServerAddress
Alamat server Radius Eksternal P2S.

```yaml
Type: System.String
Parameter Sets: RadiusServerConfiguration
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusServerSecret
Rahasia server Radius Eksternal P2S.

```yaml
Type: System.Security.SecureString
Parameter Sets: RadiusServerConfiguration
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGateway
Menentukan objek gateway jaringan virtual ke modifikasi dasar nonaktif.
Anda bisa menggunakan cmdlet Get-AzureRmVirtualNetworkGateway untuk mendapatkan objek gateway jaringan virtual.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VpnClientAddressPool
Menentukan ruang alamat yang digunakan cmdlet ini untuk mengalokasikan alamat IP klien VPN.
Ini tidak boleh tumpang tindih dengan jaringan virtual atau rentang lokal.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VpnClientIpsecPolicy
Daftar kebijakan IPSec untuk protokol tunneling klien P2S VPN.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSIpsecPolicy]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VpnClientProtocol
Daftar protokol tunneling klien P2S VPN

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:
Accepted values: SSTP, IkeV2, OpenVPN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VpnClientRevokedCertificates
Menentukan daftar sertifikat klien VPN yang dicabut.
Klien VPN yang menyajikan sertifikat yang cocok dengan salah satu hal ini dihapus.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VpnClientRootCertificates
Menentukan daftar sertifikat akar klien VPN yang akan digunakan untuk autentikasi klien VPN.
Menghubungkan klien VPN harus menyajikan sertifikat yang dihasilkan dari salah satu sertifikat akar ini.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway
Parameter: VirtualNetworkGateway (ByValue)

### System.String

### Microsoft.Azure.Commands.Network.Models.PSLocalNetworkGateway

### System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate, Microsoft.Azure.Commands.Network, Version=6.4.1.0, Culture=netral, PublicKeyToken=null]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate, Microsoft.Azure.Commands.Network, Version=6.4.1.0, Culture=netral, PublicKeyToken=null]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.PSIpsecPolicy, Microsoft.Azure.Commands.Network, Version=6.4.1.0, Culture=netral, PublicKeyToken=null]]

### System.UInt32

### System.Int32

### System.Security.SecureString

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## CATATAN
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, jaringan, jaringan

## RELATED LINKS

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[New-AzureRmVirtualNetworkGateway](./New-AzureRmVirtualNetworkGateway.md)

[Hapus-AzureRmVirtualNetworkGateway](./Remove-AzureRmVirtualNetworkGateway.md)

[Mengatur ulang AzureRmVirtualNetworkGateway](./Reset-AzureRmVirtualNetworkGateway.md)

[Mengubah ukuran AzureRmVirtualNetworkGateway](./Resize-AzureRmVirtualNetworkGateway.md)


