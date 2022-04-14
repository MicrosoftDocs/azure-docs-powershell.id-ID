---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 05626BF7-F886-4C76-8FC2-DDF783DEB539
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermvpnclientrevokedcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmVpnClientRevokedCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmVpnClientRevokedCertificate.md
ms.openlocfilehash: bb6a4c13b65697de624e9a9913e2f0f9cc6ea476
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141778230"
---
# Get-AzureRmVpnClientRevokedCertificate

## SYNOPSIS
Mendapatkan informasi tentang sertifikat pembatalan klien VPN.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmVpnClientRevokedCertificate [-VpnClientRevokedCertificateName <String>]
 -VirtualNetworkGatewayName <String> -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVpnClientRevokedCertificate** mengembalikan informasi tentang sertifikat pembatalan klien yang ditetapkan ke gateway jaringan virtual.
Sertifikat pembatalan klien mencegah komputer klien menggunakan sertifikat tertentu untuk autentikasi.
**Get-AzureRmVpnClientRevokedCertificate** memungkinkan Anda mengembalikan informasi tentang semua sertifikat pembatalan klien di gateway atau, dengan menggunakan parameter *VpnClientRevokedCertificateName* , untuk mendapatkan informasi tentang satu sertifikat.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua sertifikat pembatalan klien
```
PS C:\>Get-AzureRmVpnClientRevokedCertificate -VirtualNetworkGatewayName "ContosoVirtualNetworkGateway" -ResourceGroupName "ContosoResourceGroup"
```

Perintah ini mendapatkan informasi tentang semua sertifikat pembatalan klien yang terkait dengan gateway jaringan virtual bernama ContosoVirtualNetworkGateway.

### Contoh 2: Dapatkan informasi tentang sertifikat pembatalan klien tertentu
```
PS C:\>Get-AzureRmVpnClientRevokedCertificate -VirtualNetworkGatewayName "ContosoVirtualNetwork" -ResourceGroupName "ContosoResourceGroup" -VpnClientRevokedCertificateName "ContosoRevokedClientCertificate"
```

Perintah ini adalah variasi perintah yang diperlihatkan dalam Contoh 1.
Namun, dalam hal ini, parameter *VpnClientRevokedCertificateName* digunakan untuk membatasi data yang dikembalikan ke sertifikat klien tertentu yang dicabut: sertifikat dengan nama ContosoRevokedClientCertificate.

## PARAMETERS

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat gateway jaringan maya ditetapkan.
Grup sumber daya mengkategorikan item untuk membantu menyederhanakan manajemen inventaris dan administrasi Umum Azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate

## CATATAN

## RELATED LINKS

[Add-AzureRmVpnClientRevokedCertificate](./Add-AzureRmVpnClientRevokedCertificate.md)

[New-AzureRmVpnClientRevokedCertificate](./New-AzureRmVpnClientRevokedCertificate.md)

[Hapus-AzureRmVpnClientRevokedCertificate](./Remove-AzureRmVpnClientRevokedCertificate.md)


