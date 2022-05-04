---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azvirtualnetworkgatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVirtualNetworkGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVirtualNetworkGatewayNatRule.md
ms.openlocfilehash: 00bc41e76ef69e1738afcf2517544d57d99185fa
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144659160"
---
# Get-AzVirtualNetworkGatewayNatRule

## SYNOPSIS
Mendapatkan Virtual Network Gateway NatRule.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azvirtualnetworkgatewaynatrule) untuk informasi terbaru.

## SYNTAX

### ByVirtualNetworkGatewayName (Default)
```
Get-AzVirtualNetworkGatewayNatRule -ResourceGroupName <String> -ParentResourceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByVirtualNetworkGatewayObject
```
Get-AzVirtualNetworkGatewayNatRule -ParentObject <PSVirtualNetworkGateway> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByVirtualNetworkGatewayResourceId
```
Get-AzVirtualNetworkGatewayNatRule -ParentResourceId <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzVirtualNetworkGatewayNatRule** mengembalikan objek aturan nat gateway jaringan virtual gateway jaringan virtual Anda berdasarkan Nama dan ParentResourceName.

## EXAMPLES

### Contoh 1
```powershell
get-azVirtualNetworkGatewayNatRule -ResourceGroupName "rg1" -Name "natRule1" -ParentResourceName gw1
```

```output
Name              : natRule1
ProvisioningState : Succeeded
Type              : Static
Mode              : IngressSnat
InternalMappings  : [
                      {
                        "AddressSpace": "25.0.0.0/16"
                      }
                    ]
ExternalMappings  : [
                      {
                        "AddressSpace": "30.0.0.0/16"
                      }
                    ]
IpConfigurationId :
Id                : /subscriptions/7afd8f92-c220-4f53-886e-1df53a69afd4/resourceGroups/rg1/providers/Microsoft.Network/virtualNetworkGateways/gw1/natRules/natRule1
Etag              : W/"5150d788-e165-42ba-99c4-8138a545fce9"
```

### Contoh 2: 
```powershell
get-azVirtualNetworkGatewayNatRule -ResourceGroupName "rg1" -ParentResourceName "gw1"
```

```output
Name              : natRule1
ProvisioningState : Succeeded
Type              : Static
Mode              : IngressSnat
InternalMappings  : [
                      {
                        "AddressSpace": "25.0.0.0/16"
                      }
                    ]
ExternalMappings  : [
                      {
                        "AddressSpace": "30.0.0.0/16"
                      }
                    ]
IpConfigurationId :
Id                : /subscriptions/7afd8f92-c220-4f53-886e-1df53a69afd4/resourceGroups/rg1/providers/Microsoft.Network/virtualNetworkGateways/gw1/natRules/natRule1
Etag              : W/"5150d788-e165-42ba-99c4-8138a545fce9"

Name              : natRule2
ProvisioningState : Succeeded
Type              : Static
Mode              : EgressSnat
InternalMappings  : [
                      {
                        "AddressSpace": "20.0.0.0/16"
                      }
                    ]
ExternalMappings  : [
                      {
                        "AddressSpace": "50.0.0.0/16"
                      }
                    ]
IpConfigurationId :
Id                : /subscriptions/7afd8f92-c220-4f53-886e-1df53a69afd4/resourceGroups/rg1/providers/Microsoft.Network/virtualNetworkGateways/gw1/natRules/natRule2
Etag              : W/"5150d788-e165-42ba-99c4-8138a545fce9"
```


## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName, VirtualNetworkGatewayNatRuleName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentObject
VirtualNetworkGateway induk untuk VirtualNetworkGatewayNatRule ini.

```yaml
Type: PSVirtualNetworkGateway
Parameter Sets: ByVirtualNetworkGatewayObject
Aliases: ParentVirtualNetworkGateway, VirtualNetworkGateway

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ParentResourceId
Id sumber daya virtualNetworkGateway induk untuk VirtualNetworkGatewayNatRule ini.

```yaml
Type: String
Parameter Sets: ByVirtualNetworkGatewayResourceId
Aliases: ParentVirtualNetworkGatewayId, VirtualNetworkGatewayId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentResourceName
Nama sumber daya induk.

```yaml
Type: String
Parameter Sets: ByVirtualNetworkGatewayName
Aliases: ParentVirtualNetworkGatewayName, VirtualNetworkGatewayName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ByVirtualNetworkGatewayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule

## NOTES

## RELATED LINKS

[New-AzVirtualNetworkGatewayNatRule](./New-AzVirtualNetworkGatewayNatRule.md)

[Remove-AzVirtualNetworkGatewayNatRule](./Remove-AzVirtualNetworkGatewayNatRule.md)

[Update-AzVirtualNetworkGatewayNatRule](./Update-AzVirtualNetworkGatewayNatRule.md)
