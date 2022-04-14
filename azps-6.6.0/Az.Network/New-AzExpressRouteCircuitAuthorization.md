---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: B6E55944-1B78-463F-9FC9-98097FEEC278
online version: https://docs.microsoft.com/powershell/module/az.network/new-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 20719ff7aaf79654489b3075d1c0548d755ad5c6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142047233"
---
# New-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Membuat otorisasi sirkuit ExpressRoute.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azexpressroutecircuitauthorization) untuk informasi terbaru.

## SYNTAX

```
New-AzExpressRouteCircuitAuthorization -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzExpressRouteCircuitAuthorization membuat otorisasi** sirkuit yang dapat ditambahkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik jaringan virtual untuk menyambungkan jaringan ke sirkuit. Hanya ada satu otorisasi per jaringan virtual.
Setelah membuat sirkuit ExpressRoute, Anda dapat menggunakan **Add-AzExpressRouteCircuitAuthorization** untuk menambahkan otorisasi ke sirkuit tersebut.
Atau, Anda dapat menggunakan **New-AzExpressRouteCircuitAuthorization** untuk membuat otorisasi yang dapat ditambahkan ke sirkuit baru pada saat yang sama sirkuit dibuat.

## EXAMPLES

### Contoh 1: Membuat otorisasi sirkuit baru
```
$Authorization = New-AzExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization"
```

Perintah ini membuat otorisasi sirkuit baru bernama ContosoCircuitAuthorization lalu menyimpan objek tersebut dalam variabel bernama $Authorization. Menyimpan objek ke variabel sangatlah penting: meskipun **New-AzExpressRouteCircuitAuthorization** dapat membuat otorisasi sirkuit tidak dapat menambahkan otorisasi tersebut ke rute sirkuit. Sebagai gantinya, variabel $Authorization digunakan New-AzExpressRouteCircuit saat membuat sirkuit ExpressRoute baru.
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzExpressRouteCircuit.

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
Menentukan nama unik untuk otorisasi sirkuit ExpressRoute yang baru.

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

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitAuthorization

## CATATAN

## RELATED LINKS

[Add-AzExpressRouteCircuitAuthorization](./Add-AzExpressRouteCircuitAuthorization.md)

[Get-AzExpressRouteCircuitAuthorization](./Get-AzExpressRouteCircuitAuthorization.md)

[Remove-AzExpressRouteCircuitAuthorization](./Remove-AzExpressRouteCircuitAuthorization.md)

