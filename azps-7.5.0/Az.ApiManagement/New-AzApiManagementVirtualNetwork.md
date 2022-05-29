---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: FB5E4ED2-8EF3-462F-A053-7EC82C767E8D
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementvirtualnetwork
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementVirtualNetwork.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementVirtualNetwork.md
ms.openlocfilehash: 9352f54867e1e9eaf60c092f06892e07398d9c8a
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145774938"
---
# New-AzApiManagementVirtualNetwork

## SYNOPSIS
Membuat instans PsApiManagementVirtualNetwork.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementvirtualnetwork) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementVirtualNetwork -SubnetResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementVirtualNetwork** adalah perintah pembantu untuk membuat **instans PsApiManagementVirtualNetwork**.
Perintah ini digunakan dengan **cmdlet Set-AzApiManagement** dan **New-AzApiManagement** .

## EXAMPLES

### Contoh 1: Membuat jaringan virtual dan Memperbarui layanan APIM yang ada ke VNET
```powershell
$virtualNetwork = New-AzApiManagementVirtualNetwork -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-a1e8-3726ab15d0e2/resourceGroups/Api-Default-WestUS/providers/Microsoft.Network/virtualNetworks/dfVirtualNetwork/subnets/backendSubnet"
$apim = Get-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
$apim.VpnType = "External"
$apim.VirtualNetwork = $virtualNetwork
Set-AzApiManagement -InputObject $apim
```

Contoh ini membuat jaringan virtual lalu memanggil cmdlet **Set-AzApiManagement** .

### Contoh 2: Membuat layanan API Management untuk jaringan virtual eksternal
```powershell
$virtualNetwork = New-AzApiManagementVirtualNetwork -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-b1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/westUsVirtualNetwork/subnets/backendSubnet"
New-AzApiManagement -ResourceGroupName "ContosoGroup" -Location "West US" -Name "ContosoApi" -Organization Contoso -AdminEmail admin@contoso.com -VirtualNetwork $virtualNetwork -VpnType "External" -Sku "Premium"
```

Contoh ini membuat layanan APIM baru ke dalam Virtual Network dalam `External` mode

## PARAMETERS

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

### -SubnetResourceId
Menentukan ID sumber daya subnet dari jaringan virtual.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork

## NOTES

## RELATED LINKS

[Set-AzApiManagement](./Set-AzApiManagement.md)
 [New-AzApiManagement](./New-AzApiManagement.md)

