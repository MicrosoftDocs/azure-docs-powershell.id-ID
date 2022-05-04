---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azvirtualnetworkgatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkGatewayNatRule.md
ms.openlocfilehash: 850381b3ed9131140346c9563c788db4bbd56422
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144705990"
---
# Remove-AzVirtualNetworkGatewayNatRule

## SYNOPSIS
Menghapus atau Menghapus NatRule Gateway Virtual Network.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azvirtualnetworkgatewaynatrule) untuk informasi terbaru.

## SYNTAX

### ByVirtualNetworkGatewayNatRuleName (Default)
```
Remove-AzVirtualNetworkGatewayNatRule -ResourceGroupName <String> -ParentResourceName <String> -Name <String>
 [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualNetworkGatewayNatRuleResourceId
```
Remove-AzVirtualNetworkGatewayNatRule -ResourceId <String> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualNetworkGatewayNatRuleObject
```
Remove-AzVirtualNetworkGatewayNatRule -InputObject <PSVirtualNetworkGatewayNatRule> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Remove-AzVirtualNetworkGatewayNatRule** menghapus aturan nat gateway jaringan virtual dari gateway jaringan virtual Anda.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzVirtualNetworkGatewayNatRule -ResourceGroupName rg1 -ParentResourceName gw1 -Name natRule3
```

```output
Confirm
Are you sure you want to remove resource 'natRule3'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

## PARAMETERS

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Force
Jangan meminta konfirmasi jika Anda ingin menghapus sumber daya

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek VirtualNetworkGatewayNatRule untuk diperbarui.

```yaml
Type: PSVirtualNetworkGatewayNatRule
Parameter Sets: ByVirtualNetworkGatewayNatRuleObject
Aliases: VirtualNetworkGatewayNatRule

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya.

```yaml
Type: String
Parameter Sets: ByVirtualNetworkGatewayNatRuleName
Aliases: ResourceName, VirtualNetworkGatewayNatRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentResourceName
Nama sumber daya induk.

```yaml
Type: String
Parameter Sets: ByVirtualNetworkGatewayNatRuleName
Aliases: ParentVirtualNetworkGatewayName, VirtualNetworkGatewayName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item tempat operasi ini sedang dilakukan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ByVirtualNetworkGatewayNatRuleName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya objek VirtualNetworkGatewayNatRule yang akan dihapus.

```yaml
Type: String
Parameter Sets: ByVirtualNetworkGatewayNatRuleResourceId
Aliases: VirtualNetworkGatewayNatRuleId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
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

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGatewayNatRule

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
