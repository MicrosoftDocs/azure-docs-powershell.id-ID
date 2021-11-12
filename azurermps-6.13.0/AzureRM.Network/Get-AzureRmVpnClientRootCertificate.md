---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 16754F70-9619-4F68-86E9-5C8B27812707
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmVpnClientRootCertificate.md
ms.openlocfilehash: 6303aeac769b2303e8ebbd67a237d2eaf99ed9cc
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422942"
---
# Get-AzureRmVpnClientRootCertificate

## SYNOPSIS
Mendapatkan informasi tentang sertifikat akar VPN.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmVpnClientRootCertificate [-VpnClientRootCertificateName <String>]
 -VirtualNetworkGatewayName <String> -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVpnClientRootCertificate** mengembalikan informasi tentang sertifikat akar yang ditetapkan untuk gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan di gateway mempercayai sertifikat akar.
Secara default, **Get-AzureRmVpnClientRootCertificate** mengembalikan informasi tentang semua sertifikat akar yang ditetapkan untuk gateway.
(Gateway bisa memiliki lebih dari satu sertifikat akar.) Namun, dengan menyertakan parameter **VpnClientRootCertificateName** Anda bisa membatasi data yang dikembalikan menjadi sertifikat tertentu.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua sertifikat akar
```
PS C:\>Get-AzureRmVpnClientRootCertificate -VirtualNetworkGatewayName "ContosoVirtualNetwork" -ResourceGroupName "ContosoResourceGroup"
```

Perintah ini mendapatkan informasi tentang semua sertifikat akar yang ditetapkan ke gateway jaringan virtual bernama ContosoVirtualNetwork.

### Contoh 2: Dapatkan informasi tentang sertifikat akar tertentu
```
PS C:\>Get-AzureRmVpnClientRootCertificate -VirtualNetworkGatewayName "ContosoVirtualNetwork" -ResourceGroupName "ContosoResourceGroup" -VpnClientRootCertificateName "ContosoRootClientCertificate"
```

Perintah ini adalah variasi perintah yang diperlihatkan dalam Contoh 1.
Namun, dalam kasus ini, parameter *VpnClientRootCertificateName* disertakan untuk membatasi data yang dikembalikan ke sertifikat akar tertentu: ContosoRootClientCertificate.

## PARAMETERS

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang ditetapkan untuk gateway jaringan virtual.
Grup sumber daya mengkategorikan item untuk membantu menyederhanakan manajemen inventaris dan administrasi umum Azure.

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
Menentukan nama gateway jaringan virtual tempat sertifikat akar ditetapkan.

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

### -VpnClientRootCertificateName
Menentukan nama sertifikat akar klien yang didaurkan cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate

## CATATAN

## RELATED LINKS

[Add-AzureRmVpnClientRootCertificate](./Add-AzureRmVpnClientRootCertificate.md)

[New-AzureRmVpnClientRootCertificate](./New-AzureRmVpnClientRootCertificate.md)

[Remove-AzureRmVpnClientRootCertificate](./Remove-AzureRmVpnClientRootCertificate.md)


