---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 9994E2B2-20A1-4E95-9A9F-379B8B63F7F5
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/add-azurermexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 108ea2b0262c34e38ffd7ed2961e3cba9a8d59ba
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428220"
---
# Add-AzureRmExpressRouteCircuitAuthorization

## SYNOPSIS
Menambahkan otorisasi sirkuit ExpressRoute.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmExpressRouteCircuitAuthorization -Name <String> -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmExpressRouteCircuitAuthorization** menambahkan otorisasi ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; ini otorisasi menghasilkan kunci otorisasi yang bisa digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringannya ke sirkuit (satu otorisasi per jaringan virtual). **Add-AzureRmExpressRouteCircuitAuthorization** menambahkan otorisasi baru ke sirkuit dan, pada saat yang sama, menghasilkan kunci otorisasi terkait. Tombol ini dapat ditampilkan kapan saja dengan menjalankan cmdlet Get-AzureRmExpressRouteCircuitAuthorization, dan, sebagaimana diperlukan, kemudian dapat disalin dan diteruskan ke pemilik jaringan yang sesuai.
Perhatikan bahwa, setelah menjalankan **Add-AzureRmExpressRouteCircuitAuthorization**, Anda harus memanggil cmdlet Set-AzureRmExpressRouteCircuit untuk mengaktifkan kunci. If you do not call **Set-AzureRmExpressRouteCircuit** the authorization will be added to the circuit but will not be enabled for use.

## EXAMPLES

### Contoh 1: Tambahkan otorisasi ke sirkuit ExpressRoute yang ditentukan
```
$Circuit = Get-AzureRmExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Add-AzureRmExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization" -Circuit $Circuit
Set-AzureRmExpressRouteCircuit -ExpressRouteCircuit $Circuit
```

Perintah dalam contoh ini menambahkan otorisasi baru ke sirkuit ExpressRoute yang ada. Perintah pertama menggunakan **Get-AzureRmExpressRouteCircuit** untuk membuat referensi objek ke sirkuit bernama ContosoCircuit. Referensi objek tersebut disimpan dalam variabel yang bernama $Circuit.
Di perintah kedua, cmdlet **Add-AzureRmExpressRouteCircuitAuthorization** digunakan untuk menambahkan otorisasi baru (ContosoCircuitAuthorization) ke sirkuit ExpressRoute. Perintah ini menambahkan otorisasi tapi tidak mengaktifkan otorisasi itu. Mengaktifkan otorisasi memerlukan **Set-AzureRmExpressRouteCircuit** diperlihatkan di perintah final dalam contoh.

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
Menentukan sirkuit ExpressRoute yang menambahkan otorisasi kepada cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit
Parameter: ExpressRouteCircuit (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## CATATAN

## RELATED LINKS

[Get-AzureRmExpressRouteCircuit](./Get-AzureRmExpressRouteCircuit.md)

[Get-AzureRmExpressRouteCircuitAuthorization](./Get-AzureRmExpressRouteCircuitAuthorization.md)

[New-AzureRmExpressRouteCircuitAuthorization](./New-AzureRmExpressRouteCircuitAuthorization.md)

[Remove-AzureRmExpressRouteCircuitAuthorization](./Remove-AzureRmExpressRouteCircuitAuthorization.md)

[Set-AzureRmExpressRouteCircuit](./Set-AzureRmExpressRouteCircuit.md)
