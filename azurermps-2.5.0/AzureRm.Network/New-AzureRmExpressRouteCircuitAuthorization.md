---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: B6E55944-1B78-463F-9FC9-98097FEEC278
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/new-azurermexpressroutecircuitauthorization
schema: 2.0.0
ms.openlocfilehash: f0e66c1e601ab63eec6d2540edd3ba0235727e9a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142926889"
---
# New-AzureRmExpressRouteCircuitAuthorization

## SYNOPSIS
Membuat otorisasi sirkuit ExpressRoute.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmExpressRouteCircuitAuthorization -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmExpressRouteCircuitAuthorization** membuat otorisasi sirkuit yang dapat ditambahkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik jaringan virtual untuk menyambungkan jaringan ke sirkuit. Hanya ada satu otorisasi per jaringan virtual.

Setelah membuat sirkuit ExpressRoute, Anda dapat menggunakan **Add-AzureRmExpressRouteCircuitAuthorization** untuk menambahkan otorisasi ke sirkuit tersebut.
Atau, Anda dapat menggunakan **New-AzureRmExpressRouteCircuitAuthorization** untuk membuat otorisasi yang dapat ditambahkan ke sirkuit baru pada saat yang sama sirkuit dibuat.

## EXAMPLES

### Contoh 1: Membuat otorisasi sirkuit baru
```
$Authorization = New-AzureRmExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization"
```

Perintah ini membuat otorisasi sirkuit baru bernama ContosoCircuitAuthorization lalu menyimpan objek tersebut dalam variabel bernama $Authorization. Menyimpan objek ke variabel sangat penting: meskipun **New-AzureRmExpressRouteCircuitAuthorization** dapat membuat otorisasi sirkuit tidak dapat menambahkan otorisasi tersebut ke rute sirkuit. Sebagai gantinya, variabel $Authorization digunakan New-AzureRmExpressRouteCircuit saat membuat sirkuit ExpressRoute baru.

Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzureRmExpressRouteCircuit.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan nama unik untuk otorisasi sirkuit ExpressRoute yang baru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input pipelined.

## OUTPUTS

### PSExpressRouteCircuitAuthorization
Cmdlet ini membuat instans objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitAuthorization** .

## NOTES

## RELATED LINKS

[Add-AzureRmExpressRouteCircuitAuthorization](./Add-AzureRmExpressRouteCircuitAuthorization.md)

[Get-AzureRmExpressRouteCircuitAuthorization](./Get-AzureRmExpressRouteCircuitAuthorization.md)

[Remove-AzureRmExpressRouteCircuitAuthorization](./Remove-AzureRmExpressRouteCircuitAuthorization.md)

