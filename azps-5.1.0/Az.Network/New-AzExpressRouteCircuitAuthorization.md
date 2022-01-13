---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: B6E55944-1B78-463F-9FC9-98097FEEC278
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/New-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/New-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 28b45f5368fb7a63450276c054654313d7e1c517
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136015492"
---
# New-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Membuat otorisasi sirkuit ExpressRoute.

## SINTAKS

```
New-AzExpressRouteCircuitAuthorization -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzExpressRouteCircuitAuthorization** membuat otorisasi sirkuit yang bisa ditambahkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang bisa digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringan ke sirkuit. Hanya ada satu otorisasi per jaringan virtual.
Setelah membuat sirkuit ExpressRoute Anda bisa menggunakan **Add-AzExpressRouteCircuitAuthorization** untuk menambahkan otorisasi ke sirkuit itu.
Alternatifnya, Anda bisa menggunakan **New-AzExpressRouteCircuitAuthorization** untuk membuat otorisasi yang bisa ditambahkan ke sirkuit baru pada saat yang sama sirkuit dibuat.

## CONTOH

### Contoh 1: Buat otorisasi sirkuit baru
```
$Authorization = New-AzExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization"
```

Perintah ini membuat otorisasi sirkuit baru bernama ContosoCircuitAuthorization lalu menyimpan objek tersebut dalam variabel yang bernama $Authorization. Menyimpan objek ke variabel penting: meskipun **New-AzExpressRouteCircuitAuthorization** bisa membuat otorisasi sirkuit yang tidak bisa menambahkan otorisasi itu ke rute sirkuit. Sebaliknya, variabel $Authorization digunakan New-AzExpressRouteCircuit saat membuat sirkuit ExpressRoute yang benar-benar baru.
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzExpressRouteCircuit baru.

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
Menentukan nama yang unik untuk otorisasi sirkuit ExpressRoute baru.

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

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitAuthorization

## CATATAN

## LINK TERKAIT

[Add-AzExpressRouteCircuitAuthorization](./Add-AzExpressRouteCircuitAuthorization.md)

[Get-AzExpressRouteCircuitAuthorization](./Get-AzExpressRouteCircuitAuthorization.md)

[Remove-AzExpressRouteCircuitAuthorization](./Remove-AzExpressRouteCircuitAuthorization.md)

