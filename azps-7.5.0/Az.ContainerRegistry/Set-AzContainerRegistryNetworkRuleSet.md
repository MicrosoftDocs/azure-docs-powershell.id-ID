---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistry.dll-Help.xml
Module Name: Az.ContainerRegistry
online version: https://docs.microsoft.com/powershell/module/az.containerregistry/set-azcontainerregistrynetworkruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Set-AzContainerRegistryNetworkRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Set-AzContainerRegistryNetworkRuleSet.md
ms.openlocfilehash: 18976f691639db3e9059985ab596010549f2b0b3
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145816632"
---
# Set-AzContainerRegistryNetworkRuleSet

## SYNOPSIS
Membuat atau memperbarui seperangkat aturan jaringan. Seperangkat aturan hanya dapat diterapkan ke registri "Premium".

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerregistry/set-azcontainerregistrynetworkruleset) untuk informasi terbaru.

## SYNTAX

### TambahkanAddNetworkRuleWithoutInputObject (Default)
```
Set-AzContainerRegistryNetworkRuleSet -DefaultAction <String> [-NetworkRule <IPSNetworkRule[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AddNetworkRuleWithInputObject
```
Set-AzContainerRegistryNetworkRuleSet [-DefaultAction <String>] [-NetworkRule <IPSNetworkRule[]>]
 -InputObject <PSNetworkRuleSet> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui seperangkat aturan jaringan

## EXAMPLES

### Contoh 1
```powershell
$subnet = New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix "10.0.1.0/24" -ServiceEndpoint "Microsoft.ContainerRegistry"
$vnet = New-AzVirtualNetwork -Name $VnetName -ResourceGroupName $resourceGroupName -Location $location -AddressPrefix "10.0.0.0/16" -Subnet $subnet
$rule = New-AzContainerRegistryNetworkRule -VirtualNetworkRule -VirtualNetworkResourceId $vnet.Subnets[0].Id
$set = Set-AzContainerRegistryNetworkRuleSet -DefaultAction "Allow" -NetworkRule $rule
```

Buat seperangkat aturan jaringan baru.

## PARAMETERS

### -DefaultAction
Tindakan default, bisa berupa 'Izinkan' atau 'Tolak'

```yaml
Type: System.String
Parameter Sets: AddAddNetworkRuleWithoutInputObject
Aliases:
Accepted values: Allow, Deny

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AddNetworkRuleWithInputObject
Aliases:
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -InputObject
Input PSNetworkRuleSet

```yaml
Type: Microsoft.Azure.Commands.ContainerRegistry.Models.PSNetworkRuleSet
Parameter Sets: AddNetworkRuleWithInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkRule
Daftar aturan Jaringan

```yaml
Type: Microsoft.Azure.Commands.ContainerRegistry.Models.IPSNetworkRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.ContainerRegistry.Models.IPSNetworkRule

## OUTPUTS

### Microsoft.Azure.Commands.ContainerRegistry.Models.PSNetworkRuleSet

## NOTES

## RELATED LINKS
