---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: C2C5E0C0-E212-4554-966B-940B1B6FE235
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/set-azapplicationgatewaybackendaddresspool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzApplicationGatewayBackendAddressPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzApplicationGatewayBackendAddressPool.md
ms.openlocfilehash: fd9d9c1b7956c16ab981b5426e9453de4d730dd6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143099711"
---
# Set-AzApplicationGatewayBackendAddressPool

## SYNOPSIS
Memperbarui kumpulan alamat ujung belakang untuk gateway aplikasi.

## SYNTAX

```
Set-AzApplicationGatewayBackendAddressPool -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-BackendIPAddresses <System.Collections.Generic.List`1[System.String]>]
 [-BackendFqdns <System.Collections.Generic.List`1[System.String]>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApplicationGatewayBackendAddressPool** memperbarui kumpulan alamat ujung belakang untuk gateway aplikasi Azure.
Alamat ujung belakang dapat ditentukan sebagai alamat IP, nama domain yang sepenuhnya memenuhi syarat (FQDN) atau ID konfigurasi IP.

## EXAMPLES

### Contoh 1: Mengatur kumpulan alamat ujung belakang menggunakan FQDN
```
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewayBackendAddressPool -ApplicationGateway $AppGw -Name "Pool02" -BackendFqdns "contoso1.com", "contoso2.com"
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.

Perintah kedua memperbarui kumpulan alamat ujung belakang gateway aplikasi di $AppGw menggunakan FQDN.

### Contoh 2: Mengatur kumpulan alamat back-end dengan menggunakan alamat IP server backend
```
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewayBackendAddressPool -ApplicationGateway $AppGw -Name "Pool02" -BackendIPAddresses "10.10.10.10", "10.10.10.11"
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.

Perintah kedua memperbarui kumpulan alamat ujung belakang gateway aplikasi di $AppGw menggunakan alamat IP.

### Contoh 3: Mengatur kumpulan alamat ujung belakang menggunakan ID alamat IP server backend?s
```
PS C:\> $Nic01 = Get-AzNetworkInterface -Name "Nic01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Nic02 = Get-AzNetworkInterface -Name "Nic02" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewayBackendAddressPool -ApplicationGateway $AppGw -Name "Pool02" -BackendIPConfigurationIds $nic01.Properties.IpConfigurations[0].Id, $nic02.Properties.IpConfiguration[0].Id
```

Perintah pertama mendapatkan objek antarmuka jaringan bernama Nic01 yang termasuk dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $Nic 01.

Perintah kedua mendapatkan objek antarmuka jaringan bernama Nic02 yang termasuk dalam grup sumber daya bernama ResourceGroup02, dan menyimpannya dalam variabel $Nic 02.

Perintah ketiga mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw.

Perintah keempat menggunakan ID konfigurasi IP ujung-belakang dari $Nic 01 dan $Nic 02 untuk memperbarui kumpulan alamat ujung belakang gateway aplikasi di $AppGw.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat cmdlet ini mengaitkan kumpulan alamat ujung belakang.

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackendFqdns
Menentukan daftar alamat IP ujung-belakang untuk digunakan sebagai kumpulan server back-end.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendIPAddresses
```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Nama
Menentukan nama kumpulan alamat ujung-belakang.
Kumpulan alamat ujung belakang ini harus ada di gateway aplikasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewayBackendAddressPool](./Add-AzApplicationGatewayBackendAddressPool.md)

[Get-AzApplicationGatewayBackendAddressPool](./Get-AzApplicationGatewayBackendAddressPool.md)

[New-AzApplicationGatewayBackendAddressPool](./New-AzApplicationGatewayBackendAddressPool.md)

[Remove-AzApplicationGatewayBackendAddressPool](./Remove-AzApplicationGatewayBackendAddressPool.md)


