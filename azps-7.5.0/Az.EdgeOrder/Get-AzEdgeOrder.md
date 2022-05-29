---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/get-azedgeorder
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrder.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrder.md
ms.openlocfilehash: 0d0f592bb5d12aff2ef6847786f2026781203d0e
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145770042"
---
# Get-AzEdgeOrder

## SYNOPSIS
Mendapat pesanan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.edgeorder/get-azedgeorder) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzEdgeOrder [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzEdgeOrder -Location <String> -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzEdgeOrder -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapat pesanan.

## EXAMPLES

### Contoh 1: Dapatkan detail pesanan
```powershell
$order = Get-AzEdgeOrder -Name pwOrderItem11 -SubscriptionId "SubscriptionId" -Location "eastus" -ResourceGroupName "resourceGroupName"
$order | Format-List
```

```output
CurrentStageDisplayName      :
CurrentStageName             : Placed
CurrentStageStartTime        : 11/16/2021 10:35:00 AM
CurrentStageStatus           : Succeeded
Id                           : /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/locations/eastus/orders/pwOrderItem11
Name                         : pwOrderItem11
OrderItemId                  : {/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/orderItems/examplePowershell}
OrderStageHistory            : {, }
SystemData                   : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20.SystemData
Type                         : Microsoft.EdgeOrder/orders
```

Dapatkan detail pesanan

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Nama wilayah Azure.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama pesanan

```yaml
Type: System.String
Parameter Sets: Get
Aliases: OrderName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IOrderResource

## NOTES

ALIAS

## RELATED LINKS

