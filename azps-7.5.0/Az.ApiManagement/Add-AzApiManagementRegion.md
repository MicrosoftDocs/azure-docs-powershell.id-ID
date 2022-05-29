---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 9D4A68A8-0A39-4C9A-8EA6-391A5E7A0E25
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/add-azapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Add-AzApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Add-AzApiManagementRegion.md
ms.openlocfilehash: e431bb313ce3343fa169e69ee589dbceab529684
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145731772"
---
# Add-AzApiManagementRegion

## SYNOPSIS
Menambahkan wilayah penyebaran baru ke instans PsApiManagement.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/add-azapimanagementregion) untuk informasi terbaru.

## SYNTAX

```
Add-AzApiManagementRegion -ApiManagement <PsApiManagement> -Location <String> [-Sku <PsApiManagementSku>]
 [-Capacity <Int32>] [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-Zone <String[]>]
 [-DisableGateway <Boolean>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzApiManagementRegion** menambahkan instans baru jenis **PsApiManagementRegion** ke kumpulan **AdditionalRegions dari instans** yang disediakan dari jenis **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
Cmdlet ini tidak menyebarkan apa pun dengan sendirinya tetapi memperbarui **instans PsApiManagement** dalam memori.
Untuk memperbarui penyebaran API Management meneruskan **Instans PsApiManagement** yang dimodifikasi ke Set-AzApiManagement.

## EXAMPLES

### Contoh 1: Menambahkan wilayah penyebaran baru ke instans PsApiManagement
```powershell
Add-AzApiManagementRegion -ApiManagement $ApiManagement -Location "East US" -Sku "Premium" -Capacity 2
```

Perintah ini menambahkan dua unit SKU premium dan wilayah bernama US Timur ke **instans PsApiManagement** .

### Contoh 2: Tambahkan wilayah penyebaran baru ke instans PsApiManagement lalu perbarui penyebaran
```powershell
$service = Get-AzApiManagement -ResourceGroupName "Contoso" -Name "ContosoApi"
$service = Add-AzApiManagementRegion -ApiManagement $service -Location $secondarylocation -VirtualNetwork $additionalRegionVirtualNetwork
$service = Set-AzApiManagement -InputObject $service -PassThru
```

Perintah ini mendapatkan objek **PsApiManagement** , menambahkan dua unit SKU premium untuk wilayah bernama US Timur, lalu memperbarui penyebaran.

## PARAMETERS

### -ApiManagement
Menentukan **instans PsApiManagement** tempat cmdlet ini menambahkan wilayah penyebaran tambahan.

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
Menentukan kapasitas SKU wilayah penyebaran.

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
Bendera hanya dimaksudkan untuk digunakan untuk Premium SKU ApiManagement Service dan penyebaran VNET Non Internal. Ini berguna jika kita ingin mengeluarkan wilayah gateway dari rotasi. Ini juga dapat digunakan untuk berdiri di wilayah baru dalam mode Pasif, mengujinya dan kemudian membuatnya Langsung nanti.
Perilaku default adalah membuat wilayah langsung.

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
Menentukan lokasi wilayah penyebaran baru di antara wilayah yang didukung untuk layanan Api Management.
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

### -Sku
Menentukan tingkat wilayah penyebaran.
Nilai yang valid adalah: 
- Pengembang
- Standard
- Premium

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku]
Parameter Sets: (All)
Aliases:
Accepted values: Developer, Standard, Premium, Basic, Consumption, Isolated

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Menentukan konfigurasi jaringan virtual.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zona
Daftar zona ketersediaan yang menunjukkan tempat layanan manajemen api disebarkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES
* Cmdlet menulis **instans PsApiManagement yang** diperbarui ke alur.

## RELATED LINKS

[Remove-AzApiManagementRegion](./Remove-AzApiManagementRegion.md)

[Update-AzApiManagementRegion](./Update-AzApiManagementRegion.md)

[Set-AzApiManagement](./Set-AzApiManagement.md)


