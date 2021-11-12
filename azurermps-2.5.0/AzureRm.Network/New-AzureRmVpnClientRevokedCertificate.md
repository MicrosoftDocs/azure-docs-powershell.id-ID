---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 973E1E53-983F-45A7-A7CF-18A8D96EC4E6
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/new-azurermvpnclientrevokedcertificate
schema: 2.0.0
ms.openlocfilehash: b1c802425576679da2238afffc0b40b77fc64193
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421530"
---
# New-AzureRmVpnClientRevokedCertificate

## SYNOPSIS
Membuat sertifikat pencabutan klien VPN baru.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVpnClientRevokedCertificate -Name <String> -Thumbprint <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmVpnClientRevokedCertificate** membuat sertifikat pencabutan klien jaringan privat virtual (VPN) baru untuk digunakan di gateway jaringan virtual.
Sertifikat pencabutan klien mencegah komputer klien menggunakan sertifikat yang ditentukan untuk autentikasi.

Cmdlet ini membuat sertifikat mandiri yang tidak ditetapkan ke gateway virtual.
Sebagai gantinya, sertifikat yang dibuat **oleh New-AzureRmVpnClientRevokedCertificate** digunakan sehubungan dengan cmdlet New-AzureRmVirtualNetworkGateway saat membuat gateway baru.
Misalnya, anggaplah Anda membuat sertifikat baru dan menyimpannya di variabel yang bernama $Certificate.
Anda lalu bisa menggunakan objek sertifikat tersebut saat Anda membuat gateway virtual baru.
Sebagai contoh,

`New-AzureRmVirtualNetworkGateway -Name "ContosoVirtualGateway" -ResourceGroupName "ContosoResourceGroup" -Location "West US" -GatewayType "VPN" -IpConfigurations $Ipconfig  -VPNType "RouteBased" -VpnClientRevokedCertificates $Certificate`

Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzureRmVirtualNetworkGateway baru.

## EXAMPLES

### Contoh 1: Membuat sertifikat baru yang dicabut klien
```
PS C:\>$Certificate = New-AzureRmVpnClientRevokedCertificate -Name "ContosoClientRevokedCertificate" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3"
```

Perintah ini membuat sertifikat baru yang dicabut klien dan menyimpan objek sertifikat dalam variabel yang bernama $Certificate.
Variabel ini kemudian bisa digunakan oleh cmdlet **New-AzureRmVirtualNetworkGateway** untuk menambahkan sertifikat ke gateway jaringan virtual baru.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Menentukan nama unik untuk sertifikat pencabutan klien baru.

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

### -Thumbprint
Menentukan pengidentifikasi unik sertifikat yang ditambahkan.

Anda bisa mengembalikan informasi yang dapat dicetak dengan jempol untuk sertifikat Anda dengan menggunakan Windows PowerShell seperti ini:

`Get-ChildItem -Path Cert:\LocalMachine\Root`

Perintah sebelumnya mengembalikan informasi untuk semua sertifikat Komputer Lokal yang ditemukan di penyimpanan sertifikat Akar.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

###  
Cmdlet ini tidak menerima input saluran.

## OUTPUTS

###  
Cmdlet ini membuat contoh baru objek **Microsoft.Azure.Commands.Network.Models.PSVpnClientRevokedCertificate.**

## CATATAN

## RELATED LINKS

[Add-AzureRmVpnClientRevokedCertificate](./Add-AzureRmVpnClientRevokedCertificate.md)

[Get-AzureRmVpnClientRevokedCertificate](./Get-AzureRmVpnClientRevokedCertificate.md)

[Remove-AzureRmVpnClientRevokedCertificate](./Remove-AzureRmVpnClientRevokedCertificate.md)


