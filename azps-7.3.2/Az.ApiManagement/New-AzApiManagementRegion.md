---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: A4226BFB-AB3B-4883-9D52-5EB7F29D8A71
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementRegion.md
ms.openlocfilehash: 4ac88ae008b9cb6bc239b4ccf06dab6ba94aceb9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142115549"
---
# New-AzApiManagementRegion

## SYNOPSIS
Membuat contoh PsApiManagementRegion.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementregion) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementRegion -Location <String> [-Capacity <Int32>]
 [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-Zone <String[]>] [-DisableGateway <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah Helper untuk membuat contoh PsApiManagementRegion.
Perintah ini akan digunakan dengan perintah New-AzApiManagement.

## EXAMPLES

### Contoh 1
```powershell
$apimRegion = New-AzApiManagementRegion -Location "Central US" 

$additionalRegions = @($apimRegion)

New-AzApiManagement -ResourceGroupName ContosoGroup -Location "West US" -Name ContosoApi -Organization Contoso -AdminEmail admin@contoso.com -AdditionalRegions $additionalRegions -Sku "Premium"
```

### Contoh 2
```powershell
$apimRegionVirtualNetwork = New-AzApiManagementVirtualNetwork -Location "Central US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/centralusvirtualNetwork/subnets/backendSubnet"

$apimRegion = New-AzApiManagementRegion -Location "Central US" -VirtualNetwork $apimRegionVirtualNetwork 

$additionalRegions = @($apimRegion)

$virtualNetwork = New-AzApiManagementVirtualNetwork -Location "West US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc2-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/westUsVirtualNetwork/subnets/backendSubnet"

New-AzApiManagement -ResourceGroupName ContosoGroup -Location "West US" -Name ContosoApi -Organization Contoso -AdminEmail admin@contoso.com -AdditionalRegions $additionalRegions -VirtualNetwork $virtualNetwork -VpnType "External" -Sku "Premium"
```

Membuat layanan ApiManagement VpnType Eksternal di Kawasan AS Barat, dengan Kawasan Tambahan di AS Tengah.

## PARAMETERS

### -Kapasitas
Kapasitas Sku dari kawasan tambahan layanan azure API Management.
Nilai defaultnya adalah 1.

```yaml
Type: System.Nullable`1[System.Int32]
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

### -DisableGateway
Bendera hanya dimaksudkan untuk digunakan untuk Premium penyebaran SKU ApiManagement Service dan Non Internal VNET. Ini berguna jika kami ingin mengeluarkan kawasan gateway dari rotasi. Ini juga dapat digunakan untuk berdiri di kawasan baru dalam mode Pasif, mengujinya lalu membuatnya Langsung nanti.
Perilaku defaultnya adalah membuat kawasan langsung hidup.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi kawasan penyebaran baru di antara kawasan yang didukung untuk layanan Manajemen Api.
Untuk mendapatkan lokasi yang valid, gunakan cmdlet Get-AzResourceProvider -ProviderNamespace "Microsoft.ApiManagement" | di mana {$_. ResourceTypes[0]. ResourceTypeName -eq "service"} | Lokasi Select-Object

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

### -VirtualNetwork
Virtual Network Konfigurasi wilayah penyebaran Azure API Management.
Nilai default adalah $null.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona
Daftar zona ketersediaan yang mencantumkan tempat layanan manajemen api disebarkan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion

## CATATAN

## RELATED LINKS
