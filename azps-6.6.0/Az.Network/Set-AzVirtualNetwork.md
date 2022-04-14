---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 93D8A341-540A-43F1-8C62-28323EAA58E0
online version: https://docs.microsoft.com/powershell/module/az.network/set-azvirtualnetwork
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzVirtualNetwork.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzVirtualNetwork.md
ms.openlocfilehash: 2bcd1bf802e2148f30b97e3a244df676e0efbb27
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142045667"
---
# Set-AzVirtualNetwork

## SYNOPSIS
Memperbarui jaringan virtual.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azvirtualnetwork) untuk informasi terbaru.

## SYNTAX

```
Set-AzVirtualNetwork -VirtualNetwork <PSVirtualNetwork> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVirtualNetwork** memperbarui jaringan virtual.

## EXAMPLES

### 1: Membuat jaringan virtual dan menghapus salah satu subnetnya
```powershell
New-AzResourceGroup -Name TestResourceGroup -Location centralus ## Create resource group 
$frontendSubnet = New-AzVirtualNetworkSubnetConfig -Name frontendSubnet -AddressPrefix "10.0.1.0/24" ## Create frontend subnet 
$backendSubnet = New-AzVirtualNetworkSubnetConfig -Name backendSubnet -AddressPrefix "10.0.2.0/24" ## Create backend subnet

$virtualNetwork = New-AzVirtualNetwork -Name MyVirtualNetwork -ResourceGroupName TestResourceGroup `
    -Location centralus -AddressPrefix "10.0.0.0/16" -Subnet $frontendSubnet,$backendSubnet ## Create virtual network

Remove-AzVirtualNetworkSubnetConfig -Name backendSubnet -VirtualNetwork $virtualNetwork ## Remove subnet from in memory representation of virtual network

$virtualNetwork | Set-AzVirtualNetwork ## Remove subnet from virtual network
```

Contoh ini membuat jaringan virtual yang disebut TestResourceGroup dengan dua subnet: frontendSubnet dan backendSubnet. Kemudian menghapus subnet backendSubnet dari representasi dalam memori jaringan virtual. Cmdlet Set-AzVirtualNetwork kemudian digunakan untuk menulis status jaringan virtual yang dimodifikasi di sisi layanan. Ketika cmdlet Set-AzVirtualNetwork dijalankan, backendSubnet akan dihapus.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -VirtualNetwork
Menentukan objek jaringan maya yang mewakili status di mana jaringan maya harus disetel.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork
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

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork

## CATATAN

## RELATED LINKS

[Get-AzVirtualNetwork](./Get-AzVirtualNetwork.md)

[Get-AzVirtualNetwork](./Get-AzVirtualNetwork.md)

[New-AzVirtualNetwork](./New-AzVirtualNetwork.md)

[Remove-AzVirtualNetwork](./Remove-AzVirtualNetwork.md)


