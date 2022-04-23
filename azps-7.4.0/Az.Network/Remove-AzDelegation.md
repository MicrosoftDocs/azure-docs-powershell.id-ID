---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azdelegation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzDelegation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzDelegation.md
ms.openlocfilehash: 881e50b397f31e5d89da280ce8d9c48c82a8f262
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143280485"
---
# Remove-AzDelegation

## SYNOPSIS
Menghapus delegasi layanan dari subnet yang disediakan.

## SYNTAX

```
Remove-AzDelegation -Name <String> -Subnet <PSSubnet> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDelegation** menggunakan Subnet dengan delegasi dan menghapus delegasi bernama dari subnet tersebut.

## EXAMPLES

### Contoh 1
```powershell
# Add a delegation to an existing subnet
$vnet = Get-AzVirtualNetwork -Name "myVNet" -ResourceGroupName "myResourceGroup"
$subnet = Get-AzVirtualNetworkSubnetConfig -Name "mySubnet" -VirtualNetwork $vnet
$subnet = Add-AzDelegation -Name "myDelegation" -ServiceName "Microsoft.Sql/servers" -Subnet $subnet
Set-AzVirtualNetwork $vnet

# Remove the delegation
$vnet = Get-AzVirtualNetwork -Name "myVNet" -ResourceGroupName "myResourceGroup"
$subnet = Get-AzVirtualNetworkSubnetConfig -Name "mySubnet" -VirtualNetwork $vnet
$subnet = Remove-AzDelegation -Name "myDelegation" -Subnet $subnet
Set-AzVirtualNetwork $vnet
```

Dalam contoh ini, paruh pertama (ditemukan di bawah _"Tambahkan delegasi ke subnet yang sudah ada"_) identik dengan [Add-AzDelegation](./Add-AzDelegation.md). Di paruh kedua, dua cmdlet pertama mengambil subnet yang menarik, merefresh salinan lokal dengan apa yang ada di server. Cmdlet ketiga menghapus delegasi yang dibuat pada paruh pertama dari _mySubnet_ dan menyimpan subnet yang diperbarui di _$subnet_. Cmdlet terakhir memperbarui server dengan delegasi yang dihapus.

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

### -Nama
Nama delegasi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subnet
Subnet tempat untuk menghapus delegasi

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSSubnet
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSSubnet

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSSubnet

## NOTES

## RELATED LINKS

[Add-AzDelegation](./Add-AzDelegation.md)
 [Get-AzDelegation](./Get-AzDelegation.md)
 [New-AzDelegation](./New-AzDelegation.md)
 [Get-AzVirtualNetwork](./Get-AzVirtualNetwork.md)
 [Get-AzVirtualNetworkSubnetConfig](./Get-AzVirtualNetworkSubnetConfig.md)
 [Set-AzVirtualNetwork](./Set-AzVirtualNetwork.md)