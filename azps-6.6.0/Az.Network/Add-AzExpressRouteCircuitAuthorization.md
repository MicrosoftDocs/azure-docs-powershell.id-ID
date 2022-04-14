---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 9994E2B2-20A1-4E95-9A9F-379B8B63F7F5
online version: https://docs.microsoft.com/powershell/module/az.network/add-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 828283013510e19c785bf30200f27744dc033398
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142082155"
---
# Add-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Menambahkan otorisasi sirkuit ExpressRoute.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/add-azexpressroutecircuitauthorization) untuk informasi terbaru.

## SYNTAX

```
Add-AzExpressRouteCircuitAuthorization -Name <String> -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzExpressRouteCircuitAuthorization menambahkan otorisasi** ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik jaringan virtual untuk menyambungkan jaringannya ke sirkuit (satu otorisasi per jaringan virtual). **Add-AzExpressRouteCircuitAuthorization menambahkan otorisasi** baru ke sirkuit dan, pada saat yang sama, menghasilkan kunci otorisasi terkait. Kunci ini dapat dilihat kapan saja dengan menjalankan cmdlet Get-AzExpressRouteCircuitAuthorization dan, sesuai kebutuhan, kemudian dapat disalin dan diteruskan ke pemilik jaringan yang sesuai.
Perhatikan bahwa, setelah menjalankan **Add-AzExpressRouteCircuitAuthorization**, Anda harus memanggil cmdlet Set-AzExpressRouteCircuit untuk mengaktifkan kunci. Jika Anda tidak memanggil **Set-AzExpressRouteCircuit** , otorisasi akan ditambahkan ke sirkuit tetapi tidak akan diaktifkan untuk digunakan.

## EXAMPLES

### Contoh 1: Menambahkan otorisasi ke sirkuit ExpressRoute yang ditentukan
```
$Circuit = Get-AzExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Add-AzExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization" -Circuit $Circuit
Set-AzExpressRouteCircuit -ExpressRouteCircuit $Circuit
```

Perintah dalam contoh ini menambahkan otorisasi baru ke sirkuit ExpressRoute yang sudah ada. Perintah pertama menggunakan **Get-AzExpressRouteCircuit** untuk membuat referensi objek ke sirkuit bernama ContosoCircuit. Referensi objek tersebut disimpan dalam variabel bernama $Circuit.
Dalam perintah kedua, cmdlet **Add-AzExpressRouteCircuitAuthorization** digunakan untuk menambahkan otorisasi baru (ContosoCircuitAuthorization) ke sirkuit ExpressRoute. Perintah ini menambahkan otorisasi tetapi tidak mengaktifkan otorisasi tersebut. Mengaktifkan otorisasi memerlukan **Set-AzExpressRouteCircuit** yang diperlihatkan dalam perintah akhir dalam contoh.

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

### -ExpressRouteCircuit
Menentukan sirkuit ExpressRoute tempat cmdlet ini menambahkan otorisasi.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama otorisasi sirkuit yang akan ditambahkan.

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

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## CATATAN

## RELATED LINKS

[Get-AzExpressRouteCircuit](./Get-AzExpressRouteCircuit.md)

[Get-AzExpressRouteCircuitAuthorization](./Get-AzExpressRouteCircuitAuthorization.md)

[New-AzExpressRouteCircuitAuthorization](./New-AzExpressRouteCircuitAuthorization.md)

[Remove-AzExpressRouteCircuitAuthorization](./Remove-AzExpressRouteCircuitAuthorization.md)

[Set-AzExpressRouteCircuit](./Set-AzExpressRouteCircuit.md)
