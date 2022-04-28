---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/add-azdelegation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzDelegation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzDelegation.md
ms.openlocfilehash: b4cacecc37e6c076e4cedef8da499f6a5d917210
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144183475"
---
# Add-AzDelegation

## SYNOPSIS
Menambahkan delegasi ke subnet.

## SYNTAX

```
Add-AzDelegation -Name <String> -ServiceName <String> -Subnet <PSSubnet>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzDelegation** menambahkan delegasi layanan ke subnet Azure.

## EXAMPLES

### Contoh 1: Menambahkan delegasi
```powershell
$vnet = Get-AzVirtualNetwork -Name "myVNet" -ResourceGroupName "myResourceGroup"
$subnet = Get-AzVirtualNetworkSubnetConfig -Name "mySubnet" -VirtualNetwork $vnet
$subnet = Add-AzDelegation -Name "myDelegation" -ServiceName "Microsoft.Sql/servers" -Subnet $subnet
Set-AzVirtualNetwork $vnet
```

Perintah pertama mengambil jaringan virtual tempat subnet berada. Perintah kedua mengisolasi subnet yang menarik - yang ingin Anda delegasikan. Perintah ketiga menambahkan delegasi ke subnet. Contoh khusus ini akan berguna ketika Anda ingin mengaktifkan SQL untuk membuat titik akhir antarmuka di subnet ini. Perintah akhir mengirimkan subnet yang diperbarui ke server untuk benar-benar memperbarui subnet Anda.

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

### -Name
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

### -Subnet
Subnet

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSSubnet

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSSubnet

## NOTES

## RELATED LINKS

[Get-AzVirtualNetwork](./Get-AzVirtualNetwork.md)
 [Get-AzVirtualNetworkSubnetConfig](./Get-AzVirtualNetworkSubnetConfig.md)
 [Set-AzVirtualNetwork](./Set-AzVirtualNetwork.md)