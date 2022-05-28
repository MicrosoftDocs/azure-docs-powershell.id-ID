---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/add-azexpressrouteportauthorization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzExpressRoutePortAuthorization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzExpressRoutePortAuthorization.md
ms.openlocfilehash: 38bc7452c160cc6f815be55d69cb90ec04746b61
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500437"
---
# Add-AzExpressRoutePortAuthorization

## SYNOPSIS
Menambahkan otorisasi ExpressRoutePort.

## SYNTAX

```
Add-AzExpressRoutePortAuthorization -Name <String> -ExpressRoutePort <PSExpressRoutePort>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzExpressRoutePortAuthorization** menambahkan otorisasi ke ExpressRoutePort.
Pemilik ExpressRoutePort dapat membuat otorisasi ini yang menghasilkan kunci otorisasi yang dapat digunakan oleh pemilik sirkuit ExpressRoute untuk membuat sirkuit di ExpressRoutePort (dengan pemilik yang berbeda). Hanya satu sirkuit yang dapat dibuat dengan satu otorisasi ExpressRoutePort. **Add-AzExpressRoutePortAuthorization** menambahkan otorisasi baru ke ExpressRoutePort dan, pada saat yang sama, menghasilkan kunci otorisasi yang sesuai. Kunci ini dapat dilihat kapan saja dengan menjalankan cmdlet **Get-AzExpressRoutePortAuthorization** dan, sesuai kebutuhan, kemudian dapat disalin dan diteruskan ke pemilik sirkuit yang sesuai.

## EXAMPLES

### Contoh 1
```powershell
$ERPort = Get-AzExpressRoutePort -Name "ContosoPort" -ResourceGroupName "ContosoResourceGroup"
```
```output
Name                       : ContosoPort
ResourceGroupName          : ContosoResourceGroup
Location                   : westcentralus
Id                         : /subscriptions/62364504-2406-418e-971c-05822ff72fad/resourceGroups/ContosoResourceGroup/pr
                             oviders/Microsoft.Network/expressRoutePorts/ContosoPort
Etag                       : W/"cf987288-013e-40bf-a2aa-b29d017e7b7f"
ResourceGuid               : 4c0e5cdb-79e1-4cb8-a430-0ce9b24472ca
ProvisioningState          : Succeeded
PeeringLocation            : Area51-ERDirect
BandwidthInGbps            : 100
ProvisionedBandwidthInGbps : 0
Encapsulation              : QinQ
Mtu                        : 1500
EtherType                  : 0x8100
AllocationDate             : Thursday, March 31, 2022
Identity                   : null
Links                      : [
                               {
                                 "Name": "link1",
                                 "Etag": "W/\"cf987288-013e-40bf-a2aa-b29d017e7b7f\"",
                                 "Id": "/subscriptions/62364504-2406-418e-971c-05822ff72fad/resourceGroups/ContosoResou
                             rceGroup/providers/Microsoft.Network/expressRoutePorts/ContosoPort/links/link1",
                                 "RouterName": "a51-test-06gmr-cis-3",
                                 "InterfaceName": "HundredGigE15/15/19",
                                 "PatchPanelId": "PP:0123:1110201 - Port 42",
                                 "RackId": "A51 02050-0123-L",
                                 "ConnectorType": "LC",
                                 "AdminState": "Disabled",
                                 "ProvisioningState": "Succeeded",
                                 "MacSecConfig": {
                                   "SciState": "Disabled",
                                   "Cipher": "GcmAes128"
                                 }
                               },
                               {
                                 "Name": "link2",
                                 "Etag": "W/\"cf987288-013e-40bf-a2aa-b29d017e7b7f\"",
                                 "Id": "/subscriptions/62364504-2406-418e-971c-05822ff72fad/resourceGroups/ContosoResou
                             rceGroup/providers/Microsoft.Network/expressRoutePorts/ContosoPort/links/link2",
                                 "RouterName": "a51-test-06gmr-cis-4",
                                 "InterfaceName": "HundredGigE15/15/19",
                                 "PatchPanelId": "2050:0124:1110854 - Port 42",
                                 "RackId": "A51 02050-0124-L",
                                 "ConnectorType": "LC",
                                 "AdminState": "Disabled",
                                 "ProvisioningState": "Succeeded",
                                 "MacSecConfig": {
                                   "SciState": "Disabled",
                                   "Cipher": "GcmAes128"
                                 }
                               }
                             ]
Circuits                   : []
```
```powershell
Add-AzExpressRoutePortAuthorization -Name "ContosoPortAuthorization" -ExpressRoutePort $ERPort
```
```output
Name                   : ContosoPortAuthorization
Id                     : /subscriptions/62364504-2406-418e-971c-05822ff72fad/resourceGroups/ContosoResourceGroup/provid
                         ers/Microsoft.Network/expressRoutePorts/ContosoPort/authorizations/ContosoPortAuthorization
Etag                   : W/"36ccc199-c371-4d19-88cc-90d51bfe7ea9"
AuthorizationKey       : 10d01cd7-0b67-4c44-88ca-51e7effa452d
AuthorizationUseStatus : Available
ProvisioningState      : Succeeded
CircuitResourceUri     :
```


Perintah dalam contoh ini menambahkan otorisasi baru ke ExpressRoutePort yang ada. Perintah pertama menggunakan **Get-AzExpressRoutePort** untuk membuat referensi objek ke ExpressRoutePort bernama ContosoPort. Referensi objek tersebut disimpan dalam variabel bernama $ERPort.
Pada perintah kedua, cmdlet **Add-AzExpressRoutePortAuthorization** digunakan untuk menambahkan otorisasi baru (ContosoPortAuthorization) ke ExpressRoutePort.

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

### -ExpressRoutePort
Menentukan ExpressRoutePort tempat cmdlet ini menambahkan otorisasi.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Menentukan nama unik untuk otorisasi ExpressRoutePort baru.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePortAuthorization

## NOTES

## RELATED LINKS

[Get-AzExpressRoutePortAuthorization](./Get-AzExpressRoutePortAuthorization.md)

[Remove-AzExpressRoutePortAuthorization](./Remove-AzExpressRoutePortAuthorization.md)
