---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 9D4A68A8-0A39-4C9A-8EA6-391A5E7A0E25
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/add-azapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Add-AzApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Add-AzApiManagementRegion.md
ms.openlocfilehash: 6b1fa0713e70b8236ac81fba68cc6d35e6270fef
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143099297"
---
# Add-AzApiManagementRegion

## SYNOPSIS
Menambahkan kawasan penyebaran baru ke instans PsApiManagement.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/add-azapimanagementregion) untuk informasi terbaru.

## SYNTAX

```
Add-AzApiManagementRegion -ApiManagement <PsApiManagement> -Location <String> [-Sku <PsApiManagementSku>]
 [-Capacity <Int32>] [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-Zone <String[]>]
 [-DisableGateway <Boolean>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzApiManagementRegion** menambahkan **instans baru tipe PsApiManagementRegion** ke kumpulan **AdditionalRegions dari instans** yang disediakan dari tipe **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
Cmdlet ini tidak menyebarkan apa pun dengan sendirinya tetapi memperbarui contoh **PsApiManagement** dalam memori.
Untuk memperbarui penyebaran API Management melewati **Instans PsApiManagement** yang dimodifikasi ke Set-AzApiManagement.

## EXAMPLES

### Contoh 1: Menambahkan kawasan penyebaran baru ke instans PsApiManagement
```
PS C:\>Add-AzApiManagementRegion -ApiManagement $ApiManagement -Location "East US" -Sku "Premium" -Capacity 2
```

Perintah ini menambahkan dua unit SKU premium dan kawasan bernama East US ke **instans PsApiManagement** .

### Contoh 2: Tambahkan kawasan penyebaran baru ke instans PsApiManagement lalu perbarui penyebaran
```powershell
PS C:\>$service = Get-AzApiManagement -ResourceGroupName "Contoso" -Name "ContosoApi"
PS C:\>$service = Add-AzApiManagementRegion -ApiManagement $service -Location $secondarylocation -VirtualNetwork $additionalRegionVirtualNetwork
PS C:\>$service = Set-AzApiManagement -InputObject $service -PassThru
```

Perintah ini mendapatkan objek **PsApiManagement** , menambahkan dua unit SKU premium untuk kawasan bernama As timur, lalu memperbarui penyebaran.

## PARAMETERS

### -ApiManagement
Menentukan **instans PsApiManagement** tempat cmdlet ini menambahkan area penyebaran tambahan.

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
Menentukan kapasitas SKU dari wilayah penyebaran.

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

### -Sku
Menentukan tingkat wilayah penyebaran.
Nilai yang valid adalah: 
- Pengembang
- Standar
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

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES
* Cmdlet menulis **instans PsApiManagement** yang diperbarui ke pipeline.

## RELATED LINKS

[Remove-AzApiManagementRegion](./Remove-AzApiManagementRegion.md)

[Update-AzApiManagementRegion](./Update-AzApiManagementRegion.md)

[Set-AzApiManagement](./Set-AzApiManagement.md)


