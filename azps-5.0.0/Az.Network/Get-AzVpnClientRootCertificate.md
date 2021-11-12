---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 16754F70-9619-4F68-86E9-5C8B27812707
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzVpnClientRootCertificate.md
ms.openlocfilehash: 3cf1bea87824320b659def722d0d0f0166fa177d
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410233"
---
# Get-AzVpnClientRootCertificate

## SYNOPSIS
Mendapatkan informasi tentang sertifikat akar VPN.

## SINTAKS

```
Get-AzVpnClientRootCertificate [-VpnClientRootCertificateName <String>] -VirtualNetworkGatewayName <String>
 -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzVpnClientRootCertificate** mengembalikan informasi tentang sertifikat akar yang ditetapkan untuk gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan di gateway mempercayai sertifikat akar.
Secara default, **Get-AzVpnClientRootCertificate** mengembalikan informasi tentang semua sertifikat akar yang ditetapkan untuk gateway.
(Gateway bisa memiliki lebih dari satu sertifikat akar.) Namun, dengan menyertakan parameter **VpnClientRootCertificateName** Anda bisa membatasi data yang dikembalikan menjadi sertifikat tertentu.

## CONTOH

### Contoh 1: Dapatkan informasi tentang semua sertifikat akar
```
PS C:\>Get-AzVpnClientRootCertificate -VirtualNetworkGatewayName "ContosoVirtualNetwork" -ResourceGroupName "ContosoResourceGroup"
```

Perintah ini mendapatkan informasi tentang semua sertifikat akar yang ditetapkan ke gateway jaringan virtual bernama ContosoVirtualNetwork.

### Contoh 2: Dapatkan informasi tentang sertifikat akar tertentu
```
PS C:\>Get-AzVpnClientRootCertificate -VirtualNetworkGatewayName "ContosoVirtualNetwork" -ResourceGroupName "ContosoResourceGroup" -VpnClientRootCertificateName "ContosoRootClientCertificate"
```

Perintah ini adalah variasi perintah yang diperlihatkan dalam Contoh 1.
Namun, dalam kasus ini, parameter *VpnClientRootCertificateName* disertakan untuk membatasi data yang dikembalikan ke sertifikat akar tertentu: ContosoRootClientCertificate.

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
Menentukan nama sertifikat akar klien yang akan didaurkan cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate

## CATATAN

## LINK TERKAIT

[Add-AzVpnClientRootCertificate](./Add-AzVpnClientRootCertificate.md)

[New-AzVpnClientRootCertificate](./New-AzVpnClientRootCertificate.md)

[Remove-AzVpnClientRootCertificate](./Remove-AzVpnClientRootCertificate.md)


