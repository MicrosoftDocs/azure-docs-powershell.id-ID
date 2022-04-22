---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/get-azedgeorderitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderItem.md
ms.openlocfilehash: abc09b8f81c89656f4c285d37138d6b6f658c807
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142941833"
---
# Get-AzEdgeOrderItem

## SYNOPSIS
Mendapatkan item pesanan.

## SYNTAX

### Daftar (Default)
```
Get-AzEdgeOrderItem [-SubscriptionId <String[]>] [-Expand <String>] [-Filter <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzEdgeOrderItem -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Expand <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzEdgeOrderItem -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Expand <String>]
 [-Filter <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan item pesanan.

## EXAMPLES

### Contoh 1: Dapatkan detail orderItem
```powershell
$orderItem = Get-AzEdgeOrderItem -Name examplePowershell -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName"   
$ordderItem | Format-List
```

```output
ForwardAddressContactDetail    : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ContactDetails
ForwardAddressShippingAddress  : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ShippingAddress
ForwardAddressValidationStatus : Valid
Id                             : /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/orderItems/OrderItem-211115074927900249117427
Location                       : eastus
Name                           : OrderItem-211115074927900249117427
OrderId                        : /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/locations/eastus/orders/Order-211115074927650235470998
OrderItemDetail                : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.OrderItemDetails
ReturnAddressContactDetail     : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ContactDetails
ReturnAddressShippingAddress   : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ShippingAddress
ReturnAddressValidationStatus  : Valid
StartTime                      : 11/15/2021 7:49:29 AM
SystemData                     : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20.SystemData
Tag                            : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20.TrackedResourceTags
Type                           : Microsoft.EdgeOrder/orderItems
```

Dapatkan detail orderItem

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

### -Perluas
$expand didukung pada detail perangkat, detail pengiriman ke depan, dan parameter detail pengiriman terbalik.
Masing-masing dapat disediakan sebagai daftar yang dipisahkan koma.
Detail Perangkat untuk item pesanan menyediakan detail tentang perangkat produk, detail Pengiriman Maju dan Terbalik masing-masing menyediakan detail pengiriman maju dan terbalik.

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

### -Filter
$filter didukung untuk memfilter berdasarkan id pesanan. Filter hanya mendukung operasi yang sama dengan.

```yaml
Type: System.String
Parameter Sets: List, List1
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama item pesanan

```yaml
Type: System.String
Parameter Sets: Get
Aliases: OrderItemName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IOrderItemResource

## NOTES

ALIAS

## RELATED LINKS

