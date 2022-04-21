---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 3D80F94B-AF9D-40C2-BE7E-2F32E5E926D2
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 3b51a16d6ff2de8292b1bbb66f7f5ab24cc17b93
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142781776"
---
# Get-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Mendapatkan informasi tentang otorisasi sirkuit ExpressRoute.

## SYNTAX

```
Get-AzExpressRouteCircuitAuthorization [-Name <String>] -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRouteCircuitAuthorization** mendapatkan informasi tentang otorisasi yang ditetapkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik jaringan virtual untuk menyambungkan jaringannya ke sirkuit (satu otorisasi per jaringan virtual). Kunci otorisasi, serta informasi lain tentang otorisasi, dapat dilihat kapan saja dengan menjalankan **Get-AzExpressRouteCircuitAuthorization**.

## EXAMPLES

### Contoh 1: Dapatkan semua otorisasi ExpressRoute
```
$Circuit = Get-AzExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Get-AzExpressRouteCircuitAuthorization -Circuit $Circuit
```

Perintah ini mengembalikan informasi tentang semua otorisasi ExpressRoute yang terkait dengan sirkuit ExpressRoute. Perintah pertama menggunakan cmdlet **Get-AzExpressRouteCircuit** untuk membuat referensi objek sirkuit bernama ContosoCircuit; referensi objek tersebut disimpan dalam variabel $Circuit. Perintah kedua kemudian menggunakan referensi objek tersebut dan cmdlet **Get-AzExpressRouteCircuitAuthorization** untuk mengembalikan informasi tentang otorisasi yang terkait dengan ContosoCircuit.

### Contoh 2: Dapatkan semua otorisasi ExpressRoute menggunakan cmdlet Where-Object
```
$Circuit = Get-AzExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
 Get-AzExpressRouteCircuitAuthorization -Circuit $Circuit | Where-Object {$_.AuthorizationUseStatus -eq "Available"}
```

Perintah ini menunjukkan variasi pada perintah yang digunakan dalam Contoh 1. Namun, dalam hal ini, informasi dikembalikan hanya untuk otorisasi yang tersedia untuk digunakan (yaitu, untuk otorisasi yang belum ditetapkan ke jaringan virtual). Untuk melakukan ini, informasi otorisasi sirkuit dikembalikan dalam perintah 2 dan disalurkan ke cmdlet **Where-Object** .
**Where-Object** kemudian hanya memilih otorisasi di mana properti *AuthorizationUseStatus* diatur ke Tersedia. Untuk mencantumkan otorisasi yang tidak tersedia saja, gunakan sintaks ini untuk klausul Where:

`{$_.AuthorizationUseStatus -ne "Available"}`

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
Menentukan nama otorisasi sirkuit ExpressRoute yang didapat cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSExpressRouteCircuit
**Get-AzExpressRouteCircuitAuthorization** menerima instans pipelined objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit** .

## OUTPUTS

### PSExpressRouteCircuitAuthorization
**Get-AzExpressRouteCircuitAuthorization** mengembalikan instans objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitAuthorization** .

## NOTES

## RELATED LINKS

[Add-AzExpressRouteCircuitAuthorization](./Add-AzExpressRouteCircuitAuthorization.md)

[Get-AzExpressRouteCircuit](./Get-AzExpressRouteCircuit.md)

[New-AzExpressRouteCircuitAuthorization](./New-AzExpressRouteCircuitAuthorization.md)

[Remove-AzExpressRouteCircuitAuthorization](./Remove-AzExpressRouteCircuitAuthorization.md)
