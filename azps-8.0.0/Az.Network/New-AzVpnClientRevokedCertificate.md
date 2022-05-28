---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 973E1E53-983F-45A7-A7CF-18A8D96EC4E6
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientrevokedcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRevokedCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRevokedCertificate.md
ms.openlocfilehash: 308c7961f74637142ac2702fd9ad470f02bd47b3
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145556733"
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
Cmdlet **New-AzVpnClientRevokedCertificate** membuat sertifikat pencabutan klien jaringan privat virtual (VPN) baru untuk digunakan pada gateway jaringan virtual.
Sertifikat pencabutan klien mencegah komputer klien menggunakan sertifikat yang ditentukan untuk autentikasi.
Cmdlet ini membuat sertifikat yang berdiri sendiri yang tidak ditetapkan ke gateway virtual.
Sebagai gantinya, sertifikat yang dibuat oleh **New-AzVpnClientRevokedCertificate** digunakan bersama dengan cmdlet New-AzVirtualNetworkGateway saat membuat gateway baru.
Misalnya, Anda membuat sertifikat baru dan menyimpannya dalam variabel bernama $Certificate.
Anda kemudian dapat menggunakan objek sertifikat tersebut saat membuat gateway virtual baru.
Contohnya, `New-AzVirtualNetworkGateway -Name "ContosoVirtualGateway" -ResourceGroupName "ContosoResourceGroup" -Location "West US" -GatewayType "VPN" -IpConfigurations $Ipconfig  -VPNType "RouteBased" -VpnClientRevokedCertificates $Certificate`
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzVirtualNetworkGateway.

## EXAMPLES

### Contoh 1: Membuat sertifikat baru yang dicabut kliennya
```powershell
$Certificate = New-AzVpnClientRevokedCertificate -Name "ContosoClientRevokedCertificate" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
```

Perintah ini membuat sertifikat baru yang dicabut klien dan menyimpan objek sertifikat dalam variabel bernama $Certificate.
Variabel ini kemudian dapat digunakan oleh cmdlet **New-AzVirtualNetworkGateway** untuk menambahkan sertifikat ke gateway jaringan virtual baru.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Name
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
Anda dapat mengembalikan informasi thumbprint untuk sertifikat Anda dengan menggunakan perintah Windows PowerShell yang mirip dengan ini:`Get-ChildItem -Path Cert:\LocalMachine\Root`
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate

## NOTES

## RELATED LINKS

[Add-AzVpnClientRevokedCertificate](./Add-AzVpnClientRevokedCertificate.md)

[Get-AzVpnClientRevokedCertificate](./Get-AzVpnClientRevokedCertificate.md)

[Remove-AzVpnClientRevokedCertificate](./Remove-AzVpnClientRevokedCertificate.md)


