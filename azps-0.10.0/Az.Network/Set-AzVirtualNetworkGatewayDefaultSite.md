---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: A27EE9C0-C7F5-4BF6-AE52-58087BD1B1C3
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/set-azvirtualnetworkgatewaydefaultsite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzVirtualNetworkGatewayDefaultSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Set-AzVirtualNetworkGatewayDefaultSite.md
ms.openlocfilehash: 560053ca6b5e49ffcef8dbb6ee4b0ba32f3ed276
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142781236"
---
# Set-AzVirtualNetworkGatewayDefaultSite

## SYNOPSIS
Mengatur situs default untuk gateway jaringan virtual.

## SYNTAX

```
Set-AzVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway <PSVirtualNetworkGateway>
 -GatewayDefaultSite <PSLocalNetworkGateway> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVirtualNetworkGatewayDefaultSite** menetapkan situs default penerowongan paksa ke gateway jaringan virtual.
Penerowongan paksa menyediakan cara bagi Anda untuk mengalihkan lalu lintas yang terikat Internet dari komputer virtual Azure ke jaringan lokal Anda; ini memungkinkan Anda memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Penerowongan paksa dilakukan dengan menggunakan terowongan jaringan privat maya (VPN) ; terowongan ini memerlukan situs default, gateway lokal tempat semua lalu lintas terikat Internet Azure dialihkan.
**Set-AzVirtualNetworkGatewayDefaultSite** menyediakan cara untuk mengubah situs default yang ditetapkan ke gateway.

## EXAMPLES

### Contoh 1: Menetapkan situs default ke gateway jaringan virtual
```
PS C:\>$LocalGateway = Get-AzLocalNetworkGateway -Name "ContosoLocalGateway " -ResourceGroup "ContosoResourceGroup"
PS C:\> $VirtualGateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
PS C:\> Set-AzVirtualNetworkGatewayDefaultSite -GatewayDefaultSite $LocalGateway -VirtualNetworkGateway $VirtualGateway
```

Contoh ini menetapkan situs default ke gateway jaringan virtual bernama ContosoVirtualGateway.

Perintah pertama membuat referensi objek ke gateway lokal bernama ContosoLocalGateway.
Referensi objek yang disimpan dalam variabel bernama $LocalGateway mewakili gateway yang akan dikonfigurasi sebagai situs default

.
Perintah kedua kemudian membuat referensi objek ke gateway jaringan virtual dan menyimpan hasilnya dalam variabel bernama $VirtualGateway.

Perintah ketiga menggunakan cmdlet **Set-AzVirtualNetworkGatewayDefaultSite** untuk menetapkan situs default ke ContosoVirtualGateway.

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

### -GatewayDefaultSite
Menentukan referensi objek ke gateway jaringan lokal yang akan ditetapkan sebagai situs default untuk jaringan virtual yang ditentukan.
Anda bisa menggunakan cmdlet Get-AzLocalNetworkGateway untuk membuat referensi objek ke gateway lokal.

```yaml
Type: PSLocalNetworkGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual tempat situs default akan ditetapkan.
Anda dapat membuat referensi objek ke gateway jaringan virtual dengan menggunakan **Get-AzVirtualNetworkGateway** dan menentukan nama gateway.

Variabel $VirtualGateway kemudian dapat digunakan sebagai nilai parameter untuk parameter *VirtualNetworkGateway* :

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Cmdlet ini menerima instans yang disalurkan dari objek **Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway** .

## OUTPUTS

###  
Cmdlet ini memodifikasi instans **objek Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway yang ada** .

## NOTES

## RELATED LINKS

[Get-AzLocalNetworkGateway](./Get-AzLocalNetworkGateway.md)

[Dapatkan-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Remove-AzVirtualNetworkGatewayDefaultSite](./Remove-AzVirtualNetworkGatewayDefaultSite.md)


