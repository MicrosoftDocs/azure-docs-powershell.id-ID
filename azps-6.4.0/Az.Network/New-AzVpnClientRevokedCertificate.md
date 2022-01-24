---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 973E1E53-983F-45A7-A7CF-18A8D96EC4E6
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientrevokedcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRevokedCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRevokedCertificate.md
ms.openlocfilehash: edccb2aa85da11c8e1789c142da7e35a714ff47f
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136210734"
---
# New-AzVpnClientRevokedCertificate

## SYNOPSIS
Membuat sertifikat pencabutan klien VPN baru.

## SYNTAX

```
New-AzVpnClientRevokedCertificate -Name <String> -Thumbprint <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVpnClientRevokedCertificate** membuat sertifikat pencabutan klien jaringan privat virtual (VPN) baru untuk digunakan di gateway jaringan virtual.
Sertifikat pencabutan klien mencegah komputer klien menggunakan sertifikat yang ditentukan untuk autentikasi.
Cmdlet ini membuat sertifikat mandiri yang tidak ditetapkan ke gateway virtual.
Sebagai gantinya, sertifikat yang dibuat **oleh New-AzVpnClientRevokedCertificate** digunakan sehubungan dengan cmdlet New-AzVirtualNetworkGateway saat membuat gateway baru.
Misalnya, anggaplah Anda membuat sertifikat baru dan menyimpannya di variabel yang bernama $Certificate.
Anda lalu bisa menggunakan objek sertifikat tersebut saat Anda membuat gateway virtual baru.
Sebagai contoh, `New-AzVirtualNetworkGateway -Name "ContosoVirtualGateway" -ResourceGroupName "ContosoResourceGroup" -Location "West US" -GatewayType "VPN" -IpConfigurations $Ipconfig  -VPNType "RouteBased" -VpnClientRevokedCertificates $Certificate`
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzVirtualNetworkGateway baru.

## EXAMPLES

### Contoh 1: Membuat sertifikat baru yang dicabut klien
```
PS C:\>$Certificate = New-AzVpnClientRevokedCertificate -Name "ContosoClientRevokedCertificate" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
```

Perintah ini membuat sertifikat baru yang dicabut klien dan menyimpan objek sertifikat dalam variabel yang bernama $Certificate.
Variabel ini lalu bisa digunakan oleh cmdlet **New-AzVirtualNetworkGateway** untuk menambahkan sertifikat ke gateway jaringan virtual baru.

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

### -Nama
Menentukan nama unik untuk sertifikat pencabutan klien baru.

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

### -Thumbprint
Menentukan pengidentifikasi unik sertifikat yang ditambahkan.
Anda dapat mengembalikan informasi yang dapat dicetak dengan jempol pada sertifikat menggunakan Windows PowerShell seperti ini:`Get-ChildItem -Path Cert:\LocalMachine\Root`
Perintah sebelumnya mengembalikan informasi untuk semua sertifikat Komputer Lokal yang ditemukan di penyimpanan sertifikat Akar.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate

## CATATAN

## RELATED LINKS

[Add-AzVpnClientRevokedCertificate](./Add-AzVpnClientRevokedCertificate.md)

[Get-AzVpnClientRevokedCertificate](./Get-AzVpnClientRevokedCertificate.md)

[Remove-AzVpnClientRevokedCertificate](./Remove-AzVpnClientRevokedCertificate.md)


