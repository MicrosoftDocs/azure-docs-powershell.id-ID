---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 38D57CE4-6994-4BDA-A50E-28680EF4E568
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/remove-azurermexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 6a8c81f8c130f322e868c91e18c7fff7b1175d4b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421226"
---
# Remove-AzureRmExpressRouteCircuitAuthorization

## SYNOPSIS
Menghapus otorisasi konfigurasi ExpressRoute yang sudah ada.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmExpressRouteCircuitAuthorization [-Name <String>] -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmExpressRouteCircuitAuthorization** menghapus otorisasi yang ditetapkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menghubungkan jaringan lokal Anda ke Azure dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang bisa digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringannya ke sirkuit. Hanya bisa ada satu otorisasi per jaringan virtual. Kapan saja, namun, pemilik sirkuit bisa menggunakan **Remove-AzureRmExpressRouteCircuitAuthorization** untuk menghapus otorisasi yang ditetapkan ke jaringan virtual. Ketika hal tersebut terjadi, jaringan virtual yang terkait tidak lagi dapat menggunakan sirkuit ExpressRoute untuk tersambung ke Azure.

## EXAMPLES

### Contoh 1: Menghapus otorisasi sirkuit dari sirkuit ExpressRoute
```
$Circuit = Get-AzureRmExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Remove-AzureRmExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization" -Circuit $Circuit
Set-AzureRmExpressRouteCircuit -ExpressRouteCircuit $Circuit
```

Contoh ini menghapus otorisasi sirkuit dari sirkuit ExpressRoute. Perintah pertama menggunakan cmdlet **Get-AzureRmExpressRouteCircuit** untuk membuat referensi objek ke sirkuit ExpressRoute bernama ContosoCircuit dan menyimpan hasilnya dalam variabel yang bernama $Circuit.
Perintah kedua menandai otorisasi sirkuit ContosoCircuitAuthorization untuk penghapusan.
Perintah ketiga menggunakan cmdlet Set-AzureRmExpressRouteCircuit cmdlet untuk mengonfirmasi penghapusan sirkuit ExpressRoute yang disimpan di $Circuit variabel.

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

### -ExpressRouteCircuit
Menentukan objek ExpressRouteCircuit yang dihapus cmdlet ini.

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
Menentukan nama otorisasi sirkuit yang dihapus cmdlet ini.

```yaml
Type: System.String
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

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit
Parameter: ExpressRouteCircuit (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## CATATAN

## RELATED LINKS

[Add-AzureRmExpressRouteCircuitAuthorization](./Add-AzureRmExpressRouteCircuitAuthorization.md)

[Get-AzureRmExpressRouteCircuit](./Get-AzureRmExpressRouteCircuit.md)

[Get-AzureRmExpressRouteCircuitAuthorization](./Get-AzureRmExpressRouteCircuitAuthorization.md)

[New-AzureRmExpressRouteCircuitAuthorization](./New-AzureRmExpressRouteCircuitAuthorization.md)

[Set-AzureRmExpressRouteCircuit](./Set-AzureRmExpressRouteCircuit.md)
