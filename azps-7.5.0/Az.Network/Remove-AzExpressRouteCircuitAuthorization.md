---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 38D57CE4-6994-4BDA-A50E-28680EF4E568
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 34cd1a24a4cd9def2d887d330199325fd102e1b3
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145670782"
---
# Remove-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Menghapus otorisasi konfigurasi ExpressRoute yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azexpressroutecircuitauthorization) untuk informasi terbaru.

## SYNTAX

```
Remove-AzExpressRouteCircuitAuthorization [-Name <String>] -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzExpressRouteCircuitAuthorization** menghapus otorisasi yang ditetapkan ke sirkuit ExpressRoute. Sirkuit ExpressRoute menghubungkan jaringan lokal Anda ke Azure dengan menggunakan penyedia konektivitas alih-alih Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; otorisasi ini menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringannya ke sirkuit. Hanya ada satu otorisasi per jaringan virtual. Namun, kapan saja, pemilik sirkuit dapat menggunakan **Remove-AzExpressRouteCircuitAuthorization** untuk menghapus otorisasi yang ditetapkan ke jaringan virtual. Ketika itu terjadi, jaringan virtual yang sesuai tidak lagi dapat menggunakan sirkuit ExpressRoute untuk menyambungkan ke Azure.

## EXAMPLES

### Contoh 1: Menghapus otorisasi sirkuit dari sirkuit ExpressRoute
```powershell
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

### -Name
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## NOTES

## RELATED LINKS

[Add-AzExpressRouteCircuitAuthorization](./Add-AzExpressRouteCircuitAuthorization.md)

[Get-AzExpressRouteCircuit](./Get-AzExpressRouteCircuit.md)

[Get-AzExpressRouteCircuitAuthorization](./Get-AzExpressRouteCircuitAuthorization.md)

[New-AzExpressRouteCircuitAuthorization](./New-AzExpressRouteCircuitAuthorization.md)

[Set-AzExpressRouteCircuit](./Set-AzExpressRouteCircuit.md)
