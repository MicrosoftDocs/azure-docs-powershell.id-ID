---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 5B7B285A-6418-44D7-BD78-E14AFFAA7765
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/update-azapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Update-AzApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Update-AzApiManagementRegion.md
ms.openlocfilehash: cd9b252ad5d0ad6dca2ce6a575ad5e0645e3a15f
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145498928"
---
# Update-AzApiManagementRegion

## SYNOPSIS
Memperbarui wilayah penyebaran yang ada di instans PsApiManagement.

## SYNTAX

```
Update-AzApiManagementRegion -ApiManagement <PsApiManagement> -Location <String> -Sku <PsApiManagementSku>
 -Capacity <Int32> [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-Zone <String[]>]
 [-DisableGateway <Boolean>] [-PublicIpAddressId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzApiManagementRegion** memperbarui instans jenis **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** yang ada dalam kumpulan objek **AdditionalRegions dari instans** jenis **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
Cmdlet ini tidak menyebarkan apa pun kecuali memperbarui **instans PsApiManagement** dalam memori.
Untuk memperbarui penyebaran API Management gunakan **PsApiManagementInstance** yang dimodifikasi ke cmdlet Set-AzApiManagement.

## EXAMPLES

### Contoh 1: Meningkatkan kapasitas Wilayah Tambahan dalam instans PsApiManagement
```powershell
$apimService = Get-AzApiManagement -ResourceGroupName $resourceGroupName -Name $apiManagementName
$apimService = Update-AzApiManagementRegion -ApiManagement $apimService -Location "North Central US" -Capacity 2 -Sku Premium
$apimService = Set-AzApiManagement -InputObject $apimService -PassThru
```

Perintah ini mendapatkan layanan SKU API Management Premium, memiliki wilayah di US Tengah Selatan dan US Tengah Utara. Kemudian meningkatkan Kapasitas wilayah US Tengah Utara menjadi 2 menggunakan **Set-AzApiManagement**. Cmdlet berikutnya **Set-AzApiManagement** menerapkan perubahan konfigurasi ke layanan Api Management.

### Contoh 2

Memperbarui wilayah penyebaran yang ada di instans PsApiManagement. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Update-AzApiManagementRegion -ApiManagement <PsApiManagement> -Capacity 2 -Location 'North Central US' -Sku Developer -VirtualNetwork <PsApiManagementVirtualNetwork>
```

## PARAMETERS

### -ApiManagement
Menentukan **instans PsApiManagement** untuk memperbarui wilayah penyebaran yang ada.

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
Menentukan nilai kapasitas SKU baru untuk wilayah penyebaran.

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
Menentukan lokasi wilayah penyebaran yang akan diperbarui.
Menentukan lokasi wilayah penyebaran baru di antara wilayah yang didukung untuk layanan Api Management.
Untuk mendapatkan lokasi yang valid, gunakan cmdlet Get-AzResourceProvider -ProviderNamespace "Microsoft.ApiManagement" | di mana {$_. ResourceTypes[0]. ResourceTypeName -eq "service"} | Lokasi Select-Object

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

### -PublicIpAddressId
PublicIpAddress ResoureId SKU Standar untuk integrasi ke dalam Stv2 Virtual Network Deployments

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Menentukan nilai tingkat baru untuk wilayah penyebaran.
Nilai yang valid adalah:
- Pengembang
- Standard
- Premium

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku
Parameter Sets: (All)
Aliases:
Accepted values: Developer, Standard, Premium, Basic, Consumption, Isolated

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetwork
Menentukan konfigurasi jaringan virtual untuk wilayah penyebaran.
Melewati $null akan menghapus konfigurasi jaringan virtual untuk wilayah tersebut.

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

### System.String

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku

### System.Int32

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Add-AzApiManagementRegion](./Add-AzApiManagementRegion.md)

[Remove-AzApiManagementRegion](./Remove-AzApiManagementRegion.md)

[Set-AzApiManagement](./Set-AzApiManagement.md)
