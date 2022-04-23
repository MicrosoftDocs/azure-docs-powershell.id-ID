---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: EFB0D7A6-0C8A-4514-873D-672641CCCAF3
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/set-azvirtualnetworkgatewayvpnclientconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzVirtualNetworkGatewayVpnClientConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzVirtualNetworkGatewayVpnClientConfig.md
ms.openlocfilehash: 1c85bc5e2a935378630728083b19544ace8670b4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143099603"
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
Klien jaringan privat virtual (VPN) yang tersambung ke gateway ini akan diberi alamat IP dari kumpulan alamat ini.

## EXAMPLES

### Contoh 1: Menetapkan kumpulan alamat klien VPN ke gateway jaringan virtual
```
PS C:\>$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Set-AzVirtualNetworkGatewayVpnClientConfig -VirtualNetworkGateway $Gateway -VpnClientAddressPool "10.0.0.0/16"
```

Contoh ini menetapkan kumpulan alamat klien VPN ke gateway jaringan virtual bernama ContosoVirtualGateway.

Perintah pertama membuat referensi objek ke gateway dan objek disimpan dalam variabel bernama $Gateway.

Perintah kedua dalam contoh lalu menggunakan cmdlet **Set-AzVirtualNetworkGatewayVpnClientConfig** untuk menetapkan kumpulan alamat 10.0.0.0/16 ke ContosoVirtualGateway.

### Contoh 2: Mengonfigurasi autentikasi berbasis radius eksternal pada gateway yang sudah ada
```
PS C:\>$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> $Secure_String_Pwd = ConvertTo-SecureString "TestRadiusServerPassword" -AsPlainText -Force
PS C:\> Set-AzVirtualNetworkGatewayVpnClientConfig -VirtualNetworkGateway $Gateway -VpnClientAddressPool "10.0.0.0/16" -RadiusServerAddress "TestRadiusServer" -RadiusServerSecret $Secure_String_Pwd
```

Contoh ini menetapkan kumpulan alamat klien VPN ke gateway jaringan virtual bernama ContosoVirtualGateway.

Perintah pertama membuat referensi objek ke gateway dan objek disimpan dalam variabel bernama $Gateway.

Perintah kedua dalam contoh lalu menggunakan cmdlet **Set-AzVirtualNetworkGatewayVpnClientConfig** untuk menetapkan kumpulan alamat 10.0.0.0/16 ke ContosoVirtualGateway. Ini juga mengonfigurasi server radius eksternal "TestRadiusServer" yang akan digunakan untuk autentikasi untuk klien vpn.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan referensi objek ke gateway jaringan virtual yang berisi pengaturan konfigurasi klien VPN yang diubah cmdlet ini.
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
Menentukan alamat IP yang akan ditetapkan ke klien yang tersambung ke gateway ini

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Cmdlet ini menerima instans pipelin objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway** .

## OUTPUTS

###  
Cmdlet ini mengubah instans objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway** yang sudah ada.

## NOTES

## RELATED LINKS

[Get-AzVpnClientPackage](./Get-AzVpnClientPackage.md)

[Get-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Mengubah ukuran-AzVirtualNetworkGateway](./Resize-AzVirtualNetworkGateway.md)


