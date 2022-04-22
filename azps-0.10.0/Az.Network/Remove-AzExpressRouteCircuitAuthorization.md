---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 38D57CE4-6994-4BDA-A50E-28680EF4E568
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/remove-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Remove-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Remove-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: ef00e209b030ed4a05ad29ccb3e768df090ea8ee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142909775"
---
# Remove-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Menghapus otorisasi konfigurasi ExpressRoute yang sudah ada.

## SYNTAX

```
Remove-AzExpressRouteCircuitAuthorization [-Name <String>] -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzExpressRouteCircuitAuthorization menghapus otorisasi** yang ditetapkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke Azure menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik jaringan virtual untuk menyambungkan jaringannya ke sirkuit. Hanya bisa ada satu otorisasi per jaringan virtual. Namun, kapan saja, pemilik sirkuit dapat menggunakan **Remove-AzExpressRouteCircuitAuthorization** untuk menghapus otorisasi yang ditetapkan ke jaringan virtual. Ketika hal tersebut terjadi, jaringan virtual terkait tidak lagi dapat menggunakan sirkuit ExpressRoute untuk tersambung ke Azure.

## EXAMPLES

### Contoh 1: Menghapus otorisasi sirkuit dari sirkuit ExpressRoute
```
$Circuit = Get-AzExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Remove-AzExpressRouteCircuitAuthorization -Name "ContosoCircuitAuthorization" -Circuit $Circuit
Set-AzExpressRouteCircuit -ExpressRouteCircuit $Circuit
```

Contoh ini menghapus otorisasi sirkuit dari sirkuit ExpressRoute. Perintah pertama menggunakan cmdlet **Get-AzExpressRouteCircuit** untuk membuat referensi objek ke sirkuit ExpressRoute bernama ContosoCircuit dan menyimpan hasilnya dalam variabel bernama $Circuit.

Perintah kedua menandai otorisasi sirkuit ContosoCircuitAuthorization untuk penghapusan.

Perintah ketiga menggunakan cmdlet Set-AzExpressRouteCircuit untuk mengonfirmasi penghapusan sirkuit ExpressRoute yang disimpan dalam variabel $Circuit.

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
Menentukan objek ExpressRouteCircuit yang dihapus cmdlet ini.

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
Menentukan nama otorisasi sirkuit yang dihapus cmdlet ini.

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
Cmdlet ini menerima instance pipelined objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit** .

## OUTPUTS

### PSExpressRouteCircuit
Cmdlet ini mengubah instans objek **Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit** yang sudah ada.

## NOTES

## RELATED LINKS

[Add-AzExpressRouteCircuitAuthorization](./Add-AzExpressRouteCircuitAuthorization.md)

[Get-AzExpressRouteCircuit](./Get-AzExpressRouteCircuit.md)

[Get-AzExpressRouteCircuitAuthorization](./Get-AzExpressRouteCircuitAuthorization.md)

[New-AzExpressRouteCircuitAuthorization](./New-AzExpressRouteCircuitAuthorization.md)

[Set-AzExpressRouteCircuit](./Set-AzExpressRouteCircuit.md)
