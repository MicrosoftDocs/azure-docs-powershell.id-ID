---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
Module Name: AzureRM.ApiManagement
ms.assetid: 5B7B285A-6418-44D7-BD78-E14AFFAA7765
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.apimanagement/update-azurermapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Update-AzureRmApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Update-AzureRmApiManagementRegion.md
ms.openlocfilehash: ed26538e54cef189837bd36bf9e6f561df3541f4
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427638"
---
# Update-AzureRmApiManagementRegion

## SYNOPSIS
Memperbarui kawasan penyebaran yang sudah ada dalam contoh PsApiManagement.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Update-AzureRmApiManagementRegion -ApiManagement <PsApiManagement> -Location <String> -Sku <PsApiManagementSku>
 -Capacity <Int32> [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzureRmApiManagementRegion** memperbarui instans tipe yang sudah ada dari tipe **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** dalam kumpulan objek **AdditionalRegions** yang disediakan dari tipe **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
Cmdlet ini tidak menyebarkan apa pun selain memperbarui contoh **in-memory PsApiManagement.**
Untuk memperbarui penyebaran Manajemen API, gunakan **PsApiManagementInstance yang dimodifikasi** ke cmdlet Update-AzureRmApiManagementDeployment cmdlet.

## EXAMPLES

## PARAMETERS

### -ApiManagement
Menentukan instans **PsApiManagement** untuk memperbarui kawasan penyebaran yang sudah ada di.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Kapasitas
Menentukan nilai kapasitas SKU baru untuk kawasan penyebaran.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -Lokasi
Menentukan lokasi wilayah penyebaran untuk diperbarui.
Menentukan lokasi wilayah penyebaran baru di antara kawasan yang didukung untuk layanan Manajemen Api.
Untuk mendapatkan lokasi yang valid, gunakan cmdlet Get-AzureRmResourceProvider -ProviderNamespace "Microsoft.ApiManagement" | di mana {$_. ResourceTypes[0]. ResourceTypeName -eq "service"} | Select-Object Lokasi

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

### -Sku
Menentukan nilai tingkatan baru untuk kawasan penyebaran.
Nilai valid adalah:
- Pengembang
- Standar
- Premium

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku
Parameter Sets: (All)
Aliases:
Accepted values: Developer, Standard, Premium, Basic

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetwork
Menentukan konfigurasi jaringan virtual untuk kawasan penyebaran.
Memberikan $null akan menghapus konfigurasi jaringan virtual untuk kawasan tersebut.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement
Parameter: ApiManagement (ByValue)

### System.String

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku

### System.Int32

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## CATATAN

## RELATED LINKS

[Add-AzureRmApiManagementRegion](./Add-AzureRmApiManagementRegion.md)

[Remove-AzureRmApiManagementRegion](./Remove-AzureRmApiManagementRegion.md)

[Update-AzureRmApiManagementDeployment](./Update-AzureRmApiManagementDeployment.md)
