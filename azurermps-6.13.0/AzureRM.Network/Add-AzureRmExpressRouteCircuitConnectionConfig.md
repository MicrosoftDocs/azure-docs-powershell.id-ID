---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 7b4a8c9f-874c-4a27-b87e-c8ad7e73188d
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/add-azurermexpressroutecircuitconnectionconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmExpressRouteCircuitConnectionConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmExpressRouteCircuitConnectionConfig.md
ms.openlocfilehash: 6758557deef115f394fc44a820242163e3d604ea
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141778432"
---
# Add-AzureRmExpressRouteCircuitConnectionConfig

## SYNOPSIS
Menambahkan konfigurasi koneksi sirkuit ke Private Peering dari Express Route Circuit. 

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResource (Default)
```
Add-AzureRmExpressRouteCircuitConnectionConfig [-Name] <String> [-ExpressRouteCircuit] <PSExpressRouteCircuit>
 [-AddressPrefix] <String> [-AuthorizationKey <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetByResourceId
```
Add-AzureRmExpressRouteCircuitConnectionConfig [-Name] <String> [-ExpressRouteCircuit] <PSExpressRouteCircuit>
 [-PeerExpressRouteCircuitPeering] <String> [-AddressPrefix] <String> [-AuthorizationKey <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmExpressRouteCircuitConnectionConfig** menambahkan konfigurasi koneksi sirkuit ke peering pribadi untuk sirkuit ExpressRoute. Hal ini memungkinkan peering dua Express Route Circuits lintas kawasan atau langganan. Perhatikan bahwa, setelah menjalankan **Add-AzureRmExpressRouteCircuitPeeringConfig**, Anda harus memanggil cmdlet Set-AzureRmExpressRouteCircuit untuk mengaktifkan konfigurasi.

## EXAMPLES

### Contoh 1: Menambahkan sumber daya koneksi sirkuit ke sirkuit ExpressRoute yang sudah ada
```
$circuit_init = Get-AzureRmExpressRouteCircuit -Name $initiatingCircuitName -ResourceGroupName $rg
$circuit_peer = Get-AzureRmExpressRouteCircuit -Name $peeringCircuitName -ResourceGroupName $rg
$addressSpace = '60.0.0.0/29'
Add-AzureRmExpressRouteCircuitConnectionConfig -Name $circuitConnectionName -ExpressRouteCircuit $circuit_init -PeerExpressRouteCircuitPeering $circuit_peer.Peerings[0].Id -AddressPrefix $addressSpace -AuthorizationKey $circuit_peer.Authorizations[0].AuthorizationKey
Set-AzureRmExpressRouteCircuit -ExpressRouteCircuit $circuit_init
```

### Contoh 2: Menambahkan konfigurasi koneksi sirkuit menggunakan Piping ke Sirkuit ExpressRoute yang sudah ada
```
$circuit_peer = Get-AzureRmExpressRouteCircuit -Name $peeringCircuitName -ResourceGroupName $rg
$addressSpace = '60.0.0.0/29'
Get-AzureRmExpressRouteCircuit -Name $initiatingCircuitName -ResourceGroupName $rg|Add-AzureRmExpressRouteCircuitConnectionConfig -Name $circuitConnectionName -PeerExpressRouteCircuitPeering $circuit_peer.Peerings[0].Id -AddressPrefix $addressSpace -AuthorizationKey $circuit_peer.Authorizations[0].AuthorizationKey |Set-AzureRmExpressRouteCircuit
```

## PARAMETERS

### -AddressPrefix
Minimal /29 ruang alamat pelanggan untuk membuat terowongan VxLan antara Express Route Circuits

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthorizationKey
Otorisasi Key to peer Express Route Circuit dalam langganan lain. Otorisasi pada sirkuit rekan dapat dibuat menggunakan perintah yang sudah ada.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Sirkuit ExpressRoute sedang dimodifikasi. Ini adalah objek Azure yang dikembalikan oleh cmdlet **Get-AzureRmExpressRouteCircuit** .

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya koneksi sirkuit yang akan ditambahkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerExpressRouteCircuitPeering
Id Sumber Daya untuk Private Peering dari sirkuit jarak jauh yang akan diintip dengan sirkuit saat ini.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit
Parameter: ExpressRouteCircuit (ByValue)

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## CATATAN

## RELATED LINKS

[Get-AzureRmExpressRouteCircuit](Get-AzureRmExpressRouteCircuit.md)

[Get-AzureRmExpressRouteCircuitConnectionConfig](Get-AzureRmExpressRouteCircuitConnectionConfig.md)

[Remove-AzureRmExpressRouteCircuitConnectionConfig](Remove-AzureRmExpressRouteCircuitConnectionConfig.md)





[Set-AzureRmExpressRouteCircuit](Set-AzureRmExpressRouteCircuit.md)

[Get-AzureRmExpressRouteCircuit](Get-AzureRmExpressRouteCircuit.md)
