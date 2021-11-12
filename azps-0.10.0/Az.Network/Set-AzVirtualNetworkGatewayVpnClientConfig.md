---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: EFB0D7A6-0C8A-4514-873D-672641CCCAF3
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/set-azvirtualnetworkgatewayvpnclientconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzVirtualNetworkGatewayVpnClientConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzVirtualNetworkGatewayVpnClientConfig.md
ms.openlocfilehash: 1c85bc5e2a935378630728083b19544ace8670b4
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419852"
---
# Set-AzVirtualNetworkGatewayVpnClientConfig

## SYNOPSIS
Mengatur kumpulan alamat klien VPN untuk gateway jaringan virtual.

## SYNTAX

### Default (Default)
```
Set-AzVirtualNetworkGatewayVpnClientConfig -VirtualNetworkGateway <PSVirtualNetworkGateway>
 -VpnClientAddressPool <System.Collections.Generic.List`1[System.String]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RadiusServerConfiguration
```
Set-AzVirtualNetworkGatewayVpnClientConfig -VirtualNetworkGateway <PSVirtualNetworkGateway>
 -VpnClientAddressPool <System.Collections.Generic.List`1[System.String]> -RadiusServerAddress <String>
 -RadiusServerSecret <SecureString> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVirtualNetworkVpnClientConfig** mengonfigurasi kumpulan alamat klien untuk gateway jaringan virtual.
Klien jaringan privat virtual (VPN) yang tersambung ke gateway ini akan diberi alamat IP dari gabungan alamat ini.

## EXAMPLES

### Contoh 1: Menetapkan pool alamat klien VPN ke gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Set-AzVirtualNetworkGatewayVpnClientConfig -VirtualNetworkGateway $Gateway -VpnClientAddressPool "10.0.0.0/16"
```

Contoh ini menetapkan sebuah gabungan alamat klien VPN ke gateway jaringan virtual bernama ContosoVirtualGateway.

Perintah pertama membuat referensi objek ke gateway dan objek disimpan dalam variabel yang bernama $Gateway.

Perintah kedua dalam contoh lalu menggunakan cmdlet **Set-AzVirtualNetworkGatewayVpnClientConfig** untuk menetapkan alamat pool 10.0.0.0/16 ke ContosoVirtualGateway.

### Contoh 2: Mengonfigurasi radius eksternal berdasarkan autentikasi pada gateway yang sudah ada
```
PS C:\>$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> $Secure_String_Pwd = ConvertTo-SecureString "TestRadiusServerPassword" -AsPlainText -Force
PS C:\> Set-AzVirtualNetworkGatewayVpnClientConfig -VirtualNetworkGateway $Gateway -VpnClientAddressPool "10.0.0.0/16" -RadiusServerAddress "TestRadiusServer" -RadiusServerSecret $Secure_String_Pwd
```

Contoh ini menetapkan sebuah gabungan alamat klien VPN ke gateway jaringan virtual bernama ContosoVirtualGateway.

Perintah pertama membuat referensi objek ke gateway dan objek disimpan dalam variabel yang bernama $Gateway.

Perintah kedua dalam contoh lalu menggunakan cmdlet **Set-AzVirtualNetworkGatewayVpnClientConfig** untuk menetapkan alamat pool 10.0.0.0/16 ke ContosoVirtualGateway. Cara ini juga mengonfigurasi server radius eksternal "TestRadiusServer" untuk autentikasi bagi klien vpn.

## PARAMETERS

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

### -RadiusServerAddress
Alamat server Radius Eksternal P2S.

```yaml
Type: String
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
Type: SecureString
Parameter Sets: RadiusServerConfiguration
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual yang berisi pengaturan konfigurasi klien VPN yang dimodifikasi cmdlet ini.
Anda bisa membuat referensi objek ke gateway jaringan virtual dengan menggunakan Get-AzVirtualNetworkGateway dan menentukan nama gateway.

```yaml
Type: PSVirtualNetworkGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VpnClientAddressPool
Menentukan alamat IP yang akan ditetapkan untuk klien yang tersambung ke gateway ini

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

###  
Cmdlet ini menerima contoh pipelined dari objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway.**

## OUTPUTS

###  
Cmdlet ini memodifikasi contoh contoh **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway yang** sudah ada.

## CATATAN

## RELATED LINKS

[Get-AzVpnClientPackage](./Get-AzVpnClientPackage.md)

[Get-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Resize-AzVirtualNetworkGateway](./Resize-AzVirtualNetworkGateway.md)


