---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 5C309071-A2ED-464C-9197-0A77859C8FBB
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmVirtualNetworkGateway.md
ms.openlocfilehash: 41c94d0dd8401399f360af89f1744cc10e900e1a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428819"
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
 [-Asn <UInt32>] [-PeerWeight <Int32>] [-EnableActiveActiveFeature] [-DisableActiveActiveFeature]
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
 [-Asn <UInt32>] [-PeerWeight <Int32>] [-EnableActiveActiveFeature] [-DisableActiveActiveFeature]
 -RadiusServerAddress <String> -RadiusServerSecret <SecureString> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVirtualNetworkGateway** memperbarui gateway jaringan virtual.

## EXAMPLES

### Contoh 1: Menetapkan status tujuan gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzureRmVirtualNetworkGateway -ResourceGroupName "ResourceGroup001" -Name "Gateway001"
PS C:\> Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $Gateway -Asn 1337
```

Perintah pertama mendapatkan gateway jaringan virtual bernama Gateway01 yang dimiliki oleh grup sumber daya ResourceGroup001 dan menyimpannya ke variabel yang bernama $Gateway

Perintah kedua mengatur status tujuan untuk gateway jaringan virtual yang disimpan dalam variabel $Gateway.
Perintah juga mengatur ASN ke 1337.

## PARAMETERS

### -Asn
Menentukan gateway jaringan virtual Nomor Sistem (ASN) yang digunakan untuk menyiapkan sesi Border Gateway Protocol (BGP) dalam IPsec.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.
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
Menonaktifkan fitur aktif.

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
Mengaktifkan fitur aktif.

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
Menentukan situs default yang akan digunakan untuk memaksakan.
Jika situs default ditentukan, semua lalu lintas internet dari Jaringan Privat Virtual (VPN, Virtual Private Network) gateway dirutekan ke situs itu.

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

### -GatewaySku
Menentukan unit stock keeping unit (SKU) dari gateway jaringan virtual.
Nilai yang dapat diterima untuk parameter ini adalah:

- Dasar
- Standar
- HighPerformance
- VpnGw1
- VpnGw2
- VpnGw3

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 
Accepted values: Basic, Standard, HighPerformance, UltraPerformance, VpnGw1, VpnGw2, VpnGw3

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PeerWeight
Menentukan bobot yang ditambahkan ke rute yang dipelajari melalui BGP dari gateway jaringan virtual ini

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
Menentukan objek gateway jaringan virtual untuk membuat modifikasi dasar.
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
Menentukan ruang alamat yang digunakan cmdlet untuk mengalokasikan alamat IP klien VPN.
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

### -VpnClientProtocol
Daftar protokol klien P2S VPN
```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 
Accepted values: SSTP, IkeV2

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
Klien VPN yang terhubung harus menyajikan sertifikat yang dihasilkan dari salah satu sertifikat akar ini.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSVirtualNetworkGateway
Parameter 'VirtualNetworkGateway' menerima nilai tipe 'PSVirtualNetworkGateway' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmVirtualNetworkGateway](./Get-AzureRmVirtualNetworkGateway.md)

[New-AzureRmVirtualNetworkGateway](./New-AzureRmVirtualNetworkGateway.md)

[Remove-AzureRmVirtualNetworkGateway](./Remove-AzureRmVirtualNetworkGateway.md)

[Reset-AzureRmVirtualNetworkGateway](./Reset-AzureRmVirtualNetworkGateway.md)

[Resize-AzureRmVirtualNetworkGateway](./Resize-AzureRmVirtualNetworkGateway.md)


