---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: B6E55944-1B78-463F-9FC9-98097FEEC278
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 2fec428adb2ba8621d09a1f0ae5e762cdbe4b913
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420990"
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
Cmdlet **New-AzureRmExpressRouteCircuitAuthorization** membuat otorisasi sirkuit yang bisa ditambahkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang bisa digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringan ke sirkuit. Hanya ada satu otorisasi per jaringan virtual.

Setelah membuat sirkuit ExpressRoute, Anda dapat menggunakan **Add-AzureRmExpressRouteCircuitAuthorization** untuk menambahkan otorisasi ke sirkuit tersebut.
Alternatifnya, Anda bisa menggunakan **New-AzureRmExpressRouteCircuitAuthorization** untuk membuat otorisasi yang bisa ditambahkan ke sirkuit baru pada saat yang sama sirkuit dibuat.

## EXAMPLES

### Contoh 1: Buat otorisasi sirkuit baru
```
$Authorization = New-AzureRmExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization"
```

Perintah ini membuat otorisasi sirkuit baru bernama ContosoCircuitAuthorization lalu menyimpan objek tersebut dalam variabel yang bernama $Authorization. Menyimpan objek ke variabel penting: although **New-AzureRmExpressRouteCircuitAuthorization** can create a circuit authorization it cannot add that authorization to a circuit route. Sebaliknya, variabel $Authorization digunakan New-AzureRmExpressRouteCircuit saat membuat sirkuit ExpressRoute yang benar-benar baru.

Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzureRmExpressRouteCircuit baru.

## PARAMETERS

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input saluran.

## OUTPUTS

### PSExpressRouteCircuitAuthorization
Cmdlet ini membuat contoh objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitAuthorization.**

## CATATAN

## RELATED LINKS

[Add-AzureRmExpressRouteCircuitAuthorization](./Add-AzureRmExpressRouteCircuitAuthorization.md)

[Get-AzureRmExpressRouteCircuitAuthorization](./Get-AzureRmExpressRouteCircuitAuthorization.md)

[Remove-AzureRmExpressRouteCircuitAuthorization](./Remove-AzureRmExpressRouteCircuitAuthorization.md)

