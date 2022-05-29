---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 05626BF7-F886-4C76-8FC2-DDF783DEB539
online version: https://docs.microsoft.com/powershell/module/az.network/get-azvpnclientrevokedcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVpnClientRevokedCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVpnClientRevokedCertificate.md
ms.openlocfilehash: 0e7ead10211a5e6499b580488c6ad2e560e52999
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145678864"
---
# Get-AzVpnClientRevokedCertificate

## SYNOPSIS
Mendapatkan informasi tentang sertifikat pencabutan klien VPN.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azvpnclientrevokedcertificate) untuk informasi terbaru.

## SYNTAX

```
Get-AzVpnClientRevokedCertificate [-VpnClientRevokedCertificateName <String>]
 -VirtualNetworkGatewayName <String> -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVpnClientRevokedCertificate** mengembalikan informasi tentang sertifikat pencabutan klien yang ditetapkan ke gateway jaringan virtual.
Sertifikat pencabutan klien mencegah komputer klien menggunakan sertifikat yang ditentukan untuk autentikasi.
**Get-AzVpnClientRevokedCertificate** memungkinkan Anda mengembalikan informasi tentang semua sertifikat pencabutan klien di gateway atau, dengan menggunakan parameter *VpnClientRevokedCertificateName* , untuk mendapatkan informasi tentang satu sertifikat.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang semua sertifikat pencabutan klien
```powershell
Get-AzVpnClientRevokedCertificate -VirtualNetworkGatewayName "ContosoVirtualNetworkGateway" -ResourceGroupName "ContosoResourceGroup"
```

Perintah ini mendapatkan informasi tentang semua sertifikat pencabutan klien yang terkait dengan gateway jaringan virtual bernama ContosoVirtualNetworkGateway.

### Contoh 2: Mendapatkan informasi tentang sertifikat pencabutan klien tertentu
```powershell
Get-AzVpnClientRevokedCertificate -VirtualNetworkGatewayName "ContosoVirtualNetwork" -ResourceGroupName "ContosoResourceGroup" -VpnClientRevokedCertificateName "ContosoRevokedClientCertificate"
```

Perintah ini adalah variasi dari perintah yang ditunjukkan dalam Contoh 1.
Namun, dalam hal ini, parameter *VpnClientRevokedCertificateName* digunakan untuk membatasi data yang dikembalikan ke sertifikat tertentu yang dicabut klien: sertifikat dengan nama ContosoRevokedClientCertificate.

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat gateway jaringan virtual ditetapkan.
Grup sumber daya mengategorikan item untuk membantu menyederhanakan manajemen inventarisasi dan administrasi Azure umum.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGatewayName
Menentukan nama gateway jaringan virtual tempat informasi sertifikat yang dicabut ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VpnClientRevokedCertificateName
Menentukan nama sertifikat klien VPN yang didapat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate

## NOTES

## RELATED LINKS

[Add-AzVpnClientRevokedCertificate](./Add-AzVpnClientRevokedCertificate.md)

[New-AzVpnClientRevokedCertificate](./New-AzVpnClientRevokedCertificate.md)

[Remove-AzVpnClientRevokedCertificate](./Remove-AzVpnClientRevokedCertificate.md)


