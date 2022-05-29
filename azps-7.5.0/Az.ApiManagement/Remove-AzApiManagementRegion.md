---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 17D7EBD2-FE3F-4D24-A1AA-8C45B9B1FEF5
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/remove-azapimanagementregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Remove-AzApiManagementRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Remove-AzApiManagementRegion.md
ms.openlocfilehash: 9338affea3d81b6fc6ece5fac2428aa4258d5475
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145818746"
---
# Remove-AzApiManagementRegion

## SYNOPSIS
Menghapus wilayah penyebaran yang ada dari instans PsApiManagement.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/remove-azapimanagementregion) untuk informasi terbaru.

## SYNTAX

```
Remove-AzApiManagementRegion -ApiManagement <PsApiManagement> -Location <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzApiManagementRegion** menghapus instans jenis **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** dari kumpulan **AdditionalRegions** asalkan instans jenis **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
Cmdlet ini tidak memodifikasi penyebaran dengan sendirinya tetapi memperbarui **instans PsApiManagement** dalam memori.
Untuk memperbarui penyebaran API Management, lewati **PsApiManagementInstance** yang dimodifikasi ke **Set-AzApiManagement**.

## EXAMPLES

### Contoh 1: Menghapus wilayah dari instans PsApiManagement
```powershell
Remove-AzApiManagementRegion -ApiManagement $ApiManagement -Location "East US"
```

Perintah ini menghapus wilayah bernama US Timur dari **instans PsApiManagement** .

### Contoh 2: Menghapus wilayah dari instans PsApiManagement menggunakan serangkaian perintah
```powershell
Get-AzApiManagement -ResourceGroupName "Contoso" -Name ContosoApi | Remove-AzApiManagementRegion -Location "East US" | Set-AzApiManagement
```

Perintah pertama ini mendapatkan **instans PsApiManagement** dari grup sumber daya bernama Contoso bernama ContosoApi.
Perintah akhir kemudian menghapus wilayah bernama US Timur dari instans tersebut kemudian memperbarui penyebaran.

## PARAMETERS

### -ApiManagement
Menentukan **instans PsApiManagement** tempat cmdlet ini menghapus wilayah penyebaran tambahan.

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

### -DefaultProfile

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

### -Lokasi
Menentukan lokasi wilayah yang dihapus cmdlet ini.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Add-AzApiManagementRegion](./Add-AzApiManagementRegion.md)

[Update-AzApiManagementRegion](./Update-AzApiManagementRegion.md)


