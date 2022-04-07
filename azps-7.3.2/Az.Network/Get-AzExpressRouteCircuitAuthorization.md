---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 3D80F94B-AF9D-40C2-BE7E-2F32E5E926D2
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressroutecircuitauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteCircuitAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRouteCircuitAuthorization.md
ms.openlocfilehash: 0f60c6b77bafd834a19b51d7dd31478a6f7fa4cb
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140372270"
---
# Get-AzExpressRouteCircuitAuthorization

## SYNOPSIS
Dapatkan informasi tentang otorisasi sirkuit ExpressRoute.

## SYNTAX

```
Get-AzExpressRouteCircuitAuthorization [-Name <String>] -ExpressRouteCircuit <PSExpressRouteCircuit>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRouteCircuitAuthorization** mendapatkan informasi tentang otorisasi yang ditetapkan untuk sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Pemilik sirkuit ExpressRoute dapat membuat sebanyak 10 otorisasi untuk setiap sirkuit; ini otorisasi menghasilkan kunci otorisasi yang bisa digunakan oleh pemilik jaringan virtual untuk menghubungkan jaringannya ke sirkuit (satu otorisasi per jaringan virtual). Tombol otorisasi, serta informasi lain tentang otorisasi, bisa dilihat kapan saja dengan menjalankan **Get-AzExpressRouteCircuitAuthorization**.

## EXAMPLES

### Contoh 1: Dapatkan semua otorisasi ExpressRoute
```
$Circuit = Get-AzExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
Get-AzExpressRouteCircuitAuthorization -Circuit $Circuit
```

Perintah ini mengembalikan informasi tentang semua otorisasi ExpressRoute yang terkait dengan sirkuit ExpressRoute. Perintah pertama menggunakan cmdlet **Get-AzExpressRouteCircuit** untuk membuat referensi objek sirkuit bernama ContosoCircuit; referensi objek tersebut disimpan di variabel $Circuit. Perintah kedua lalu menggunakan referensi objek itu dan cmdlet **Get-AzExpressRouteCircuitAuthorization** untuk mengembalikan informasi tentang otorisasi yang terkait dengan ContosoCircuit.

### Contoh 2: Dapatkan semua otorisasi ExpressRoute menggunakan cmdlet Where-Object
```
$Circuit = Get-AzExpressRouteCircuit -Name "ContosoCircuit" -ResourceGroupName "ContosoResourceGroup"
 Get-AzExpressRouteCircuitAuthorization -Circuit $Circuit | Where-Object {$_.AuthorizationUseStatus -eq "Available"}
```

Perintah ini menunjukkan variasi pada perintah yang digunakan dalam Contoh 1. Namun, dalam kasus ini, informasi hanya dikembalikan untuk otorisasi yang tersedia untuk digunakan (yaitu, untuk otorisasi yang belum ditetapkan ke jaringan virtual). Untuk melakukan ini, informasi otorisasi sirkuit dikembalikan di perintah 2 dan pipa ke cmdlet **Where-Object** .
**Jika kemudian Objek** hanya memilih otorisasi dengan properti *AuthorizationUseStatus* yang diatur ke Tersedia. Untuk mencantumkan izin yang tidak tersedia saja, gunakan sintaks ini untuk klausul Where: `{$_.AuthorizationUseStatus -ne "Available"}`

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
Menentukan otorisasi sirkuit ExpressRoute.

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
Menentukan nama otorisasi sirkuit ExpressRoute yang akan cmdlet ini dapatkan.
-Name "ContosoCircuitAuthorization"

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuitAuthorization

## CATATAN

## RELATED LINKS

[Add-AzExpressRouteCircuitAuthorization](./Add-AzExpressRouteCircuitAuthorization.md)

[Get-AzExpressRouteCircuit](./Get-AzExpressRouteCircuit.md)

[New-AzExpressRouteCircuitAuthorization](./New-AzExpressRouteCircuitAuthorization.md)

[Remove-AzExpressRouteCircuitAuthorization](./Remove-AzExpressRouteCircuitAuthorization.md)
