---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
Module Name: AzureRM.ApiManagement
ms.assetid: A4226BFB-AB3B-4883-9D52-5EB7F29D8A71
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.apimanagement/new-azurermapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/New-AzureRmApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/New-AzureRmApiManagementRegion.md
ms.openlocfilehash: 8d292f6e03661ae55a63686a0282ce65292087f5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142796428"
---
# New-AzureRmApiManagementRegion

## SYNOPSIS
Membuat contoh PsApiManagementRegion.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmApiManagementRegion -Location <String> [-Capacity <Int32>]
 [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Perintah Helper untuk membuat contoh PsApiManagementRegion.
Perintah ini akan digunakan dengan perintah New-AzureRmApiManagement.

## EXAMPLES

### Contoh 1
```
$apimRegion = New-AzureRmApiManagementRegion -Location "Central US" 

$additionalRegions = @($apimRegion)

New-AzureRmApiManagement -ResourceGroupName ContosoGroup -Location "West US" -Name ContosoApi -Organization Contoso -AdminEmail admin@contoso.com -AdditionalRegions $additionalRegions -Sku "Premium"
```

### Contoh 2
```
$apimRegionVirtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location "Central US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/centralusvirtualNetwork/subnets/backendSubnet"

$apimRegion = New-AzureRmApiManagementRegion -Location "Central US" -VirtualNetwork $apimRegionVirtualNetwork 

$additionalRegions = @($apimRegion)

$virtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location "West US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc2-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/westUsVirtualNetwork/subnets/backendSubnet"

New-AzureRmApiManagement -ResourceGroupName ContosoGroup -Location "West US" -Name ContosoApi -Organization Contoso -AdminEmail admin@contoso.com -AdditionalRegions $additionalRegions -VirtualNetwork $virtualNetwork -VpnType "External" -Sku "Premium"
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi kawasan penyebaran baru di antara kawasan yang didukung untuk layanan Manajemen Api.
Untuk mendapatkan lokasi yang valid, gunakan cmdlet Get-AzureRmResourceProvider -ProviderNamespace "Microsoft.ApiManagement" | di mana {$_. ResourceTypes[0]. ResourceTypeName -eq "service"} | Lokasi Select-Object

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion

## NOTES

## RELATED LINKS
