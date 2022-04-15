---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 973E1E53-983F-45A7-A7CF-18A8D96EC4E6
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientrevokedcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRevokedCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRevokedCertificate.md
ms.openlocfilehash: 2ccd2f1f3916e98ea3ed3a7c1087a9bef69503b5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142227871"
---
# New-AzVpnClientRevokedCertificate

## SYNOPSIS
Membuat sertifikat pembatalan klien VPN baru.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azvpnclientrevokedcertificate) untuk informasi terbaru.

## SYNTAX

```
New-AzVpnClientRevokedCertificate -Name <String> -Thumbprint <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVpnClientRevokedCertificate** membuat sertifikat pembatalan klien (VPN) jaringan privat virtual baru untuk digunakan di gateway jaringan virtual.
Sertifikat pembatalan klien mencegah komputer klien menggunakan sertifikat tertentu untuk autentikasi.
Cmdlet ini membuat sertifikat mandiri yang tidak ditetapkan ke gateway virtual.
Sebagai gantinya, sertifikat yang dibuat oleh **New-AzVpnClientRevokedCertificate** digunakan bersama dengan cmdlet New-AzVirtualNetworkGateway saat membuat gateway baru.
Misalnya, Anda membuat sertifikat baru dan menyimpannya dalam variabel bernama $Certificate.
Anda kemudian bisa menggunakan objek sertifikat itu saat Anda membuat gateway virtual baru.
Misalnya, `New-AzVirtualNetworkGateway -Name "ContosoVirtualGateway" -ResourceGroupName "ContosoResourceGroup" -Location "West US" -GatewayType "VPN" -IpConfigurations $Ipconfig  -VPNType "RouteBased" -VpnClientRevokedCertificates $Certificate`
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzVirtualNetworkGateway.

## EXAMPLES

### Contoh 1: Membuat sertifikat klien baru yang dicabut
```
PS C:\>$Certificate = New-AzVpnClientRevokedCertificate -Name "ContosoClientRevokedCertificate" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
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

### -Nama
Menentukan nama unik untuk sertifikat pembatalan klien baru.

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

### -Sidik jari
Menentukan pengidentifikasi unik sertifikat yang ditambahkan.
Anda bisa mengembalikan informasi sidik jari untuk sertifikat Anda dengan menggunakan perintah Windows PowerShell seperti ini:`Get-ChildItem -Path Cert:\LocalMachine\Root`
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate

## CATATAN

## RELATED LINKS

[Add-AzVpnClientRevokedCertificate](./Add-AzVpnClientRevokedCertificate.md)

[Get-AzVpnClientRevokedCertificate](./Get-AzVpnClientRevokedCertificate.md)

[Remove-AzVpnClientRevokedCertificate](./Remove-AzVpnClientRevokedCertificate.md)


