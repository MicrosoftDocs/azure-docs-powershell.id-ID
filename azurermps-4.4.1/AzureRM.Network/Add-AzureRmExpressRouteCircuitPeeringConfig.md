---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: C44AD23A-E575-418C-BE90-323B44D6D2E8
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmExpressRouteCircuitPeeringConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Add-AzureRmExpressRouteCircuitPeeringConfig.md
ms.openlocfilehash: 5655fafa866fbc3702a1c6bf017caddd21df6fab
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423880"
---
# Add-AzureRmExpressRouteCircuitPeeringConfig

## SYNOPSIS
Menambahkan konfigurasi peering ke sirkuit ExpressRoute.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResource (Default)
```
Add-AzureRmExpressRouteCircuitPeeringConfig -Name <String> -ExpressRouteCircuit <PSExpressRouteCircuit>
 -PeeringType <String> -PeerASN <Int32> -PrimaryPeerAddressPrefix <String> -SecondaryPeerAddressPrefix <String>
 -VlanId <Int32> [-SharedKey <String>]
 [-MicrosoftConfigAdvertisedPublicPrefixes <System.Collections.Generic.List`1[System.String]>]
 [-MicrosoftConfigCustomerAsn <Int32>] [-MicrosoftConfigRoutingRegistryName <String>]
 [-PeerAddressType <String>] [-LegacyMode <Boolean>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### MicrosoftPeeringConfigroutFilterId
```
Add-AzureRmExpressRouteCircuitPeeringConfig -Name <String> -ExpressRouteCircuit <PSExpressRouteCircuit>
 -PeeringType <String> -PeerASN <Int32> -PrimaryPeerAddressPrefix <String> -SecondaryPeerAddressPrefix <String>
 -VlanId <Int32> [-SharedKey <String>]
 [-MicrosoftConfigAdvertisedPublicPrefixes <System.Collections.Generic.List`1[System.String]>]
 [-MicrosoftConfigCustomerAsn <Int32>] [-MicrosoftConfigRoutingRegistryName <String>] -RouteFilterId <String>
 [-PeerAddressType <String>] [-LegacyMode <Boolean>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### MicrosoftPeeringConfigroutFilter
```
Add-AzureRmExpressRouteCircuitPeeringConfig -Name <String> -ExpressRouteCircuit <PSExpressRouteCircuit>
 -PeeringType <String> -PeerASN <Int32> -PrimaryPeerAddressPrefix <String> -SecondaryPeerAddressPrefix <String>
 -VlanId <Int32> [-SharedKey <String>]
 [-MicrosoftConfigAdvertisedPublicPrefixes <System.Collections.Generic.List`1[System.String]>]
 [-MicrosoftConfigCustomerAsn <Int32>] [-MicrosoftConfigRoutingRegistryName <String>]
 -RouteFilter <PSRouteFilter> [-PeerAddressType <String>] [-LegacyMode <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmExpressRouteCircuitPeeringConfig** menambahkan konfigurasi peering ke sirkuit ExpressRoute. Sirkuit ExpressRoute menyambungkan jaringan lokal Anda ke awan Microsoft dengan menggunakan penyedia konektivitas, bukan Internet publik. Perhatikan bahwa, setelah menjalankan **Add-AzureRmExpressRouteCircuitPeeringConfig**, Anda harus memanggil cmdlet Set-AzureRmExpressRouteCircuit untuk mengaktifkan konfigurasi.

## EXAMPLES

### Contoh 1: Menambahkan rekan ke sirkuit ExpressRoute yang sudah ada
```
$circuit = Get-AzureRmExpressRouteCircuit -Name $CircuitName -ResourceGroupName $rg
$parameters = @{
    Name = 'AzurePrivatePeering'
    Circuit = $circuit
    PeeringType = 'AzurePrivatePeering'
    PeerASN = 100
    PrimaryPeerAddressPrefix = '10.6.1.0/30'
    SecondaryPeerAddressPrefix = '10.6.2.0/30'
    VlanId  = 200
}
Add-AzureRmExpressRouteCircuitPeeringConfig @parameters
Set-AzureRmExpressRouteCircuit -ExpressRouteCircuit $circuit
```

## PARAMETERS

### -ExpressRouteCircuit
Sirkuit ExpressRoute sedang diubah. Ini adalah objek Azure yang dikembalikan oleh cmdlet **Get-AzureRmExpressRouteCircuit.**

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

### -LegacyMode
Mode warisan Peering

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MicrosoftConfigAdvertisedPublicPrefixes
Untuk PeeringType MicrosoftPeering, Anda harus menyediakan daftar semua prefiks yang Anda rencanakan untuk diiklankan melalui sesi BGP. Hanya prefiks alamat IP publik yang diterima. Anda bisa mengirim daftar yang dipisahkan koma jika Anda berencana mengirim rangkaian prefiks. Prefiks ini harus didaftarkan kepada Anda dalam Routing Registry Name (RIR / IRR).

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MicrosoftConfigCustomerAsn
Jika Anda mengiklankan prefiks yang tidak terdaftar ke nomor peering AS, Anda bisa menentukan jumlah AS tempat mereka terdaftar.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MicrosoftConfigRoutingRegistryName
Nama Registri Perutean (RIR / IRR, Routing Registry Name) tempat angka dan prefiks AS didaftarkan.

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

### -Nama
Nama hubungan peering yang akan ditambahkan.

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

### -PeerAddressType
PeerAddressType

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PeerASN
Jumlah AS sirkuit ExpressRoute Anda. Ini harus menjadi ASN Publik ketika PeeringType adalah AzurePublicPeering.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeeringType
Nilai yang dapat diterima untuk parameter ini adalah: `AzurePrivatePeering` , `AzurePublicPeering` , dan `MicrosoftPeering`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 
Accepted values: AzurePrivatePeering, AzurePublicPeering, MicrosoftPeering

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryPeerAddressPrefix
Ini adalah rentang Alamat IP untuk jalur perutean utama dari hubungan peering ini. Hal ini harus termasuk subnet CIDR /30. Alamat bernomor ganjil pertama dalam subnet ini harus ditetapkan ke antarmuka perute Anda. Azure akan mengonfigurasi alamat bernomor genap berikutnya ke antarmuka perute Azure.

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

### -RouteFilter
Ini adalah objek RouteFilter yang sudah ada.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSRouteFilter
Parameter Sets: MicrosoftPeeringConfigRoutFilter
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteFilterId
Ini adalah Id sumber daya dari objek RouteFilter yang sudah ada.

```yaml
Type: System.String
Parameter Sets: MicrosoftPeeringConfigRoutFilterId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecondaryPeerAddressPrefix
Ini adalah rentang Alamat IP untuk jalur perutean sekunder dari hubungan peering ini. Hal ini harus termasuk subnet CIDR /30. Alamat bernomor ganjil pertama dalam subnet ini harus ditetapkan ke antarmuka perute Anda. Azure akan mengonfigurasi alamat bernomor genap berikutnya ke antarmuka perute Azure.

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

### -SharedKey
Ini adalah hash MD5 opsional yang digunakan sebagai kunci bersama untuk konfigurasi peering.

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

### -VlanId
Ini adalah nomor Id VLAN yang ditetapkan untuk peering ini.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSExpressRouteCircuit
Parameter 'ExpressRouteCircuit' menerima nilai tipe 'PSExpressRouteCircuit' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit

## CATATAN

## RELATED LINKS

[Get-AzureRmExpressRouteCircuit](Get-AzureRmExpressRouteCircuit.md)

[New-AzureRmExpressRouteCircuitPeeringConfig](New-AzureRmExpressRouteCircuitPeeringConfig.md)

[Remove-AzureRmExpressRouteCircuitPeeringConfig](Remove-AzureRmExpressRouteCircuitPeeringConfig.md)

[Set-AzureRmExpressRouteCircuit](Set-AzureRmExpressRouteCircuit.md)
