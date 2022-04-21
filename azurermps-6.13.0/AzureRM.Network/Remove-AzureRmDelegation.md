---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/remove-azurermdelegation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmDelegation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmDelegation.md
ms.openlocfilehash: 1daa68e021646d91a2ab1b45382b137771411325
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142856548"
---
# Remove-AzureRmDelegation

## SYNOPSIS
Menghapus delegasi layanan dari subnet yang disediakan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmDelegation -Name <String> -Subnet <PSSubnet> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmDelegation** menggunakan Subnet dengan delegasi dan menghapus delegasi bernama dari subnet tersebut.

## EXAMPLES

### Contoh 1
```powershell
# Add a delegation to an existing subnet
PS C:\> $vnet = Get-AzureRmVirtualNetwork -Name "myVNet" -ResourceGroupName "myResourceGroup"
PS C:\> $subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "mySubnet" -VirtualNetwork $vnet
PS C:\> $subnet = Add-AzureRmDelegation -Name "myDelegation" -ServiceName "Microsoft.Sql/servers" -Subnet $subnet
PS C:\> Set-AzureRmVirtualNetwork $vnet

# Remove the delegation
PS C:\> $vnet = Get-AzureRmVirtualNetwork -Name "myVNet" -ResourceGroupName "myResourceGroup"
PS C:\> $subnet = Get-AzureRmVirtualNetworkSubnetConfig -Name "mySubnet" -VirtualNetwork $vnet
PS C:\> $subnet = Remove-AzureRmDelegation -Name "myDelegation" -Subnet $subnet
PS C:\> Set-AzureRmVirtualNetwork $vnet
```

Dalam contoh ini, paruh pertama (ditemukan di bawah _"Tambahkan delegasi ke subnet yang sudah ada"_) identik dengan [Add-AzureRmDelegation](./Add-AzureRmDelegation.md). Di paruh kedua, dua cmdlet pertama mengambil subnet yang menarik, merefresh salinan lokal dengan apa yang ada di server. Cmdlet ketiga menghapus delegasi yang dibuat pada paruh pertama dari _mySubnet_ dan menyimpan subnet yang diperbarui di _$subnet_. Cmdlet terakhir memperbarui server dengan delegasi yang dihapus.

## PARAMETERS

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

### -Nama
Nama delegasi

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

### -ServiceName
Nama layanan tempat subnet harus didelegasikan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSSubnet
### System.String
## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSSubnet
## NOTES

## RELATED LINKS

[Add-AzureRmDelegation](./Add-AzureRmDelegation.md)
 [Get-AzureRmDelegation](./Get-AzureRmDelegation.md)
 [New-AzureRmDelegation](./New-AzureRmDelegation.md)
 [Get-AzureRmVirtualNetwork](./Get-AzureRmVirtualNetwork.md)
 [Get-AzureRmVirtualNetworkSubnetConfig](./Get-AzureRmVirtualNetworkSubnetConfig.md)
 [Set-AzureRmVirtualNetwork](./Set-AzureRmVirtualNetwork.md)
