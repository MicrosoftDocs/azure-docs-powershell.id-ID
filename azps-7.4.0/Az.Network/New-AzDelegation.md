---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azdelegation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzDelegation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzDelegation.md
ms.openlocfilehash: bf3b0d295d37ec8decc7b780317f72473b9e530c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142742896"
---
# New-AzDelegation

## SYNOPSIS
Membuat delegasi layanan.

## SYNTAX

```
New-AzDelegation -Name <String> -ServiceName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDelegation** membuat delegasi layanan yang dapat ditambahkan ke subnet.

## EXAMPLES

### Contoh 1
```powershell
$delegation = New-AzDelegation -Name "myDelegation" -ServiceName "Microsoft.Sql/servers"
$vnet = Get-AzVirtualNetwork -Name "myVNet" -ResourceGroupName "myResourceGroup"
$subnet = Get-AzVirtualNetworkSubnetConfig -Name "mySubnet" -VirtualNetwork $vnet
$subnet.Delegations.Add($delegation)
Set-AzVirtualNetwork $vnet
```

Cmdlet pertama membuat delegasi yang dapat ditambahkan ke subnet, dan menyimpannya dalam variabel $delegation. Cmdlet kedua dan ketiga mengambil subnet untuk didelegasikan. Cmdlet keempat menambahkan delegasi yang dibuat ke subnet minat, dan cmdlet akhir mengirimkan konfigurasi yang diperbarui ke server.

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

### -ServiceName
Nama layanan tempat subnet harus didelegasikan

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSDelegation

## NOTES

## RELATED LINKS

[Add-AzDelegation](./Add-AzDelegation.md)
 [Get-AzDelegation](./Get-AzDelegation.md)
 [Hapus-AzDelegation](./Remove-AzDelegation.md)
 [Get-AzVirtualNetwork](./Get-AzVirtualNetwork.md)
 [Get-AzVirtualNetworkSubnetConfig](./Get-AzVirtualNetworkSubnetConfig.md)
 [Set-AzVirtualNetwork](./Set-AzVirtualNetwork.md)