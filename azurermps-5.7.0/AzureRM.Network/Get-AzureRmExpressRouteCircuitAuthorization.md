---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 3D80F94B-AF9D-40C2-BE7E-2F32E5E926D2
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 3aed1a20a8a5878819ea3634ff5d31babba3261c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426386"
---
# Get-AzureRmExpressRouteCircuitAuthorization

## SYNOPSIS
Dapatkan informasi tentang otorisasi sirkuit ExpressRoute.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmExpressRouteCircuitAuthorization [-Name <String>] -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmExpressRouteCircuitAuthorization** mendapatkan informasi tentang otorisasi yang ditetapkan untuk sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; ini otorisasi menghasilkan kunci otorisasi yang bisa digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringannya ke sirkuit (satu otorisasi per jaringan virtual). Tombol otorisasi, serta informasi lain tentang otorisasi, dapat dilihat kapan saja dengan menjalankan **Get-AzureRmExpressRouteCircuitAuthorization**.

## EXAMPLES

### Contoh 1: Dapatkan semua otorisasi ExpressRoute
```
$Circuit = Get-AzureRmExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Get-AzureRmExpressRouteCircuitAuthorization -Circuit $Circuit
```

Perintah ini mengembalikan informasi tentang semua otorisasi ExpressRoute yang terkait dengan sirkuit ExpressRoute. Perintah pertama menggunakan cmdlet **Get-AzureRmExpressRouteCircuit** untuk membuat referensi objek sirkuit bernama ContosoCircuit; referensi objek tersebut disimpan di variabel $Circuit. Perintah kedua lalu menggunakan referensi objek dan cmdlet **Get-AzureRmExpressRouteCircuitAuthorization** untuk mengembalikan informasi tentang otorisasi yang terkait dengan ContosoCircuit.

### Contoh 2: Dapatkan semua otorisasi ExpressRoute menggunakan cmdlet Where-Object
```
$Circuit = Get-AzureRmExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
 Get-AzureRmExpressRouteCircuitAuthorization -Circuit $Circuit | Where-Object {$_.AuthorizationUseStatus -eq "Available"}
```

Perintah ini menunjukkan variasi pada perintah yang digunakan dalam Contoh 1. Namun, dalam kasus ini, informasi hanya dikembalikan untuk otorisasi yang tersedia untuk digunakan (yaitu, untuk otorisasi yang belum ditetapkan ke jaringan virtual). Untuk melakukan ini, informasi otorisasi sirkuit dikembalikan di perintah 2 dan pipa ke cmdlet **Where-Object.**
**Jika kemudian Objek** hanya memilih otorisasi dengan properti *AuthorizationUseStatus* yang diatur ke Tersedia. Untuk mencantumkan izin yang tidak tersedia saja, gunakan sintaks ini untuk klausul Where:

`{$_.AuthorizationUseStatus -ne "Available"}`

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

### -ExpressRouteCircuit
Menentukan otorisasi sirkuit ExpressRoute.

```yaml
Type: PSExpressRouteCircuit
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama otorisasi sirkuit ExpressRoute yang akan cmdlet ini dapatkan.

-Name "ContosoCircuitAuthorization"

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSExpressRouteCircuit
**Get-AzureRmExpressRouteCircuitAuthorization** accepts pipelined instances of the **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit** object.

## OUTPUTS

### PSExpressRouteCircuitAuthorization
**Get-AzureRmExpressRouteCircuitAuthorization** mengembalikan contoh objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitAuthorization.**

## CATATAN

## RELATED LINKS

[Add-AzureRmExpressRouteCircuitAuthorization](./Add-AzureRmExpressRouteCircuitAuthorization.md)

[Get-AzureRmExpressRouteCircuit](./Get-AzureRmExpressRouteCircuit.md)

[New-AzureRmExpressRouteCircuitAuthorization](./New-AzureRmExpressRouteCircuitAuthorization.md)

[Remove-AzureRmExpressRouteCircuitAuthorization](./Remove-AzureRmExpressRouteCircuitAuthorization.md)
