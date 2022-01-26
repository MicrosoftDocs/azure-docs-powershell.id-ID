---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 38D57CE4-6994-4BDA-A50E-28680EF4E568
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/remove-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Remove-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Remove-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: d98366d9bd3fb42be39f68976e131ec644274431
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136015246"
---
# Remove-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Menghapus otorisasi konfigurasi ExpressRoute yang sudah ada.

## SINTAKS

```
Remove-AzExpressRouteCircuitAuthorization [-Name <String>] -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Remove-AzExpressRouteCircuitAuthorization** menghapus otorisasi yang ditetapkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menghubungkan jaringan lokal Anda ke Azure dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang bisa digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringannya ke sirkuit. Hanya bisa ada satu otorisasi per jaringan virtual. Kapan saja, namun, pemilik sirkuit bisa menggunakan **Remove-AzExpressRouteCircuitAuthorization** untuk menghapus otorisasi yang ditetapkan ke jaringan virtual. Ketika hal tersebut terjadi, jaringan virtual yang terkait tidak lagi dapat menggunakan sirkuit ExpressRoute untuk tersambung ke Azure.

## CONTOH

### Contoh 1: Menghapus otorisasi sirkuit dari sirkuit ExpressRoute
```
$Circuit = Get-AzExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Remove-AzExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization" -Circuit $Circuit
Set-AzExpressRouteCircuit -ExpressRouteCircuit $Circuit
```

Contoh ini menghapus otorisasi sirkuit dari sirkuit ExpressRoute. Perintah pertama menggunakan cmdlet **Get-AzExpressRouteCircuit** untuk membuat referensi objek ke sirkuit ExpressRoute yang bernama ContosoCircuit dan menyimpan hasilnya dalam variabel yang bernama $Circuit.
Perintah kedua menandai otorisasi sirkuit ContosoCircuitAuthorization untuk penghapusan.
Perintah ketiga menggunakan cmdlet Set-AzExpressRouteCircuit cmdlet untuk mengonfirmasi penghapusan sirkuit ExpressRoute yang disimpan di $Circuit variabel.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## CATATAN

## LINK TERKAIT

[Add-AzExpressRouteCircuitAuthorization](./Add-AzExpressRouteCircuitAuthorization.md)

[Get-AzExpressRouteCircuit](./Get-AzExpressRouteCircuit.md)

[Get-AzExpressRouteCircuitAuthorization](./Get-AzExpressRouteCircuitAuthorization.md)

[New-AzExpressRouteCircuitAuthorization](./New-AzExpressRouteCircuitAuthorization.md)

[Set-AzExpressRouteCircuit](./Set-AzExpressRouteCircuit.md)
