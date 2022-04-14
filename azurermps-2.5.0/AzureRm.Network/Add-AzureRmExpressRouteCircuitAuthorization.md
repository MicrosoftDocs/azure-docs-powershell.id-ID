---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 9994E2B2-20A1-4E95-9A9F-379B8B63F7F5
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/add-azurermexpressroutecircuitauthorization
schema: 2.0.0
ms.openlocfilehash: 9b41eb0c95c2b1693e56c8b11fee86b6e49a4609
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142146619"
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
Cmdlet **Add-AzureRmExpressRouteCircuitAuthorization menambahkan otorisasi** ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik jaringan virtual untuk menyambungkan jaringannya ke sirkuit (satu otorisasi per jaringan virtual). **Add-AzureRmExpressRouteCircuitAuthorization menambahkan otorisasi** baru ke sirkuit dan, pada saat yang sama, menghasilkan kunci otorisasi terkait. Kunci ini dapat dilihat kapan saja dengan menjalankan cmdlet Get-AzureRmExpressRouteCircuitAuthorization dan, sesuai kebutuhan, kemudian dapat disalin dan diteruskan ke pemilik jaringan yang sesuai.

Perhatikan bahwa, setelah menjalankan **Add-AzureRmExpressRouteCircuitAuthorization**, Anda harus menghubungi cmdlet Set-AzureRmExpressRouteCircuit untuk mengaktifkan kunci. Jika Anda tidak memanggil **Set-AzureRmExpressRouteCircuit** , otorisasi akan ditambahkan ke sirkuit tetapi tidak akan diaktifkan untuk digunakan.

## EXAMPLES

### Contoh 1: Menambahkan otorisasi ke sirkuit ExpressRoute yang ditentukan
```
$Circuit = Get-AzureRmExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Add-AzureRmExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization" -Circuit $Circuit
Set-AzureRmExpressRouteCircuit -ExpressRouteCircuit $Circuit
```

Perintah dalam contoh ini menambahkan otorisasi baru ke sirkuit ExpressRoute yang sudah ada. Perintah pertama menggunakan **Get-AzureRmExpressRouteCircuit** untuk membuat referensi objek ke sirkuit bernama ContosoCircuit. Referensi objek tersebut disimpan dalam variabel bernama $Circuit.

Dalam perintah kedua, cmdlet **Add-AzureRmExpressRouteCircuitAuthorization** digunakan untuk menambahkan otorisasi baru (ContosoCircuitAuthorization) ke sirkuit ExpressRoute. Perintah ini menambahkan otorisasi tetapi tidak mengaktifkan otorisasi tersebut. Mengaktifkan otorisasi memerlukan **Set-AzureRmExpressRouteCircuit** yang diperlihatkan dalam perintah akhir dalam contoh.

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

### -ExpressRouteCircuit
Menentukan sirkuit ExpressRoute tempat cmdlet ini menambahkan otorisasi.

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
Menentukan nama otorisasi sirkuit yang akan ditambahkan.

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

### PSExpressRouteCircuit
**Add-AzureRmExpressRouteCircuitAuthorization** menerima instans pipelined objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit** .

## OUTPUTS

### PSExpressRouteCircuit
**Add-AzureRmExpressRouteCircuitAuthorization** mengubah instans objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit** .

## CATATAN

## RELATED LINKS

[Get-AzureRmExpressRouteCircuit](./Get-AzureRmExpressRouteCircuit.md)

[Get-AzureRmExpressRouteCircuitAuthorization](./Get-AzureRmExpressRouteCircuitAuthorization.md)

[New-AzureRmExpressRouteCircuitAuthorization](./New-AzureRmExpressRouteCircuitAuthorization.md)

[Remove-AzureRmExpressRouteCircuitAuthorization](./Remove-AzureRmExpressRouteCircuitAuthorization.md)

[Set-AzureRmExpressRouteCircuit](./Set-AzureRmExpressRouteCircuit.md)
